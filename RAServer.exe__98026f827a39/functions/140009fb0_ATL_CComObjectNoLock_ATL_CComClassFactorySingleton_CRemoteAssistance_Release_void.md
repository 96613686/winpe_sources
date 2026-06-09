# ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::Release(void)

- ea: `0x140009fb0`
- end: `0x140009fdd`
- name: `?Release@?$CComObjectNoLock@V?$CComClassFactorySingleton@VCRemoteAssistance@@@ATL@@@ATL@@UEAAKXZ`
- size: `45`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003f00`
- `0x140009fb0`
- `0x14000a230`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  _QWORD *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((volatile int *)(a1 + 8));
  if ( !v1 && v2 )
    ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::`scalar deleting destructor'(v2);
  return v1;
}

```

## disassembly

```asm
0x140009fb0  push    rbx
0x140009fb2  sub     rsp, 20h
0x140009fb6  mov     r10, rcx
0x140009fb9  add     rcx, 8; volatile int *
0x140009fbd  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x140009fc2  mov     ebx, eax
0x140009fc4  test    eax, eax
0x140009fc6  jnz     short loc_140009FD5
0x140009fc8  test    r10, r10
0x140009fcb  jz      short loc_140009FD5
0x140009fcd  mov     rcx, r10
0x140009fd0  call    ??_G?$CComObjectNoLock@V?$CComClassFactorySingleton@VCRemoteAssistance@@@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::`scalar deleting destructor'(uint)
0x140009fd5  mov     eax, ebx
0x140009fd7  add     rsp, 20h
0x140009fdb  pop     rbx
0x140009fdc  retn
```
