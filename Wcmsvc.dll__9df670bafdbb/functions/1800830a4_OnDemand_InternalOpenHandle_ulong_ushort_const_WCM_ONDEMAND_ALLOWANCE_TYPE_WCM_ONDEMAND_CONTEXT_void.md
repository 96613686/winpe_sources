# OnDemand::InternalOpenHandle(ulong,ushort const *,_WCM_ONDEMAND_ALLOWANCE_TYPE,_WCM_ONDEMAND_CONTEXT *,void * *)

- ea: `0x1800830a4`
- end: `0x1800834fa`
- name: `?InternalOpenHandle@OnDemand@@AEAAKKPEBGW4_WCM_ONDEMAND_ALLOWANCE_TYPE@@PEAU_WCM_ONDEMAND_CONTEXT@@PEAPEAX@Z`
- size: `1110`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18007d28c`
- `0x180082e10`

## callees

- `0x180010080`
- `0x180011bb0`
- `0x180011c20`
- `0x1800137a0`
- `0x180015974`
- `0x180019434`
- `0x180027630`
- `0x1800791f0`
- `0x1800830a4`
- `0x180083500`
- `0x18008fd2c`
- `0x180090e24`
- `0x180092cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008317b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800832bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008343a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008317b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800832bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008343a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083489`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180083452`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180083452`

## string_xrefs

- `0x1800830f4`: `OnDemand::InternalOpenHandle`
- `0x1800832ef`: `OnDemand::InternalOpenHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OnDemand::InternalOpenHandle(
        void *a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        struct _WCM_ONDEMAND_CONTEXT *a5,
        std::_Ref_count_base **a6)
{
  OnDemand *v10; // rcx
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // r10
  struct _RTL_CRITICAL_SECTION *v14; // rcx
  int v15; // edi
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned int v20; // eax
  void *v21; // r14
  std::_Ref_count_base *v22; // rdi
  std::_Ref_count_base *v23; // rsi
  DWORD LastError; // eax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-38h] BYREF
  std::_Ref_count_base *v26[2]; // [rsp+48h] [rbp-30h] BYREF
  std::_Ref_count_base *v27[2]; // [rsp+58h] [rbp-20h] BYREF
  std::_Ref_count_base **v28; // [rsp+68h] [rbp-10h]

  v28 = a6;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      65,
      WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
      "OnDemand::InternalOpenHandle");
  }
  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, a1);
  v11 = OnDemand::OnDemandContextConsistencyCheck(v10, a5);
  v12 = v11;
  if ( v11 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 66, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids, v11);
LABEL_10:
      v13 = WPP_GLOBAL_Control;
      goto LABEL_11;
    }
    goto LABEL_11;
  }
  if ( a4 - 1 <= 1 || (v15 = 0, !a3) )
    v15 = 1;
  *(_OWORD *)v26 = 0;
  v16 = OnDemand::FindOnDemandInterfaceInfo(a1, v15);
  v12 = v16;
  if ( v16 )
  {
    if ( v16 == 1168 && !v15 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 67, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids);
        v13 = WPP_GLOBAL_Control;
      }
      v12 = 5;
      goto LABEL_29;
    }
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
      || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
    {
      goto LABEL_29;
    }
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 68, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids, v16);
LABEL_28:
    v13 = WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  v12 = OnDemand::CheckPermission((char *)v26[0] + 2616, v17, a3, a4, 0, a5);
  if ( v12 )
  {
    OnDemand::LogInterfaceInfo(v18, L"Permission check failed.", v26);
    if ( v26[1] )
      std::_Ref_count_base::_Decref(v26[1]);
    v14 = lpCriticalSection;
    if ( !lpCriticalSection )
      goto LABEL_36;
    goto LABEL_35;
  }
  *(_OWORD *)v27 = 0;
  v20 = OnDemand::AddNewOnDemandRequestInfo((_DWORD)a1, a2, a3, (unsigned int)v26, (__int64)v27);
  v12 = v20;
  if ( !v20 )
  {
    v21 = 0;
    v22 = v26[0];
    v23 = v27[0];
    if ( v27[0] && (Microsoft_Windows_WcmsvcEnableBits & 2) != 0 )
      McTemplateU0zqqzzq_EtwEventWriteTransfer(
        LODWORD(v26[0]) + 532,
        (unsigned int)OnDemandRequestOpen,
        v27[0],
        *((_DWORD *)v27[0] + 49),
        *(_DWORD *)v26[0],
        (__int64)v26[0] + 532,
        (__int64)v26[0] + 20,
        0);
    if ( *((_QWORD *)v22 + 394) )
    {
      v21 = (void *)*((_QWORD *)v22 + 394);
      *((_QWORD *)v22 + 394) = 0;
      *((_DWORD *)v22 + 787) = -1;
    }
    *v28 = v23;
    if ( v27[1] )
      std::_Ref_count_base::_Decref(v27[1]);
    if ( v26[1] )
      std::_Ref_count_base::_Decref(v26[1]);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    if ( !v21 )
      goto LABEL_36;
    if ( DeleteTimerQueueTimer(0, v21, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v12;
      if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 4u || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_37;
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 71, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids);
      goto LABEL_36;
    }
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v12;
    if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 70, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids, LastError);
      goto LABEL_36;
    }
    goto LABEL_37;
  }
  v13 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 69, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids, v20);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v27[1] )
  {
    std::_Ref_count_base::_Decref(v27[1]);
    goto LABEL_28;
  }
LABEL_29:
  if ( v26[1] )
  {
    std::_Ref_count_base::_Decref(v26[1]);
    goto LABEL_10;
  }
LABEL_11:
  v14 = lpCriticalSection;
  if ( lpCriticalSection )
  {
LABEL_35:
    LeaveCriticalSection(v14);
LABEL_36:
    v13 = WPP_GLOBAL_Control;
  }
LABEL_37:
  if ( (_UNKNOWN *)v13 != &WPP_GLOBAL_Control && *(_BYTE *)(v13 + 25) >= 5u && (*(_BYTE *)(v13 + 28) & 1) != 0 )
    WPP_SF_sL(
      *(_QWORD *)(v13 + 16),
      72,
      (unsigned int)WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
      (unsigned int)"OnDemand::InternalOpenHandle",
      v12);
  return v12;
}

```

## disassembly

```asm
0x1800830a4  push    rbp
0x1800830a6  push    rbx
0x1800830a7  push    rsi
0x1800830a8  push    rdi
0x1800830a9  push    r12
0x1800830ab  push    r13
0x1800830ad  push    r14
0x1800830af  push    r15
0x1800830b1  mov     rbp, rsp
0x1800830b4  sub     rsp, 78h
0x1800830b8  mov     r15d, r9d
0x1800830bb  mov     r14, r8
0x1800830be  mov     r13d, edx
0x1800830c1  mov     r12, rcx
0x1800830c4  mov     rsi, [rbp+arg_20]
0x1800830c8  mov     rax, [rbp+arg_28]
0x1800830cc  mov     [rbp+var_10], rax
0x1800830d0  lea     rax, WPP_GLOBAL_Control
0x1800830d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800830de  cmp     rcx, rax
0x1800830e1  jz      short loc_18008310B
0x1800830e3  cmp     byte ptr [rcx+19h], 5
0x1800830e7  jb      short loc_18008310B
0x1800830e9  test    byte ptr [rcx+1Ch], 1
0x1800830ed  jz      short loc_18008310B
0x1800830ef  mov     edx, 41h ; 'A'
0x1800830f4  lea     r9, aOndemandIntern_14; "OnDemand::InternalOpenHandle"
0x1800830fb  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x180083102  mov     rcx, [rcx+10h]
0x180083106  call    WPP_SF_s
0x18008310b  mov     [rbp+lpCriticalSection], 0
0x180083113  mov     rdx, r12
0x180083116  lea     rcx, [rbp+lpCriticalSection]
0x18008311a  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18008311f  nop
0x180083120  mov     rdx, rsi; struct _WCM_ONDEMAND_CONTEXT *
0x180083123  call    ?OnDemandContextConsistencyCheck@OnDemand@@AEAAKPEAU_WCM_ONDEMAND_CONTEXT@@@Z; OnDemand::OnDemandContextConsistencyCheck(_WCM_ONDEMAND_CONTEXT *)
0x180083128  mov     ebx, eax
0x18008312a  test    eax, eax
0x18008312c  jz      short loc_180083186
0x18008312e  mov     r10, cs:WPP_GLOBAL_Control
0x180083135  lea     rdi, WPP_GLOBAL_Control
0x18008313c  cmp     r10, rdi
0x18008313f  jz      short loc_18008316E
0x180083141  cmp     byte ptr [r10+19h], 1
0x180083146  jb      short loc_18008316E
0x180083148  test    byte ptr [r10+1Ch], 1
0x18008314d  jz      short loc_18008316E
0x18008314f  mov     edx, 42h ; 'B'
0x180083154  mov     r9d, eax
0x180083157  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x18008315e  mov     rcx, [r10+10h]
0x180083162  call    WPP_SF_d
0x180083167  mov     r10, cs:WPP_GLOBAL_Control
0x18008316e  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180083172  test    rcx, rcx
0x180083175  jz      loc_1800832D3
0x18008317b  call    cs:__imp_LeaveCriticalSection
0x180083181  jmp     loc_1800832CC
0x180083186  lea     eax, [r15-1]
0x18008318a  cmp     eax, 1
0x18008318d  jbe     short loc_180083196
0x18008318f  xor     edi, edi
0x180083191  test    r14, r14
0x180083194  jnz     short loc_18008319B
0x180083196  mov     edi, 1
0x18008319b  xorps   xmm1, xmm1
0x18008319e  movdqu  xmmword ptr [rbp+var_30], xmm1
0x1800831a3  mov     [rsp+78h+var_58], edi; int
0x1800831a7  lea     r9, [rbp+var_30]
0x1800831ab  mov     r8, rsi
0x1800831ae  mov     edx, [rsi]
0x1800831b0  mov     rcx, r12; CallerContext
0x1800831b3  call    ?FindOnDemandInterfaceInfo@OnDemand@@AEAAKW4_WCM_ONDEMAND_TYPE@@PEAU_WCM_ONDEMAND_CONTEXT@@AEAV?$shared_ptr@UOnDemandInterfaceInfo@OnDemand@@@std@@H@Z; OnDemand::FindOnDemandInterfaceInfo(_WCM_ONDEMAND_TYPE,_WCM_ONDEMAND_CONTEXT *,std::shared_ptr<OnDemand::OnDemandInterfaceInfo> &,int)
0x1800831b8  mov     ebx, eax
0x1800831ba  test    eax, eax
0x1800831bc  jz      loc_180083268
0x1800831c2  cmp     eax, 490h
0x1800831c7  jnz     short loc_180083211
0x1800831c9  test    edi, edi
0x1800831cb  jnz     short loc_180083211
0x1800831cd  mov     r10, cs:WPP_GLOBAL_Control
0x1800831d4  lea     rdi, WPP_GLOBAL_Control
0x1800831db  cmp     r10, rdi
0x1800831de  jz      short loc_18008320A
0x1800831e0  cmp     byte ptr [r10+19h], 1
0x1800831e5  jb      short loc_18008320A
0x1800831e7  test    byte ptr [r10+1Ch], 1
0x1800831ec  jz      short loc_18008320A
0x1800831ee  mov     edx, 43h ; 'C'
0x1800831f3  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x1800831fa  mov     rcx, [r10+10h]
0x1800831fe  call    WPP_SF_
0x180083203  mov     r10, cs:WPP_GLOBAL_Control
0x18008320a  mov     ebx, 5
0x18008320f  jmp     short loc_180083251
0x180083211  mov     r10, cs:WPP_GLOBAL_Control
0x180083218  lea     rdi, WPP_GLOBAL_Control
0x18008321f  cmp     r10, rdi
0x180083222  jz      short loc_180083251
0x180083224  cmp     byte ptr [r10+19h], 1
0x180083229  jb      short loc_180083251
0x18008322b  test    byte ptr [r10+1Ch], 1
0x180083230  jz      short loc_180083251
0x180083232  mov     edx, 44h ; 'D'
0x180083237  mov     r9d, eax
0x18008323a  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x180083241  mov     rcx, [r10+10h]
0x180083245  call    WPP_SF_d
0x18008324a  mov     r10, cs:WPP_GLOBAL_Control
0x180083251  mov     rcx, [rbp+var_30+8]; this
0x180083255  test    rcx, rcx
0x180083258  jz      loc_18008316E
0x18008325e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180083263  jmp     loc_180083167
0x180083268  mov     rcx, [rbp+var_30]
0x18008326c  add     rcx, 0A38h
0x180083273  mov     [rsp+78h+var_50], rsi
0x180083278  mov     qword ptr [rsp+78h+var_58], 0
0x180083281  mov     r9d, r15d
0x180083284  mov     r8, r14
0x180083287  call    ?CheckPermission@OnDemand@@SAKAEBU_GUID@@W4_WCM_MEDIA_TYPE@@PEBGW4_WCM_ONDEMAND_ALLOWANCE_TYPE@@2PEAU_WCM_ONDEMAND_CONTEXT@@@Z; OnDemand::CheckPermission(_GUID const &,_WCM_MEDIA_TYPE,ushort const *,_WCM_ONDEMAND_ALLOWANCE_TYPE,ushort const *,_WCM_ONDEMAND_CONTEXT *)
0x18008328c  mov     ebx, eax
0x18008328e  test    eax, eax
0x180083290  jz      loc_180083319
0x180083296  lea     r8, [rbp+var_30]
0x18008329a  lea     rdx, aPermissionChec; "Permission check failed."
0x1800832a1  call    ?LogInterfaceInfo@OnDemand@@AEAAXPEBGAEBV?$shared_ptr@UOnDemandInterfaceInfo@OnDemand@@@std@@@Z; OnDemand::LogInterfaceInfo(ushort const *,std::shared_ptr<OnDemand::OnDemandInterfaceInfo> const &)
0x1800832a6  nop
0x1800832a7  mov     rcx, [rbp+var_30+8]; this
0x1800832ab  test    rcx, rcx
0x1800832ae  jz      short loc_1800832B6
0x1800832b0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800832b5  nop
0x1800832b6  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800832ba  test    rcx, rcx
0x1800832bd  jz      short loc_1800832C5
0x1800832bf  call    cs:__imp_LeaveCriticalSection
0x1800832c5  lea     rdi, WPP_GLOBAL_Control
0x1800832cc  mov     r10, cs:WPP_GLOBAL_Control
0x1800832d3  cmp     r10, rdi
0x1800832d6  jz      short loc_180083306
0x1800832d8  cmp     byte ptr [r10+19h], 5
0x1800832dd  jb      short loc_180083306
0x1800832df  test    byte ptr [r10+1Ch], 1
0x1800832e4  jz      short loc_180083306
0x1800832e6  mov     edx, 48h ; 'H'
0x1800832eb  mov     [rsp+78h+var_58], ebx
0x1800832ef  lea     r9, aOndemandIntern_14; "OnDemand::InternalOpenHandle"
0x1800832f6  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x1800832fd  mov     rcx, [r10+10h]
0x180083301  call    WPP_SF_sL
0x180083306  mov     eax, ebx
0x180083308  add     rsp, 78h
0x18008330c  pop     r15
0x18008330e  pop     r14
0x180083310  pop     r13
0x180083312  pop     r12
0x180083314  pop     rdi
0x180083315  pop     rsi
0x180083316  pop     rbx
0x180083317  pop     rbp
0x180083318  retn
0x180083319  xorps   xmm1, xmm1
0x18008331c  movdqu  xmmword ptr [rbp+var_20], xmm1
0x180083321  lea     rax, [rbp+var_20]
0x180083325  mov     qword ptr [rsp+78h+var_58], rax
0x18008332a  lea     r9, [rbp+var_30]
0x18008332e  mov     r8, r14
0x180083331  mov     edx, r13d
0x180083334  mov     rcx, r12
0x180083337  call    ?AddNewOnDemandRequestInfo@OnDemand@@AEAAKKPEBGAEAV?$shared_ptr@UOnDemandInterfaceInfo@OnDemand@@@std@@AEAV?$shared_ptr@UOnDemandRequestInfo@OnDemand@@@3@@Z; OnDemand::AddNewOnDemandRequestInfo(ulong,ushort const *,std::shared_ptr<OnDemand::OnDemandInterfaceInfo> &,std::shared_ptr<OnDemand::OnDemandRequestInfo> &)
0x18008333c  mov     ebx, eax
0x18008333e  test    eax, eax
0x180083340  jz      short loc_180083399
0x180083342  mov     r10, cs:WPP_GLOBAL_Control
0x180083349  lea     rdi, WPP_GLOBAL_Control
0x180083350  cmp     r10, rdi
0x180083353  jz      short loc_180083382
0x180083355  cmp     byte ptr [r10+19h], 1
0x18008335a  jb      short loc_180083382
0x18008335c  test    byte ptr [r10+1Ch], 1
0x180083361  jz      short loc_180083382
0x180083363  mov     edx, 45h ; 'E'
0x180083368  mov     r9d, eax
0x18008336b  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x180083372  mov     rcx, [r10+10h]
0x180083376  call    WPP_SF_d
0x18008337b  mov     r10, cs:WPP_GLOBAL_Control
0x180083382  mov     rcx, [rbp+var_20+8]; this
0x180083386  test    rcx, rcx
0x180083389  jz      loc_180083251
0x18008338f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180083394  jmp     loc_18008324A
0x180083399  xor     r14d, r14d
0x18008339c  mov     rdi, [rbp+var_30]
0x1800833a0  mov     rsi, [rbp+var_20]
0x1800833a4  test    rsi, rsi
0x1800833a7  jz      short loc_1800833E8
0x1800833a9  test    cs:Microsoft_Windows_WcmsvcEnableBits, 2
0x1800833b0  jz      short loc_1800833E8
0x1800833b2  lea     rax, [rdi+14h]
0x1800833b6  lea     rcx, [rdi+214h]
0x1800833bd  mov     [rsp+78h+var_40], r14d
0x1800833c2  mov     [rsp+78h+var_48], rax
0x1800833c7  mov     [rsp+78h+var_50], rcx
0x1800833cc  mov     eax, [rdi]
0x1800833ce  mov     [rsp+78h+var_58], eax
0x1800833d2  mov     r9d, [rsi+0C4h]
0x1800833d9  mov     r8, rsi
0x1800833dc  lea     rdx, OnDemandRequestOpen
0x1800833e3  call    McTemplateU0zqqzzq_EtwEventWriteTransfer
0x1800833e8  mov     rax, [rdi+0C50h]
0x1800833ef  test    rax, rax
0x1800833f2  jz      short loc_18008340C
0x1800833f4  mov     r14, rax
0x1800833f7  mov     qword ptr [rdi+0C50h], 0
0x180083402  mov     dword ptr [rdi+0C4Ch], 0FFFFFFFFh
0x18008340c  mov     rax, [rbp+var_10]
0x180083410  mov     [rax], rsi
0x180083413  mov     rcx, [rbp+var_20+8]; this
0x180083417  test    rcx, rcx
0x18008341a  jz      short loc_180083422
0x18008341c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180083421  nop
0x180083422  mov     rcx, [rbp+var_30+8]; this
0x180083426  test    rcx, rcx
0x180083429  jz      short loc_180083431
0x18008342b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180083430  nop
0x180083431  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180083435  test    rcx, rcx
0x180083438  jz      short loc_180083440
0x18008343a  call    cs:__imp_LeaveCriticalSection
0x180083440  test    r14, r14
0x180083443  jz      loc_1800832C5
0x180083449  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18008344d  mov     rdx, r14; Timer
0x180083450  xor     ecx, ecx; TimerQueue
0x180083452  call    cs:__imp_DeleteTimerQueueTimer
0x180083458  test    eax, eax
0x18008345a  jnz     short loc_1800834B3
0x18008345c  mov     r10, cs:WPP_GLOBAL_Control
0x180083463  lea     rdi, WPP_GLOBAL_Control
0x18008346a  cmp     r10, rdi
0x18008346d  jz      loc_180083306
0x180083473  cmp     byte ptr [r10+19h], 3
0x180083478  jb      loc_1800832D3
0x18008347e  test    byte ptr [r10+1Ch], 1
0x180083483  jz      loc_1800832D3
0x180083489  call    cs:__imp_GetLastError
0x18008348f  mov     edx, 46h ; 'F'
0x180083494  mov     r9d, eax
0x180083497  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x18008349e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800834a5  mov     rcx, [rcx+10h]
0x1800834a9  call    WPP_SF_d
0x1800834ae  jmp     loc_1800832CC
0x1800834b3  mov     r10, cs:WPP_GLOBAL_Control
0x1800834ba  lea     rdi, WPP_GLOBAL_Control
0x1800834c1  cmp     r10, rdi
0x1800834c4  jz      loc_180083306
0x1800834ca  cmp     byte ptr [r10+19h], 4
0x1800834cf  jb      loc_1800832D3
0x1800834d5  test    byte ptr [r10+1Ch], 1
0x1800834da  jz      loc_1800832D3
0x1800834e0  mov     edx, 47h ; 'G'
0x1800834e5  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x1800834ec  mov     rcx, [r10+10h]
0x1800834f0  call    WPP_SF_
0x1800834f5  jmp     loc_1800832CC
```
