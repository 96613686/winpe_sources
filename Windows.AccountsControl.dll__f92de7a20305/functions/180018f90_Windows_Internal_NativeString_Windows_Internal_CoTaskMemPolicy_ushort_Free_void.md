# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x180018f90`
- end: `0x180018fc4`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000bee0`
- `0x1800137b0`
- `0x18001d868`
- `0x18002a400`
- `0x18002aa70`
- `0x180030004`
- `0x1800301d4`
- `0x1800303c8`
- `0x180032188`
- `0x180032b70`
- `0x18003319c`
- `0x180033270`
- `0x18003987c`
- `0x180040384`
- `0x180043ee4`
- `0x180064630`
- `0x180065d64`
- `0x1800661ec`
- `0x18006665c`

## callees

- `0x180018f90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018fa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018fa1`

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
0x180018f90  push    rbx
0x180018f92  sub     rsp, 20h
0x180018f96  mov     rbx, rcx
0x180018f99  mov     rcx, [rcx]; pv
0x180018f9c  test    rcx, rcx
0x180018f9f  jz      short loc_180018FAE
0x180018fa1  call    cs:__imp_CoTaskMemFree
0x180018fa7  mov     qword ptr [rbx], 0
0x180018fae  mov     qword ptr [rbx+8], 0
0x180018fb6  mov     qword ptr [rbx+10h], 0
0x180018fbe  add     rsp, 20h
0x180018fc2  pop     rbx
0x180018fc3  retn
```
