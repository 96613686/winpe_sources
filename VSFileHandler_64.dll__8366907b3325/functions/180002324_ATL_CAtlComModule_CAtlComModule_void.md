# ATL::CAtlComModule::CAtlComModule(void)

- ea: `0x180002324`
- end: `0x1800023a3`
- name: `??0CAtlComModule@ATL@@QEAA@XZ`
- size: `127`
- prototype: `__int64 __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800010b0`

## callees

- `0x180002324`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x180002369`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180002369`
- `KERNEL32!GetLastError` at `0x180002373`
- `KERNEL32!GetLastError` at `0x180002373`

## pseudocode

```c
ATL::CAtlComModule *__fastcall ATL::CAtlComModule::CAtlComModule(ATL::CAtlComModule *this)
{
  char *v2; // rcx
  signed int LastError; // eax
  signed int v4; // ecx

  v2 = (char *)this + 32;
  *(_OWORD *)v2 = 0;
  *((_OWORD *)v2 + 1) = 0;
  *((_QWORD *)v2 + 4) = 0;
  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = 0x180000000uLL;
  *((_QWORD *)this + 2) = &_pobjMap_CVsShellExtHandler;
  *((_QWORD *)this + 3) = &_pobjMapEntryLast;
  if ( InitializeCriticalSectionEx((LPCRITICAL_SECTION)v2, 0, 0) )
    goto LABEL_6;
  LastError = GetLastError();
  v4 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v4 = LastError;
  if ( v4 >= 0 )
LABEL_6:
    *(_DWORD *)this = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return this;
}

```

## disassembly

```asm
0x180002324  push    rbx
0x180002326  sub     rsp, 20h
0x18000232a  mov     rbx, rcx
0x18000232d  xor     eax, eax
0x18000232f  add     rcx, 20h ; ' '; lpCriticalSection
0x180002333  xorps   xmm0, xmm0
0x180002336  xor     r8d, r8d; Flags
0x180002339  xor     edx, edx; dwSpinCount
0x18000233b  movups  xmmword ptr [rcx], xmm0
0x18000233e  movups  xmmword ptr [rcx+10h], xmm0
0x180002342  mov     [rcx+20h], rax
0x180002346  and     [rbx], eax
0x180002348  lea     rax, cs:180000000h
0x18000234f  mov     [rbx+8], rax
0x180002353  lea     rax, __pobjMap_CVsShellExtHandler
0x18000235a  mov     [rbx+10h], rax
0x18000235e  lea     rax, __pobjMapEntryLast
0x180002365  mov     [rbx+18h], rax
0x180002369  call    cs:__imp_InitializeCriticalSectionEx
0x18000236f  test    eax, eax
0x180002371  jnz     short loc_180002394
0x180002373  call    cs:__imp_GetLastError
0x180002379  movzx   ecx, ax
0x18000237c  or      ecx, 80070000h
0x180002382  test    eax, eax
0x180002384  cmovle  ecx, eax
0x180002387  test    ecx, ecx
0x180002389  jns     short loc_180002394
0x18000238b  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x180002392  jmp     short loc_18000239A
0x180002394  mov     dword ptr [rbx], 48h ; 'H'
0x18000239a  mov     rax, rbx
0x18000239d  add     rsp, 20h
0x1800023a1  pop     rbx
0x1800023a2  retn
```
