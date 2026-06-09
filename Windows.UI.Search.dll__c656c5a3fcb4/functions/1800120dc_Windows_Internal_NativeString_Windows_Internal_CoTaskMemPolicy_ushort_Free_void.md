# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x1800120dc`
- end: `0x180012110`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `52`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e0a4`
- `0x18000e970`
- `0x18000eb10`
- `0x1800111b0`
- `0x180012d24`
- `0x180013db4`
- `0x180013e38`
- `0x180014630`
- `0x180014c20`
- `0x1800150cc`
- `0x1800152e8`
- `0x180015464`
- `0x180016f90`
- `0x1800170c0`
- `0x180020258`
- `0x1800219a0`
- `0x1800224e0`
- `0x1800242f0`
- `0x1800245c0`
- `0x18002528c`
- `0x1800253c4`
- `0x1800255c0`
- `0x18002e0d4`
- `0x18002ea20`
- `0x180030754`
- `0x1800336c0`
- `0x1800336f0`
- `0x180033718`
- `0x180033750`
- `0x180035e54`
- `0x180036620`
- `0x180036930`
- `0x180037ac0`
- `0x1800381f0`
- `0x1800383b0`
- `0x180038894`
- `0x180038a18`
- `0x1800391a8`
- `0x180039310`
- `0x180039e6c`
- `0x18003c690`
- `0x1800435c8`
- `0x180043df4`
- `0x1800447b4`
- `0x180046f28`
- `0x180049b78`
- `0x18004a294`
- `0x18006f004`
- `0x180070734`
- `0x180075b90`

## callees

- `0x1800120dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120ed`

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
0x1800120dc  push    rbx
0x1800120de  sub     rsp, 20h
0x1800120e2  mov     rbx, rcx
0x1800120e5  mov     rcx, [rcx]; pv
0x1800120e8  test    rcx, rcx
0x1800120eb  jz      short loc_1800120FA
0x1800120ed  call    cs:__imp_CoTaskMemFree
0x1800120f3  mov     qword ptr [rbx], 0
0x1800120fa  mov     qword ptr [rbx+8], 0
0x180012102  mov     qword ptr [rbx+10h], 0
0x18001210a  add     rsp, 20h
0x18001210e  pop     rbx
0x18001210f  retn
```
