# CRDPEncConnectionMonitor::Initialize(IUnknown *)

- ea: `0x18004a360`
- end: `0x18004a6e7`
- name: `?Initialize@CRDPEncConnectionMonitor@@UEAAJPEAUIUnknown@@@Z`
- size: `903`
- prototype: `__int64 __fastcall(CRDPEncConnectionMonitor *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18004a180`

## callees

- `0x1800024a8`
- `0x18000f660`
- `0x18004a360`
- `0x180051870`
- `0x180076090`
- `0x180079770`
- `0x18007a404`
- `0x18007e9e0`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a470`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x18004a5e8`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x18004a613`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x18004a63c`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x18004a5e8`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x18004a613`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x18004a63c`
- `OLEAUT32!__imp_VariantInit` at `0x18004a3b2`
- `OLEAUT32!__imp_VariantInit` at `0x18004a3b2`
- `OLEAUT32!__imp_VariantClear` at `0x18004a6b9`
- `OLEAUT32!__imp_VariantClear` at `0x18004a6b9`

## pseudocode

```c
__int64 __fastcall CRDPEncConnectionMonitor::Initialize(CRDPEncConnectionMonitor *this, struct IUnknown *a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v5; // ebx
  unsigned int v6; // eax
  signed int LastError; // eax
  unsigned int v8; // eax
  int v9; // edx
  const char *v10; // rcx
  _QWORD *v11; // r14
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v17; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v18; // [rsp+48h] [rbp-B8h] BYREF
  int v19; // [rsp+4Ch] [rbp-B4h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+54h] [rbp-ACh] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-A8h] BYREF
  const char *v23; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v24[264]; // [rsp+80h] [rbp-80h] BYREF

  v17 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v16 = 0;
  v18 = 0;
  VariantInit(&pvarg);
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_48ccf58db2c73f5eef1819a5a1da481a_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"pPlatformContext",
        3);
    }
    v5 = -2147467261;
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_48ccf58db2c73f5eef1819a5a1da481a_Traceguids, v6);
  }
  if ( !(unsigned int)CTSCriticalSection::Initialize((CRDPEncConnectionMonitor *)((char *)this + 56)) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 16;
      v10 = "m_objLock.Initialize";
      goto LABEL_19;
    }
  }
  *((_DWORD *)this + 7) |= 2u;
  v11 = (_QWORD *)((char *)this + 72);
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IRDPENCPlatformContext,
         (char *)this + 72);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 18;
    v10 = "QueryInterface(IID_IRDPENCPlatformContext) failed!";
LABEL_19:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_48ccf58db2c73f5eef1819a5a1da481a_Traceguids,
      v8,
      (__int64)v10,
      v5);
    goto LABEL_43;
  }
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, unsigned int *))(*(_QWORD *)*v11 + 40LL))(
         *v11,
         L"MissedHeartbeatWarningCount",
         &v16) >= 0
    && v16 >= 4 )
  {
    *((_DWORD *)this + 25) = v16;
  }
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(*(_QWORD *)*v11 + 24LL))(
         *v11,
         L"RDP::TerminalName",
         &pvarg) >= 0
    && pvarg.vt == 8
    && StringCchPrintfW(
         v24,
         0x104u,
         L"%s\\%s",
         L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
         pvarg.llVal) >= 0 )
  {
    if ( (unsigned int)RDPENCHLPREG_ReadValueDWORD(-2147483646, v24, L"HeartbeatInterval", &v17) && v17 >= 0x1F4 )
      *((_DWORD *)this + 23) = v17;
    if ( (unsigned int)RDPENCHLPREG_ReadValueDWORD(-2147483646, v24, L"HeartbeatWarnCount", &v16) && v16 >= 4 )
      *((_DWORD *)this + 25) = v16;
    if ( (unsigned int)RDPENCHLPREG_ReadValueDWORD(-2147483646, v24, L"HeartbeatDropCount", &v18) && v18 >= 3 )
      *((_DWORD *)this + 26) = v18;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v19 = *((_DWORD *)this + 26);
    v20 = *((_DWORD *)this + 25);
    v21 = *((_DWORD *)this + 23);
    v23 = "Heartbeat";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)&dword_180294304,
      v13,
      v14,
      (__int64)&v23,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v19);
  }
  v5 = 0;
LABEL_43:
  VariantClear(&pvarg);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004a360  mov     [rsp-8+arg_10], rbx
0x18004a365  push    rbp
0x18004a366  push    rsi
0x18004a367  push    rdi
0x18004a368  push    r14
0x18004a36a  push    r15
0x18004a36c  lea     rbp, [rsp-1A0h]
0x18004a374  sub     rsp, 2A0h
0x18004a37b  mov     rax, cs:__security_cookie
0x18004a382  xor     rax, rsp
0x18004a385  mov     [rbp+1C0h+var_30], rax
0x18004a38c  xor     eax, eax
0x18004a38e  mov     rdi, rcx
0x18004a391  xorps   xmm0, xmm0
0x18004a394  mov     qword ptr [rsp+2C0h+pvarg+10h], rax
0x18004a399  lea     rcx, [rsp+2C0h+pvarg]; pvarg
0x18004a39e  mov     [rsp+2C0h+var_27C], eax
0x18004a3a2  movups  xmmword ptr [rsp+2C0h+pvarg], xmm0
0x18004a3a7  mov     [rsp+2C0h+var_280], eax
0x18004a3ab  mov     r15, rdx
0x18004a3ae  mov     [rsp+2C0h+var_278], eax
0x18004a3b2  call    cs:__imp_VariantInit
0x18004a3b8  test    r15, r15
0x18004a3bb  jnz     short loc_18004A41D
0x18004a3bd  mov     rax, cs:WPP_GLOBAL_Control
0x18004a3c4  lea     rsi, WPP_GLOBAL_Control
0x18004a3cb  cmp     rax, rsi
0x18004a3ce  jz      short loc_18004A413
0x18004a3d0  test    byte ptr [rax+1Ch], 8
0x18004a3d4  jz      short loc_18004A413
0x18004a3d6  cmp     byte ptr [rax+19h], 2
0x18004a3da  jb      short loc_18004A413
0x18004a3dc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004a3e1  lea     rcx, aPplatformconte; "pPlatformContext"
0x18004a3e8  mov     dword ptr [rsp+2C0h+var_298], 80004003h
0x18004a3f0  mov     [rsp+2C0h+var_2A0], rcx
0x18004a3f5  lea     edx, [r15+0Eh]
0x18004a3f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a400  lea     r8, WPP_48ccf58db2c73f5eef1819a5a1da481a_Traceguids
0x18004a407  mov     r9d, eax
0x18004a40a  mov     rcx, [rcx+10h]
0x18004a40e  call    WPP_SF_DsD
0x18004a413  mov     ebx, 80004003h
0x18004a418  jmp     loc_18004A6B4
0x18004a41d  mov     rax, cs:WPP_GLOBAL_Control
0x18004a424  lea     rsi, WPP_GLOBAL_Control
0x18004a42b  cmp     rax, rsi
0x18004a42e  jz      short loc_18004A463
0x18004a430  test    dword ptr [rax+1Ch], 800h
0x18004a437  jz      short loc_18004A463
0x18004a439  cmp     byte ptr [rax+19h], 4
0x18004a43d  jb      short loc_18004A463
0x18004a43f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004a444  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a44b  lea     r8, WPP_48ccf58db2c73f5eef1819a5a1da481a_Traceguids
0x18004a452  mov     edx, 0Fh
0x18004a457  mov     r9d, eax
0x18004a45a  mov     rcx, [rcx+10h]
0x18004a45e  call    WPP_SF_d
0x18004a463  lea     rcx, [rdi+38h]; this
0x18004a467  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18004a46c  test    eax, eax
0x18004a46e  jnz     short loc_18004A4E6
0x18004a470  call    cs:__imp_GetLastError
0x18004a476  mov     ebx, eax
0x18004a478  test    eax, eax
0x18004a47a  jle     short loc_18004A485
0x18004a47c  movzx   ebx, ax
0x18004a47f  or      ebx, 80070000h
0x18004a485  test    ebx, ebx
0x18004a487  jns     short loc_18004A4E6
0x18004a489  mov     rax, cs:WPP_GLOBAL_Control
0x18004a490  cmp     rax, rsi
0x18004a493  jz      loc_18004A6B4
0x18004a499  test    byte ptr [rax+1Ch], 8
0x18004a49d  jz      loc_18004A6B4
0x18004a4a3  cmp     byte ptr [rax+19h], 2
0x18004a4a7  jb      loc_18004A6B4
0x18004a4ad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004a4b2  mov     edx, 10h
0x18004a4b7  lea     rcx, aMObjlockInitia; "m_objLock.Initialize"
0x18004a4be  mov     dword ptr [rsp+2C0h+var_298], ebx
0x18004a4c2  lea     r8, WPP_48ccf58db2c73f5eef1819a5a1da481a_Traceguids
0x18004a4c9  mov     [rsp+2C0h+var_2A0], rcx
0x18004a4ce  mov     r9d, eax
0x18004a4d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a4d8  mov     rcx, [rcx+10h]
0x18004a4dc  call    WPP_SF_DsD
0x18004a4e1  jmp     loc_18004A6B4
0x18004a4e6  or      dword ptr [rdi+1Ch], 2
0x18004a4ea  lea     r14, [rdi+48h]
0x18004a4ee  mov     rax, [r15]
0x18004a4f1  lea     rdx, IID_IRDPENCPlatformContext
0x18004a4f8  mov     r8, r14
0x18004a4fb  mov     rcx, r15
0x18004a4fe  mov     rax, [rax]
0x18004a501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a506  mov     ebx, eax
0x18004a508  test    eax, eax
0x18004a50a  jns     short loc_18004A546
0x18004a50c  mov     rax, cs:WPP_GLOBAL_Control
0x18004a513  cmp     rax, rsi
0x18004a516  jz      loc_18004A6B4
0x18004a51c  test    byte ptr [rax+1Ch], 8
0x18004a520  jz      loc_18004A6B4
0x18004a526  cmp     byte ptr [rax+19h], 2
0x18004a52a  jb      loc_18004A6B4
0x18004a530  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004a535  mov     edx, 12h
0x18004a53a  lea     rcx, aQueryinterface_6; "QueryInterface(IID_IRDPENCPlatformConte"...
0x18004a541  jmp     loc_18004A4BE
0x18004a546  mov     rcx, [r14]
0x18004a549  lea     r8, [rsp+2C0h+var_280]
0x18004a54e  lea     rdx, aMissedheartbea; "MissedHeartbeatWarningCount"
0x18004a555  mov     rax, [rcx]
0x18004a558  mov     rax, [rax+28h]
0x18004a55c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a561  test    eax, eax
0x18004a563  js      short loc_18004A571
0x18004a565  mov     eax, [rsp+2C0h+var_280]
0x18004a569  cmp     eax, 4
0x18004a56c  jb      short loc_18004A571
0x18004a56e  mov     [rdi+64h], eax
0x18004a571  mov     rcx, [r14]
0x18004a574  lea     r8, [rsp+2C0h+pvarg]
0x18004a579  lea     rdx, aRdpTerminalnam; "RDP::TerminalName"
0x18004a580  mov     rax, [rcx]
0x18004a583  mov     rax, [rax+18h]
0x18004a587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a58c  test    eax, eax
0x18004a58e  js      loc_18004A652
0x18004a594  cmp     word ptr [rsp+2C0h+pvarg], 8
0x18004a59a  jnz     loc_18004A652
0x18004a5a0  mov     rax, qword ptr [rsp+2C0h+pvarg+8]
0x18004a5a5  lea     r9, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18004a5ac  lea     r8, aSS_0; "%s\\%s"
0x18004a5b3  mov     [rsp+2C0h+var_2A0], rax
0x18004a5b8  mov     edx, 104h; unsigned __int64
0x18004a5bd  lea     rcx, [rbp+1C0h+var_240]; unsigned __int16 *
0x18004a5c1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a5c6  test    eax, eax
0x18004a5c8  js      loc_18004A652
0x18004a5ce  mov     rbx, 0FFFFFFFF80000002h
0x18004a5d5  lea     r9, [rsp+2C0h+var_27C]
0x18004a5da  mov     rcx, rbx
0x18004a5dd  lea     r8, aHeartbeatinter; "HeartbeatInterval"
0x18004a5e4  lea     rdx, [rbp+1C0h+var_240]
0x18004a5e8  call    cs:__imp_RDPENCHLPREG_ReadValueDWORD
0x18004a5ee  test    eax, eax
0x18004a5f0  jz      short loc_18004A600
0x18004a5f2  mov     eax, [rsp+2C0h+var_27C]
0x18004a5f6  cmp     eax, 1F4h
0x18004a5fb  jb      short loc_18004A600
0x18004a5fd  mov     [rdi+5Ch], eax
0x18004a600  lea     r9, [rsp+2C0h+var_280]
0x18004a605  mov     rcx, rbx
0x18004a608  lea     r8, aHeartbeatwarnc; "HeartbeatWarnCount"
0x18004a60f  lea     rdx, [rbp+1C0h+var_240]
0x18004a613  call    cs:__imp_RDPENCHLPREG_ReadValueDWORD
0x18004a619  test    eax, eax
0x18004a61b  jz      short loc_18004A629
0x18004a61d  mov     eax, [rsp+2C0h+var_280]
0x18004a621  cmp     eax, 4
0x18004a624  jb      short loc_18004A629
0x18004a626  mov     [rdi+64h], eax
0x18004a629  lea     r9, [rsp+2C0h+var_278]
0x18004a62e  mov     rcx, rbx
0x18004a631  lea     r8, aHeartbeatdropc; "HeartbeatDropCount"
0x18004a638  lea     rdx, [rbp+1C0h+var_240]
0x18004a63c  call    cs:__imp_RDPENCHLPREG_ReadValueDWORD
0x18004a642  test    eax, eax
0x18004a644  jz      short loc_18004A652
0x18004a646  mov     eax, [rsp+2C0h+var_278]
0x18004a64a  cmp     eax, 3
0x18004a64d  jb      short loc_18004A652
0x18004a64f  mov     [rdi+68h], eax
0x18004a652  mov     eax, cs:CallbackContext
0x18004a658  cmp     eax, 4
0x18004a65b  jbe     short loc_18004A6B2
0x18004a65d  mov     eax, [rdi+68h]
0x18004a660  lea     rdx, dword_180294304
0x18004a667  mov     [rsp+2C0h+var_274], eax
0x18004a66b  mov     eax, [rdi+64h]
0x18004a66e  mov     [rsp+2C0h+var_270], eax
0x18004a672  mov     eax, [rdi+5Ch]
0x18004a675  mov     [rsp+2C0h+var_26C], eax
0x18004a679  lea     rax, aHeartbeat; "Heartbeat"
0x18004a680  mov     [rsp+2C0h+var_250], rax
0x18004a685  lea     rax, [rsp+2C0h+var_274]
0x18004a68a  mov     [rsp+2C0h+var_288], rax
0x18004a68f  lea     rax, [rsp+2C0h+var_270]
0x18004a694  mov     [rsp+2C0h+var_290], rax
0x18004a699  lea     rax, [rsp+2C0h+var_26C]
0x18004a69e  mov     [rsp+2C0h+var_298], rax
0x18004a6a3  lea     rax, [rsp+2C0h+var_250]
0x18004a6a8  mov     [rsp+2C0h+var_2A0], rax
0x18004a6ad  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004a6b2  xor     ebx, ebx
0x18004a6b4  lea     rcx, [rsp+2C0h+pvarg]; pvarg
0x18004a6b9  call    cs:__imp_VariantClear
0x18004a6bf  mov     eax, ebx
0x18004a6c1  mov     rcx, [rbp+1C0h+var_30]
0x18004a6c8  xor     rcx, rsp; StackCookie
0x18004a6cb  call    __security_check_cookie
0x18004a6d0  mov     rbx, [rsp+2C0h+arg_10]
0x18004a6d8  add     rsp, 2A0h
0x18004a6df  pop     r15
0x18004a6e1  pop     r14
0x18004a6e3  pop     rdi
0x18004a6e4  pop     rsi
0x18004a6e5  pop     rbp
0x18004a6e6  retn
```
