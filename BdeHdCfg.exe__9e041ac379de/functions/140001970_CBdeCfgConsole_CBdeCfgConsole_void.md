# CBdeCfgConsole::CBdeCfgConsole(void)

- ea: `0x140001970`
- end: `0x140001a21`
- name: `??0CBdeCfgConsole@@QEAA@XZ`
- size: `177`
- prototype: `CBdeCfgConsole *__fastcall(CBdeCfgConsole *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140001bf4`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x140001a12`
- `KERNEL32!InitializeCriticalSection` at `0x140001a12`
- `KERNEL32!CreateWaitableTimerW` at `0x1400019fe`
- `KERNEL32!CreateWaitableTimerW` at `0x1400019fe`
- `KERNEL32!CreateEventW` at `0x1400019ea`
- `KERNEL32!CreateEventW` at `0x1400019ea`
- `BDEHDCFGLIB!??0CDriveConfiguration@@QEAA@XZ` at `0x140001991`
- `BDEHDCFGLIB!??0CDriveConfiguration@@QEAA@XZ` at `0x140001991`
- `BDEHDCFGLIB!??0CBdeCfgLibraryLoader@@QEAA@XZ` at `0x140001987`
- `BDEHDCFGLIB!??0CBdeCfgLibraryLoader@@QEAA@XZ` at `0x140001987`

## pseudocode

```c
CBdeCfgConsole *__fastcall CBdeCfgConsole::CBdeCfgConsole(CBdeCfgConsole *this)
{
  *(_QWORD *)this = &CBdeCfgConsole::`vftable';
  CBdeCfgLibraryLoader::CBdeCfgLibraryLoader((CBdeCfgConsole *)((char *)this + 8));
  CDriveConfiguration::CDriveConfiguration((CBdeCfgConsole *)((char *)this + 72));
  *((_DWORD *)this + 374) = -1;
  *((_QWORD *)this + 180) = 0;
  *((_QWORD *)this + 181) = 0;
  *((_DWORD *)this + 375) = 0;
  *((_OWORD *)this + 85) = 0;
  *((_OWORD *)this + 86) = 0;
  *((_OWORD *)this + 87) = 0;
  *((_OWORD *)this + 88) = 0;
  *((_OWORD *)this + 89) = 0;
  *((_QWORD *)this + 180) = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 181) = CreateWaitableTimerW(0, 0, 0);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1456));
  return this;
}

```

## disassembly

```asm
0x140001970  push    rbx
0x140001972  sub     rsp, 20h
0x140001976  lea     rax, ??_7CBdeCfgConsole@@6B@; const CBdeCfgConsole::`vftable'
0x14000197d  mov     rbx, rcx
0x140001980  mov     [rcx], rax
0x140001983  add     rcx, 8
0x140001987  call    cs:__imp_??0CBdeCfgLibraryLoader@@QEAA@XZ; CBdeCfgLibraryLoader::CBdeCfgLibraryLoader(void)
0x14000198d  lea     rcx, [rbx+48h]
0x140001991  call    cs:__imp_??0CDriveConfiguration@@QEAA@XZ; CDriveConfiguration::CDriveConfiguration(void)
0x140001997  mov     dword ptr [rbx+5D8h], 0FFFFFFFFh
0x1400019a1  xor     eax, eax
0x1400019a3  mov     [rbx+5A0h], rax
0x1400019aa  xorps   xmm1, xmm1
0x1400019ad  mov     [rbx+5A8h], rax
0x1400019b4  xorps   xmm0, xmm0
0x1400019b7  mov     [rbx+5DCh], eax
0x1400019bd  xor     r9d, r9d; lpName
0x1400019c0  movups  xmmword ptr [rbx+550h], xmm0
0x1400019c7  xor     r8d, r8d; bInitialState
0x1400019ca  xor     edx, edx; bManualReset
0x1400019cc  movups  xmmword ptr [rbx+560h], xmm0
0x1400019d3  xor     ecx, ecx; lpEventAttributes
0x1400019d5  movups  xmmword ptr [rbx+570h], xmm1
0x1400019dc  movups  xmmword ptr [rbx+580h], xmm1
0x1400019e3  movups  xmmword ptr [rbx+590h], xmm1
0x1400019ea  call    cs:__imp_CreateEventW
0x1400019f0  xor     r8d, r8d; lpTimerName
0x1400019f3  xor     edx, edx; bManualReset
0x1400019f5  xor     ecx, ecx; lpTimerAttributes
0x1400019f7  mov     [rbx+5A0h], rax
0x1400019fe  call    cs:__imp_CreateWaitableTimerW
0x140001a04  lea     rcx, [rbx+5B0h]; lpCriticalSection
0x140001a0b  mov     [rbx+5A8h], rax
0x140001a12  call    cs:__imp_InitializeCriticalSection
0x140001a18  mov     rax, rbx
0x140001a1b  add     rsp, 20h
0x140001a1f  pop     rbx
0x140001a20  retn
```
