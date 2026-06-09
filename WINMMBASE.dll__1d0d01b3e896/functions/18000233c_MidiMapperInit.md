# MidiMapperInit

- ea: `0x18000233c`
- end: `0x1800023e7`
- name: `MidiMapperInit`
- size: `171`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180001378`
- `0x180001b70`
- `0x1800076b0`
- `0x1800077ec`
- `0x1800078f4`
- `0x18000fd94`

## callees

- `0x180001f30`
- `0x18000233c`
- `0x18000296c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002347`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002354`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002347`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002354`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023e0`

## pseudocode

```c
void MidiMapperInit()
{
  HDRVR v0; // rax
  HDRVR v1; // rax

  EnterCriticalSection(&NumDevsCritSec);
  EnterCriticalSection(&MapperInitCritSec);
  if ( !MidiMapperInitialized && wTotalMidiOutDevs + wTotalMidiInDevs )
  {
    v0 = (HDRVR)mmDrvOpen(wszMidiMapper);
    if ( v0 )
    {
      mmDrvInstall(v0, wszMidiMapper, 0, 0xC004u);
      v1 = (HDRVR)mmDrvOpen(wszMidiMapper);
      mmDrvInstall(v1, wszMidiMapper, 0, 0xC003u);
    }
    MidiMapperInitialized = 1;
  }
  LeaveCriticalSection(&MapperInitCritSec);
  LeaveCriticalSection(&NumDevsCritSec);
}

```

## disassembly

```asm
0x18000233c  sub     rsp, 28h
0x180002340  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180002347  call    cs:__imp_EnterCriticalSection
0x18000234d  lea     rcx, ?MapperInitCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002354  call    cs:__imp_EnterCriticalSection
0x18000235a  cmp     cs:MidiMapperInitialized, 0
0x180002361  jnz     short loc_1800023C8
0x180002363  mov     ecx, cs:wTotalMidiInDevs
0x180002369  add     ecx, cs:wTotalMidiOutDevs
0x18000236f  jz      short loc_1800023C8
0x180002371  lea     rcx, wszMidiMapper; "midimapper"
0x180002378  call    ?mmDrvOpen@@YAPEAUHDRVR__@@PEBG@Z; mmDrvOpen(ushort const *)
0x18000237d  test    rax, rax
0x180002380  jz      short loc_1800023BE
0x180002382  mov     r9d, 0C004h; wFlags
0x180002388  lea     rdx, wszMidiMapper; "midimapper"
0x18000238f  xor     r8d, r8d; drvMessage
0x180002392  mov     rcx, rax; hDriver
0x180002395  call    mmDrvInstall
0x18000239a  lea     rcx, wszMidiMapper; "midimapper"
0x1800023a1  call    ?mmDrvOpen@@YAPEAUHDRVR__@@PEBG@Z; mmDrvOpen(ushort const *)
0x1800023a6  mov     r9d, 0C003h; wFlags
0x1800023ac  lea     rdx, wszMidiMapper; "midimapper"
0x1800023b3  xor     r8d, r8d; drvMessage
0x1800023b6  mov     rcx, rax; hDriver
0x1800023b9  call    mmDrvInstall
0x1800023be  mov     cs:MidiMapperInitialized, 1
0x1800023c8  lea     rcx, ?MapperInitCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800023cf  call    cs:__imp_LeaveCriticalSection
0x1800023d5  lea     rcx, NumDevsCritSec
0x1800023dc  add     rsp, 28h
0x1800023e0  jmp     cs:__imp_LeaveCriticalSection
```
