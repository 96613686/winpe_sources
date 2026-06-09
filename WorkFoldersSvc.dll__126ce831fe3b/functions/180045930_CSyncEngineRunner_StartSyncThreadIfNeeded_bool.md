# CSyncEngineRunner::StartSyncThreadIfNeeded(bool)

- ea: `0x180045930`
- end: `0x180045a4a`
- name: `?StartSyncThreadIfNeeded@CSyncEngineRunner@@AEAAX_N@Z`
- size: `282`
- prototype: `void __fastcall(CSyncEngineRunner *__hidden this, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180043830`
- `0x1800472d0`

## callees

- `0x180007e10`
- `0x180008b60`
- `0x180011314`
- `0x180045930`

## import_xrefs

- `KERNEL32!SubmitThreadpoolWork` at `0x180045a0a`
- `KERNEL32!SubmitThreadpoolWork` at `0x180045a0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045a25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045a25`

## string_xrefs

- `0x1800459a6`: `CSyncEngineRunner::StartSyncThreadIfNeeded`
- `0x1800459ef`: `CEcsThreadPool::SubmitWork`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CSyncEngineRunner::StartSyncThreadIfNeeded(struct _RTL_CRITICAL_SECTION *this, char a2)
{
  _BYTE *v4; // rax
  char v5; // cl
  __int64 LockCount_low; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-50h] BYREF
  char v8; // [rsp+28h] [rbp-48h]
  _DWORD v9[2]; // [rsp+30h] [rbp-40h] BYREF
  char v10; // [rsp+38h] [rbp-38h]
  const char *v11; // [rsp+40h] [rbp-30h]
  __int64 v12; // [rsp+48h] [rbp-28h]
  _DWORD v13[2]; // [rsp+50h] [rbp-20h] BYREF
  char v14; // [rsp+58h] [rbp-18h]
  const char *v15; // [rsp+60h] [rbp-10h]
  __int64 v16; // [rsp+68h] [rbp-8h]

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_8:
      v5 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 8) == 0 || v4[65] < 6u )
    goto LABEL_8;
  v5 = 1;
LABEL_9:
  v13[0] = 0;
  v13[1] = 201;
  v14 = v5;
  v15 = "CSyncEngineRunner::StartSyncThreadIfNeeded";
  v16 = 0;
  CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>((__int64)&lpCriticalSection, this + 3);
  if ( !*(_QWORD *)&this[5].LockCount || a2 )
  {
    LockCount_low = LOBYTE(this[10].LockCount);
    v9[0] = 0;
    v9[1] = 169;
    v10 = 0;
    v11 = "CEcsThreadPool::SubmitWork";
    v12 = 0;
    SubmitThreadpoolWork(*((PTP_WORK *)&this[8].OwningThread + LockCount_low));
    CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)v9);
  }
  if ( v8 )
  {
    LeaveCriticalSection(lpCriticalSection);
    v8 = 0;
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)v13);
}

```

## disassembly

```asm
0x180045930  mov     [rsp-8+arg_0], rbx
0x180045935  mov     [rsp-8+arg_8], rdi
0x18004593a  push    rbp
0x18004593b  mov     rbp, rsp
0x18004593e  sub     rsp, 70h
0x180045942  mov     dil, dl
0x180045945  mov     rbx, rcx
0x180045948  lea     rcx, WPP_GLOBAL_Control
0x18004594f  mov     rax, cs:WPP_GLOBAL_Control
0x180045956  cmp     rax, rcx
0x180045959  jz      short loc_180045983
0x18004595b  test    byte ptr [rax+44h], 8
0x18004595f  jz      short loc_180045993
0x180045961  cmp     byte ptr [rax+41h], 6
0x180045965  jb      short loc_180045983
0x180045967  mov     edx, 14h
0x18004596c  lea     r8, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids
0x180045973  mov     rcx, [rax+38h]
0x180045977  call    WPP_SF_
0x18004597c  mov     rax, cs:WPP_GLOBAL_Control
0x180045983  test    byte ptr [rax+44h], 8
0x180045987  jz      short loc_180045993
0x180045989  cmp     byte ptr [rax+41h], 6
0x18004598d  jb      short loc_180045993
0x18004598f  mov     cl, 1
0x180045991  jmp     short loc_180045995
0x180045993  xor     cl, cl
0x180045995  mov     [rbp+var_20], 0
0x18004599c  mov     [rbp+var_1C], 0C9h
0x1800459a3  mov     [rbp+var_18], cl
0x1800459a6  lea     rax, aCsyncenginerun_20; "CSyncEngineRunner::StartSyncThreadIfNee"...
0x1800459ad  mov     [rbp+var_10], rax
0x1800459b1  mov     [rbp+var_8], 0
0x1800459b9  lea     rdx, [rbx+78h]
0x1800459bd  lea     rcx, [rbp+lpCriticalSection]
0x1800459c1  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x1800459c6  nop
0x1800459c7  cmp     qword ptr [rbx+0D0h], 0
0x1800459cf  jz      short loc_1800459D6
0x1800459d1  test    dil, dil
0x1800459d4  jz      short loc_180045A1B
0x1800459d6  movzx   ecx, byte ptr [rbx+198h]
0x1800459dd  mov     [rbp+var_40], 0
0x1800459e4  mov     [rbp+var_3C], 0A9h
0x1800459eb  mov     [rbp+var_38], 0
0x1800459ef  lea     rax, aCecsthreadpool_1; "CEcsThreadPool::SubmitWork"
0x1800459f6  mov     [rbp+var_30], rax
0x1800459fa  mov     [rbp+var_28], 0
0x180045a02  mov     rcx, [rbx+rcx*8+150h]; pwk
0x180045a0a  call    cs:__imp_SubmitThreadpoolWork
0x180045a10  nop
0x180045a11  lea     rcx, [rbp+var_40]; this
0x180045a15  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180045a1a  nop
0x180045a1b  cmp     [rbp+var_48], 0
0x180045a1f  jz      short loc_180045A2F
0x180045a21  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180045a25  call    cs:__imp_LeaveCriticalSection
0x180045a2b  mov     [rbp+var_48], 0
0x180045a2f  lea     rcx, [rbp+var_20]; this
0x180045a33  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180045a38  lea     r11, [rsp+70h+var_s0]
0x180045a3d  mov     rbx, [r11+10h]
0x180045a41  mov     rdi, [r11+18h]
0x180045a45  mov     rsp, r11
0x180045a48  pop     rbp
0x180045a49  retn
```
