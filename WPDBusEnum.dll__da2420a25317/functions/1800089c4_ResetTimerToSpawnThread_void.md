# ResetTimerToSpawnThread(void)

- ea: `0x1800089c4`
- end: `0x180008a63`
- name: `?ResetTimerToSpawnThread@@YAXXZ`
- size: `159`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800018c0`
- `0x1800031b0`

## callees

- `0x1800089c4`
- `0x18000e080`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008a4e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008a4e`

## pseudocode

```c
void ResetTimerToSpawnThread(void)
{
  struct _TP_TIMER *v0; // rcx
  const wchar_t *v1; // r9
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  v0 = g_shutdownTimer;
  if ( g_shutdownTimer )
  {
    pftDueTime = 0;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v1 = L"Reset";
      if ( !g_fShutdownTimerSet )
        v1 = L"Set";
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
        (_DWORD)v1,
        120);
      v0 = g_shutdownTimer;
    }
    pftDueTime = (struct _FILETIME)-1200000000LL;
    SetThreadpoolTimer(v0, &pftDueTime, 0, 0);
    g_fShutdownTimerSet = 1;
  }
}

```

## disassembly

```asm
0x1800089c4  sub     rsp, 38h
0x1800089c8  mov     rcx, cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA; _TP_TIMER * g_shutdownTimer
0x1800089cf  test    rcx, rcx
0x1800089d2  jz      loc_180008A5E
0x1800089d8  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0
0x1800089e1  mov     rax, cs:WPP_GLOBAL_Control
0x1800089e8  lea     rdx, WPP_GLOBAL_Control
0x1800089ef  cmp     rax, rdx
0x1800089f2  jz      short loc_180008A3A
0x1800089f4  test    dword ptr [rax+1Ch], 200h
0x1800089fb  jz      short loc_180008A3A
0x1800089fd  cmp     cs:?g_fShutdownTimerSet@@3HA, 0; int g_fShutdownTimerSet
0x180008a04  lea     rcx, aSet; "Set"
0x180008a0b  lea     r9, aReset; "Reset"
0x180008a12  mov     [rsp+38h+var_18], 78h ; 'x'
0x180008a1a  cmovz   r9, rcx
0x180008a1e  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180008a25  mov     rcx, [rax+10h]
0x180008a29  mov     edx, 0Eh
0x180008a2e  call    WPP_SF_Sd
0x180008a33  mov     rcx, cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA; pti
0x180008a3a  xor     r9d, r9d; msWindowLength
0x180008a3d  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFB8797400h
0x180008a46  xor     r8d, r8d; msPeriod
0x180008a49  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180008a4e  call    cs:__imp_SetThreadpoolTimer
0x180008a54  mov     cs:?g_fShutdownTimerSet@@3HA, 1; int g_fShutdownTimerSet
0x180008a5e  add     rsp, 38h
0x180008a62  retn
```
