# GameInputReading::Release(void)

- ea: `0x18000a710`
- end: `0x18000a788`
- name: `?Release@GameInputReading@@UEAAKXZ`
- size: `120`
- prototype: `unsigned int __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000a790`

## callees

- `0x1800041f8`
- `0x180005854`
- `0x18000a710`
- `0x18000c11c`
- `0x18000d68c`

## pseudocode

```c
__int64 __fastcall GameInputReading::Release(volatile signed __int32 *P)
{
  signed __int32 v2; // edi
  unsigned __int32 v3; // edi
  const struct std::nothrow_t *v4; // rdx

  v2 = _InterlockedExchangeAdd(P + 4, 0xFFFFFFFF);
  if ( !v2 )
  {
    GameInputFailFast(2147500036LL, 157);
    JUMPOUT(0x18000A787LL);
  }
  v3 = v2 - 1;
  if ( !v3 )
    GameInputClient::DecrementGlobalObjectCount();
  ++dword_1800696C4;
  if ( !v3 && P )
  {
    ReadingPoolElementPtr::~ReadingPoolElementPtr((ReadingPoolElementPtr *)(P + 14));
    *(_QWORD *)P = &ClientObjectBase<InterfaceHierarchy<IGameInputReading,IGameInputReadingPrivate>,InterfaceHierarchy<IGameInputRawDeviceReport,IGameInputRawDeviceReportPrivate>>::`vftable'{for `InterfaceHierarchy<IGameInputReading,IGameInputReadingPrivate>'};
    *((_QWORD *)P + 1) = &ClientObjectBase<InterfaceHierarchy<IGameInputReading,IGameInputReadingPrivate>,InterfaceHierarchy<IGameInputRawDeviceReport,IGameInputRawDeviceReportPrivate>>::`vftable'{for `InterfaceHierarchy<IGameInputRawDeviceReport,IGameInputRawDeviceReportPrivate>'};
    operator delete((PVOID)P, v4);
  }
  return v3;
}

```

## disassembly

```asm
0x18000a710  mov     [rsp+arg_0], rbx
0x18000a715  push    rdi
0x18000a716  sub     rsp, 20h
0x18000a71a  mov     rbx, rcx
0x18000a71d  nop
0x18000a71e  or      edi, 0FFFFFFFFh
0x18000a721  lock xadd [rcx+10h], edi
0x18000a726  nop
0x18000a727  test    edi, edi
0x18000a729  jz      short loc_18000A778
0x18000a72b  sub     edi, 1
0x18000a72e  jnz     short loc_18000A735
0x18000a730  call    ?DecrementGlobalObjectCount@GameInputClient@@SAXXZ; GameInputClient::DecrementGlobalObjectCount(void)
0x18000a735  inc     cs:dword_1800696C4
0x18000a73b  test    edi, edi
0x18000a73d  jnz     short loc_18000A76A
0x18000a73f  test    rbx, rbx
0x18000a742  jz      short loc_18000A76A
0x18000a744  lea     rcx, [rbx+38h]; this
0x18000a748  call    ??1ReadingPoolElementPtr@@QEAA@XZ; ReadingPoolElementPtr::~ReadingPoolElementPtr(void)
0x18000a74d  lea     rax, ??_7?$ClientObjectBase@U?$InterfaceHierarchy@UIGameInputReading@@UIGameInputReadingPrivate@@@@U?$InterfaceHierarchy@UIGameInputRawDeviceReport@@UIGameInputRawDeviceReportPrivate@@@@@@6B?$InterfaceHierarchy@UIGameInputReading@@UIGameInputReadingPrivate@@@@@; const ClientObjectBase<InterfaceHierarchy<IGameInputReading,IGameInputReadingPrivate>,InterfaceHierarchy<IGameInputRawDeviceReport,IGameInputRawDeviceReportPrivate>>::`vftable'{for `InterfaceHierarchy<IGameInputReading,IGameInputReadingPrivate>'}
0x18000a754  mov     rcx, rbx; P
0x18000a757  mov     [rbx], rax
0x18000a75a  lea     rax, ??_7?$ClientObjectBase@U?$InterfaceHierarchy@UIGameInputReading@@UIGameInputReadingPrivate@@@@U?$InterfaceHierarchy@UIGameInputRawDeviceReport@@UIGameInputRawDeviceReportPrivate@@@@@@6B?$InterfaceHierarchy@UIGameInputRawDeviceReport@@UIGameInputRawDeviceReportPrivate@@@@@; const ClientObjectBase<InterfaceHierarchy<IGameInputReading,IGameInputReadingPrivate>,InterfaceHierarchy<IGameInputRawDeviceReport,IGameInputRawDeviceReportPrivate>>::`vftable'{for `InterfaceHierarchy<IGameInputRawDeviceReport,IGameInputRawDeviceReportPrivate>'}
0x18000a761  mov     [rbx+8], rax
0x18000a765  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a76a  mov     rbx, [rsp+28h+arg_0]
0x18000a76f  mov     eax, edi
0x18000a771  add     rsp, 20h
0x18000a775  pop     rdi
0x18000a776  retn
0x18000a778  mov     edx, 9Dh
0x18000a77d  mov     ecx, 80004004h
0x18000a782  call    GameInputFailFast
```
