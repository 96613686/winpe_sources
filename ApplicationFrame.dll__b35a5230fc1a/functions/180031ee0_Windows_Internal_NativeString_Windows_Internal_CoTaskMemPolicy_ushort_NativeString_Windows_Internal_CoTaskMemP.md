# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::~NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>(void)

- ea: `0x180031ee0`
- end: `0x180031f14`
- name: `??1?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ`
- size: `52`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006fa06`
- `0x18006fcdb`
- `0x18006ff8a`
- `0x18006ffbc`
- `0x1800700a0`
- `0x1800700d2`
- `0x180070196`
- `0x18007145f`
- `0x1800714a7`

## callees

- `0x180031ee0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031ef1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031ef1`

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
0x180031ee0  push    rbx
0x180031ee2  sub     rsp, 20h
0x180031ee6  mov     rbx, rcx
0x180031ee9  mov     rcx, [rcx]; pv
0x180031eec  test    rcx, rcx
0x180031eef  jz      short loc_180031EFE
0x180031ef1  call    cs:__imp_CoTaskMemFree
0x180031ef7  mov     qword ptr [rbx], 0
0x180031efe  mov     qword ptr [rbx+8], 0
0x180031f06  mov     qword ptr [rbx+10h], 0
0x180031f0e  add     rsp, 20h
0x180031f12  pop     rbx
0x180031f13  retn
```
