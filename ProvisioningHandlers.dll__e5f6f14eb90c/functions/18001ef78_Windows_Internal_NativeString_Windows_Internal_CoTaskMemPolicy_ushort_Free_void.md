# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x18001ef78`
- end: `0x18001efb3`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `59`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000fe34`
- `0x180010524`
- `0x180010be8`
- `0x180010c9c`
- `0x1800110fc`
- `0x1800129b0`
- `0x180012b88`
- `0x18001d5b0`
- `0x180020d70`

## callees

- `0x18001ef78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef89`

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
0x18001ef78  push    rbx
0x18001ef7a  sub     rsp, 20h
0x18001ef7e  mov     rbx, rcx
0x18001ef81  mov     rcx, [rcx]; pv
0x18001ef84  test    rcx, rcx
0x18001ef87  jz      short loc_18001EF9C
0x18001ef89  call    cs:__imp_CoTaskMemFree
0x18001ef90  nop     dword ptr [rax+rax+00h]
0x18001ef95  mov     qword ptr [rbx], 0
0x18001ef9c  mov     qword ptr [rbx+8], 0
0x18001efa4  mov     qword ptr [rbx+10h], 0
0x18001efac  add     rsp, 20h
0x18001efb0  pop     rbx
0x18001efb1  retn
```
