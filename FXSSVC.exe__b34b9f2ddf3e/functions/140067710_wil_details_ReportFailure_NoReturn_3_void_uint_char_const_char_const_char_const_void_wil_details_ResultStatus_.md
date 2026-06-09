# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140067710`
- end: `0x140067972`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400674b4`

## callees

- `0x140002c43`
- `0x140067710`
- `0x140069a44`
- `0x14006a1e0`
- `0x14006b090`
- `0x14006d180`
- `0x140081970`
- `0x140085010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400678b5`
- `KERNEL32!IsDebuggerPresent` at `0x1400678b5`
- `KERNEL32!OutputDebugStringW` at `0x14006793f`
- `KERNEL32!OutputDebugStringW` at `0x14006793f`
- `KERNEL32!GetCurrentThreadId` at `0x1400677b2`
- `KERNEL32!GetCurrentThreadId` at `0x1400677b2`

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
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x140067710  mov     [rsp-8+arg_18], rbx
0x140067715  push    rbp
0x140067716  push    rsi
0x140067717  push    rdi
0x140067718  push    r12
0x14006771a  push    r13
0x14006771c  push    r14
0x14006771e  push    r15
0x140067720  lea     rbp, [rsp-13C0h]
0x140067728  mov     eax, 14C0h
0x14006772d  call    _alloca_probe
0x140067732  sub     rsp, rax
0x140067735  mov     r15, r8
0x140067738  mov     r14d, edx
0x14006773b  mov     r12, rcx
0x14006773e  mov     rsi, [rbp+13F0h+arg_28]
0x140067745  xor     edx, edx; Val
0x140067747  mov     r8d, 98h; Size
0x14006774d  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140067752  call    memset_0
0x140067757  nop
0x140067758  xor     r13d, r13d
0x14006775b  mov     [rbp+13F0h+OutputString], r13w
0x140067763  mov     [rbp+13F0h+var_1430], r13b
0x140067767  mov     rbx, [rbp+13F0h+arg_30]
0x14006776e  mov     ecx, [rbx]; this
0x140067770  mov     [rsp+14F0h+var_14C8], ecx
0x140067774  mov     eax, [rbx+4]
0x140067777  mov     [rsp+14F0h+var_14C4], eax
0x14006777b  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140067780  mov     edi, eax
0x140067782  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x14006778a  mov     ecx, r13d
0x14006778d  lea     eax, [r13+8]
0x140067791  cmp     dword ptr [rbx+8], 1
0x140067795  cmovz   ecx, eax
0x140067798  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14006779c  lea     ecx, [rax-7]
0x14006779f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400677a7  inc     ecx
0x1400677a9  mov     [rsp+14F0h+var_14C0], ecx
0x1400677ad  mov     [rsp+14F0h+var_14B8], r13
0x1400677b2  call    cs:__imp_GetCurrentThreadId
0x1400677b8  mov     [rsp+14F0h+var_14B0], eax
0x1400677bc  mov     [rsp+14F0h+var_1498], r15
0x1400677c1  mov     [rsp+14F0h+var_1490], r14d
0x1400677c6  mov     [rsp+14F0h+var_148C], edi
0x1400677ca  mov     [rsp+14F0h+var_14A8], r13
0x1400677cf  mov     [rsp+14F0h+var_14A0], r13
0x1400677d4  mov     [rbp+13F0h+var_1448], rsi
0x1400677d8  mov     [rbp+13F0h+var_1440], r12
0x1400677dc  mov     [rsp+14F0h+var_1488], r13
0x1400677e1  xorps   xmm0, xmm0
0x1400677e4  xor     eax, eax
0x1400677e6  movups  [rbp+13F0h+var_1468], xmm0
0x1400677ea  mov     [rbp+13F0h+var_1458], rax
0x1400677ee  xorps   xmm1, xmm1
0x1400677f1  movups  [rsp+14F0h+var_1480], xmm1
0x1400677f6  mov     [rbp+13F0h+var_1470], rax
0x1400677fa  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140067801  test    rax, rax
0x140067804  jz      short loc_140067811
0x140067806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006780b  mov     [rbp+13F0h+var_1450], rax
0x14006780f  jmp     short loc_140067815
0x140067811  mov     [rbp+13F0h+var_1450], r13
0x140067815  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14006781c  test    rax, rax
0x14006781f  jz      short loc_14006782B
0x140067821  lea     rcx, [rsp+14F0h+var_14D0]
0x140067826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006782b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140067832  test    rax, rax
0x140067835  jz      short loc_14006784B
0x140067837  mov     r8d, 400h
0x14006783d  lea     rdx, [rbp+13F0h+var_1430]
0x140067841  lea     rcx, [rsp+14F0h+var_14D0]
0x140067846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006784b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140067852  test    rax, rax
0x140067855  jz      short loc_140067861
0x140067857  lea     rcx, [rsp+14F0h+var_14D0]
0x14006785c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067861  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140067868  test    rax, rax
0x14006786b  jz      short loc_14006787E
0x14006786d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140067872  jnz     short loc_14006787E
0x140067874  lea     rcx, [rsp+14F0h+var_14D0]
0x140067879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006787e  cmp     [rsp+14F0h+var_14C8], r13d
0x140067883  jl      short loc_140067897
0x140067885  mov     ecx, 8000FFFFh; this
0x14006788a  mov     [rsp+14F0h+var_14C8], ecx
0x14006788e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140067893  mov     [rsp+14F0h+var_14C4], eax
0x140067897  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x14006789e  jnz     short loc_1400678BF
0x1400678a0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400678a7  test    rax, rax
0x1400678aa  jz      short loc_1400678B5
0x1400678ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400678b1  test    al, al
0x1400678b3  jmp     short loc_1400678BD
0x1400678b5  call    cs:__imp_IsDebuggerPresent
0x1400678bb  test    eax, eax
0x1400678bd  jz      short loc_1400678C6
0x1400678bf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400678c4  jz      short loc_1400678EC
0x1400678c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1400678cd  test    rax, rax
0x1400678d0  jz      short loc_140067945
0x1400678d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400678d9  jnz     short loc_140067945
0x1400678db  xor     r8d, r8d
0x1400678de  xor     edx, edx
0x1400678e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1400678e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400678ea  jmp     short loc_140067945
0x1400678ec  mov     ebx, 800h
0x1400678f1  mov     rax, cs:g_pfnResultLoggingCallback
0x1400678f8  test    rax, rax
0x1400678fb  jz      short loc_14006791A
0x1400678fd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140067904  jnz     short loc_14006791A
0x140067906  mov     r8d, ebx
0x140067909  lea     rdx, [rbp+13F0h+OutputString]
0x140067910  lea     rcx, [rsp+14F0h+var_14D0]
0x140067915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006791a  cmp     [rbp+13F0h+OutputString], r13w
0x140067922  jnz     short loc_140067938
0x140067924  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140067929  mov     rdx, rbx; unsigned __int16 *
0x14006792c  lea     rcx, [rbp+13F0h+OutputString]; this
0x140067933  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140067938  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14006793f  call    cs:__imp_OutputDebugStringW
0x140067945  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14006794a  jnz     short loc_140067955
0x14006794c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140067953  jz      short loc_140067967
0x140067955  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14006795c  test    rax, rax
0x14006795f  jz      short loc_140067967
0x140067961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067966  nop
0x140067967  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14006796c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
