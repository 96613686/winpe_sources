# CEditionUpgradeBroker::CanUpgrade(void)

- ea: `0x180008bb0`
- end: `0x180008be6`
- name: `?CanUpgrade@CEditionUpgradeBroker@@UEAAJXZ`
- size: `54`
- prototype: `__int64 __fastcall(CEditionUpgradeBroker *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008bb0`
- `0x180008c60`
- `0x180009978`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeBroker::CanUpgrade(CEditionUpgradeBroker *this)
{
  unsigned int v1; // ebx
  int v2; // eax

  v1 = 0;
  if ( !*((_QWORD *)this + 6) )
  {
    v2 = (*(__int64 (__fastcall **)(CEditionUpgradeBroker *))(*(_QWORD *)this + 64LL))(this);
    v1 = v2;
    if ( v2 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v2);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v1);
  return v1;
}

```

## disassembly

```asm
0x180008bb0  push    rbx
0x180008bb2  sub     rsp, 20h
0x180008bb6  xor     ebx, ebx
0x180008bb8  cmp     [rcx+30h], rbx
0x180008bbc  jnz     short loc_180008BD7
0x180008bbe  mov     rax, [rcx]
0x180008bc1  mov     rax, [rax+40h]
0x180008bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bca  mov     ebx, eax
0x180008bcc  test    eax, eax
0x180008bce  jns     short loc_180008BD7
0x180008bd0  mov     ecx, eax
0x180008bd2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180008bd7  mov     ecx, ebx
0x180008bd9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180008bde  mov     eax, ebx
0x180008be0  add     rsp, 20h
0x180008be4  pop     rbx
0x180008be5  retn
```
