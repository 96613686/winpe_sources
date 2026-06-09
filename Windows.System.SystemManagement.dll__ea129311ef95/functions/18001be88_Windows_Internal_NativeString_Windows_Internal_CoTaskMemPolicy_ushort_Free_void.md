# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x18001be88`
- end: `0x18001bebc`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800194f8`
- `0x18001bad0`

## callees

- `0x18001be88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001be99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001be99`

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
0x18001be88  push    rbx
0x18001be8a  sub     rsp, 20h
0x18001be8e  mov     rbx, rcx
0x18001be91  mov     rcx, [rcx]; pv
0x18001be94  test    rcx, rcx
0x18001be97  jz      short loc_18001BEA6
0x18001be99  call    cs:__imp_CoTaskMemFree
0x18001be9f  mov     qword ptr [rbx], 0
0x18001bea6  mov     qword ptr [rbx+8], 0
0x18001beae  mov     qword ptr [rbx+10h], 0
0x18001beb6  add     rsp, 20h
0x18001beba  pop     rbx
0x18001bebb  retn
```
