# FaxRouteThread(_JOB_QUEUE *)

- ea: `0x14002f580`
- end: `0x14002f934`
- name: `?FaxRouteThread@@YAKPEAU_JOB_QUEUE@@@Z`
- size: `948`
- prototype: `__int64 __fastcall(struct _FAX_ROUTE **)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140022a4c`
- `0x14002f580`
- `0x1400328e8`
- `0x140037b14`
- `0x14003a3d8`
- `0x14003bc8c`
- `0x14003e7ac`
- `0x140043134`
- `0x1400433e0`
- `0x14004eedc`
- `0x140055acc`
- `0x140065df8`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002f8e4`
- `KERNEL32!GetLastError` at `0x14002f8e4`
- `KERNEL32!EnterCriticalSection` at `0x14002f5ee`
- `KERNEL32!EnterCriticalSection` at `0x14002f5fb`
- `KERNEL32!EnterCriticalSection` at `0x14002f659`
- `KERNEL32!EnterCriticalSection` at `0x14002f724`
- `KERNEL32!EnterCriticalSection` at `0x14002f731`
- `KERNEL32!EnterCriticalSection` at `0x14002f779`
- `KERNEL32!EnterCriticalSection` at `0x14002f5ee`
- `KERNEL32!EnterCriticalSection` at `0x14002f5fb`
- `KERNEL32!EnterCriticalSection` at `0x14002f659`
- `KERNEL32!EnterCriticalSection` at `0x14002f724`
- `KERNEL32!EnterCriticalSection` at `0x14002f731`
- `KERNEL32!EnterCriticalSection` at `0x14002f779`
- `KERNEL32!LeaveCriticalSection` at `0x14002f608`
- `KERNEL32!LeaveCriticalSection` at `0x14002f615`
- `KERNEL32!LeaveCriticalSection` at `0x14002f705`
- `KERNEL32!LeaveCriticalSection` at `0x14002f790`
- `KERNEL32!LeaveCriticalSection` at `0x14002f8b0`
- `KERNEL32!LeaveCriticalSection` at `0x14002f8bd`
- `KERNEL32!LeaveCriticalSection` at `0x14002f608`
- `KERNEL32!LeaveCriticalSection` at `0x14002f615`
- `KERNEL32!LeaveCriticalSection` at `0x14002f705`
- `KERNEL32!LeaveCriticalSection` at `0x14002f790`
- `KERNEL32!LeaveCriticalSection` at `0x14002f8b0`
- `KERNEL32!LeaveCriticalSection` at `0x14002f8bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
        FaxLog((unsigned int)(v4 + 3), 1, (unsigned int)(v4 + 6), 3221257561LL, v12);
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
      FaxLog(3, 1, 3, 3221257550LL, v12);
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
0x14002f580  mov     [rsp+arg_8], rbx
0x14002f585  mov     [rsp+arg_10], rbp
0x14002f58a  push    rsi
0x14002f58b  push    rdi
0x14002f58c  push    r13
0x14002f58e  push    r14
0x14002f590  push    r15
0x14002f592  sub     rsp, 80h
0x14002f599  mov     rax, cs:__security_cookie
0x14002f5a0  xor     rax, rsp
0x14002f5a3  mov     [rsp+0A8h+var_30], rax
0x14002f5a8  mov     r15d, 1
0x14002f5ae  mov     rdi, rcx
0x14002f5b1  mov     ebp, r15d
0x14002f5b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f5bb  lea     r13, WPP_GLOBAL_Control
0x14002f5c2  cmp     rcx, r13
0x14002f5c5  jz      short loc_14002F5E7
0x14002f5c7  test    byte ptr [rcx+1Ch], 4
0x14002f5cb  jz      short loc_14002F5E7
0x14002f5cd  cmp     byte ptr [rcx+19h], 5
0x14002f5d1  jb      short loc_14002F5E7
0x14002f5d3  mov     rcx, [rcx+10h]
0x14002f5d7  lea     edx, [r15+3Fh]
0x14002f5db  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f5e2  call    WPP_SF_
0x14002f5e7  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002f5ee  call    cs:__imp_EnterCriticalSection
0x14002f5f4  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002f5fb  call    cs:__imp_EnterCriticalSection
0x14002f601  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002f608  call    cs:__imp_LeaveCriticalSection
0x14002f60e  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002f615  call    cs:__imp_LeaveCriticalSection
0x14002f61b  xor     ebx, ebx
0x14002f61d  cmp     [rdi+720h], ebx
0x14002f623  jbe     loc_14002F71D
0x14002f629  mov     rdx, [rdi+728h]
0x14002f630  lea     rsi, [rbx+rbx*2]
0x14002f634  mov     rcx, [rdi+718h]; struct _FAX_ROUTE *
0x14002f63b  shl     rsi, 5
0x14002f63f  add     rdx, rsi; struct _ROUTE_FAILURE_INFO *
0x14002f642  call    ?FaxRouteRetry@@YAHPEAU_FAX_ROUTE@@PEAU_ROUTE_FAILURE_INFO@@@Z; FaxRouteRetry(_FAX_ROUTE *,_ROUTE_FAILURE_INFO *)
0x14002f647  mov     r14d, eax
0x14002f64a  test    eax, eax
0x14002f64c  jnz     loc_14002F70B
0x14002f652  lea     rcx, ?g_CsRouting@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002f659  call    cs:__imp_EnterCriticalSection
0x14002f65f  mov     rcx, [rdi+728h]
0x14002f666  add     rcx, rsi; unsigned __int16 *
0x14002f669  call    ?FindRoutingMethodByGuid@@YAPEAU_ROUTING_METHOD@@PEBG@Z; FindRoutingMethodByGuid(ushort const *)
0x14002f66e  mov     rsi, rax
0x14002f671  test    rax, rax
0x14002f674  jz      loc_14002F6FE
0x14002f67a  mov     r9, [rdi+10h]
0x14002f67e  lea     r8, a0x016i64x; "0x%016I64x"
0x14002f685  xor     eax, eax
0x14002f687  lea     rcx, [rsp+0A8h+var_58]; unsigned __int16 *
0x14002f68c  xorps   xmm0, xmm0
0x14002f68f  mov     [rsp+0A8h+var_38], rax
0x14002f694  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x14002f699  lea     edx, [rax+14h]; unsigned __int64
0x14002f69c  movups  [rsp+0A8h+var_48], xmm0
0x14002f6a1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002f6a6  mov     rdx, [rdi+718h]
0x14002f6ad  lea     r8d, [r14+6]
0x14002f6b1  mov     rax, [rsi+40h]
0x14002f6b5  mov     r9d, 0C0007D59h
0x14002f6bb  mov     rcx, [rsi+58h]
0x14002f6bf  mov     [rsp+0A8h+var_60], rax
0x14002f6c4  add     rcx, 34h ; '4'
0x14002f6c8  mov     rax, [rdi+48h]
0x14002f6cc  mov     [rsp+0A8h+var_68], rcx
0x14002f6d1  lea     ecx, [r14+3]
0x14002f6d5  mov     [rsp+0A8h+var_70], rax
0x14002f6da  mov     rax, [rdx+28h]
0x14002f6de  mov     [rsp+0A8h+var_78], rax
0x14002f6e3  mov     rax, [rdx+50h]
0x14002f6e7  mov     edx, r15d
0x14002f6ea  mov     [rsp+0A8h+var_80], rax
0x14002f6ef  lea     rax, [rsp+0A8h+var_58]
0x14002f6f4  mov     [rsp+0A8h+var_88], rax
0x14002f6f9  call    FaxLog
0x14002f6fe  lea     rcx, ?g_CsRouting@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002f705  call    cs:__imp_LeaveCriticalSection
0x14002f70b  and     ebp, r14d
0x14002f70e  add     ebx, r15d
0x14002f711  cmp     ebx, [rdi+720h]
0x14002f717  jb      loc_14002F629
0x14002f71d  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002f724  call    cs:__imp_EnterCriticalSection
0x14002f72a  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002f731  call    cs:__imp_EnterCriticalSection
0x14002f737  xor     eax, eax
0x14002f739  mov     dword ptr [rdi+698h], 0
0x14002f743  mov     [rdi+498h], ax
0x14002f74a  lea     esi, [rax+2]
0x14002f74d  test    ebp, ebp
0x14002f74f  jz      short loc_14002F772
0x14002f751  lea     edx, [rax+4]; unsigned int
0x14002f754  mov     rcx, rdi; this
0x14002f757  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x14002f75c  xor     r9d, r9d; int
0x14002f75f  mov     r8d, r15d; int
0x14002f762  mov     edx, r15d; int
0x14002f765  mov     rcx, rdi; struct _JOB_QUEUE *
0x14002f768  call    ?DecreaseJobRefCount@@YAXPEAU_JOB_QUEUE@@HHH@Z; DecreaseJobRefCount(_JOB_QUEUE *,int,int,int)
0x14002f76d  jmp     loc_14002F8A9
0x14002f772  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002f779  call    cs:__imp_EnterCriticalSection
0x14002f77f  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14002f786  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002f78d  mov     ebx, [rax+0Ch]
0x14002f790  call    cs:__imp_LeaveCriticalSection
0x14002f796  add     [rdi+250h], r15d
0x14002f79d  mov     rcx, rdi; this
0x14002f7a0  cmp     [rdi+250h], ebx
0x14002f7a6  ja      short loc_14002F7BC
0x14002f7a8  mov     edx, 40h ; '@'; unsigned int
0x14002f7ad  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x14002f7b2  mov     rcx, rdi; struct _JOB_QUEUE *
0x14002f7b5  call    ?RescheduleJobQueueEntry@@YAXPEAU_JOB_QUEUE@@@Z; RescheduleJobQueueEntry(_JOB_QUEUE *)
0x14002f7ba  jmp     short loc_14002F827
0x14002f7bc  call    ?MarkJobAsExpired@@YAHPEAU_JOB_QUEUE@@@Z; MarkJobAsExpired(_JOB_QUEUE *)
0x14002f7c1  mov     r9, [rdi+10h]
0x14002f7c5  lea     r8, a0x016i64x; "0x%016I64x"
0x14002f7cc  xor     eax, eax
0x14002f7ce  lea     rcx, [rsp+0A8h+var_58]; unsigned __int16 *
0x14002f7d3  xorps   xmm0, xmm0
0x14002f7d6  mov     [rsp+0A8h+var_38], rax
0x14002f7db  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x14002f7e0  lea     edx, [rax+14h]; unsigned __int64
0x14002f7e3  movups  [rsp+0A8h+var_48], xmm0
0x14002f7e8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002f7ed  mov     rdx, [rdi+718h]
0x14002f7f4  mov     r8d, 3
0x14002f7fa  mov     r9d, 0C0007D4Eh
0x14002f800  mov     ecx, r8d
0x14002f803  mov     rax, [rdx+28h]
0x14002f807  mov     [rsp+0A8h+var_78], rax
0x14002f80c  mov     rax, [rdx+50h]
0x14002f810  mov     edx, r15d
0x14002f813  mov     [rsp+0A8h+var_80], rax
0x14002f818  lea     rax, [rsp+0A8h+var_58]
0x14002f81d  mov     [rsp+0A8h+var_88], rax
0x14002f822  call    FaxLog
0x14002f827  mov     rdx, rdi
0x14002f82a  mov     ecx, esi
0x14002f82c  call    ?CreateQueueEvent@@YAKW4FAX_ENUM_JOB_EVENT_TYPE@@QEAU_JOB_QUEUE@@@Z; CreateQueueEvent(FAX_ENUM_JOB_EVENT_TYPE,_JOB_QUEUE * const)
0x14002f831  test    eax, eax
0x14002f833  jz      short loc_14002F86B
0x14002f835  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f83c  cmp     rcx, r13
0x14002f83f  jz      short loc_14002F86B
0x14002f841  test    byte ptr [rcx+1Ch], 4
0x14002f845  jz      short loc_14002F86B
0x14002f847  cmp     [rcx+19h], sil
0x14002f84b  jb      short loc_14002F86B
0x14002f84d  mov     r9d, [rdi+10h]
0x14002f851  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f858  mov     rcx, [rcx+10h]
0x14002f85c  mov     edx, 41h ; 'A'
0x14002f861  mov     word ptr [rsp+0A8h+var_88], ax
0x14002f866  call    WPP_SF_lh
0x14002f86b  mov     rcx, rdi; struct _JOB_QUEUE *
0x14002f86e  call    ?UpdatePersistentJobStatus@@YAHQEAU_JOB_QUEUE@@@Z; UpdatePersistentJobStatus(_JOB_QUEUE * const)
0x14002f873  test    eax, eax
0x14002f875  jnz     short loc_14002F8A9
0x14002f877  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f87e  cmp     rcx, r13
0x14002f881  jz      short loc_14002F8A9
0x14002f883  test    byte ptr [rcx+1Ch], 4
0x14002f887  jz      short loc_14002F8A9
0x14002f889  cmp     [rcx+19h], sil
0x14002f88d  jb      short loc_14002F8A9
0x14002f88f  mov     r9d, [rdi+734h]
0x14002f896  lea     edx, [rax+42h]
0x14002f899  mov     rcx, [rcx+10h]
0x14002f89d  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f8a4  call    WPP_SF_d
0x14002f8a9  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002f8b0  call    cs:__imp_LeaveCriticalSection
0x14002f8b6  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002f8bd  call    cs:__imp_LeaveCriticalSection
0x14002f8c3  call    ?DecreaseServiceThreadsCount@@YAHXZ; DecreaseServiceThreadsCount(void)
0x14002f8c8  test    eax, eax
0x14002f8ca  jnz     short loc_14002F909
0x14002f8cc  mov     rax, cs:WPP_GLOBAL_Control
0x14002f8d3  cmp     rax, r13
0x14002f8d6  jz      short loc_14002F909
0x14002f8d8  test    byte ptr [rax+1Ch], 4
0x14002f8dc  jz      short loc_14002F909
0x14002f8de  cmp     [rax+19h], sil
0x14002f8e2  jb      short loc_14002F909
0x14002f8e4  call    cs:__imp_GetLastError
0x14002f8ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f8f1  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f8f8  mov     edx, 43h ; 'C'
0x14002f8fd  mov     r9d, eax
0x14002f900  mov     rcx, [rcx+10h]
0x14002f904  call    WPP_SF_d
0x14002f909  xor     eax, eax
0x14002f90b  mov     rcx, [rsp+0A8h+var_30]
0x14002f910  xor     rcx, rsp; StackCookie
0x14002f913  call    __security_check_cookie
0x14002f918  lea     r11, [rsp+0A8h+var_28]
0x14002f920  mov     rbx, [r11+38h]
0x14002f924  mov     rbp, [r11+40h]
0x14002f928  mov     rsp, r11
0x14002f92b  pop     r15
0x14002f92d  pop     r14
0x14002f92f  pop     r13
0x14002f931  pop     rdi
0x14002f932  pop     rsi
0x14002f933  retn
```
