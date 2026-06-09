# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x18002407c`
- end: `0x1800240b0`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `65`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018e5c`
- `0x180019be4`
- `0x180019ffc`
- `0x18001a1b4`
- `0x18001a234`
- `0x18001a970`
- `0x18001c09c`
- `0x18001da18`
- `0x18001dee4`
- `0x18001f990`
- `0x1800240b8`
- `0x1800246f4`
- `0x180024a08`
- `0x180024a6c`
- `0x1800252fc`
- `0x18002533c`
- `0x1800254b0`
- `0x180025a08`
- `0x18002699c`
- `0x180026a90`
- `0x180026b80`
- `0x180026c1c`
- `0x180026cc8`
- `0x180026e18`
- `0x1800277c0`
- `0x180027eec`
- `0x180027fb4`
- `0x180028480`
- `0x1800285b0`
- `0x18002a144`
- `0x18002a73c`
- `0x18002a8e4`
- `0x18002b7a4`
- `0x18002b9c0`
- `0x18002be98`
- `0x18002c090`
- `0x18002c154`
- `0x18002c7a0`
- `0x18002e974`
- `0x18002eb74`
- `0x180030908`
- `0x180033994`
- `0x180033b48`
- `0x180035590`
- `0x1800358e8`
- `0x180037df8`
- `0x180037e94`
- `0x180037f58`
- `0x180039d10`
- `0x18003c360`

## callees

- `0x18002407c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002408d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002408d`

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
0x18002407c  push    rbx
0x18002407e  sub     rsp, 20h
0x180024082  mov     rbx, rcx
0x180024085  mov     rcx, [rcx]; pv
0x180024088  test    rcx, rcx
0x18002408b  jz      short loc_18002409A
0x18002408d  call    cs:__imp_CoTaskMemFree
0x180024093  mov     qword ptr [rbx], 0
0x18002409a  mov     qword ptr [rbx+8], 0
0x1800240a2  mov     qword ptr [rbx+10h], 0
0x1800240aa  add     rsp, 20h
0x1800240ae  pop     rbx
0x1800240af  retn
```
