# winrt::impl::consume_Windows_Data_Json_IJsonArray<winrt::Windows::Data::Json::IJsonArray>::GetObjectAt(uint)

- ea: `0x180008364`
- end: `0x1800083c3`
- name: `?GetObjectAt@?$consume_Windows_Data_Json_IJsonArray@UIJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@I@Z`
- size: `95`
- prototype: `_QWORD *__fastcall(__int64 **, _QWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006920`

## callees

- `0x180008364`
- `0x18000bde4`
- `0x18000d010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonArray<winrt::Windows::Data::Json::IJsonArray>::GetObjectAt(
        __int64 **a1,
        _QWORD *a2,
        unsigned int a3)
{
  __int64 *v3; // rcx
  __int64 v5; // rax
  int v6; // eax
  int v8; // [rsp+28h] [rbp-20h] BYREF
  __int128 v9; // [rsp+30h] [rbp-18h]
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  v3 = *a1;
  v10 = 0;
  v8 = 0;
  v5 = *v3;
  v9 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v5 + 48))(v3, a3, &v10);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v8);
  *a2 = v10;
  return a2;
}

```

## disassembly

```asm
0x180008364  push    rbx
0x180008366  sub     rsp, 40h
0x18000836a  mov     rcx, [rcx]
0x18000836d  mov     r9d, r8d
0x180008370  mov     [rsp+48h+arg_0], 0
0x180008379  lea     r8, [rsp+48h+arg_0]
0x18000837e  mov     rbx, rdx
0x180008381  mov     [rsp+48h+var_20], 0
0x180008389  xorps   xmm0, xmm0
0x18000838c  mov     edx, r9d
0x18000838f  mov     rax, [rcx]
0x180008392  movdqu  [rsp+48h+var_18], xmm0
0x180008398  mov     rax, [rax+30h]
0x18000839c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083a1  test    eax, eax
0x1800083a3  js      short loc_1800083B6
0x1800083a5  mov     rax, [rsp+48h+arg_0]
0x1800083aa  mov     [rbx], rax
0x1800083ad  mov     rax, rbx
0x1800083b0  add     rsp, 40h
0x1800083b4  pop     rbx
0x1800083b5  retn
0x1800083b6  lea     rdx, [rsp+48h+var_20]
0x1800083bb  mov     ecx, eax
0x1800083bd  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
