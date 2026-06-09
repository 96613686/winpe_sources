# CBrowserBrokerInstance::TakeTaskExemptionInternal(ulong)

- ea: `0x18000d368`
- end: `0x18000d4dd`
- name: `?TakeTaskExemptionInternal@CBrowserBrokerInstance@@AEAAJK@Z`
- size: `373`
- prototype: `__int64 __fastcall(CBrowserBrokerInstance *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d320`
- `0x18000d4f0`

## callees

- `0x1800066d8`
- `0x1800068f0`
- `0x1800072ec`
- `0x18000a4d0`
- `0x18000d368`
- `0x18000dc74`
- `0x18000dfdc`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d42e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d42e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d395`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d473`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d395`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d473`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d3dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d3dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4be`

## string_xrefs

- `0x18000d43f`: `onecoreuap\inetcore\spartan\desktopbroker\brokerfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CBrowserBrokerInstance::TakeTaskExemptionInternal(CBrowserBrokerInstance *this, unsigned int a2)
{
  __int64 *v3; // r14
  __int64 v4; // rdi
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  __int64 v6; // rsi
  HRESULT v7; // eax
  int v8; // edi
  int ppv; // [rsp+20h] [rbp-38h]
  unsigned int v11; // [rsp+30h] [rbp-28h] BYREF
  LPVOID v12; // [rsp+38h] [rbp-20h] BYREF
  _BYTE v13[24]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  LPVOID v15; // [rsp+90h] [rbp+38h] BYREF
  unsigned int v16; // [rsp+98h] [rbp+40h] BYREF
  struct _RTL_CRITICAL_SECTION *v17; // [rsp+A0h] [rbp+48h] BYREF
  __int64 v18; // [rsp+A8h] [rbp+50h] BYREF

  v16 = a2;
  v3 = (__int64 *)((char *)this + 1232);
  v4 = 0;
  v17 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1192);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1192));
  std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<IOSTaskCompletion>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<IOSTaskCompletion>>>,0>>::find(
    v3,
    &v18,
    &v16);
  v6 = v18;
  if ( v18 != *v3 )
  {
    Microsoft::WRL::ComPtr<IOSTaskCompletion>::operator=((__int64 *)&v17, (_QWORD *)(v18 + 40));
    std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<IOSTaskCompletion>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<IOSTaskCompletion>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,Microsoft::WRL::ComPtr<IOSTaskCompletion>>>>>,0>(
      (__int64)v3,
      &v18,
      v6);
    v4 = (__int64)v17;
  }
  if ( v5 )
    LeaveCriticalSection(v5);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 40LL))(v4);
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v17);
  v15 = 0;
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v15);
  v7 = CoCreateInstance(&CLSID_OSTaskCompletion, 0, 1u, &GUID_c7e40572_c36a_43ea_9a40_f3b168da5558, &v15);
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xB73,
      (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\brokerfactory.cpp",
      (const char *)(unsigned int)v7,
      ppv);
  v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)v15 + 24LL))(v15, a2, 16);
  if ( v8 >= 0 )
  {
    EnterCriticalSection(v5);
    v17 = v5;
    v11 = a2;
    v12 = v15;
    if ( v15 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 8LL))(v15);
    std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<IOSTaskCompletion>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<IOSTaskCompletion>>>,0>>::_Emplace<std::pair<unsigned long,Microsoft::WRL::ComPtr<IOSTaskCompletion>>>(
      v3,
      (__int64)v13,
      (__int64)&v11);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v12);
    if ( v5 )
      LeaveCriticalSection(v5);
  }
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v15);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d368  mov     [rsp-30h+arg_8], edx
0x18000d36c  push    rbp
0x18000d36d  push    rbx
0x18000d36e  push    rsi
0x18000d36f  push    rdi
0x18000d370  push    r14
0x18000d372  push    r15
0x18000d374  mov     rbp, rsp
0x18000d377  sub     rsp, 58h
0x18000d37b  mov     r15d, edx
0x18000d37e  lea     r14, [rcx+4D0h]
0x18000d385  xor     edi, edi
0x18000d387  mov     [rbp+arg_10], rdi
0x18000d38b  lea     rbx, [rcx+4A8h]
0x18000d392  mov     rcx, rbx; lpCriticalSection
0x18000d395  call    cs:__imp_EnterCriticalSection
0x18000d39b  lea     r8, [rbp+arg_8]
0x18000d39f  lea     rdx, [rbp+arg_18]
0x18000d3a3  mov     rcx, r14
0x18000d3a6  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$ComPtr@UIOSTaskCompletion@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@UIOSTaskCompletion@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@UIOSTaskCompletion@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<IOSTaskCompletion>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<IOSTaskCompletion>>>,0>>::find(ulong const &)
0x18000d3ab  mov     rsi, [rbp+arg_18]
0x18000d3af  cmp     rsi, [r14]
0x18000d3b2  jz      short loc_18000D3D4
0x18000d3b4  lea     rdx, [rsi+28h]
0x18000d3b8  lea     rcx, [rbp+arg_10]
0x18000d3bc  call    ??4?$ComPtr@UIOSTaskCompletion@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IOSTaskCompletion>::operator=(Microsoft::WRL::ComPtr<IOSTaskCompletion> const &)
0x18000d3c1  mov     r8, rsi
0x18000d3c4  lea     rdx, [rbp+arg_18]
0x18000d3c8  mov     rcx, r14
0x18000d3cb  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@UIOSTaskCompletion@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@KV?$ComPtr@UIOSTaskCompletion@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@UIOSTaskCompletion@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@UIOSTaskCompletion@@@WRL@Microsoft@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<IOSTaskCompletion>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<IOSTaskCompletion>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Microsoft::WRL::ComPtr<IOSTaskCompletion>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Microsoft::WRL::ComPtr<IOSTaskCompletion>>>>>)
0x18000d3d0  mov     rdi, [rbp+arg_10]
0x18000d3d4  test    rbx, rbx
0x18000d3d7  jz      short loc_18000D3E2
0x18000d3d9  mov     rcx, rbx; lpCriticalSection
0x18000d3dc  call    cs:__imp_LeaveCriticalSection
0x18000d3e2  test    rdi, rdi
0x18000d3e5  jz      short loc_18000D3F7
0x18000d3e7  mov     rax, [rdi]
0x18000d3ea  mov     rcx, rdi
0x18000d3ed  mov     rax, [rax+28h]
0x18000d3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3f6  nop
0x18000d3f7  lea     rcx, [rbp+arg_10]
0x18000d3fb  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18000d400  mov     [rbp+arg_0], 0
0x18000d408  lea     rcx, [rbp+arg_0]
0x18000d40c  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18000d411  lea     rax, [rbp+arg_0]
0x18000d415  mov     qword ptr [rsp+58h+ppv], rax; int
0x18000d41a  lea     r9, _GUID_c7e40572_c36a_43ea_9a40_f3b168da5558; riid
0x18000d421  xor     edx, edx; pUnkOuter
0x18000d423  lea     r8d, [rdx+1]; dwClsContext
0x18000d427  lea     rcx, CLSID_OSTaskCompletion; rclsid
0x18000d42e  call    cs:__imp_CoCreateInstance
0x18000d434  mov     rcx, [rbp+30h]; this
0x18000d438  test    eax, eax
0x18000d43a  jns     short loc_18000D451
0x18000d43c  mov     r9d, eax; char *
0x18000d43f  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18000d446  mov     edx, 0B73h; void *
0x18000d44b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000d451  mov     rcx, [rbp+arg_0]
0x18000d455  mov     rax, [rcx]
0x18000d458  mov     r8d, 10h
0x18000d45e  mov     edx, r15d
0x18000d461  mov     rax, [rax+18h]
0x18000d465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d46a  mov     edi, eax
0x18000d46c  test    eax, eax
0x18000d46e  js      short loc_18000D4C5
0x18000d470  mov     rcx, rbx; lpCriticalSection
0x18000d473  call    cs:__imp_EnterCriticalSection
0x18000d479  mov     [rbp+arg_10], rbx
0x18000d47d  mov     [rbp+var_28], r15d
0x18000d481  mov     rcx, [rbp+arg_0]
0x18000d485  mov     [rbp+var_20], rcx
0x18000d489  test    rcx, rcx
0x18000d48c  jz      short loc_18000D49B
0x18000d48e  mov     rax, [rcx]
0x18000d491  mov     rax, [rax+8]
0x18000d495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d49a  nop
0x18000d49b  lea     r8, [rbp+var_28]
0x18000d49f  lea     rdx, [rbp+var_18]
0x18000d4a3  mov     rcx, r14
0x18000d4a6  call    ??$_Emplace@U?$pair@KV?$ComPtr@UIOSTaskCompletion@@@WRL@Microsoft@@@std@@@?$_Tree@V?$_Tmap_traits@KV?$ComPtr@UIOSTaskCompletion@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@UIOSTaskCompletion@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$ComPtr@UIOSTaskCompletion@@@WRL@Microsoft@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@KV?$ComPtr@UIOSTaskCompletion@@@WRL@Microsoft@@@1@@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<IOSTaskCompletion>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<IOSTaskCompletion>>>,0>>::_Emplace<std::pair<ulong,Microsoft::WRL::ComPtr<IOSTaskCompletion>>>(std::pair<ulong,Microsoft::WRL::ComPtr<IOSTaskCompletion>> &&)
0x18000d4ab  nop
0x18000d4ac  lea     rcx, [rbp+var_20]
0x18000d4b0  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18000d4b5  nop
0x18000d4b6  test    rbx, rbx
0x18000d4b9  jz      short loc_18000D4C5
0x18000d4bb  mov     rcx, rbx; lpCriticalSection
0x18000d4be  call    cs:__imp_LeaveCriticalSection
0x18000d4c4  nop
0x18000d4c5  lea     rcx, [rbp+arg_0]
0x18000d4c9  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18000d4ce  mov     eax, edi
0x18000d4d0  add     rsp, 58h
0x18000d4d4  pop     r15
0x18000d4d6  pop     r14
0x18000d4d8  pop     rdi
0x18000d4d9  pop     rsi
0x18000d4da  pop     rbx
0x18000d4db  pop     rbp
0x18000d4dc  retn
```
