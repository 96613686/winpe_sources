# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000bcfc`
- end: `0x14000bff4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x14000a530`
- `0x14000a8dc`

## callees

- `0x140005d50`
- `0x140007714`
- `0x14000a460`
- `0x14000b4d4`
- `0x14000bcfc`
- `0x14000c288`
- `0x14000c2b0`
- `0x14000c320`
- `0x14000cd74`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000be1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000be1f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000bfb0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000bfb0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000bf3e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000bf3e`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW((LPCWSTR)lpOutputString);
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
0x14000bcfc  mov     [rsp+arg_10], rbx
0x14000bd01  mov     [rsp+arg_8], edx
0x14000bd05  mov     [rsp+arg_0], rcx
0x14000bd0a  push    rbp
0x14000bd0b  push    rsi
0x14000bd0c  push    rdi
0x14000bd0d  push    r12
0x14000bd0f  push    r13
0x14000bd11  push    r14
0x14000bd13  push    r15
0x14000bd15  sub     rsp, 40h
0x14000bd19  mov     r14, [rsp+78h+arg_38]
0x14000bd21  xor     eax, eax
0x14000bd23  mov     rbx, [rsp+78h+arg_78]
0x14000bd2b  xor     ebp, ebp
0x14000bd2d  mov     r15d, [rsp+78h+arg_30]
0x14000bd35  mov     r10, rcx
0x14000bd38  mov     rsi, [rsp+78h+lpOutputString]
0x14000bd40  mov     r12, r9
0x14000bd43  mov     r13, r8
0x14000bd46  mov     ecx, r15d
0x14000bd49  mov     [rsi], ax
0x14000bd4c  mov     rax, [rsp+78h+arg_60]
0x14000bd54  mov     byte ptr [rax], 0
0x14000bd57  mov     edi, [r14]
0x14000bd5a  mov     [rbx+8], edi
0x14000bd5d  mov     eax, [r14+4]
0x14000bd61  mov     [rbx+0Ch], eax
0x14000bd64  test    r15d, r15d
0x14000bd67  jz      short loc_14000BDCF
0x14000bd69  sub     ecx, 1
0x14000bd6c  jz      short loc_14000BDC6
0x14000bd6e  sub     ecx, 1
0x14000bd71  jz      short loc_14000BD81
0x14000bd73  cmp     ecx, 1
0x14000bd76  jnz     short loc_14000BDD8
0x14000bd78  mov     ecx, edi; this
0x14000bd7a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000bd7f  jmp     short loc_14000BDD6
0x14000bd81  test    edi, edi
0x14000bd83  js      short loc_14000BDBD
0x14000bd85  mov     rax, [rsp+78h+arg_28]
0x14000bd8d  mov     edi, 8007029Ch
0x14000bd92  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000bd96  mov     rcx, r10; int
0x14000bd99  mov     [rsp+78h+var_50], rax; __int64
0x14000bd9e  mov     rax, [rsp+78h+arg_20]
0x14000bda6  mov     [rsp+78h+var_58], rax; __int64
0x14000bdab  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000bdb0  mov     ecx, edi; this
0x14000bdb2  mov     [rbx+8], edi
0x14000bdb5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000bdba  mov     [rbx+0Ch], eax
0x14000bdbd  mov     ecx, edi; this
0x14000bdbf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000bdc4  jmp     short loc_14000BDD6
0x14000bdc6  mov     ecx, edi; this
0x14000bdc8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000bdcd  jmp     short loc_14000BDD6
0x14000bdcf  mov     ecx, edi; this
0x14000bdd1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000bdd6  mov     ebp, eax
0x14000bdd8  mov     eax, [rsp+78h+arg_70]
0x14000bddf  mov     [rbx+4], eax
0x14000bde2  mov     [rbx], r15d
0x14000bde5  cmp     dword ptr [r14+8], 1
0x14000bdea  jnz     short loc_14000BDF2
0x14000bdec  or      eax, 8
0x14000bdef  mov     [rbx+4], eax
0x14000bdf2  mov     eax, 1
0x14000bdf7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000bdff  inc     eax
0x14000be01  xor     edi, edi
0x14000be03  mov     [rbx+10h], eax
0x14000be06  mov     rax, [rsp+78h+arg_40]
0x14000be0e  test    rax, rax
0x14000be11  jz      short loc_14000BE18
0x14000be13  cmp     [rax], di
0x14000be16  jnz     short loc_14000BE1B
0x14000be18  mov     rax, rdi
0x14000be1b  mov     [rbx+18h], rax
0x14000be1f  call    cs:__imp_GetCurrentThreadId
0x14000be25  mov     [rbx+38h], r13
0x14000be29  xorps   xmm0, xmm0
0x14000be2c  mov     [rbx+20h], eax
0x14000be2f  mov     eax, [rsp+78h+arg_8]
0x14000be36  mov     [rbx+40h], eax
0x14000be39  mov     rax, [rsp+78h+arg_20]
0x14000be41  mov     [rbx+28h], rax
0x14000be45  mov     rax, [rsp+78h+arg_28]
0x14000be4d  mov     [rbx+88h], rax
0x14000be54  mov     rax, [rsp+78h+arg_0]
0x14000be5c  mov     [rbx+90h], rax
0x14000be63  xor     eax, eax
0x14000be65  mov     [rbx+44h], ebp
0x14000be68  mov     [rbx+30h], r12
0x14000be6c  mov     [rbx+48h], rdi
0x14000be70  movups  xmmword ptr [rbx+68h], xmm0
0x14000be74  mov     [rbx+78h], rax
0x14000be78  movups  xmmword ptr [rbx+50h], xmm0
0x14000be7c  mov     [rbx+60h], rax
0x14000be80  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000be87  test    rax, rax
0x14000be8a  jz      short loc_14000BE93
0x14000be8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be91  jmp     short loc_14000BE96
0x14000be93  mov     rax, rdi
0x14000be96  mov     [rbx+80h], rax
0x14000be9d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000bea4  test    rax, rax
0x14000bea7  jz      short loc_14000BEB1
0x14000bea9  mov     rcx, rbx
0x14000beac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000beb1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000beb8  test    rax, rax
0x14000bebb  jz      short loc_14000BED3
0x14000bebd  mov     rdx, [rsp+78h+arg_60]
0x14000bec5  mov     r8d, 400h
0x14000becb  mov     rcx, rbx
0x14000bece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bed3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000beda  test    rax, rax
0x14000bedd  jz      short loc_14000BEE7
0x14000bedf  mov     rcx, rbx
0x14000bee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bee7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000beee  test    rax, rax
0x14000bef1  jz      short loc_14000BF01
0x14000bef3  test    byte ptr [rbx+4], 2
0x14000bef7  jnz     short loc_14000BF01
0x14000bef9  mov     rcx, rbx
0x14000befc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf01  cmp     [rbx+8], edi
0x14000bf04  jl      short loc_14000BF20
0x14000bf06  cmp     r15d, 3
0x14000bf0a  jnz     loc_14000BFEE
0x14000bf10  mov     ecx, 8000FFFFh; this
0x14000bf15  mov     [rbx+8], ecx
0x14000bf18  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000bf1d  mov     [rbx+0Ch], eax
0x14000bf20  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000bf27  jnz     short loc_14000BF48
0x14000bf29  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000bf30  test    rax, rax
0x14000bf33  jz      short loc_14000BF3E
0x14000bf35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf3a  test    al, al
0x14000bf3c  jmp     short loc_14000BF46
0x14000bf3e  call    cs:__imp_IsDebuggerPresent
0x14000bf44  test    eax, eax
0x14000bf46  jz      short loc_14000BF4E
0x14000bf48  test    byte ptr [rbx+4], 2
0x14000bf4c  jz      short loc_14000BF72
0x14000bf4e  mov     rax, cs:g_pfnResultLoggingCallback
0x14000bf55  test    rax, rax
0x14000bf58  jz      short loc_14000BFB6
0x14000bf5a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000bf61  jnz     short loc_14000BFB6
0x14000bf63  xor     r8d, r8d
0x14000bf66  xor     edx, edx
0x14000bf68  mov     rcx, rbx
0x14000bf6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf70  jmp     short loc_14000BFB6
0x14000bf72  mov     rax, cs:g_pfnResultLoggingCallback
0x14000bf79  mov     ebp, 800h
0x14000bf7e  test    rax, rax
0x14000bf81  jz      short loc_14000BF9A
0x14000bf83  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000bf8a  jnz     short loc_14000BF9A
0x14000bf8c  mov     r8d, ebp
0x14000bf8f  mov     rdx, rsi
0x14000bf92  mov     rcx, rbx
0x14000bf95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf9a  cmp     [rsi], di
0x14000bf9d  jnz     short loc_14000BFAD
0x14000bf9f  mov     r8, rbx; unsigned __int64
0x14000bfa2  mov     rdx, rbp; unsigned __int16 *
0x14000bfa5  mov     rcx, rsi; this
0x14000bfa8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000bfad  mov     rcx, rsi; lpOutputString
0x14000bfb0  call    cs:__imp_OutputDebugStringW
0x14000bfb6  test    byte ptr [rbx+4], 4
0x14000bfba  jnz     short loc_14000BFC5
0x14000bfbc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000bfc3  jz      short loc_14000BFD6
0x14000bfc5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000bfcc  test    rax, rax
0x14000bfcf  jz      short loc_14000BFD6
0x14000bfd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bfd6  mov     rbx, [rsp+78h+arg_10]
0x14000bfde  add     rsp, 40h
0x14000bfe2  pop     r15
0x14000bfe4  pop     r14
0x14000bfe6  pop     r13
0x14000bfe8  pop     r12
0x14000bfea  pop     rdi
0x14000bfeb  pop     rsi
0x14000bfec  pop     rbp
0x14000bfed  retn
0x14000bfee  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
