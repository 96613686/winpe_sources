# winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNode<winrt::Windows::Data::Xml::Dom::IXmlNode>::AppendChild(winrt::Windows::Data::Xml::Dom::IXmlNode const &)

- ea: `0x18000b0b4`
- end: `0x18000b114`
- name: `?AppendChild@?$consume_Windows_Data_Xml_Dom_IXmlNode@UIXmlNode@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUIXmlNode@Dom@Xml@Data@Windows@3@@Z`
- size: `96`
- prototype: `_QWORD *__fastcall(__int64 **, _QWORD *, __int64 *)`
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
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNode<winrt::Windows::Data::Xml::Dom::IXmlNode>::AppendChild(
        __int64 **a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 *v3; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  unsigned int v7; // eax
  int v9; // [rsp+28h] [rbp-20h] BYREF
  __int128 v10; // [rsp+30h] [rbp-18h]
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF
  _QWORD *v12; // [rsp+58h] [rbp+10h] BYREF

  v12 = a2;
  v3 = *a1;
  v11 = 0;
  v9 = 0;
  v5 = *v3;
  v6 = *a3;
  v10 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v5 + 176))(v3, v6, &v11);
  winrt::check_hresult(&v12, v7, &v9);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x18000b0b4  mov     [rsp+arg_8], rdx
0x18000b0b9  push    rbx
0x18000b0ba  sub     rsp, 40h
0x18000b0be  mov     rcx, [rcx]
0x18000b0c1  xor     eax, eax
0x18000b0c3  mov     [rsp+48h+arg_0], rax
0x18000b0c8  mov     r9, r8
0x18000b0cb  mov     [rsp+48h+var_20], eax
0x18000b0cf  lea     r8, [rsp+48h+arg_0]
0x18000b0d4  mov     rbx, rdx
0x18000b0d7  xorps   xmm0, xmm0
0x18000b0da  mov     rax, [rcx]
0x18000b0dd  mov     rdx, [r9]
0x18000b0e0  movdqu  [rsp+48h+var_18], xmm0
0x18000b0e6  mov     rax, [rax+0B0h]
0x18000b0ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0f2  lea     r8, [rsp+48h+var_20]
0x18000b0f7  mov     edx, eax
0x18000b0f9  lea     rcx, [rsp+48h+arg_8]
0x18000b0fe  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000b103  mov     rax, [rsp+48h+arg_0]
0x18000b108  mov     [rbx], rax
0x18000b10b  mov     rax, rbx
0x18000b10e  add     rsp, 40h
0x18000b112  pop     rbx
0x18000b113  retn
```
