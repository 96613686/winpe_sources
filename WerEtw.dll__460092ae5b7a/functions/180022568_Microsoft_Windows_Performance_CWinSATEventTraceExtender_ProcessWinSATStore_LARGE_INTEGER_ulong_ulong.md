# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATStore(_LARGE_INTEGER,ulong,ulong)

- ea: `0x180022568`
- end: `0x180022798`
- name: `?ProcessWinSATStore@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `560`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021e20`

## callees

- `0x180021f6c`
- `0x180022568`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800225a9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800225a9`

## string_xrefs

- `0x180022734`: `WinSAT/SystemConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATStore(
        Microsoft::Windows::Performance::CWinSATEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  HRESULT Instance; // edi
  int v10; // ebx
  __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 v11; // [rsp+40h] [rbp-28h] BYREF
  struct IQueryRecentWinSATAssessment *ppv; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v13[3]; // [rsp+50h] [rbp-18h] BYREF

  ppv = 0;
  Instance = CoCreateInstance(
               &GUID_f3bdfad3_f276_49e9_9b17_c474f48f0764,
               0,
               1u,
               &GUID_f8ad5d1f_3b47_4bdc_9375_7c6b1da4eca7,
               (LPVOID *)&ppv);
  if ( Instance < 0 )
  {
    if ( ppv )
      ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *))ppv->lpVtbl->Release)(ppv);
    return (unsigned int)Instance;
  }
  v11 = WINSAT_ASSESSMENT_STATE_MIN;
  v13[0] = 0;
  Instance = ((__int64 (__fastcall *)(struct IQueryRecentWinSATAssessment *, _QWORD *))ppv->lpVtbl->get_Info)(ppv, v13);
  if ( Instance < 0 )
  {
    if ( v13[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[0] + 16LL))(v13[0]);
    if ( ppv )
      ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *))ppv->lpVtbl->Release)(ppv);
    return (unsigned int)Instance;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *))(*(_QWORD *)v13[0] + 64LL))(
               v13[0],
               &v11);
  if ( Instance < 0 )
  {
    if ( v13[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[0] + 16LL))(v13[0]);
    if ( ppv )
      ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *))ppv->lpVtbl->Release)(ppv);
    return (unsigned int)Instance;
  }
  if ( v13[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[0] + 16LL))(v13[0]);
  Instance = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
               this,
               ppv,
               v11,
               0x20u,
               (OLECHAR *)L"WinSAT/WinSPR",
               a2,
               a3,
               a4);
  if ( Instance < 0 )
  {
    if ( ppv )
      ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *))ppv->lpVtbl->Release)(ppv);
    return (unsigned int)Instance;
  }
  Instance = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
               this,
               ppv,
               v11,
               0x22u,
               (OLECHAR *)L"WinSAT/Metrics",
               a2,
               a3,
               a4);
  if ( Instance < 0 )
  {
    if ( ppv )
      ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *))ppv->lpVtbl->Release)(ppv);
    return (unsigned int)Instance;
  }
  v10 = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
          this,
          ppv,
          v11,
          0x24u,
          (OLECHAR *)L"WinSAT/SystemConfig",
          a2,
          a3,
          a4);
  if ( v10 >= 0 )
  {
    if ( ppv )
      ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *))ppv->lpVtbl->Release)(ppv);
    return 0;
  }
  else
  {
    if ( ppv )
      ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *))ppv->lpVtbl->Release)(ppv);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x180022568  push    rbp
0x18002256a  push    rbx
0x18002256b  push    rsi
0x18002256c  push    rdi
0x18002256d  push    r14
0x18002256f  push    r15
0x180022571  mov     rbp, rsp
0x180022574  sub     rsp, 68h
0x180022578  mov     esi, r9d
0x18002257b  mov     r14d, r8d
0x18002257e  mov     rbx, rdx
0x180022581  mov     r15, rcx
0x180022584  mov     [rbp+var_20], 0
0x18002258c  lea     rax, [rbp+var_20]
0x180022590  mov     [rsp+68h+ppv], rax; ppv
0x180022595  lea     r9, _GUID_f8ad5d1f_3b47_4bdc_9375_7c6b1da4eca7; riid
0x18002259c  xor     edx, edx; pUnkOuter
0x18002259e  lea     r8d, [rdx+1]; dwClsContext
0x1800225a2  lea     rcx, _GUID_f3bdfad3_f276_49e9_9b17_c474f48f0764; rclsid
0x1800225a9  call    cs:__imp_CoCreateInstance
0x1800225af  mov     edi, eax
0x1800225b1  test    eax, eax
0x1800225b3  jns     short loc_1800225D2
0x1800225b5  mov     rcx, [rbp+var_20]
0x1800225b9  test    rcx, rcx
0x1800225bc  jz      short loc_1800225CB
0x1800225be  mov     rdx, [rcx]
0x1800225c1  mov     rax, [rdx+10h]
0x1800225c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225ca  nop
0x1800225cb  mov     eax, edi
0x1800225cd  jmp     loc_18002278B
0x1800225d2  mov     [rbp+var_28], 0
0x1800225d9  mov     [rbp+var_18], 0
0x1800225e1  mov     rcx, [rbp+var_20]
0x1800225e5  mov     rax, [rcx]
0x1800225e8  lea     rdx, [rbp+var_18]
0x1800225ec  mov     rax, [rax+40h]
0x1800225f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225f5  mov     edi, eax
0x1800225f7  test    eax, eax
0x1800225f9  jns     short loc_180022629
0x1800225fb  mov     rcx, [rbp+var_18]
0x1800225ff  test    rcx, rcx
0x180022602  jz      short loc_180022611
0x180022604  mov     rdx, [rcx]
0x180022607  mov     rax, [rdx+10h]
0x18002260b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022610  nop
0x180022611  mov     rcx, [rbp+var_20]
0x180022615  test    rcx, rcx
0x180022618  jz      short loc_180022627
0x18002261a  mov     rax, [rcx]
0x18002261d  mov     rax, [rax+10h]
0x180022621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022626  nop
0x180022627  jmp     short loc_1800225CB
0x180022629  mov     rcx, [rbp+var_18]
0x18002262d  mov     rax, [rcx]
0x180022630  lea     rdx, [rbp+var_28]
0x180022634  mov     rax, [rax+40h]
0x180022638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002263d  mov     edi, eax
0x18002263f  test    eax, eax
0x180022641  jns     short loc_180022674
0x180022643  mov     rcx, [rbp+var_18]
0x180022647  test    rcx, rcx
0x18002264a  jz      short loc_180022659
0x18002264c  mov     rdx, [rcx]
0x18002264f  mov     rax, [rdx+10h]
0x180022653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022658  nop
0x180022659  mov     rcx, [rbp+var_20]
0x18002265d  test    rcx, rcx
0x180022660  jz      short loc_18002266F
0x180022662  mov     rax, [rcx]
0x180022665  mov     rax, [rax+10h]
0x180022669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002266e  nop
0x18002266f  jmp     loc_1800225CB
0x180022674  mov     rcx, [rbp+var_18]
0x180022678  test    rcx, rcx
0x18002267b  jz      short loc_18002268A
0x18002267d  mov     rax, [rcx]
0x180022680  mov     rax, [rax+10h]
0x180022684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022689  nop
0x18002268a  mov     [rsp+68h+var_30], esi; unsigned int
0x18002268e  mov     [rsp+68h+var_38], r14d; unsigned int
0x180022693  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x180022698  lea     rax, psz; "WinSAT/WinSPR"
0x18002269f  mov     [rsp+68h+ppv], rax; psz
0x1800226a4  mov     r9b, 20h ; ' '; unsigned __int8
0x1800226a7  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x1800226ab  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x1800226af  mov     rcx, r15; this
0x1800226b2  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x1800226b7  mov     edi, eax
0x1800226b9  test    eax, eax
0x1800226bb  jns     short loc_1800226D8
0x1800226bd  mov     rcx, [rbp+var_20]
0x1800226c1  test    rcx, rcx
0x1800226c4  jz      short loc_1800226D3
0x1800226c6  mov     rdx, [rcx]
0x1800226c9  mov     rax, [rdx+10h]
0x1800226cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226d2  nop
0x1800226d3  jmp     loc_1800225CB
0x1800226d8  mov     [rsp+68h+var_30], esi; unsigned int
0x1800226dc  mov     [rsp+68h+var_38], r14d; unsigned int
0x1800226e1  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x1800226e6  lea     rax, aWinsatMetrics; "WinSAT/Metrics"
0x1800226ed  mov     [rsp+68h+ppv], rax; psz
0x1800226f2  mov     r9b, 22h ; '"'; unsigned __int8
0x1800226f5  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x1800226f9  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x1800226fd  mov     rcx, r15; this
0x180022700  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x180022705  mov     edi, eax
0x180022707  test    eax, eax
0x180022709  jns     short loc_180022726
0x18002270b  mov     rcx, [rbp+var_20]
0x18002270f  test    rcx, rcx
0x180022712  jz      short loc_180022721
0x180022714  mov     rdx, [rcx]
0x180022717  mov     rax, [rdx+10h]
0x18002271b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022720  nop
0x180022721  jmp     loc_1800225CB
0x180022726  mov     [rsp+68h+var_30], esi; unsigned int
0x18002272a  mov     [rsp+68h+var_38], r14d; unsigned int
0x18002272f  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x180022734  lea     rax, aWinsatSystemco; "WinSAT/SystemConfig"
0x18002273b  mov     [rsp+68h+ppv], rax; psz
0x180022740  mov     r9b, 24h ; '$'; unsigned __int8
0x180022743  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x180022747  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x18002274b  mov     rcx, r15; this
0x18002274e  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x180022753  mov     ebx, eax
0x180022755  test    eax, eax
0x180022757  jns     short loc_180022773
0x180022759  mov     rcx, [rbp+var_20]
0x18002275d  test    rcx, rcx
0x180022760  jz      short loc_18002276F
0x180022762  mov     rdx, [rcx]
0x180022765  mov     rax, [rdx+10h]
0x180022769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002276e  nop
0x18002276f  mov     eax, ebx
0x180022771  jmp     short loc_18002278B
0x180022773  mov     rcx, [rbp+var_20]
0x180022777  test    rcx, rcx
0x18002277a  jz      short loc_180022789
0x18002277c  mov     rax, [rcx]
0x18002277f  mov     rax, [rax+10h]
0x180022783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022788  nop
0x180022789  xor     eax, eax
0x18002278b  add     rsp, 68h
0x18002278f  pop     r15
0x180022791  pop     r14
0x180022793  pop     rdi
0x180022794  pop     rsi
0x180022795  pop     rbx
0x180022796  pop     rbp
0x180022797  retn
```
