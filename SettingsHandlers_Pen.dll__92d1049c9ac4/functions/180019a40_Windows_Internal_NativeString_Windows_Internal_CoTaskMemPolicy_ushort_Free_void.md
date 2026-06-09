# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x180019a40`
- end: `0x180019a74`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010bf4`
- `0x1800142b0`
- `0x180015000`
- `0x180016400`
- `0x180019b90`
- `0x180019c14`
- `0x18001b9c0`
- `0x18001ba80`
- `0x18001d790`
- `0x180020bdc`
- `0x1800272b8`
- `0x180027350`
- `0x180027b20`
- `0x1800281d0`
- `0x180029580`
- `0x18002faf0`
- `0x180030130`
- `0x1800511d4`

## callees

- `0x180019a40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019a51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019a51`

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
0x180019a40  push    rbx
0x180019a42  sub     rsp, 20h
0x180019a46  mov     rbx, rcx
0x180019a49  mov     rcx, [rcx]; pv
0x180019a4c  test    rcx, rcx
0x180019a4f  jz      short loc_180019A5E
0x180019a51  call    cs:__imp_CoTaskMemFree
0x180019a57  mov     qword ptr [rbx], 0
0x180019a5e  mov     qword ptr [rbx+8], 0
0x180019a66  mov     qword ptr [rbx+10h], 0
0x180019a6e  add     rsp, 20h
0x180019a72  pop     rbx
0x180019a73  retn
```
