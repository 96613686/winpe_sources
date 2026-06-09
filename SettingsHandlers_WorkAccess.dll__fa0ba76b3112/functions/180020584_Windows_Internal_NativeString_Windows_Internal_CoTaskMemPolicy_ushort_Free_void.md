# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x180020584`
- end: `0x1800205bf`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `59`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `26`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019d44`
- `0x18001a8b4`
- `0x18001cb1c`
- `0x18001ce98`
- `0x18001e100`
- `0x1800208f8`
- `0x180023910`
- `0x180025cf0`
- `0x180025e30`
- `0x180026140`
- `0x180027bd8`
- `0x18002f060`
- `0x18002f38c`
- `0x18002f468`
- `0x18002f4d4`
- `0x1800339a0`
- `0x18003b018`
- `0x18003b52c`
- `0x18003b5d8`
- `0x18003bbf8`
- `0x18003d944`
- `0x18003e2f0`
- `0x180042080`
- `0x180043694`
- `0x180043740`
- `0x1800441d0`

## callees

- `0x180020584`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020595`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020595`

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
0x180020584  push    rbx
0x180020586  sub     rsp, 20h
0x18002058a  mov     rbx, rcx
0x18002058d  mov     rcx, [rcx]; pv
0x180020590  test    rcx, rcx
0x180020593  jz      short loc_1800205A8
0x180020595  call    cs:__imp_CoTaskMemFree
0x18002059c  nop     dword ptr [rax+rax+00h]
0x1800205a1  mov     qword ptr [rbx], 0
0x1800205a8  mov     qword ptr [rbx+8], 0
0x1800205b0  mov     qword ptr [rbx+10h], 0
0x1800205b8  add     rsp, 20h
0x1800205bc  pop     rbx
0x1800205bd  retn
```
