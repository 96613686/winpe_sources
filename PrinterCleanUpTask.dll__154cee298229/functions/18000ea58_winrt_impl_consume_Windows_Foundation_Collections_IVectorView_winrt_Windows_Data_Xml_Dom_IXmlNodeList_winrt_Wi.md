# winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Data::Xml::Dom::IXmlNodeList,winrt::Windows::Data::Xml::Dom::IXmlNode>::Size(void)

- ea: `0x18000ea58`
- end: `0x18000eb0b`
- name: `?Size@?$consume_Windows_Foundation_Collections_IVectorView@UIXmlNodeList@Dom@Xml@Data@Windows@winrt@@UIXmlNode@23456@@impl@winrt@@QEBA@XZ`
- size: `179`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *))`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d424`

## callees

- `0x18000a360`
- `0x18000ea58`
- `0x18000f38c`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Data::Xml::Dom::IXmlNodeList,winrt::Windows::Data::Xml::Dom::IXmlNode>::Size(
        __int64 (__fastcall ****a1)(_QWORD, __int64 *, __int64 *))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64 *, __int64 *); // rcx
  int v2; // eax
  __int64 v3; // rbx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-20h] BYREF
  __int128 v7; // [rsp+28h] [rbp-18h]
  unsigned int v8; // [rsp+50h] [rbp+10h] BYREF
  __int64 v9; // [rsp+58h] [rbp+18h] BYREF
  __int64 v10; // [rsp+60h] [rbp+20h] BYREF

  v8 = 0;
  v1 = *a1;
  if ( v1 )
  {
    v9 = 0;
    v2 = (**v1)(
           v1,
           winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Data::Xml::Dom::IXmlNode>>,
           &v9);
    v3 = v9;
    v10 = v9;
  }
  else
  {
    v2 = 0;
    v10 = 0;
    v3 = 0;
  }
  v6 = 0;
  v7 = 0;
  winrt::check_hresult((int *)&v9, v2, (__int64)&v6);
  v6 = 0;
  v7 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v3 + 56LL))(v3, &v8);
  winrt::check_hresult((int *)&v9, v4, (__int64)&v6);
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v10);
  return v8;
}

```

## disassembly

```asm
0x18000ea58  mov     [rsp-8+arg_18], rbx
0x18000ea5d  push    rbp
0x18000ea5e  mov     rbp, rsp
0x18000ea61  sub     rsp, 40h
0x18000ea65  mov     [rbp+arg_0], 0
0x18000ea6c  mov     rcx, [rcx]
0x18000ea6f  test    rcx, rcx
0x18000ea72  jnz     short loc_18000EA7E
0x18000ea74  xor     eax, eax
0x18000ea76  mov     [rbp+arg_10], rax
0x18000ea7a  xor     ebx, ebx
0x18000ea7c  jmp     short loc_18000EAA4
0x18000ea7e  mov     [rbp+arg_8], 0
0x18000ea86  mov     rax, [rcx]
0x18000ea89  lea     r8, [rbp+arg_8]
0x18000ea8d  lea     rdx, ??$guid_v@U?$IVectorView@UIXmlNode@Dom@Xml@Data@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Data::Xml::Dom::IXmlNode>>
0x18000ea94  mov     rax, [rax]
0x18000ea97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea9c  mov     rbx, [rbp+arg_8]
0x18000eaa0  mov     [rbp+arg_10], rbx
0x18000eaa4  mov     [rbp+var_20], 0
0x18000eaab  xorps   xmm0, xmm0
0x18000eaae  movdqu  [rbp+var_18], xmm0
0x18000eab3  lea     r8, [rbp+var_20]
0x18000eab7  mov     edx, eax
0x18000eab9  lea     rcx, [rbp+arg_8]
0x18000eabd  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000eac2  mov     [rbp+var_20], 0
0x18000eac9  xorps   xmm0, xmm0
0x18000eacc  movdqu  [rbp+var_18], xmm0
0x18000ead1  mov     rax, [rbx]
0x18000ead4  lea     rdx, [rbp+arg_0]
0x18000ead8  mov     rcx, rbx
0x18000eadb  mov     rax, [rax+38h]
0x18000eadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eae4  lea     r8, [rbp+var_20]
0x18000eae8  mov     edx, eax
0x18000eaea  lea     rcx, [rbp+arg_8]
0x18000eaee  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000eaf3  nop
0x18000eaf4  lea     rcx, [rbp+arg_10]; this
0x18000eaf8  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000eafd  mov     eax, [rbp+arg_0]
0x18000eb00  mov     rbx, [rsp+40h+arg_18]
0x18000eb05  add     rsp, 40h
0x18000eb09  pop     rbp
0x18000eb0a  retn
```
