# `winrt::Windows::Data::Json::JsonObject::JsonObject(void)'::`1'::_lambda_17__::operator()(winrt::Windows::Foundation::IActivationFactory const &)

- ea: `0x18001c9a8`
- end: `0x18001ca55`
- name: `??R_lambda_17__@?0???0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@45@@Z`
- size: `173`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ba40`
- `0x18001d184`
- `0x18001d680`

## callees

- `0x18001a3fc`
- `0x18001a798`
- `0x18001c9a8`
- `0x180021010`

## pseudocode

```c
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
0x18001c9a8  mov     [rsp-8+arg_8], rbx
0x18001c9ad  mov     [rsp-8+arg_0], rcx
0x18001c9b2  push    rbp
0x18001c9b3  mov     rbp, rsp
0x18001c9b6  sub     rsp, 40h
0x18001c9ba  mov     rbx, rdx
0x18001c9bd  mov     [rbp+arg_0], 0
0x18001c9c5  mov     [rbp+var_18], 19CDh
0x18001c9cc  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001c9d3  mov     [rbp+var_10], rax
0x18001c9d7  mov     [rbp+var_8], 0
0x18001c9df  mov     rcx, [r8]
0x18001c9e2  mov     rax, [rcx]
0x18001c9e5  lea     rdx, [rbp+arg_0]
0x18001c9e9  mov     rax, [rax+30h]
0x18001c9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9f2  test    eax, eax
0x18001c9f4  js      short loc_18001CA49
0x18001c9f6  mov     rcx, [rbp+arg_0]
0x18001c9fa  test    rcx, rcx
0x18001c9fd  jnz     short loc_18001CA04
0x18001c9ff  mov     [rbx], rcx
0x18001ca02  jmp     short loc_18001CA2D
0x18001ca04  mov     [rbp+arg_10], 0
0x18001ca0c  mov     rax, [rcx]
0x18001ca0f  lea     r8, [rbp+arg_10]
0x18001ca13  lea     rdx, ??$guid_v@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObject>
0x18001ca1a  mov     rax, [rax]
0x18001ca1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca22  mov     rax, [rbp+arg_10]
0x18001ca26  mov     [rbx], rax
0x18001ca29  mov     rcx, [rbp+arg_0]
0x18001ca2d  test    rcx, rcx
0x18001ca30  jz      short loc_18001CA3B
0x18001ca32  lea     rcx, [rbp+arg_0]
0x18001ca36  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ca3b  mov     rax, rbx
0x18001ca3e  mov     rbx, [rsp+40h+arg_8]
0x18001ca43  add     rsp, 40h
0x18001ca47  pop     rbp
0x18001ca48  retn
0x18001ca49  lea     rdx, [rbp+var_18]
0x18001ca4d  mov     ecx, eax
0x18001ca4f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
