# CReader::PowerDownTimeoutStart(void)

- ea: `0x18000371c`
- end: `0x1800037af`
- name: `?PowerDownTimeoutStart@CReader@@IEAAXXZ`
- size: `147`
- prototype: `void __fastcall(CReader *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180001950`
- `0x180018d4c`

## callees

- `0x18000371c`
- `0x1800044e0`
- `0x1800075d0`
- `0x18000cd80`
- `0x18000d7a0`
- `0x180028b78`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003798`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003798`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CReader::PowerDownTimeoutStart(CReader *this)
{
  __int64 v2; // rcx
  char v3; // [rsp+30h] [rbp+8h] BYREF

  CLockWrite::CLockWrite((CLockWrite *)&v3, (CReader *)((char *)this + 56));
  if ( (unsigned int)CReader::AvailabilityStatus((__int64)this) == 5 )
  {
    WppTraceIndent(v2, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids, WPP_pszIndent);
    }
    SetThreadpoolTimer(*((PTP_TIMER *)this + 88), (PFILETIME)this + 90, 0, 0);
  }
  CLockWrite::~CLockWrite((CLockWrite *)&v3);
}

```

## disassembly

```asm
0x18000371c  push    rbx
0x18000371e  sub     rsp, 20h
0x180003722  mov     rbx, rcx
0x180003725  lea     rdx, [rcx+38h]; struct CAccessLock *
0x180003729  lea     rcx, [rsp+28h+arg_0]; this
0x18000372e  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x180003733  nop
0x180003734  mov     rcx, rbx
0x180003737  call    ?AvailabilityStatus@CReader@@QEAA?AW4AvailableState@1@XZ; CReader::AvailabilityStatus(void)
0x18000373c  cmp     eax, 5
0x18000373f  jnz     short loc_18000379F
0x180003741  lea     edx, [rax-3]
0x180003744  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180003749  lea     rax, WPP_GLOBAL_Control
0x180003750  mov     rcx, cs:WPP_GLOBAL_Control
0x180003757  cmp     rcx, rax
0x18000375a  jz      short loc_180003784
0x18000375c  test    byte ptr [rcx+1Ch], 10h
0x180003760  jz      short loc_180003784
0x180003762  cmp     byte ptr [rcx+19h], 4
0x180003766  jb      short loc_180003784
0x180003768  mov     edx, 0Ah
0x18000376d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180003774  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x18000377b  mov     rcx, [rcx+10h]
0x18000377f  call    WPP_SF_s
0x180003784  lea     rdx, [rbx+2D0h]; pftDueTime
0x18000378b  xor     r9d, r9d; msWindowLength
0x18000378e  xor     r8d, r8d; msPeriod
0x180003791  mov     rcx, [rbx+2C0h]; pti
0x180003798  call    cs:__imp_SetThreadpoolTimer
0x18000379e  nop
0x18000379f  lea     rcx, [rsp+28h+arg_0]; this
0x1800037a4  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x1800037a9  add     rsp, 20h
0x1800037ad  pop     rbx
0x1800037ae  retn
```
