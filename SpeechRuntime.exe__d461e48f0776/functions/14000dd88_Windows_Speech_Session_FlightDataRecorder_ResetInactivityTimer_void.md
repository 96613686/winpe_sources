# Windows::Speech::Session::FlightDataRecorder::ResetInactivityTimer(void)

- ea: `0x14000dd88`
- end: `0x14000ddac`
- name: `?ResetInactivityTimer@FlightDataRecorder@Session@Speech@Windows@@IEAAXXZ`
- size: `36`
- prototype: `void __fastcall(Windows::Speech::Session::FlightDataRecorder *__hidden this)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x1400078b0`
- `0x14000a1b0`
- `0x14000a46c`
- `0x14000ac24`
- `0x14000b084`
- `0x14000b1ac`
- `0x14000c5e0`
- `0x14000c708`
- `0x14000d4f4`
- `0x14000d7e0`
- `0x14000e720`
- `0x14000f1ac`
- `0x14000f470`
- `0x140010134`
- `0x1400109ec`
- `0x140010b14`

## callees

- `0x14000dd88`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000dda1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000dda1`

## pseudocode

```c
void __fastcall Windows::Speech::Session::FlightDataRecorder::ResetInactivityTimer(
        Windows::Speech::Session::FlightDataRecorder *this)
{
  if ( *((_QWORD *)this + 12) )
    SetThreadpoolTimer(*((PTP_TIMER *)this + 12), (PFILETIME)this + 13, 0, 0);
}

```

## disassembly

```asm
0x14000dd88  sub     rsp, 28h
0x14000dd8c  cmp     qword ptr [rcx+60h], 0
0x14000dd91  jz      short loc_14000DDA7
0x14000dd93  lea     rdx, [rcx+68h]; pftDueTime
0x14000dd97  xor     r9d, r9d; msWindowLength
0x14000dd9a  mov     rcx, [rcx+60h]; pti
0x14000dd9e  xor     r8d, r8d; msPeriod
0x14000dda1  call    cs:__imp_SetThreadpoolTimer
0x14000dda7  add     rsp, 28h
0x14000ddab  retn
```
