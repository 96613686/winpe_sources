# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000db50`
- end: `0x18000de49`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180008df0`
- `0x18000913c`

## callees

- `0x180008d30`
- `0x18000cccc`
- `0x18000d718`
- `0x18000db50`
- `0x18000eec4`
- `0x18000eee0`
- `0x18000f064`
- `0x18000f080`
- `0x180012744`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000de04`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000de04`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000dd92`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000dd92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dc73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dc73`

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
0x18000db50  mov     [rsp+arg_10], rbx
0x18000db55  mov     [rsp+arg_8], edx
0x18000db59  mov     [rsp+arg_0], rcx
0x18000db5e  push    rbp
0x18000db5f  push    rsi
0x18000db60  push    rdi
0x18000db61  push    r12
0x18000db63  push    r13
0x18000db65  push    r14
0x18000db67  push    r15
0x18000db69  sub     rsp, 40h
0x18000db6d  mov     r12, r9
0x18000db70  mov     r13, r8
0x18000db73  mov     r10, rcx
0x18000db76  xor     eax, eax
0x18000db78  mov     rsi, [rsp+78h+lpOutputString]
0x18000db80  mov     [rsi], ax
0x18000db83  mov     rax, [rsp+78h+arg_60]
0x18000db8b  mov     byte ptr [rax], 0
0x18000db8e  mov     r14, [rsp+78h+arg_38]
0x18000db96  mov     edi, [r14]
0x18000db99  mov     rbx, [rsp+78h+arg_78]
0x18000dba1  mov     [rbx+8], edi
0x18000dba4  mov     eax, [r14+4]
0x18000dba8  mov     [rbx+0Ch], eax
0x18000dbab  xor     ebp, ebp
0x18000dbad  mov     r15d, [rsp+78h+arg_30]
0x18000dbb5  mov     ecx, r15d
0x18000dbb8  test    r15d, r15d
0x18000dbbb  jz      short loc_18000DC23
0x18000dbbd  sub     ecx, 1
0x18000dbc0  jz      short loc_18000DC1A
0x18000dbc2  sub     ecx, 1
0x18000dbc5  jz      short loc_18000DBD5
0x18000dbc7  cmp     ecx, 1
0x18000dbca  jnz     short loc_18000DC2C
0x18000dbcc  mov     ecx, edi; this
0x18000dbce  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000dbd3  jmp     short loc_18000DC2A
0x18000dbd5  test    edi, edi
0x18000dbd7  js      short loc_18000DC11
0x18000dbd9  mov     edi, 8007029Ch
0x18000dbde  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000dbe2  mov     rax, [rsp+78h+arg_28]
0x18000dbea  mov     [rsp+78h+var_50], rax; __int64
0x18000dbef  mov     rax, [rsp+78h+arg_20]
0x18000dbf7  mov     [rsp+78h+var_58], rax; __int64
0x18000dbfc  mov     rcx, r10; int
0x18000dbff  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000dc04  mov     [rbx+8], edi
0x18000dc07  mov     ecx, edi; this
0x18000dc09  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000dc0e  mov     [rbx+0Ch], eax
0x18000dc11  mov     ecx, edi; this
0x18000dc13  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000dc18  jmp     short loc_18000DC2A
0x18000dc1a  mov     ecx, edi; this
0x18000dc1c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000dc21  jmp     short loc_18000DC2A
0x18000dc23  mov     ecx, edi; this
0x18000dc25  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000dc2a  mov     ebp, eax
0x18000dc2c  mov     [rbx], r15d
0x18000dc2f  mov     eax, [rsp+78h+arg_70]
0x18000dc36  mov     [rbx+4], eax
0x18000dc39  cmp     dword ptr [r14+8], 1
0x18000dc3e  jnz     short loc_18000DC46
0x18000dc40  or      eax, 8
0x18000dc43  mov     [rbx+4], eax
0x18000dc46  mov     eax, 1
0x18000dc4b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000dc53  inc     eax
0x18000dc55  mov     [rbx+10h], eax
0x18000dc58  mov     rax, [rsp+78h+arg_40]
0x18000dc60  xor     edi, edi
0x18000dc62  test    rax, rax
0x18000dc65  jz      short loc_18000DC6C
0x18000dc67  cmp     [rax], di
0x18000dc6a  jnz     short loc_18000DC6F
0x18000dc6c  mov     rax, rdi
0x18000dc6f  mov     [rbx+18h], rax
0x18000dc73  call    cs:__imp_GetCurrentThreadId
0x18000dc79  mov     [rbx+20h], eax
0x18000dc7c  mov     [rbx+38h], r13
0x18000dc80  mov     eax, [rsp+78h+arg_8]
0x18000dc87  mov     [rbx+40h], eax
0x18000dc8a  mov     [rbx+44h], ebp
0x18000dc8d  mov     rax, [rsp+78h+arg_20]
0x18000dc95  mov     [rbx+28h], rax
0x18000dc99  mov     [rbx+30h], r12
0x18000dc9d  mov     rax, [rsp+78h+arg_28]
0x18000dca5  mov     [rbx+88h], rax
0x18000dcac  mov     rax, [rsp+78h+arg_0]
0x18000dcb4  mov     [rbx+90h], rax
0x18000dcbb  mov     [rbx+48h], rdi
0x18000dcbf  xorps   xmm0, xmm0
0x18000dcc2  xor     eax, eax
0x18000dcc4  movups  xmmword ptr [rbx+68h], xmm0
0x18000dcc8  mov     [rbx+78h], rax
0x18000dccc  movups  xmmword ptr [rbx+50h], xmm0
0x18000dcd0  mov     [rbx+60h], rax
0x18000dcd4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000dcdb  test    rax, rax
0x18000dcde  jz      short loc_18000DCE7
0x18000dce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dce5  jmp     short loc_18000DCEA
0x18000dce7  mov     rax, rdi
0x18000dcea  mov     [rbx+80h], rax
0x18000dcf1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000dcf8  test    rax, rax
0x18000dcfb  jz      short loc_18000DD05
0x18000dcfd  mov     rcx, rbx
0x18000dd00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd05  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000dd0c  test    rax, rax
0x18000dd0f  jz      short loc_18000DD27
0x18000dd11  mov     r8d, 400h
0x18000dd17  mov     rdx, [rsp+78h+arg_60]
0x18000dd1f  mov     rcx, rbx
0x18000dd22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd27  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000dd2e  test    rax, rax
0x18000dd31  jz      short loc_18000DD3B
0x18000dd33  mov     rcx, rbx
0x18000dd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd3b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000dd42  test    rax, rax
0x18000dd45  jz      short loc_18000DD55
0x18000dd47  test    byte ptr [rbx+4], 2
0x18000dd4b  jnz     short loc_18000DD55
0x18000dd4d  mov     rcx, rbx
0x18000dd50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd55  cmp     [rbx+8], edi
0x18000dd58  jl      short loc_18000DD74
0x18000dd5a  cmp     r15d, 3
0x18000dd5e  jnz     loc_18000DE43
0x18000dd64  mov     ecx, 8000FFFFh; this
0x18000dd69  mov     [rbx+8], ecx
0x18000dd6c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000dd71  mov     [rbx+0Ch], eax
0x18000dd74  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000dd7b  jnz     short loc_18000DD9C
0x18000dd7d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000dd84  test    rax, rax
0x18000dd87  jz      short loc_18000DD92
0x18000dd89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd8e  test    al, al
0x18000dd90  jmp     short loc_18000DD9A
0x18000dd92  call    cs:__imp_IsDebuggerPresent
0x18000dd98  test    eax, eax
0x18000dd9a  jz      short loc_18000DDA2
0x18000dd9c  test    byte ptr [rbx+4], 2
0x18000dda0  jz      short loc_18000DDC6
0x18000dda2  mov     rax, cs:g_pfnResultLoggingCallback
0x18000dda9  test    rax, rax
0x18000ddac  jz      short loc_18000DE0A
0x18000ddae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ddb5  jnz     short loc_18000DE0A
0x18000ddb7  xor     r8d, r8d
0x18000ddba  xor     edx, edx
0x18000ddbc  mov     rcx, rbx
0x18000ddbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddc4  jmp     short loc_18000DE0A
0x18000ddc6  mov     ebp, 800h
0x18000ddcb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ddd2  test    rax, rax
0x18000ddd5  jz      short loc_18000DDEE
0x18000ddd7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ddde  jnz     short loc_18000DDEE
0x18000dde0  mov     r8d, ebp
0x18000dde3  mov     rdx, rsi
0x18000dde6  mov     rcx, rbx
0x18000dde9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddee  cmp     [rsi], di
0x18000ddf1  jnz     short loc_18000DE01
0x18000ddf3  mov     r8, rbx; unsigned __int64
0x18000ddf6  mov     rdx, rbp; unsigned __int16 *
0x18000ddf9  mov     rcx, rsi; this
0x18000ddfc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000de01  mov     rcx, rsi; lpOutputString
0x18000de04  call    cs:__imp_OutputDebugStringW
0x18000de0a  test    byte ptr [rbx+4], 4
0x18000de0e  jnz     short loc_18000DE19
0x18000de10  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000de17  jz      short loc_18000DE2B
0x18000de19  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000de20  test    rax, rax
0x18000de23  jz      short loc_18000DE2B
0x18000de25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de2a  nop
0x18000de2b  mov     rbx, [rsp+78h+arg_10]
0x18000de33  add     rsp, 40h
0x18000de37  pop     r15
0x18000de39  pop     r14
0x18000de3b  pop     r13
0x18000de3d  pop     r12
0x18000de3f  pop     rdi
0x18000de40  pop     rsi
0x18000de41  pop     rbp
0x18000de42  retn
0x18000de43  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
