# winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNode<winrt::Windows::Data::Xml::Dom::IXmlNode>::Attributes(void)

- ea: `0x18000b2a8`
- end: `0x18000b302`
- name: `?Attributes@?$consume_Windows_Data_Xml_Dom_IXmlNode@UIXmlNode@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `90`
- prototype: `_QWORD *__fastcall(__int64 **, _QWORD *)`
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
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNode<winrt::Windows::Data::Xml::Dom::IXmlNode>::Attributes(
        __int64 **a1,
        _QWORD *a2)
{
  __int64 *v2; // rcx
  __int64 v4; // rax
  unsigned int v5; // eax
  int v7; // [rsp+28h] [rbp-20h] BYREF
  __int128 v8; // [rsp+30h] [rbp-18h]
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF
  _QWORD *v10; // [rsp+58h] [rbp+10h] BYREF

  v10 = a2;
  v2 = *a1;
  v9 = 0;
  v7 = 0;
  v4 = *v2;
  v8 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v4 + 128))(v2, &v9);
  winrt::check_hresult(&v10, v5, &v7);
  *a2 = v9;
  return a2;
}

```

## disassembly

```asm
0x18000b2a8  mov     [rsp+arg_8], rdx
0x18000b2ad  push    rbx
0x18000b2ae  sub     rsp, 40h
0x18000b2b2  mov     rcx, [rcx]
0x18000b2b5  xor     eax, eax
0x18000b2b7  mov     [rsp+48h+arg_0], rax
0x18000b2bc  mov     rbx, rdx
0x18000b2bf  mov     [rsp+48h+var_20], eax
0x18000b2c3  lea     rdx, [rsp+48h+arg_0]
0x18000b2c8  xorps   xmm0, xmm0
0x18000b2cb  mov     rax, [rcx]
0x18000b2ce  movdqu  [rsp+48h+var_18], xmm0
0x18000b2d4  mov     rax, [rax+80h]
0x18000b2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2e0  lea     r8, [rsp+48h+var_20]
0x18000b2e5  mov     edx, eax
0x18000b2e7  lea     rcx, [rsp+48h+arg_8]
0x18000b2ec  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000b2f1  mov     rax, [rsp+48h+arg_0]
0x18000b2f6  mov     [rbx], rax
0x18000b2f9  mov     rax, rbx
0x18000b2fc  add     rsp, 40h
0x18000b300  pop     rbx
0x18000b301  retn
```
