# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(void)

- ea: `0x18005a960`
- end: `0x18005a994`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005a754`
- `0x18005a89c`
- `0x1800981dc`

## callees

- `0x18005a960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a971`

## pseudocode

```c
void __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(__int64 a1)
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
0x18005a960  push    rbx
0x18005a962  sub     rsp, 20h
0x18005a966  mov     rbx, rcx
0x18005a969  mov     rcx, [rcx]; pv
0x18005a96c  test    rcx, rcx
0x18005a96f  jz      short loc_18005A97E
0x18005a971  call    cs:__imp_CoTaskMemFree
0x18005a977  mov     qword ptr [rbx], 0
0x18005a97e  mov     qword ptr [rbx+8], 0
0x18005a986  mov     qword ptr [rbx+10h], 0
0x18005a98e  add     rsp, 20h
0x18005a992  pop     rbx
0x18005a993  retn
```
