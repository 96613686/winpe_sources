# BackupSingleFile(_FILELIST *,_BAKDATA *)

- ea: `0x1800156b8`
- end: `0x18001591b`
- name: `?BackupSingleFile@@YAHPEAU_FILELIST@@PEAU_BAKDATA@@@Z`
- size: `611`
- prototype: `__int64 __fastcall(LPCWSTR *, struct _BAKDATA *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800152d8`

## callees

- `0x180014e30`
- `0x1800156b8`
- `0x180015924`
- `0x1800172dc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800158f4`
- `KERNEL32!LocalFree` at `0x180015902`
- `KERNEL32!LocalFree` at `0x1800158f4`
- `KERNEL32!LocalFree` at `0x180015902`
- `KERNEL32!CreateFileW` at `0x180015756`
- `KERNEL32!CreateFileW` at `0x180015756`
- `KERNEL32!WriteFile` at `0x1800157a6`
- `KERNEL32!WriteFile` at `0x180015851`
- `KERNEL32!WriteFile` at `0x18001587a`
- `KERNEL32!WriteFile` at `0x180015895`
- `KERNEL32!WriteFile` at `0x1800157a6`
- `KERNEL32!WriteFile` at `0x180015851`
- `KERNEL32!WriteFile` at `0x18001587a`
- `KERNEL32!WriteFile` at `0x180015895`
- `KERNEL32!CloseHandle` at `0x1800158be`
- `KERNEL32!CloseHandle` at `0x1800158be`
- `KERNEL32!LocalAlloc` at `0x180015705`
- `KERNEL32!LocalAlloc` at `0x180015716`
- `KERNEL32!LocalAlloc` at `0x180015705`
- `KERNEL32!LocalAlloc` at `0x180015716`
- `KERNEL32!GetFileSize` at `0x180015788`
- `KERNEL32!GetFileSize` at `0x180015788`
- `KERNEL32!GetFileTime` at `0x18001577d`
- `KERNEL32!GetFileTime` at `0x18001577d`
- `KERNEL32!ReadFile` at `0x1800157e4`
- `KERNEL32!ReadFile` at `0x1800157e4`

## pseudocode

```c
__int64 __fastcall BackupSingleFile(LPCWSTR *a1, struct _BAKDATA *a2)
{
  unsigned int v2; // eax
  HLOCAL v5; // r14
  HLOCAL v6; // rax
  void *v7; // r15
  HANDLE FileW; // rax
  void *v9; // r13
  unsigned int v10; // ebx
  BOOL v11; // r12d
  unsigned int v12; // esi
  unsigned int v13; // r10d
  DWORD v14; // eax
  DWORD v15; // esi
  void *v16; // rcx
  void *v17; // rcx
  BOOL v18; // eax
  unsigned int v20; // [rsp+40h] [rbp-28h]
  unsigned int v21; // [rsp+44h] [rbp-24h]
  DWORD FileSize; // [rsp+48h] [rbp-20h]
  struct _FILETIME LastWriteTime; // [rsp+50h] [rbp-18h] BYREF
  DWORD NumberOfBytesRead; // [rsp+B8h] [rbp+50h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+C0h] [rbp+58h] BYREF
  DWORD Buffer; // [rsp+C8h] [rbp+60h] BYREF

  v2 = *((_DWORD *)a2 + 2);
  Buffer = 1347045187;
  v21 = v2;
  NumberOfBytesWritten = 0;
  LastWriteTime = 0;
  NumberOfBytesRead = 0x8000;
  v5 = LocalAlloc(0x40u, 0x8020u);
  v6 = LocalAlloc(0x40u, NumberOfBytesRead + 32);
  v7 = v6;
  if ( v5 && v6 )
  {
    FileW = CreateFileW(*a1, 0x80000000, 3u, 0, 3u, 0x80u, 0);
    v9 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v10 = 0;
    }
    else
    {
      v11 = 0;
      v12 = 0;
      GetFileTime(FileW, 0, 0, &LastWriteTime);
      FileSize = GetFileSize(v9, 0);
      if ( WriteFile(*(HANDLE *)a2, &Buffer, 4u, &NumberOfBytesWritten, 0) )
      {
        *((_DWORD *)a2 + 2) += 4;
        v10 = 1;
      }
      else
      {
        NumberOfBytesRead = 0;
        v10 = 0;
      }
      while ( NumberOfBytesRead == 0x8000 )
      {
        if ( !ReadFile(v9, v5, 0x8000u, &NumberOfBytesRead, 0) )
          goto LABEL_23;
        if ( !NumberOfBytesRead )
          break;
        v20 = CRC32Compute((unsigned __int8 *)v5, NumberOfBytesRead, v12);
        v14 = Mrci1MaxCompress(v5, v13, v7);
        v15 = v14;
        if ( v14 == -1 || v14 >= NumberOfBytesRead )
          v15 = 0;
        v16 = *(void **)a2;
        Buffer = NumberOfBytesRead | (v15 << 16);
        if ( !WriteFile(v16, &Buffer, 4u, &NumberOfBytesWritten, 0) )
          goto LABEL_22;
        *((_DWORD *)a2 + 2) += 4;
        v17 = *(void **)a2;
        if ( v15 )
        {
          if ( !WriteFile(v17, v7, v15, &NumberOfBytesWritten, 0) )
          {
            v11 = 1;
LABEL_22:
            v12 = v20;
LABEL_23:
            v10 = 0;
            break;
          }
          v11 = 0;
        }
        else
        {
          v18 = WriteFile(v17, v5, NumberOfBytesRead, &NumberOfBytesWritten, 0);
          v11 = !v18;
          if ( !v18 )
            goto LABEL_22;
        }
        *((_DWORD *)a2 + 2) += NumberOfBytesWritten;
        v12 = v20;
      }
      CloseHandle(v9);
      if ( !v11 )
        DosPrintf(a2, (struct _FILELIST *)a1, FileSize, LastWriteTime, v21, v12);
    }
  }
  else
  {
    v10 = 0;
    if ( !v6 )
      goto LABEL_28;
  }
  LocalFree(v7);
LABEL_28:
  if ( v5 )
    LocalFree(v5);
  return v10;
}

```

## disassembly

```asm
0x1800156b8  mov     [rsp-40h+arg_0], rcx
0x1800156bd  push    rbp
0x1800156be  push    rbx
0x1800156bf  push    rsi
0x1800156c0  push    rdi
0x1800156c1  push    r12
0x1800156c3  push    r13
0x1800156c5  push    r14
0x1800156c7  push    r15
0x1800156c9  mov     rbp, rsp
0x1800156cc  sub     rsp, 68h
0x1800156d0  mov     eax, [rdx+8]
0x1800156d3  mov     rdi, rdx
0x1800156d6  mov     rsi, rcx
0x1800156d9  mov     [rbp+Buffer], 504A4743h
0x1800156e0  mov     ebx, 40h ; '@'
0x1800156e5  mov     [rbp+var_24], eax
0x1800156e8  mov     ecx, ebx; uFlags
0x1800156ea  mov     [rbp+NumberOfBytesWritten], 0
0x1800156f1  mov     edx, 8020h; uBytes
0x1800156f6  mov     qword ptr [rbp+LastWriteTime.dwLowDateTime], 0
0x1800156fe  mov     [rbp+NumberOfBytesRead], 8000h
0x180015705  call    cs:__imp_LocalAlloc
0x18001570b  mov     edx, [rbp+NumberOfBytesRead]
0x18001570e  mov     ecx, ebx; uFlags
0x180015710  add     edx, 20h ; ' '; uBytes
0x180015713  mov     r14, rax
0x180015716  call    cs:__imp_LocalAlloc
0x18001571c  mov     r15, rax
0x18001571f  test    r14, r14
0x180015722  jz      loc_1800158EA
0x180015728  test    rax, rax
0x18001572b  jz      loc_1800158EA
0x180015731  mov     rcx, [rsi]; lpFileName
0x180015734  lea     r8d, [rbx-3Dh]; dwShareMode
0x180015738  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180015741  xor     r9d, r9d; lpSecurityAttributes
0x180015744  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001574c  mov     edx, 80000000h; dwDesiredAccess
0x180015751  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x180015756  call    cs:__imp_CreateFileW
0x18001575c  mov     r13, rax
0x18001575f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015763  jnz     short loc_18001576C
0x180015765  xor     ebx, ebx
0x180015767  jmp     loc_1800158F1
0x18001576c  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x180015770  xor     r8d, r8d; lpLastAccessTime
0x180015773  xor     edx, edx; lpCreationTime
0x180015775  mov     rcx, r13; hFile
0x180015778  xor     r12d, r12d
0x18001577b  xor     esi, esi
0x18001577d  call    cs:__imp_GetFileTime
0x180015783  xor     edx, edx; lpFileSizeHigh
0x180015785  mov     rcx, r13; hFile
0x180015788  call    cs:__imp_GetFileSize
0x18001578e  mov     rcx, [rdi]; hFile
0x180015791  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180015795  lea     r8d, [r12+4]; nNumberOfBytesToWrite
0x18001579a  mov     [rbp+var_20], eax
0x18001579d  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800157a1  mov     qword ptr [rsp+68h+dwCreationDisposition], rsi; lpOverlapped
0x1800157a6  call    cs:__imp_WriteFile
0x1800157ac  test    eax, eax
0x1800157ae  jnz     short loc_1800157B7
0x1800157b0  mov     [rbp+NumberOfBytesRead], esi
0x1800157b3  xor     ebx, ebx
0x1800157b5  jmp     short loc_1800157C0
0x1800157b7  add     dword ptr [rdi+8], 4
0x1800157bb  mov     ebx, 1
0x1800157c0  mov     eax, 8000h
0x1800157c5  cmp     [rbp+NumberOfBytesRead], eax
0x1800157c8  jnz     loc_1800158BB
0x1800157ce  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800157d2  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x1800157db  mov     r8d, eax; nNumberOfBytesToRead
0x1800157de  mov     rdx, r14; lpBuffer
0x1800157e1  mov     rcx, r13; hFile
0x1800157e4  call    cs:__imp_ReadFile
0x1800157ea  test    eax, eax
0x1800157ec  jz      loc_1800158B9
0x1800157f2  mov     r10d, [rbp+NumberOfBytesRead]
0x1800157f6  test    r10d, r10d
0x1800157f9  jz      loc_1800158BB
0x1800157ff  mov     r8d, esi; unsigned int
0x180015802  mov     edx, r10d; unsigned int
0x180015805  mov     rcx, r14; unsigned __int8 *
0x180015808  call    ?CRC32Compute@@YAKPEAEIK@Z; CRC32Compute(uchar *,uint,ulong)
0x18001580d  mov     r8, r15
0x180015810  mov     [rbp+var_28], eax
0x180015813  mov     edx, r10d
0x180015816  mov     rcx, r14
0x180015819  call    Mrci1MaxCompress
0x18001581e  mov     esi, eax
0x180015820  cmp     eax, 0FFFFFFFFh
0x180015823  jz      short loc_18001582A
0x180015825  cmp     eax, [rbp+NumberOfBytesRead]
0x180015828  jb      short loc_18001582C
0x18001582a  xor     esi, esi
0x18001582c  mov     rcx, [rdi]; hFile
0x18001582f  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180015833  mov     eax, esi
0x180015835  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x18001583e  shl     eax, 10h
0x180015841  lea     rdx, [rbp+Buffer]; lpBuffer
0x180015845  or      eax, [rbp+NumberOfBytesRead]
0x180015848  mov     r8d, 4; nNumberOfBytesToWrite
0x18001584e  mov     [rbp+Buffer], eax
0x180015851  call    cs:__imp_WriteFile
0x180015857  test    eax, eax
0x180015859  jz      short loc_1800158B6
0x18001585b  add     dword ptr [rdi+8], 4
0x18001585f  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180015863  mov     rcx, [rdi]; hFile
0x180015866  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x18001586f  test    esi, esi
0x180015871  jnz     short loc_18001588F
0x180015873  mov     r8d, [rbp+NumberOfBytesRead]; nNumberOfBytesToWrite
0x180015877  mov     rdx, r14; lpBuffer
0x18001587a  call    cs:__imp_WriteFile
0x180015880  xor     r12d, r12d
0x180015883  test    eax, eax
0x180015885  setz    r12b
0x180015889  test    eax, eax
0x18001588b  jz      short loc_1800158B6
0x18001588d  jmp     short loc_1800158A2
0x18001588f  mov     r8d, esi; nNumberOfBytesToWrite
0x180015892  mov     rdx, r15; lpBuffer
0x180015895  call    cs:__imp_WriteFile
0x18001589b  test    eax, eax
0x18001589d  jz      short loc_1800158B0
0x18001589f  xor     r12d, r12d
0x1800158a2  mov     eax, [rbp+NumberOfBytesWritten]
0x1800158a5  add     [rdi+8], eax
0x1800158a8  mov     esi, [rbp+var_28]
0x1800158ab  jmp     loc_1800157C0
0x1800158b0  mov     r12d, 1
0x1800158b6  mov     esi, [rbp+var_28]
0x1800158b9  xor     ebx, ebx
0x1800158bb  mov     rcx, r13; hObject
0x1800158be  call    cs:__imp_CloseHandle
0x1800158c4  test    r12d, r12d
0x1800158c7  jnz     short loc_1800158F1
0x1800158c9  mov     eax, [rbp+var_24]
0x1800158cc  mov     rcx, rdi; struct _BAKDATA *
0x1800158cf  mov     r9, qword ptr [rbp+LastWriteTime.dwLowDateTime]; struct _FILETIME
0x1800158d3  mov     r8d, [rbp+var_20]; unsigned int
0x1800158d7  mov     rdx, [rbp+arg_0]; struct _FILELIST *
0x1800158db  mov     [rsp+68h+dwFlagsAndAttributes], esi; unsigned int
0x1800158df  mov     [rsp+68h+dwCreationDisposition], eax; unsigned int
0x1800158e3  call    ?DosPrintf@@YAHPEAU_BAKDATA@@PEAU_FILELIST@@KU_FILETIME@@KK@Z; DosPrintf(_BAKDATA *,_FILELIST *,ulong,_FILETIME,ulong,ulong)
0x1800158e8  jmp     short loc_1800158F1
0x1800158ea  xor     ebx, ebx
0x1800158ec  test    r15, r15
0x1800158ef  jz      short loc_1800158FA
0x1800158f1  mov     rcx, r15; hMem
0x1800158f4  call    cs:__imp_LocalFree
0x1800158fa  test    r14, r14
0x1800158fd  jz      short loc_180015908
0x1800158ff  mov     rcx, r14; hMem
0x180015902  call    cs:__imp_LocalFree
0x180015908  mov     eax, ebx
0x18001590a  add     rsp, 68h
0x18001590e  pop     r15
0x180015910  pop     r14
0x180015912  pop     r13
0x180015914  pop     r12
0x180015916  pop     rdi
0x180015917  pop     rsi
0x180015918  pop     rbx
0x180015919  pop     rbp
0x18001591a  retn
```
