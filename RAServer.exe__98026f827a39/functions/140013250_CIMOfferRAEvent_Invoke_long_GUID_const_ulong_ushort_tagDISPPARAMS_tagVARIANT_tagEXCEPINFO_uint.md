# CIMOfferRAEvent::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x140013250`
- end: `0x140013755`
- name: `?Invoke@CIMOfferRAEvent@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `1285`
- prototype: `__int64 __fastcall(CIMOfferRAEvent *this, unsigned int, const struct _GUID *, __int64, unsigned __int16, struct tagDISPPARAMS *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400035c8`
- `0x14000e664`
- `0x14000e6a0`
- `0x14000e6fc`
- `0x14000e778`
- `0x140011b74`
- `0x140011bd8`
- `0x140012b4c`
- `0x140013250`
- `0x140015240`
- `0x140015400`
- `0x140015548`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140013512`
- `KERNEL32!GetLastError` at `0x1400136da`
- `KERNEL32!GetLastError` at `0x140013512`
- `KERNEL32!GetLastError` at `0x1400136da`
- `KERNEL32!CloseHandle` at `0x140013535`
- `KERNEL32!CloseHandle` at `0x14001371d`
- `KERNEL32!CloseHandle` at `0x140013535`
- `KERNEL32!CloseHandle` at `0x14001371d`
- `KERNEL32!HeapAlloc` at `0x14001342e`
- `KERNEL32!HeapAlloc` at `0x14001342e`
- `KERNEL32!GetProcessHeap` at `0x14001341c`
- `KERNEL32!GetProcessHeap` at `0x1400134fe`
- `KERNEL32!GetProcessHeap` at `0x14001341c`
- `KERNEL32!GetProcessHeap` at `0x1400134fe`
- `KERNEL32!CreateThread` at `0x1400134d1`
- `KERNEL32!CreateThread` at `0x1400136cf`
- `KERNEL32!CreateThread` at `0x1400134d1`
- `KERNEL32!CreateThread` at `0x1400136cf`
- `KERNEL32!HeapFree` at `0x14001350c`
- `KERNEL32!HeapFree` at `0x14001350c`
- `OLEAUT32!__imp_SysFreeString` at `0x14001330f`
- `OLEAUT32!__imp_SysFreeString` at `0x140013319`
- `OLEAUT32!__imp_SysFreeString` at `0x140013323`
- `OLEAUT32!__imp_SysFreeString` at `0x14001332b`
- `OLEAUT32!__imp_SysFreeString` at `0x140013390`
- `OLEAUT32!__imp_SysFreeString` at `0x1400134e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1400134f5`
- `OLEAUT32!__imp_SysFreeString` at `0x14001330f`
- `OLEAUT32!__imp_SysFreeString` at `0x140013319`
- `OLEAUT32!__imp_SysFreeString` at `0x140013323`
- `OLEAUT32!__imp_SysFreeString` at `0x14001332b`
- `OLEAUT32!__imp_SysFreeString` at `0x140013390`
- `OLEAUT32!__imp_SysFreeString` at `0x1400134e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1400134f5`

## string_xrefs

- `0x14001329d`: `base\diagnosis\ra\dcom\src\raimofferevnt.cpp`

## pseudocode

```c
__int64 __fastcall CIMOfferRAEvent::Invoke(
        CIMOfferRAEvent *this,
        unsigned int a2,
        const struct _GUID *a3,
        __int64 a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6)
{
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  CEventLogger *v11; // rcx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  int appended; // ebx
  unsigned __int16 **v17; // rax
  const struct _EVENT_DESCRIPTOR *v18; // rdx
  CEventLogger *v19; // rcx
  __int64 v20; // rcx
  unsigned int v21; // r9d
  signed int v22; // eax
  const struct _EVENT_DESCRIPTOR *v23; // rdx
  CEventLogger *v24; // rcx
  const OLECHAR *v25; // rax
  HANDLE ProcessHeap; // rax
  const struct _EVENT_DESCRIPTOR *v27; // rdx
  CEventLogger *v28; // rcx
  BSTR *v29; // rsi
  BSTR v30; // rax
  CEventLogger *v31; // rcx
  __int64 v32; // rcx
  BSTR *v33; // r14
  signed int v34; // eax
  const struct _EVENT_DESCRIPTOR *v35; // rdx
  CEventLogger *v36; // rcx
  HANDLE v37; // rax
  HANDLE v38; // rax
  signed int v39; // eax
  const struct _EVENT_DESCRIPTOR *v40; // rdx
  CEventLogger *v41; // rcx
  unsigned int v42; // r9d
  signed int v43; // eax
  const struct _EVENT_DESCRIPTOR *v44; // rdx
  CEventLogger *v45; // rcx
  __int64 v46; // rcx
  signed int v47; // eax
  const struct _EVENT_DESCRIPTOR *v48; // rdx
  unsigned int v49; // r8d
  __int64 v50; // rcx
  const struct _EVENT_DESCRIPTOR *v51; // rdx
  CEventLogger *v52; // rcx
  CEventLogger *v53; // rcx
  unsigned int v54; // r8d
  __int64 v55; // rcx
  signed int v56; // eax
  const struct _EVENT_DESCRIPTOR *v57; // rdx
  HANDLE Thread; // rax
  signed int LastError; // eax
  unsigned int v60; // [rsp+30h] [rbp-30h] BYREF
  BSTR v61; // [rsp+38h] [rbp-28h] BYREF
  BSTR v62; // [rsp+40h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-18h] BYREF
  BSTR v64; // [rsp+50h] [rbp-10h] BYREF
  __int64 v65; // [rsp+58h] [rbp-8h] BYREF
  int v66; // [rsp+98h] [rbp+38h] BYREF

  v65 = 0;
  v66 = 0;
  v61 = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v62, L"EndRendezvous");
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"Termination");
  CEventLogger::LogEvent(v9, v8, L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp", 0x17Bu, a2);
  v12 = a2 - 5;
  if ( !v12 )
  {
    CEventLogger::LogEvent(v11, &Enter_Conditional_Block, 0x180u, L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp");
    v50 = *((_QWORD *)this + 1);
    v60 = 0;
    if ( !v50 )
    {
      v21 = 394;
      goto LABEL_12;
    }
    appended = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v50 + 72LL))(v50, &v60);
    if ( appended < 0 )
      goto LABEL_6;
    CEventLogger::LogEvent(v52, v51, L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp", 0x193u, v60);
    v45 = (CEventLogger *)(v60 - 4);
    if ( v60 == 4 )
    {
      CEventLogger::LogEvent(
        v45,
        &Enter_Conditional_Block,
        0x1A8u,
        L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp");
      v55 = *((_QWORD *)this + 1);
      if ( !v55 )
      {
        v21 = 438;
        goto LABEL_12;
      }
      v56 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 40LL))(v55, &v66);
      appended = v56;
      if ( v56 < 0 )
      {
        CEventLogger::LogError(
          v53,
          v57,
          L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
          0x1BCu,
          L"CIMOfferRAEvent::Invoke",
          v56);
        goto LABEL_6;
      }
      if ( !v66 )
      {
        Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)IMOfferObtainTicket, this, 0, 0);
        if ( !Thread )
        {
          LastError = GetLastError();
          appended = LastError;
          if ( LastError > 0 )
            appended = (unsigned __int16)LastError | 0x80070000;
          v42 = 465;
LABEL_57:
          CEventLogger::LogError(
            v41,
            v40,
            L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
            v42,
            L"CIMOfferRAEvent::Invoke",
            appended);
          if ( appended >= 0 )
            goto LABEL_7;
          goto LABEL_6;
        }
        CloseHandle(Thread);
      }
      v54 = 473;
    }
    else
    {
      if ( v60 != 5 )
      {
LABEL_62:
        v49 = 501;
        goto LABEL_63;
      }
      CEventLogger::LogEvent(
        v45,
        &Enter_Conditional_Block,
        0x1DEu,
        L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp");
      CIMRequestRAEvent::Unadvise(this);
      CIMRequestRAEvent::CleanupSessionState(this, 0);
      v54 = 488;
    }
    CEventLogger::LogEvent(v53, &Exit_Conditional_Block, v54, L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp");
    goto LABEL_62;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    CIMRequestRAEvent::Unadvise(this);
    goto LABEL_64;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    CEventLogger::LogEvent(v11, &Enter_Conditional_Block, 0x1FEu, L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp");
    v17 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v64, a6->rgvarg->bstrVal);
    appended = ATL::CComBSTR::AppendBSTR(&v61, *v17);
    SysFreeString(v64);
    if ( appended < 0 )
    {
      CEventLogger::LogError(
        v19,
        v18,
        L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
        0x203u,
        L"CIMOfferRAEvent::Invoke",
        appended);
      goto LABEL_6;
    }
    v20 = *((_QWORD *)this + 1);
    if ( !v20 )
    {
      v21 = 526;
LABEL_12:
      appended = -2147418113;
      CEventLogger::LogError(
        0,
        v18,
        L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
        v21,
        L"CIMOfferRAEvent::Invoke",
        0x8000FFFF);
      goto LABEL_6;
    }
    v22 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 40LL))(v20, &v66);
    appended = v22;
    if ( v22 < 0 )
    {
      CEventLogger::LogError(
        v24,
        v23,
        L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
        0x213u,
        L"CIMOfferRAEvent::Invoke",
        v22);
      goto LABEL_6;
    }
    if ( v66 )
    {
      v25 = ATL::CComBSTR::Copy((LPCSTR *)&v61);
      ATL::CComBSTR::operator=((BSTR *)this + 7, v25);
      ProcessHeap = GetProcessHeap();
      v29 = (BSTR *)HeapAlloc(ProcessHeap, 8u, 0x10u);
      if ( !v29 )
      {
        appended = -2147024882;
        CEventLogger::LogError(
          v28,
          v27,
          L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
          0x225u,
          L"CIMOfferRAEvent::Invoke",
          0x8007000E);
        goto LABEL_6;
      }
      v30 = ATL::CComBSTR::Copy((LPCSTR *)this + 7);
      *v29 = v30;
      if ( !v30 )
      {
        appended = -2147024882;
        CEventLogger::LogError(
          v31,
          v18,
          L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
          0x22Bu,
          L"CIMOfferRAEvent::Invoke",
          0x8007000E);
        goto LABEL_6;
      }
      v32 = *((_QWORD *)this + 1);
      if ( !v32 )
      {
        v21 = 562;
        goto LABEL_12;
      }
      v33 = v29 + 1;
      v34 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v32 + 32LL))(v32, v29 + 1);
      appended = v34;
      if ( v34 < 0 )
      {
        CEventLogger::LogError(
          v36,
          v35,
          L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
          0x236u,
          L"CIMOfferRAEvent::Invoke",
          v34);
        goto LABEL_6;
      }
      v37 = CreateThread(0, 0, PersistOfferRAObjectUntilConsumed, v29, 0, 0);
      if ( !v37 )
      {
        if ( *v29 )
        {
          SysFreeString(*v29);
          *v29 = 0;
        }
        if ( *v33 )
        {
          SysFreeString(*v33);
          *v33 = 0;
        }
        v38 = GetProcessHeap();
        HeapFree(v38, 0, v29);
        v39 = GetLastError();
        appended = v39;
        if ( v39 > 0 )
          appended = (unsigned __int16)v39 | 0x80070000;
        v42 = 589;
        goto LABEL_57;
      }
      CloseHandle(v37);
      v43 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1), v62);
      appended = v43;
      if ( v43 < 0 )
      {
        CEventLogger::LogError(
          v45,
          v44,
          L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
          0x264u,
          L"CIMOfferRAEvent::Invoke",
          v43);
        goto LABEL_6;
      }
    }
    else if ( ATL::CComBSTR::operator==(&v61, &v62) )
    {
      v46 = *((_QWORD *)this + 1);
      if ( !v46 )
      {
        v21 = 630;
        goto LABEL_12;
      }
      v47 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR))(*(_QWORD *)v46 + 64LL))(v46, 0, bstrString);
      appended = v47;
      if ( v47 < 0 )
      {
        CEventLogger::LogError(
          v45,
          v48,
          L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
          0x27Bu,
          L"CIMOfferRAEvent::Invoke",
          v47);
        goto LABEL_6;
      }
    }
    v49 = 642;
LABEL_63:
    CEventLogger::LogEvent(v45, &Exit_Conditional_Block, v49, L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp");
    goto LABEL_64;
  }
  if ( v14 != 1 )
  {
LABEL_64:
    appended = 0;
    goto LABEL_7;
  }
  CEventLogger::LogError(
    v11,
    v10,
    L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
    0x287u,
    L"CIMOfferRAEvent::Invoke",
    0);
  appended = -2147467259;
LABEL_6:
  CIMRequestRAEvent::CleanupSessionState(this, 1);
LABEL_7:
  SysFreeString(bstrString);
  SysFreeString(v62);
  SysFreeString(v61);
  SysFreeString(0);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v65);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140013250  mov     [rsp-28h+arg_0], rbx
0x140013255  mov     [rsp-28h+arg_10], rsi
0x14001325a  push    rbp
0x14001325b  push    rdi
0x14001325c  push    r12
0x14001325e  push    r14
0x140013260  push    r15
0x140013262  mov     rbp, rsp
0x140013265  sub     rsp, 60h
0x140013269  xor     r15d, r15d
0x14001326c  mov     ebx, edx
0x14001326e  mov     rdi, rcx
0x140013271  mov     [rbp+var_8], r15
0x140013275  lea     rdx, aEndrendezvous; "EndRendezvous"
0x14001327c  mov     [rbp+arg_8], r15d
0x140013280  lea     rcx, [rbp+var_20]; this
0x140013284  mov     [rbp+var_28], r15
0x140013288  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14001328d  lea     rdx, aTermination; "Termination"
0x140013294  lea     rcx, [rbp+bstrString]; this
0x140013298  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14001329d  lea     r12, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\dcom\\src\\raimoff"...
0x1400132a4  mov     [rsp+60h+dwCreationFlags], ebx; unsigned int
0x1400132a8  mov     r8, r12; unsigned __int16 *
0x1400132ab  mov     r9d, 17Bh; unsigned int
0x1400132b1  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGII@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *,uint,uint)
0x1400132b6  sub     ebx, 5
0x1400132b9  jz      loc_1400135C4
0x1400132bf  sub     ebx, 1
0x1400132c2  jz      loc_1400135B7
0x1400132c8  sub     ebx, 1
0x1400132cb  jz      loc_140013355
0x1400132d1  cmp     ebx, 1
0x1400132d4  jnz     loc_14001374D
0x1400132da  lea     rax, aCimofferraeven_0; "CIMOfferRAEvent::Invoke"
0x1400132e1  mov     dword ptr [rsp+60h+lpThreadId], r15d; unsigned int
0x1400132e6  mov     r9d, 287h; unsigned int
0x1400132ec  mov     qword ptr [rsp+60h+dwCreationFlags], rax; unsigned __int16 *
0x1400132f1  mov     r8, r12; unsigned __int16 *
0x1400132f4  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400132f9  mov     ebx, 80004005h
0x1400132fe  mov     edx, 1; int
0x140013303  mov     rcx, rdi; this
0x140013306  call    ?CleanupSessionState@CIMRequestRAEvent@@QEAAXH@Z; CIMRequestRAEvent::CleanupSessionState(int)
0x14001330b  mov     rcx, [rbp+bstrString]; bstrString
0x14001330f  call    cs:__imp_SysFreeString
0x140013315  mov     rcx, [rbp+var_20]; bstrString
0x140013319  call    cs:__imp_SysFreeString
0x14001331f  mov     rcx, [rbp+var_28]; bstrString
0x140013323  call    cs:__imp_SysFreeString
0x140013329  xor     ecx, ecx; bstrString
0x14001332b  call    cs:__imp_SysFreeString
0x140013331  lea     rcx, [rbp+var_8]
0x140013335  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001333a  lea     r11, [rsp+60h+var_s0]
0x14001333f  mov     eax, ebx
0x140013341  mov     rbx, [r11+30h]
0x140013345  mov     rsi, [r11+40h]
0x140013349  mov     rsp, r11
0x14001334c  pop     r15
0x14001334e  pop     r14
0x140013350  pop     r12
0x140013352  pop     rdi
0x140013353  pop     rbp
0x140013354  retn
0x140013355  mov     r9, r12; unsigned __int16 *
0x140013358  lea     rdx, Enter_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x14001335f  mov     r8d, 1FEh; unsigned int
0x140013365  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x14001336a  mov     rax, [rbp+arg_28]
0x14001336e  lea     rcx, [rbp+var_10]; this
0x140013372  mov     rdx, [rax]
0x140013375  mov     rdx, [rdx+8]; unsigned __int16 *
0x140013379  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14001337e  lea     rcx, [rbp+var_28]; this
0x140013382  mov     rdx, [rax]; unsigned __int16 *
0x140013385  call    ?AppendBSTR@CComBSTR@ATL@@QEAAJPEAG@Z; ATL::CComBSTR::AppendBSTR(ushort *)
0x14001338a  mov     rcx, [rbp+var_10]; bstrString
0x14001338e  mov     ebx, eax
0x140013390  call    cs:__imp_SysFreeString
0x140013396  test    ebx, ebx
0x140013398  jns     short loc_1400133A6
0x14001339a  mov     dword ptr [rsp+60h+lpThreadId], ebx
0x14001339e  mov     r9d, 203h
0x1400133a4  jmp     short loc_1400133C2
0x1400133a6  mov     rcx, [rdi+8]; this
0x1400133aa  test    rcx, rcx
0x1400133ad  jnz     short loc_1400133DB
0x1400133af  mov     r9d, 20Eh; unsigned int
0x1400133b5  mov     ebx, 8000FFFFh
0x1400133ba  mov     dword ptr [rsp+60h+lpThreadId], 8000FFFFh; unsigned int
0x1400133c2  lea     rax, aCimofferraeven_0; "CIMOfferRAEvent::Invoke"
0x1400133c9  mov     r8, r12; unsigned __int16 *
0x1400133cc  mov     qword ptr [rsp+60h+dwCreationFlags], rax; unsigned __int16 *
0x1400133d1  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400133d6  jmp     loc_1400132FE
0x1400133db  mov     rax, [rcx]
0x1400133de  lea     rdx, [rbp+arg_8]
0x1400133e2  mov     rax, [rax+28h]
0x1400133e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400133eb  mov     ebx, eax
0x1400133ed  test    eax, eax
0x1400133ef  jns     short loc_1400133FD
0x1400133f1  mov     dword ptr [rsp+60h+lpThreadId], eax
0x1400133f5  mov     r9d, 213h
0x1400133fb  jmp     short loc_1400133C2
0x1400133fd  lea     rcx, [rbp+var_28]; this
0x140013401  cmp     [rbp+arg_8], r15d
0x140013405  jz      loc_140013564
0x14001340b  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x140013410  mov     rdx, rax
0x140013413  lea     rcx, [rdi+38h]
0x140013417  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x14001341c  call    cs:__imp_GetProcessHeap
0x140013422  mov     edx, 8; dwFlags
0x140013427  mov     rcx, rax; hHeap
0x14001342a  lea     r8d, [rdx+8]; dwBytes
0x14001342e  call    cs:__imp_HeapAlloc
0x140013434  mov     rsi, rax
0x140013437  test    rax, rax
0x14001343a  jnz     short loc_140013454
0x14001343c  mov     ebx, 8007000Eh
0x140013441  mov     dword ptr [rsp+60h+lpThreadId], 8007000Eh
0x140013449  mov     r9d, 225h
0x14001344f  jmp     loc_1400133C2
0x140013454  lea     rcx, [rdi+38h]; this
0x140013458  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x14001345d  mov     [rsi], rax
0x140013460  test    rax, rax
0x140013463  jnz     short loc_14001347D
0x140013465  mov     ebx, 8007000Eh
0x14001346a  mov     dword ptr [rsp+60h+lpThreadId], 8007000Eh
0x140013472  mov     r9d, 22Bh
0x140013478  jmp     loc_1400133C2
0x14001347d  mov     rcx, [rdi+8]
0x140013481  test    rcx, rcx
0x140013484  jnz     short loc_140013491
0x140013486  mov     r9d, 232h
0x14001348c  jmp     loc_1400133B5
0x140013491  mov     rax, [rcx]
0x140013494  lea     r14, [rsi+8]
0x140013498  mov     rdx, r14
0x14001349b  mov     rax, [rax+20h]
0x14001349f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400134a4  mov     ebx, eax
0x1400134a6  test    eax, eax
0x1400134a8  jns     short loc_1400134B9
0x1400134aa  mov     dword ptr [rsp+60h+lpThreadId], eax
0x1400134ae  mov     r9d, 236h
0x1400134b4  jmp     loc_1400133C2
0x1400134b9  mov     [rsp+60h+lpThreadId], r15; lpThreadId
0x1400134be  lea     r8, ?PersistOfferRAObjectUntilConsumed@@YAKPEAX@Z; lpStartAddress
0x1400134c5  mov     r9, rsi; lpParameter
0x1400134c8  mov     [rsp+60h+dwCreationFlags], r15d; dwCreationFlags
0x1400134cd  xor     edx, edx; dwStackSize
0x1400134cf  xor     ecx, ecx; lpThreadAttributes
0x1400134d1  call    cs:__imp_CreateThread
0x1400134d7  test    rax, rax
0x1400134da  jnz     short loc_140013532
0x1400134dc  mov     rcx, [rsi]; bstrString
0x1400134df  test    rcx, rcx
0x1400134e2  jz      short loc_1400134ED
0x1400134e4  call    cs:__imp_SysFreeString
0x1400134ea  mov     [rsi], r15
0x1400134ed  mov     rcx, [r14]; bstrString
0x1400134f0  test    rcx, rcx
0x1400134f3  jz      short loc_1400134FE
0x1400134f5  call    cs:__imp_SysFreeString
0x1400134fb  mov     [r14], r15
0x1400134fe  call    cs:__imp_GetProcessHeap
0x140013504  mov     r8, rsi; lpMem
0x140013507  xor     edx, edx; dwFlags
0x140013509  mov     rcx, rax; hHeap
0x14001350c  call    cs:__imp_HeapFree
0x140013512  call    cs:__imp_GetLastError
0x140013518  mov     ebx, eax
0x14001351a  test    eax, eax
0x14001351c  jle     short loc_140013527
0x14001351e  movzx   ebx, ax
0x140013521  or      ebx, 80070000h
0x140013527  mov     r9d, 24Dh
0x14001352d  jmp     loc_1400136F5
0x140013532  mov     rcx, rax; hObject
0x140013535  call    cs:__imp_CloseHandle
0x14001353b  mov     rcx, [rdi+8]
0x14001353f  mov     rdx, [rbp+var_20]
0x140013543  mov     rax, [rcx]
0x140013546  mov     rax, [rax+38h]
0x14001354a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001354f  mov     ebx, eax
0x140013551  test    eax, eax
0x140013553  jns     short loc_1400135AC
0x140013555  mov     dword ptr [rsp+60h+lpThreadId], eax
0x140013559  mov     r9d, 264h
0x14001355f  jmp     loc_1400133C2
0x140013564  lea     rdx, [rbp+var_20]
0x140013568  call    ??8CComBSTR@ATL@@QEBA_NAEBV01@@Z; ATL::CComBSTR::operator==(ATL::CComBSTR const &)
0x14001356d  test    al, al
0x14001356f  jz      short loc_1400135AC
0x140013571  mov     rcx, [rdi+8]
0x140013575  test    rcx, rcx
0x140013578  jnz     short loc_140013585
0x14001357a  mov     r9d, 276h
0x140013580  jmp     loc_1400133B5
0x140013585  mov     rax, [rcx]
0x140013588  xor     edx, edx
0x14001358a  mov     r8, [rbp+bstrString]
0x14001358e  mov     rax, [rax+40h]
0x140013592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013597  mov     ebx, eax
0x140013599  test    eax, eax
0x14001359b  jns     short loc_1400135AC
0x14001359d  mov     dword ptr [rsp+60h+lpThreadId], eax
0x1400135a1  mov     r9d, 27Bh
0x1400135a7  jmp     loc_1400133C2
0x1400135ac  mov     r8d, 282h
0x1400135b2  jmp     loc_14001373E
0x1400135b7  mov     rcx, rdi; this
0x1400135ba  call    ?Unadvise@CIMRequestRAEvent@@QEAAJXZ; CIMRequestRAEvent::Unadvise(void)
0x1400135bf  jmp     loc_14001374D
0x1400135c4  mov     r9, r12; unsigned __int16 *
0x1400135c7  lea     rdx, Enter_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x1400135ce  mov     r8d, 180h; unsigned int
0x1400135d4  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x1400135d9  mov     rcx, [rdi+8]
0x1400135dd  mov     [rbp+var_30], r15d
0x1400135e1  test    rcx, rcx
0x1400135e4  jnz     short loc_1400135F1
0x1400135e6  mov     r9d, 18Ah
0x1400135ec  jmp     loc_1400133B5
0x1400135f1  mov     rax, [rcx]
0x1400135f4  lea     rdx, [rbp+var_30]
0x1400135f8  mov     rax, [rax+48h]
0x1400135fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013601  mov     ebx, eax
0x140013603  test    eax, eax
0x140013605  js      loc_1400132FE
0x14001360b  mov     eax, [rbp+var_30]
0x14001360e  mov     r9d, 193h; unsigned int
0x140013614  mov     r8, r12; unsigned __int16 *
0x140013617  mov     [rsp+60h+dwCreationFlags], eax; unsigned int
0x14001361b  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGII@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *,uint,uint)
0x140013620  mov     ecx, [rbp+var_30]
0x140013623  sub     ecx, 4; this
0x140013626  jz      short loc_140013663
0x140013628  cmp     ecx, 1
0x14001362b  jnz     loc_140013738
0x140013631  mov     r9, r12; unsigned __int16 *
0x140013634  lea     rdx, Enter_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x14001363b  mov     r8d, 1DEh; unsigned int
0x140013641  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x140013646  mov     rcx, rdi; this
0x140013649  call    ?Unadvise@CIMRequestRAEvent@@QEAAJXZ; CIMRequestRAEvent::Unadvise(void)
0x14001364e  xor     edx, edx; int
0x140013650  mov     rcx, rdi; this
0x140013653  call    ?CleanupSessionState@CIMRequestRAEvent@@QEAAXH@Z; CIMRequestRAEvent::CleanupSessionState(int)
0x140013658  mov     r8d, 1E8h
0x14001365e  jmp     loc_140013729
0x140013663  mov     r9, r12; unsigned __int16 *
0x140013666  lea     rdx, Enter_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x14001366d  mov     r8d, 1A8h; unsigned int
0x140013673  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x140013678  mov     rcx, [rdi+8]
0x14001367c  test    rcx, rcx
0x14001367f  jnz     short loc_14001368C
0x140013681  mov     r9d, 1B6h
0x140013687  jmp     loc_1400133B5
0x14001368c  mov     rax, [rcx]
0x14001368f  lea     rdx, [rbp+arg_8]
0x140013693  mov     rax, [rax+28h]
0x140013697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001369c  mov     ebx, eax
0x14001369e  test    eax, eax
0x1400136a0  jns     short loc_1400136B1
0x1400136a2  mov     dword ptr [rsp+60h+lpThreadId], eax
0x1400136a6  mov     r9d, 1BCh
0x1400136ac  jmp     loc_1400133C2
0x1400136b1  cmp     [rbp+arg_8], r15d
0x1400136b5  jnz     short loc_140013723
0x1400136b7  mov     [rsp+60h+lpThreadId], r15; lpThreadId
0x1400136bc  lea     r8, ?IMOfferObtainTicket@@YAKPEAX@Z; lpStartAddress
0x1400136c3  mov     r9, rdi; lpParameter
0x1400136c6  mov     [rsp+60h+dwCreationFlags], r15d; dwCreationFlags
0x1400136cb  xor     edx, edx; dwStackSize
0x1400136cd  xor     ecx, ecx; lpThreadAttributes
0x1400136cf  call    cs:__imp_CreateThread
0x1400136d5  test    rax, rax
0x1400136d8  jnz     short loc_14001371A
0x1400136da  call    cs:__imp_GetLastError
0x1400136e0  mov     ebx, eax
0x1400136e2  test    eax, eax
0x1400136e4  jle     short loc_1400136EF
0x1400136e6  movzx   ebx, ax
0x1400136e9  or      ebx, 80070000h
0x1400136ef  mov     r9d, 1D1h; unsigned int
0x1400136f5  lea     rax, aCimofferraeven_0; "CIMOfferRAEvent::Invoke"
0x1400136fc  mov     dword ptr [rsp+60h+lpThreadId], ebx; unsigned int
0x140013700  mov     r8, r12; unsigned __int16 *
0x140013703  mov     qword ptr [rsp+60h+dwCreationFlags], rax; unsigned __int16 *
0x140013708  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
  ... truncated ...
```
