# `winrt::Windows::Data::Json::JsonArray::JsonArray(void)'::`1'::_lambda_16__::operator()(winrt::Windows::Foundation::IActivationFactory const &)

- ea: `0x18001c8f4`
- end: `0x18001c9a1`
- name: `??R_lambda_16__@?0???0JsonArray@Json@Data@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@45@@Z`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ba10`
- `0x18001d680`

## callees

- `0x18001a3fc`
- `0x18001a798`
- `0x18001c8f4`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall `winrt::Windows::Data::Json::JsonArray::JsonArray'::`1'::_lambda_16__::operator()(
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
    (**v11)(v11, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonArray>, &v12);
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
0x18001c8f4  mov     [rsp-8+arg_8], rbx
0x18001c8f9  mov     [rsp-8+arg_0], rcx
0x18001c8fe  push    rbp
0x18001c8ff  mov     rbp, rsp
0x18001c902  sub     rsp, 40h
0x18001c906  mov     rbx, rdx
0x18001c909  mov     [rbp+arg_0], 0
0x18001c911  mov     [rbp+var_18], 19CDh
0x18001c918  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001c91f  mov     [rbp+var_10], rax
0x18001c923  mov     [rbp+var_8], 0
0x18001c92b  mov     rcx, [r8]
0x18001c92e  mov     rax, [rcx]
0x18001c931  lea     rdx, [rbp+arg_0]
0x18001c935  mov     rax, [rax+30h]
0x18001c939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c93e  test    eax, eax
0x18001c940  js      short loc_18001C995
0x18001c942  mov     rcx, [rbp+arg_0]
0x18001c946  test    rcx, rcx
0x18001c949  jnz     short loc_18001C950
0x18001c94b  mov     [rbx], rcx
0x18001c94e  jmp     short loc_18001C979
0x18001c950  mov     [rbp+arg_10], 0
0x18001c958  mov     rax, [rcx]
0x18001c95b  lea     r8, [rbp+arg_10]
0x18001c95f  lea     rdx, ??$guid_v@UIJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonArray>
0x18001c966  mov     rax, [rax]
0x18001c969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c96e  mov     rax, [rbp+arg_10]
0x18001c972  mov     [rbx], rax
0x18001c975  mov     rcx, [rbp+arg_0]
0x18001c979  test    rcx, rcx
0x18001c97c  jz      short loc_18001C987
0x18001c97e  lea     rcx, [rbp+arg_0]
0x18001c982  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c987  mov     rax, rbx
0x18001c98a  mov     rbx, [rsp+40h+arg_8]
0x18001c98f  add     rsp, 40h
0x18001c993  pop     rbp
0x18001c994  retn
0x18001c995  lea     rdx, [rbp+var_18]
0x18001c999  mov     ecx, eax
0x18001c99b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
