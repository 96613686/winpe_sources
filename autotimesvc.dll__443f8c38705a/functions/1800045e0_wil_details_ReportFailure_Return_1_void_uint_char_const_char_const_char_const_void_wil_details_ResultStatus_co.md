# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800045e0`
- end: `0x180004886`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003c30`

## callees

- `0x180002a70`
- `0x18000365c`
- `0x1800045e0`
- `0x1800069e4`
- `0x180008d60`
- `0x18000a198`
- `0x18000a348`
- `0x180010e00`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046a6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000479b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000479b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004825`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004825`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x1800045e0  push    rbp
0x1800045e2  push    rbx
0x1800045e3  push    rsi
0x1800045e4  push    rdi
0x1800045e5  push    r12
0x1800045e7  push    r14
0x1800045e9  push    r15
0x1800045eb  lea     rbp, [rsp-13D0h]
0x1800045f3  mov     eax, 14D0h
0x1800045f8  call    _alloca_probe
0x1800045fd  sub     rsp, rax
0x180004600  mov     rax, cs:__security_cookie
0x180004607  xor     rax, rsp
0x18000460a  mov     [rbp+1400h+var_40], rax
0x180004611  mov     rsi, r8
0x180004614  mov     edi, edx
0x180004616  mov     rbx, rcx
0x180004619  mov     r14, [rbp+1400h+arg_28]
0x180004620  xor     edx, edx; Val
0x180004622  mov     r8d, 98h; Size
0x180004628  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000462d  call    memset_0
0x180004632  nop
0x180004633  xor     r12d, r12d
0x180004636  mov     [rbp+1400h+OutputString], r12w
0x18000463e  mov     [rbp+1400h+var_1440], r12b
0x180004642  mov     rdx, [rbp+1400h+arg_30]; int
0x180004649  mov     ecx, [rdx]; this
0x18000464b  mov     [rsp+1500h+var_14D8], ecx
0x18000464f  mov     eax, [rdx+4]
0x180004652  mov     [rsp+1500h+var_14D4], eax
0x180004656  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000465b  mov     r15d, eax
0x18000465e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004666  mov     ecx, r12d
0x180004669  lea     eax, [r12+8]
0x18000466e  cmp     dword ptr [rdx+8], 1
0x180004672  cmovz   ecx, eax
0x180004675  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004679  lea     ecx, [rax-7]
0x18000467c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004684  inc     ecx
0x180004686  mov     [rsp+1500h+var_14D0], ecx
0x18000468a  mov     rcx, [rbp+1400h+arg_38]
0x180004691  test    rcx, rcx
0x180004694  jz      short loc_1800046A1
0x180004696  cmp     [rcx], r12w
0x18000469a  mov     [rsp+1500h+var_14C8], rcx
0x18000469f  jnz     short loc_1800046A6
0x1800046a1  mov     [rsp+1500h+var_14C8], r12
0x1800046a6  call    cs:__imp_GetCurrentThreadId
0x1800046ac  mov     [rsp+1500h+var_14C0], eax
0x1800046b0  mov     [rsp+1500h+var_14A8], rsi
0x1800046b5  mov     [rsp+1500h+var_14A0], edi
0x1800046b9  mov     [rsp+1500h+var_149C], r15d
0x1800046be  mov     [rsp+1500h+var_14B8], r12
0x1800046c3  mov     [rsp+1500h+var_14B0], r12
0x1800046c8  mov     [rbp+1400h+var_1458], r14
0x1800046cc  mov     [rbp+1400h+var_1450], rbx
0x1800046d0  mov     [rsp+1500h+var_1498], r12
0x1800046d5  xorps   xmm0, xmm0
0x1800046d8  xor     eax, eax
0x1800046da  movups  [rbp+1400h+var_1478], xmm0
0x1800046de  mov     [rbp+1400h+var_1468], rax
0x1800046e2  xorps   xmm1, xmm1
0x1800046e5  movups  [rsp+1500h+var_1490], xmm1
0x1800046ea  mov     [rbp+1400h+var_1480], rax
0x1800046ee  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800046f5  test    rax, rax
0x1800046f8  jz      short loc_180004705
0x1800046fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ff  mov     [rbp+1400h+var_1460], rax
0x180004703  jmp     short loc_180004709
0x180004705  mov     [rbp+1400h+var_1460], r12
0x180004709  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004710  test    rax, rax
0x180004713  jz      short loc_18000471F
0x180004715  lea     rcx, [rsp+1500h+var_14E0]
0x18000471a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000471f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004726  test    rax, rax
0x180004729  jz      short loc_18000473F
0x18000472b  mov     r8d, 400h
0x180004731  lea     rdx, [rbp+1400h+var_1440]
0x180004735  lea     rcx, [rsp+1500h+var_14E0]
0x18000473a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004746  test    rax, rax
0x180004749  jz      short loc_180004755
0x18000474b  lea     rcx, [rsp+1500h+var_14E0]
0x180004750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004755  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000475c  test    rax, rax
0x18000475f  jz      short loc_180004772
0x180004761  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004766  jnz     short loc_180004772
0x180004768  lea     rcx, [rsp+1500h+var_14E0]
0x18000476d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004772  cmp     [rsp+1500h+var_14D8], r12d
0x180004777  jge     loc_180004880
0x18000477d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004784  jnz     short loc_1800047A5
0x180004786  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000478d  test    rax, rax
0x180004790  jz      short loc_18000479B
0x180004792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004797  test    al, al
0x180004799  jmp     short loc_1800047A3
0x18000479b  call    cs:__imp_IsDebuggerPresent
0x1800047a1  test    eax, eax
0x1800047a3  jz      short loc_1800047AC
0x1800047a5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800047aa  jz      short loc_1800047D2
0x1800047ac  mov     rax, cs:g_pfnResultLoggingCallback
0x1800047b3  test    rax, rax
0x1800047b6  jz      short loc_18000482B
0x1800047b8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800047bf  jnz     short loc_18000482B
0x1800047c1  xor     r8d, r8d
0x1800047c4  xor     edx, edx
0x1800047c6  lea     rcx, [rsp+1500h+var_14E0]
0x1800047cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047d0  jmp     short loc_18000482B
0x1800047d2  mov     ebx, 800h
0x1800047d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800047de  test    rax, rax
0x1800047e1  jz      short loc_180004800
0x1800047e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800047ea  jnz     short loc_180004800
0x1800047ec  mov     r8d, ebx
0x1800047ef  lea     rdx, [rbp+1400h+OutputString]
0x1800047f6  lea     rcx, [rsp+1500h+var_14E0]
0x1800047fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004800  cmp     [rbp+1400h+OutputString], r12w
0x180004808  jnz     short loc_18000481E
0x18000480a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000480f  mov     rdx, rbx; unsigned __int16 *
0x180004812  lea     rcx, [rbp+1400h+OutputString]; this
0x180004819  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000481e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004825  call    cs:__imp_OutputDebugStringW
0x18000482b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004830  jnz     short loc_18000483B
0x180004832  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004839  jz      short loc_18000484D
0x18000483b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004842  test    rax, rax
0x180004845  jz      short loc_18000484D
0x180004847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000484c  nop
0x18000484d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004852  jnz     short loc_180004875
0x180004854  mov     rcx, [rbp+1400h+var_40]
0x18000485b  xor     rcx, rsp; StackCookie
0x18000485e  call    __security_check_cookie
0x180004863  add     rsp, 14D0h
0x18000486a  pop     r15
0x18000486c  pop     r14
0x18000486e  pop     r12
0x180004870  pop     rdi
0x180004871  pop     rsi
0x180004872  pop     rbx
0x180004873  pop     rbp
0x180004874  retn
0x180004875  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000487a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004880  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
