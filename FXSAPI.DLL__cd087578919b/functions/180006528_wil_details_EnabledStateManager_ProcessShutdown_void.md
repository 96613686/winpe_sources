# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180006528`
- end: `0x180006787`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `607`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180002e68`
- `0x18003d990`

## callees

- `0x180006528`
- `0x180009238`
- `0x18000981c`
- `0x18003d510`
- `0x18003e010`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x180006753`
- `KERNEL32!CloseThreadpoolTimer` at `0x180006753`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180006744`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180006744`
- `KERNEL32!SetThreadpoolTimer` at `0x180006732`
- `KERNEL32!SetThreadpoolTimer` at `0x180006732`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006705`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006705`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000656e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000656e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(wil::details::EnabledStateManager *this)
{
  RTL_SRWLOCK *v2; // rbp
  int *v3; // rbx
  int *v4; // rdi
  __int64 v5; // r8
  int v6; // r10d
  unsigned __int32 v7; // ecx
  unsigned __int32 v8; // eax
  char *v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // rdx
  void (__fastcall *v12)(_QWORD, __int64, _QWORD, _QWORD); // rax
  struct _TP_TIMER *v13; // rbx
  PTP_TIMER pti; // [rsp+30h] [rbp-68h] BYREF
  _DWORD v15[2]; // [rsp+38h] [rbp-60h] BYREF
  char v16; // [rsp+40h] [rbp-58h] BYREF

  *(_DWORD *)this = 0;
  pti = (PTP_TIMER)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  v2 = (RTL_SRWLOCK *)((char *)this + 8);
  AcquireSRWLockExclusive((PSRWLOCK)this + 1);
  v3 = (int *)*((_QWORD *)this + 6);
  v4 = (int *)*((_QWORD *)this + 7);
  if ( (unsigned __int64)((char *)v4 - (char *)v3) >= 0x10 )
  {
    while ( v3 != v4 )
    {
      v5 = *((_QWORD *)v3 + 1);
      v6 = *v3;
      _m_prefetchw((const void *)v5);
      v7 = _InterlockedAnd((volatile signed __int32 *)v5, 0xFFC0401E);
      if ( ((v7 >> 1) & 0xF) != 0 )
      {
        _m_prefetchw((const void *)(v5 + 4));
        v8 = (v7 >> 1) & 0xF & ~_InterlockedOr((volatile signed __int32 *)(v5 + 4), (v7 >> 1) & 0xF);
      }
      else
      {
        v8 = 0;
      }
      if ( (v8 & 1) != 0 )
      {
        v15[0] = v6;
        v15[1] = 65538;
        v9 = &v16;
      }
      else
      {
        v9 = (char *)v15;
      }
      if ( (v8 & 2) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65542;
        v9 += 8;
      }
      if ( (v8 & 4) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65539;
        v9 += 8;
      }
      if ( v8 >= 8 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65543;
        v9 += 8;
      }
      v10 = v7 >> 5;
      if ( (v10 & 0x1FF) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 14) & 1);
        LOWORD(v10) = v10 & 0x1FF;
        *((_WORD *)v9 + 3) = v10;
        v9 += 8;
      }
      if ( ((v7 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 22) & 1) + 1;
        *((_WORD *)v9 + 3) = (v7 >> 15) & 0x7F;
        v9 += 8;
      }
      v11 = (v9 - (char *)v15) >> 3;
      if ( v11 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v15,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v11,
          v10);
      v3 += 4;
    }
    *((_QWORD *)this + 7) = *((_QWORD *)this + 6);
    v12 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v12 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v12(0, 254, 0, 0);
    }
  }
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    &pti,
    0);
  v13 = pti;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v13, 1);
    CloseThreadpoolTimer(v13);
  }
}

```

## disassembly

```asm
0x180006528  mov     [rsp+arg_8], rbx
0x18000652d  mov     [rsp+arg_10], rbp
0x180006532  push    rsi
0x180006533  push    rdi
0x180006534  push    r12
0x180006536  push    r14
0x180006538  push    r15
0x18000653a  sub     rsp, 70h
0x18000653e  mov     rax, cs:__security_cookie
0x180006545  xor     rax, rsp
0x180006548  mov     [rsp+98h+var_30], rax
0x18000654d  mov     rsi, rcx
0x180006550  mov     dword ptr [rcx], 0
0x180006556  mov     rax, [rcx+10h]
0x18000655a  mov     [rsp+98h+pti], rax
0x18000655f  mov     qword ptr [rcx+10h], 0
0x180006567  lea     rbp, [rcx+8]
0x18000656b  mov     rcx, rbp; SRWLock
0x18000656e  call    cs:__imp_AcquireSRWLockExclusive
0x180006575  nop     dword ptr [rax+rax+00h]
0x18000657a  nop
0x18000657b  mov     rbx, [rsi+30h]
0x18000657f  mov     rdi, [rsi+38h]
0x180006583  mov     rax, rdi
0x180006586  sub     rax, rbx
0x180006589  mov     r14d, 1
0x18000658f  cmp     rax, 10h
0x180006593  jb      loc_1800066FD
0x180006599  lea     r15d, [r14+1]
0x18000659d  mov     r12d, 1FFh
0x1800065a3  cmp     rbx, rdi
0x1800065a6  jz      loc_1800066CA
0x1800065ac  mov     r8, [rbx+8]
0x1800065b0  mov     r10d, [rbx]
0x1800065b3  prefetchw byte ptr [r8]
0x1800065b7  mov     eax, [r8]
0x1800065ba  mov     ecx, eax
0x1800065bc  and     ecx, 0FFC0401Eh
0x1800065c2  lock cmpxchg [r8], ecx
0x1800065c7  jnz     short loc_1800065BA
0x1800065c9  mov     ecx, eax
0x1800065cb  mov     r9d, eax
0x1800065ce  shr     r9d, 1
0x1800065d1  and     r9d, 0Fh
0x1800065d5  jz      short loc_1800065F4
0x1800065d7  prefetchw byte ptr [r8+4]
0x1800065dc  mov     eax, [r8+4]
0x1800065e0  mov     edx, eax
0x1800065e2  or      edx, r9d
0x1800065e5  lock cmpxchg [r8+4], edx
0x1800065eb  jnz     short loc_1800065E0
0x1800065ed  not     eax
0x1800065ef  and     eax, r9d
0x1800065f2  jmp     short loc_1800065F7
0x1800065f4  mov     eax, r9d
0x1800065f7  test    r14b, al
0x1800065fa  jz      short loc_180006610
0x1800065fc  mov     [rsp+98h+var_60], r10d
0x180006601  mov     [rsp+98h+var_5C], 10002h
0x180006609  lea     rdx, [rsp+98h+var_58]
0x18000660e  jmp     short loc_180006615
0x180006610  lea     rdx, [rsp+98h+var_60]
0x180006615  test    r15b, al
0x180006618  jz      short loc_180006628
0x18000661a  mov     [rdx], r10d
0x18000661d  mov     dword ptr [rdx+4], 10006h
0x180006624  add     rdx, 8
0x180006628  test    al, 4
0x18000662a  jz      short loc_18000663A
0x18000662c  mov     [rdx], r10d
0x18000662f  mov     dword ptr [rdx+4], 10003h
0x180006636  add     rdx, 8
0x18000663a  cmp     eax, 8
0x18000663d  jb      short loc_18000664D
0x18000663f  mov     [rdx], r10d
0x180006642  mov     dword ptr [rdx+4], 10007h
0x180006649  add     rdx, 8
0x18000664d  mov     r8d, ecx
0x180006650  shr     r8d, 5
0x180006654  test    r12d, r8d
0x180006657  jz      short loc_18000667A
0x180006659  mov     [rdx], r10d
0x18000665c  mov     eax, ecx
0x18000665e  shr     eax, 0Eh
0x180006661  and     ax, r14w
0x180006665  shl     ax, 2
0x180006669  mov     [rdx+4], ax
0x18000666d  and     r8w, r12w; unsigned __int64
0x180006671  mov     [rdx+6], r8w
0x180006676  add     rdx, 8
0x18000667a  mov     eax, ecx
0x18000667c  shr     eax, 0Fh
0x18000667f  test    al, 7Fh
0x180006681  jz      short loc_1800066A5
0x180006683  mov     [rdx], r10d
0x180006686  shr     ecx, 16h
0x180006689  and     cx, r14w
0x18000668d  shl     cx, 2
0x180006691  add     cx, r14w
0x180006695  mov     [rdx+4], cx
0x180006699  and     ax, 7Fh
0x18000669d  mov     [rdx+6], ax
0x1800066a1  add     rdx, 8
0x1800066a5  lea     rax, [rsp+98h+var_60]
0x1800066aa  sub     rdx, rax
0x1800066ad  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1800066b1  test    rdx, rdx
0x1800066b4  jle     short loc_1800066C1
0x1800066b6  lea     rcx, [rsp+98h+var_60]; this
0x1800066bb  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1800066c0  nop
0x1800066c1  add     rbx, 10h
0x1800066c5  jmp     loc_1800065A3
0x1800066ca  mov     rax, [rsi+30h]
0x1800066ce  mov     [rsi+38h], rax
0x1800066d2  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800066d9  test    rax, rax
0x1800066dc  jnz     short loc_1800066EA
0x1800066de  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800066e5  test    rax, rax
0x1800066e8  jz      short loc_1800066FD
0x1800066ea  xor     r9d, r9d
0x1800066ed  xor     r8d, r8d
0x1800066f0  mov     edx, 0FEh
0x1800066f5  xor     ecx, ecx
0x1800066f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066fc  nop
0x1800066fd  test    rbp, rbp
0x180006700  jz      short loc_180006711
0x180006702  mov     rcx, rbp; SRWLock
0x180006705  call    cs:__imp_ReleaseSRWLockExclusive
0x18000670c  nop     dword ptr [rax+rax+00h]
0x180006711  xor     edx, edx
0x180006713  lea     rcx, [rsp+98h+pti]
0x180006718  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000671d  mov     rbx, [rsp+98h+pti]
0x180006722  test    rbx, rbx
0x180006725  jz      short loc_180006760
0x180006727  xor     r9d, r9d; msWindowLength
0x18000672a  xor     r8d, r8d; msPeriod
0x18000672d  xor     edx, edx; pftDueTime
0x18000672f  mov     rcx, rbx; pti
0x180006732  call    cs:__imp_SetThreadpoolTimer
0x180006739  nop     dword ptr [rax+rax+00h]
0x18000673e  mov     edx, r14d; fCancelPendingCallbacks
0x180006741  mov     rcx, rbx; pti
0x180006744  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000674b  nop     dword ptr [rax+rax+00h]
0x180006750  mov     rcx, rbx; pti
0x180006753  call    cs:__imp_CloseThreadpoolTimer
0x18000675a  nop     dword ptr [rax+rax+00h]
0x18000675f  nop
0x180006760  mov     rcx, [rsp+98h+var_30]
0x180006765  xor     rcx, rsp; StackCookie
0x180006768  call    __security_check_cookie
0x18000676d  lea     r11, [rsp+98h+var_28]
0x180006772  mov     rbx, [r11+38h]
0x180006776  mov     rbp, [r11+40h]
0x18000677a  mov     rsp, r11
0x18000677d  pop     r15
0x18000677f  pop     r14
0x180006781  pop     r12
0x180006783  pop     rdi
0x180006784  pop     rsi
0x180006785  retn
```
