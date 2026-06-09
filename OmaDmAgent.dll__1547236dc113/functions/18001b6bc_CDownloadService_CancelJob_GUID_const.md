# CDownloadService::CancelJob(_GUID const &)

- ea: `0x18001b6bc`
- end: `0x18001b9ce`
- name: `?CancelJob@CDownloadService@@QEAAJAEBU_GUID@@@Z`
- size: `786`
- prototype: `int(CDownloadService *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180013330`
- `0x180013ce4`

## callees

- `0x18000702c`
- `0x18000a2c0`
- `0x18000a358`
- `0x18001afb4`
- `0x18001b6bc`
- `0x18001c54c`
- `0x18001e154`
- `0x180021010`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x18001b712`
- `ADVAPI32!RevertToSelf` at `0x18001b712`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDownloadService::CancelJob(CDownloadService *this, struct _GUID *a2)
{
  char v4; // si
  _QWORD *v5; // r9
  int BITSJob; // ebx
  struct IBackgroundCopyJob *v7; // rdi
  HRESULT (__stdcall *GetNotifyInterface)(IBackgroundCopyJob *, IUnknown **); // rbx
  unsigned int v9; // ebx
  _QWORD *v10; // rdi
  wchar_t *v11; // rax
  int v12; // eax
  unsigned int v13; // ebx
  _QWORD *v14; // rdi
  wchar_t *v15; // rax
  int v16; // eax
  LPCWSTR v17; // rcx
  __int64 v18; // rdx
  __int64 v20; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v21[40]; // [rsp+38h] [rbp-28h] BYREF
  char v22; // [rsp+A0h] [rbp+40h] BYREF
  int (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp+50h] BYREF
  struct IBackgroundCopyJob *v24; // [rsp+B8h] [rbp+58h] BYREF

  v24 = 0;
  v23 = 0;
  v20 = 0;
  v4 = 0;
  v22 = 0;
  if ( *((_BYTE *)this + 8) )
  {
    RevertToSelf();
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v5 = (_QWORD *)((char *)this + 16);
      if ( *((_QWORD *)this + 5) >= 8u )
        v5 = (_QWORD *)*v5;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v5);
    }
    v4 = 1;
  }
  BITSJob = FindBITSJob(a2, &v24);
  if ( BITSJob < 0 )
    goto LABEL_31;
  v7 = v24;
  GetNotifyInterface = v24->lpVtbl->GetNotifyInterface;
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>((__int64 *)&v23);
  v23 = 0;
  if ( ((int (__fastcall *)(struct IBackgroundCopyJob *, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))GetNotifyInterface)(
         v7,
         &v23) >= 0
    && v23
    && (**v23)(v23, &GUID_5cfdcbb7_0052_4e8d_b6bd_aadebd2f3621, &v20) >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 32LL))(v20);
  }
  BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *))v24->lpVtbl->Cancel)(v24);
  if ( BITSJob < 0 )
  {
LABEL_31:
    if ( !v4 )
      goto LABEL_49;
  }
  else
  {
    if ( !v4 )
      goto LABEL_49;
    v9 = *((_DWORD *)this + 12);
    v10 = (_QWORD *)((char *)this + 16);
    v11 = (wchar_t *)std::wstring::wstring(v21, (char *)this + 16);
    v12 = __ImpersonateUser(v11, v9, &v22);
    BITSJob = v12;
    if ( v12 >= 0 )
    {
      if ( v22 )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          if ( *((_QWORD *)this + 5) >= 8u )
            v10 = (_QWORD *)*v10;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v10);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          if ( *((_QWORD *)this + 5) >= 8u )
            v10 = (_QWORD *)*v10;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v10);
        }
        BITSJob = -2147418113;
      }
    }
    else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids,
        (unsigned int)v12);
    }
  }
  if ( v22 )
    goto LABEL_49;
  v13 = *((_DWORD *)this + 12);
  v14 = (_QWORD *)((char *)this + 16);
  v15 = (wchar_t *)std::wstring::wstring(v21, (char *)this + 16);
  v16 = __ImpersonateUser(v15, v13, &v22);
  BITSJob = v16;
  if ( v16 >= 0 )
  {
    if ( v22 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_49;
      if ( *((_QWORD *)this + 5) >= 8u )
        v14 = (_QWORD *)*v14;
      v18 = 36;
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_49;
      if ( *((_QWORD *)this + 5) >= 8u )
        v14 = (_QWORD *)*v14;
      v18 = 35;
    }
    WPP_SF_S(*((_QWORD *)v17 + 2), v18, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v14);
    goto LABEL_49;
  }
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids,
      (unsigned int)v16);
LABEL_49:
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v20);
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>((__int64 *)&v23);
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>((__int64 *)&v24);
  return (unsigned int)BITSJob;
}

```

## disassembly

```asm
0x18001b6bc  push    rbp
0x18001b6be  push    rbx
0x18001b6bf  push    rsi
0x18001b6c0  push    rdi
0x18001b6c1  push    r12
0x18001b6c3  push    r13
0x18001b6c5  push    r14
0x18001b6c7  mov     rbp, rsp
0x18001b6ca  sub     rsp, 60h
0x18001b6ce  mov     rbx, rdx
0x18001b6d1  mov     r14, rcx
0x18001b6d4  mov     [rbp+arg_18], 0
0x18001b6dc  mov     [rbp+arg_10], 0
0x18001b6e4  mov     [rbp+var_30], 0
0x18001b6ec  lea     rax, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001b6f3  mov     [rbp+var_38], rax
0x18001b6f7  xor     sil, sil
0x18001b6fa  mov     [rbp+arg_0], sil
0x18001b6fe  lea     r12, WPP_GLOBAL_Control
0x18001b705  lea     r13, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001b70c  cmp     [rcx+8], sil
0x18001b710  jz      short loc_18001B752
0x18001b712  call    cs:__imp_RevertToSelf
0x18001b719  nop     dword ptr [rax+rax+00h]
0x18001b71e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b725  cmp     rcx, r12
0x18001b728  jz      short loc_18001B74F
0x18001b72a  test    byte ptr [rcx+1Ch], 1
0x18001b72e  jz      short loc_18001B74F
0x18001b730  lea     r9, [r14+10h]
0x18001b734  cmp     qword ptr [r9+18h], 8
0x18001b739  jb      short loc_18001B73E
0x18001b73b  mov     r9, [r9]
0x18001b73e  mov     edx, 1Eh
0x18001b743  mov     r8, r13
0x18001b746  mov     rcx, [rcx+10h]
0x18001b74a  call    WPP_SF_S
0x18001b74f  mov     sil, 1
0x18001b752  lea     rdx, [rbp+arg_18]; struct IBackgroundCopyJob **
0x18001b756  mov     rcx, rbx; Uuid
0x18001b759  call    ?FindBITSJob@@YAJAEBU_GUID@@PEAPEAUIBackgroundCopyJob@@@Z; FindBITSJob(_GUID const &,IBackgroundCopyJob * *)
0x18001b75e  mov     ebx, eax
0x18001b760  test    eax, eax
0x18001b762  js      loc_18001B8D7
0x18001b768  mov     rdi, [rbp+arg_18]
0x18001b76c  mov     rax, [rdi]
0x18001b76f  mov     rbx, [rax+0D0h]
0x18001b776  lea     rcx, [rbp+arg_10]
0x18001b77a  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001b77f  mov     [rbp+arg_10], 0
0x18001b787  lea     rdx, [rbp+arg_10]
0x18001b78b  mov     rcx, rdi
0x18001b78e  mov     rax, rbx
0x18001b791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b796  test    eax, eax
0x18001b798  js      short loc_18001B7ED
0x18001b79a  mov     rbx, [rbp+arg_10]
0x18001b79e  test    rbx, rbx
0x18001b7a1  jz      short loc_18001B7ED
0x18001b7a3  mov     rcx, [rbp+var_30]
0x18001b7a7  test    rcx, rcx
0x18001b7aa  jz      short loc_18001B7C0
0x18001b7ac  mov     [rbp+var_30], 0
0x18001b7b4  mov     rax, [rcx]
0x18001b7b7  mov     rax, [rax+10h]
0x18001b7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7c0  mov     rax, [rbx]
0x18001b7c3  lea     r8, [rbp+var_30]
0x18001b7c7  lea     rdx, _GUID_5cfdcbb7_0052_4e8d_b6bd_aadebd2f3621
0x18001b7ce  mov     rcx, rbx
0x18001b7d1  mov     rax, [rax]
0x18001b7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7d9  test    eax, eax
0x18001b7db  js      short loc_18001B7ED
0x18001b7dd  mov     rcx, [rbp+var_30]
0x18001b7e1  mov     rax, [rcx]
0x18001b7e4  mov     rax, [rax+20h]
0x18001b7e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7ed  mov     rcx, [rbp+arg_18]
0x18001b7f1  mov     rax, [rcx]
0x18001b7f4  mov     rax, [rax+40h]
0x18001b7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7fd  mov     ebx, eax
0x18001b7ff  test    eax, eax
0x18001b801  js      loc_18001B8D7
0x18001b807  test    sil, sil
0x18001b80a  jz      loc_18001B994
0x18001b810  mov     ebx, [r14+30h]
0x18001b814  lea     rdi, [r14+10h]
0x18001b818  mov     rdx, rdi
0x18001b81b  lea     rcx, [rbp+var_28]
0x18001b81f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001b824  lea     r8, [rbp+arg_0]
0x18001b828  mov     edx, ebx; SessionId
0x18001b82a  mov     rcx, rax; String2
0x18001b82d  call    ?__ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z; __ImpersonateUser(std::wstring,ulong,bool &)
0x18001b832  mov     ebx, eax
0x18001b834  test    eax, eax
0x18001b836  jns     short loc_18001B868
0x18001b838  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b83f  cmp     rcx, r12
0x18001b842  jz      loc_18001B8E0
0x18001b848  test    byte ptr [rcx+1Ch], 4
0x18001b84c  jz      loc_18001B8E0
0x18001b852  mov     edx, 1Fh
0x18001b857  mov     r9d, eax
0x18001b85a  mov     r8, r13
0x18001b85d  mov     rcx, [rcx+10h]
0x18001b861  call    WPP_SF_d
0x18001b866  jmp     short loc_18001B8E0
0x18001b868  cmp     [rbp+arg_0], 0
0x18001b86c  jnz     short loc_18001B8A5
0x18001b86e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b875  cmp     rcx, r12
0x18001b878  jz      short loc_18001B89E
0x18001b87a  test    byte ptr [rcx+1Ch], 4
0x18001b87e  jz      short loc_18001B89E
0x18001b880  cmp     qword ptr [rdi+18h], 8
0x18001b885  jb      short loc_18001B88A
0x18001b887  mov     rdi, [rdi]
0x18001b88a  mov     edx, 20h ; ' '
0x18001b88f  mov     r9, rdi
0x18001b892  mov     r8, r13
0x18001b895  mov     rcx, [rcx+10h]
0x18001b899  call    WPP_SF_S
0x18001b89e  mov     ebx, 8000FFFFh
0x18001b8a3  jmp     short loc_18001B8E0
0x18001b8a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8ac  cmp     rcx, r12
0x18001b8af  jz      short loc_18001B8E0
0x18001b8b1  test    byte ptr [rcx+1Ch], 1
0x18001b8b5  jz      short loc_18001B8E0
0x18001b8b7  cmp     qword ptr [rdi+18h], 8
0x18001b8bc  jb      short loc_18001B8C1
0x18001b8be  mov     rdi, [rdi]
0x18001b8c1  mov     edx, 21h ; '!'
0x18001b8c6  mov     r9, rdi
0x18001b8c9  mov     r8, r13
0x18001b8cc  mov     rcx, [rcx+10h]
0x18001b8d0  call    WPP_SF_S
0x18001b8d5  jmp     short loc_18001B8E0
0x18001b8d7  test    sil, sil
0x18001b8da  jz      loc_18001B994
0x18001b8e0  cmp     [rbp+arg_0], 0
0x18001b8e4  jnz     loc_18001B994
0x18001b8ea  mov     ebx, [r14+30h]
0x18001b8ee  lea     rdi, [r14+10h]
0x18001b8f2  mov     rdx, rdi
0x18001b8f5  lea     rcx, [rbp+var_28]
0x18001b8f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001b8fe  lea     r8, [rbp+arg_0]
0x18001b902  mov     edx, ebx; SessionId
0x18001b904  mov     rcx, rax; String2
0x18001b907  call    ?__ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z; __ImpersonateUser(std::wstring,ulong,bool &)
0x18001b90c  mov     ebx, eax
0x18001b90e  test    eax, eax
0x18001b910  jns     short loc_18001B93A
0x18001b912  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b919  cmp     rcx, r12
0x18001b91c  jz      short loc_18001B994
0x18001b91e  test    byte ptr [rcx+1Ch], 4
0x18001b922  jz      short loc_18001B994
0x18001b924  mov     edx, 22h ; '"'
0x18001b929  mov     r9d, eax
0x18001b92c  mov     r8, r13
0x18001b92f  mov     rcx, [rcx+10h]
0x18001b933  call    WPP_SF_d
0x18001b938  jmp     short loc_18001B994
0x18001b93a  cmp     [rbp+arg_0], 0
0x18001b93e  jnz     short loc_18001B963
0x18001b940  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b947  cmp     rcx, r12
0x18001b94a  jz      short loc_18001B994
0x18001b94c  test    byte ptr [rcx+1Ch], 4
0x18001b950  jz      short loc_18001B994
0x18001b952  cmp     qword ptr [rdi+18h], 8
0x18001b957  jb      short loc_18001B95C
0x18001b959  mov     rdi, [rdi]
0x18001b95c  mov     edx, 23h ; '#'
0x18001b961  jmp     short loc_18001B984
0x18001b963  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b96a  cmp     rcx, r12
0x18001b96d  jz      short loc_18001B994
0x18001b96f  test    byte ptr [rcx+1Ch], 1
0x18001b973  jz      short loc_18001B994
0x18001b975  cmp     qword ptr [rdi+18h], 8
0x18001b97a  jb      short loc_18001B97F
0x18001b97c  mov     rdi, [rdi]
0x18001b97f  mov     edx, 24h ; '$'
0x18001b984  mov     r9, rdi
0x18001b987  mov     r8, r13
0x18001b98a  mov     rcx, [rcx+10h]
0x18001b98e  call    WPP_SF_S
0x18001b993  nop
0x18001b994  lea     rax, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001b99b  mov     [rbp+var_38], rax
0x18001b99f  lea     rcx, [rbp+var_30]
0x18001b9a3  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001b9a8  nop
0x18001b9a9  lea     rcx, [rbp+arg_10]
0x18001b9ad  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001b9b2  nop
0x18001b9b3  lea     rcx, [rbp+arg_18]
0x18001b9b7  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001b9bc  mov     eax, ebx
0x18001b9be  add     rsp, 60h
0x18001b9c2  pop     r14
0x18001b9c4  pop     r13
0x18001b9c6  pop     r12
0x18001b9c8  pop     rdi
0x18001b9c9  pop     rsi
0x18001b9ca  pop     rbx
0x18001b9cb  pop     rbp
0x18001b9cc  retn
```
