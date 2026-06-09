# FullDuplexChannel::OnEventTerminated(bool,IChannelObserver::Event,ulong,ulong)

- ea: `0x18002d5cc`
- end: `0x18002dc1a`
- name: `?OnEventTerminated@FullDuplexChannel@@IEAAX_NW4Event@IChannelObserver@@KK@Z`
- size: `1614`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x18002cf80`
- `0x1800d9650`

## callees

- `0x180005d10`
- `0x18002c580`
- `0x18002d5cc`
- `0x18002dc20`
- `0x18002dd20`
- `0x18011349c`
- `0x18011a6d4`
- `0x180123660`
- `0x18012c430`
- `0x18012c548`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d700`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d72e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d761`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d700`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d72e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d761`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d621`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d621`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d6c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d6c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d9bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d9bf`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002d6ad`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002d6ad`

## string_xrefs

- `0x18002d71d`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x18002d750`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall FullDuplexChannel::OnEventTerminated(
        __int64 a1,
        unsigned __int8 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  int v7; // r12d
  unsigned int v9; // esi
  __int64 v10; // r15
  DWORD *v11; // r14
  DWORD v12; // ecx
  __int64 v13; // rdx
  PVOID *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // [rsp+50h] [rbp-28h] BYREF
  int v19; // [rsp+58h] [rbp-20h]
  __int64 v20; // [rsp+60h] [rbp-18h]
  int v21; // [rsp+68h] [rbp-10h]
  __int64 v22; // [rsp+C0h] [rbp+48h] BYREF

  v7 = a2;
  v9 = 0;
  v18 = 0;
  v22 = 0;
  v10 = *(_QWORD *)(a1 + 8);
  if ( !v10 )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\fullduplexchannel.cpp", 381, L"381", 0x54Fu, 0);
  v11 = (DWORD *)(a1 + 808);
  v20 = a1 + 808;
  v21 = 0;
  v12 = *(_DWORD *)(a1 + 808);
  if ( v12 )
  {
    SetLastError(v12);
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
      59,
      L"59",
      0x54Fu,
      0);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 816));
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qddddq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      *(unsigned __int8 *)(a1 + 797),
      a1,
      *(unsigned __int8 *)(a1 + 797),
      a3,
      a4,
      v7,
      *(_QWORD *)(a1 + 112));
  if ( *(_BYTE *)(a1 + 797) )
  {
    if ( a3 == 1 )
    {
      if ( (_BYTE)v7 )
        v17 = *(_QWORD *)(a1 + 112);
      else
        v17 = *(_QWORD *)(a1 + 24);
      v18 = v17;
    }
    a3 = *(_DWORD *)(a1 + 1084);
    a4 = *(_DWORD *)(a1 + 1088);
    v9 = *(_DWORD *)(a1 + 1092);
    FullDuplexChannel::CheckWaitForCancelToBeIssued((FullDuplexChannel *)a1);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_qddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        &WPP_c09890fbe2553e46dab0283952d3a950_Traceguids,
        a1,
        *(_DWORD *)(a1 + 1084),
        *(_DWORD *)(a1 + 1088),
        *(_DWORD *)(a1 + 1092));
LABEL_69:
      v14 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_9;
    }
    goto LABEL_9;
  }
  *(_BYTE *)(a1 + 797) = 1;
  if ( a3 != 1 )
  {
    if ( !(_BYTE)v7 )
      goto LABEL_25;
    if ( !a3 && *(_BYTE *)(a1 + 799) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_c09890fbe2553e46dab0283952d3a950_Traceguids, a1);
      a3 = 2;
      a4 = 995;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(a1 + 120) + 72LL))(a1 + 120, 995);
      goto LABEL_41;
    }
LABEL_40:
    v9 = a5;
LABEL_41:
    if ( !*(_QWORD *)(a1 + 24) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\fullduplexchannel.cpp", 420, L"420", 0x54Fu, 0);
    v16 = *(_QWORD *)(a1 + 24);
    goto LABEL_26;
  }
  if ( *(_BYTE *)(a1 + 800) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\fullduplexchannel.cpp", 396, L"396", 0x54Fu, 0);
  *(_BYTE *)(a1 + 800) = 1;
  if ( (_BYTE)v7 )
  {
    *(_BYTE *)(a1 + 801) = 1;
    goto LABEL_40;
  }
LABEL_25:
  v16 = *(_QWORD *)(a1 + 112);
  v9 = a5;
  if ( v16 )
  {
LABEL_26:
    v22 = v16;
    goto LABEL_27;
  }
  v16 = v22;
LABEL_27:
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        &WPP_c09890fbe2553e46dab0283952d3a950_Traceguids,
        a1,
        a3,
        a4,
        v9);
    *(_DWORD *)(a1 + 1084) = a3;
    *(_DWORD *)(a1 + 1088) = a4;
    *(_DWORD *)(a1 + 1092) = v9;
    *(_DWORD *)(a1 + 1096) = v7;
    if ( *(_QWORD *)(a1 + 1072) )
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_c09890fbe2553e46dab0283952d3a950_Traceguids, a1);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      v22 = 0;
    }
    else
    {
      *(_DWORD *)(a1 + 1080) = GetCurrentThreadId();
      *(_QWORD *)(a1 + 1072) = &v22;
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = 0;
  }
  else
  {
    FullDuplexChannel::CheckWaitForCancelToBeIssued((FullDuplexChannel *)a1);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (_BYTE)v7 )
  {
    if ( *(_BYTE *)(a1 + 798) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\fullduplexchannel.cpp", 464, L"464", 0x54Fu, 0);
    *(_BYTE *)(a1 + 798) = 1;
    goto LABEL_69;
  }
LABEL_9:
  if ( v10 && a3 != 1 && *(_BYTE *)(a1 + 800) )
  {
    if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x400) != 0 )
      WPP_SF_qddd(v14[2], 32, &WPP_c09890fbe2553e46dab0283952d3a950_Traceguids, a1, a3, a4, v9);
    *(_BYTE *)(a1 + 1100) = 1;
    *(_DWORD *)(a1 + 1104) = a3;
    *(_DWORD *)(a1 + 1108) = a4;
    *(_DWORD *)(a1 + 1112) = v9;
    v10 = 0;
  }
  if ( *v11 )
  {
    SetLastError(*v11);
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
      102,
      L"102",
      0x54Fu,
      0);
  }
  else
  {
    WakeAllConditionVariable((PCONDITION_VARIABLE)(a1 + 856));
  }
  if ( *v11 )
    SetLastError(*v11);
  else
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 816));
  if ( v18 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_c09890fbe2553e46dab0283952d3a950_Traceguids, a1, v18);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 72LL))(v18);
  }
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qqddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        &WPP_c09890fbe2553e46dab0283952d3a950_Traceguids,
        a1,
        v10,
        a3,
        a4,
        v9);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1);
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v10 + 16LL))(v10, a3, a4, v9);
  }
  else
  {
    v15 = v22;
    if ( v22 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_c09890fbe2553e46dab0283952d3a950_Traceguids, a1, v22);
        v15 = v22;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 24LL))(v15);
      if ( v22 )
      {
        v18 = a1 + 808;
        v19 = 0;
        CWSManCriticalSection::Acquire((CWSManCriticalSection *)(a1 + 808));
        *(_QWORD *)(a1 + 1072) = 0;
        InCritSecWithConditionVar::~InCritSecWithConditionVar((InCritSecWithConditionVar *)&v18);
      }
    }
  }
}

```

## disassembly

```asm
0x18002d5cc  push    rbp
0x18002d5ce  push    rbx
0x18002d5cf  push    rsi
0x18002d5d0  push    rdi
0x18002d5d1  push    r12
0x18002d5d3  push    r13
0x18002d5d5  push    r14
0x18002d5d7  push    r15
0x18002d5d9  mov     rbp, rsp
0x18002d5dc  sub     rsp, 78h
0x18002d5e0  mov     r13d, r9d
0x18002d5e3  mov     edi, r8d
0x18002d5e6  movzx   r12d, dl
0x18002d5ea  mov     rbx, rcx
0x18002d5ed  xor     esi, esi
0x18002d5ef  mov     [rbp+var_28], rsi
0x18002d5f3  mov     [rbp+arg_0], rsi
0x18002d5f7  mov     r15, [rcx+8]
0x18002d5fb  test    r15, r15
0x18002d5fe  jz      loc_18002D80A
0x18002d604  lea     r14, [rbx+328h]
0x18002d60b  mov     [rbp+var_18], r14
0x18002d60f  mov     [rbp+var_10], esi
0x18002d612  mov     ecx, [r14]; dwErrCode
0x18002d615  test    ecx, ecx
0x18002d617  jnz     loc_18002D700
0x18002d61d  lea     rcx, [r14+8]; lpCriticalSection
0x18002d621  call    cs:__imp_EnterCriticalSection
0x18002d627  nop
0x18002d628  lea     rax, WPP_GLOBAL_Control
0x18002d62f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d636  cmp     rcx, rax
0x18002d639  jnz     loc_18002D832
0x18002d63f  cmp     [rbx+31Dh], sil
0x18002d646  jz      loc_18002D76C
0x18002d64c  cmp     edi, 1
0x18002d64f  jz      loc_18002DA5C
0x18002d655  mov     edi, [rbx+43Ch]
0x18002d65b  mov     r13d, [rbx+440h]
0x18002d662  mov     esi, [rbx+444h]
0x18002d668  mov     rcx, rbx; this
0x18002d66b  call    ?CheckWaitForCancelToBeIssued@FullDuplexChannel@@IEAAXXZ; FullDuplexChannel::CheckWaitForCancelToBeIssued(void)
0x18002d670  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d677  lea     rax, WPP_GLOBAL_Control
0x18002d67e  cmp     rcx, rax
0x18002d681  jnz     loc_18002DA74
0x18002d687  test    r15, r15
0x18002d68a  jz      short loc_18002D69E
0x18002d68c  cmp     edi, 1
0x18002d68f  jz      short loc_18002D69E
0x18002d691  cmp     byte ptr [rbx+320h], 0
0x18002d698  jnz     loc_18002DAC3
0x18002d69e  mov     ecx, [r14]; dwErrCode
0x18002d6a1  test    ecx, ecx
0x18002d6a3  jnz     loc_18002D72E
0x18002d6a9  lea     rcx, [r14+30h]; ConditionVariable
0x18002d6ad  call    cs:__imp_WakeAllConditionVariable
0x18002d6b3  mov     ecx, [r14]; dwErrCode
0x18002d6b6  test    ecx, ecx
0x18002d6b8  jnz     loc_18002D761
0x18002d6be  lea     rcx, [r14+8]; lpCriticalSection
0x18002d6c2  call    cs:__imp_LeaveCriticalSection
0x18002d6c8  nop
0x18002d6c9  mov     r12, [rbp+var_28]
0x18002d6cd  test    r12, r12
0x18002d6d0  jnz     loc_18002DB18
0x18002d6d6  xor     r12d, r12d
0x18002d6d9  test    r15, r15
0x18002d6dc  jnz     loc_18002D7C2
0x18002d6e2  mov     rcx, [rbp+arg_0]
0x18002d6e6  test    rcx, rcx
0x18002d6e9  jnz     loc_18002DBA2
0x18002d6ef  add     rsp, 78h
0x18002d6f3  pop     r15
0x18002d6f5  pop     r14
0x18002d6f7  pop     r13
0x18002d6f9  pop     r12
0x18002d6fb  pop     rdi
0x18002d6fc  pop     rsi
0x18002d6fd  pop     rbx
0x18002d6fe  pop     rbp
0x18002d6ff  retn
0x18002d700  call    cs:__imp_SetLastError
0x18002d706  mov     [rsp+78h+var_58], rsi; struct IRequestContext *
0x18002d70b  mov     r9d, 54Fh; unsigned int
0x18002d711  lea     r8, a59; "59"
0x18002d718  mov     edx, 3Bh ; ';'; unsigned int
0x18002d71d  lea     rcx, aOnecoreAdminWm_164; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18002d724  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002d729  jmp     loc_18002D628
0x18002d72e  call    cs:__imp_SetLastError
0x18002d734  nop
0x18002d735  mov     [rsp+78h+var_58], 0; struct IRequestContext *
0x18002d73e  mov     r9d, 54Fh; unsigned int
0x18002d744  lea     r8, a102; "102"
0x18002d74b  mov     edx, 66h ; 'f'; unsigned int
0x18002d750  lea     rcx, aOnecoreAdminWm_164; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18002d757  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002d75c  jmp     loc_18002D6B3
0x18002d761  call    cs:__imp_SetLastError
0x18002d767  jmp     loc_18002D6C9
0x18002d76c  mov     byte ptr [rbx+31Dh], 1
0x18002d773  cmp     edi, 1
0x18002d776  jz      loc_18002D87B
0x18002d77c  test    r12b, r12b
0x18002d77f  jnz     loc_18002D8F8
0x18002d785  mov     rax, [rbx+70h]
0x18002d789  mov     esi, [rbp+arg_20]
0x18002d78c  test    rax, rax
0x18002d78f  jz      short loc_18002D804
0x18002d791  mov     [rbp+arg_0], rax
0x18002d795  test    rax, rax
0x18002d798  jnz     loc_18002D953
0x18002d79e  mov     rcx, rbx; this
0x18002d7a1  call    ?CheckWaitForCancelToBeIssued@FullDuplexChannel@@IEAAXXZ; FullDuplexChannel::CheckWaitForCancelToBeIssued(void)
0x18002d7a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d7ad  test    r12b, r12b
0x18002d7b0  jnz     loc_18002DA23
0x18002d7b6  lea     rax, WPP_GLOBAL_Control
0x18002d7bd  jmp     loc_18002D687
0x18002d7c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d7c9  lea     rax, WPP_GLOBAL_Control
0x18002d7d0  cmp     rcx, rax
0x18002d7d3  jnz     loc_18002DB66
0x18002d7d9  mov     rax, [rbx]
0x18002d7dc  mov     rcx, rbx
0x18002d7df  mov     rax, [rax+58h]
0x18002d7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7e8  mov     rax, [r15]
0x18002d7eb  mov     r9d, esi
0x18002d7ee  mov     r8d, r13d
0x18002d7f1  mov     edx, edi
0x18002d7f3  mov     rcx, r15
0x18002d7f6  mov     rax, [rax+10h]
0x18002d7fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7ff  jmp     loc_18002D6EF
0x18002d804  mov     rax, [rbp+arg_0]
0x18002d808  jmp     short loc_18002D795
0x18002d80a  mov     [rsp+78h+var_58], rsi; struct IRequestContext *
0x18002d80f  mov     r9d, 54Fh; unsigned int
0x18002d815  lea     r8, a381; "381"
0x18002d81c  mov     edx, 17Dh; unsigned int
0x18002d821  lea     rcx, aOnecoreAdminWm_132; "onecore\\admin\\wmi\\wmx\\stdlib\\fulld"...
0x18002d828  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002d82d  jmp     loc_18002D604
0x18002d832  test    dword ptr [rcx+1Ch], 400h
0x18002d839  jz      loc_18002D63F
0x18002d83f  movzx   r8d, byte ptr [rbx+31Dh]
0x18002d847  mov     rax, [rbx+70h]
0x18002d84b  mov     [rsp+78h+var_38], rax
0x18002d850  mov     [rsp+78h+var_40], r12d
0x18002d855  mov     [rsp+78h+var_48], r13d
0x18002d85a  mov     [rsp+78h+var_50], edi
0x18002d85e  mov     dword ptr [rsp+78h+var_58], r8d
0x18002d863  mov     r9, rbx
0x18002d866  mov     rcx, [rcx+10h]
0x18002d86a  call    WPP_SF_qddddq
0x18002d86f  lea     rax, WPP_GLOBAL_Control
0x18002d876  jmp     loc_18002D63F
0x18002d87b  cmp     [rbx+320h], sil
0x18002d882  jz      short loc_18002D8A7
0x18002d884  mov     [rsp+78h+var_58], rsi; struct IRequestContext *
0x18002d889  mov     r9d, 54Fh; unsigned int
0x18002d88f  lea     r8, a396; "396"
0x18002d896  mov     edx, 18Ch; unsigned int
0x18002d89b  lea     rcx, aOnecoreAdminWm_132; "onecore\\admin\\wmi\\wmx\\stdlib\\fulld"...
0x18002d8a2  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002d8a7  mov     byte ptr [rbx+320h], 1
0x18002d8ae  test    r12b, r12b
0x18002d8b1  jz      loc_18002D785
0x18002d8b7  mov     byte ptr [rbx+321h], 1
0x18002d8be  mov     esi, [rbp+arg_20]
0x18002d8c1  cmp     qword ptr [rbx+18h], 0
0x18002d8c6  jnz     short loc_18002D8EF
0x18002d8c8  mov     [rsp+78h+var_58], 0; struct IRequestContext *
0x18002d8d1  mov     r9d, 54Fh; unsigned int
0x18002d8d7  lea     r8, a420; "420"
0x18002d8de  mov     edx, 1A4h; unsigned int
0x18002d8e3  lea     rcx, aOnecoreAdminWm_132; "onecore\\admin\\wmi\\wmx\\stdlib\\fulld"...
0x18002d8ea  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002d8ef  mov     rax, [rbx+18h]
0x18002d8f3  jmp     loc_18002D791
0x18002d8f8  test    edi, edi
0x18002d8fa  jnz     short loc_18002D8BE
0x18002d8fc  cmp     [rbx+31Fh], sil
0x18002d903  jz      short loc_18002D8BE
0x18002d905  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d90c  cmp     rcx, rax
0x18002d90f  jz      short loc_18002D930
0x18002d911  test    dword ptr [rcx+1Ch], 400h
0x18002d918  jz      short loc_18002D930
0x18002d91a  lea     edx, [rdi+1Ch]
0x18002d91d  mov     r9, rbx
0x18002d920  lea     r8, WPP_c09890fbe2553e46dab0283952d3a950_Traceguids
0x18002d927  mov     rcx, [rcx+10h]
0x18002d92b  call    WPP_SF_q
0x18002d930  mov     edi, 2
0x18002d935  mov     r13d, 3E3h
0x18002d93b  lea     rcx, [rbx+78h]
0x18002d93f  mov     rax, [rcx]
0x18002d942  mov     edx, r13d
0x18002d945  mov     rax, [rax+48h]
0x18002d949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d94e  jmp     loc_18002D8C1
0x18002d953  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d95a  lea     rdx, WPP_GLOBAL_Control
0x18002d961  cmp     rcx, rdx
0x18002d964  jz      short loc_18002D99B
0x18002d966  test    dword ptr [rcx+1Ch], 400h
0x18002d96d  jz      short loc_18002D99B
0x18002d96f  mov     edx, 1Dh
0x18002d974  mov     [rsp+78h+var_48], esi
0x18002d978  mov     [rsp+78h+var_50], r13d
0x18002d97d  mov     dword ptr [rsp+78h+var_58], edi
0x18002d981  mov     r9, rbx
0x18002d984  lea     r8, WPP_c09890fbe2553e46dab0283952d3a950_Traceguids
0x18002d98b  mov     rcx, [rcx+10h]
0x18002d98f  call    WPP_SF_qddd
0x18002d994  lea     rdx, WPP_GLOBAL_Control
0x18002d99b  mov     [rbx+43Ch], edi
0x18002d9a1  mov     [rbx+440h], r13d
0x18002d9a8  mov     [rbx+444h], esi
0x18002d9ae  mov     [rbx+448h], r12d
0x18002d9b5  cmp     qword ptr [rbx+430h], 0
0x18002d9bd  jnz     short loc_18002D9DF
0x18002d9bf  call    cs:__imp_GetCurrentThreadId
0x18002d9c5  mov     [rbx+438h], eax
0x18002d9cb  lea     rax, [rbp+arg_0]
0x18002d9cf  mov     [rbx+430h], rax
0x18002d9d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d9dd  jmp     short loc_18002DA1B
0x18002d9df  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d9e6  cmp     rcx, rdx
0x18002d9e9  jz      short loc_18002DA13
0x18002d9eb  test    dword ptr [rcx+1Ch], 400h
0x18002d9f2  jz      short loc_18002DA13
0x18002d9f4  mov     edx, 1Eh
0x18002d9f9  mov     r9, rbx
0x18002d9fc  lea     r8, WPP_c09890fbe2553e46dab0283952d3a950_Traceguids
0x18002da03  mov     rcx, [rcx+10h]
0x18002da07  call    WPP_SF_q
0x18002da0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da13  mov     [rbp+arg_0], 0
0x18002da1b  xor     r15d, r15d
0x18002da1e  jmp     loc_18002D7AD
0x18002da23  cmp     byte ptr [rbx+31Eh], 0
0x18002da2a  jz      short loc_18002DA53
0x18002da2c  mov     [rsp+78h+var_58], 0; struct IRequestContext *
0x18002da35  mov     r9d, 54Fh; unsigned int
0x18002da3b  lea     r8, a464; "464"
0x18002da42  mov     edx, 1D0h; unsigned int
0x18002da47  lea     rcx, aOnecoreAdminWm_132; "onecore\\admin\\wmi\\wmx\\stdlib\\fulld"...
0x18002da4e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002da53  mov     byte ptr [rbx+31Eh], 1
0x18002da5a  jmp     short loc_18002DAB7
0x18002da5c  test    r12b, r12b
0x18002da5f  jz      short loc_18002DA67
0x18002da61  mov     rax, [rbx+70h]
0x18002da65  jmp     short loc_18002DA6B
0x18002da67  mov     rax, [rbx+18h]
0x18002da6b  mov     [rbp+var_28], rax
0x18002da6f  jmp     loc_18002D655
0x18002da74  test    dword ptr [rcx+1Ch], 400h
0x18002da7b  jz      loc_18002D687
0x18002da81  mov     edx, 1Fh
0x18002da86  mov     eax, [rbx+444h]
0x18002da8c  mov     [rsp+78h+var_48], eax
0x18002da90  mov     eax, [rbx+440h]
0x18002da96  mov     [rsp+78h+var_50], eax
0x18002da9a  mov     eax, [rbx+43Ch]
0x18002daa0  mov     dword ptr [rsp+78h+var_58], eax
0x18002daa4  mov     r9, rbx
0x18002daa7  lea     r8, WPP_c09890fbe2553e46dab0283952d3a950_Traceguids
0x18002daae  mov     rcx, [rcx+10h]
0x18002dab2  call    WPP_SF_qddd
0x18002dab7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dabe  jmp     loc_18002D7B6
0x18002dac3  cmp     rcx, rax
0x18002dac6  jz      short loc_18002DAF6
0x18002dac8  test    dword ptr [rcx+1Ch], 400h
0x18002dacf  jz      short loc_18002DAF6
0x18002dad1  mov     edx, 20h ; ' '
0x18002dad6  mov     [rsp+78h+var_48], esi
0x18002dada  mov     [rsp+78h+var_50], r13d
0x18002dadf  mov     dword ptr [rsp+78h+var_58], edi
0x18002dae3  mov     r9, rbx
0x18002dae6  lea     r8, WPP_c09890fbe2553e46dab0283952d3a950_Traceguids
0x18002daed  mov     rcx, [rcx+10h]
0x18002daf1  call    WPP_SF_qddd
0x18002daf6  mov     byte ptr [rbx+44Ch], 1
0x18002dafd  mov     [rbx+450h], edi
0x18002db03  mov     [rbx+454h], r13d
0x18002db0a  mov     [rbx+458h], esi
0x18002db10  xor     r15d, r15d
0x18002db13  jmp     loc_18002D69E
0x18002db18  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db1f  lea     rax, WPP_GLOBAL_Control
0x18002db26  cmp     rcx, rax
0x18002db29  jz      short loc_18002DB51
0x18002db2b  test    dword ptr [rcx+1Ch], 400h
  ... truncated ...
```
