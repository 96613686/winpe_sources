# Utils::ReadFileIntoBuffer(ushort const *,uchar * *,ulong *)

- ea: `0x18004f0ac`
- end: `0x18004f2a4`
- name: `?ReadFileIntoBuffer@Utils@@SAKPEBGPEAPEAEPEAK@Z`
- size: `504`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18004e288`
- `0x18005c840`

## callees

- `0x180001f94`
- `0x180001fa0`
- `0x18004f0ac`
- `0x18004f8a8`
- `0x18004f8d0`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004f123`
- `KERNEL32!GetLastError` at `0x18004f142`
- `KERNEL32!GetLastError` at `0x18004f1e3`
- `KERNEL32!GetLastError` at `0x18004f123`
- `KERNEL32!GetLastError` at `0x18004f142`
- `KERNEL32!GetLastError` at `0x18004f1e3`
- `KERNEL32!ReadFile` at `0x18004f1d9`
- `KERNEL32!ReadFile` at `0x18004f1d9`
- `KERNEL32!GetFileSize` at `0x18004f133`
- `KERNEL32!GetFileSize` at `0x18004f133`
- `KERNEL32!CreateFileW` at `0x18004f114`
- `KERNEL32!CreateFileW` at `0x18004f114`
- `KERNEL32!CloseHandle` at `0x18004f27c`
- `KERNEL32!CloseHandle` at `0x18004f27c`

## pseudocode

```c
DWORD __fastcall Utils::ReadFileIntoBuffer(const unsigned __int16 *a1, unsigned __int8 **a2, unsigned int *a3)
{
  HANDLE FileW; // rax
  void *v6; // rsi
  DWORD FileSize; // eax
  DWORD v9; // ebx
  unsigned __int8 *v10; // rdi
  DWORD LastError; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned __int8 *v14; // rax
  DWORD v15; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-38h] BYREF

  NumberOfBytesRead = 0;
  if ( !a1 || !a2 || !a3 )
    return 87;
  FileW = CreateFileW(a1, 0x80000000, 0, 0, 3u, 0x80u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  FileSize = GetFileSize(FileW, 0);
  v9 = FileSize;
  if ( FileSize == -1 )
  {
    v10 = 0;
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v13 = 37;
LABEL_18:
      WPP_SF_d(v12[2], v13, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, LastError);
    }
  }
  else
  {
    v14 = (unsigned __int8 *)operator new[](FileSize);
    v10 = v14;
    if ( !v14 )
    {
      LastError = 14;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, 14);
      goto LABEL_29;
    }
    if ( ReadFile(v6, v14, v9, &NumberOfBytesRead, 0) )
    {
      v15 = NumberOfBytesRead;
      if ( NumberOfBytesRead == v9 )
      {
        *a2 = v10;
        LastError = 0;
        *a3 = v15;
        goto LABEL_29;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids);
      LastError = 31;
      goto LABEL_27;
    }
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v13 = 39;
      goto LABEL_18;
    }
  }
  if ( LastError && v10 )
LABEL_27:
    operator delete(v10);
LABEL_29:
  if ( v6 )
    CloseHandle(v6);
  return LastError;
}

```

## disassembly

```asm
0x18004f0ac  push    rbx
0x18004f0ae  push    rsi
0x18004f0af  push    rdi
0x18004f0b0  push    r14
0x18004f0b2  push    r15
0x18004f0b4  sub     rsp, 50h
0x18004f0b8  mov     rax, cs:__security_cookie
0x18004f0bf  xor     rax, rsp
0x18004f0c2  mov     [rsp+78h+var_30], rax
0x18004f0c7  mov     [rsp+78h+NumberOfBytesRead], 0
0x18004f0cf  mov     r15, r8
0x18004f0d2  mov     r14, rdx
0x18004f0d5  test    rcx, rcx
0x18004f0d8  jz      loc_18004F286
0x18004f0de  test    rdx, rdx
0x18004f0e1  jz      loc_18004F286
0x18004f0e7  test    r8, r8
0x18004f0ea  jz      loc_18004F286
0x18004f0f0  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18004f0f9  xor     r9d, r9d; lpSecurityAttributes
0x18004f0fc  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004f104  xor     r8d, r8d; dwShareMode
0x18004f107  mov     edx, 80000000h; dwDesiredAccess
0x18004f10c  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18004f114  call    cs:__imp_CreateFileW
0x18004f11a  mov     rsi, rax
0x18004f11d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004f121  jnz     short loc_18004F12E
0x18004f123  call    cs:__imp_GetLastError
0x18004f129  jmp     loc_18004F28B
0x18004f12e  xor     edx, edx; lpFileSizeHigh
0x18004f130  mov     rcx, rsi; hFile
0x18004f133  call    cs:__imp_GetFileSize
0x18004f139  mov     ebx, eax
0x18004f13b  cmp     eax, 0FFFFFFFFh
0x18004f13e  jnz     short loc_18004F173
0x18004f140  xor     edi, edi
0x18004f142  call    cs:__imp_GetLastError
0x18004f148  mov     ebx, eax
0x18004f14a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f151  lea     rax, WPP_GLOBAL_Control
0x18004f158  cmp     rcx, rax
0x18004f15b  jz      loc_18004F21C
0x18004f161  test    byte ptr [rcx+1Ch], 2
0x18004f165  jz      loc_18004F21C
0x18004f16b  lea     edx, [rdi+25h]
0x18004f16e  jmp     loc_18004F209
0x18004f173  mov     rcx, rbx; unsigned __int64
0x18004f176  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004f17b  mov     rdi, rax
0x18004f17e  test    rax, rax
0x18004f181  jnz     short loc_18004F1C2
0x18004f183  lea     ebx, [rax+0Eh]
0x18004f186  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f18d  lea     rax, WPP_GLOBAL_Control
0x18004f194  cmp     rcx, rax
0x18004f197  jz      loc_18004F274
0x18004f19d  test    byte ptr [rcx+1Ch], 2
0x18004f1a1  jz      loc_18004F274
0x18004f1a7  mov     rcx, [rcx+10h]
0x18004f1ab  lea     edx, [rdi+26h]
0x18004f1ae  mov     r9d, ebx
0x18004f1b1  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004f1b8  call    WPP_SF_d
0x18004f1bd  jmp     loc_18004F274
0x18004f1c2  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004f1c7  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x18004f1d0  mov     r8d, ebx; nNumberOfBytesToRead
0x18004f1d3  mov     rdx, rdi; lpBuffer
0x18004f1d6  mov     rcx, rsi; hFile
0x18004f1d9  call    cs:__imp_ReadFile
0x18004f1df  test    eax, eax
0x18004f1e1  jnz     short loc_18004F227
0x18004f1e3  call    cs:__imp_GetLastError
0x18004f1e9  mov     ebx, eax
0x18004f1eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f1f2  lea     rax, WPP_GLOBAL_Control
0x18004f1f9  cmp     rcx, rax
0x18004f1fc  jz      short loc_18004F21C
0x18004f1fe  test    byte ptr [rcx+1Ch], 2
0x18004f202  jz      short loc_18004F21C
0x18004f204  mov     edx, 27h ; '''
0x18004f209  mov     rcx, [rcx+10h]
0x18004f20d  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004f214  mov     r9d, ebx
0x18004f217  call    WPP_SF_d
0x18004f21c  test    ebx, ebx
0x18004f21e  jz      short loc_18004F274
0x18004f220  test    rdi, rdi
0x18004f223  jz      short loc_18004F274
0x18004f225  jmp     short loc_18004F262
0x18004f227  mov     eax, [rsp+78h+NumberOfBytesRead]
0x18004f22b  cmp     eax, ebx
0x18004f22d  jz      short loc_18004F26C
0x18004f22f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f236  lea     rax, WPP_GLOBAL_Control
0x18004f23d  cmp     rcx, rax
0x18004f240  jz      short loc_18004F25D
0x18004f242  test    byte ptr [rcx+1Ch], 2
0x18004f246  jz      short loc_18004F25D
0x18004f248  mov     rcx, [rcx+10h]
0x18004f24c  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004f253  mov     edx, 28h ; '('
0x18004f258  call    WPP_SF_
0x18004f25d  mov     ebx, 1Fh
0x18004f262  mov     rcx, rdi; Block
0x18004f265  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004f26a  jmp     short loc_18004F274
0x18004f26c  mov     [r14], rdi
0x18004f26f  xor     ebx, ebx
0x18004f271  mov     [r15], eax
0x18004f274  test    rsi, rsi
0x18004f277  jz      short loc_18004F282
0x18004f279  mov     rcx, rsi; hObject
0x18004f27c  call    cs:__imp_CloseHandle
0x18004f282  mov     eax, ebx
0x18004f284  jmp     short loc_18004F28B
0x18004f286  mov     eax, 57h ; 'W'
0x18004f28b  mov     rcx, [rsp+78h+var_30]
0x18004f290  xor     rcx, rsp; StackCookie
0x18004f293  call    __security_check_cookie
0x18004f298  add     rsp, 50h
0x18004f29c  pop     r15
0x18004f29e  pop     r14
0x18004f2a0  pop     rdi
0x18004f2a1  pop     rsi
0x18004f2a2  pop     rbx
0x18004f2a3  retn
```
