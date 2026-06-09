# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140008188`
- end: `0x14000841c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140007c68`

## callees

- `0x140008188`
- `0x140009e34`
- `0x14000b234`
- `0x14000cbf0`
- `0x14000cdac`
- `0x14001094e`
- `0x140010980`
- `0x140010a10`
- `0x140011010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1400083b7`
- `KERNEL32!OutputDebugStringW` at `0x1400083b7`
- `KERNEL32!IsDebuggerPresent` at `0x14000832d`
- `KERNEL32!IsDebuggerPresent` at `0x14000832d`
- `KERNEL32!GetCurrentThreadId` at `0x140008232`
- `KERNEL32!GetCurrentThreadId` at `0x140008232`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x140008188  mov     [rsp-8+arg_10], rbx
0x14000818d  push    rbp
0x14000818e  push    rsi
0x14000818f  push    rdi
0x140008190  push    r14
0x140008192  push    r15
0x140008194  lea     rbp, [rsp-13D0h]
0x14000819c  mov     eax, 14D0h
0x1400081a1  call    _alloca_probe
0x1400081a6  sub     rsp, rax
0x1400081a9  mov     rax, cs:__security_cookie
0x1400081b0  xor     rax, rsp
0x1400081b3  mov     [rbp+13F0h+var_30], rax
0x1400081ba  mov     rdi, [rbp+13F0h+arg_28]
0x1400081c1  mov     esi, edx
0x1400081c3  mov     r14, rcx
0x1400081c6  xor     edx, edx; Val
0x1400081c8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400081cd  mov     r8d, 98h; Size
0x1400081d3  call    memset_0
0x1400081d8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400081df  xor     r15d, r15d
0x1400081e2  mov     [rbp+13F0h+OutputString], r15w
0x1400081ea  mov     [rbp+13F0h+var_1430], r15b
0x1400081ee  mov     ecx, [rdx]; this
0x1400081f0  mov     eax, [rdx+4]
0x1400081f3  mov     [rsp+14F0h+var_14C8], ecx
0x1400081f7  mov     [rsp+14F0h+var_14C4], eax
0x1400081fb  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140008200  cmp     dword ptr [rdx+8], 1
0x140008204  mov     ebx, eax
0x140008206  lea     eax, [r15+8]
0x14000820a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140008212  mov     ecx, r15d
0x140008215  cmovz   ecx, eax
0x140008218  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14000821c  lea     ecx, [rax-7]
0x14000821f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140008227  inc     ecx
0x140008229  mov     [rsp+14F0h+var_14B8], r15
0x14000822e  mov     [rsp+14F0h+var_14C0], ecx
0x140008232  call    cs:__imp_GetCurrentThreadId
0x140008238  xorps   xmm0, xmm0
0x14000823b  mov     [rsp+14F0h+var_1490], esi
0x14000823f  mov     [rsp+14F0h+var_14B0], eax
0x140008243  xorps   xmm1, xmm1
0x140008246  lea     rax, aWil; "wil"
0x14000824d  mov     [rsp+14F0h+var_148C], ebx
0x140008251  mov     [rsp+14F0h+var_1498], rax
0x140008256  xor     eax, eax
0x140008258  mov     [rbp+13F0h+var_1458], rax
0x14000825c  mov     [rbp+13F0h+var_1470], rax
0x140008260  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140008267  mov     [rsp+14F0h+var_14A8], r15
0x14000826c  mov     [rsp+14F0h+var_14A0], r15
0x140008271  mov     [rbp+13F0h+var_1448], rdi
0x140008275  mov     [rbp+13F0h+var_1440], r14
0x140008279  mov     [rsp+14F0h+var_1488], r15
0x14000827e  movups  [rbp+13F0h+var_1468], xmm0
0x140008282  movups  [rsp+14F0h+var_1480], xmm1
0x140008287  test    rax, rax
0x14000828a  jz      short loc_140008297
0x14000828c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008291  mov     [rbp+13F0h+var_1450], rax
0x140008295  jmp     short loc_14000829B
0x140008297  mov     [rbp+13F0h+var_1450], r15
0x14000829b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400082a2  test    rax, rax
0x1400082a5  jz      short loc_1400082B1
0x1400082a7  lea     rcx, [rsp+14F0h+var_14D0]
0x1400082ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400082b1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400082b8  test    rax, rax
0x1400082bb  jz      short loc_1400082D1
0x1400082bd  mov     r8d, 400h
0x1400082c3  lea     rdx, [rbp+13F0h+var_1430]
0x1400082c7  lea     rcx, [rsp+14F0h+var_14D0]
0x1400082cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400082d1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400082d8  test    rax, rax
0x1400082db  jz      short loc_1400082E7
0x1400082dd  lea     rcx, [rsp+14F0h+var_14D0]
0x1400082e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400082e7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400082ee  test    rax, rax
0x1400082f1  jz      short loc_140008304
0x1400082f3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400082f8  jnz     short loc_140008304
0x1400082fa  lea     rcx, [rsp+14F0h+var_14D0]
0x1400082ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008304  cmp     [rsp+14F0h+var_14C8], r15d
0x140008309  jge     loc_14000840B
0x14000830f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140008316  jnz     short loc_140008337
0x140008318  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000831f  test    rax, rax
0x140008322  jz      short loc_14000832D
0x140008324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008329  test    al, al
0x14000832b  jmp     short loc_140008335
0x14000832d  call    cs:__imp_IsDebuggerPresent
0x140008333  test    eax, eax
0x140008335  jz      short loc_14000833E
0x140008337  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000833c  jz      short loc_140008364
0x14000833e  mov     rax, cs:g_pfnResultLoggingCallback
0x140008345  test    rax, rax
0x140008348  jz      short loc_1400083BD
0x14000834a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140008351  jnz     short loc_1400083BD
0x140008353  xor     r8d, r8d
0x140008356  lea     rcx, [rsp+14F0h+var_14D0]
0x14000835b  xor     edx, edx
0x14000835d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008362  jmp     short loc_1400083BD
0x140008364  mov     rax, cs:g_pfnResultLoggingCallback
0x14000836b  mov     ebx, 800h
0x140008370  test    rax, rax
0x140008373  jz      short loc_140008392
0x140008375  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000837c  jnz     short loc_140008392
0x14000837e  mov     r8d, ebx
0x140008381  lea     rdx, [rbp+13F0h+OutputString]
0x140008388  lea     rcx, [rsp+14F0h+var_14D0]
0x14000838d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008392  cmp     [rbp+13F0h+OutputString], r15w
0x14000839a  jnz     short loc_1400083B0
0x14000839c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400083a1  mov     rdx, rbx; unsigned __int16 *
0x1400083a4  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400083ab  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400083b0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400083b7  call    cs:__imp_OutputDebugStringW
0x1400083bd  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400083c2  jnz     short loc_1400083CD
0x1400083c4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1400083cb  jz      short loc_1400083DE
0x1400083cd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400083d4  test    rax, rax
0x1400083d7  jz      short loc_1400083DE
0x1400083d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400083de  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1400083e3  jnz     short loc_140008411
0x1400083e5  mov     rcx, [rbp+13F0h+var_30]
0x1400083ec  xor     rcx, rsp; StackCookie
0x1400083ef  call    __security_check_cookie
0x1400083f4  mov     rbx, [rsp+14F0h+arg_10]
0x1400083fc  add     rsp, 14D0h
0x140008403  pop     r15
0x140008405  pop     r14
0x140008407  pop     rdi
0x140008408  pop     rsi
0x140008409  pop     rbp
0x14000840a  retn
0x14000840b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140008411  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140008416  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
