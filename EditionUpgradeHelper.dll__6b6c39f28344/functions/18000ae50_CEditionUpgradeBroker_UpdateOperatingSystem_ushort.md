# CEditionUpgradeBroker::UpdateOperatingSystem(ushort *)

- ea: `0x18000ae50`
- end: `0x18000aebd`
- name: `?UpdateOperatingSystem@CEditionUpgradeBroker@@UEAAJPEAG@Z`
- size: `109`
- prototype: `__int64 __fastcall(CEditionUpgradeBroker *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180008c60`
- `0x180009978`
- `0x18000ae50`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeBroker::UpdateOperatingSystem(CEditionUpgradeBroker *this, unsigned __int16 *a2)
{
  int v4; // eax
  unsigned int v5; // ebx

  if ( !*((_QWORD *)this + 6)
    && (v4 = (*(__int64 (__fastcall **)(CEditionUpgradeBroker *))(*(_QWORD *)this + 64LL))(this), v5 = v4, v4 < 0)
    || (v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 6) + 32LL))(
               *((_QWORD *)this + 6),
               a2,
               1),
        v5 = v4,
        v4 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x18000ae50  mov     [rsp+arg_0], rbx
0x18000ae55  mov     [rsp+arg_8], rsi
0x18000ae5a  push    rdi
0x18000ae5b  sub     rsp, 20h
0x18000ae5f  cmp     qword ptr [rcx+30h], 0
0x18000ae64  mov     rsi, rdx
0x18000ae67  mov     rdi, rcx
0x18000ae6a  jnz     short loc_18000AE7E
0x18000ae6c  mov     rax, [rcx]
0x18000ae6f  mov     rax, [rax+40h]
0x18000ae73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae78  mov     ebx, eax
0x18000ae7a  test    eax, eax
0x18000ae7c  js      short loc_18000AE9D
0x18000ae7e  mov     rcx, [rdi+30h]
0x18000ae82  mov     r8d, 1
0x18000ae88  mov     rdx, rsi
0x18000ae8b  mov     rax, [rcx]
0x18000ae8e  mov     rax, [rax+20h]
0x18000ae92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae97  mov     ebx, eax
0x18000ae99  test    eax, eax
0x18000ae9b  jns     short loc_18000AEA4
0x18000ae9d  mov     ecx, eax
0x18000ae9f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000aea4  mov     ecx, ebx
0x18000aea6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000aeab  mov     rsi, [rsp+28h+arg_8]
0x18000aeb0  mov     eax, ebx
0x18000aeb2  mov     rbx, [rsp+28h+arg_0]
0x18000aeb7  add     rsp, 20h
0x18000aebb  pop     rdi
0x18000aebc  retn
```
