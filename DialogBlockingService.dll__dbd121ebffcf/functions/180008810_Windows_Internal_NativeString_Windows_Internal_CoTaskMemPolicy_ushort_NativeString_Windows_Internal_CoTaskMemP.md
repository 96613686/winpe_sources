# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::~NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>(void)

- ea: `0x180008810`
- end: `0x180008844`
- name: `??1?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000cd49`
- `0x18000cdab`
- `0x18000cee6`

## callees

- `0x180008810`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008821`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008821`

## pseudocode

```c
void __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::~NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>(
        __int64 a1)
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
0x180008810  push    rbx
0x180008812  sub     rsp, 20h
0x180008816  mov     rbx, rcx
0x180008819  mov     rcx, [rcx]; pv
0x18000881c  test    rcx, rcx
0x18000881f  jz      short loc_18000882E
0x180008821  call    cs:__imp_CoTaskMemFree
0x180008827  mov     qword ptr [rbx], 0
0x18000882e  mov     qword ptr [rbx+8], 0
0x180008836  mov     qword ptr [rbx+10h], 0
0x18000883e  add     rsp, 20h
0x180008842  pop     rbx
0x180008843  retn
```
