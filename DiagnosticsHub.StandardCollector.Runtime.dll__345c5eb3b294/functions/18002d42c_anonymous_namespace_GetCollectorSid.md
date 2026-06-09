# _anonymous_namespace_::GetCollectorSid

- ea: `0x18002d42c`
- end: `0x18002d5d1`
- name: `_anonymous_namespace_::GetCollectorSid`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18002f0fc`

## callees

- `0x18002d42c`
- `0x180031284`
- `0x18003153c`
- `0x1800315c8`
- `0x180049b50`
- `0x18004ad58`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18002d454`
- `KERNEL32!GetCurrentProcess` at `0x18002d454`
- `KERNEL32!CloseHandle` at `0x18002d51d`
- `KERNEL32!CloseHandle` at `0x18002d51d`
- `KERNEL32!GetLastError` at `0x18002d498`
- `KERNEL32!GetLastError` at `0x18002d540`
- `KERNEL32!GetLastError` at `0x18002d569`
- `KERNEL32!GetLastError` at `0x18002d591`
- `KERNEL32!GetLastError` at `0x18002d498`
- `KERNEL32!GetLastError` at `0x18002d540`
- `KERNEL32!GetLastError` at `0x18002d569`
- `KERNEL32!GetLastError` at `0x18002d591`
- `ADVAPI32!OpenProcessToken` at `0x18002d466`
- `ADVAPI32!OpenProcessToken` at `0x18002d466`
- `ADVAPI32!GetTokenInformation` at `0x18002d492`
- `ADVAPI32!GetTokenInformation` at `0x18002d4d9`
- `ADVAPI32!GetTokenInformation` at `0x18002d492`
- `ADVAPI32!GetTokenInformation` at `0x18002d4d9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002d50d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002d50d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002d4aa`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002d4aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void anonymous_namespace_::GetCollectorSid()
{
  HANDLE CurrentProcess; // rax
  const struct _SID **v1; // rbx
  const unsigned __int16 *v2; // r8
  __int64 v3; // rax
  signed int v4; // eax
  unsigned int v5; // ecx
  signed int LastError; // eax
  unsigned int v7; // ecx
  signed int v8; // eax
  unsigned int v9; // ecx
  int pExceptionObject; // [rsp+30h] [rbp-59h] BYREF
  const struct _SID **v11; // [rsp+38h] [rbp-51h]
  _BYTE v12[128]; // [rsp+40h] [rbp-49h] BYREF
  DWORD TokenInformationLength; // [rsp+C0h] [rbp+37h] BYREF
  HANDLE TokenHandle; // [rsp+C8h] [rbp+3Fh] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
  {
    LastError = GetLastError();
    v7 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v7 = LastError;
    pExceptionObject = v7;
    throw (long *)&pExceptionObject;
  }
  TokenInformationLength = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( GetLastError() != 122 )
  {
    v8 = GetLastError();
    v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v9 = v8;
    pExceptionObject = v9;
    throw (long *)&pExceptionObject;
  }
  v1 = (const struct _SID **)malloc(TokenInformationLength);
  v11 = v1;
  if ( !v1 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v1, TokenInformationLength, &TokenInformationLength) )
  {
    v4 = GetLastError();
    v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v4 <= 0 )
      v5 = v4;
    pExceptionObject = v5;
    throw (long *)&pExceptionObject;
  }
  v3 = ATL::CSid::CSid((ATL::CSid *)v12, *v1, v2);
  ATL::CSid::operator=(&qword_180077070, v3);
  ATL::CSid::~CSid((ATL::CSid *)v12);
  free(v1);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
}

```

## disassembly

```asm
0x18002d42c  mov     [rsp-8+arg_0], rbx
0x18002d431  push    rbp
0x18002d432  lea     rbp, [rsp-57h]
0x18002d437  sub     rsp, 0E0h
0x18002d43e  mov     rax, cs:__security_cookie
0x18002d445  xor     rax, rsp
0x18002d448  mov     [rbp+57h+var_10], rax
0x18002d44c  mov     [rbp+57h+TokenHandle], 0
0x18002d454  call    cs:__imp_GetCurrentProcess
0x18002d45a  mov     rcx, rax; ProcessHandle
0x18002d45d  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18002d461  mov     edx, 0Ah; DesiredAccess
0x18002d466  call    cs:__imp_OpenProcessToken
0x18002d46c  test    eax, eax
0x18002d46e  jz      loc_18002D569
0x18002d474  mov     [rbp+57h+TokenInformationLength], 0
0x18002d47b  lea     rax, [rbp+57h+TokenInformationLength]
0x18002d47f  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18002d484  xor     r9d, r9d; TokenInformationLength
0x18002d487  xor     r8d, r8d; TokenInformation
0x18002d48a  lea     edx, [r9+1]; TokenInformationClass
0x18002d48e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18002d492  call    cs:__imp_GetTokenInformation
0x18002d498  call    cs:__imp_GetLastError
0x18002d49e  cmp     eax, 7Ah ; 'z'
0x18002d4a1  jnz     loc_18002D591
0x18002d4a7  mov     ecx, [rbp+57h+TokenInformationLength]; Size
0x18002d4aa  call    cs:__imp_malloc
0x18002d4b0  mov     rbx, rax
0x18002d4b3  mov     [rbp+57h+var_A8], rax
0x18002d4b7  test    rax, rax
0x18002d4ba  jz      loc_18002D5B9
0x18002d4c0  lea     rax, [rbp+57h+TokenInformationLength]
0x18002d4c4  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18002d4c9  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18002d4cd  mov     r8, rbx; TokenInformation
0x18002d4d0  mov     edx, 1; TokenInformationClass
0x18002d4d5  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18002d4d9  call    cs:__imp_GetTokenInformation
0x18002d4df  test    eax, eax
0x18002d4e1  jz      short loc_18002D540
0x18002d4e3  mov     rdx, [rbx]; struct _SID *
0x18002d4e6  lea     rcx, [rbp+57h+var_A0]; this
0x18002d4ea  call    ??0CSid@ATL@@QEAA@PEBU_SID@@PEBG@Z; ATL::CSid::CSid(_SID const *,ushort const *)
0x18002d4ef  nop
0x18002d4f0  mov     rdx, rax
0x18002d4f3  lea     rcx, qword_180077070
0x18002d4fa  call    ??4CSid@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSid::operator=(ATL::CSid const &)
0x18002d4ff  nop
0x18002d500  lea     rcx, [rbp+57h+var_A0]; this
0x18002d504  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002d509  nop
0x18002d50a  mov     rcx, rbx; Block
0x18002d50d  call    cs:__imp_free
0x18002d513  nop
0x18002d514  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18002d518  test    rcx, rcx
0x18002d51b  jz      short loc_18002D523
0x18002d51d  call    cs:__imp_CloseHandle
0x18002d523  mov     rcx, [rbp+57h+var_10]
0x18002d527  xor     rcx, rsp; StackCookie
0x18002d52a  call    __security_check_cookie
0x18002d52f  mov     rbx, [rsp+0E0h+arg_0]
0x18002d537  add     rsp, 0E0h
0x18002d53e  pop     rbp
0x18002d53f  retn
0x18002d540  call    cs:__imp_GetLastError
0x18002d546  nop
0x18002d547  movzx   ecx, ax
0x18002d54a  or      ecx, 80070000h
0x18002d550  test    eax, eax
0x18002d552  cmovle  ecx, eax
0x18002d555  mov     [rbp+57h+pExceptionObject], ecx
0x18002d558  lea     rdx, _TI1J; pThrowInfo
0x18002d55f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002d563  call    _CxxThrowException_0
0x18002d569  call    cs:__imp_GetLastError
0x18002d56f  movzx   ecx, ax
0x18002d572  or      ecx, 80070000h
0x18002d578  test    eax, eax
0x18002d57a  cmovle  ecx, eax
0x18002d57d  mov     [rbp+57h+pExceptionObject], ecx
0x18002d580  lea     rdx, _TI1J; pThrowInfo
0x18002d587  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002d58b  call    _CxxThrowException_0
0x18002d591  call    cs:__imp_GetLastError
0x18002d597  movzx   ecx, ax
0x18002d59a  or      ecx, 80070000h
0x18002d5a0  test    eax, eax
0x18002d5a2  cmovle  ecx, eax
0x18002d5a5  mov     [rbp+57h+pExceptionObject], ecx
0x18002d5a8  lea     rdx, _TI1J; pThrowInfo
0x18002d5af  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002d5b3  call    _CxxThrowException_0
0x18002d5b9  mov     [rbp+57h+pExceptionObject], 8007000Eh
0x18002d5c0  lea     rdx, _TI1J; pThrowInfo
0x18002d5c7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002d5cb  call    _CxxThrowException_0
```
