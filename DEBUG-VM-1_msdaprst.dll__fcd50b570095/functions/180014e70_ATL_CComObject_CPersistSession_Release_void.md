# ATL::CComObject<CPersistSession>::Release(void)

- ea: `0x180014e70`
- end: `0x180014eae`
- name: `?Release@?$CComObject@VCPersistSession@@@ATL@@UEAAKXZ`
- size: `62`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014ec0`
- `0x180014ed0`
- `0x180014ee0`

## callees

- `0x180001dd8`
- `0x18000c848`
- `0x180013904`
- `0x180014e70`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPersistSession>::Release(unsigned __int8 *a1)
{
  unsigned int v2; // edi

  v2 = ATL::SafeDecrementReferenceMultiThread((int *)a1 + 8);
  if ( !v2 && a1 )
  {
    ATL::CComObject<CPersistSession>::~CComObject<CPersistSession>(a1);
    MMMFree(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x180014e70  mov     [rsp+arg_0], rbx
0x180014e75  push    rdi
0x180014e76  sub     rsp, 20h
0x180014e7a  mov     rbx, rcx
0x180014e7d  add     rcx, 20h ; ' '; int *
0x180014e81  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPEAJ@Z; ATL::SafeDecrementReferenceMultiThread(long *)
0x180014e86  mov     edi, eax
0x180014e88  test    eax, eax
0x180014e8a  jnz     short loc_180014EA1
0x180014e8c  test    rbx, rbx
0x180014e8f  jz      short loc_180014EA1
0x180014e91  mov     rcx, rbx
0x180014e94  call    ??1?$CComObject@VCPersistSession@@@ATL@@QEAA@XZ; ATL::CComObject<CPersistSession>::~CComObject<CPersistSession>(void)
0x180014e99  mov     rcx, rbx; unsigned __int8 *
0x180014e9c  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x180014ea1  mov     rbx, [rsp+28h+arg_0]
0x180014ea6  mov     eax, edi
0x180014ea8  add     rsp, 20h
0x180014eac  pop     rdi
0x180014ead  retn
```
