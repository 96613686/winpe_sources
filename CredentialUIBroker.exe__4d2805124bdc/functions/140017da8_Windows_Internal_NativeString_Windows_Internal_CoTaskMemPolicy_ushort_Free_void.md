# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x140017da8`
- end: `0x140017ddc`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400092d4`
- `0x14000d090`
- `0x140017de4`

## callees

- `0x140017da8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017db9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017db9`

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
0x140017da8  push    rbx
0x140017daa  sub     rsp, 20h
0x140017dae  mov     rbx, rcx
0x140017db1  mov     rcx, [rcx]; pv
0x140017db4  test    rcx, rcx
0x140017db7  jz      short loc_140017DC6
0x140017db9  call    cs:__imp_CoTaskMemFree
0x140017dbf  mov     qword ptr [rbx], 0
0x140017dc6  mov     qword ptr [rbx+8], 0
0x140017dce  mov     qword ptr [rbx+10h], 0
0x140017dd6  add     rsp, 20h
0x140017dda  pop     rbx
0x140017ddb  retn
```
