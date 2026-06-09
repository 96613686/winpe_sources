# PeerDistSvcSartTimer(ITnoCfgMgr *)

- ea: `0x1801145a4`
- end: `0x1801146ba`
- name: `?PeerDistSvcSartTimer@@YAXPEAVITnoCfgMgr@@@Z`
- size: `278`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801140e0`

## callees

- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x1801145a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011465c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011465c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801146a4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801146a4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180114628`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180114628`

## pseudocode

```c
void __fastcall PeerDistSvcSartTimer(PVOID pv)
{
  struct _TP_TIMER *ThreadpoolTimer; // rax
  DWORD LastError; // eax
  _BYTE v4[40]; // [rsp+20h] [rbp-28h] BYREF
  struct _FILETIME pftDueTime; // [rsp+58h] [rbp+10h] BYREF

  pftDueTime = 0;
  InCritSec::InCritSec((InCritSec *)v4, (struct CritSec *)&qword_1801A72D0, 1);
  if ( byte_1801A76D0 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 35, WPP_c106f1c2962a3571e634919788e67001_Traceguids);
    }
  }
  else
  {
    ThreadpoolTimer = CreateThreadpoolTimer(StaticTimerCallback, pv, 0);
    pti = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      pftDueTime.dwHighDateTime = -26;
      pftDueTime.dwLowDateTime = -625817600;
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0xA4CB80u, 0);
    }
    else if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 36, WPP_c106f1c2962a3571e634919788e67001_Traceguids, LastError);
    }
  }
  InCritSec::~InCritSec((InCritSec *)v4);
}

```

## disassembly

```asm
0x1801145a4  push    rbx
0x1801145a6  sub     rsp, 40h
0x1801145aa  mov     rbx, rcx
0x1801145ad  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0
0x1801145b6  lea     rcx, [rsp+48h+var_28]; this
0x1801145bb  mov     r8b, 1; bool
0x1801145be  lea     rdx, qword_1801A72D0; struct CritSec *
0x1801145c5  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x1801145ca  cmp     cs:byte_1801A76D0, 0
0x1801145d1  jz      short loc_18011461B
0x1801145d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801145da  lea     rdx, WPP_GLOBAL_Control
0x1801145e1  cmp     rcx, rdx
0x1801145e4  jz      loc_1801146AA
0x1801145ea  test    dword ptr [rcx+6Ch], 800h
0x1801145f1  jz      loc_1801146AA
0x1801145f7  cmp     byte ptr [rcx+69h], 1
0x1801145fb  jb      loc_1801146AA
0x180114601  mov     rcx, [rcx+60h]
0x180114605  lea     r8, WPP_c106f1c2962a3571e634919788e67001_Traceguids
0x18011460c  mov     edx, 23h ; '#'
0x180114611  call    WPP_SF_
0x180114616  jmp     loc_1801146AA
0x18011461b  xor     r8d, r8d; pcbe
0x18011461e  lea     rcx, ?StaticTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180114625  mov     rdx, rbx; pv
0x180114628  call    cs:__imp_CreateThreadpoolTimer
0x18011462e  mov     cs:pti, rax
0x180114635  test    rax, rax
0x180114638  jnz     short loc_180114683
0x18011463a  mov     rax, cs:WPP_GLOBAL_Control
0x180114641  lea     rdx, WPP_GLOBAL_Control
0x180114648  cmp     rax, rdx
0x18011464b  jz      short loc_1801146AA
0x18011464d  test    dword ptr [rax+6Ch], 800h
0x180114654  jz      short loc_1801146AA
0x180114656  cmp     byte ptr [rax+69h], 1
0x18011465a  jb      short loc_1801146AA
0x18011465c  call    cs:__imp_GetLastError
0x180114662  mov     rcx, cs:WPP_GLOBAL_Control
0x180114669  lea     r8, WPP_c106f1c2962a3571e634919788e67001_Traceguids
0x180114670  mov     edx, 24h ; '$'
0x180114675  mov     r9d, eax
0x180114678  mov     rcx, [rcx+60h]
0x18011467c  call    WPP_SF_d
0x180114681  jmp     short loc_1801146AA
0x180114683  xor     r9d, r9d; msWindowLength
0x180114686  mov     [rsp+48h+pftDueTime.dwHighDateTime], 0FFFFFFE6h
0x18011468e  mov     r8d, 0A4CB80h; msPeriod
0x180114694  mov     [rsp+48h+pftDueTime.dwLowDateTime], 0DAB2C800h
0x18011469c  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1801146a1  mov     rcx, rax; pti
0x1801146a4  call    cs:__imp_SetThreadpoolTimer
0x1801146aa  lea     rcx, [rsp+48h+var_28]; this
0x1801146af  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1801146b4  add     rsp, 40h
0x1801146b8  pop     rbx
0x1801146b9  retn
```
