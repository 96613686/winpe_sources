# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140002934`
- end: `0x140002b94`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400026d8`

## callees

- `0x140002934`
- `0x140003b24`
- `0x1400042bc`
- `0x140004b60`
- `0x140005410`
- `0x14001346e`
- `0x140013530`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400029d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400029d5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002b62`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002b62`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002ad8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002ad8`

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
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x140002934  mov     [rsp-8+arg_18], rbx
0x140002939  push    rbp
0x14000293a  push    rsi
0x14000293b  push    rdi
0x14000293c  push    r12
0x14000293e  push    r13
0x140002940  push    r14
0x140002942  push    r15
0x140002944  lea     rbp, [rsp-13C0h]
0x14000294c  mov     eax, 14C0h
0x140002951  call    _alloca_probe
0x140002956  sub     rsp, rax
0x140002959  mov     rsi, [rbp+13F0h+arg_28]
0x140002960  mov     r15, r8
0x140002963  mov     r14d, edx
0x140002966  mov     r12, rcx
0x140002969  xor     edx, edx; Val
0x14000296b  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140002970  mov     r8d, 98h; Size
0x140002976  call    memset_0
0x14000297b  mov     rbx, [rbp+13F0h+arg_30]
0x140002982  xor     r13d, r13d
0x140002985  mov     [rbp+13F0h+OutputString], r13w
0x14000298d  mov     [rbp+13F0h+var_1430], r13b
0x140002991  mov     ecx, [rbx]; this
0x140002993  mov     eax, [rbx+4]
0x140002996  mov     [rsp+14F0h+var_14C8], ecx
0x14000299a  mov     [rsp+14F0h+var_14C4], eax
0x14000299e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400029a3  cmp     dword ptr [rbx+8], 1
0x1400029a7  mov     edi, eax
0x1400029a9  lea     eax, [r13+8]
0x1400029ad  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1400029b5  mov     ecx, r13d
0x1400029b8  cmovz   ecx, eax
0x1400029bb  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400029bf  lea     ecx, [rax-7]
0x1400029c2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400029ca  inc     ecx
0x1400029cc  mov     [rsp+14F0h+var_14B8], r13
0x1400029d1  mov     [rsp+14F0h+var_14C0], ecx
0x1400029d5  call    cs:__imp_GetCurrentThreadId
0x1400029db  xorps   xmm0, xmm0
0x1400029de  mov     [rsp+14F0h+var_1498], r15
0x1400029e3  mov     [rsp+14F0h+var_14B0], eax
0x1400029e7  xorps   xmm1, xmm1
0x1400029ea  xor     eax, eax
0x1400029ec  mov     [rsp+14F0h+var_1490], r14d
0x1400029f1  mov     [rbp+13F0h+var_1458], rax
0x1400029f5  mov     [rbp+13F0h+var_1470], rax
0x1400029f9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002a00  mov     [rsp+14F0h+var_148C], edi
0x140002a04  mov     [rsp+14F0h+var_14A8], r13
0x140002a09  mov     [rsp+14F0h+var_14A0], r13
0x140002a0e  mov     [rbp+13F0h+var_1448], rsi
0x140002a12  mov     [rbp+13F0h+var_1440], r12
0x140002a16  mov     [rsp+14F0h+var_1488], r13
0x140002a1b  movups  [rbp+13F0h+var_1468], xmm0
0x140002a1f  movups  [rsp+14F0h+var_1480], xmm1
0x140002a24  test    rax, rax
0x140002a27  jz      short loc_140002A34
0x140002a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a2e  mov     [rbp+13F0h+var_1450], rax
0x140002a32  jmp     short loc_140002A38
0x140002a34  mov     [rbp+13F0h+var_1450], r13
0x140002a38  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002a3f  test    rax, rax
0x140002a42  jz      short loc_140002A4E
0x140002a44  lea     rcx, [rsp+14F0h+var_14D0]
0x140002a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a4e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002a55  test    rax, rax
0x140002a58  jz      short loc_140002A6E
0x140002a5a  mov     r8d, 400h
0x140002a60  lea     rdx, [rbp+13F0h+var_1430]
0x140002a64  lea     rcx, [rsp+14F0h+var_14D0]
0x140002a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a6e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002a75  test    rax, rax
0x140002a78  jz      short loc_140002A84
0x140002a7a  lea     rcx, [rsp+14F0h+var_14D0]
0x140002a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a84  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002a8b  test    rax, rax
0x140002a8e  jz      short loc_140002AA1
0x140002a90  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002a95  jnz     short loc_140002AA1
0x140002a97  lea     rcx, [rsp+14F0h+var_14D0]
0x140002a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002aa1  cmp     [rsp+14F0h+var_14C8], r13d
0x140002aa6  jl      short loc_140002ABA
0x140002aa8  mov     ecx, 8000FFFFh; this
0x140002aad  mov     [rsp+14F0h+var_14C8], ecx
0x140002ab1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002ab6  mov     [rsp+14F0h+var_14C4], eax
0x140002aba  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140002ac1  jnz     short loc_140002AE2
0x140002ac3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002aca  test    rax, rax
0x140002acd  jz      short loc_140002AD8
0x140002acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ad4  test    al, al
0x140002ad6  jmp     short loc_140002AE0
0x140002ad8  call    cs:__imp_IsDebuggerPresent
0x140002ade  test    eax, eax
0x140002ae0  jz      short loc_140002AE9
0x140002ae2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002ae7  jz      short loc_140002B0F
0x140002ae9  mov     rax, cs:g_pfnResultLoggingCallback
0x140002af0  test    rax, rax
0x140002af3  jz      short loc_140002B68
0x140002af5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002afc  jnz     short loc_140002B68
0x140002afe  xor     r8d, r8d
0x140002b01  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b06  xor     edx, edx
0x140002b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b0d  jmp     short loc_140002B68
0x140002b0f  mov     rax, cs:g_pfnResultLoggingCallback
0x140002b16  mov     ebx, 800h
0x140002b1b  test    rax, rax
0x140002b1e  jz      short loc_140002B3D
0x140002b20  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002b27  jnz     short loc_140002B3D
0x140002b29  mov     r8d, ebx
0x140002b2c  lea     rdx, [rbp+13F0h+OutputString]
0x140002b33  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b3d  cmp     [rbp+13F0h+OutputString], r13w
0x140002b45  jnz     short loc_140002B5B
0x140002b47  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002b4c  mov     rdx, rbx; unsigned __int16 *
0x140002b4f  lea     rcx, [rbp+13F0h+OutputString]; this
0x140002b56  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002b5b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002b62  call    cs:__imp_OutputDebugStringW
0x140002b68  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002b6d  jnz     short loc_140002B78
0x140002b6f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140002b76  jz      short loc_140002B89
0x140002b78  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002b7f  test    rax, rax
0x140002b82  jz      short loc_140002B89
0x140002b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b89  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002b8e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
