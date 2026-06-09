# winrt::impl::consume_Windows_Data_Xml_Dom_IXmlElement<winrt::Windows::Data::Xml::Dom::IXmlElement>::SetAttribute(winrt::param::hstring const &,winrt::param::hstring const &)

- ea: `0x18000e8e4`
- end: `0x18000e924`
- name: `?SetAttribute@?$consume_Windows_Data_Xml_Dom_IXmlElement@UIXmlElement@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z`
- size: `64`
- prototype: `int *__fastcall(__int64 **, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d424`

## callees

- `0x18000f38c`
- `0x180018010`

## pseudocode

```c
int *__fastcall winrt::impl::consume_Windows_Data_Xml_Dom_IXmlElement<winrt::Windows::Data::Xml::Dom::IXmlElement>::SetAttribute(
        __int64 **a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 *v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rax
  int v7; // eax
  int v9; // [rsp+20h] [rbp-28h] BYREF
  __int128 v10; // [rsp+28h] [rbp-20h]
  int v11; // [rsp+50h] [rbp+8h] BYREF

  v3 = *a1;
  v4 = *a3;
  v5 = *a2;
  v9 = 0;
  v6 = *v3;
  v10 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(v6 + 64))(v3, v5, v4);
  return winrt::check_hresult(&v11, v7, (__int64)&v9);
}

```

## disassembly

```asm
0x18000e8e4  sub     rsp, 48h
0x18000e8e8  mov     rcx, [rcx]
0x18000e8eb  xorps   xmm0, xmm0
0x18000e8ee  mov     r8, [r8]
0x18000e8f1  mov     rdx, [rdx]
0x18000e8f4  mov     [rsp+48h+var_28], 0
0x18000e8fc  mov     rax, [rcx]
0x18000e8ff  movdqu  [rsp+48h+var_20], xmm0
0x18000e905  mov     rax, [rax+40h]
0x18000e909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e90e  lea     r8, [rsp+48h+var_28]
0x18000e913  mov     edx, eax
0x18000e915  lea     rcx, [rsp+48h+arg_0]
0x18000e91a  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000e91f  add     rsp, 48h
0x18000e923  retn
```
