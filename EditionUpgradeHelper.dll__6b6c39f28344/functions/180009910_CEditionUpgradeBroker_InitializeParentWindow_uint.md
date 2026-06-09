# CEditionUpgradeBroker::InitializeParentWindow(uint)

- ea: `0x180009910`
- end: `0x180009925`
- name: `?InitializeParentWindow@CEditionUpgradeBroker@@UEAAJI@Z`
- size: `21`
- prototype: `__int64 __fastcall(CEditionUpgradeBroker *this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009978`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeBroker::InitializeParentWindow(CEditionUpgradeBroker *this, int a2)
{
  *((_DWORD *)this + 10) = a2;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  return 0;
}

```

## disassembly

```asm
0x180009910  sub     rsp, 28h
0x180009914  mov     [rcx+28h], edx
0x180009917  xor     ecx, ecx
0x180009919  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000991e  xor     eax, eax
0x180009920  add     rsp, 28h
0x180009924  retn
```
