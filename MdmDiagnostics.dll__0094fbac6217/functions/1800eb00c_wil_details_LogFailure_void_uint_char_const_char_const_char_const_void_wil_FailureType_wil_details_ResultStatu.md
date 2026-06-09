# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800eb00c`
- end: `0x1800eb305`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800e4b24`
- `0x1800e4e90`
- `0x1800f6f94`

## callees

- `0x1800e498c`
- `0x1800ea2e4`
- `0x1800eab50`
- `0x1800eb00c`
- `0x1800ec1b4`
- `0x1800ec1d0`
- `0x1800ec320`
- `0x1800ec33c`
- `0x1800eeb1c`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eb12f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eb12f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800eb24e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800eb24e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800eb2c0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800eb2c0`

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
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x1800eb00c  mov     [rsp+arg_10], rbx
0x1800eb011  mov     [rsp+arg_8], edx
0x1800eb015  mov     [rsp+arg_0], rcx
0x1800eb01a  push    rbp
0x1800eb01b  push    rsi
0x1800eb01c  push    rdi
0x1800eb01d  push    r12
0x1800eb01f  push    r13
0x1800eb021  push    r14
0x1800eb023  push    r15
0x1800eb025  sub     rsp, 40h
0x1800eb029  mov     r12, r9
0x1800eb02c  mov     r13, r8
0x1800eb02f  mov     r10, rcx
0x1800eb032  xor     eax, eax
0x1800eb034  mov     rsi, [rsp+78h+lpOutputString]
0x1800eb03c  mov     [rsi], ax
0x1800eb03f  mov     rax, [rsp+78h+arg_60]
0x1800eb047  mov     byte ptr [rax], 0
0x1800eb04a  mov     r14, [rsp+78h+arg_38]
0x1800eb052  mov     edi, [r14]
0x1800eb055  mov     rbx, [rsp+78h+arg_78]
0x1800eb05d  mov     [rbx+8], edi
0x1800eb060  mov     eax, [r14+4]
0x1800eb064  mov     [rbx+0Ch], eax
0x1800eb067  xor     ebp, ebp
0x1800eb069  mov     r15d, [rsp+78h+arg_30]
0x1800eb071  mov     ecx, r15d
0x1800eb074  test    r15d, r15d
0x1800eb077  jz      short loc_1800EB0DF
0x1800eb079  sub     ecx, 1
0x1800eb07c  jz      short loc_1800EB0D6
0x1800eb07e  sub     ecx, 1
0x1800eb081  jz      short loc_1800EB091
0x1800eb083  cmp     ecx, 1
0x1800eb086  jnz     short loc_1800EB0E8
0x1800eb088  mov     ecx, edi; this
0x1800eb08a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800eb08f  jmp     short loc_1800EB0E6
0x1800eb091  test    edi, edi
0x1800eb093  js      short loc_1800EB0CD
0x1800eb095  mov     edi, 8007029Ch
0x1800eb09a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800eb09e  mov     rax, [rsp+78h+arg_28]
0x1800eb0a6  mov     [rsp+78h+var_50], rax; __int64
0x1800eb0ab  mov     rax, [rsp+78h+arg_20]
0x1800eb0b3  mov     [rsp+78h+var_58], rax; __int64
0x1800eb0b8  mov     rcx, r10; int
0x1800eb0bb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800eb0c0  mov     [rbx+8], edi
0x1800eb0c3  mov     ecx, edi; this
0x1800eb0c5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800eb0ca  mov     [rbx+0Ch], eax
0x1800eb0cd  mov     ecx, edi; this
0x1800eb0cf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800eb0d4  jmp     short loc_1800EB0E6
0x1800eb0d6  mov     ecx, edi; this
0x1800eb0d8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800eb0dd  jmp     short loc_1800EB0E6
0x1800eb0df  mov     ecx, edi; this
0x1800eb0e1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800eb0e6  mov     ebp, eax
0x1800eb0e8  mov     [rbx], r15d
0x1800eb0eb  mov     eax, [rsp+78h+arg_70]
0x1800eb0f2  mov     [rbx+4], eax
0x1800eb0f5  cmp     dword ptr [r14+8], 1
0x1800eb0fa  jnz     short loc_1800EB102
0x1800eb0fc  or      eax, 8
0x1800eb0ff  mov     [rbx+4], eax
0x1800eb102  mov     eax, 1
0x1800eb107  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800eb10f  inc     eax
0x1800eb111  mov     [rbx+10h], eax
0x1800eb114  mov     rax, [rsp+78h+arg_40]
0x1800eb11c  xor     edi, edi
0x1800eb11e  test    rax, rax
0x1800eb121  jz      short loc_1800EB128
0x1800eb123  cmp     [rax], di
0x1800eb126  jnz     short loc_1800EB12B
0x1800eb128  mov     rax, rdi
0x1800eb12b  mov     [rbx+18h], rax
0x1800eb12f  call    cs:__imp_GetCurrentThreadId
0x1800eb135  mov     [rbx+20h], eax
0x1800eb138  mov     [rbx+38h], r13
0x1800eb13c  mov     eax, [rsp+78h+arg_8]
0x1800eb143  mov     [rbx+40h], eax
0x1800eb146  mov     [rbx+44h], ebp
0x1800eb149  mov     rax, [rsp+78h+arg_20]
0x1800eb151  mov     [rbx+28h], rax
0x1800eb155  mov     [rbx+30h], r12
0x1800eb159  mov     rax, [rsp+78h+arg_28]
0x1800eb161  mov     [rbx+88h], rax
0x1800eb168  mov     rax, [rsp+78h+arg_0]
0x1800eb170  mov     [rbx+90h], rax
0x1800eb177  mov     [rbx+48h], rdi
0x1800eb17b  xorps   xmm0, xmm0
0x1800eb17e  xor     eax, eax
0x1800eb180  movups  xmmword ptr [rbx+68h], xmm0
0x1800eb184  mov     [rbx+78h], rax
0x1800eb188  movups  xmmword ptr [rbx+50h], xmm0
0x1800eb18c  mov     [rbx+60h], rax
0x1800eb190  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800eb197  test    rax, rax
0x1800eb19a  jz      short loc_1800EB1A3
0x1800eb19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb1a1  jmp     short loc_1800EB1A6
0x1800eb1a3  mov     rax, rdi
0x1800eb1a6  mov     [rbx+80h], rax
0x1800eb1ad  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800eb1b4  test    rax, rax
0x1800eb1b7  jz      short loc_1800EB1C1
0x1800eb1b9  mov     rcx, rbx
0x1800eb1bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb1c1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800eb1c8  test    rax, rax
0x1800eb1cb  jz      short loc_1800EB1E3
0x1800eb1cd  mov     r8d, 400h
0x1800eb1d3  mov     rdx, [rsp+78h+arg_60]
0x1800eb1db  mov     rcx, rbx
0x1800eb1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb1e3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800eb1ea  test    rax, rax
0x1800eb1ed  jz      short loc_1800EB1F7
0x1800eb1ef  mov     rcx, rbx
0x1800eb1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb1f7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800eb1fe  test    rax, rax
0x1800eb201  jz      short loc_1800EB211
0x1800eb203  test    byte ptr [rbx+4], 2
0x1800eb207  jnz     short loc_1800EB211
0x1800eb209  mov     rcx, rbx
0x1800eb20c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb211  cmp     [rbx+8], edi
0x1800eb214  jl      short loc_1800EB230
0x1800eb216  cmp     r15d, 3
0x1800eb21a  jnz     loc_1800EB2FF
0x1800eb220  mov     ecx, 8000FFFFh; this
0x1800eb225  mov     [rbx+8], ecx
0x1800eb228  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800eb22d  mov     [rbx+0Ch], eax
0x1800eb230  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800eb237  jnz     short loc_1800EB258
0x1800eb239  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800eb240  test    rax, rax
0x1800eb243  jz      short loc_1800EB24E
0x1800eb245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb24a  test    al, al
0x1800eb24c  jmp     short loc_1800EB256
0x1800eb24e  call    cs:__imp_IsDebuggerPresent
0x1800eb254  test    eax, eax
0x1800eb256  jz      short loc_1800EB25E
0x1800eb258  test    byte ptr [rbx+4], 2
0x1800eb25c  jz      short loc_1800EB282
0x1800eb25e  mov     rax, cs:g_pfnResultLoggingCallback
0x1800eb265  test    rax, rax
0x1800eb268  jz      short loc_1800EB2C6
0x1800eb26a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800eb271  jnz     short loc_1800EB2C6
0x1800eb273  xor     r8d, r8d
0x1800eb276  xor     edx, edx
0x1800eb278  mov     rcx, rbx
0x1800eb27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb280  jmp     short loc_1800EB2C6
0x1800eb282  mov     ebp, 800h
0x1800eb287  mov     rax, cs:g_pfnResultLoggingCallback
0x1800eb28e  test    rax, rax
0x1800eb291  jz      short loc_1800EB2AA
0x1800eb293  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800eb29a  jnz     short loc_1800EB2AA
0x1800eb29c  mov     r8d, ebp
0x1800eb29f  mov     rdx, rsi
0x1800eb2a2  mov     rcx, rbx
0x1800eb2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb2aa  cmp     [rsi], di
0x1800eb2ad  jnz     short loc_1800EB2BD
0x1800eb2af  mov     r8, rbx; unsigned __int64
0x1800eb2b2  mov     rdx, rbp; unsigned __int16 *
0x1800eb2b5  mov     rcx, rsi; this
0x1800eb2b8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800eb2bd  mov     rcx, rsi; lpOutputString
0x1800eb2c0  call    cs:__imp_OutputDebugStringW
0x1800eb2c6  test    byte ptr [rbx+4], 4
0x1800eb2ca  jnz     short loc_1800EB2D5
0x1800eb2cc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800eb2d3  jz      short loc_1800EB2E7
0x1800eb2d5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800eb2dc  test    rax, rax
0x1800eb2df  jz      short loc_1800EB2E7
0x1800eb2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb2e6  nop
0x1800eb2e7  mov     rbx, [rsp+78h+arg_10]
0x1800eb2ef  add     rsp, 40h
0x1800eb2f3  pop     r15
0x1800eb2f5  pop     r14
0x1800eb2f7  pop     r13
0x1800eb2f9  pop     r12
0x1800eb2fb  pop     rdi
0x1800eb2fc  pop     rsi
0x1800eb2fd  pop     rbp
0x1800eb2fe  retn
0x1800eb2ff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
