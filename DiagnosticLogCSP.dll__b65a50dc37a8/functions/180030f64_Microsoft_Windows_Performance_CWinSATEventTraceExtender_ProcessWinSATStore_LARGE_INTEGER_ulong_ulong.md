# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATStore(_LARGE_INTEGER,ulong,ulong)

- ea: `0x180030f64`
- end: `0x18003119b`
- name: `?ProcessWinSATStore@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `567`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800307d0`

## callees

- `0x180030930`
- `0x180030f64`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030fa5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030fa5`

## string_xrefs

- `0x180031136`: `WinSAT/SystemConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x180030f64  push    rbp
0x180030f66  push    rbx
0x180030f67  push    rsi
0x180030f68  push    rdi
0x180030f69  push    r14
0x180030f6b  push    r15
0x180030f6d  mov     rbp, rsp
0x180030f70  sub     rsp, 68h
0x180030f74  mov     esi, r9d
0x180030f77  mov     r14d, r8d
0x180030f7a  mov     rbx, rdx
0x180030f7d  mov     r15, rcx
0x180030f80  mov     [rbp+var_20], 0
0x180030f88  lea     rax, [rbp+var_20]
0x180030f8c  mov     [rsp+68h+ppv], rax; ppv
0x180030f91  lea     r9, _GUID_f8ad5d1f_3b47_4bdc_9375_7c6b1da4eca7; riid
0x180030f98  xor     edx, edx; pUnkOuter
0x180030f9a  lea     r8d, [rdx+1]; dwClsContext
0x180030f9e  lea     rcx, _GUID_f3bdfad3_f276_49e9_9b17_c474f48f0764; rclsid
0x180030fa5  call    cs:__imp_CoCreateInstance
0x180030fac  nop     dword ptr [rax+rax+00h]
0x180030fb1  mov     edi, eax
0x180030fb3  test    eax, eax
0x180030fb5  jns     short loc_180030FD4
0x180030fb7  mov     rcx, [rbp+var_20]
0x180030fbb  test    rcx, rcx
0x180030fbe  jz      short loc_180030FCD
0x180030fc0  mov     rdx, [rcx]
0x180030fc3  mov     rax, [rdx+10h]
0x180030fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030fcc  nop
0x180030fcd  mov     eax, edi
0x180030fcf  jmp     loc_18003118D
0x180030fd4  mov     [rbp+var_28], 0
0x180030fdb  mov     [rbp+var_18], 0
0x180030fe3  mov     rcx, [rbp+var_20]
0x180030fe7  mov     rax, [rcx]
0x180030fea  lea     rdx, [rbp+var_18]
0x180030fee  mov     rax, [rax+40h]
0x180030ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ff7  mov     edi, eax
0x180030ff9  test    eax, eax
0x180030ffb  jns     short loc_18003102B
0x180030ffd  mov     rcx, [rbp+var_18]
0x180031001  test    rcx, rcx
0x180031004  jz      short loc_180031013
0x180031006  mov     rdx, [rcx]
0x180031009  mov     rax, [rdx+10h]
0x18003100d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031012  nop
0x180031013  mov     rcx, [rbp+var_20]
0x180031017  test    rcx, rcx
0x18003101a  jz      short loc_180031029
0x18003101c  mov     rax, [rcx]
0x18003101f  mov     rax, [rax+10h]
0x180031023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031028  nop
0x180031029  jmp     short loc_180030FCD
0x18003102b  mov     rcx, [rbp+var_18]
0x18003102f  mov     rax, [rcx]
0x180031032  lea     rdx, [rbp+var_28]
0x180031036  mov     rax, [rax+40h]
0x18003103a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003103f  mov     edi, eax
0x180031041  test    eax, eax
0x180031043  jns     short loc_180031076
0x180031045  mov     rcx, [rbp+var_18]
0x180031049  test    rcx, rcx
0x18003104c  jz      short loc_18003105B
0x18003104e  mov     rdx, [rcx]
0x180031051  mov     rax, [rdx+10h]
0x180031055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003105a  nop
0x18003105b  mov     rcx, [rbp+var_20]
0x18003105f  test    rcx, rcx
0x180031062  jz      short loc_180031071
0x180031064  mov     rax, [rcx]
0x180031067  mov     rax, [rax+10h]
0x18003106b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031070  nop
0x180031071  jmp     loc_180030FCD
0x180031076  mov     rcx, [rbp+var_18]
0x18003107a  test    rcx, rcx
0x18003107d  jz      short loc_18003108C
0x18003107f  mov     rax, [rcx]
0x180031082  mov     rax, [rax+10h]
0x180031086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003108b  nop
0x18003108c  mov     [rsp+68h+var_30], esi; unsigned int
0x180031090  mov     [rsp+68h+var_38], r14d; unsigned int
0x180031095  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x18003109a  lea     rax, psz; "WinSAT/WinSPR"
0x1800310a1  mov     [rsp+68h+ppv], rax; psz
0x1800310a6  mov     r9b, 20h ; ' '; unsigned __int8
0x1800310a9  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x1800310ad  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x1800310b1  mov     rcx, r15; this
0x1800310b4  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x1800310b9  mov     edi, eax
0x1800310bb  test    eax, eax
0x1800310bd  jns     short loc_1800310DA
0x1800310bf  mov     rcx, [rbp+var_20]
0x1800310c3  test    rcx, rcx
0x1800310c6  jz      short loc_1800310D5
0x1800310c8  mov     rdx, [rcx]
0x1800310cb  mov     rax, [rdx+10h]
0x1800310cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310d4  nop
0x1800310d5  jmp     loc_180030FCD
0x1800310da  mov     [rsp+68h+var_30], esi; unsigned int
0x1800310de  mov     [rsp+68h+var_38], r14d; unsigned int
0x1800310e3  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x1800310e8  lea     rax, aWinsatMetrics; "WinSAT/Metrics"
0x1800310ef  mov     [rsp+68h+ppv], rax; psz
0x1800310f4  mov     r9b, 22h ; '"'; unsigned __int8
0x1800310f7  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x1800310fb  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x1800310ff  mov     rcx, r15; this
0x180031102  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x180031107  mov     edi, eax
0x180031109  test    eax, eax
0x18003110b  jns     short loc_180031128
0x18003110d  mov     rcx, [rbp+var_20]
0x180031111  test    rcx, rcx
0x180031114  jz      short loc_180031123
0x180031116  mov     rdx, [rcx]
0x180031119  mov     rax, [rdx+10h]
0x18003111d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031122  nop
0x180031123  jmp     loc_180030FCD
0x180031128  mov     [rsp+68h+var_30], esi; unsigned int
0x18003112c  mov     [rsp+68h+var_38], r14d; unsigned int
0x180031131  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x180031136  lea     rax, aWinsatSystemco; "WinSAT/SystemConfig"
0x18003113d  mov     [rsp+68h+ppv], rax; psz
0x180031142  mov     r9b, 24h ; '$'; unsigned __int8
0x180031145  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x180031149  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x18003114d  mov     rcx, r15; this
0x180031150  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x180031155  mov     ebx, eax
0x180031157  test    eax, eax
0x180031159  jns     short loc_180031175
0x18003115b  mov     rcx, [rbp+var_20]
0x18003115f  test    rcx, rcx
0x180031162  jz      short loc_180031171
0x180031164  mov     rdx, [rcx]
0x180031167  mov     rax, [rdx+10h]
0x18003116b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031170  nop
0x180031171  mov     eax, ebx
0x180031173  jmp     short loc_18003118D
0x180031175  mov     rcx, [rbp+var_20]
0x180031179  test    rcx, rcx
0x18003117c  jz      short loc_18003118B
0x18003117e  mov     rax, [rcx]
0x180031181  mov     rax, [rax+10h]
0x180031185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003118a  nop
0x18003118b  xor     eax, eax
0x18003118d  add     rsp, 68h
0x180031191  pop     r15
0x180031193  pop     r14
0x180031195  pop     rdi
0x180031196  pop     rsi
0x180031197  pop     rbx
0x180031198  pop     rbp
0x180031199  retn
```
