# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005030`
- end: `0x180005292`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004dd4`

## callees

- `0x180002134`
- `0x180005030`
- `0x180007294`
- `0x180007a30`
- `0x180008620`
- `0x18000a930`
- `0x18000bba0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050d2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800051d5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800051d5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000525f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000525f`

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
0x180005030  mov     [rsp-8+arg_18], rbx
0x180005035  push    rbp
0x180005036  push    rsi
0x180005037  push    rdi
0x180005038  push    r12
0x18000503a  push    r13
0x18000503c  push    r14
0x18000503e  push    r15
0x180005040  lea     rbp, [rsp-13C0h]
0x180005048  mov     eax, 14C0h
0x18000504d  call    _alloca_probe
0x180005052  sub     rsp, rax
0x180005055  mov     r15, r8
0x180005058  mov     r14d, edx
0x18000505b  mov     r12, rcx
0x18000505e  mov     rsi, [rbp+13F0h+arg_28]
0x180005065  xor     edx, edx; Val
0x180005067  mov     r8d, 98h; Size
0x18000506d  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005072  call    memset_0
0x180005077  nop
0x180005078  xor     r13d, r13d
0x18000507b  mov     [rbp+13F0h+OutputString], r13w
0x180005083  mov     [rbp+13F0h+var_1430], r13b
0x180005087  mov     rbx, [rbp+13F0h+arg_30]
0x18000508e  mov     ecx, [rbx]; this
0x180005090  mov     [rsp+14F0h+var_14C8], ecx
0x180005094  mov     eax, [rbx+4]
0x180005097  mov     [rsp+14F0h+var_14C4], eax
0x18000509b  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800050a0  mov     edi, eax
0x1800050a2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800050aa  mov     ecx, r13d
0x1800050ad  lea     eax, [r13+8]
0x1800050b1  cmp     dword ptr [rbx+8], 1
0x1800050b5  cmovz   ecx, eax
0x1800050b8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800050bc  lea     ecx, [rax-7]
0x1800050bf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800050c7  inc     ecx
0x1800050c9  mov     [rsp+14F0h+var_14C0], ecx
0x1800050cd  mov     [rsp+14F0h+var_14B8], r13
0x1800050d2  call    cs:__imp_GetCurrentThreadId
0x1800050d8  mov     [rsp+14F0h+var_14B0], eax
0x1800050dc  mov     [rsp+14F0h+var_1498], r15
0x1800050e1  mov     [rsp+14F0h+var_1490], r14d
0x1800050e6  mov     [rsp+14F0h+var_148C], edi
0x1800050ea  mov     [rsp+14F0h+var_14A8], r13
0x1800050ef  mov     [rsp+14F0h+var_14A0], r13
0x1800050f4  mov     [rbp+13F0h+var_1448], rsi
0x1800050f8  mov     [rbp+13F0h+var_1440], r12
0x1800050fc  mov     [rsp+14F0h+var_1488], r13
0x180005101  xorps   xmm0, xmm0
0x180005104  xor     eax, eax
0x180005106  movups  [rbp+13F0h+var_1468], xmm0
0x18000510a  mov     [rbp+13F0h+var_1458], rax
0x18000510e  xorps   xmm1, xmm1
0x180005111  movups  [rsp+14F0h+var_1480], xmm1
0x180005116  mov     [rbp+13F0h+var_1470], rax
0x18000511a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005121  test    rax, rax
0x180005124  jz      short loc_180005131
0x180005126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000512b  mov     [rbp+13F0h+var_1450], rax
0x18000512f  jmp     short loc_180005135
0x180005131  mov     [rbp+13F0h+var_1450], r13
0x180005135  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000513c  test    rax, rax
0x18000513f  jz      short loc_18000514B
0x180005141  lea     rcx, [rsp+14F0h+var_14D0]
0x180005146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000514b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005152  test    rax, rax
0x180005155  jz      short loc_18000516B
0x180005157  mov     r8d, 400h
0x18000515d  lea     rdx, [rbp+13F0h+var_1430]
0x180005161  lea     rcx, [rsp+14F0h+var_14D0]
0x180005166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000516b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005172  test    rax, rax
0x180005175  jz      short loc_180005181
0x180005177  lea     rcx, [rsp+14F0h+var_14D0]
0x18000517c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005181  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005188  test    rax, rax
0x18000518b  jz      short loc_18000519E
0x18000518d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005192  jnz     short loc_18000519E
0x180005194  lea     rcx, [rsp+14F0h+var_14D0]
0x180005199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000519e  cmp     [rsp+14F0h+var_14C8], r13d
0x1800051a3  jl      short loc_1800051B7
0x1800051a5  mov     ecx, 8000FFFFh; this
0x1800051aa  mov     [rsp+14F0h+var_14C8], ecx
0x1800051ae  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800051b3  mov     [rsp+14F0h+var_14C4], eax
0x1800051b7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800051be  jnz     short loc_1800051DF
0x1800051c0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800051c7  test    rax, rax
0x1800051ca  jz      short loc_1800051D5
0x1800051cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051d1  test    al, al
0x1800051d3  jmp     short loc_1800051DD
0x1800051d5  call    cs:__imp_IsDebuggerPresent
0x1800051db  test    eax, eax
0x1800051dd  jz      short loc_1800051E6
0x1800051df  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800051e4  jz      short loc_18000520C
0x1800051e6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800051ed  test    rax, rax
0x1800051f0  jz      short loc_180005265
0x1800051f2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800051f9  jnz     short loc_180005265
0x1800051fb  xor     r8d, r8d
0x1800051fe  xor     edx, edx
0x180005200  lea     rcx, [rsp+14F0h+var_14D0]
0x180005205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000520a  jmp     short loc_180005265
0x18000520c  mov     ebx, 800h
0x180005211  mov     rax, cs:g_pfnResultLoggingCallback
0x180005218  test    rax, rax
0x18000521b  jz      short loc_18000523A
0x18000521d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005224  jnz     short loc_18000523A
0x180005226  mov     r8d, ebx
0x180005229  lea     rdx, [rbp+13F0h+OutputString]
0x180005230  lea     rcx, [rsp+14F0h+var_14D0]
0x180005235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000523a  cmp     [rbp+13F0h+OutputString], r13w
0x180005242  jnz     short loc_180005258
0x180005244  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005249  mov     rdx, rbx; unsigned __int16 *
0x18000524c  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005253  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005258  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000525f  call    cs:__imp_OutputDebugStringW
0x180005265  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000526a  jnz     short loc_180005275
0x18000526c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180005273  jz      short loc_180005287
0x180005275  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000527c  test    rax, rax
0x18000527f  jz      short loc_180005287
0x180005281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005286  nop
0x180005287  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000528c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
