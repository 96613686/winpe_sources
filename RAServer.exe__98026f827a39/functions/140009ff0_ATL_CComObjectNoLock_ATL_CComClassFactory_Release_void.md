# ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(void)

- ea: `0x140009ff0`
- end: `0x14000a01d`
- name: `?Release@?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `45`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003f28`
- `0x140009ff0`
- `0x14000a230`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  void *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((volatile int *)(a1 + 8));
  if ( !v1 && v2 )
    ATL::CComObjectNoLock<ATL::CComClassFactory>::`scalar deleting destructor'(v2);
  return v1;
}

```

## disassembly

```asm
0x140009ff0  push    rbx
0x140009ff2  sub     rsp, 20h
0x140009ff6  mov     r10, rcx
0x140009ff9  add     rcx, 8; volatile int *
0x140009ffd  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x14000a002  mov     ebx, eax
0x14000a004  test    eax, eax
0x14000a006  jnz     short loc_14000A015
0x14000a008  test    r10, r10
0x14000a00b  jz      short loc_14000A015
0x14000a00d  mov     rcx, r10
0x14000a010  call    ??_G?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectNoLock<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x14000a015  mov     eax, ebx
0x14000a017  add     rsp, 20h
0x14000a01b  pop     rbx
0x14000a01c  retn
```
