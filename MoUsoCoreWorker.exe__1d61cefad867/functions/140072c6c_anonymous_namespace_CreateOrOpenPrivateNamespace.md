# _anonymous_namespace_::CreateOrOpenPrivateNamespace

- ea: `0x140072c6c`
- end: `0x140072eea`
- name: `_anonymous_namespace_::CreateOrOpenPrivateNamespace`
- size: `638`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400230ec`
- `0x140072f48`
- `0x1400730a4`

## callees

- `0x14003c578`
- `0x1400413a8`
- `0x140072a98`
- `0x140072c6c`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x140379070`
- `0x1403790cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140072d81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140072df0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140072d81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140072df0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072d6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072ddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072d6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072ddb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140072e5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140072e5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140072e0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140072e0f`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x140072e32`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x140072e32`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x140072d05`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x140072d05`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x140072dc6`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x140072dc6`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x140072cde`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x140072cde`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x140072d57`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x140072d57`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x140072d79`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x140072de8`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x140072d79`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x140072de8`

## string_xrefs

- `0x140072e82`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`
- `0x140072eb4`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`
- `0x140072ec6`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`
- `0x140072ed8`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall anonymous_namespace_::CreateOrOpenPrivateNamespace(PSID **a1)
{
  int v2; // eax
  const char *v3; // r9
  PSID *v4; // rbx
  PSID *v5; // rdi
  const char *v6; // r9
  HANDLE v7; // rdi
  HANDLE v8; // rsi
  DWORD LastError; // ebx
  signed int v10; // eax
  unsigned __int64 v11; // r9
  HANDLE v12; // rdi
  const char *v13; // r9
  HANDLE v14; // rsi
  DWORD v15; // ebx
  HLOCAL hMem[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 *v17; // [rsp+30h] [rbp-30h]
  struct _SECURITY_ATTRIBUTES PrivateNamespaceAttributes; // [rsp+38h] [rbp-28h] BYREF
  HANDLE BoundaryDescriptor; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v17 = qword_140507220;
  if ( (unsigned int)mtx_do_lock(qword_140507220, 0) )
    std::_Throw_Cpp_error(5);
  v2 = dword_14050726C;
  if ( dword_14050726C == 0x7FFFFFFF )
  {
    dword_14050726C = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( !Handle )
  {
    BoundaryDescriptor = CreateBoundaryDescriptorW(L"USOPrivateBoundary", 0);
    if ( !BoundaryDescriptor )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x6C,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PrivateNamespaceHelpers.cpp",
        v3);
    v4 = *a1;
    v5 = a1[1];
    while ( v4 != v5 )
    {
      if ( !AddSIDToBoundaryDescriptor(&BoundaryDescriptor, *v4) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x70,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PrivateNamespaceHelpers.cpp",
          v6);
      ++v4;
    }
    *(_OWORD *)hMem = 0;
    anonymous_namespace_::SecurityDescriptorAndAcls::SecurityDescriptorAndAcls(hMem, a1);
    *(_QWORD *)&PrivateNamespaceAttributes.nLength = 24;
    *(_QWORD *)&PrivateNamespaceAttributes.bInheritHandle = 0;
    PrivateNamespaceAttributes.lpSecurityDescriptor = hMem[1];
    v7 = OpenPrivateNamespaceW(BoundaryDescriptor, L"USOPrivate");
    v8 = Handle;
    if ( Handle )
    {
      LastError = GetLastError();
      ClosePrivateNamespace(v8, 0);
      SetLastError(LastError);
    }
    Handle = v7;
    if ( !v7 )
    {
      v10 = GetLastError();
      v11 = (unsigned __int16)v10 | 0x80070000;
      if ( v10 <= 0 )
        v11 = (unsigned int)v10;
      if ( v10 != 3 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7D,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PrivateNamespaceHelpers.cpp",
          (const char *)v11,
          (int)hMem[0]);
      v12 = CreatePrivateNamespaceW(&PrivateNamespaceAttributes, BoundaryDescriptor, L"USOPrivate");
      v14 = Handle;
      if ( Handle )
      {
        v15 = GetLastError();
        ClosePrivateNamespace(v14, 0);
        SetLastError(v15);
      }
      Handle = v12;
      if ( !v12 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x81,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PrivateNamespaceHelpers.cpp",
          v13);
    }
    if ( hMem[1] )
      LocalFree(hMem[1]);
    if ( hMem[0] )
      operator delete(hMem[0]);
    if ( BoundaryDescriptor )
      DeleteBoundaryDescriptor(BoundaryDescriptor);
    v2 = dword_14050726C;
  }
  dword_14050726C = v2 - 1;
  if ( v2 == 1 )
  {
    dword_140507268 = -1;
    ReleaseSRWLockExclusive(&stru_140507230);
  }
}

```

## disassembly

```asm
0x140072c6c  mov     [rsp-8+arg_8], rbx
0x140072c71  mov     [rsp-8+arg_10], rsi
0x140072c76  mov     [rsp-8+arg_18], rdi
0x140072c7b  push    rbp
0x140072c7c  mov     rbp, rsp
0x140072c7f  sub     rsp, 60h
0x140072c83  mov     rax, cs:__security_cookie
0x140072c8a  xor     rax, rsp
0x140072c8d  mov     [rbp+var_8], rax
0x140072c91  mov     rsi, rcx
0x140072c94  lea     rcx, qword_140507220
0x140072c9b  mov     [rbp+var_30], rcx
0x140072c9f  xor     edx, edx
0x140072ca1  call    mtx_do_lock
0x140072ca6  test    eax, eax
0x140072ca8  jnz     loc_140072E94
0x140072cae  mov     eax, cs:dword_14050726C
0x140072cb4  cmp     eax, 7FFFFFFFh
0x140072cb9  jz      loc_140072E9F
0x140072cbf  cmp     cs:Handle, 0
0x140072cc7  jnz     loc_140072E3E
0x140072ccd  mov     [rbp+BoundaryDescriptor], 0
0x140072cd5  xor     edx, edx; Flags
0x140072cd7  lea     rcx, Name; "USOPrivateBoundary"
0x140072cde  call    cs:__imp_CreateBoundaryDescriptorW
0x140072ce4  mov     [rbp+BoundaryDescriptor], rax
0x140072ce8  mov     rcx, [rbp+8]; this
0x140072cec  test    rax, rax
0x140072cef  jz      loc_140072EB4
0x140072cf5  mov     rbx, [rsi]
0x140072cf8  mov     rdi, [rsi+8]
0x140072cfc  jmp     short loc_140072D1B
0x140072cfe  mov     rdx, [rbx]; RequiredSid
0x140072d01  lea     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x140072d05  call    cs:__imp_AddSIDToBoundaryDescriptor
0x140072d0b  mov     rcx, [rbp+8]; this
0x140072d0f  test    eax, eax
0x140072d11  jz      loc_140072ED8
0x140072d17  add     rbx, 8
0x140072d1b  cmp     rbx, rdi
0x140072d1e  jnz     short loc_140072CFE
0x140072d20  xorps   xmm0, xmm0
0x140072d23  movups  xmmword ptr [rbp+hMem], xmm0
0x140072d27  mov     rdx, rsi
0x140072d2a  lea     rcx, [rbp+hMem]
0x140072d2e  call    _anonymous_namespace___SecurityDescriptorAndAcls__SecurityDescriptorAndAcls
0x140072d33  nop
0x140072d34  mov     qword ptr [rbp+PrivateNamespaceAttributes.nLength], 18h
0x140072d3c  mov     qword ptr [rbp+PrivateNamespaceAttributes.bInheritHandle], 0
0x140072d44  mov     rax, [rbp+hMem+8]
0x140072d48  mov     [rbp+PrivateNamespaceAttributes.lpSecurityDescriptor], rax
0x140072d4c  lea     rdx, AliasPrefix; "USOPrivate"
0x140072d53  mov     rcx, [rbp+BoundaryDescriptor]; lpBoundaryDescriptor
0x140072d57  call    cs:__imp_OpenPrivateNamespaceW
0x140072d5d  mov     rdi, rax
0x140072d60  mov     rsi, cs:Handle
0x140072d67  test    rsi, rsi
0x140072d6a  jz      short loc_140072D87
0x140072d6c  call    cs:__imp_GetLastError
0x140072d72  mov     ebx, eax
0x140072d74  xor     edx, edx; Flags
0x140072d76  mov     rcx, rsi; Handle
0x140072d79  call    cs:__imp_ClosePrivateNamespace
0x140072d7f  mov     ecx, ebx; dwErrCode
0x140072d81  call    cs:__imp_SetLastError
0x140072d87  mov     cs:Handle, rdi
0x140072d8e  test    rdi, rdi
0x140072d91  jnz     short loc_140072E06
0x140072d93  call    cs:__imp_GetLastError
0x140072d99  movzx   r9d, ax
0x140072d9d  or      r9d, 80070000h
0x140072da4  test    eax, eax
0x140072da6  cmovle  r9d, eax; char *
0x140072daa  mov     rcx, [rbp+8]; this
0x140072dae  cmp     eax, 3
0x140072db1  jnz     loc_140072EC6
0x140072db7  lea     r8, AliasPrefix; "USOPrivate"
0x140072dbe  mov     rdx, [rbp+BoundaryDescriptor]; lpBoundaryDescriptor
0x140072dc2  lea     rcx, [rbp+PrivateNamespaceAttributes]; lpPrivateNamespaceAttributes
0x140072dc6  call    cs:__imp_CreatePrivateNamespaceW
0x140072dcc  mov     rdi, rax
0x140072dcf  mov     rsi, cs:Handle
0x140072dd6  test    rsi, rsi
0x140072dd9  jz      short loc_140072DF6
0x140072ddb  call    cs:__imp_GetLastError
0x140072de1  mov     ebx, eax
0x140072de3  xor     edx, edx; Flags
0x140072de5  mov     rcx, rsi; Handle
0x140072de8  call    cs:__imp_ClosePrivateNamespace
0x140072dee  mov     ecx, ebx; dwErrCode
0x140072df0  call    cs:__imp_SetLastError
0x140072df6  mov     cs:Handle, rdi
0x140072dfd  mov     rcx, [rbp+8]; this
0x140072e01  test    rdi, rdi
0x140072e04  jz      short loc_140072E82
0x140072e06  mov     rcx, [rbp+hMem+8]; hMem
0x140072e0a  test    rcx, rcx
0x140072e0d  jz      short loc_140072E15
0x140072e0f  call    cs:__imp_LocalFree
0x140072e15  mov     rcx, [rbp+hMem]; Block
0x140072e19  test    rcx, rcx
0x140072e1c  jz      short loc_140072E29
0x140072e1e  mov     edx, 8
0x140072e23  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140072e28  nop
0x140072e29  mov     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x140072e2d  test    rcx, rcx
0x140072e30  jz      short loc_140072E38
0x140072e32  call    cs:__imp_DeleteBoundaryDescriptor
0x140072e38  mov     eax, cs:dword_14050726C
0x140072e3e  sub     eax, 1
0x140072e41  mov     cs:dword_14050726C, eax
0x140072e47  jnz     short loc_140072E60
0x140072e49  mov     cs:dword_140507268, 0FFFFFFFFh
0x140072e53  lea     rcx, stru_140507230; SRWLock
0x140072e5a  call    cs:__imp_ReleaseSRWLockExclusive
0x140072e60  mov     rcx, [rbp+var_8]
0x140072e64  xor     rcx, rsp; StackCookie
0x140072e67  call    __security_check_cookie
0x140072e6c  lea     r11, [rsp+60h+var_s0]
0x140072e71  mov     rbx, [r11+18h]
0x140072e75  mov     rsi, [r11+20h]
0x140072e79  mov     rdi, [r11+28h]
0x140072e7d  mov     rsp, r11
0x140072e80  pop     rbp
0x140072e81  retn
0x140072e82  lea     r8, aCW1SSrcOrchest_0; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140072e89  mov     edx, 81h; void *
0x140072e8e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140072e94  mov     ecx, 5; int
0x140072e99  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140072e9f  mov     cs:dword_14050726C, 7FFFFFFEh
0x140072ea9  mov     ecx, 6; int
0x140072eae  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140072eb4  lea     r8, aCW1SSrcOrchest_0; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140072ebb  mov     edx, 6Ch ; 'l'; void *
0x140072ec0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140072ec6  lea     r8, aCW1SSrcOrchest_0; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140072ecd  mov     edx, 7Dh ; '}'; void *
0x140072ed2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140072ed8  lea     r8, aCW1SSrcOrchest_0; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140072edf  mov     edx, 70h ; 'p'; void *
0x140072ee4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
