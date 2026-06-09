# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x1800195e8`
- end: `0x18001961c`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014d8c`
- `0x1800155e8`
- `0x180017394`

## callees

- `0x1800195e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800195f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800195f9`

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
0x1800195e8  push    rbx
0x1800195ea  sub     rsp, 20h
0x1800195ee  mov     rbx, rcx
0x1800195f1  mov     rcx, [rcx]; pv
0x1800195f4  test    rcx, rcx
0x1800195f7  jz      short loc_180019606
0x1800195f9  call    cs:__imp_CoTaskMemFree
0x1800195ff  mov     qword ptr [rbx], 0
0x180019606  mov     qword ptr [rbx+8], 0
0x18001960e  mov     qword ptr [rbx+10h], 0
0x180019616  add     rsp, 20h
0x18001961a  pop     rbx
0x18001961b  retn
```
