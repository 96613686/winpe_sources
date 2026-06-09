# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x180021534`
- end: `0x180021568`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `15`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f808`
- `0x18001fbb8`
- `0x180020cf0`
- `0x180027030`
- `0x180037c40`
- `0x18004c840`
- `0x18004e7dc`
- `0x18004eba0`
- `0x180052128`
- `0x18005249c`
- `0x180052848`
- `0x1800531c0`
- `0x180053500`
- `0x180053700`
- `0x18005387c`

## callees

- `0x180021534`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021545`

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
0x180021534  push    rbx
0x180021536  sub     rsp, 20h
0x18002153a  mov     rbx, rcx
0x18002153d  mov     rcx, [rcx]; pv
0x180021540  test    rcx, rcx
0x180021543  jz      short loc_180021552
0x180021545  call    cs:__imp_CoTaskMemFree
0x18002154b  mov     qword ptr [rbx], 0
0x180021552  mov     qword ptr [rbx+8], 0
0x18002155a  mov     qword ptr [rbx+10h], 0
0x180021562  add     rsp, 20h
0x180021566  pop     rbx
0x180021567  retn
```
