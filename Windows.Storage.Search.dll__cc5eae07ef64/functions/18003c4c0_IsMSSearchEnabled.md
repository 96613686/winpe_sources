# IsMSSearchEnabled

- ea: `0x18003c4c0`
- end: `0x18003c5eb`
- name: `IsMSSearchEnabled`
- size: `299`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18003c220`
- `0x18003c5f4`
- `0x180078d00`
- `0x18008762c`
- `0x18009d650`
- `0x1800b8360`
- `0x1800bd358`

## callees

- `0x18003c4c0`
- `0x18006c6bc`
- `0x180071dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c5bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c5bb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003c531`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003c5b0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003c531`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003c5b0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003c4ee`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003c4ee`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003c50e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003c50e`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18003c598`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18003c598`

## pseudocode

```c
__int64 __fastcall IsMSSearchEnabled(const WCHAR *a1, BOOL *a2)
{
  BOOL v3; // edi
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rbp
  SC_HANDLE v6; // rsi
  int Error; // ebx
  signed int LastError; // eax
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-58h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-50h] BYREF
  __int128 v12; // [rsp+48h] [rbp-40h]
  int v13; // [rsp+58h] [rbp-30h]

  v3 = 1;
  v4 = OpenSCManagerW(a1, 0, 1u);
  v5 = v4;
  if ( v4 )
  {
    v6 = OpenServiceW(v4, L"wsearch", 4u);
    if ( v6 )
    {
      pcbBytesNeeded = 0;
      v13 = 0;
      *(_OWORD *)Buffer = 0;
      v12 = 0;
      if ( QueryServiceStatusEx(v6, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded)
        || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        Error = *(_DWORD *)&Buffer[4] != 4;
      }
      CloseServiceHandle(v6);
    }
    else
    {
      Error = ResultFromKnownLastError();
      v3 = Error != -2147023836;
    }
    CloseServiceHandle(v5);
  }
  else
  {
    LastError = GetLastError();
    Error = LastError;
    if ( LastError > 0 )
      Error = (unsigned __int16)LastError | 0x80070000;
    if ( Error >= 0 )
      Error = -2147467259;
  }
  if ( a2 )
    *a2 = v3;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18003c4c0  mov     [rsp+arg_10], rbx
0x18003c4c5  mov     [rsp+arg_18], rbp
0x18003c4ca  push    rsi
0x18003c4cb  push    rdi
0x18003c4cc  push    r14
0x18003c4ce  sub     rsp, 70h
0x18003c4d2  mov     rax, cs:__security_cookie
0x18003c4d9  xor     rax, rsp
0x18003c4dc  mov     [rsp+88h+var_28], rax
0x18003c4e1  mov     r14, rdx
0x18003c4e4  mov     edi, 1
0x18003c4e9  mov     r8d, edi; dwDesiredAccess
0x18003c4ec  xor     edx, edx; lpDatabaseName
0x18003c4ee  call    cs:__imp_OpenSCManagerW
0x18003c4f4  mov     rbp, rax
0x18003c4f7  test    rax, rax
0x18003c4fa  jz      loc_18003C5BB
0x18003c500  lea     r8d, [rdi+3]; dwDesiredAccess
0x18003c504  mov     rcx, rax; hSCManager
0x18003c507  lea     rdx, ServiceName; "wsearch"
0x18003c50e  call    cs:__imp_OpenServiceW
0x18003c514  mov     rsi, rax
0x18003c517  test    rax, rax
0x18003c51a  jnz     short loc_18003C563
0x18003c51c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003c521  mov     ebx, eax
0x18003c523  xor     eax, eax
0x18003c525  cmp     ebx, 80070424h
0x18003c52b  cmovz   edi, eax
0x18003c52e  mov     rcx, rbp; hSCObject
0x18003c531  call    cs:__imp_CloseServiceHandle
0x18003c537  test    r14, r14
0x18003c53a  jz      short loc_18003C53F
0x18003c53c  mov     [r14], edi
0x18003c53f  mov     eax, ebx
0x18003c541  mov     rcx, [rsp+88h+var_28]
0x18003c546  xor     rcx, rsp; StackCookie
0x18003c549  call    __security_check_cookie
0x18003c54e  lea     r11, [rsp+88h+var_18]
0x18003c553  mov     rbx, [r11+30h]
0x18003c557  mov     rbp, [r11+38h]
0x18003c55b  mov     rsp, r11
0x18003c55e  pop     r14
0x18003c560  pop     rdi
0x18003c561  pop     rsi
0x18003c562  retn
0x18003c563  xor     eax, eax
0x18003c565  mov     [rsp+88h+var_58], 0
0x18003c56d  xorps   xmm0, xmm0
0x18003c570  mov     [rsp+88h+var_30], eax
0x18003c574  lea     rax, [rsp+88h+var_58]
0x18003c579  mov     r9d, 24h ; '$'; cbBufSize
0x18003c57f  lea     r8, [rsp+88h+Buffer]; lpBuffer
0x18003c584  mov     [rsp+88h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18003c589  xor     edx, edx; InfoLevel
0x18003c58b  mov     rcx, rsi; hService
0x18003c58e  movups  xmmword ptr [rsp+88h+Buffer], xmm0
0x18003c593  movups  [rsp+88h+var_40], xmm0
0x18003c598  call    cs:__imp_QueryServiceStatusEx
0x18003c59e  test    eax, eax
0x18003c5a0  jnz     short loc_18003C5DF
0x18003c5a2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003c5a7  mov     ebx, eax
0x18003c5a9  test    eax, eax
0x18003c5ab  jns     short loc_18003C5DF
0x18003c5ad  mov     rcx, rsi; hSCObject
0x18003c5b0  call    cs:__imp_CloseServiceHandle
0x18003c5b6  jmp     loc_18003C52E
0x18003c5bb  call    cs:__imp_GetLastError
0x18003c5c1  mov     ebx, eax
0x18003c5c3  test    eax, eax
0x18003c5c5  jle     short loc_18003C5D0
0x18003c5c7  movzx   ebx, ax
0x18003c5ca  or      ebx, 80070000h
0x18003c5d0  test    ebx, ebx
0x18003c5d2  mov     eax, 80004005h
0x18003c5d7  cmovns  ebx, eax
0x18003c5da  jmp     loc_18003C537
0x18003c5df  xor     ebx, ebx
0x18003c5e1  cmp     dword ptr [rsp+88h+Buffer+4], 4
0x18003c5e6  setnz   bl
0x18003c5e9  jmp     short loc_18003C5AD
```
