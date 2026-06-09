# CodeIntegrity::Management::ParsePolicy(uchar const *,unsigned __int64)

- ea: `0x180014c20`
- end: `0x180014ccf`
- name: `?ParsePolicy@Management@CodeIntegrity@@YA?AV?$unique_ptr@$$CBVSiPolicyView@Management@CodeIntegrity@@U?$default_delete@$$CBVSiPolicyView@Management@CodeIntegrity@@@std@@@std@@PEBE_K@Z`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009420`

## callees

- `0x180002ab4`
- `0x18000d470`
- `0x1800105c8`
- `0x180010c90`
- `0x18001132c`
- `0x1800113e4`
- `0x180014c20`
- `0x1800173c0`
- `0x180025f64`

## string_xrefs

- `0x180014c6f`: `onecore\base\ci\management\dll\manageci.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall CodeIntegrity::Management::ParsePolicy(_QWORD *a1)
{
  __int64 v2; // rax
  unsigned int v3; // r8d
  __int64 v4; // r10
  int v5; // eax
  void *v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int v10; // r8d
  const char *v11; // r9
  int v12; // [rsp+20h] [rbp-48h]
  void *v13[2]; // [rsp+38h] [rbp-30h] BYREF
  _BYTE v14[32]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  void *v16; // [rsp+88h] [rbp+20h] BYREF

  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&v16);
  v2 = wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
         v14,
         &v16)
     + 8;
  try
  {
    v5 = SIPolicyParsePolicyFormat(0, 0, v4, v3, v2);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x2F8,
        (int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
        (const char *)(unsigned int)v5,
        v12);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(v14);
    v13[0] = v16;
    v6 = operator new(0xB0u);
    v13[1] = v6;
  }
  catch ( std::exception )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x2FD, v7, v8);
    wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0x2FE, v10, v11);
  }
  *a1 = CodeIntegrity::Management::SiPolicyView::SiPolicyView((CodeIntegrity::Management::SiPolicyView *)v6, v13);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&v16);
  return a1;
}

```

## disassembly

```asm
0x180014c20  mov     rax, rsp
0x180014c23  push    rbx
0x180014c24  sub     rsp, 60h
0x180014c28  mov     r10, rdx
0x180014c2b  mov     rbx, rcx
0x180014c2e  lea     rcx, [rax+20h]
0x180014c32  call    ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyUninitialize@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x180014c37  nop
0x180014c38  lea     rdx, [rsp+68h+arg_18]
0x180014c40  lea     rcx, [rsp+68h+var_20]
0x180014c45  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyUninitialize@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyUninitialize@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyUninitialize@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x180014c4a  nop
0x180014c4b  add     rax, 8
0x180014c4f  mov     r9d, r8d
0x180014c52  mov     qword ptr [rsp+68h+var_48], rax; int
0x180014c57  mov     r8, r10
0x180014c5a  xor     edx, edx
0x180014c5c  xor     ecx, ecx
0x180014c5e  call    SIPolicyParsePolicyFormat
0x180014c63  mov     rcx, [rsp+68h]; this
0x180014c68  test    eax, eax
0x180014c6a  jns     short loc_180014C81
0x180014c6c  mov     r9d, eax; char *
0x180014c6f  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x180014c76  mov     edx, 2F8h; void *
0x180014c7b  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180014c81  lea     rcx, [rsp+68h+var_20]
0x180014c86  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyUninitialize@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180014c8b  mov     rax, [rsp+68h+arg_18]
0x180014c93  mov     [rsp+68h+var_30], rax
0x180014c98  mov     ecx, 0B0h; Size
0x180014c9d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014ca2  mov     [rsp+68h+var_28], rax
0x180014ca7  lea     rdx, [rsp+68h+var_30]; void **
0x180014cac  mov     rcx, rax; this
0x180014caf  call    ??0SiPolicyView@Management@CodeIntegrity@@QEAA@AEBQEAX@Z; CodeIntegrity::Management::SiPolicyView::SiPolicyView(void * const &)
0x180014cb4  nop
0x180014cb5  mov     [rbx], rax
0x180014cb8  lea     rcx, [rsp+68h+arg_18]
0x180014cc0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyUninitialize@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x180014cc5  mov     rax, rbx
0x180014cc8  add     rsp, 60h
0x180014ccc  pop     rbx
0x180014ccd  retn
```
