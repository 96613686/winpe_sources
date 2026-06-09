# winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Data::Xml::Dom::XmlDocument>(void)

- ea: `0x180007708`
- end: `0x1800077bb`
- name: `??$ActivateInstance@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUXmlDocument@Dom@Xml@Data@23@XZ`
- size: `179`
- prototype: `struct IUnknown *__fastcall(__int64 *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800075a0`
- `0x180009c84`

## callees

- `0x18000750c`
- `0x180007708`
- `0x18000f38c`
- `0x18000fb18`
- `0x180018010`

## pseudocode

```c
struct IUnknown *__fastcall winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Data::Xml::Dom::XmlDocument>(
        __int64 *a1,
        struct IUnknown *a2)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, void **); // rbx
  void **v5; // rax
  unsigned int v6; // eax
  void (__fastcall ***v7)(_QWORD, __int64 *, _QWORD *); // rcx
  int v9; // [rsp+28h] [rbp-18h] BYREF
  __int128 v10; // [rsp+30h] [rbp-10h]
  void (__fastcall ***v11)(_QWORD, __int64 *, struct IUnknown **); // [rsp+60h] [rbp+20h] BYREF
  struct IUnknown *v12; // [rsp+68h] [rbp+28h] BYREF

  v12 = a2;
  v11 = 0;
  v9 = 0;
  v10 = 0;
  v3 = *a1;
  v4 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)*a1 + 48LL);
  v5 = winrt::put_abi((winrt *)&v11, a2);
  v6 = v4(v3, v5);
  winrt::check_hresult(&v12, v6, &v9);
  v7 = (void (__fastcall ***)(_QWORD, __int64 *, _QWORD *))v11;
  if ( v11 )
  {
    v12 = 0;
    (**v11)(v11, winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlDocument>, &v12);
    a2->lpVtbl = (struct IUnknownVtbl *)v12;
    v7 = (void (__fastcall ***)(_QWORD, __int64 *, _QWORD *))v11;
  }
  else
  {
    a2->lpVtbl = 0;
  }
  if ( v7 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  return a2;
}

```

## disassembly

```asm
0x180007708  mov     [rsp-18h+arg_10], rbx
0x18000770d  mov     [rsp-18h+arg_8], rdx
0x180007712  push    rbp
0x180007713  push    rsi
0x180007714  push    rdi
0x180007715  mov     rbp, rsp
0x180007718  sub     rsp, 40h
0x18000771c  mov     rsi, rdx
0x18000771f  mov     [rbp+arg_0], 0
0x180007727  mov     [rbp+var_18], 0
0x18000772e  xorps   xmm0, xmm0
0x180007731  movdqu  [rbp+var_10], xmm0
0x180007736  mov     rdi, [rcx]
0x180007739  mov     rax, [rdi]
0x18000773c  mov     rbx, [rax+30h]
0x180007740  lea     rcx, [rbp+arg_0]; this
0x180007744  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x180007749  mov     rdx, rax
0x18000774c  mov     rcx, rdi
0x18000774f  mov     rax, rbx
0x180007752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007757  lea     r8, [rbp+var_18]
0x18000775b  mov     edx, eax
0x18000775d  lea     rcx, [rbp+arg_8]
0x180007761  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180007766  mov     rcx, [rbp+arg_0]
0x18000776a  test    rcx, rcx
0x18000776d  jnz     short loc_180007774
0x18000776f  mov     [rsi], rcx
0x180007772  jmp     short loc_18000779D
0x180007774  mov     [rbp+arg_8], 0
0x18000777c  mov     rax, [rcx]
0x18000777f  lea     r8, [rbp+arg_8]
0x180007783  lea     rdx, ??$guid_v@UIXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlDocument>
0x18000778a  mov     rax, [rax]
0x18000778d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007792  mov     rax, [rbp+arg_8]
0x180007796  mov     [rsi], rax
0x180007799  mov     rcx, [rbp+arg_0]
0x18000779d  test    rcx, rcx
0x1800077a0  jz      short loc_1800077AB
0x1800077a2  lea     rcx, [rbp+arg_0]
0x1800077a6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800077ab  mov     rax, rsi
0x1800077ae  mov     rbx, [rsp+40h+arg_10]
0x1800077b3  add     rsp, 40h
0x1800077b7  pop     rdi
0x1800077b8  pop     rsi
0x1800077b9  pop     rbp
0x1800077ba  retn
```
