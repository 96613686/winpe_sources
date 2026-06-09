# winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(winrt::param::hstring const &)

- ea: `0x1800082fc`
- end: `0x18000835b`
- name: `?GetNamedArray@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
- size: `95`
- prototype: `_QWORD *__fastcall(__int64 **, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006920`

## callees

- `0x1800082fc`
- `0x18000bde4`
- `0x18000d010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
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

  v3 = *a1;
  v11 = 0;
  v9 = 0;
  v5 = *v3;
  v6 = *a3;
  v10 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v5 + 72))(v3, v6, &v11);
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v9);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x1800082fc  push    rbx
0x1800082fe  sub     rsp, 40h
0x180008302  mov     rcx, [rcx]
0x180008305  mov     r9, r8
0x180008308  mov     [rsp+48h+arg_0], 0
0x180008311  lea     r8, [rsp+48h+arg_0]
0x180008316  mov     rbx, rdx
0x180008319  mov     [rsp+48h+var_20], 0
0x180008321  xorps   xmm0, xmm0
0x180008324  mov     rax, [rcx]
0x180008327  mov     rdx, [r9]
0x18000832a  movdqu  [rsp+48h+var_18], xmm0
0x180008330  mov     rax, [rax+48h]
0x180008334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008339  test    eax, eax
0x18000833b  js      short loc_18000834E
0x18000833d  mov     rax, [rsp+48h+arg_0]
0x180008342  mov     [rbx], rax
0x180008345  mov     rax, rbx
0x180008348  add     rsp, 40h
0x18000834c  pop     rbx
0x18000834d  retn
0x18000834e  lea     rdx, [rsp+48h+var_20]
0x180008353  mov     ecx, eax
0x180008355  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
