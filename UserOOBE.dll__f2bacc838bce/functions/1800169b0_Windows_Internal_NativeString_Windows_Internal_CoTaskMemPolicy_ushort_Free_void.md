# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x1800169b0`
- end: `0x1800169e4`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010770`
- `0x180011354`
- `0x180013760`
- `0x180029260`
- `0x18002a480`
- `0x18002abbc`
- `0x180037118`
- `0x180038f8c`
- `0x18003bac0`
- `0x1800423bc`
- `0x18004b254`

## callees

- `0x1800169b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800169c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800169c1`

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
0x1800169b0  push    rbx
0x1800169b2  sub     rsp, 20h
0x1800169b6  mov     rbx, rcx
0x1800169b9  mov     rcx, [rcx]; pv
0x1800169bc  test    rcx, rcx
0x1800169bf  jz      short loc_1800169CE
0x1800169c1  call    cs:__imp_CoTaskMemFree
0x1800169c7  mov     qword ptr [rbx], 0
0x1800169ce  mov     qword ptr [rbx+8], 0
0x1800169d6  mov     qword ptr [rbx+10h], 0
0x1800169de  add     rsp, 20h
0x1800169e2  pop     rbx
0x1800169e3  retn
```
