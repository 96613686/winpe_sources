# CChangeTrackerWatcher::RegisterThreadPoolWaitEvent(CEcsFileTime &)

- ea: `0x18003efd0`
- end: `0x18003f0ac`
- name: `?RegisterThreadPoolWaitEvent@CChangeTrackerWatcher@@AEAAXAEAVCEcsFileTime@@@Z`
- size: `220`
- prototype: `void(CChangeTrackerWatcher *__hidden this, struct CEcsFileTime *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18003e9f0`
- `0x18003f0c0`

## callees

- `0x180007e10`
- `0x180008b60`
- `0x180011314`
- `0x18003efd0`

## import_xrefs

- `KERNEL32!SetThreadpoolWait` at `0x18003f079`
- `KERNEL32!SetThreadpoolWait` at `0x18003f079`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f08c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f08c`

## string_xrefs

- `0x18003f041`: `CChangeTrackerWatcher::RegisterThreadPoolWaitEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CChangeTrackerWatcher::RegisterThreadPoolWaitEvent(CChangeTrackerWatcher *this, struct _FILETIME *a2)
{
  _BYTE *v4; // rax
  char v5; // cl
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-38h] BYREF
  char v7; // [rsp+28h] [rbp-30h]
  _DWORD v8[2]; // [rsp+30h] [rbp-28h] BYREF
  char v9; // [rsp+38h] [rbp-20h]
  const char *v10; // [rsp+40h] [rbp-18h]
  __int64 v11; // [rsp+48h] [rbp-10h]

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, WPP_80060c42e9283c9fa2e2881e1fba40a3_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 8) != 0 && v4[65] >= 6u )
  {
    v5 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v5 = 0;
LABEL_9:
  v8[0] = 0;
  v8[1] = 156;
  v9 = v5;
  v10 = "CChangeTrackerWatcher::RegisterThreadPoolWaitEvent";
  v11 = 0;
  CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(
    (__int64)&lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)this + 2);
  if ( !*((_BYTE *)this + 168) )
    SetThreadpoolWait(*((PTP_WAIT *)this + 2), *((HANDLE *)this + 1), a2);
  if ( v7 )
  {
    LeaveCriticalSection(lpCriticalSection);
    v7 = 0;
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)v8);
}

```

## disassembly

```asm
0x18003efd0  mov     [rsp+arg_0], rbx
0x18003efd5  push    rdi
0x18003efd6  sub     rsp, 50h
0x18003efda  mov     rdi, rdx
0x18003efdd  mov     rbx, rcx
0x18003efe0  lea     rcx, WPP_GLOBAL_Control
0x18003efe7  mov     rax, cs:WPP_GLOBAL_Control
0x18003efee  cmp     rax, rcx
0x18003eff1  jz      short loc_18003F01B
0x18003eff3  test    byte ptr [rax+44h], 8
0x18003eff7  jz      short loc_18003F02B
0x18003eff9  cmp     byte ptr [rax+41h], 6
0x18003effd  jb      short loc_18003F01B
0x18003efff  mov     edx, 13h
0x18003f004  lea     r8, WPP_80060c42e9283c9fa2e2881e1fba40a3_Traceguids
0x18003f00b  mov     rcx, [rax+38h]
0x18003f00f  call    WPP_SF_
0x18003f014  mov     rax, cs:WPP_GLOBAL_Control
0x18003f01b  test    byte ptr [rax+44h], 8
0x18003f01f  jz      short loc_18003F02B
0x18003f021  cmp     byte ptr [rax+41h], 6
0x18003f025  jb      short loc_18003F02B
0x18003f027  mov     cl, 1
0x18003f029  jmp     short loc_18003F02D
0x18003f02b  xor     cl, cl
0x18003f02d  mov     [rsp+58h+var_28], 0
0x18003f035  mov     [rsp+58h+var_24], 9Ch
0x18003f03d  mov     [rsp+58h+var_20], cl
0x18003f041  lea     rax, aCchangetracker_3; "CChangeTrackerWatcher::RegisterThreadPo"...
0x18003f048  mov     [rsp+58h+var_18], rax
0x18003f04d  mov     [rsp+58h+var_10], 0
0x18003f056  lea     rdx, [rbx+50h]
0x18003f05a  lea     rcx, [rsp+58h+lpCriticalSection]
0x18003f05f  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x18003f064  nop
0x18003f065  cmp     byte ptr [rbx+0A8h], 0
0x18003f06c  jnz     short loc_18003F080
0x18003f06e  mov     r8, rdi; pftTimeout
0x18003f071  mov     rdx, [rbx+8]; h
0x18003f075  mov     rcx, [rbx+10h]; pwa
0x18003f079  call    cs:__imp_SetThreadpoolWait
0x18003f07f  nop
0x18003f080  cmp     [rsp+58h+var_30], 0
0x18003f085  jz      short loc_18003F097
0x18003f087  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x18003f08c  call    cs:__imp_LeaveCriticalSection
0x18003f092  mov     [rsp+58h+var_30], 0
0x18003f097  lea     rcx, [rsp+58h+var_28]; this
0x18003f09c  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18003f0a1  mov     rbx, [rsp+58h+arg_0]
0x18003f0a6  add     rsp, 50h
0x18003f0aa  pop     rdi
0x18003f0ab  retn
```
