# ReadJobQueueFile(ushort const *,_JOB_QUEUE_FILE * *)

- ea: `0x14003c834`
- end: `0x14003cb46`
- name: `?ReadJobQueueFile@@YAHPEBGPEAPEAU_JOB_QUEUE_FILE@@@Z`
- size: `786`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct _JOB_QUEUE_FILE **, __int64, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14003e4d8`
- `0x14003ea34`
- `0x14003f308`

## callees

- `0x140004c78`
- `0x140004f64`
- `0x14003af34`
- `0x14003c638`
- `0x14003c834`
- `0x14003cb4c`
- `0x14006998c`
- `0x14006e124`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003c8df`
- `KERNEL32!GetLastError` at `0x14003ca08`
- `KERNEL32!GetLastError` at `0x14003c8df`
- `KERNEL32!GetLastError` at `0x14003ca08`
- `KERNEL32!CloseHandle` at `0x14003c9c1`
- `KERNEL32!CloseHandle` at `0x14003cb1d`
- `KERNEL32!CloseHandle` at `0x14003c9c1`
- `KERNEL32!CloseHandle` at `0x14003cb1d`
- `KERNEL32!DeleteFileW` at `0x14003c9d0`
- `KERNEL32!DeleteFileW` at `0x14003c9d0`

## pseudocode

```c
__int64 __fastcall ReadJobQueueFile(LPCWSTR lpFileName, struct _JOB_QUEUE_FILE **a2, __int64 a3, __int64 a4)
{
  int v6; // ebp
  void *File; // rax
  void *v8; // rbx
  int QueueFileVersion; // eax
  CMapDeviceId *v10; // rcx
  int v11; // edx
  char LastError; // al

  v6 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  File = (void *)InternalSafeCreateFile(lpFileName, 0x80000000, 0, a4, 3u, 128);
  v8 = File;
  if ( File == (void *)-1LL )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LOBYTE(QueueFileVersion) = GetLastError();
      v10 = WPP_GLOBAL_Control;
      v11 = 37;
LABEL_10:
      WPP_SF_Sd(
        *((_QWORD *)v10 + 2),
        v11,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        (_DWORD)lpFileName,
        QueueFileVersion);
    }
  }
  else
  {
    QueueFileVersion = GetQueueFileVersion(File);
    if ( QueueFileVersion )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 38;
        goto LABEL_10;
      }
    }
    else
    {
      v6 = 1;
    }
  }
  pMemFree(0);
  if ( v6 )
  {
    CloseHandle(v8);
    if ( !DeleteFileW(lpFileName)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        (_DWORD)lpFileName,
        LastError);
    }
  }
  else if ( v8 != (void *)-1LL )
  {
    CloseHandle(v8);
  }
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x14003c834  mov     rax, rsp
0x14003c837  mov     [rax+8], rbx
0x14003c83b  push    rbp
0x14003c83c  push    rsi
0x14003c83d  push    rdi
0x14003c83e  push    r12
0x14003c840  push    r14
0x14003c842  sub     rsp, 40h
0x14003c846  mov     r14, rdx
0x14003c849  mov     qword ptr [rax+18h], 0
0x14003c851  mov     rsi, rcx
0x14003c854  mov     dword ptr [rax+10h], 0
0x14003c85b  xor     ebp, ebp
0x14003c85d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c864  lea     r12, WPP_GLOBAL_Control
0x14003c86b  lea     rdi, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003c872  cmp     rcx, r12
0x14003c875  jz      short loc_14003C892
0x14003c877  test    byte ptr [rcx+1Ch], 4
0x14003c87b  jz      short loc_14003C892
0x14003c87d  cmp     byte ptr [rcx+19h], 5
0x14003c881  jb      short loc_14003C892
0x14003c883  mov     rcx, [rcx+10h]
0x14003c887  lea     edx, [rbp+24h]
0x14003c88a  mov     r8, rdi
0x14003c88d  call    WPP_SF_
0x14003c892  mov     [rsp+68h+var_40], 80h; int
0x14003c89a  xor     r8d, r8d; dwShareMode
0x14003c89d  mov     edx, 80000000h; dwDesiredAccess
0x14003c8a2  mov     [rsp+68h+var_48], 3; DWORD
0x14003c8aa  mov     rcx, rsi; lpFileName
0x14003c8ad  call    InternalSafeCreateFile
0x14003c8b2  mov     rbx, rax
0x14003c8b5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14003c8b9  jnz     short loc_14003C90D
0x14003c8bb  mov     rax, cs:WPP_GLOBAL_Control
0x14003c8c2  cmp     rax, r12
0x14003c8c5  jz      loc_14003C9A7
0x14003c8cb  test    byte ptr [rax+1Ch], 4
0x14003c8cf  jz      loc_14003C9A7
0x14003c8d5  cmp     byte ptr [rax+19h], 2
0x14003c8d9  jb      loc_14003C9A7
0x14003c8df  call    cs:__imp_GetLastError
0x14003c8e6  nop     dword ptr [rax+rax+00h]
0x14003c8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c8f2  lea     edx, [rbx+26h]
0x14003c8f5  mov     r8, rdi
0x14003c8f8  mov     rcx, [rcx+10h]
0x14003c8fc  mov     r9, rsi
0x14003c8ff  mov     [rsp+68h+var_48], eax
0x14003c903  call    WPP_SF_Sd
0x14003c908  jmp     loc_14003C9A7
0x14003c90d  lea     rdx, [rsp+68h+arg_8]
0x14003c912  mov     rcx, rbx; hFile
0x14003c915  call    GetQueueFileVersion
0x14003c91a  test    eax, eax
0x14003c91c  jz      short loc_14003C93D
0x14003c91e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c925  cmp     rcx, r12
0x14003c928  jz      short loc_14003C9A7
0x14003c92a  test    byte ptr [rcx+1Ch], 4
0x14003c92e  jz      short loc_14003C9A7
0x14003c930  cmp     byte ptr [rcx+19h], 2
0x14003c934  jb      short loc_14003C9A7
0x14003c936  mov     edx, 26h ; '&'
0x14003c93b  jmp     short loc_14003C8F5
0x14003c93d  mov     edi, 1
0x14003c942  cmp     [rsp+68h+arg_8], edi
0x14003c946  jnz     loc_14003CA6F
0x14003c94c  lea     rdx, [rsp+68h+lpMem]
0x14003c954  mov     rcx, rbx; hFile
0x14003c957  call    ReadHashedJobQueueFile
0x14003c95c  test    eax, eax
0x14003c95e  jz      loc_14003CB0A
0x14003c964  cmp     eax, 80091007h
0x14003c969  jnz     loc_14003CA3A
0x14003c96f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c976  cmp     rcx, r12
0x14003c979  jz      short loc_14003C9A5
0x14003c97b  test    byte ptr [rcx+1Ch], 4
0x14003c97f  jz      short loc_14003C9A5
0x14003c981  cmp     byte ptr [rcx+19h], 2
0x14003c985  jb      short loc_14003C9A5
0x14003c987  mov     rcx, [rcx+10h]
0x14003c98b  lea     edx, [rdi+26h]
0x14003c98e  mov     r9, rsi
0x14003c991  mov     [rsp+68h+var_48], 80091007h
0x14003c999  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003c9a0  call    WPP_SF_Sd
0x14003c9a5  mov     ebp, edi
0x14003c9a7  mov     rcx, [rsp+68h+lpMem]; lpMem
0x14003c9af  call    pMemFree
0x14003c9b4  xor     edi, edi
0x14003c9b6  test    ebp, ebp
0x14003c9b8  jz      loc_14003CB14
0x14003c9be  mov     rcx, rbx; hObject
0x14003c9c1  call    cs:__imp_CloseHandle
0x14003c9c8  nop     dword ptr [rax+rax+00h]
0x14003c9cd  mov     rcx, rsi; lpFileName
0x14003c9d0  call    cs:__imp_DeleteFileW
0x14003c9d7  nop     dword ptr [rax+rax+00h]
0x14003c9dc  test    eax, eax
0x14003c9de  jnz     loc_14003CB29
0x14003c9e4  mov     rax, cs:WPP_GLOBAL_Control
0x14003c9eb  cmp     rax, r12
0x14003c9ee  jz      loc_14003CB29
0x14003c9f4  test    byte ptr [rax+1Ch], 4
0x14003c9f8  jz      loc_14003CB29
0x14003c9fe  cmp     byte ptr [rax+19h], 2
0x14003ca02  jb      loc_14003CB29
0x14003ca08  call    cs:__imp_GetLastError
0x14003ca0f  nop     dword ptr [rax+rax+00h]
0x14003ca14  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ca1b  lea     edx, [rdi+2Bh]
0x14003ca1e  mov     r9, rsi
0x14003ca21  mov     [rsp+68h+var_48], eax
0x14003ca25  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003ca2c  mov     rcx, [rcx+10h]
0x14003ca30  call    WPP_SF_Sd
0x14003ca35  jmp     loc_14003CB29
0x14003ca3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ca41  cmp     rcx, r12
0x14003ca44  jz      loc_14003C9A7
0x14003ca4a  test    byte ptr [rcx+1Ch], 4
0x14003ca4e  jz      loc_14003C9A7
0x14003ca54  cmp     byte ptr [rcx+19h], 2
0x14003ca58  jb      loc_14003C9A7
0x14003ca5e  mov     edx, 28h ; '('
0x14003ca63  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003ca6a  jmp     loc_14003C8F8
0x14003ca6f  cmp     [rsp+68h+arg_8], 678h
0x14003ca77  jnz     loc_14003C9A5
0x14003ca7d  lea     rdx, [rsp+68h+lpMem]
0x14003ca85  mov     rcx, rbx; hFile
0x14003ca88  call    ReadLegacyJobQueueFile
0x14003ca8d  mov     edi, eax
0x14003ca8f  test    eax, eax
0x14003ca91  jz      short loc_14003CB0A
0x14003ca93  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ca9a  cmp     rcx, r12
0x14003ca9d  jz      short loc_14003CACE
0x14003ca9f  test    byte ptr [rcx+1Ch], 4
0x14003caa3  jz      short loc_14003CACE
0x14003caa5  cmp     byte ptr [rcx+19h], 2
0x14003caa9  jb      short loc_14003CACE
0x14003caab  mov     rcx, [rcx+10h]
0x14003caaf  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003cab6  mov     edx, 29h ; ')'
0x14003cabb  mov     [rsp+68h+var_48], eax
0x14003cabf  mov     r9, rsi
0x14003cac2  call    WPP_SF_Sd
0x14003cac7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cace  cmp     edi, 570h
0x14003cad4  jnz     loc_14003C9A7
0x14003cada  cmp     rcx, r12
0x14003cadd  jz      short loc_14003CB00
0x14003cadf  test    byte ptr [rcx+1Ch], 4
0x14003cae3  jz      short loc_14003CB00
0x14003cae5  cmp     byte ptr [rcx+19h], 2
0x14003cae9  jb      short loc_14003CB00
0x14003caeb  mov     rcx, [rcx+10h]
0x14003caef  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003caf6  mov     edx, 2Ah ; '*'
0x14003cafb  call    WPP_SF_
0x14003cb00  mov     ebp, 1
0x14003cb05  jmp     loc_14003C9A7
0x14003cb0a  mov     rdi, [rsp+68h+lpMem]
0x14003cb12  jmp     short loc_14003CB1A
0x14003cb14  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14003cb18  jz      short loc_14003CB29
0x14003cb1a  mov     rcx, rbx; hObject
0x14003cb1d  call    cs:__imp_CloseHandle
0x14003cb24  nop     dword ptr [rax+rax+00h]
0x14003cb29  mov     rbx, [rsp+68h+arg_0]
0x14003cb2e  xor     eax, eax
0x14003cb30  test    rdi, rdi
0x14003cb33  mov     [r14], rdi
0x14003cb36  setnz   al
0x14003cb39  add     rsp, 40h
0x14003cb3d  pop     r14
0x14003cb3f  pop     r12
0x14003cb41  pop     rdi
0x14003cb42  pop     rsi
0x14003cb43  pop     rbp
0x14003cb44  retn
```
