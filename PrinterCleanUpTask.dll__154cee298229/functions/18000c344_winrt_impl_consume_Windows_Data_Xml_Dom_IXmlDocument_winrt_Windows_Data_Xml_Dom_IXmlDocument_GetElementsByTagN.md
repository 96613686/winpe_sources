# winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocument<winrt::Windows::Data::Xml::Dom::IXmlDocument>::GetElementsByTagName(winrt::param::hstring const &)

- ea: `0x18000c344`
- end: `0x18000c3a4`
- name: `?GetElementsByTagName@?$consume_Windows_Data_Xml_Dom_IXmlDocument@UIXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
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
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocument<winrt::Windows::Data::Xml::Dom::IXmlDocument>::GetElementsByTagName(
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
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v5 + 128))(v3, v6, &v11);
  winrt::check_hresult((int *)&v12, v7, (__int64)&v9);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x18000c344  mov     [rsp+arg_8], rdx
0x18000c349  push    rbx
0x18000c34a  sub     rsp, 40h
0x18000c34e  mov     rcx, [rcx]
0x18000c351  xor     eax, eax
0x18000c353  mov     [rsp+48h+arg_0], rax
0x18000c358  mov     r9, r8
0x18000c35b  mov     [rsp+48h+var_20], eax
0x18000c35f  lea     r8, [rsp+48h+arg_0]
0x18000c364  mov     rbx, rdx
0x18000c367  xorps   xmm0, xmm0
0x18000c36a  mov     rax, [rcx]
0x18000c36d  mov     rdx, [r9]
0x18000c370  movdqu  [rsp+48h+var_18], xmm0
0x18000c376  mov     rax, [rax+80h]
0x18000c37d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c382  lea     r8, [rsp+48h+var_20]
0x18000c387  mov     edx, eax
0x18000c389  lea     rcx, [rsp+48h+arg_8]
0x18000c38e  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000c393  mov     rax, [rsp+48h+arg_0]
0x18000c398  mov     [rbx], rax
0x18000c39b  mov     rax, rbx
0x18000c39e  add     rsp, 40h
0x18000c3a2  pop     rbx
0x18000c3a3  retn
```
