# winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Data::Xml::Dom::IXmlNodeList,winrt::Windows::Data::Xml::Dom::IXmlNode>::GetAt(uint)

- ea: `0x18000c120`
- end: `0x18000c1e8`
- name: `?GetAt@?$consume_Windows_Foundation_Collections_IVectorView@UIXmlNodeList@Dom@Xml@Data@Windows@winrt@@UIXmlNode@23456@@impl@winrt@@QEBA@I@Z`
- size: `200`
- prototype: `winrt *__fastcall(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *), winrt *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000d424`

## callees

- `0x18000a360`
- `0x18000c120`
- `0x18000f38c`
- `0x18000fb18`
- `0x180018010`

## pseudocode

```c
winrt *__fastcall winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Data::Xml::Dom::IXmlNodeList,winrt::Windows::Data::Xml::Dom::IXmlNode>::GetAt(
        __int64 (__fastcall ****a1)(_QWORD, __int64 *, __int64 *),
        winrt *a2,
        unsigned int a3)
{
  __int64 (__fastcall ***v5)(_QWORD, __int64 *, __int64 *); // rcx
  int v6; // eax
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, _QWORD, void **); // rbx
  struct IUnknown *v9; // rdx
  void **v10; // rax
  int v11; // eax
  int v13; // [rsp+28h] [rbp-18h] BYREF
  __int128 v14; // [rsp+30h] [rbp-10h]
  __int64 v15; // [rsp+70h] [rbp+30h] BYREF
  winrt *v16; // [rsp+78h] [rbp+38h]
  __int64 v17; // [rsp+88h] [rbp+48h] BYREF

  v16 = a2;
  *(_QWORD *)a2 = 0;
  v5 = *a1;
  if ( v5 )
  {
    v15 = 0;
    v6 = (**v5)(
           v5,
           winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Data::Xml::Dom::IXmlNode>>,
           &v15);
    v7 = v15;
    v17 = v15;
  }
  else
  {
    v6 = 0;
    v17 = 0;
    v7 = 0;
  }
  v13 = 0;
  v14 = 0;
  winrt::check_hresult((int *)&v15, v6, (__int64)&v13);
  v13 = 0;
  v14 = 0;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v7 + 48LL);
  v10 = winrt::put_abi(a2, v9);
  v11 = v8(v7, a3, v10);
  winrt::check_hresult((int *)&v15, v11, (__int64)&v13);
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v17);
  return a2;
}

```

## disassembly

```asm
0x18000c120  mov     [rsp-28h+arg_8], rdx
0x18000c125  push    rbp
0x18000c126  push    rbx
0x18000c127  push    rsi
0x18000c128  push    rdi
0x18000c129  push    r14
0x18000c12b  mov     rbp, rsp
0x18000c12e  sub     rsp, 40h
0x18000c132  mov     r14d, r8d
0x18000c135  mov     rdi, rdx
0x18000c138  xor     ebx, ebx
0x18000c13a  mov     [rbp+var_20], ebx
0x18000c13d  mov     [rdx], rbx
0x18000c140  mov     [rbp+var_20], 1
0x18000c147  mov     rcx, [rcx]
0x18000c14a  test    rcx, rcx
0x18000c14d  jnz     short loc_18000C159
0x18000c14f  mov     eax, ebx
0x18000c151  mov     [rbp+arg_18], rbx
0x18000c155  mov     esi, ebx
0x18000c157  jmp     short loc_18000C17B
0x18000c159  mov     [rbp+arg_0], rbx
0x18000c15d  mov     rax, [rcx]
0x18000c160  lea     r8, [rbp+arg_0]
0x18000c164  lea     rdx, ??$guid_v@U?$IVectorView@UIXmlNode@Dom@Xml@Data@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Data::Xml::Dom::IXmlNode>>
0x18000c16b  mov     rax, [rax]
0x18000c16e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c173  mov     rsi, [rbp+arg_0]
0x18000c177  mov     [rbp+arg_18], rsi
0x18000c17b  mov     [rbp+var_18], ebx
0x18000c17e  xorps   xmm0, xmm0
0x18000c181  movdqu  [rbp+var_10], xmm0
0x18000c186  lea     r8, [rbp+var_18]
0x18000c18a  mov     edx, eax
0x18000c18c  lea     rcx, [rbp+arg_0]
0x18000c190  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000c195  mov     [rbp+var_18], ebx
0x18000c198  xorps   xmm0, xmm0
0x18000c19b  movdqu  [rbp+var_10], xmm0
0x18000c1a0  mov     rax, [rsi]
0x18000c1a3  mov     rbx, [rax+30h]
0x18000c1a7  mov     rcx, rdi; this
0x18000c1aa  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18000c1af  mov     r8, rax
0x18000c1b2  mov     edx, r14d
0x18000c1b5  mov     rcx, rsi
0x18000c1b8  mov     rax, rbx
0x18000c1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1c0  lea     r8, [rbp+var_18]
0x18000c1c4  mov     edx, eax
0x18000c1c6  lea     rcx, [rbp+arg_0]
0x18000c1ca  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000c1cf  nop
0x18000c1d0  lea     rcx, [rbp+arg_18]; this
0x18000c1d4  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000c1d9  mov     rax, rdi
0x18000c1dc  add     rsp, 40h
0x18000c1e0  pop     r14
0x18000c1e2  pop     rdi
0x18000c1e3  pop     rsi
0x18000c1e4  pop     rbx
0x18000c1e5  pop     rbp
0x18000c1e6  retn
```
