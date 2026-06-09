# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATStore(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18001e7d8`
- end: `0x18001e975`
- name: `?ProcessWinSATStore@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `413`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e980`

## callees

- `0x18001e0e4`
- `0x18001e7d8`
- `0x180027910`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18001e828`
- `ole32!CoCreateInstance` at `0x18001e828`

## string_xrefs

- `0x18001e91c`: `WinSAT/SystemConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATStore(
        Microsoft::Windows::Performance::CWinSATEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        __int16 a4)
{
  int Instance; // edi
  __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 v10; // [rsp+40h] [rbp-20h] BYREF
  struct IQueryRecentWinSATAssessment *v11; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v12[2]; // [rsp+50h] [rbp-10h] BYREF

  v12[1] = -2;
  v11 = 0;
  Instance = CoCreateInstance(
               &GUID_f3bdfad3_f276_49e9_9b17_c474f48f0764,
               0,
               1u,
               &GUID_f8ad5d1f_3b47_4bdc_9375_7c6b1da4eca7,
               (LPVOID *)&v11);
  if ( Instance >= 0 )
  {
    v12[0] = 0;
    Instance = ((__int64 (__fastcall *)(struct IQueryRecentWinSATAssessment *, _QWORD *))v11->lpVtbl->get_Info)(
                 v11,
                 v12);
    if ( Instance >= 0
      && (Instance = (*(__int64 (__fastcall **)(_QWORD, __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *))(*(_QWORD *)v12[0] + 64LL))(
                       v12[0],
                       &v10),
          Instance >= 0) )
    {
      if ( v12[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12[0] + 16LL))(v12[0]);
      Instance = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
                   this,
                   v11,
                   v10,
                   32,
                   (OLECHAR *)L"WinSAT/WinSPR",
                   a2,
                   a3,
                   a4);
      if ( Instance >= 0 )
      {
        Instance = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
                     this,
                     v11,
                     v10,
                     34,
                     (OLECHAR *)L"WinSAT/Metrics",
                     a2,
                     a3,
                     a4);
        if ( Instance >= 0 )
        {
          Instance = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
                       this,
                       v11,
                       v10,
                       36,
                       (OLECHAR *)L"WinSAT/SystemConfig",
                       a2,
                       a3,
                       a4);
          if ( Instance >= 0 )
            Instance = 0;
        }
      }
    }
    else if ( v12[0] )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12[0] + 16LL))(v12[0]);
    }
  }
  if ( v11 )
    ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *))v11->lpVtbl->Release)(v11);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001e7d8  mov     r11, rsp
0x18001e7db  push    rbp
0x18001e7dc  push    r14
0x18001e7de  push    r15
0x18001e7e0  mov     rbp, rsp
0x18001e7e3  sub     rsp, 60h
0x18001e7e7  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x18001e7ef  mov     [r11+8], rbx
0x18001e7f3  mov     [r11+10h], rsi
0x18001e7f7  mov     [r11+18h], rdi
0x18001e7fb  mov     esi, r9d
0x18001e7fe  mov     r14d, r8d
0x18001e801  mov     rbx, rdx
0x18001e804  mov     r15, rcx
0x18001e807  and     [rbp+var_18], 0
0x18001e80c  lea     rax, [rbp+var_18]
0x18001e810  mov     [r11-58h], rax
0x18001e814  lea     r9, _GUID_f8ad5d1f_3b47_4bdc_9375_7c6b1da4eca7; riid
0x18001e81b  xor     edx, edx; pUnkOuter
0x18001e81d  lea     r8d, [rdx+1]; dwClsContext
0x18001e821  lea     rcx, _GUID_f3bdfad3_f276_49e9_9b17_c474f48f0764; rclsid
0x18001e828  call    cs:__imp_CoCreateInstance
0x18001e82e  mov     edi, eax
0x18001e830  test    eax, eax
0x18001e832  js      loc_18001E943
0x18001e838  and     [rbp+var_10], 0
0x18001e83d  mov     rcx, [rbp+var_18]
0x18001e841  mov     rax, [rcx]
0x18001e844  lea     rdx, [rbp+var_10]
0x18001e848  mov     rax, [rax+40h]
0x18001e84c  call    cs:__guard_dispatch_icall_fptr
0x18001e852  mov     edi, eax
0x18001e854  test    eax, eax
0x18001e856  js      short loc_18001E873
0x18001e858  mov     rcx, [rbp+var_10]
0x18001e85c  mov     rax, [rcx]
0x18001e85f  lea     rdx, [rbp+var_20]
0x18001e863  mov     rax, [rax+40h]
0x18001e867  call    cs:__guard_dispatch_icall_fptr
0x18001e86d  mov     edi, eax
0x18001e86f  test    eax, eax
0x18001e871  jns     short loc_18001E892
0x18001e873  mov     rcx, [rbp+var_10]
0x18001e877  test    rcx, rcx
0x18001e87a  jz      loc_18001E943
0x18001e880  mov     rax, [rcx]
0x18001e883  mov     rax, [rax+10h]
0x18001e887  call    cs:__guard_dispatch_icall_fptr
0x18001e88d  jmp     loc_18001E943
0x18001e892  mov     rcx, [rbp+var_10]
0x18001e896  test    rcx, rcx
0x18001e899  jz      short loc_18001E8A8
0x18001e89b  mov     rax, [rcx]
0x18001e89e  mov     rax, [rax+10h]
0x18001e8a2  call    cs:__guard_dispatch_icall_fptr
0x18001e8a8  mov     [rsp+60h+var_28], esi; unsigned int
0x18001e8ac  mov     [rsp+60h+var_30], r14d; unsigned int
0x18001e8b1  mov     qword ptr [rsp+60h+var_38], rbx; union _LARGE_INTEGER
0x18001e8b6  lea     rax, psz; "WinSAT/WinSPR"
0x18001e8bd  mov     [rsp+60h+psz], rax; psz
0x18001e8c2  mov     r9b, 20h ; ' '; unsigned __int8
0x18001e8c5  mov     r8d, [rbp+var_20]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x18001e8c9  mov     rdx, [rbp+var_18]; struct IQueryRecentWinSATAssessment *
0x18001e8cd  mov     rcx, r15; this
0x18001e8d0  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x18001e8d5  mov     edi, eax
0x18001e8d7  test    eax, eax
0x18001e8d9  js      short loc_18001E943
0x18001e8db  mov     [rsp+60h+var_28], esi; unsigned int
0x18001e8df  mov     [rsp+60h+var_30], r14d; unsigned int
0x18001e8e4  mov     qword ptr [rsp+60h+var_38], rbx; union _LARGE_INTEGER
0x18001e8e9  lea     rax, aWinsatMetrics; "WinSAT/Metrics"
0x18001e8f0  mov     [rsp+60h+psz], rax; psz
0x18001e8f5  mov     r9b, 22h ; '"'; unsigned __int8
0x18001e8f8  mov     r8d, [rbp+var_20]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x18001e8fc  mov     rdx, [rbp+var_18]; struct IQueryRecentWinSATAssessment *
0x18001e900  mov     rcx, r15; this
0x18001e903  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x18001e908  mov     edi, eax
0x18001e90a  test    eax, eax
0x18001e90c  js      short loc_18001E943
0x18001e90e  mov     [rsp+60h+var_28], esi; unsigned int
0x18001e912  mov     [rsp+60h+var_30], r14d; unsigned int
0x18001e917  mov     qword ptr [rsp+60h+var_38], rbx; union _LARGE_INTEGER
0x18001e91c  lea     rax, aWinsatSystemco; "WinSAT/SystemConfig"
0x18001e923  mov     [rsp+60h+psz], rax; psz
0x18001e928  mov     r9b, 24h ; '$'; unsigned __int8
0x18001e92b  mov     r8d, [rbp+var_20]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x18001e92f  mov     rdx, [rbp+var_18]; struct IQueryRecentWinSATAssessment *
0x18001e933  mov     rcx, r15; this
0x18001e936  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x18001e93b  mov     edi, eax
0x18001e93d  test    eax, eax
0x18001e93f  js      short loc_18001E943
0x18001e941  xor     edi, edi
0x18001e943  mov     rcx, [rbp+var_18]
0x18001e947  test    rcx, rcx
0x18001e94a  jz      short loc_18001E959
0x18001e94c  mov     rdx, [rcx]
0x18001e94f  mov     rax, [rdx+10h]
0x18001e953  call    cs:__guard_dispatch_icall_fptr
0x18001e959  mov     eax, edi
0x18001e95b  lea     r11, [rsp+60h+var_s0]
0x18001e960  mov     rbx, [r11+20h]
0x18001e964  mov     rsi, [r11+28h]
0x18001e968  mov     rdi, [r11+30h]
0x18001e96c  mov     rsp, r11
0x18001e96f  pop     r15
0x18001e971  pop     r14
0x18001e973  pop     rbp
0x18001e974  retn
```
