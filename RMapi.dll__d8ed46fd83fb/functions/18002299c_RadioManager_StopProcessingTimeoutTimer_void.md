# RadioManager::_StopProcessingTimeoutTimer(void)

- ea: `0x18002299c`
- end: `0x1800229d0`
- name: `?_StopProcessingTimeoutTimer@RadioManager@@AEAAXXZ`
- size: `52`
- prototype: `void __fastcall(RadioManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b968`
- `0x18001c23c`

## callees

- `0x18002299c`
- `0x180023a64`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800229b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800229b9`

## pseudocode

```c
void __fastcall RadioManager::_StopProcessingTimeoutTimer(RadioManager *this)
{
  struct _TP_TIMER *v2; // rcx

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 54);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    ProtectedSystemState::SetProcessingTimeoutFired((RadioManager *)((char *)this + 48), 0);
  }
}

```

## disassembly

```asm
0x18002299c  push    rbx
0x18002299e  sub     rsp, 20h
0x1800229a2  mov     rbx, rcx
0x1800229a5  mov     rcx, [rcx+1B0h]; pti
0x1800229ac  test    rcx, rcx
0x1800229af  jz      short loc_1800229CA
0x1800229b1  xor     r9d, r9d; msWindowLength
0x1800229b4  xor     r8d, r8d; msPeriod
0x1800229b7  xor     edx, edx; pftDueTime
0x1800229b9  call    cs:__imp_SetThreadpoolTimer
0x1800229bf  lea     rcx, [rbx+30h]; this
0x1800229c3  xor     edx, edx; bool
0x1800229c5  call    ?SetProcessingTimeoutFired@ProtectedSystemState@@QEAAX_N@Z; ProtectedSystemState::SetProcessingTimeoutFired(bool)
0x1800229ca  add     rsp, 20h
0x1800229ce  pop     rbx
0x1800229cf  retn
```
