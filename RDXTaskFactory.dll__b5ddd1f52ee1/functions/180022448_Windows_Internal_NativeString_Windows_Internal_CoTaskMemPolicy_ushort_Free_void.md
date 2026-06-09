# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x180022448`
- end: `0x18002247c`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021428`
- `0x180021830`
- `0x180022848`
- `0x180022bfc`
- `0x18002315c`
- `0x18003106c`
- `0x1800314dc`
- `0x180036b5c`
- `0x18003e178`
- `0x18004a7a0`

## callees

- `0x180022448`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022459`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022459`

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
0x180022448  push    rbx
0x18002244a  sub     rsp, 20h
0x18002244e  mov     rbx, rcx
0x180022451  mov     rcx, [rcx]; pv
0x180022454  test    rcx, rcx
0x180022457  jz      short loc_180022466
0x180022459  call    cs:__imp_CoTaskMemFree
0x18002245f  mov     qword ptr [rbx], 0
0x180022466  mov     qword ptr [rbx+8], 0
0x18002246e  mov     qword ptr [rbx+10h], 0
0x180022476  add     rsp, 20h
0x18002247a  pop     rbx
0x18002247b  retn
```
