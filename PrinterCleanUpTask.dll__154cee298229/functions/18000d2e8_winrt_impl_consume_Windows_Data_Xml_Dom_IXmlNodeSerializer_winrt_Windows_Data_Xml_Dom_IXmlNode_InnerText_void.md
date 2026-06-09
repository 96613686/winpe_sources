# winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNodeSerializer<winrt::Windows::Data::Xml::Dom::IXmlNode>::InnerText(void)

- ea: `0x18000d2e8`
- end: `0x18000d3a5`
- name: `?InnerText@?$consume_Windows_Data_Xml_Dom_IXmlNodeSerializer@UIXmlNode@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `189`
- prototype: `_QWORD *__fastcall(__int64 (__fastcall ****)(_QWORD, __int64 *, _QWORD **), _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d424`

## callees

- `0x18000a360`
- `0x18000d2e8`
- `0x18000f38c`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNodeSerializer<winrt::Windows::Data::Xml::Dom::IXmlNode>::InnerText(
        __int64 (__fastcall ****a1)(_QWORD, __int64 *, _QWORD **),
        _QWORD *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, __int64 *, _QWORD **); // rcx
  int v4; // eax
  _QWORD *v5; // rbx
  int v6; // eax
  int v8; // [rsp+28h] [rbp-18h] BYREF
  __int128 v9; // [rsp+30h] [rbp-10h]
  _QWORD *v10; // [rsp+60h] [rbp+20h] BYREF
  _QWORD *v11; // [rsp+68h] [rbp+28h] BYREF
  __int64 v12; // [rsp+70h] [rbp+30h] BYREF

  v11 = a2;
  v12 = 0;
  v3 = *a1;
  if ( v3 )
  {
    v11 = 0;
    v4 = (**v3)(v3, winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlNodeSerializer>, &v11);
    v5 = v11;
    v10 = v11;
  }
  else
  {
    v4 = 0;
    v10 = 0;
    v5 = 0;
  }
  v8 = 0;
  v9 = 0;
  winrt::check_hresult((int *)&v11, v4, (__int64)&v8);
  v8 = 0;
  v9 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v5 + 56LL))(v5, &v12);
  winrt::check_hresult((int *)&v11, v6, (__int64)&v8);
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v10);
  *a2 = v12;
  return a2;
}

```

## disassembly

```asm
0x18000d2e8  mov     [rsp-18h+arg_8], rdx
0x18000d2ed  push    rbp
0x18000d2ee  push    rbx
0x18000d2ef  push    rdi
0x18000d2f0  mov     rbp, rsp
0x18000d2f3  sub     rsp, 40h
0x18000d2f7  mov     rdi, rdx
0x18000d2fa  mov     [rbp+arg_10], 0
0x18000d302  mov     rcx, [rcx]
0x18000d305  test    rcx, rcx
0x18000d308  jnz     short loc_18000D314
0x18000d30a  xor     eax, eax
0x18000d30c  mov     [rbp+arg_0], rax
0x18000d310  xor     ebx, ebx
0x18000d312  jmp     short loc_18000D33A
0x18000d314  mov     [rbp+arg_8], 0
0x18000d31c  mov     rax, [rcx]
0x18000d31f  lea     r8, [rbp+arg_8]
0x18000d323  lea     rdx, ??$guid_v@UIXmlNodeSerializer@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlNodeSerializer>
0x18000d32a  mov     rax, [rax]
0x18000d32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d332  mov     rbx, [rbp+arg_8]
0x18000d336  mov     [rbp+arg_0], rbx
0x18000d33a  mov     [rbp+var_18], 0
0x18000d341  xorps   xmm0, xmm0
0x18000d344  movdqu  [rbp+var_10], xmm0
0x18000d349  lea     r8, [rbp+var_18]
0x18000d34d  mov     edx, eax
0x18000d34f  lea     rcx, [rbp+arg_8]
0x18000d353  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000d358  mov     [rbp+var_18], 0
0x18000d35f  xorps   xmm0, xmm0
0x18000d362  movdqu  [rbp+var_10], xmm0
0x18000d367  mov     rax, [rbx]
0x18000d36a  lea     rdx, [rbp+arg_10]
0x18000d36e  mov     rcx, rbx
0x18000d371  mov     rax, [rax+38h]
0x18000d375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d37a  lea     r8, [rbp+var_18]
0x18000d37e  mov     edx, eax
0x18000d380  lea     rcx, [rbp+arg_8]
0x18000d384  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000d389  nop
0x18000d38a  lea     rcx, [rbp+arg_0]; this
0x18000d38e  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d393  mov     rax, [rbp+arg_10]
0x18000d397  mov     [rdi], rax
0x18000d39a  mov     rax, rdi
0x18000d39d  add     rsp, 40h
0x18000d3a1  pop     rdi
0x18000d3a2  pop     rbx
0x18000d3a3  pop     rbp
0x18000d3a4  retn
```
