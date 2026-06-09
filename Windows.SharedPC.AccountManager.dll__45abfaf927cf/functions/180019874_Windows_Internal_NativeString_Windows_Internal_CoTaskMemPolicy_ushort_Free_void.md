# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x180019874`
- end: `0x1800198a8`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014a7c`
- `0x1800153fc`
- `0x180015638`
- `0x180015b40`
- `0x180015db0`
- `0x180019500`
- `0x180019e4c`
- `0x18001a50c`
- `0x18001eab0`
- `0x18001ffc0`
- `0x1800216f0`

## callees

- `0x180019874`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019885`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019885`

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
0x180019874  push    rbx
0x180019876  sub     rsp, 20h
0x18001987a  mov     rbx, rcx
0x18001987d  mov     rcx, [rcx]; pv
0x180019880  test    rcx, rcx
0x180019883  jz      short loc_180019892
0x180019885  call    cs:__imp_CoTaskMemFree
0x18001988b  mov     qword ptr [rbx], 0
0x180019892  mov     qword ptr [rbx+8], 0
0x18001989a  mov     qword ptr [rbx+10h], 0
0x1800198a2  add     rsp, 20h
0x1800198a6  pop     rbx
0x1800198a7  retn
```
