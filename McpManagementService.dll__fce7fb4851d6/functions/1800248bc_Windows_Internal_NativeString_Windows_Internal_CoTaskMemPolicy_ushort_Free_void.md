# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x1800248bc`
- end: `0x1800248f0`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024370`
- `0x1800244d0`
- `0x1800245e0`
- `0x1800248f8`
- `0x180025ba0`
- `0x180025d00`
- `0x180025e60`
- `0x180026070`
- `0x1800261d0`
- `0x180026330`

## callees

- `0x1800248bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248cd`

## pseudocode

```c
void __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x1800248bc  push    rbx
0x1800248be  sub     rsp, 20h
0x1800248c2  mov     rbx, rcx
0x1800248c5  mov     rcx, [rcx]; pv
0x1800248c8  test    rcx, rcx
0x1800248cb  jz      short loc_1800248DA
0x1800248cd  call    cs:__imp_CoTaskMemFree
0x1800248d3  mov     qword ptr [rbx], 0
0x1800248da  mov     qword ptr [rbx+8], 0
0x1800248e2  mov     qword ptr [rbx+10h], 0
0x1800248ea  add     rsp, 20h
0x1800248ee  pop     rbx
0x1800248ef  retn
```
