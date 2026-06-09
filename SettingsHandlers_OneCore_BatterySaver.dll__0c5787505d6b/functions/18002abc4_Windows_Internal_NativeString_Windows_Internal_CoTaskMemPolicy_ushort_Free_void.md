# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x18002abc4`
- end: `0x18002abf8`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001776c`
- `0x18001a060`
- `0x18001dda4`
- `0x18001fef0`
- `0x180021fc0`
- `0x180022480`
- `0x18002aed4`
- `0x18002d8a0`
- `0x180034ca0`
- `0x1800361f0`
- `0x1800372d0`
- `0x18003ae30`
- `0x18004597c`

## callees

- `0x18002abc4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002abd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002abd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18002abc4  push    rbx
0x18002abc6  sub     rsp, 20h
0x18002abca  mov     rbx, rcx
0x18002abcd  mov     rcx, [rcx]; pv
0x18002abd0  test    rcx, rcx
0x18002abd3  jz      short loc_18002ABE2
0x18002abd5  call    cs:__imp_CoTaskMemFree
0x18002abdb  mov     qword ptr [rbx], 0
0x18002abe2  mov     qword ptr [rbx+8], 0
0x18002abea  mov     qword ptr [rbx+10h], 0
0x18002abf2  add     rsp, 20h
0x18002abf6  pop     rbx
0x18002abf7  retn
```
