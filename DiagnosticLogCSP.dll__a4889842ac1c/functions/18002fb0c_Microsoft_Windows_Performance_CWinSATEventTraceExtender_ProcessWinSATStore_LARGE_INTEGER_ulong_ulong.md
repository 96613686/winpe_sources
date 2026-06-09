# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATStore(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18002fb0c`
- end: `0x18002fd3c`
- name: `?ProcessWinSATStore@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `560`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f3c0`

## callees

- `0x18002f50c`
- `0x18002fb0c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fb4d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fb4d`

## string_xrefs

- `0x18002fcd8`: `WinSAT/SystemConfig`

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
0x18002fb0c  push    rbp
0x18002fb0e  push    rbx
0x18002fb0f  push    rsi
0x18002fb10  push    rdi
0x18002fb11  push    r14
0x18002fb13  push    r15
0x18002fb15  mov     rbp, rsp
0x18002fb18  sub     rsp, 68h
0x18002fb1c  mov     esi, r9d
0x18002fb1f  mov     r14d, r8d
0x18002fb22  mov     rbx, rdx
0x18002fb25  mov     r15, rcx
0x18002fb28  mov     [rbp+var_20], 0
0x18002fb30  lea     rax, [rbp+var_20]
0x18002fb34  mov     [rsp+68h+ppv], rax; ppv
0x18002fb39  lea     r9, _GUID_f8ad5d1f_3b47_4bdc_9375_7c6b1da4eca7; riid
0x18002fb40  xor     edx, edx; pUnkOuter
0x18002fb42  lea     r8d, [rdx+1]; dwClsContext
0x18002fb46  lea     rcx, _GUID_f3bdfad3_f276_49e9_9b17_c474f48f0764; rclsid
0x18002fb4d  call    cs:__imp_CoCreateInstance
0x18002fb53  mov     edi, eax
0x18002fb55  test    eax, eax
0x18002fb57  jns     short loc_18002FB76
0x18002fb59  mov     rcx, [rbp+var_20]
0x18002fb5d  test    rcx, rcx
0x18002fb60  jz      short loc_18002FB6F
0x18002fb62  mov     rdx, [rcx]
0x18002fb65  mov     rax, [rdx+10h]
0x18002fb69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb6e  nop
0x18002fb6f  mov     eax, edi
0x18002fb71  jmp     loc_18002FD2F
0x18002fb76  mov     [rbp+var_28], 0
0x18002fb7d  mov     [rbp+var_18], 0
0x18002fb85  mov     rcx, [rbp+var_20]
0x18002fb89  mov     rax, [rcx]
0x18002fb8c  lea     rdx, [rbp+var_18]
0x18002fb90  mov     rax, [rax+40h]
0x18002fb94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb99  mov     edi, eax
0x18002fb9b  test    eax, eax
0x18002fb9d  jns     short loc_18002FBCD
0x18002fb9f  mov     rcx, [rbp+var_18]
0x18002fba3  test    rcx, rcx
0x18002fba6  jz      short loc_18002FBB5
0x18002fba8  mov     rdx, [rcx]
0x18002fbab  mov     rax, [rdx+10h]
0x18002fbaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbb4  nop
0x18002fbb5  mov     rcx, [rbp+var_20]
0x18002fbb9  test    rcx, rcx
0x18002fbbc  jz      short loc_18002FBCB
0x18002fbbe  mov     rax, [rcx]
0x18002fbc1  mov     rax, [rax+10h]
0x18002fbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbca  nop
0x18002fbcb  jmp     short loc_18002FB6F
0x18002fbcd  mov     rcx, [rbp+var_18]
0x18002fbd1  mov     rax, [rcx]
0x18002fbd4  lea     rdx, [rbp+var_28]
0x18002fbd8  mov     rax, [rax+40h]
0x18002fbdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbe1  mov     edi, eax
0x18002fbe3  test    eax, eax
0x18002fbe5  jns     short loc_18002FC18
0x18002fbe7  mov     rcx, [rbp+var_18]
0x18002fbeb  test    rcx, rcx
0x18002fbee  jz      short loc_18002FBFD
0x18002fbf0  mov     rdx, [rcx]
0x18002fbf3  mov     rax, [rdx+10h]
0x18002fbf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbfc  nop
0x18002fbfd  mov     rcx, [rbp+var_20]
0x18002fc01  test    rcx, rcx
0x18002fc04  jz      short loc_18002FC13
0x18002fc06  mov     rax, [rcx]
0x18002fc09  mov     rax, [rax+10h]
0x18002fc0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc12  nop
0x18002fc13  jmp     loc_18002FB6F
0x18002fc18  mov     rcx, [rbp+var_18]
0x18002fc1c  test    rcx, rcx
0x18002fc1f  jz      short loc_18002FC2E
0x18002fc21  mov     rax, [rcx]
0x18002fc24  mov     rax, [rax+10h]
0x18002fc28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc2d  nop
0x18002fc2e  mov     [rsp+68h+var_30], esi; unsigned int
0x18002fc32  mov     [rsp+68h+var_38], r14d; unsigned int
0x18002fc37  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x18002fc3c  lea     rax, psz; "WinSAT/WinSPR"
0x18002fc43  mov     [rsp+68h+ppv], rax; psz
0x18002fc48  mov     r9b, 20h ; ' '; unsigned __int8
0x18002fc4b  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x18002fc4f  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x18002fc53  mov     rcx, r15; this
0x18002fc56  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x18002fc5b  mov     edi, eax
0x18002fc5d  test    eax, eax
0x18002fc5f  jns     short loc_18002FC7C
0x18002fc61  mov     rcx, [rbp+var_20]
0x18002fc65  test    rcx, rcx
0x18002fc68  jz      short loc_18002FC77
0x18002fc6a  mov     rdx, [rcx]
0x18002fc6d  mov     rax, [rdx+10h]
0x18002fc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc76  nop
0x18002fc77  jmp     loc_18002FB6F
0x18002fc7c  mov     [rsp+68h+var_30], esi; unsigned int
0x18002fc80  mov     [rsp+68h+var_38], r14d; unsigned int
0x18002fc85  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x18002fc8a  lea     rax, aWinsatMetrics; "WinSAT/Metrics"
0x18002fc91  mov     [rsp+68h+ppv], rax; psz
0x18002fc96  mov     r9b, 22h ; '"'; unsigned __int8
0x18002fc99  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x18002fc9d  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x18002fca1  mov     rcx, r15; this
0x18002fca4  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x18002fca9  mov     edi, eax
0x18002fcab  test    eax, eax
0x18002fcad  jns     short loc_18002FCCA
0x18002fcaf  mov     rcx, [rbp+var_20]
0x18002fcb3  test    rcx, rcx
0x18002fcb6  jz      short loc_18002FCC5
0x18002fcb8  mov     rdx, [rcx]
0x18002fcbb  mov     rax, [rdx+10h]
0x18002fcbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcc4  nop
0x18002fcc5  jmp     loc_18002FB6F
0x18002fcca  mov     [rsp+68h+var_30], esi; unsigned int
0x18002fcce  mov     [rsp+68h+var_38], r14d; unsigned int
0x18002fcd3  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x18002fcd8  lea     rax, aWinsatSystemco; "WinSAT/SystemConfig"
0x18002fcdf  mov     [rsp+68h+ppv], rax; psz
0x18002fce4  mov     r9b, 24h ; '$'; unsigned __int8
0x18002fce7  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x18002fceb  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x18002fcef  mov     rcx, r15; this
0x18002fcf2  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x18002fcf7  mov     ebx, eax
0x18002fcf9  test    eax, eax
0x18002fcfb  jns     short loc_18002FD17
0x18002fcfd  mov     rcx, [rbp+var_20]
0x18002fd01  test    rcx, rcx
0x18002fd04  jz      short loc_18002FD13
0x18002fd06  mov     rdx, [rcx]
0x18002fd09  mov     rax, [rdx+10h]
0x18002fd0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd12  nop
0x18002fd13  mov     eax, ebx
0x18002fd15  jmp     short loc_18002FD2F
0x18002fd17  mov     rcx, [rbp+var_20]
0x18002fd1b  test    rcx, rcx
0x18002fd1e  jz      short loc_18002FD2D
0x18002fd20  mov     rax, [rcx]
0x18002fd23  mov     rax, [rax+10h]
0x18002fd27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd2c  nop
0x18002fd2d  xor     eax, eax
0x18002fd2f  add     rsp, 68h
0x18002fd33  pop     r15
0x18002fd35  pop     r14
0x18002fd37  pop     rdi
0x18002fd38  pop     rsi
0x18002fd39  pop     rbx
0x18002fd3a  pop     rbp
0x18002fd3b  retn
```
