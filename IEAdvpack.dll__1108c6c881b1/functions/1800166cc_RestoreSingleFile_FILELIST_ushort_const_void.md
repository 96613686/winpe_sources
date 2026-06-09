# RestoreSingleFile(_FILELIST *,ushort const *,void *)

- ea: `0x1800166cc`
- end: `0x180016a2a`
- name: `?RestoreSingleFile@@YAHPEAU_FILELIST@@PEBGPEAX@Z`
- size: `862`
- prototype: `__int64 __fastcall(FILETIME *, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016268`

## callees

- `0x1800022bc`
- `0x18000521c`
- `0x180014cb8`
- `0x1800166cc`
- `0x1800172dc`
- `0x18001b980`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800169ea`
- `KERNEL32!LocalFree` at `0x1800169f8`
- `KERNEL32!LocalFree` at `0x1800169ea`
- `KERNEL32!LocalFree` at `0x1800169f8`
- `KERNEL32!CreateFileW` at `0x180016788`
- `KERNEL32!CreateFileW` at `0x1800167ee`
- `KERNEL32!CreateFileW` at `0x180016788`
- `KERNEL32!CreateFileW` at `0x1800167ee`
- `KERNEL32!WriteFile` at `0x18001695e`
- `KERNEL32!WriteFile` at `0x18001695e`
- `KERNEL32!CloseHandle` at `0x1800169b4`
- `KERNEL32!CloseHandle` at `0x1800169b4`
- `KERNEL32!LocalAlloc` at `0x18001673a`
- `KERNEL32!LocalAlloc` at `0x18001674a`
- `KERNEL32!LocalAlloc` at `0x18001673a`
- `KERNEL32!LocalAlloc` at `0x18001674a`
- `KERNEL32!SetFilePointer` at `0x180016814`
- `KERNEL32!SetFilePointer` at `0x180016814`
- `KERNEL32!DeleteFileW` at `0x1800169d5`
- `KERNEL32!DeleteFileW` at `0x1800169d5`
- `KERNEL32!ReadFile` at `0x18001683b`
- `KERNEL32!ReadFile` at `0x180016891`
- `KERNEL32!ReadFile` at `0x1800168e0`
- `KERNEL32!ReadFile` at `0x180016904`
- `KERNEL32!ReadFile` at `0x18001683b`
- `KERNEL32!ReadFile` at `0x180016891`
- `KERNEL32!ReadFile` at `0x1800168e0`
- `KERNEL32!ReadFile` at `0x180016904`
- `KERNEL32!SetFileTime` at `0x1800169ab`
- `KERNEL32!SetFileTime` at `0x1800169ab`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800167b3`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800167b3`

## pseudocode

```c
__int64 __fastcall RestoreSingleFile(FILETIME *a1, const unsigned __int16 *a2, void *a3)
{
  int dwLowDateTime; // r14d
  const FILETIME *v5; // r12
  HLOCAL v7; // rdi
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rsi
  HANDLE FileW; // rax
  unsigned int v11; // ebx
  HANDLE v12; // r15
  unsigned int v13; // r14d
  DWORD v14; // r10d
  unsigned __int8 *v15; // r12
  DWORD v16; // r10d
  unsigned int Buffer; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v19; // [rsp+44h] [rbp-BCh] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v21; // [rsp+4Ch] [rbp-B4h]
  struct _FILELIST *v22; // [rsp+50h] [rbp-B0h]
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+5Ch] [rbp-A4h]
  unsigned int v25; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpFileName; // [rsp+68h] [rbp-98h]
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF

  dwLowDateTime = a1[3].dwLowDateTime;
  lpFileName = a2;
  v5 = a1;
  v22 = (struct _FILELIST *)a1;
  Buffer = 0;
  NumberOfBytesRead = 0;
  v19 = 0;
  NumberOfBytesWritten = 0;
  v24 = dwLowDateTime;
  v7 = LocalAlloc(0x40u, 0x8000u);
  v8 = (unsigned __int8 *)LocalAlloc(0x40u, 0x8000u);
  v9 = v8;
  if ( !v7 || !v8 )
  {
    v11 = -9;
    if ( !v7 )
      goto LABEL_34;
    goto LABEL_33;
  }
  FileW = CreateFileW(a2, 0xC0000000, 0, 0, 2u, 0x80u, 0);
  v11 = -1;
  v12 = FileW;
  if ( FileW != (HANDLE)-1LL
    || (StringCchCopyW(pszPath, 0x104u, lpFileName),
        PathRemoveFileSpecW(pszPath),
        CreateFullPath(pszPath, 0),
        v12 = CreateFileW(lpFileName, 0xC0000000, 0, 0, 2u, 0x80u, 0),
        v12 != (HANDLE)-1LL) )
  {
    if ( SetFilePointer(a3, v5[3].dwHighDateTime, 0, 0) != -1 )
    {
      if ( ReadFile(a3, &Buffer, 4u, &NumberOfBytesRead, 0) )
      {
        v11 = 0;
        if ( Buffer != 1347045187 )
          v11 = -7;
      }
      else
      {
        v11 = -5;
      }
    }
    v21 = 0;
    if ( !v11 )
    {
      while ( dwLowDateTime > 0 )
      {
        if ( !ReadFile(a3, &Buffer, 4u, &NumberOfBytesRead, 0) )
          goto LABEL_26;
        v13 = (unsigned __int16)Buffer;
        v19 = (unsigned __int16)Buffer;
        if ( HIWORD(Buffer) > 0x8000u || (unsigned __int16)Buffer > 0x8000u )
        {
          v11 = -3;
          break;
        }
        if ( HIWORD(Buffer) )
        {
          v25 = HIWORD(Buffer);
          if ( !ReadFile(a3, v7, HIWORD(Buffer), &NumberOfBytesRead, 0) )
          {
LABEL_26:
            v11 = -5;
            break;
          }
          v15 = v9;
          v19 = Mrci1Decompress(v7, v25, v9, v13);
          v14 = v19;
          if ( v19 != v13 )
          {
            v11 = -8;
            break;
          }
        }
        else
        {
          if ( !ReadFile(a3, v7, (unsigned __int16)Buffer, &v19, 0) )
            goto LABEL_26;
          v14 = v19;
          v15 = (unsigned __int8 *)v7;
        }
        v21 = CRC32Compute(v15, v14, v21);
        if ( !WriteFile(v12, v15, v16, &NumberOfBytesWritten, 0) )
        {
          v11 = -6;
          break;
        }
        dwLowDateTime = v24 - NumberOfBytesWritten;
        v24 -= NumberOfBytesWritten;
      }
      v5 = (const FILETIME *)v22;
    }
    SetFileTime(v12, 0, 0, v5 + 2);
    CloseHandle(v12);
    if ( v21 == v5[4].dwLowDateTime )
    {
      if ( !v11 )
        goto LABEL_33;
    }
    else
    {
      v11 = -11;
    }
    DeleteFileW(lpFileName);
    goto LABEL_33;
  }
  v11 = -10;
LABEL_33:
  LocalFree(v7);
LABEL_34:
  if ( v9 )
    LocalFree(v9);
  return v11;
}

```

## disassembly

```asm
0x1800166cc  mov     [rsp-8+arg_18], rbx
0x1800166d1  push    rbp
0x1800166d2  push    rsi
0x1800166d3  push    rdi
0x1800166d4  push    r12
0x1800166d6  push    r13
0x1800166d8  push    r14
0x1800166da  push    r15
0x1800166dc  lea     rbp, [rsp-190h]
0x1800166e4  sub     rsp, 290h
0x1800166eb  mov     rax, cs:__security_cookie
0x1800166f2  xor     rax, rsp
0x1800166f5  mov     [rbp+1C0h+var_40], rax
0x1800166fc  mov     r14d, [rcx+18h]
0x180016700  xor     r15d, r15d
0x180016703  mov     rbx, rdx
0x180016706  mov     [rsp+2C0h+lpFileName], rdx
0x18001670b  mov     r12, rcx
0x18001670e  mov     [rsp+2C0h+var_270], rcx
0x180016713  mov     edx, 8000h; uBytes
0x180016718  mov     [rsp+2C0h+Buffer], r15d
0x18001671d  lea     esi, [r15+40h]
0x180016721  mov     [rsp+2C0h+NumberOfBytesRead], r15d
0x180016726  mov     ecx, esi; uFlags
0x180016728  mov     [rsp+2C0h+var_27C], r15d
0x18001672d  mov     r13, r8
0x180016730  mov     [rsp+2C0h+NumberOfBytesWritten], r15d
0x180016735  mov     [rsp+2C0h+var_264], r14d
0x18001673a  call    cs:__imp_LocalAlloc
0x180016740  mov     edx, 8000h; uBytes
0x180016745  mov     ecx, esi; uFlags
0x180016747  mov     rdi, rax
0x18001674a  call    cs:__imp_LocalAlloc
0x180016750  mov     rsi, rax
0x180016753  test    rdi, rdi
0x180016756  jz      loc_1800169DD
0x18001675c  test    rax, rax
0x18001675f  jz      loc_1800169DD
0x180016765  mov     [rsp+2C0h+hTemplateFile], r15; hTemplateFile
0x18001676a  xor     r9d, r9d; lpSecurityAttributes
0x18001676d  mov     [rsp+2C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180016775  xor     r8d, r8d; dwShareMode
0x180016778  mov     edx, 0C0000000h; dwDesiredAccess
0x18001677d  mov     [rsp+2C0h+dwCreationDisposition], 2; dwCreationDisposition
0x180016785  mov     rcx, rbx; lpFileName
0x180016788  call    cs:__imp_CreateFileW
0x18001678e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016792  mov     r15, rax
0x180016795  cmp     rax, rbx
0x180016798  jnz     short loc_180016806
0x18001679a  mov     r8, [rsp+2C0h+lpFileName]; unsigned __int16 *
0x18001679f  lea     rcx, [rsp+2C0h+pszPath]; unsigned __int16 *
0x1800167a4  mov     edx, 104h; unsigned __int64
0x1800167a9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800167ae  lea     rcx, [rsp+2C0h+pszPath]; pszPath
0x1800167b3  call    cs:__imp_PathRemoveFileSpecW
0x1800167b9  xor     edx, edx; int
0x1800167bb  lea     rcx, [rsp+2C0h+pszPath]; unsigned __int16 *
0x1800167c0  call    ?CreateFullPath@@YAJPEBGH@Z; CreateFullPath(ushort const *,int)
0x1800167c5  mov     rcx, [rsp+2C0h+lpFileName]; lpFileName
0x1800167ca  xor     r9d, r9d; lpSecurityAttributes
0x1800167cd  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x1800167d6  xor     r8d, r8d; dwShareMode
0x1800167d9  mov     [rsp+2C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800167e1  mov     edx, 0C0000000h; dwDesiredAccess
0x1800167e6  mov     [rsp+2C0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800167ee  call    cs:__imp_CreateFileW
0x1800167f4  mov     r15, rax
0x1800167f7  cmp     rax, rbx
0x1800167fa  jnz     short loc_180016806
0x1800167fc  mov     ebx, 0FFFFFFF6h
0x180016801  jmp     loc_1800169E7
0x180016806  mov     edx, [r12+1Ch]; lDistanceToMove
0x18001680b  xor     r9d, r9d; dwMoveMethod
0x18001680e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180016811  mov     rcx, r13; hFile
0x180016814  call    cs:__imp_SetFilePointer
0x18001681a  cmp     eax, 0FFFFFFFFh
0x18001681d  jz      short loc_18001685F
0x18001681f  lea     r9, [rsp+2C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180016824  mov     qword ptr [rsp+2C0h+dwCreationDisposition], 0; lpOverlapped
0x18001682d  mov     r8d, 4; nNumberOfBytesToRead
0x180016833  lea     rdx, [rsp+2C0h+Buffer]; lpBuffer
0x180016838  mov     rcx, r13; hFile
0x18001683b  call    cs:__imp_ReadFile
0x180016841  xor     ecx, ecx
0x180016843  test    eax, eax
0x180016845  jz      short loc_180016858
0x180016847  cmp     [rsp+2C0h+Buffer], 504A4743h
0x18001684f  mov     ebx, ecx
0x180016851  jz      short loc_180016861
0x180016853  lea     ebx, [rcx-7]
0x180016856  jmp     short loc_180016861
0x180016858  mov     ebx, 0FFFFFFFBh
0x18001685d  jmp     short loc_180016861
0x18001685f  xor     ecx, ecx
0x180016861  mov     [rsp+2C0h+var_274], ecx
0x180016865  test    ebx, ebx
0x180016867  jnz     loc_18001699E
0x18001686d  xor     r12d, r12d
0x180016870  test    r14d, r14d
0x180016873  jle     loc_180016999
0x180016879  lea     r9, [rsp+2C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001687e  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r12; lpOverlapped
0x180016883  mov     r8d, 4; nNumberOfBytesToRead
0x180016889  lea     rdx, [rsp+2C0h+Buffer]; lpBuffer
0x18001688e  mov     rcx, r13; hFile
0x180016891  call    cs:__imp_ReadFile
0x180016897  test    eax, eax
0x180016899  jz      loc_180016994
0x18001689f  mov     ecx, [rsp+2C0h+Buffer]
0x1800168a3  mov     edx, 8000h
0x1800168a8  mov     eax, ecx
0x1800168aa  movzx   r14d, cx
0x1800168ae  shr     eax, 10h
0x1800168b1  mov     [rsp+2C0h+var_27C], r14d
0x1800168b6  cmp     ax, dx
0x1800168b9  ja      loc_18001698D
0x1800168bf  cmp     cx, dx
0x1800168c2  ja      loc_18001698D
0x1800168c8  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r12; lpOverlapped
0x1800168cd  mov     rdx, rdi; lpBuffer
0x1800168d0  mov     rcx, r13; hFile
0x1800168d3  test    ax, ax
0x1800168d6  jnz     short loc_1800168F8
0x1800168d8  lea     r9, [rsp+2C0h+var_27C]; lpNumberOfBytesRead
0x1800168dd  mov     r8d, r14d; nNumberOfBytesToRead
0x1800168e0  call    cs:__imp_ReadFile
0x1800168e6  test    eax, eax
0x1800168e8  jz      loc_180016994
0x1800168ee  mov     r10d, [rsp+2C0h+var_27C]
0x1800168f3  mov     r12, rdi
0x1800168f6  jmp     short loc_180016933
0x1800168f8  lea     r9, [rsp+2C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800168fd  mov     [rsp+2C0h+var_260], eax
0x180016901  mov     r8d, eax; nNumberOfBytesToRead
0x180016904  call    cs:__imp_ReadFile
0x18001690a  test    eax, eax
0x18001690c  jz      loc_180016994
0x180016912  mov     edx, [rsp+2C0h+var_260]
0x180016916  mov     r9d, r14d
0x180016919  mov     r8, rsi
0x18001691c  mov     rcx, rdi
0x18001691f  mov     r12, rsi
0x180016922  call    Mrci1Decompress
0x180016927  mov     [rsp+2C0h+var_27C], eax
0x18001692b  mov     r10d, eax
0x18001692e  cmp     eax, r14d
0x180016931  jnz     short loc_180016986
0x180016933  mov     r8d, [rsp+2C0h+var_274]; unsigned int
0x180016938  mov     edx, r10d; unsigned int
0x18001693b  mov     rcx, r12; unsigned __int8 *
0x18001693e  call    ?CRC32Compute@@YAKPEAEIK@Z; CRC32Compute(uchar *,uint,ulong)
0x180016943  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180016948  mov     [rsp+2C0h+var_274], eax
0x18001694c  mov     r8d, r10d; nNumberOfBytesToWrite
0x18001694f  mov     qword ptr [rsp+2C0h+dwCreationDisposition], 0; lpOverlapped
0x180016958  mov     rdx, r12; lpBuffer
0x18001695b  mov     rcx, r15; hFile
0x18001695e  call    cs:__imp_WriteFile
0x180016964  xor     r12d, r12d
0x180016967  test    eax, eax
0x180016969  jz      short loc_18001697F
0x18001696b  mov     r14d, [rsp+2C0h+var_264]
0x180016970  sub     r14d, [rsp+2C0h+NumberOfBytesWritten]
0x180016975  mov     [rsp+2C0h+var_264], r14d
0x18001697a  jmp     loc_180016870
0x18001697f  mov     ebx, 0FFFFFFFAh
0x180016984  jmp     short loc_180016999
0x180016986  mov     ebx, 0FFFFFFF8h
0x18001698b  jmp     short loc_180016999
0x18001698d  mov     ebx, 0FFFFFFFDh
0x180016992  jmp     short loc_180016999
0x180016994  mov     ebx, 0FFFFFFFBh
0x180016999  mov     r12, [rsp+2C0h+var_270]
0x18001699e  lea     r9, [r12+10h]; lpLastWriteTime
0x1800169a3  xor     r8d, r8d; lpLastAccessTime
0x1800169a6  xor     edx, edx; lpCreationTime
0x1800169a8  mov     rcx, r15; hFile
0x1800169ab  call    cs:__imp_SetFileTime
0x1800169b1  mov     rcx, r15; hObject
0x1800169b4  call    cs:__imp_CloseHandle
0x1800169ba  mov     eax, [rsp+2C0h+var_274]
0x1800169be  cmp     eax, [r12+20h]
0x1800169c3  jz      short loc_1800169CC
0x1800169c5  mov     ebx, 0FFFFFFF5h
0x1800169ca  jmp     short loc_1800169D0
0x1800169cc  test    ebx, ebx
0x1800169ce  jz      short loc_1800169E7
0x1800169d0  mov     rcx, [rsp+2C0h+lpFileName]; lpFileName
0x1800169d5  call    cs:__imp_DeleteFileW
0x1800169db  jmp     short loc_1800169E7
0x1800169dd  mov     ebx, 0FFFFFFF7h
0x1800169e2  test    rdi, rdi
0x1800169e5  jz      short loc_1800169F0
0x1800169e7  mov     rcx, rdi; hMem
0x1800169ea  call    cs:__imp_LocalFree
0x1800169f0  test    rsi, rsi
0x1800169f3  jz      short loc_1800169FE
0x1800169f5  mov     rcx, rsi; hMem
0x1800169f8  call    cs:__imp_LocalFree
0x1800169fe  mov     eax, ebx
0x180016a00  mov     rcx, [rbp+1C0h+var_40]
0x180016a07  xor     rcx, rsp; StackCookie
0x180016a0a  call    __security_check_cookie
0x180016a0f  mov     rbx, [rsp+2C0h+arg_18]
0x180016a17  add     rsp, 290h
0x180016a1e  pop     r15
0x180016a20  pop     r14
0x180016a22  pop     r13
0x180016a24  pop     r12
0x180016a26  pop     rdi
0x180016a27  pop     rsi
0x180016a28  pop     rbp
0x180016a29  retn
```
