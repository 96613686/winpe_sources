# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x18003a0f4`
- end: `0x18003a128`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180035a94`
- `0x180035ba8`
- `0x180037280`
- `0x180038dc8`
- `0x18003a130`

## callees

- `0x18003a0f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a105`

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
0x18003a0f4  push    rbx
0x18003a0f6  sub     rsp, 20h
0x18003a0fa  mov     rbx, rcx
0x18003a0fd  mov     rcx, [rcx]; pv
0x18003a100  test    rcx, rcx
0x18003a103  jz      short loc_18003A112
0x18003a105  call    cs:__imp_CoTaskMemFree
0x18003a10b  mov     qword ptr [rbx], 0
0x18003a112  mov     qword ptr [rbx+8], 0
0x18003a11a  mov     qword ptr [rbx+10h], 0
0x18003a122  add     rsp, 20h
0x18003a126  pop     rbx
0x18003a127  retn
```
