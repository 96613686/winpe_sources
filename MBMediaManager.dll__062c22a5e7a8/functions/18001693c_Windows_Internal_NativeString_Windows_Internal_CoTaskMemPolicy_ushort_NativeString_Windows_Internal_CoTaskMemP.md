# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::~NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>(void)

- ea: `0x18001693c`
- end: `0x180016970`
- name: `??1?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180056be0`
- `0x180056ea3`
- `0x1800571f0`
- `0x180057202`
- `0x1800574c5`
- `0x1800574d7`

## callees

- `0x18001693c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001694d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001694d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001693c  push    rbx
0x18001693e  sub     rsp, 20h
0x180016942  mov     rbx, rcx
0x180016945  mov     rcx, [rcx]; pv
0x180016948  test    rcx, rcx
0x18001694b  jz      short loc_18001695A
0x18001694d  call    cs:__imp_CoTaskMemFree
0x180016953  mov     qword ptr [rbx], 0
0x18001695a  mov     qword ptr [rbx+8], 0
0x180016962  mov     qword ptr [rbx+10h], 0
0x18001696a  add     rsp, 20h
0x18001696e  pop     rbx
0x18001696f  retn
```
