# ReadJobQueueFile(ushort const *,_JOB_QUEUE_FILE * *)

- ea: `0x14003a754`
- end: `0x14003aa47`
- name: `?ReadJobQueueFile@@YAHPEBGPEAPEAU_JOB_QUEUE_FILE@@@Z`
- size: `755`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct _JOB_QUEUE_FILE **, __int64, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14003c270`
- `0x14003c79c`
- `0x14003d010`

## callees

- `0x140004b30`
- `0x140004df0`
- `0x140038f94`
- `0x14003a558`
- `0x14003a754`
- `0x14003aa50`
- `0x140065dbc`
- `0x14006a3a4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003a7ff`
- `KERNEL32!GetLastError` at `0x14003a916`
- `KERNEL32!GetLastError` at `0x14003a7ff`
- `KERNEL32!GetLastError` at `0x14003a916`
- `KERNEL32!CloseHandle` at `0x14003a8db`
- `KERNEL32!CloseHandle` at `0x14003aa25`
- `KERNEL32!CloseHandle` at `0x14003a8db`
- `KERNEL32!CloseHandle` at `0x14003aa25`
- `KERNEL32!DeleteFileW` at `0x14003a8e4`
- `KERNEL32!DeleteFileW` at `0x14003a8e4`

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
0x14003a754  mov     rax, rsp
0x14003a757  mov     [rax+8], rbx
0x14003a75b  push    rbp
0x14003a75c  push    rsi
0x14003a75d  push    rdi
0x14003a75e  push    r12
0x14003a760  push    r14
0x14003a762  sub     rsp, 40h
0x14003a766  mov     r14, rdx
0x14003a769  mov     qword ptr [rax+18h], 0
0x14003a771  mov     rsi, rcx
0x14003a774  mov     dword ptr [rax+10h], 0
0x14003a77b  xor     ebp, ebp
0x14003a77d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a784  lea     r12, WPP_GLOBAL_Control
0x14003a78b  lea     rdi, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003a792  cmp     rcx, r12
0x14003a795  jz      short loc_14003A7B2
0x14003a797  test    byte ptr [rcx+1Ch], 4
0x14003a79b  jz      short loc_14003A7B2
0x14003a79d  cmp     byte ptr [rcx+19h], 5
0x14003a7a1  jb      short loc_14003A7B2
0x14003a7a3  mov     rcx, [rcx+10h]
0x14003a7a7  lea     edx, [rbp+24h]
0x14003a7aa  mov     r8, rdi
0x14003a7ad  call    WPP_SF_
0x14003a7b2  mov     [rsp+68h+var_40], 80h; int
0x14003a7ba  xor     r8d, r8d; dwShareMode
0x14003a7bd  mov     edx, 80000000h; dwDesiredAccess
0x14003a7c2  mov     [rsp+68h+var_48], 3; DWORD
0x14003a7ca  mov     rcx, rsi; lpFileName
0x14003a7cd  call    InternalSafeCreateFile
0x14003a7d2  mov     rbx, rax
0x14003a7d5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14003a7d9  jnz     short loc_14003A827
0x14003a7db  mov     rax, cs:WPP_GLOBAL_Control
0x14003a7e2  cmp     rax, r12
0x14003a7e5  jz      loc_14003A8C1
0x14003a7eb  test    byte ptr [rax+1Ch], 4
0x14003a7ef  jz      loc_14003A8C1
0x14003a7f5  cmp     byte ptr [rax+19h], 2
0x14003a7f9  jb      loc_14003A8C1
0x14003a7ff  call    cs:__imp_GetLastError
0x14003a805  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a80c  lea     edx, [rbx+26h]
0x14003a80f  mov     r8, rdi
0x14003a812  mov     rcx, [rcx+10h]
0x14003a816  mov     r9, rsi
0x14003a819  mov     [rsp+68h+var_48], eax
0x14003a81d  call    WPP_SF_Sd
0x14003a822  jmp     loc_14003A8C1
0x14003a827  lea     rdx, [rsp+68h+arg_8]
0x14003a82c  mov     rcx, rbx; hFile
0x14003a82f  call    GetQueueFileVersion
0x14003a834  test    eax, eax
0x14003a836  jz      short loc_14003A857
0x14003a838  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a83f  cmp     rcx, r12
0x14003a842  jz      short loc_14003A8C1
0x14003a844  test    byte ptr [rcx+1Ch], 4
0x14003a848  jz      short loc_14003A8C1
0x14003a84a  cmp     byte ptr [rcx+19h], 2
0x14003a84e  jb      short loc_14003A8C1
0x14003a850  mov     edx, 26h ; '&'
0x14003a855  jmp     short loc_14003A80F
0x14003a857  mov     edi, 1
0x14003a85c  cmp     [rsp+68h+arg_8], edi
0x14003a860  jnz     loc_14003A977
0x14003a866  lea     rdx, [rsp+68h+lpMem]
0x14003a86e  mov     rcx, rbx; hFile
0x14003a871  call    ReadHashedJobQueueFile
0x14003a876  test    eax, eax
0x14003a878  jz      loc_14003AA12
0x14003a87e  cmp     eax, 80091007h
0x14003a883  jnz     loc_14003A942
0x14003a889  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a890  cmp     rcx, r12
0x14003a893  jz      short loc_14003A8BF
0x14003a895  test    byte ptr [rcx+1Ch], 4
0x14003a899  jz      short loc_14003A8BF
0x14003a89b  cmp     byte ptr [rcx+19h], 2
0x14003a89f  jb      short loc_14003A8BF
0x14003a8a1  mov     rcx, [rcx+10h]
0x14003a8a5  lea     edx, [rdi+26h]
0x14003a8a8  mov     r9, rsi
0x14003a8ab  mov     [rsp+68h+var_48], 80091007h
0x14003a8b3  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003a8ba  call    WPP_SF_Sd
0x14003a8bf  mov     ebp, edi
0x14003a8c1  mov     rcx, [rsp+68h+lpMem]; lpMem
0x14003a8c9  call    pMemFree
0x14003a8ce  xor     edi, edi
0x14003a8d0  test    ebp, ebp
0x14003a8d2  jz      loc_14003AA1C
0x14003a8d8  mov     rcx, rbx; hObject
0x14003a8db  call    cs:__imp_CloseHandle
0x14003a8e1  mov     rcx, rsi; lpFileName
0x14003a8e4  call    cs:__imp_DeleteFileW
0x14003a8ea  test    eax, eax
0x14003a8ec  jnz     loc_14003AA2B
0x14003a8f2  mov     rax, cs:WPP_GLOBAL_Control
0x14003a8f9  cmp     rax, r12
0x14003a8fc  jz      loc_14003AA2B
0x14003a902  test    byte ptr [rax+1Ch], 4
0x14003a906  jz      loc_14003AA2B
0x14003a90c  cmp     byte ptr [rax+19h], 2
0x14003a910  jb      loc_14003AA2B
0x14003a916  call    cs:__imp_GetLastError
0x14003a91c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a923  lea     edx, [rdi+2Bh]
0x14003a926  mov     r9, rsi
0x14003a929  mov     [rsp+68h+var_48], eax
0x14003a92d  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003a934  mov     rcx, [rcx+10h]
0x14003a938  call    WPP_SF_Sd
0x14003a93d  jmp     loc_14003AA2B
0x14003a942  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a949  cmp     rcx, r12
0x14003a94c  jz      loc_14003A8C1
0x14003a952  test    byte ptr [rcx+1Ch], 4
0x14003a956  jz      loc_14003A8C1
0x14003a95c  cmp     byte ptr [rcx+19h], 2
0x14003a960  jb      loc_14003A8C1
0x14003a966  mov     edx, 28h ; '('
0x14003a96b  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003a972  jmp     loc_14003A812
0x14003a977  cmp     [rsp+68h+arg_8], 678h
0x14003a97f  jnz     loc_14003A8BF
0x14003a985  lea     rdx, [rsp+68h+lpMem]
0x14003a98d  mov     rcx, rbx; hFile
0x14003a990  call    ReadLegacyJobQueueFile
0x14003a995  mov     edi, eax
0x14003a997  test    eax, eax
0x14003a999  jz      short loc_14003AA12
0x14003a99b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a9a2  cmp     rcx, r12
0x14003a9a5  jz      short loc_14003A9D6
0x14003a9a7  test    byte ptr [rcx+1Ch], 4
0x14003a9ab  jz      short loc_14003A9D6
0x14003a9ad  cmp     byte ptr [rcx+19h], 2
0x14003a9b1  jb      short loc_14003A9D6
0x14003a9b3  mov     rcx, [rcx+10h]
0x14003a9b7  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003a9be  mov     edx, 29h ; ')'
0x14003a9c3  mov     [rsp+68h+var_48], eax
0x14003a9c7  mov     r9, rsi
0x14003a9ca  call    WPP_SF_Sd
0x14003a9cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a9d6  cmp     edi, 570h
0x14003a9dc  jnz     loc_14003A8C1
0x14003a9e2  cmp     rcx, r12
0x14003a9e5  jz      short loc_14003AA08
0x14003a9e7  test    byte ptr [rcx+1Ch], 4
0x14003a9eb  jz      short loc_14003AA08
0x14003a9ed  cmp     byte ptr [rcx+19h], 2
0x14003a9f1  jb      short loc_14003AA08
0x14003a9f3  mov     rcx, [rcx+10h]
0x14003a9f7  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003a9fe  mov     edx, 2Ah ; '*'
0x14003aa03  call    WPP_SF_
0x14003aa08  mov     ebp, 1
0x14003aa0d  jmp     loc_14003A8C1
0x14003aa12  mov     rdi, [rsp+68h+lpMem]
0x14003aa1a  jmp     short loc_14003AA22
0x14003aa1c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14003aa20  jz      short loc_14003AA2B
0x14003aa22  mov     rcx, rbx; hObject
0x14003aa25  call    cs:__imp_CloseHandle
0x14003aa2b  mov     rbx, [rsp+68h+arg_0]
0x14003aa30  xor     eax, eax
0x14003aa32  test    rdi, rdi
0x14003aa35  mov     [r14], rdi
0x14003aa38  setnz   al
0x14003aa3b  add     rsp, 40h
0x14003aa3f  pop     r14
0x14003aa41  pop     r12
0x14003aa43  pop     rdi
0x14003aa44  pop     rsi
0x14003aa45  pop     rbp
0x14003aa46  retn
```
