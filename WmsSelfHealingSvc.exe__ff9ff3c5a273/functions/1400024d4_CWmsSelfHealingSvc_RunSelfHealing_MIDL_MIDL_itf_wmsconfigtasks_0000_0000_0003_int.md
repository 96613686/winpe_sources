# CWmsSelfHealingSvc::RunSelfHealing(__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003,int *)

- ea: `0x1400024d4`
- end: `0x140002831`
- name: `?RunSelfHealing@CWmsSelfHealingSvc@@AEAAJW4__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003@@PEAH@Z`
- size: `861`
- prototype: `__int64 __fastcall(__int64, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400029e8`

## callees

- `0x1400024d4`
- `0x1400036a0`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x140006544`
- `0x14000c010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1400026b5`
- `KERNEL32!WaitForSingleObject` at `0x1400026b5`
- `KERNEL32!IsDebuggerPresent` at `0x1400025a9`
- `KERNEL32!IsDebuggerPresent` at `0x14000264f`
- `KERNEL32!IsDebuggerPresent` at `0x140002797`
- `KERNEL32!IsDebuggerPresent` at `0x1400025a9`
- `KERNEL32!IsDebuggerPresent` at `0x14000264f`
- `KERNEL32!IsDebuggerPresent` at `0x140002797`
- `KERNEL32!GetLastError` at `0x14000254e`
- `KERNEL32!GetLastError` at `0x14000273c`
- `KERNEL32!GetLastError` at `0x14000254e`
- `KERNEL32!GetLastError` at `0x14000273c`
- `KERNEL32!CreateEventW` at `0x14000253c`
- `KERNEL32!CreateEventW` at `0x14000253c`
- `KERNEL32!CloseHandle` at `0x140002802`
- `KERNEL32!CloseHandle` at `0x140002802`
- `ole32!CoCreateInstance` at `0x14000260a`
- `ole32!CoCreateInstance` at `0x14000260a`
- `OLEAUT32!__imp_VariantInit` at `0x140002516`
- `OLEAUT32!__imp_VariantInit` at `0x140002516`
- `OLEAUT32!__imp_VariantClear` at `0x1400027d2`
- `OLEAUT32!__imp_VariantClear` at `0x1400027d2`

## string_xrefs

- `0x1400026e0`: `CWmsSelfHealingSvc::RunSelfHealing - dwPercentCompleted = %i\n`

## pseudocode

```c
__int64 __fastcall CWmsSelfHealingSvc::RunSelfHealing(__int64 a1, unsigned int a2, _DWORD *a3)
{
  __int64 v5; // rax
  char *EventW; // r15
  signed int LastError; // eax
  signed int v8; // ebx
  unsigned int v9; // r13d
  bool v10; // zf
  const unsigned __int16 *v11; // rax
  HRESULT v12; // eax
  const wchar_t *v13; // rdx
  signed int v14; // eax
  LPVOID ppv; // [rsp+40h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v18; // [rsp+90h] [rbp+30h] BYREF
  int v19; // [rsp+94h] [rbp+34h]
  int v20; // [rsp+A8h] [rbp+48h] BYREF

  v19 = HIDWORD(a1);
  ppv = 0;
  v20 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v18 = 0;
  VariantInit(&pvarg);
  v5 = Utils::ExecutionModeToString(a2);
  DEBUGMSG(L"CWmsSelfHealingSvc::RunSelfHealing - eMode = %s\n", v5);
  EventW = (char *)CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = 267;
    if ( v8 >= 0 )
      v8 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      0x10Bu,
      L"CWmsSelfHealingSvc::RunSelfHealing",
      L"CBRAEx",
      L"hProgressEvent != 0",
      v8);
    v10 = !IsDebuggerPresent();
    v11 = L"hProgressEvent != 0";
LABEL_7:
    if ( v10 )
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        v9,
        L"CWmsSelfHealingSvc::RunSelfHealing",
        L"CBRAEx",
        v11,
        v8);
    else
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        v9,
        L"CWmsSelfHealingSvc::RunSelfHealing",
        L"CBRAEx",
        v11,
        v8);
    goto LABEL_28;
  }
  v12 = CoCreateInstance(&CLSID_WmsConfig, 0, 1u, &GUID_ba39869c_0ad9_4112_95b2_944730e430a9, &ppv);
  v8 = v12;
  if ( v12 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, VARIANTARG *, char *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           a2,
           &pvarg,
           EventW);
    if ( v8 < 0 )
      goto LABEL_28;
    while ( !WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v8 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 48LL))(ppv, &v18);
      if ( v8 < 0 )
        goto LABEL_28;
      DEBUGMSG(L"CWmsSelfHealingSvc::RunSelfHealing - dwPercentCompleted = %i\n", v18);
      if ( v18 >= 0x64 )
      {
        v8 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 56LL))(ppv, &v20);
        if ( v8 >= 0 )
        {
          v13 = L"TRUE";
          if ( !v20 )
            v13 = L"FALSE";
          DEBUGMSG(L"CWmsSelfHealingSvc::RunSelfHealing fRebootRequired = %s\n", v13);
          *a3 = v20;
        }
        goto LABEL_28;
      }
    }
    v14 = GetLastError();
    v8 = v14;
    if ( v14 > 0 )
      v8 = (unsigned __int16)v14 | 0x80070000;
    v9 = 280;
    if ( v8 >= 0 )
      v8 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      0x118u,
      L"CWmsSelfHealingSvc::RunSelfHealing",
      L"CBRAEx",
      L"dwWait == ((((DWORD )0x00000000L) ) + 0 )",
      v8);
    v10 = !IsDebuggerPresent();
    v11 = L"dwWait == ((((DWORD )0x00000000L) ) + 0 )";
    goto LABEL_7;
  }
  LOGASSERTHR(
    L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
    0x10Fu,
    L"CWmsSelfHealingSvc::RunSelfHealing",
    L"CHRA",
    L"hr",
    v12);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      271,
      L"CWmsSelfHealingSvc::RunSelfHealing",
      L"CHRA",
      L"hr",
      v8);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      271,
      L"CWmsSelfHealingSvc::RunSelfHealing",
      L"CHRA",
      L"hr",
      v8);
LABEL_28:
  VariantClear(&pvarg);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(EventW);
  DEBUGMSG(L"CWmsSelfHealingSvc::RunSelfHealing - hr = 0x%08X\n", (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400024d4  mov     [rsp-28h+arg_8], rbx
0x1400024d9  mov     [rsp-28h+arg_10], rsi
0x1400024de  mov     [rsp-28h+arg_0], rcx
0x1400024e3  push    rbp
0x1400024e4  push    rdi
0x1400024e5  push    r13
0x1400024e7  push    r14
0x1400024e9  push    r15
0x1400024eb  mov     rbp, rsp
0x1400024ee  sub     rsp, 60h
0x1400024f2  xor     eax, eax
0x1400024f4  mov     [rbp+var_20], 0
0x1400024fc  xorps   xmm0, xmm0
0x1400024ff  mov     qword ptr [rbp+pvarg+10h], rax
0x140002503  lea     rcx, [rbp+pvarg]; pvarg
0x140002507  mov     [rbp+arg_18], eax
0x14000250a  movups  xmmword ptr [rbp+pvarg], xmm0
0x14000250e  mov     dword ptr [rbp+arg_0], eax
0x140002511  mov     rsi, r8
0x140002514  mov     edi, edx
0x140002516  call    cs:__imp_VariantInit
0x14000251c  mov     ecx, edi
0x14000251e  call    ?ExecutionModeToString@Utils@@YAPEBGW4__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003@@@Z; Utils::ExecutionModeToString(__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003)
0x140002523  mov     rdx, rax
0x140002526  lea     rcx, aCwmsselfhealin_3; "CWmsSelfHealingSvc::RunSelfHealing - eM"...
0x14000252d  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002532  xor     r9d, r9d; lpName
0x140002535  xor     r8d, r8d; bInitialState
0x140002538  xor     edx, edx; bManualReset
0x14000253a  xor     ecx, ecx; lpEventAttributes
0x14000253c  call    cs:__imp_CreateEventW
0x140002542  mov     r15, rax
0x140002545  test    rax, rax
0x140002548  jnz     loc_1400025ED
0x14000254e  call    cs:__imp_GetLastError
0x140002554  mov     ebx, eax
0x140002556  test    eax, eax
0x140002558  jle     short loc_140002563
0x14000255a  movzx   ebx, ax
0x14000255d  or      ebx, 80070000h
0x140002563  mov     eax, 80004005h
0x140002568  lea     r14, aCbraex; "CBRAEx"
0x14000256f  test    ebx, ebx
0x140002571  lea     rsi, aCwmsselfhealin_19; "CWmsSelfHealingSvc::RunSelfHealing"
0x140002578  mov     r13d, 10Bh
0x14000257e  lea     rdi, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140002585  cmovns  ebx, eax
0x140002588  mov     r9, r14; unsigned __int16 *
0x14000258b  lea     rax, aHprogressevent; "hProgressEvent != 0"
0x140002592  mov     [rsp+60h+var_38], ebx; int
0x140002596  mov     r8, rsi; unsigned __int16 *
0x140002599  mov     [rsp+60h+ppv], rax; unsigned __int16 *
0x14000259e  mov     edx, r13d; unsigned int
0x1400025a1  mov     rcx, rdi; unsigned __int16 *
0x1400025a4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400025a9  call    cs:__imp_IsDebuggerPresent
0x1400025af  test    eax, eax
0x1400025b1  lea     rax, aHprogressevent; "hProgressEvent != 0"
0x1400025b8  jz      loc_1400027AB
0x1400025be  mov     [rsp+60h+var_28], ebx
0x1400025c2  mov     r9d, r13d
0x1400025c5  mov     [rsp+60h+var_30], rax
0x1400025ca  mov     qword ptr [rsp+60h+var_38], r14
0x1400025cf  mov     r8, rdi
0x1400025d2  mov     [rsp+60h+ppv], rsi
0x1400025d7  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400025de  mov     ecx, 2; unsigned __int8
0x1400025e3  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400025e8  jmp     loc_1400027CE
0x1400025ed  xor     edx, edx; pUnkOuter
0x1400025ef  lea     rax, [rbp+var_20]
0x1400025f3  lea     r9, _GUID_ba39869c_0ad9_4112_95b2_944730e430a9; riid
0x1400025fa  mov     [rsp+60h+ppv], rax; ppv
0x1400025ff  lea     rcx, CLSID_WmsConfig; rclsid
0x140002606  lea     r8d, [rdx+1]; dwClsContext
0x14000260a  call    cs:__imp_CoCreateInstance
0x140002610  mov     ebx, eax
0x140002612  test    eax, eax
0x140002614  jns     short loc_14000268C
0x140002616  mov     [rsp+60h+var_38], eax; int
0x14000261a  lea     rsi, aCwmsselfhealin_19; "CWmsSelfHealingSvc::RunSelfHealing"
0x140002621  mov     r14d, 10Fh
0x140002627  lea     rdi, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x14000262e  lea     r13, aHr; "hr"
0x140002635  mov     r8, rsi; unsigned __int16 *
0x140002638  mov     edx, r14d; unsigned int
0x14000263b  mov     [rsp+60h+ppv], r13; unsigned __int16 *
0x140002640  mov     rcx, rdi; unsigned __int16 *
0x140002643  lea     r9, aChra; "CHRA"
0x14000264a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000264f  call    cs:__imp_IsDebuggerPresent
0x140002655  test    eax, eax
0x140002657  lea     rax, aChra; "CHRA"
0x14000265e  jz      short loc_140002676
0x140002660  mov     [rsp+60h+var_28], ebx
0x140002664  mov     r9d, r14d
0x140002667  mov     [rsp+60h+var_30], r13
0x14000266c  mov     qword ptr [rsp+60h+var_38], rax
0x140002671  jmp     loc_1400025CF
0x140002676  mov     dword ptr [rsp+60h+var_30], ebx
0x14000267a  mov     r8d, r14d
0x14000267d  mov     qword ptr [rsp+60h+var_38], r13
0x140002682  mov     [rsp+60h+ppv], rax
0x140002687  jmp     loc_1400027BC
0x14000268c  mov     rcx, [rbp+var_20]
0x140002690  lea     r8, [rbp+pvarg]
0x140002694  mov     r9, r15
0x140002697  mov     edx, edi
0x140002699  mov     rax, [rcx]
0x14000269c  mov     rax, [rax+18h]
0x1400026a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026a5  mov     ebx, eax
0x1400026a7  test    eax, eax
0x1400026a9  js      loc_1400027CE
0x1400026af  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400026b2  mov     rcx, r15; hHandle
0x1400026b5  call    cs:__imp_WaitForSingleObject
0x1400026bb  test    eax, eax
0x1400026bd  jnz     short loc_14000273C
0x1400026bf  mov     rcx, [rbp+var_20]
0x1400026c3  lea     rdx, [rbp+arg_0]
0x1400026c7  mov     rax, [rcx]
0x1400026ca  mov     rax, [rax+30h]
0x1400026ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026d3  mov     ebx, eax
0x1400026d5  test    eax, eax
0x1400026d7  js      loc_1400027CE
0x1400026dd  mov     edx, dword ptr [rbp+arg_0]
0x1400026e0  lea     rcx, aCwmsselfhealin_12; "CWmsSelfHealingSvc::RunSelfHealing - dw"...
0x1400026e7  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400026ec  cmp     dword ptr [rbp+arg_0], 64h ; 'd'
0x1400026f0  jb      short loc_1400026AF
0x1400026f2  mov     rcx, [rbp+var_20]
0x1400026f6  lea     rdx, [rbp+arg_18]
0x1400026fa  mov     rax, [rcx]
0x1400026fd  mov     rax, [rax+38h]
0x140002701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002706  mov     ebx, eax
0x140002708  test    eax, eax
0x14000270a  js      loc_1400027CE
0x140002710  cmp     [rbp+arg_18], 0
0x140002714  lea     rax, aFalse; "FALSE"
0x14000271b  lea     rdx, aTrue; "TRUE"
0x140002722  cmovz   rdx, rax
0x140002726  lea     rcx, aCwmsselfhealin_14; "CWmsSelfHealingSvc::RunSelfHealing fReb"...
0x14000272d  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002732  mov     eax, [rbp+arg_18]
0x140002735  mov     [rsi], eax
0x140002737  jmp     loc_1400027CE
0x14000273c  call    cs:__imp_GetLastError
0x140002742  mov     ebx, eax
0x140002744  test    eax, eax
0x140002746  jle     short loc_140002751
0x140002748  movzx   ebx, ax
0x14000274b  or      ebx, 80070000h
0x140002751  mov     eax, 80004005h
0x140002756  lea     r14, aCbraex; "CBRAEx"
0x14000275d  test    ebx, ebx
0x14000275f  lea     rsi, aCwmsselfhealin_19; "CWmsSelfHealingSvc::RunSelfHealing"
0x140002766  mov     r13d, 118h
0x14000276c  lea     rdi, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140002773  cmovns  ebx, eax
0x140002776  mov     r9, r14; unsigned __int16 *
0x140002779  lea     rax, aDwwaitDword0x0; "dwWait == ((((DWORD )0x00000000L) ) + 0"...
0x140002780  mov     [rsp+60h+var_38], ebx; int
0x140002784  mov     r8, rsi; unsigned __int16 *
0x140002787  mov     [rsp+60h+ppv], rax; unsigned __int16 *
0x14000278c  mov     edx, r13d; unsigned int
0x14000278f  mov     rcx, rdi; unsigned __int16 *
0x140002792  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140002797  call    cs:__imp_IsDebuggerPresent
0x14000279d  test    eax, eax
0x14000279f  lea     rax, aDwwaitDword0x0; "dwWait == ((((DWORD )0x00000000L) ) + 0"...
0x1400027a6  jmp     loc_1400025B8
0x1400027ab  mov     dword ptr [rsp+60h+var_30], ebx
0x1400027af  mov     r8d, r13d
0x1400027b2  mov     qword ptr [rsp+60h+var_38], rax
0x1400027b7  mov     [rsp+60h+ppv], r14
0x1400027bc  mov     r9, rsi
0x1400027bf  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400027c6  mov     rdx, rdi
0x1400027c9  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400027ce  lea     rcx, [rbp+pvarg]; pvarg
0x1400027d2  call    cs:__imp_VariantClear
0x1400027d8  mov     rcx, [rbp+var_20]
0x1400027dc  test    rcx, rcx
0x1400027df  jz      short loc_1400027F5
0x1400027e1  mov     rax, [rcx]
0x1400027e4  mov     rax, [rax+10h]
0x1400027e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027ed  mov     [rbp+var_20], 0
0x1400027f5  lea     rax, [r15-1]
0x1400027f9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400027fd  ja      short loc_140002808
0x1400027ff  mov     rcx, r15; hObject
0x140002802  call    cs:__imp_CloseHandle
0x140002808  mov     edx, ebx
0x14000280a  lea     rcx, aCwmsselfhealin_13; "CWmsSelfHealingSvc::RunSelfHealing - hr"...
0x140002811  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002816  lea     r11, [rsp+60h+var_s0]
0x14000281b  mov     eax, ebx
0x14000281d  mov     rbx, [r11+38h]
0x140002821  mov     rsi, [r11+40h]
0x140002825  mov     rsp, r11
0x140002828  pop     r15
0x14000282a  pop     r14
0x14000282c  pop     r13
0x14000282e  pop     rdi
0x14000282f  pop     rbp
0x140002830  retn
```
