# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180026228`
- end: `0x180026521`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800259d8`
- `0x180025a8c`

## callees

- `0x180025920`
- `0x180025be0`
- `0x180026064`
- `0x180026228`
- `0x1800265a4`
- `0x1800265c0`
- `0x1800265d4`
- `0x1800265f0`
- `0x180026740`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002634b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002634b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800264dc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800264dc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002646a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002646a`

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
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
        v27)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x180026228  mov     [rsp+arg_10], rbx
0x18002622d  mov     [rsp+arg_8], edx
0x180026231  mov     [rsp+arg_0], rcx
0x180026236  push    rbp
0x180026237  push    rsi
0x180026238  push    rdi
0x180026239  push    r12
0x18002623b  push    r13
0x18002623d  push    r14
0x18002623f  push    r15
0x180026241  sub     rsp, 40h
0x180026245  mov     r12, r9
0x180026248  mov     r13, r8
0x18002624b  mov     r10, rcx
0x18002624e  xor     eax, eax
0x180026250  mov     rsi, [rsp+78h+lpOutputString]
0x180026258  mov     [rsi], ax
0x18002625b  mov     rax, [rsp+78h+arg_60]
0x180026263  mov     byte ptr [rax], 0
0x180026266  mov     r14, [rsp+78h+arg_38]
0x18002626e  mov     edi, [r14]
0x180026271  mov     rbx, [rsp+78h+arg_78]
0x180026279  mov     [rbx+8], edi
0x18002627c  mov     eax, [r14+4]
0x180026280  mov     [rbx+0Ch], eax
0x180026283  xor     ebp, ebp
0x180026285  mov     r15d, [rsp+78h+arg_30]
0x18002628d  mov     ecx, r15d
0x180026290  test    r15d, r15d
0x180026293  jz      short loc_1800262FB
0x180026295  sub     ecx, 1
0x180026298  jz      short loc_1800262F2
0x18002629a  sub     ecx, 1
0x18002629d  jz      short loc_1800262AD
0x18002629f  cmp     ecx, 1
0x1800262a2  jnz     short loc_180026304
0x1800262a4  mov     ecx, edi; this
0x1800262a6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800262ab  jmp     short loc_180026302
0x1800262ad  test    edi, edi
0x1800262af  js      short loc_1800262E9
0x1800262b1  mov     edi, 8007029Ch
0x1800262b6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800262ba  mov     rax, [rsp+78h+arg_28]
0x1800262c2  mov     [rsp+78h+var_50], rax; __int64
0x1800262c7  mov     rax, [rsp+78h+arg_20]
0x1800262cf  mov     [rsp+78h+var_58], rax; __int64
0x1800262d4  mov     rcx, r10; int
0x1800262d7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800262dc  mov     [rbx+8], edi
0x1800262df  mov     ecx, edi; this
0x1800262e1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800262e6  mov     [rbx+0Ch], eax
0x1800262e9  mov     ecx, edi; this
0x1800262eb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800262f0  jmp     short loc_180026302
0x1800262f2  mov     ecx, edi; this
0x1800262f4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800262f9  jmp     short loc_180026302
0x1800262fb  mov     ecx, edi; this
0x1800262fd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180026302  mov     ebp, eax
0x180026304  mov     [rbx], r15d
0x180026307  mov     eax, [rsp+78h+arg_70]
0x18002630e  mov     [rbx+4], eax
0x180026311  cmp     dword ptr [r14+8], 1
0x180026316  jnz     short loc_18002631E
0x180026318  or      eax, 8
0x18002631b  mov     [rbx+4], eax
0x18002631e  mov     eax, 1
0x180026323  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002632b  inc     eax
0x18002632d  mov     [rbx+10h], eax
0x180026330  mov     rax, [rsp+78h+arg_40]
0x180026338  xor     edi, edi
0x18002633a  test    rax, rax
0x18002633d  jz      short loc_180026344
0x18002633f  cmp     [rax], di
0x180026342  jnz     short loc_180026347
0x180026344  mov     rax, rdi
0x180026347  mov     [rbx+18h], rax
0x18002634b  call    cs:__imp_GetCurrentThreadId
0x180026351  mov     [rbx+20h], eax
0x180026354  mov     [rbx+38h], r13
0x180026358  mov     eax, [rsp+78h+arg_8]
0x18002635f  mov     [rbx+40h], eax
0x180026362  mov     [rbx+44h], ebp
0x180026365  mov     rax, [rsp+78h+arg_20]
0x18002636d  mov     [rbx+28h], rax
0x180026371  mov     [rbx+30h], r12
0x180026375  mov     rax, [rsp+78h+arg_28]
0x18002637d  mov     [rbx+88h], rax
0x180026384  mov     rax, [rsp+78h+arg_0]
0x18002638c  mov     [rbx+90h], rax
0x180026393  mov     [rbx+48h], rdi
0x180026397  xorps   xmm0, xmm0
0x18002639a  xor     eax, eax
0x18002639c  movups  xmmword ptr [rbx+68h], xmm0
0x1800263a0  mov     [rbx+78h], rax
0x1800263a4  movups  xmmword ptr [rbx+50h], xmm0
0x1800263a8  mov     [rbx+60h], rax
0x1800263ac  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800263b3  test    rax, rax
0x1800263b6  jz      short loc_1800263BF
0x1800263b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263bd  jmp     short loc_1800263C2
0x1800263bf  mov     rax, rdi
0x1800263c2  mov     [rbx+80h], rax
0x1800263c9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800263d0  test    rax, rax
0x1800263d3  jz      short loc_1800263DD
0x1800263d5  mov     rcx, rbx
0x1800263d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263dd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800263e4  test    rax, rax
0x1800263e7  jz      short loc_1800263FF
0x1800263e9  mov     r8d, 400h
0x1800263ef  mov     rdx, [rsp+78h+arg_60]
0x1800263f7  mov     rcx, rbx
0x1800263fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263ff  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180026406  test    rax, rax
0x180026409  jz      short loc_180026413
0x18002640b  mov     rcx, rbx
0x18002640e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026413  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002641a  test    rax, rax
0x18002641d  jz      short loc_18002642D
0x18002641f  test    byte ptr [rbx+4], 2
0x180026423  jnz     short loc_18002642D
0x180026425  mov     rcx, rbx
0x180026428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002642d  cmp     [rbx+8], edi
0x180026430  jl      short loc_18002644C
0x180026432  cmp     r15d, 3
0x180026436  jnz     loc_18002651B
0x18002643c  mov     ecx, 8000FFFFh; this
0x180026441  mov     [rbx+8], ecx
0x180026444  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180026449  mov     [rbx+0Ch], eax
0x18002644c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180026453  jnz     short loc_180026474
0x180026455  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002645c  test    rax, rax
0x18002645f  jz      short loc_18002646A
0x180026461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026466  test    al, al
0x180026468  jmp     short loc_180026472
0x18002646a  call    cs:__imp_IsDebuggerPresent
0x180026470  test    eax, eax
0x180026472  jz      short loc_18002647A
0x180026474  test    byte ptr [rbx+4], 2
0x180026478  jz      short loc_18002649E
0x18002647a  mov     rax, cs:g_pfnResultLoggingCallback
0x180026481  test    rax, rax
0x180026484  jz      short loc_1800264E2
0x180026486  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002648d  jnz     short loc_1800264E2
0x18002648f  xor     r8d, r8d
0x180026492  xor     edx, edx
0x180026494  mov     rcx, rbx
0x180026497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002649c  jmp     short loc_1800264E2
0x18002649e  mov     ebp, 800h
0x1800264a3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800264aa  test    rax, rax
0x1800264ad  jz      short loc_1800264C6
0x1800264af  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800264b6  jnz     short loc_1800264C6
0x1800264b8  mov     r8d, ebp
0x1800264bb  mov     rdx, rsi
0x1800264be  mov     rcx, rbx
0x1800264c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264c6  cmp     [rsi], di
0x1800264c9  jnz     short loc_1800264D9
0x1800264cb  mov     r8, rbx; unsigned __int64
0x1800264ce  mov     rdx, rbp; unsigned __int16 *
0x1800264d1  mov     rcx, rsi; this
0x1800264d4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800264d9  mov     rcx, rsi; lpOutputString
0x1800264dc  call    cs:__imp_OutputDebugStringW
0x1800264e2  test    byte ptr [rbx+4], 4
0x1800264e6  jnz     short loc_1800264F1
0x1800264e8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800264ef  jz      short loc_180026503
0x1800264f1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800264f8  test    rax, rax
0x1800264fb  jz      short loc_180026503
0x1800264fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026502  nop
0x180026503  mov     rbx, [rsp+78h+arg_10]
0x18002650b  add     rsp, 40h
0x18002650f  pop     r15
0x180026511  pop     r14
0x180026513  pop     r13
0x180026515  pop     r12
0x180026517  pop     rdi
0x180026518  pop     rsi
0x180026519  pop     rbp
0x18002651a  retn
0x18002651b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
