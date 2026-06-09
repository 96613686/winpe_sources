# CBdeCfgConsole::ProgressTimerEntry(void *,ulong,ulong)

- ea: `0x140003520`
- end: `0x14000354c`
- name: `?ProgressTimerEntry@CBdeCfgConsole@@CAXPEAXKK@Z`
- size: `44`
- prototype: `void __fastcall(CBdeCfgConsole *lpArgToCompletionRoutine, DWORD dwTimerLowValue, DWORD dwTimerHighValue)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003520`
- `0x140004010`

## import_xrefs

- `KERNEL32!SetThreadPreferredUILanguages` at `0x140003533`
- `KERNEL32!SetThreadPreferredUILanguages` at `0x140003533`

## pseudocode

```c
void __fastcall CBdeCfgConsole::ProgressTimerEntry(
        CBdeCfgConsole *lpArgToCompletionRoutine,
        DWORD dwTimerLowValue,
        DWORD dwTimerHighValue)
{
  SetThreadPreferredUILanguages(0x100u, 0, 0);
  if ( lpArgToCompletionRoutine )
    CBdeCfgConsole::UpdateProgress(lpArgToCompletionRoutine);
}

```

## disassembly

```asm
0x140003520  push    rbx
0x140003522  sub     rsp, 20h
0x140003526  mov     rbx, rcx
0x140003529  xor     r8d, r8d; pulNumLanguages
0x14000352c  mov     ecx, 100h; dwFlags
0x140003531  xor     edx, edx; pwszLanguagesBuffer
0x140003533  call    cs:__imp_SetThreadPreferredUILanguages
0x140003539  test    rbx, rbx
0x14000353c  jz      short loc_140003546
0x14000353e  mov     rcx, rbx; this
0x140003541  call    ?UpdateProgress@CBdeCfgConsole@@AEAAJXZ; CBdeCfgConsole::UpdateProgress(void)
0x140003546  add     rsp, 20h
0x14000354a  pop     rbx
0x14000354b  retn
```
