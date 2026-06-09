# winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNamedNodeMap<winrt::Windows::Data::Xml::Dom::IXmlNamedNodeMap>::GetNamedItem(winrt::param::hstring const &)

- ea: `0x18000ca54`
- end: `0x18000cab1`
- name: `?GetNamedItem@?$consume_Windows_Data_Xml_Dom_IXmlNamedNodeMap@UIXmlNamedNodeMap@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
- size: `93`
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
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNamedNodeMap<winrt::Windows::Data::Xml::Dom::IXmlNamedNodeMap>::GetNamedItem(
        __int64 **a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 *v3; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  int v7; // eax
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
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v5 + 64))(v3, v6, &v11);
  winrt::check_hresult((int *)&v12, v7, (__int64)&v9);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x18000ca54  mov     [rsp+arg_8], rdx
0x18000ca59  push    rbx
0x18000ca5a  sub     rsp, 40h
0x18000ca5e  mov     rcx, [rcx]
0x18000ca61  xor     eax, eax
0x18000ca63  mov     [rsp+48h+arg_0], rax
0x18000ca68  mov     r9, r8
0x18000ca6b  mov     [rsp+48h+var_20], eax
0x18000ca6f  lea     r8, [rsp+48h+arg_0]
0x18000ca74  mov     rbx, rdx
0x18000ca77  xorps   xmm0, xmm0
0x18000ca7a  mov     rax, [rcx]
0x18000ca7d  mov     rdx, [r9]
0x18000ca80  movdqu  [rsp+48h+var_18], xmm0
0x18000ca86  mov     rax, [rax+40h]
0x18000ca8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca8f  lea     r8, [rsp+48h+var_20]
0x18000ca94  mov     edx, eax
0x18000ca96  lea     rcx, [rsp+48h+arg_8]
0x18000ca9b  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000caa0  mov     rax, [rsp+48h+arg_0]
0x18000caa5  mov     [rbx], rax
0x18000caa8  mov     rax, rbx
0x18000caab  add     rsp, 40h
0x18000caaf  pop     rbx
0x18000cab0  retn
```
