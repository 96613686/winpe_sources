# CodeIntegrity::Management::BeginRemoveCIPolicy(_GUID const *)

- ea: `0x180011c00`
- end: `0x180011cf4`
- name: `?BeginRemoveCIPolicy@Management@CodeIntegrity@@YAXPEBU_GUID@@@Z`
- size: `244`
- prototype: `void __fastcall(CodeIntegrity::Management *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008ab0`

## callees

- `0x18000d470`
- `0x18000de54`
- `0x18000f33c`
- `0x180011308`
- `0x1800114f8`
- `0x180011c00`
- `0x180013fa8`
- `0x1800154c0`
- `0x180015518`
- `0x18002195c`

## string_xrefs

- `0x180011c99`: `onecore\base\ci\management\dll\manageci.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CodeIntegrity::Management::BeginRemoveCIPolicy(CodeIntegrity::Management *this, const struct _GUID *a2)
{
  unsigned __int8 **v3; // rbx
  unsigned int v4; // r8d
  const char *v5; // r9
  const struct CodeIntegrity::Management::SiPolicyView *v6; // rbx
  int v7; // eax
  wil *v8; // rcx
  CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *v9; // rbx
  int v10; // eax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v14; // [rsp+28h] [rbp-20h] BYREF
  char v15; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v17; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int8 *v18; // [rsp+60h] [rbp+18h] BYREF

  v17 = 0;
  v3 = (unsigned __int8 **)qword_180039828;
  std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::find<_GUID,std::less<void>,0>(
    qword_180039828,
    &v18,
    this);
  try
  {
    if ( v18 == *v3 )
      wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x1A5, v4, v5, v13[0]);
    v6 = (const struct CodeIntegrity::Management::SiPolicyView *)(v18 + 32);
    if ( v18[125] )
      wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x1AD, v4, (const char *)0x80070005LL, v13[0]);
    *(_QWORD *)v13 = &v17;
    v14 = 0;
    v15 = 1;
    v7 = SIPolicyPmDeletePolicyBegin(this, v18[123], &v14);
    v8 = retaddr;
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x1B3,
        (int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
        (const char *)(unsigned int)v7,
        v13[0]);
  }
  catch ( std::exception )
  {
    v9 = qword_180039708;
    v10 = wil::ResultFromCaughtException(v8);
    CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRemoveCIPolicy(v9, v10);
    wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0x1BF, v11, v12);
  }
  if ( v18 == *v3 )
    wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x1A5, v4, v5, v13[0]);
  v6 = (const struct CodeIntegrity::Management::SiPolicyView *)(v18 + 32);
  if ( v18[125] )
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x1AD, v4, (const char *)0x80070005LL, v13[0]);
  *(_QWORD *)v13 = &v17;
}

```

## disassembly

```asm
0x180011c00  mov     [rsp+arg_0], rbx
0x180011c05  push    rdi
0x180011c06  sub     rsp, 40h
0x180011c0a  mov     rdi, rcx
0x180011c0d  mov     [rsp+48h+arg_8], 0
0x180011c16  mov     r8, rcx
0x180011c19  lea     rdx, [rsp+48h+arg_10]
0x180011c1e  mov     rbx, cs:qword_180039828
0x180011c25  mov     rcx, rbx
0x180011c28  call    ??$find@U_GUID@@U?$less@X@std@@$0A@@?$_Tree@V?$_Tset_traits@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VSiPolicyView@Management@CodeIntegrity@@@std@@@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::find<_GUID,std::less<void>,0>(_GUID const &)
0x180011c2d  mov     rax, [rsp+48h+arg_10]
0x180011c32  cmp     rax, [rbx]
0x180011c35  jnz     short loc_180011C46
0x180011c37  mov     rcx, [rsp+48h]; this
0x180011c3c  mov     edx, 1A5h; void *
0x180011c41  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180011c46  lea     rbx, [rax+20h]
0x180011c4a  cmp     byte ptr [rbx+5Dh], 0
0x180011c4e  jz      short loc_180011C65
0x180011c50  mov     rcx, [rsp+48h]; this
0x180011c55  mov     edx, 1ADh; void *
0x180011c5a  mov     r9d, 80070005h; char *
0x180011c60  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011c65  lea     rax, [rsp+48h+arg_8]
0x180011c6a  mov     qword ptr [rsp+48h+var_28], rax; int
0x180011c6f  mov     [rsp+48h+var_20], 0
0x180011c78  mov     [rsp+48h+var_18], 1
0x180011c7d  lea     r8, [rsp+48h+var_20]
0x180011c82  mov     dl, [rbx+5Bh]
0x180011c85  mov     rcx, rdi
0x180011c88  call    SIPolicyPmDeletePolicyBegin
0x180011c8d  mov     rcx, [rsp+48h]; this
0x180011c92  test    eax, eax
0x180011c94  jns     short loc_180011CAB
0x180011c96  mov     r9d, eax; char *
0x180011c99  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x180011ca0  mov     edx, 1B3h; void *
0x180011ca5  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180011cab  lea     rcx, [rsp+48h+var_28]
0x180011cb0  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180011cb5  mov     rdx, rbx; struct CodeIntegrity::Management::SiPolicyView *
0x180011cb8  mov     rcx, cs:qword_180039708; this
0x180011cbf  call    ?InstrumentRemoveCIPolicy@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVSiPolicyView@45@@Z; CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRemoveCIPolicy(CodeIntegrity::Management::SiPolicyView const &)
0x180011cc4  mov     r9, rbx
0x180011cc7  lea     r8, [rsp+48h+arg_8]
0x180011ccc  lea     rdx, [rsp+48h+var_28]
0x180011cd1  mov     rcx, cs:qword_180039840
0x180011cd8  call    ??$_Emplace@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBVSiPolicyView@Management@CodeIntegrity@@@?$_Tree@V?$_Tset_traits@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@_N@1@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBVSiPolicyView@Management@CodeIntegrity@@@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>,0>>::_Emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,CodeIntegrity::Management::SiPolicyView const &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,CodeIntegrity::Management::SiPolicyView const &)
0x180011cdd  nop
0x180011cde  lea     rcx, [rsp+48h+arg_8]
0x180011ce3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180011ce8  nop
0x180011ce9  mov     rbx, [rsp+48h+arg_0]
0x180011cee  add     rsp, 40h
0x180011cf2  pop     rdi
0x180011cf3  retn
```
