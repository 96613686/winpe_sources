# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x18007978c`
- end: `0x1800797c0`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180073b00`
- `0x1800744ac`
- `0x180076d64`
- `0x180083528`

## callees

- `0x18007978c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007979d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007979d`

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
0x18007978c  push    rbx
0x18007978e  sub     rsp, 20h
0x180079792  mov     rbx, rcx
0x180079795  mov     rcx, [rcx]; pv
0x180079798  test    rcx, rcx
0x18007979b  jz      short loc_1800797AA
0x18007979d  call    cs:__imp_CoTaskMemFree
0x1800797a3  mov     qword ptr [rbx], 0
0x1800797aa  mov     qword ptr [rbx+8], 0
0x1800797b2  mov     qword ptr [rbx+10h], 0
0x1800797ba  add     rsp, 20h
0x1800797be  pop     rbx
0x1800797bf  retn
```
