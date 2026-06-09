# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x180012b0c`
- end: `0x180012b40`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010a54`
- `0x1800120b8`
- `0x180012b48`
- `0x18001642c`
- `0x1800166a0`
- `0x180016868`
- `0x18001874c`

## callees

- `0x180012b0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012b1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012b1d`

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
0x180012b0c  push    rbx
0x180012b0e  sub     rsp, 20h
0x180012b12  mov     rbx, rcx
0x180012b15  mov     rcx, [rcx]; pv
0x180012b18  test    rcx, rcx
0x180012b1b  jz      short loc_180012B2A
0x180012b1d  call    cs:__imp_CoTaskMemFree
0x180012b23  mov     qword ptr [rbx], 0
0x180012b2a  mov     qword ptr [rbx+8], 0
0x180012b32  mov     qword ptr [rbx+10h], 0
0x180012b3a  add     rsp, 20h
0x180012b3e  pop     rbx
0x180012b3f  retn
```
