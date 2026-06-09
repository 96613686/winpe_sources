# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180004f10`
- end: `0x18000517e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `622`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180003da0`

## callees

- `0x1800022e0`
- `0x1800027c0`
- `0x180002990`
- `0x180003cc0`
- `0x180004f10`
- `0x18000b8d0`
- `0x18000b930`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004fa1`
- `KERNEL32!GetCurrentThreadId` at `0x180004fa1`
- `KERNEL32!OutputDebugStringW` at `0x18000514a`
- `KERNEL32!OutputDebugStringW` at `0x18000514a`
- `KERNEL32!IsDebuggerPresent` at `0x1800050b7`
- `KERNEL32!IsDebuggerPresent` at `0x1800050b7`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int IsDebuggerPresent; // r12d
  int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh]
  int v17; // [rsp+28h] [rbp-D8h]
  int v18; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v19; // [rsp+30h] [rbp-D0h]
  __int64 v20; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+48h] [rbp-B8h]
  __int64 v23; // [rsp+50h] [rbp-B0h]
  const char *v24; // [rsp+58h] [rbp-A8h]
  int v25; // [rsp+60h] [rbp-A0h]
  int v26; // [rsp+64h] [rbp-9Ch]
  __int64 v27; // [rsp+68h] [rbp-98h]
  __int128 v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+80h] [rbp-80h]
  __int128 v30; // [rsp+88h] [rbp-78h]
  __int64 v31; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+A8h] [rbp-58h]
  __int64 v34; // [rsp+B0h] [rbp-50h]
  char v35[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  IsDebuggerPresent = 0;
  OutputString[0] = 0;
  v35[0] = 0;
  v17 = *a7;
  v18 = a7[1];
  v10 = wil::details::RecordFailFast((wil::details *)(unsigned int)v17, a2);
  v15 = 3;
  v11 = 0;
  if ( a7[2] == 1 )
    v11 = 8;
  v16 = v11;
  v19 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v20 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v24 = "C:\\__w\\1\\s\\packages\\Microsoft.Windows.ImplementationLibrary.1.0.240803.1\\include\\wil\\resource.h";
  v25 = a2;
  v26 = v10;
  v22 = 0;
  v23 = 0;
  v33 = a6;
  v34 = a1;
  v27 = 0;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  v29 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v15, v35, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v15);
  if ( wil::details::g_pfnOriginateCallback && (v16 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v15);
  if ( v17 >= 0 )
  {
    v17 = -2147418113;
    v18 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13)),
         IsDebuggerPresent))
    && (v16 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v15, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v15, v14);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v15, 0, 0);
  }
  if ( (v16 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v13);
  }
  wil::details::WilFailFast((wil::details *)&v15, v12);
}

```

## disassembly

```asm
0x180004f10  mov     [rsp-8+arg_10], rbx
0x180004f15  mov     [rsp-8+arg_18], rsi
0x180004f1a  push    rbp
0x180004f1b  push    rdi
0x180004f1c  push    r12
0x180004f1e  push    r14
0x180004f20  push    r15
0x180004f22  lea     rbp, [rsp-13C0h]
0x180004f2a  mov     eax, 14C0h
0x180004f2f  call    _alloca_probe
0x180004f34  sub     rsp, rax
0x180004f37  mov     r14d, edx
0x180004f3a  mov     r15, rcx
0x180004f3d  mov     rsi, [rbp+13E0h+arg_28]
0x180004f44  xor     r12d, r12d
0x180004f47  mov     [rbp+13E0h+OutputString], r12w
0x180004f4f  mov     [rbp+13E0h+var_1420], r12b
0x180004f53  mov     rbx, [rbp+13E0h+arg_30]
0x180004f5a  mov     ecx, [rbx]; this
0x180004f5c  mov     [rsp+14E0h+var_14B8], ecx
0x180004f60  mov     eax, [rbx+4]
0x180004f63  mov     [rsp+14E0h+var_14B4], eax
0x180004f67  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004f6c  mov     edi, eax
0x180004f6e  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180004f76  mov     ecx, r12d
0x180004f79  mov     eax, 8
0x180004f7e  cmp     dword ptr [rbx+8], 1
0x180004f82  cmovz   ecx, eax
0x180004f85  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180004f89  mov     ecx, 1
0x180004f8e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004f96  inc     ecx
0x180004f98  mov     [rsp+14E0h+var_14B0], ecx
0x180004f9c  mov     [rsp+14E0h+var_14A8], r12
0x180004fa1  call    cs:__imp_GetCurrentThreadId
0x180004fa7  mov     [rsp+14E0h+var_14A0], eax
0x180004fab  lea     rax, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180004fb2  mov     [rsp+14E0h+var_1488], rax
0x180004fb7  mov     [rsp+14E0h+var_1480], r14d
0x180004fbc  mov     [rsp+14E0h+var_147C], edi
0x180004fc0  mov     [rsp+14E0h+var_1498], r12
0x180004fc5  mov     [rsp+14E0h+var_1490], r12
0x180004fca  mov     [rbp+13E0h+var_1438], rsi
0x180004fce  mov     [rbp+13E0h+var_1430], r15
0x180004fd2  mov     [rsp+14E0h+var_1478], r12
0x180004fd7  xorps   xmm0, xmm0
0x180004fda  xor     eax, eax
0x180004fdc  movups  [rbp+13E0h+var_1458], xmm0
0x180004fe0  mov     [rbp+13E0h+var_1448], rax
0x180004fe4  xorps   xmm1, xmm1
0x180004fe7  movups  [rsp+14E0h+var_1470], xmm1
0x180004fec  mov     [rbp+13E0h+var_1460], rax
0x180004ff0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004ff7  test    rax, rax
0x180004ffa  jz      short loc_180005008
0x180004ffc  call    cs:__guard_dispatch_icall_fptr
0x180005002  mov     [rbp+13E0h+var_1440], rax
0x180005006  jmp     short loc_18000500C
0x180005008  mov     [rbp+13E0h+var_1440], r12
0x18000500c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005013  test    rax, rax
0x180005016  jz      short loc_180005023
0x180005018  lea     rcx, [rsp+14E0h+var_14C0]
0x18000501d  call    cs:__guard_dispatch_icall_fptr
0x180005023  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000502a  test    rax, rax
0x18000502d  jz      short loc_180005044
0x18000502f  mov     r8d, 400h
0x180005035  lea     rdx, [rbp+13E0h+var_1420]
0x180005039  lea     rcx, [rsp+14E0h+var_14C0]
0x18000503e  call    cs:__guard_dispatch_icall_fptr
0x180005044  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000504b  test    rax, rax
0x18000504e  jz      short loc_18000505B
0x180005050  lea     rcx, [rsp+14E0h+var_14C0]
0x180005055  call    cs:__guard_dispatch_icall_fptr
0x18000505b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005062  test    rax, rax
0x180005065  jz      short loc_180005079
0x180005067  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000506c  jnz     short loc_180005079
0x18000506e  lea     rcx, [rsp+14E0h+var_14C0]
0x180005073  call    cs:__guard_dispatch_icall_fptr
0x180005079  cmp     [rsp+14E0h+var_14B8], r12d
0x18000507e  jl      short loc_180005096
0x180005080  mov     [rsp+14E0h+var_14B8], 8000FFFFh
0x180005088  mov     ecx, 8000FFFFh; this
0x18000508d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005092  mov     [rsp+14E0h+var_14B4], eax
0x180005096  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000509d  jnz     short loc_1800050C8
0x18000509f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800050a6  test    rax, rax
0x1800050a9  jz      short loc_1800050B7
0x1800050ab  call    cs:__guard_dispatch_icall_fptr
0x1800050b1  movzx   r12d, al
0x1800050b5  jmp     short loc_1800050C3
0x1800050b7  call    cs:__imp_IsDebuggerPresent
0x1800050bd  test    eax, eax
0x1800050bf  setnz   r12b
0x1800050c3  test    r12d, r12d
0x1800050c6  jz      short loc_1800050CF
0x1800050c8  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800050cd  jz      short loc_1800050F6
0x1800050cf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050d6  test    rax, rax
0x1800050d9  jz      short loc_180005150
0x1800050db  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1800050e2  jnz     short loc_180005150
0x1800050e4  xor     r8d, r8d
0x1800050e7  xor     edx, edx
0x1800050e9  lea     rcx, [rsp+14E0h+var_14C0]
0x1800050ee  call    cs:__guard_dispatch_icall_fptr
0x1800050f4  jmp     short loc_180005150
0x1800050f6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050fd  test    rax, rax
0x180005100  jz      short loc_180005123
0x180005102  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180005109  jnz     short loc_180005123
0x18000510b  mov     r8d, 800h
0x180005111  lea     rdx, [rbp+13E0h+OutputString]
0x180005118  lea     rcx, [rsp+14E0h+var_14C0]
0x18000511d  call    cs:__guard_dispatch_icall_fptr
0x180005123  cmp     [rbp+13E0h+OutputString], 0
0x18000512b  jnz     short loc_180005143
0x18000512d  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180005132  mov     edx, 800h; wchar_t *
0x180005137  lea     rcx, [rbp+13E0h+OutputString]; this
0x18000513e  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005143  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x18000514a  call    cs:__imp_OutputDebugStringW
0x180005150  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180005155  jnz     short loc_180005160
0x180005157  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x18000515e  jz      short loc_180005173
0x180005160  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005167  test    rax, rax
0x18000516a  jz      short loc_180005173
0x18000516c  call    cs:__guard_dispatch_icall_fptr
0x180005172  nop
0x180005173  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180005178  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
