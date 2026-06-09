# GetApplicablePackagesForUserWithAppChosenResources

- ea: `0x18000d510`
- end: `0x18000d6ee`
- name: `GetApplicablePackagesForUserWithAppChosenResources`
- size: `478`
- prototype: `__int64 __fastcall(struct IAppxBundleManifestReader *, void *, __int64, const unsigned __int16 **, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d290`

## callees

- `0x1800098c0`
- `0x180009ed0`
- `0x18000a9a4`
- `0x18000af18`
- `0x18000cef0`
- `0x18000d510`
- `0x18000d6f4`
- `0x18000db80`
- `0x1800227c0`

## pseudocode

```c
__int64 __fastcall GetApplicablePackagesForUserWithAppChosenResources(
        struct IAppxBundleManifestReader *a1,
        void *a2,
        __int64 a3,
        const unsigned __int16 **a4,
        _DWORD *a5,
        _QWORD *a6)
{
  unsigned int v7; // r15d
  int ApplicabilityContext; // eax
  int v11; // edx
  int v12; // ecx
  int v13; // ebx
  int v14; // edx
  int v15; // ecx
  int v16; // ebx
  int v17; // edx
  int v18; // ecx
  int ApplicablePackagesWithAppChosenResources; // ebx
  __int64 v20; // rcx
  __int64 v21; // r8
  const char *v22; // r9
  __int64 result; // rax
  int v24; // [rsp+20h] [rbp-78h]
  int v25; // [rsp+20h] [rbp-78h]
  struct ApplicabilityContext *v26[2]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v7 = a3;
  if ( (Microsoft_Windows_ApplicabilityEngineEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, GetApplicablePackages_Start, a3, 1, v26);
  *a6 = 0;
  *a5 = 0;
  v26[0] = 0;
  ApplicabilityContext = CreateApplicabilityContext(v26);
  v13 = ApplicabilityContext;
  if ( ApplicabilityContext == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
    McTemplateU0zqd_EventWriteTransfer(
      v12,
      v11,
      (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
      511,
      94);
  try
  {
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1FF,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        (const char *)(unsigned int)v13,
        v24);
    v16 = GetApplicabilityContext(a2, v26[0]);
    if ( v16 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
      McTemplateU0zqd_EventWriteTransfer(
        v15,
        v14,
        (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        512,
        94);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x200,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        (const char *)(unsigned int)v16,
        v24);
    ApplicablePackagesWithAppChosenResources = GetApplicablePackagesWithAppChosenResources(a1, v26[0], v7, a4, a5, a6);
    if ( ApplicablePackagesWithAppChosenResources == -2147023266
      && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
    {
      McTemplateU0zqd_EventWriteTransfer(
        v18,
        v17,
        (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        513,
        94);
    }
    if ( ApplicablePackagesWithAppChosenResources < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x201,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        (const char *)(unsigned int)ApplicablePackagesWithAppChosenResources,
        v25);
    wil::details::unique_storage<wil::details::resource_policy<ApplicabilityContext *,long (*)(ApplicabilityContext *),&long FreeApplicabilityContext(ApplicabilityContext *),wistd::integral_constant<unsigned __int64,0>,ApplicabilityContext *,ApplicabilityContext *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ApplicabilityContext *,long (*)(ApplicabilityContext *),&long FreeApplicabilityContext(ApplicabilityContext *),wistd::integral_constant<unsigned __int64,0>,ApplicabilityContext *,ApplicabilityContext *,0,std::nullptr_t>>(v26);
    if ( (Microsoft_Windows_ApplicabilityEngineEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v20, "k", v21, 1, v26);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x205,
                           (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
                           v22);
  }
  return result;
}

```

## disassembly

```asm
0x18000d510  push    rbx
0x18000d512  push    rsi
0x18000d513  push    rdi
0x18000d514  push    r12
0x18000d516  push    r13
0x18000d518  push    r14
0x18000d51a  push    r15
0x18000d51c  sub     rsp, 60h
0x18000d520  mov     [rsp+98h+var_60], 0FFFFFFFFFFFFFFFEh
0x18000d529  mov     rax, cs:__security_cookie
0x18000d530  xor     rax, rsp
0x18000d533  mov     [rsp+98h+var_48], rax
0x18000d538  mov     r13, r9
0x18000d53b  mov     r15d, r8d
0x18000d53e  mov     rdi, rdx
0x18000d541  mov     r12, rcx
0x18000d544  mov     rsi, [rsp+98h+arg_20]
0x18000d54c  mov     r14, [rsp+98h+arg_28]
0x18000d554  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 1
0x18000d55b  jz      short loc_18000D579
0x18000d55d  lea     rax, [rsp+98h+var_58]
0x18000d562  mov     [rsp+98h+var_78], rax
0x18000d567  mov     r9d, 1
0x18000d56d  lea     rdx, GetApplicablePackages_Start
0x18000d574  call    McGenEventWrite_EventWriteTransfer
0x18000d579  mov     [rsp+98h+var_67], 1
0x18000d57e  xor     eax, eax
0x18000d580  mov     [r14], rax
0x18000d583  mov     [rsi], eax
0x18000d585  mov     [rsp+98h+var_58], rax
0x18000d58a  lea     rcx, [rsp+98h+var_58]
0x18000d58f  call    CreateApplicabilityContext
0x18000d594  mov     ebx, eax
0x18000d596  mov     eax, 8007065Eh
0x18000d59b  cmp     ebx, eax
0x18000d59d  jnz     short loc_18000D5BE
0x18000d59f  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 2
0x18000d5a6  jz      short loc_18000D5BE
0x18000d5a8  mov     dword ptr [rsp+98h+var_78], eax; int
0x18000d5ac  mov     r9d, 1FFh
0x18000d5b2  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000d5b9  call    McTemplateU0zqd_EventWriteTransfer
0x18000d5be  mov     rcx, [rsp+98h]; this
0x18000d5c6  test    ebx, ebx
0x18000d5c8  jns     short loc_18000D5DE
0x18000d5ca  mov     r9d, ebx; char *
0x18000d5cd  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000d5d4  mov     edx, 1FFh; void *
0x18000d5d9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d5de  mov     rdx, [rsp+98h+var_58]; struct ApplicabilityContext *
0x18000d5e3  mov     rcx, rdi; void *
0x18000d5e6  call    ?GetApplicabilityContext@@YAJPEAXPEAVApplicabilityContext@@@Z; GetApplicabilityContext(void *,ApplicabilityContext *)
0x18000d5eb  mov     ebx, eax
0x18000d5ed  mov     edi, 8007065Eh
0x18000d5f2  cmp     eax, edi
0x18000d5f4  jnz     short loc_18000D615
0x18000d5f6  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 2
0x18000d5fd  jz      short loc_18000D615
0x18000d5ff  mov     dword ptr [rsp+98h+var_78], edi; int
0x18000d603  mov     r9d, 200h
0x18000d609  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000d610  call    McTemplateU0zqd_EventWriteTransfer
0x18000d615  mov     rcx, [rsp+98h]; this
0x18000d61d  test    ebx, ebx
0x18000d61f  jns     short loc_18000D635
0x18000d621  mov     r9d, ebx; char *
0x18000d624  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000d62b  mov     edx, 200h; void *
0x18000d630  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d635  mov     [rsp+98h+var_70], r14; __int64
0x18000d63a  mov     [rsp+98h+var_78], rsi; __int64
0x18000d63f  mov     r9, r13; unsigned __int16 **
0x18000d642  mov     r8d, r15d; unsigned int
0x18000d645  mov     rdx, [rsp+98h+var_58]; struct ApplicabilityContext *
0x18000d64a  mov     rcx, r12; struct IAppxBundleManifestReader *
0x18000d64d  call    GetApplicablePackagesWithAppChosenResources
0x18000d652  mov     ebx, eax
0x18000d654  cmp     eax, edi
0x18000d656  jnz     short loc_18000D677
0x18000d658  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 2
0x18000d65f  jz      short loc_18000D677
0x18000d661  mov     dword ptr [rsp+98h+var_78], edi; int
0x18000d665  mov     r9d, 201h
0x18000d66b  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000d672  call    McTemplateU0zqd_EventWriteTransfer
0x18000d677  mov     rcx, [rsp+98h]; this
0x18000d67f  test    ebx, ebx
0x18000d681  jns     short loc_18000D698
0x18000d683  mov     r9d, ebx; char *
0x18000d686  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000d68d  mov     edx, 201h; void *
0x18000d692  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d698  lea     rcx, [rsp+98h+var_58]
0x18000d69d  call    ??1?$unique_storage@U?$resource_policy@PEAVApplicabilityContext@@P6AJPEAV1@@Z$1?FreeApplicabilityContext@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAV1@PEAV1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ApplicabilityContext *,long (*)(ApplicabilityContext *),&FreeApplicabilityContext(ApplicabilityContext *),wistd::integral_constant<unsigned __int64,0>,ApplicabilityContext *,ApplicabilityContext *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ApplicabilityContext *,long (*)(ApplicabilityContext *),&FreeApplicabilityContext(ApplicabilityContext *),wistd::integral_constant<unsigned __int64,0>,ApplicabilityContext *,ApplicabilityContext *,0,std::nullptr_t>>(void)
0x18000d6a2  nop
0x18000d6a3  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 1
0x18000d6aa  jz      short loc_18000D6C8
0x18000d6ac  lea     rax, [rsp+98h+var_58]
0x18000d6b1  mov     [rsp+98h+var_78], rax
0x18000d6b6  mov     r9d, 1
0x18000d6bc  lea     rdx, GetApplicablePackages_Stop; "k"
0x18000d6c3  call    McGenEventWrite_EventWriteTransfer
0x18000d6c8  xor     eax, eax
0x18000d6ca  jmp     short loc_18000D6D0
0x18000d6cc  mov     eax, [rsp+30h]
0x18000d6d0  mov     rcx, [rsp+98h+var_48]
0x18000d6d5  xor     rcx, rsp; StackCookie
0x18000d6d8  call    __security_check_cookie
0x18000d6dd  add     rsp, 60h
0x18000d6e1  pop     r15
0x18000d6e3  pop     r14
0x18000d6e5  pop     r13
0x18000d6e7  pop     r12
0x18000d6e9  pop     rdi
0x18000d6ea  pop     rsi
0x18000d6eb  pop     rbx
0x18000d6ec  retn
```
