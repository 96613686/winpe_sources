# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180002878`
- end: `0x180002b7b`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000226c`

## callees

- `0x180002234`
- `0x180002250`
- `0x1800023e8`
- `0x18000244c`
- `0x180002470`
- `0x180002484`
- `0x1800025bc`
- `0x180002878`
- `0x180002f28`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002abc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002abc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002b36`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002b36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000299d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000299d`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int *a8,
        _WORD *a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  unsigned int v18; // edi
  int v19; // esi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  int IsDebuggerPresent; // ecx
  wil::details *v28; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v19 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v20;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent()),
         IsDebuggerPresent))
    && (*(_BYTE *)(a16 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180002878  mov     [rsp+arg_10], rbx
0x18000287d  mov     [rsp+arg_8], edx
0x180002881  mov     [rsp+arg_0], rcx
0x180002886  push    rbp
0x180002887  push    rsi
0x180002888  push    rdi
0x180002889  push    r12
0x18000288b  push    r13
0x18000288d  push    r14
0x18000288f  push    r15
0x180002891  sub     rsp, 40h
0x180002895  mov     r12, r9
0x180002898  mov     r13, r8
0x18000289b  mov     r10, rcx
0x18000289e  xor     r8d, r8d
0x1800028a1  mov     r14, [rsp+78h+lpOutputString]
0x1800028a9  mov     [r14], r8w
0x1800028ad  mov     rax, [rsp+78h+arg_60]
0x1800028b5  mov     [rax], r8b
0x1800028b8  mov     r15, [rsp+78h+arg_38]
0x1800028c0  mov     edi, [r15]
0x1800028c3  mov     rbx, [rsp+78h+arg_78]
0x1800028cb  mov     [rbx+8], edi
0x1800028ce  mov     eax, [r15+4]
0x1800028d2  mov     [rbx+0Ch], eax
0x1800028d5  mov     esi, r8d
0x1800028d8  mov     ebp, [rsp+78h+arg_30]
0x1800028df  mov     ecx, ebp
0x1800028e1  test    ebp, ebp
0x1800028e3  jz      short loc_18000294E
0x1800028e5  sub     ecx, 1
0x1800028e8  jz      short loc_180002945
0x1800028ea  sub     ecx, 1
0x1800028ed  jz      short loc_1800028FD
0x1800028ef  cmp     ecx, 1
0x1800028f2  jnz     short loc_180002957
0x1800028f4  mov     ecx, edi; this
0x1800028f6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800028fb  jmp     short loc_180002955
0x1800028fd  test    edi, edi
0x1800028ff  js      short loc_18000293C
0x180002901  mov     edi, 8007029Ch
0x180002906  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000290a  mov     rax, [rsp+78h+arg_28]
0x180002912  mov     [rsp+78h+var_50], rax; __int64
0x180002917  mov     rax, [rsp+78h+arg_20]
0x18000291f  mov     [rsp+78h+var_58], rax; __int64
0x180002924  mov     r8, r13; int
0x180002927  mov     rcx, r10; int
0x18000292a  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000292f  mov     [rbx+8], edi
0x180002932  mov     ecx, edi; this
0x180002934  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002939  mov     [rbx+0Ch], eax
0x18000293c  mov     ecx, edi; this
0x18000293e  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180002943  jmp     short loc_180002955
0x180002945  mov     ecx, edi; this
0x180002947  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000294c  jmp     short loc_180002955
0x18000294e  mov     ecx, edi; this
0x180002950  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180002955  mov     esi, eax
0x180002957  mov     [rbx], ebp
0x180002959  mov     eax, [rsp+78h+arg_70]
0x180002960  mov     [rbx+4], eax
0x180002963  cmp     dword ptr [r15+8], 1
0x180002968  jnz     short loc_180002970
0x18000296a  or      eax, 8
0x18000296d  mov     [rbx+4], eax
0x180002970  mov     eax, 1
0x180002975  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000297d  inc     eax
0x18000297f  mov     [rbx+10h], eax
0x180002982  mov     rax, [rsp+78h+arg_40]
0x18000298a  xor     edi, edi
0x18000298c  test    rax, rax
0x18000298f  jz      short loc_180002996
0x180002991  cmp     [rax], di
0x180002994  jnz     short loc_180002999
0x180002996  mov     rax, rdi
0x180002999  mov     [rbx+18h], rax
0x18000299d  call    cs:__imp_GetCurrentThreadId
0x1800029a3  mov     [rbx+20h], eax
0x1800029a6  mov     [rbx+38h], r13
0x1800029aa  mov     eax, [rsp+78h+arg_8]
0x1800029b1  mov     [rbx+40h], eax
0x1800029b4  mov     [rbx+44h], esi
0x1800029b7  mov     rax, [rsp+78h+arg_20]
0x1800029bf  mov     [rbx+28h], rax
0x1800029c3  mov     [rbx+30h], r12
0x1800029c7  mov     rax, [rsp+78h+arg_28]
0x1800029cf  mov     [rbx+88h], rax
0x1800029d6  mov     rax, [rsp+78h+arg_0]
0x1800029de  mov     [rbx+90h], rax
0x1800029e5  mov     [rbx+48h], rdi
0x1800029e9  xorps   xmm0, xmm0
0x1800029ec  xor     eax, eax
0x1800029ee  movups  xmmword ptr [rbx+68h], xmm0
0x1800029f2  mov     [rbx+78h], rax
0x1800029f6  movups  xmmword ptr [rbx+50h], xmm0
0x1800029fa  mov     [rbx+60h], rax
0x1800029fe  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002a05  test    rax, rax
0x180002a08  jz      short loc_180002A11
0x180002a0a  call    _guard_dispatch_icall
0x180002a0f  jmp     short loc_180002A14
0x180002a11  mov     rax, rdi
0x180002a14  mov     [rbx+80h], rax
0x180002a1b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002a22  test    rax, rax
0x180002a25  jz      short loc_180002A2F
0x180002a27  mov     rcx, rbx
0x180002a2a  call    _guard_dispatch_icall
0x180002a2f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002a36  test    rax, rax
0x180002a39  jz      short loc_180002A51
0x180002a3b  mov     r8d, 400h
0x180002a41  mov     rdx, [rsp+78h+arg_60]
0x180002a49  mov     rcx, rbx
0x180002a4c  call    _guard_dispatch_icall
0x180002a51  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a58  test    rax, rax
0x180002a5b  jz      short loc_180002A65
0x180002a5d  mov     rcx, rbx
0x180002a60  call    _guard_dispatch_icall
0x180002a65  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a6c  test    rax, rax
0x180002a6f  jz      short loc_180002A7F
0x180002a71  test    byte ptr [rbx+4], 2
0x180002a75  jnz     short loc_180002A7F
0x180002a77  mov     rcx, rbx
0x180002a7a  call    _guard_dispatch_icall
0x180002a7f  cmp     [rbx+8], edi
0x180002a82  jl      short loc_180002A9D
0x180002a84  cmp     ebp, 3
0x180002a87  jnz     loc_180002B75
0x180002a8d  mov     ecx, 8000FFFFh; this
0x180002a92  mov     [rbx+8], ecx
0x180002a95  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002a9a  mov     [rbx+0Ch], eax
0x180002a9d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180002aa4  jnz     short loc_180002ACD
0x180002aa6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002aad  test    rax, rax
0x180002ab0  jz      short loc_180002ABC
0x180002ab2  call    _guard_dispatch_icall
0x180002ab7  movzx   ecx, al
0x180002aba  jmp     short loc_180002AC9
0x180002abc  call    cs:__imp_IsDebuggerPresent
0x180002ac2  mov     ecx, edi
0x180002ac4  test    eax, eax
0x180002ac6  setnz   cl
0x180002ac9  test    ecx, ecx
0x180002acb  jz      short loc_180002AD3
0x180002acd  test    byte ptr [rbx+4], 2
0x180002ad1  jz      short loc_180002AF7
0x180002ad3  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ada  test    rax, rax
0x180002add  jz      short loc_180002B3C
0x180002adf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180002ae6  jnz     short loc_180002B3C
0x180002ae8  xor     r8d, r8d
0x180002aeb  xor     edx, edx
0x180002aed  mov     rcx, rbx
0x180002af0  call    _guard_dispatch_icall
0x180002af5  jmp     short loc_180002B3C
0x180002af7  mov     esi, 800h
0x180002afc  mov     rax, cs:g_pfnResultLoggingCallback
0x180002b03  test    rax, rax
0x180002b06  jz      short loc_180002B1F
0x180002b08  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180002b0f  jnz     short loc_180002B1F
0x180002b11  mov     r8d, esi
0x180002b14  mov     rdx, r14
0x180002b17  mov     rcx, rbx
0x180002b1a  call    _guard_dispatch_icall
0x180002b1f  cmp     [r14], di
0x180002b23  jnz     short loc_180002B33
0x180002b25  mov     r8, rbx; unsigned __int64
0x180002b28  mov     rdx, rsi; wchar_t *
0x180002b2b  mov     rcx, r14; this
0x180002b2e  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180002b33  mov     rcx, r14; lpOutputString
0x180002b36  call    cs:__imp_OutputDebugStringW
0x180002b3c  test    byte ptr [rbx+4], 4
0x180002b40  jnz     short loc_180002B4B
0x180002b42  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180002b49  jz      short loc_180002B5D
0x180002b4b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002b52  test    rax, rax
0x180002b55  jz      short loc_180002B5D
0x180002b57  call    _guard_dispatch_icall
0x180002b5c  nop
0x180002b5d  mov     rbx, [rsp+78h+arg_10]
0x180002b65  add     rsp, 40h
0x180002b69  pop     r15
0x180002b6b  pop     r14
0x180002b6d  pop     r13
0x180002b6f  pop     r12
0x180002b71  pop     rdi
0x180002b72  pop     rsi
0x180002b73  pop     rbp
0x180002b74  retn
0x180002b75  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
