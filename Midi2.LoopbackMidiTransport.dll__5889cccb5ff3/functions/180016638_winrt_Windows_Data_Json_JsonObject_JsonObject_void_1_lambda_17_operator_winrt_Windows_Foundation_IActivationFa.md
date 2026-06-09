# `winrt::Windows::Data::Json::JsonObject::JsonObject(void)'::`1'::_lambda_17__::operator()(winrt::Windows::Foundation::IActivationFactory const &)

- ea: `0x180016638`
- end: `0x1800166e5`
- name: `??R_lambda_17__@?0???0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@45@@Z`
- size: `173`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014be0`
- `0x1800167c4`
- `0x180018090`
- `0x180018710`

## callees

- `0x1800145d8`
- `0x180014974`
- `0x180016638`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall `winrt::Windows::Data::Json::JsonObject::JsonObject'::`1'::_lambda_17__::operator()(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  signed int v4; // eax
  __int64 v5; // r8
  void (__fastcall ***v6)(_QWORD, _QWORD, _QWORD); // rcx
  unsigned int v8; // [rsp+28h] [rbp-18h] BYREF
  const char *v9; // [rsp+30h] [rbp-10h]
  __int64 v10; // [rsp+38h] [rbp-8h]
  void (__fastcall ***v11)(_QWORD, __int64 *, __int64 *); // [rsp+50h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+20h] BYREF

  v11 = 0;
  v8 = 6605;
  v9 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/base.h";
  v10 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, void (__fastcall ****)(_QWORD, __int64 *, __int64 *)))(*(_QWORD *)*a3 + 48LL))(
         *a3,
         &v11);
  if ( v4 < 0 )
    winrt::throw_hresult(v4, &v8, v5);
  v6 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v11;
  if ( v11 )
  {
    v12 = 0;
    (**v11)(v11, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObject>, &v12);
    *a2 = v12;
    v6 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v11;
  }
  else
  {
    *a2 = 0;
  }
  if ( v6 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v11);
  return a2;
}

```

## disassembly

```asm
0x180016638  mov     [rsp-8+arg_8], rbx
0x18001663d  mov     [rsp-8+arg_0], rcx
0x180016642  push    rbp
0x180016643  mov     rbp, rsp
0x180016646  sub     rsp, 40h
0x18001664a  mov     rbx, rdx
0x18001664d  mov     [rbp+arg_0], 0
0x180016655  mov     [rbp+var_18], 19CDh
0x18001665c  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180016663  mov     [rbp+var_10], rax
0x180016667  mov     [rbp+var_8], 0
0x18001666f  mov     rcx, [r8]
0x180016672  mov     rax, [rcx]
0x180016675  lea     rdx, [rbp+arg_0]
0x180016679  mov     rax, [rax+30h]
0x18001667d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016682  test    eax, eax
0x180016684  js      short loc_1800166D9
0x180016686  mov     rcx, [rbp+arg_0]
0x18001668a  test    rcx, rcx
0x18001668d  jnz     short loc_180016694
0x18001668f  mov     [rbx], rcx
0x180016692  jmp     short loc_1800166BD
0x180016694  mov     [rbp+arg_10], 0
0x18001669c  mov     rax, [rcx]
0x18001669f  lea     r8, [rbp+arg_10]
0x1800166a3  lea     rdx, ??$guid_v@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObject>
0x1800166aa  mov     rax, [rax]
0x1800166ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166b2  mov     rax, [rbp+arg_10]
0x1800166b6  mov     [rbx], rax
0x1800166b9  mov     rcx, [rbp+arg_0]
0x1800166bd  test    rcx, rcx
0x1800166c0  jz      short loc_1800166CB
0x1800166c2  lea     rcx, [rbp+arg_0]
0x1800166c6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800166cb  mov     rax, rbx
0x1800166ce  mov     rbx, [rsp+40h+arg_8]
0x1800166d3  add     rsp, 40h
0x1800166d7  pop     rbp
0x1800166d8  retn
0x1800166d9  lea     rdx, [rbp+var_18]
0x1800166dd  mov     ecx, eax
0x1800166df  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
