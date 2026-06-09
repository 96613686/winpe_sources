# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATStore(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18007ff7c`
- end: `0x1800800e0`
- name: `?ProcessWinSATStore@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `356`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *this, union _LARGE_INTEGER, unsigned int, __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007fab0`

## callees

- `0x180040a04`
- `0x18007fb4c`
- `0x18007ff7c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007ffc5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007ffc5`

## string_xrefs

- `0x1800800a3`: `WinSAT/SystemConfig`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATStore(
        Microsoft::Windows::Performance::CWinSATEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        __int16 a4)
{
  HRESULT Instance; // edi
  int v9; // eax
  __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 v11; // [rsp+40h] [rbp-28h] BYREF
  struct IQueryRecentWinSATAssessment *ppv; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v13[3]; // [rsp+50h] [rbp-18h] BYREF

  v13[1] = -2;
  ppv = 0;
  Instance = CoCreateInstance(
               &GUID_f3bdfad3_f276_49e9_9b17_c474f48f0764,
               0,
               1u,
               &GUID_f8ad5d1f_3b47_4bdc_9375_7c6b1da4eca7,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    v11 = WINSAT_ASSESSMENT_STATE_MIN;
    v13[0] = 0;
    Instance = ((__int64 (__fastcall *)(struct IQueryRecentWinSATAssessment *, _QWORD *))ppv->lpVtbl->get_Info)(
                 ppv,
                 v13);
    if ( Instance < 0
      || (Instance = (*(__int64 (__fastcall **)(_QWORD, __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *))(*(_QWORD *)v13[0] + 64LL))(
                       v13[0],
                       &v11),
          Instance < 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v13);
    }
    else
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v13);
      v9 = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
             this,
             ppv,
             v11,
             32,
             L"WinSAT/WinSPR",
             a2,
             a3,
             a4);
      if ( v9 < 0
        || (v9 = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
                   this,
                   ppv,
                   v11,
                   34,
                   L"WinSAT/Metrics",
                   a2,
                   a3,
                   a4),
            v9 < 0)
        || (v9 = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
                   this,
                   ppv,
                   v11,
                   36,
                   L"WinSAT/SystemConfig",
                   a2,
                   a3,
                   a4),
            v9 < 0) )
      {
        Instance = v9;
      }
      else
      {
        Instance = 0;
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18007ff7c  push    rbp
0x18007ff7e  push    rbx
0x18007ff7f  push    rsi
0x18007ff80  push    rdi
0x18007ff81  push    r14
0x18007ff83  push    r15
0x18007ff85  mov     rbp, rsp
0x18007ff88  sub     rsp, 68h
0x18007ff8c  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18007ff94  mov     esi, r9d
0x18007ff97  mov     r14d, r8d
0x18007ff9a  mov     rbx, rdx
0x18007ff9d  mov     r15, rcx
0x18007ffa0  mov     [rbp+var_20], 0
0x18007ffa8  lea     rax, [rbp+var_20]
0x18007ffac  mov     [rsp+68h+ppv], rax; ppv
0x18007ffb1  lea     r9, _GUID_f8ad5d1f_3b47_4bdc_9375_7c6b1da4eca7; riid
0x18007ffb8  xor     edx, edx; pUnkOuter
0x18007ffba  lea     r8d, [rdx+1]; dwClsContext
0x18007ffbe  lea     rcx, _GUID_f3bdfad3_f276_49e9_9b17_c474f48f0764; rclsid
0x18007ffc5  call    cs:__imp_CoCreateInstance
0x18007ffcb  mov     edi, eax
0x18007ffcd  test    eax, eax
0x18007ffcf  js      loc_1800800C8
0x18007ffd5  mov     [rbp+var_28], 0
0x18007ffdc  mov     [rbp+var_18], 0
0x18007ffe4  mov     rcx, [rbp+var_20]
0x18007ffe8  mov     rax, [rcx]
0x18007ffeb  lea     rdx, [rbp+var_18]
0x18007ffef  mov     rax, [rax+40h]
0x18007fff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fff8  mov     edi, eax
0x18007fffa  test    eax, eax
0x18007fffc  jns     short loc_18008000C
0x18007fffe  lea     rcx, [rbp+var_18]
0x180080002  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180080007  jmp     loc_1800800C8
0x18008000c  mov     rcx, [rbp+var_18]
0x180080010  mov     rax, [rcx]
0x180080013  lea     rdx, [rbp+var_28]
0x180080017  mov     rax, [rax+40h]
0x18008001b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080020  mov     edi, eax
0x180080022  lea     rcx, [rbp+var_18]
0x180080026  test    eax, eax
0x180080028  js      short loc_180080002
0x18008002a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18008002f  mov     [rsp+68h+var_30], esi; unsigned int
0x180080033  mov     [rsp+68h+var_38], r14d; unsigned int
0x180080038  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x18008003d  lea     rax, aWinsatWinspr; "WinSAT/WinSPR"
0x180080044  mov     [rsp+68h+ppv], rax; unsigned __int16 *
0x180080049  mov     r9b, 20h ; ' '; unsigned __int8
0x18008004c  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x180080050  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x180080054  mov     rcx, r15; this
0x180080057  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x18008005c  test    eax, eax
0x18008005e  jns     short loc_180080064
0x180080060  mov     edi, eax
0x180080062  jmp     short loc_1800800C8
0x180080064  mov     [rsp+68h+var_30], esi; unsigned int
0x180080068  mov     [rsp+68h+var_38], r14d; unsigned int
0x18008006d  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x180080072  lea     rax, aWinsatMetrics; "WinSAT/Metrics"
0x180080079  mov     [rsp+68h+ppv], rax; unsigned __int16 *
0x18008007e  mov     r9b, 22h ; '"'; unsigned __int8
0x180080081  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x180080085  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x180080089  mov     rcx, r15; this
0x18008008c  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x180080091  test    eax, eax
0x180080093  js      short loc_180080060
0x180080095  mov     [rsp+68h+var_30], esi; unsigned int
0x180080099  mov     [rsp+68h+var_38], r14d; unsigned int
0x18008009e  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x1800800a3  lea     rax, aWinsatSystemco; "WinSAT/SystemConfig"
0x1800800aa  mov     [rsp+68h+ppv], rax; unsigned __int16 *
0x1800800af  mov     r9b, 24h ; '$'; unsigned __int8
0x1800800b2  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x1800800b6  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x1800800ba  mov     rcx, r15; this
0x1800800bd  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x1800800c2  test    eax, eax
0x1800800c4  js      short loc_180080060
0x1800800c6  xor     edi, edi
0x1800800c8  lea     rcx, [rbp+var_20]
0x1800800cc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800800d1  mov     eax, edi
0x1800800d3  add     rsp, 68h
0x1800800d7  pop     r15
0x1800800d9  pop     r14
0x1800800db  pop     rdi
0x1800800dc  pop     rsi
0x1800800dd  pop     rbx
0x1800800de  pop     rbp
0x1800800df  retn
```
