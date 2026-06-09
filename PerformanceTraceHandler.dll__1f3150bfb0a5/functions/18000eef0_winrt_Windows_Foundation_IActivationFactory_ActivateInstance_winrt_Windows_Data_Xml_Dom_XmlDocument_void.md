# winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Data::Xml::Dom::XmlDocument>(void)

- ea: `0x18000eef0`
- end: `0x18000ef91`
- name: `??$ActivateInstance@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUXmlDocument@Dom@Xml@Data@23@XZ`
- size: `161`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ee80`
- `0x1800106e0`

## callees

- `0x180009c74`
- `0x18000eef0`
- `0x180012e00`
- `0x18001c010`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Data::Xml::Dom::XmlDocument>(
        _QWORD *a1,
        _QWORD *a2)
{
  unsigned int v3; // eax
  void (__fastcall ***v4)(_QWORD, __int64 *, _QWORD *); // rcx
  int v6; // [rsp+28h] [rbp-18h] BYREF
  __int128 v7; // [rsp+30h] [rbp-10h]
  void (__fastcall ***v8)(_QWORD, __int64 *, _QWORD *); // [rsp+50h] [rbp+10h] BYREF
  _QWORD *v9; // [rsp+58h] [rbp+18h] BYREF

  v9 = a2;
  v8 = 0;
  v6 = 0;
  v7 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, void (__fastcall ****)(_QWORD, __int64 *, _QWORD *)))(*(_QWORD *)*a1 + 48LL))(
         *a1,
         &v8);
  winrt::check_hresult(&v9, v3, &v6);
  v4 = v8;
  if ( v8 )
  {
    v9 = 0;
    (**v8)(v8, winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlDocument>, &v9);
    *a2 = v9;
    v4 = v8;
  }
  else
  {
    *a2 = 0;
  }
  if ( v4 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v8);
  return a2;
}

```

## disassembly

```asm
0x18000eef0  mov     [rsp-8+arg_10], rbx
0x18000eef5  mov     [rsp-8+arg_8], rdx
0x18000eefa  push    rbp
0x18000eefb  mov     rbp, rsp
0x18000eefe  sub     rsp, 40h
0x18000ef02  mov     rbx, rdx
0x18000ef05  mov     [rbp+arg_0], 0
0x18000ef0d  mov     [rbp+var_18], 0
0x18000ef14  xorps   xmm0, xmm0
0x18000ef17  movdqu  [rbp+var_10], xmm0
0x18000ef1c  mov     rcx, [rcx]
0x18000ef1f  mov     rax, [rcx]
0x18000ef22  lea     rdx, [rbp+arg_0]
0x18000ef26  mov     rax, [rax+30h]
0x18000ef2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef2f  lea     r8, [rbp+var_18]
0x18000ef33  mov     edx, eax
0x18000ef35  lea     rcx, [rbp+arg_8]
0x18000ef39  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000ef3e  mov     rcx, [rbp+arg_0]
0x18000ef42  test    rcx, rcx
0x18000ef45  jnz     short loc_18000EF4C
0x18000ef47  mov     [rbx], rcx
0x18000ef4a  jmp     short loc_18000EF75
0x18000ef4c  mov     [rbp+arg_8], 0
0x18000ef54  mov     rax, [rcx]
0x18000ef57  lea     r8, [rbp+arg_8]
0x18000ef5b  lea     rdx, ??$guid_v@UIXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlDocument>
0x18000ef62  mov     rax, [rax]
0x18000ef65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef6a  mov     rax, [rbp+arg_8]
0x18000ef6e  mov     [rbx], rax
0x18000ef71  mov     rcx, [rbp+arg_0]
0x18000ef75  test    rcx, rcx
0x18000ef78  jz      short loc_18000EF83
0x18000ef7a  lea     rcx, [rbp+arg_0]
0x18000ef7e  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18000ef83  mov     rax, rbx
0x18000ef86  mov     rbx, [rsp+40h+arg_10]
0x18000ef8b  add     rsp, 40h
0x18000ef8f  pop     rbp
0x18000ef90  retn
```
