# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x180037e94`
- end: `0x180037ec8`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180032854`
- `0x1800364e0`
- `0x180036dc8`
- `0x180037f98`

## callees

- `0x180037e94`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037ea5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037ea5`

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
0x180037e94  push    rbx
0x180037e96  sub     rsp, 20h
0x180037e9a  mov     rbx, rcx
0x180037e9d  mov     rcx, [rcx]; pv
0x180037ea0  test    rcx, rcx
0x180037ea3  jz      short loc_180037EB2
0x180037ea5  call    cs:__imp_CoTaskMemFree
0x180037eab  mov     qword ptr [rbx], 0
0x180037eb2  mov     qword ptr [rbx+8], 0
0x180037eba  mov     qword ptr [rbx+10h], 0
0x180037ec2  add     rsp, 20h
0x180037ec6  pop     rbx
0x180037ec7  retn
```
