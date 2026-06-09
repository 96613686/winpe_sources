# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x18001ad64`
- end: `0x18001ad98`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800061f8`
- `0x18001a454`
- `0x18001a734`
- `0x18001a8e0`
- `0x18001a970`
- `0x18001ab34`

## callees

- `0x18001ad64`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad75`

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
0x18001ad64  push    rbx
0x18001ad66  sub     rsp, 20h
0x18001ad6a  mov     rbx, rcx
0x18001ad6d  mov     rcx, [rcx]; pv
0x18001ad70  test    rcx, rcx
0x18001ad73  jz      short loc_18001AD82
0x18001ad75  call    cs:__imp_CoTaskMemFree
0x18001ad7b  mov     qword ptr [rbx], 0
0x18001ad82  mov     qword ptr [rbx+8], 0
0x18001ad8a  mov     qword ptr [rbx+10h], 0
0x18001ad92  add     rsp, 20h
0x18001ad96  pop     rbx
0x18001ad97  retn
```
