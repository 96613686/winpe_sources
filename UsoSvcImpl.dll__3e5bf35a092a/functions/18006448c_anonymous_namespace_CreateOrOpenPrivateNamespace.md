# _anonymous_namespace_::CreateOrOpenPrivateNamespace

- ea: `0x18006448c`
- end: `0x180064708`
- name: `_anonymous_namespace_::CreateOrOpenPrivateNamespace`
- size: `636`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180064768`
- `0x1800648fc`
- `0x180064a3c`

## callees

- `0x180010f24`
- `0x1800112d0`
- `0x180042e00`
- `0x180042e48`
- `0x1800642b8`
- `0x18006448c`
- `0x1800dd930`
- `0x1800dddf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180064678`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180064678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006458a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800645b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800645f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006458a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800645b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800645f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006459f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006460e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006459f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006460e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006462d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006462d`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x1800645e4`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x1800645e4`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x180064575`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x180064575`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x180064523`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x180064523`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180064597`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180064606`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180064597`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180064606`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x1800644fc`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x1800644fc`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180064650`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180064650`

## string_xrefs

- `0x1800646a0`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`
- `0x1800646d2`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`
- `0x1800646e4`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`
- `0x1800646f6`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`

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

  v17 = qword_18014D1E0;
  if ( (unsigned int)mtx_do_lock() )
    std::_Throw_Cpp_error(5);
  v2 = dword_18014D22C;
  if ( dword_18014D22C == 0x7FFFFFFF )
  {
    dword_18014D22C = 2147483646;
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
      operator delete(hMem[0], (const struct std::nothrow_t *)8);
    if ( BoundaryDescriptor )
      DeleteBoundaryDescriptor(BoundaryDescriptor);
    v2 = dword_18014D22C;
  }
  dword_18014D22C = v2 - 1;
  if ( v2 == 1 )
  {
    dword_18014D228 = -1;
    ReleaseSRWLockExclusive(&stru_18014D1F0);
  }
}

```

## disassembly

```asm
0x18006448c  mov     [rsp-8+arg_8], rbx
0x180064491  mov     [rsp-8+arg_10], rsi
0x180064496  mov     [rsp-8+arg_18], rdi
0x18006449b  push    rbp
0x18006449c  mov     rbp, rsp
0x18006449f  sub     rsp, 60h
0x1800644a3  mov     rax, cs:__security_cookie
0x1800644aa  xor     rax, rsp
0x1800644ad  mov     [rbp+var_8], rax
0x1800644b1  mov     rsi, rcx
0x1800644b4  lea     rcx, qword_18014D1E0
0x1800644bb  mov     [rbp+var_30], rcx
0x1800644bf  call    mtx_do_lock
0x1800644c4  test    eax, eax
0x1800644c6  jnz     loc_1800646B2
0x1800644cc  mov     eax, cs:dword_18014D22C
0x1800644d2  cmp     eax, 7FFFFFFFh
0x1800644d7  jz      loc_1800646BD
0x1800644dd  cmp     cs:Handle, 0
0x1800644e5  jnz     loc_18006465C
0x1800644eb  mov     [rbp+BoundaryDescriptor], 0
0x1800644f3  xor     edx, edx; Flags
0x1800644f5  lea     rcx, aUsoprivateboun; "USOPrivateBoundary"
0x1800644fc  call    cs:__imp_CreateBoundaryDescriptorW
0x180064502  mov     [rbp+BoundaryDescriptor], rax
0x180064506  mov     rcx, [rbp+8]; this
0x18006450a  test    rax, rax
0x18006450d  jz      loc_1800646D2
0x180064513  mov     rbx, [rsi]
0x180064516  mov     rdi, [rsi+8]
0x18006451a  jmp     short loc_180064539
0x18006451c  mov     rdx, [rbx]; RequiredSid
0x18006451f  lea     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x180064523  call    cs:__imp_AddSIDToBoundaryDescriptor
0x180064529  mov     rcx, [rbp+8]; this
0x18006452d  test    eax, eax
0x18006452f  jz      loc_1800646F6
0x180064535  add     rbx, 8
0x180064539  cmp     rbx, rdi
0x18006453c  jnz     short loc_18006451C
0x18006453e  xorps   xmm0, xmm0
0x180064541  movups  xmmword ptr [rbp+hMem], xmm0
0x180064545  mov     rdx, rsi
0x180064548  lea     rcx, [rbp+hMem]
0x18006454c  call    _anonymous_namespace___SecurityDescriptorAndAcls__SecurityDescriptorAndAcls
0x180064551  nop
0x180064552  mov     qword ptr [rbp+PrivateNamespaceAttributes.nLength], 18h
0x18006455a  mov     qword ptr [rbp+PrivateNamespaceAttributes.bInheritHandle], 0
0x180064562  mov     rax, [rbp+hMem+8]
0x180064566  mov     [rbp+PrivateNamespaceAttributes.lpSecurityDescriptor], rax
0x18006456a  lea     rdx, AliasPrefix; "USOPrivate"
0x180064571  mov     rcx, [rbp+BoundaryDescriptor]; lpBoundaryDescriptor
0x180064575  call    cs:__imp_OpenPrivateNamespaceW
0x18006457b  mov     rdi, rax
0x18006457e  mov     rsi, cs:Handle
0x180064585  test    rsi, rsi
0x180064588  jz      short loc_1800645A5
0x18006458a  call    cs:__imp_GetLastError
0x180064590  mov     ebx, eax
0x180064592  xor     edx, edx; Flags
0x180064594  mov     rcx, rsi; Handle
0x180064597  call    cs:__imp_ClosePrivateNamespace
0x18006459d  mov     ecx, ebx; dwErrCode
0x18006459f  call    cs:__imp_SetLastError
0x1800645a5  mov     cs:Handle, rdi
0x1800645ac  test    rdi, rdi
0x1800645af  jnz     short loc_180064624
0x1800645b1  call    cs:__imp_GetLastError
0x1800645b7  movzx   r9d, ax
0x1800645bb  or      r9d, 80070000h
0x1800645c2  test    eax, eax
0x1800645c4  cmovle  r9d, eax; char *
0x1800645c8  mov     rcx, [rbp+8]; this
0x1800645cc  cmp     eax, 3
0x1800645cf  jnz     loc_1800646E4
0x1800645d5  lea     r8, AliasPrefix; "USOPrivate"
0x1800645dc  mov     rdx, [rbp+BoundaryDescriptor]; lpBoundaryDescriptor
0x1800645e0  lea     rcx, [rbp+PrivateNamespaceAttributes]; lpPrivateNamespaceAttributes
0x1800645e4  call    cs:__imp_CreatePrivateNamespaceW
0x1800645ea  mov     rdi, rax
0x1800645ed  mov     rsi, cs:Handle
0x1800645f4  test    rsi, rsi
0x1800645f7  jz      short loc_180064614
0x1800645f9  call    cs:__imp_GetLastError
0x1800645ff  mov     ebx, eax
0x180064601  xor     edx, edx; Flags
0x180064603  mov     rcx, rsi; Handle
0x180064606  call    cs:__imp_ClosePrivateNamespace
0x18006460c  mov     ecx, ebx; dwErrCode
0x18006460e  call    cs:__imp_SetLastError
0x180064614  mov     cs:Handle, rdi
0x18006461b  mov     rcx, [rbp+8]; this
0x18006461f  test    rdi, rdi
0x180064622  jz      short loc_1800646A0
0x180064624  mov     rcx, [rbp+hMem+8]; hMem
0x180064628  test    rcx, rcx
0x18006462b  jz      short loc_180064633
0x18006462d  call    cs:__imp_LocalFree
0x180064633  mov     rcx, [rbp+hMem]; void *
0x180064637  test    rcx, rcx
0x18006463a  jz      short loc_180064647
0x18006463c  mov     edx, 8; struct std::nothrow_t *
0x180064641  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180064646  nop
0x180064647  mov     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x18006464b  test    rcx, rcx
0x18006464e  jz      short loc_180064656
0x180064650  call    cs:__imp_DeleteBoundaryDescriptor
0x180064656  mov     eax, cs:dword_18014D22C
0x18006465c  sub     eax, 1
0x18006465f  mov     cs:dword_18014D22C, eax
0x180064665  jnz     short loc_18006467E
0x180064667  mov     cs:dword_18014D228, 0FFFFFFFFh
0x180064671  lea     rcx, stru_18014D1F0; SRWLock
0x180064678  call    cs:__imp_ReleaseSRWLockExclusive
0x18006467e  mov     rcx, [rbp+var_8]
0x180064682  xor     rcx, rsp; StackCookie
0x180064685  call    __security_check_cookie
0x18006468a  lea     r11, [rsp+60h+var_s0]
0x18006468f  mov     rbx, [r11+18h]
0x180064693  mov     rsi, [r11+20h]
0x180064697  mov     rdi, [r11+28h]
0x18006469b  mov     rsp, r11
0x18006469e  pop     rbp
0x18006469f  retn
0x1800646a0  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800646a7  mov     edx, 81h; void *
0x1800646ac  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800646b2  mov     ecx, 5; int
0x1800646b7  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800646bd  mov     cs:dword_18014D22C, 7FFFFFFEh
0x1800646c7  mov     ecx, 6; int
0x1800646cc  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800646d2  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800646d9  mov     edx, 6Ch ; 'l'; void *
0x1800646de  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800646e4  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800646eb  mov     edx, 7Dh ; '}'; void *
0x1800646f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800646f6  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800646fd  mov     edx, 70h ; 'p'; void *
0x180064702  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
