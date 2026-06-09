# FaxRouteThread(_JOB_QUEUE *)

- ea: `0x140030cf0`
- end: `0x1400310f3`
- name: `?FaxRouteThread@@YAKPEAU_JOB_QUEUE@@@Z`
- size: `1027`
- prototype: `unsigned int __fastcall(struct _JOB_QUEUE *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140023a0c`
- `0x140030cf0`
- `0x14003437c`
- `0x1400399f0`
- `0x14003c4ac`
- `0x14003de98`
- `0x140040c14`
- `0x140045a14`
- `0x140045cec`
- `0x140052184`
- `0x14005900c`
- `0x1400699d0`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003109c`
- `KERNEL32!GetLastError` at `0x14003109c`
- `KERNEL32!EnterCriticalSection` at `0x140030d5e`
- `KERNEL32!EnterCriticalSection` at `0x140030d71`
- `KERNEL32!EnterCriticalSection` at `0x140030de1`
- `KERNEL32!EnterCriticalSection` at `0x140030eb8`
- `KERNEL32!EnterCriticalSection` at `0x140030ecb`
- `KERNEL32!EnterCriticalSection` at `0x140030f19`
- `KERNEL32!EnterCriticalSection` at `0x140030d5e`
- `KERNEL32!EnterCriticalSection` at `0x140030d71`
- `KERNEL32!EnterCriticalSection` at `0x140030de1`
- `KERNEL32!EnterCriticalSection` at `0x140030eb8`
- `KERNEL32!EnterCriticalSection` at `0x140030ecb`
- `KERNEL32!EnterCriticalSection` at `0x140030f19`
- `KERNEL32!LeaveCriticalSection` at `0x140030d84`
- `KERNEL32!LeaveCriticalSection` at `0x140030d97`
- `KERNEL32!LeaveCriticalSection` at `0x140030e93`
- `KERNEL32!LeaveCriticalSection` at `0x140030f36`
- `KERNEL32!LeaveCriticalSection` at `0x14003105c`
- `KERNEL32!LeaveCriticalSection` at `0x14003106f`
- `KERNEL32!LeaveCriticalSection` at `0x140030d84`
- `KERNEL32!LeaveCriticalSection` at `0x140030d97`
- `KERNEL32!LeaveCriticalSection` at `0x140030e93`
- `KERNEL32!LeaveCriticalSection` at `0x140030f36`
- `KERNEL32!LeaveCriticalSection` at `0x14003105c`
- `KERNEL32!LeaveCriticalSection` at `0x14003106f`

## pseudocode

```c
__int64 __fastcall FaxRouteThread(struct _FAX_ROUTE **a1)
{
  int v2; // ebp
  __int64 i; // rbx
  int v4; // r14d
  struct _FAX_ROUTE *v5; // r9
  unsigned int v6; // ebx
  struct _FAX_ROUTE *v7; // r9
  int QueueEvent; // eax
  DWORD LastError; // eax
  int v11; // [rsp+20h] [rbp-88h]
  unsigned __int16 v12[8]; // [rsp+50h] [rbp-58h] BYREF
  __int128 v13; // [rsp+60h] [rbp-48h]
  __int64 v14; // [rsp+70h] [rbp-38h]

  v2 = 1;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  EnterCriticalSection(&g_CsJob);
  EnterCriticalSection(&g_CsQueue);
  LeaveCriticalSection(&g_CsQueue);
  LeaveCriticalSection(&g_CsJob);
  for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 456); i = (unsigned int)(i + 1) )
  {
    v4 = FaxRouteRetry(a1[227], (struct _ROUTE_FAILURE_INFO *)((char *)a1[229] + 96 * i));
    if ( !v4 )
    {
      EnterCriticalSection(&g_CsRouting);
      if ( FindRoutingMethodByGuid((const unsigned __int16 *)a1[229] + 48 * i) )
      {
        v5 = a1[2];
        v14 = 0;
        *(_OWORD *)v12 = 0;
        v13 = 0;
        StringCchPrintfW(v12, 0x14u, L"0x%016I64x", v5);
        FaxLog(v4 + 3, 1u, v4 + 6, 0xC0007D59, (char)v12);
      }
      LeaveCriticalSection(&g_CsRouting);
    }
    v2 &= v4;
  }
  EnterCriticalSection(&g_CsJob);
  EnterCriticalSection(&g_CsQueue);
  *((_DWORD *)a1 + 422) = 0;
  *((_WORD *)a1 + 588) = 0;
  if ( v2 )
  {
    _JOB_QUEUE::PutStatus((_JOB_QUEUE *)a1, 4u);
    DecreaseJobRefCount((struct _JOB_QUEUE *)a1, 1, 1, 0);
  }
  else
  {
    EnterCriticalSection(&g_CsConfig);
    v6 = *((_DWORD *)g_pFaxConfig + 3);
    LeaveCriticalSection(&g_CsConfig);
    if ( ++*((_DWORD *)a1 + 148) > v6 )
    {
      MarkJobAsExpired((struct _JOB_QUEUE *)a1);
      v7 = a1[2];
      v14 = 0;
      *(_OWORD *)v12 = 0;
      v13 = 0;
      StringCchPrintfW(v12, 0x14u, L"0x%016I64x", v7);
      FaxLog(3u, 1u, 3u, 0xC0007D4E, (char)v12);
    }
    else
    {
      _JOB_QUEUE::PutStatus((_JOB_QUEUE *)a1, 0x40u);
      RescheduleJobQueueEntry((struct _JOB_QUEUE *)a1);
    }
    QueueEvent = CreateQueueEvent(2u, (__int64)a1);
    if ( QueueEvent
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LOWORD(v11) = QueueEvent;
      WPP_SF_lh(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *((unsigned int *)a1 + 4),
        v11);
    }
    if ( !(unsigned int)UpdatePersistentJobStatus((struct _JOB_QUEUE *const)a1)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *((unsigned int *)a1 + 461));
    }
  }
  LeaveCriticalSection(&g_CsQueue);
  LeaveCriticalSection(&g_CsJob);
  if ( !(unsigned int)DecreaseServiceThreadsCount()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x140030cf0  mov     [rsp+arg_8], rbx
0x140030cf5  mov     [rsp+arg_10], rbp
0x140030cfa  push    rsi
0x140030cfb  push    rdi
0x140030cfc  push    r13
0x140030cfe  push    r14
0x140030d00  push    r15
0x140030d02  sub     rsp, 80h
0x140030d09  mov     rax, cs:__security_cookie
0x140030d10  xor     rax, rsp
0x140030d13  mov     [rsp+0A8h+var_30], rax
0x140030d18  mov     r15d, 1
0x140030d1e  mov     rdi, rcx
0x140030d21  mov     ebp, r15d
0x140030d24  mov     rcx, cs:WPP_GLOBAL_Control
0x140030d2b  lea     r13, WPP_GLOBAL_Control
0x140030d32  cmp     rcx, r13
0x140030d35  jz      short loc_140030D57
0x140030d37  test    byte ptr [rcx+1Ch], 4
0x140030d3b  jz      short loc_140030D57
0x140030d3d  cmp     byte ptr [rcx+19h], 5
0x140030d41  jb      short loc_140030D57
0x140030d43  mov     rcx, [rcx+10h]
0x140030d47  lea     edx, [r15+3Fh]
0x140030d4b  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140030d52  call    WPP_SF_
0x140030d57  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140030d5e  call    cs:__imp_EnterCriticalSection
0x140030d65  nop     dword ptr [rax+rax+00h]
0x140030d6a  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140030d71  call    cs:__imp_EnterCriticalSection
0x140030d78  nop     dword ptr [rax+rax+00h]
0x140030d7d  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140030d84  call    cs:__imp_LeaveCriticalSection
0x140030d8b  nop     dword ptr [rax+rax+00h]
0x140030d90  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140030d97  call    cs:__imp_LeaveCriticalSection
0x140030d9e  nop     dword ptr [rax+rax+00h]
0x140030da3  xor     ebx, ebx
0x140030da5  cmp     [rdi+720h], ebx
0x140030dab  jbe     loc_140030EB1
0x140030db1  mov     rdx, [rdi+728h]
0x140030db8  lea     rsi, [rbx+rbx*2]
0x140030dbc  mov     rcx, [rdi+718h]; struct _FAX_ROUTE *
0x140030dc3  shl     rsi, 5
0x140030dc7  add     rdx, rsi; struct _ROUTE_FAILURE_INFO *
0x140030dca  call    ?FaxRouteRetry@@YAHPEAU_FAX_ROUTE@@PEAU_ROUTE_FAILURE_INFO@@@Z; FaxRouteRetry(_FAX_ROUTE *,_ROUTE_FAILURE_INFO *)
0x140030dcf  mov     r14d, eax
0x140030dd2  test    eax, eax
0x140030dd4  jnz     loc_140030E9F
0x140030dda  lea     rcx, ?g_CsRouting@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140030de1  call    cs:__imp_EnterCriticalSection
0x140030de8  nop     dword ptr [rax+rax+00h]
0x140030ded  mov     rcx, [rdi+728h]
0x140030df4  add     rcx, rsi; unsigned __int16 *
0x140030df7  call    ?FindRoutingMethodByGuid@@YAPEAU_ROUTING_METHOD@@PEBG@Z; FindRoutingMethodByGuid(ushort const *)
0x140030dfc  mov     rsi, rax
0x140030dff  test    rax, rax
0x140030e02  jz      loc_140030E8C
0x140030e08  mov     r9, [rdi+10h]
0x140030e0c  lea     r8, a0x016i64x; "0x%016I64x"
0x140030e13  xor     eax, eax
0x140030e15  lea     rcx, [rsp+0A8h+var_58]; unsigned __int16 *
0x140030e1a  xorps   xmm0, xmm0
0x140030e1d  mov     [rsp+0A8h+var_38], rax
0x140030e22  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x140030e27  lea     edx, [rax+14h]; unsigned __int64
0x140030e2a  movups  [rsp+0A8h+var_48], xmm0
0x140030e2f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140030e34  mov     rdx, [rdi+718h]
0x140030e3b  lea     r8d, [r14+6]
0x140030e3f  mov     rax, [rsi+40h]
0x140030e43  mov     r9d, 0C0007D59h
0x140030e49  mov     rcx, [rsi+58h]
0x140030e4d  mov     [rsp+0A8h+var_60], rax
0x140030e52  add     rcx, 34h ; '4'
0x140030e56  mov     rax, [rdi+48h]
0x140030e5a  mov     [rsp+0A8h+var_68], rcx
0x140030e5f  lea     ecx, [r14+3]
0x140030e63  mov     [rsp+0A8h+var_70], rax
0x140030e68  mov     rax, [rdx+28h]
0x140030e6c  mov     [rsp+0A8h+var_78], rax
0x140030e71  mov     rax, [rdx+50h]
0x140030e75  mov     edx, r15d
0x140030e78  mov     [rsp+0A8h+var_80], rax
0x140030e7d  lea     rax, [rsp+0A8h+var_58]
0x140030e82  mov     [rsp+0A8h+var_88], rax
0x140030e87  call    FaxLog
0x140030e8c  lea     rcx, ?g_CsRouting@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140030e93  call    cs:__imp_LeaveCriticalSection
0x140030e9a  nop     dword ptr [rax+rax+00h]
0x140030e9f  and     ebp, r14d
0x140030ea2  add     ebx, r15d
0x140030ea5  cmp     ebx, [rdi+720h]
0x140030eab  jb      loc_140030DB1
0x140030eb1  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140030eb8  call    cs:__imp_EnterCriticalSection
0x140030ebf  nop     dword ptr [rax+rax+00h]
0x140030ec4  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140030ecb  call    cs:__imp_EnterCriticalSection
0x140030ed2  nop     dword ptr [rax+rax+00h]
0x140030ed7  xor     eax, eax
0x140030ed9  mov     dword ptr [rdi+698h], 0
0x140030ee3  mov     [rdi+498h], ax
0x140030eea  lea     esi, [rax+2]
0x140030eed  test    ebp, ebp
0x140030eef  jz      short loc_140030F12
0x140030ef1  lea     edx, [rax+4]; unsigned int
0x140030ef4  mov     rcx, rdi; this
0x140030ef7  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x140030efc  xor     r9d, r9d; int
0x140030eff  mov     r8d, r15d; int
0x140030f02  mov     edx, r15d; int
0x140030f05  mov     rcx, rdi; struct _JOB_QUEUE *
0x140030f08  call    ?DecreaseJobRefCount@@YAXPEAU_JOB_QUEUE@@HHH@Z; DecreaseJobRefCount(_JOB_QUEUE *,int,int,int)
0x140030f0d  jmp     loc_140031055
0x140030f12  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140030f19  call    cs:__imp_EnterCriticalSection
0x140030f20  nop     dword ptr [rax+rax+00h]
0x140030f25  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140030f2c  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140030f33  mov     ebx, [rax+0Ch]
0x140030f36  call    cs:__imp_LeaveCriticalSection
0x140030f3d  nop     dword ptr [rax+rax+00h]
0x140030f42  add     [rdi+250h], r15d
0x140030f49  mov     rcx, rdi; this
0x140030f4c  cmp     [rdi+250h], ebx
0x140030f52  ja      short loc_140030F68
0x140030f54  mov     edx, 40h ; '@'; unsigned int
0x140030f59  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x140030f5e  mov     rcx, rdi; struct _JOB_QUEUE *
0x140030f61  call    ?RescheduleJobQueueEntry@@YAXPEAU_JOB_QUEUE@@@Z; RescheduleJobQueueEntry(_JOB_QUEUE *)
0x140030f66  jmp     short loc_140030FD3
0x140030f68  call    ?MarkJobAsExpired@@YAHPEAU_JOB_QUEUE@@@Z; MarkJobAsExpired(_JOB_QUEUE *)
0x140030f6d  mov     r9, [rdi+10h]
0x140030f71  lea     r8, a0x016i64x; "0x%016I64x"
0x140030f78  xor     eax, eax
0x140030f7a  lea     rcx, [rsp+0A8h+var_58]; unsigned __int16 *
0x140030f7f  xorps   xmm0, xmm0
0x140030f82  mov     [rsp+0A8h+var_38], rax
0x140030f87  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x140030f8c  lea     edx, [rax+14h]; unsigned __int64
0x140030f8f  movups  [rsp+0A8h+var_48], xmm0
0x140030f94  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140030f99  mov     rdx, [rdi+718h]
0x140030fa0  mov     r8d, 3
0x140030fa6  mov     r9d, 0C0007D4Eh
0x140030fac  mov     ecx, r8d
0x140030faf  mov     rax, [rdx+28h]
0x140030fb3  mov     [rsp+0A8h+var_78], rax
0x140030fb8  mov     rax, [rdx+50h]
0x140030fbc  mov     edx, r15d
0x140030fbf  mov     [rsp+0A8h+var_80], rax
0x140030fc4  lea     rax, [rsp+0A8h+var_58]
0x140030fc9  mov     [rsp+0A8h+var_88], rax
0x140030fce  call    FaxLog
0x140030fd3  mov     rdx, rdi
0x140030fd6  mov     ecx, esi
0x140030fd8  call    ?CreateQueueEvent@@YAKW4FAX_ENUM_JOB_EVENT_TYPE@@QEAU_JOB_QUEUE@@@Z; CreateQueueEvent(FAX_ENUM_JOB_EVENT_TYPE,_JOB_QUEUE * const)
0x140030fdd  test    eax, eax
0x140030fdf  jz      short loc_140031017
0x140030fe1  mov     rcx, cs:WPP_GLOBAL_Control
0x140030fe8  cmp     rcx, r13
0x140030feb  jz      short loc_140031017
0x140030fed  test    byte ptr [rcx+1Ch], 4
0x140030ff1  jz      short loc_140031017
0x140030ff3  cmp     [rcx+19h], sil
0x140030ff7  jb      short loc_140031017
0x140030ff9  mov     r9d, [rdi+10h]
0x140030ffd  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140031004  mov     rcx, [rcx+10h]
0x140031008  mov     edx, 41h ; 'A'
0x14003100d  mov     word ptr [rsp+0A8h+var_88], ax
0x140031012  call    WPP_SF_lh
0x140031017  mov     rcx, rdi; struct _JOB_QUEUE *
0x14003101a  call    ?UpdatePersistentJobStatus@@YAHQEAU_JOB_QUEUE@@@Z; UpdatePersistentJobStatus(_JOB_QUEUE * const)
0x14003101f  test    eax, eax
0x140031021  jnz     short loc_140031055
0x140031023  mov     rcx, cs:WPP_GLOBAL_Control
0x14003102a  cmp     rcx, r13
0x14003102d  jz      short loc_140031055
0x14003102f  test    byte ptr [rcx+1Ch], 4
0x140031033  jz      short loc_140031055
0x140031035  cmp     [rcx+19h], sil
0x140031039  jb      short loc_140031055
0x14003103b  mov     r9d, [rdi+734h]
0x140031042  lea     edx, [rax+42h]
0x140031045  mov     rcx, [rcx+10h]
0x140031049  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140031050  call    WPP_SF_d
0x140031055  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003105c  call    cs:__imp_LeaveCriticalSection
0x140031063  nop     dword ptr [rax+rax+00h]
0x140031068  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003106f  call    cs:__imp_LeaveCriticalSection
0x140031076  nop     dword ptr [rax+rax+00h]
0x14003107b  call    ?DecreaseServiceThreadsCount@@YAHXZ; DecreaseServiceThreadsCount(void)
0x140031080  test    eax, eax
0x140031082  jnz     short loc_1400310C7
0x140031084  mov     rax, cs:WPP_GLOBAL_Control
0x14003108b  cmp     rax, r13
0x14003108e  jz      short loc_1400310C7
0x140031090  test    byte ptr [rax+1Ch], 4
0x140031094  jz      short loc_1400310C7
0x140031096  cmp     [rax+19h], sil
0x14003109a  jb      short loc_1400310C7
0x14003109c  call    cs:__imp_GetLastError
0x1400310a3  nop     dword ptr [rax+rax+00h]
0x1400310a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400310af  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400310b6  mov     edx, 43h ; 'C'
0x1400310bb  mov     r9d, eax
0x1400310be  mov     rcx, [rcx+10h]
0x1400310c2  call    WPP_SF_d
0x1400310c7  xor     eax, eax
0x1400310c9  mov     rcx, [rsp+0A8h+var_30]
0x1400310ce  xor     rcx, rsp; StackCookie
0x1400310d1  call    __security_check_cookie
0x1400310d6  lea     r11, [rsp+0A8h+var_28]
0x1400310de  mov     rbx, [r11+38h]
0x1400310e2  mov     rbp, [r11+40h]
0x1400310e6  mov     rsp, r11
0x1400310e9  pop     r15
0x1400310eb  pop     r14
0x1400310ed  pop     r13
0x1400310ef  pop     rdi
0x1400310f0  pop     rsi
0x1400310f1  retn
```
