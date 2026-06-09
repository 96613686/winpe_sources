# CEditionUpgradeBroker::ShowSystemDialog(ushort *,ushort *)

- ea: `0x18000a4e0`
- end: `0x18000a509`
- name: `?ShowSystemDialog@CEditionUpgradeBroker@@UEAAJPEAG0@Z`
- size: `41`
- prototype: `__int64 __fastcall(CEditionUpgradeBroker *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009978`

## import_xrefs

- `USER32!MessageBoxW` at `0x18000a4f5`
- `USER32!MessageBoxW` at `0x18000a4f5`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeBroker::ShowSystemDialog(
        CEditionUpgradeBroker *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  MessageBoxW(0, a3, a2, 0x1030u);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  return 0;
}

```

## disassembly

```asm
0x18000a4e0  sub     rsp, 28h
0x18000a4e4  mov     rax, r8
0x18000a4e7  mov     r9d, 1030h; uType
0x18000a4ed  mov     r8, rdx; lpCaption
0x18000a4f0  xor     ecx, ecx; hWnd
0x18000a4f2  mov     rdx, rax; lpText
0x18000a4f5  call    cs:__imp_MessageBoxW
0x18000a4fb  xor     ecx, ecx
0x18000a4fd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a502  xor     eax, eax
0x18000a504  add     rsp, 28h
0x18000a508  retn
```
