# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001a46c`
- end: `0x18001a774`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `776`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18001a138`
- `0x18001a240`
- `0x18001a340`
- `0x18002e818`

## callees

- `0x180019750`
- `0x18001a46c`
- `0x1800258ac`
- `0x18002f4d4`
- `0x18003033c`
- `0x180030360`
- `0x180030374`
- `0x180030394`
- `0x180031888`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a58f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a58f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a72e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a72e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001a6b6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001a6b6`

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
0x18001a46c  mov     [rsp+arg_10], rbx
0x18001a471  mov     [rsp+arg_8], edx
0x18001a475  mov     [rsp+arg_0], rcx
0x18001a47a  push    rbp
0x18001a47b  push    rsi
0x18001a47c  push    rdi
0x18001a47d  push    r12
0x18001a47f  push    r13
0x18001a481  push    r14
0x18001a483  push    r15
0x18001a485  sub     rsp, 40h
0x18001a489  mov     r12, r9
0x18001a48c  mov     r13, r8
0x18001a48f  mov     r10, rcx
0x18001a492  xor     eax, eax
0x18001a494  mov     rsi, [rsp+78h+lpOutputString]
0x18001a49c  mov     [rsi], ax
0x18001a49f  mov     rax, [rsp+78h+arg_60]
0x18001a4a7  mov     byte ptr [rax], 0
0x18001a4aa  mov     r14, [rsp+78h+arg_38]
0x18001a4b2  mov     edi, [r14]
0x18001a4b5  mov     rbx, [rsp+78h+arg_78]
0x18001a4bd  mov     [rbx+8], edi
0x18001a4c0  mov     eax, [r14+4]
0x18001a4c4  mov     [rbx+0Ch], eax
0x18001a4c7  xor     ebp, ebp
0x18001a4c9  mov     r15d, [rsp+78h+arg_30]
0x18001a4d1  mov     ecx, r15d
0x18001a4d4  test    r15d, r15d
0x18001a4d7  jz      short loc_18001A53F
0x18001a4d9  sub     ecx, 1
0x18001a4dc  jz      short loc_18001A536
0x18001a4de  sub     ecx, 1
0x18001a4e1  jz      short loc_18001A4F1
0x18001a4e3  cmp     ecx, 1
0x18001a4e6  jnz     short loc_18001A548
0x18001a4e8  mov     ecx, edi; this
0x18001a4ea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001a4ef  jmp     short loc_18001A546
0x18001a4f1  test    edi, edi
0x18001a4f3  js      short loc_18001A52D
0x18001a4f5  mov     edi, 8007029Ch
0x18001a4fa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001a4fe  mov     rax, [rsp+78h+arg_28]
0x18001a506  mov     [rsp+78h+var_50], rax; __int64
0x18001a50b  mov     rax, [rsp+78h+arg_20]
0x18001a513  mov     [rsp+78h+var_58], rax; __int64
0x18001a518  mov     rcx, r10; int
0x18001a51b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001a520  mov     [rbx+8], edi
0x18001a523  mov     ecx, edi; this
0x18001a525  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001a52a  mov     [rbx+0Ch], eax
0x18001a52d  mov     ecx, edi; this
0x18001a52f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001a534  jmp     short loc_18001A546
0x18001a536  mov     ecx, edi; this
0x18001a538  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001a53d  jmp     short loc_18001A546
0x18001a53f  mov     ecx, edi; this
0x18001a541  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001a546  mov     ebp, eax
0x18001a548  mov     [rbx], r15d
0x18001a54b  mov     eax, [rsp+78h+arg_70]
0x18001a552  mov     [rbx+4], eax
0x18001a555  cmp     dword ptr [r14+8], 1
0x18001a55a  jnz     short loc_18001A562
0x18001a55c  or      eax, 8
0x18001a55f  mov     [rbx+4], eax
0x18001a562  mov     eax, 1
0x18001a567  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001a56f  inc     eax
0x18001a571  mov     [rbx+10h], eax
0x18001a574  mov     rax, [rsp+78h+arg_40]
0x18001a57c  xor     edi, edi
0x18001a57e  test    rax, rax
0x18001a581  jz      short loc_18001A588
0x18001a583  cmp     [rax], di
0x18001a586  jnz     short loc_18001A58B
0x18001a588  mov     rax, rdi
0x18001a58b  mov     [rbx+18h], rax
0x18001a58f  call    cs:__imp_GetCurrentThreadId
0x18001a596  nop     dword ptr [rax+rax+00h]
0x18001a59b  mov     [rbx+20h], eax
0x18001a59e  mov     [rbx+38h], r13
0x18001a5a2  mov     eax, [rsp+78h+arg_8]
0x18001a5a9  mov     [rbx+40h], eax
0x18001a5ac  mov     [rbx+44h], ebp
0x18001a5af  mov     rax, [rsp+78h+arg_20]
0x18001a5b7  mov     [rbx+28h], rax
0x18001a5bb  mov     [rbx+30h], r12
0x18001a5bf  mov     rax, [rsp+78h+arg_28]
0x18001a5c7  mov     [rbx+88h], rax
0x18001a5ce  mov     rax, [rsp+78h+arg_0]
0x18001a5d6  mov     [rbx+90h], rax
0x18001a5dd  mov     [rbx+48h], rdi
0x18001a5e1  xorps   xmm0, xmm0
0x18001a5e4  xor     eax, eax
0x18001a5e6  movups  xmmword ptr [rbx+68h], xmm0
0x18001a5ea  mov     [rbx+78h], rax
0x18001a5ee  movups  xmmword ptr [rbx+50h], xmm0
0x18001a5f2  mov     [rbx+60h], rax
0x18001a5f6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001a5fd  test    rax, rax
0x18001a600  jz      short loc_18001A609
0x18001a602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a607  jmp     short loc_18001A60C
0x18001a609  mov     rax, rdi
0x18001a60c  mov     [rbx+80h], rax
0x18001a613  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001a61a  test    rax, rax
0x18001a61d  jz      short loc_18001A627
0x18001a61f  mov     rcx, rbx
0x18001a622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a627  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001a62e  test    rax, rax
0x18001a631  jz      short loc_18001A649
0x18001a633  mov     r8d, 400h
0x18001a639  mov     rdx, [rsp+78h+arg_60]
0x18001a641  mov     rcx, rbx
0x18001a644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a649  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001a650  test    rax, rax
0x18001a653  jz      short loc_18001A65D
0x18001a655  mov     rcx, rbx
0x18001a658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a65d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001a664  test    rax, rax
0x18001a667  jz      short loc_18001A677
0x18001a669  test    byte ptr [rbx+4], 2
0x18001a66d  jnz     short loc_18001A677
0x18001a66f  mov     rcx, rbx
0x18001a672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a677  cmp     [rbx+8], edi
0x18001a67a  jl      short loc_18001A698
0x18001a67c  cmp     r15d, 3
0x18001a680  jz      short loc_18001A688
0x18001a682  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001a688  mov     ecx, 8000FFFFh; this
0x18001a68d  mov     [rbx+8], ecx
0x18001a690  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001a695  mov     [rbx+0Ch], eax
0x18001a698  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001a69f  jnz     short loc_18001A6C6
0x18001a6a1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001a6a8  test    rax, rax
0x18001a6ab  jz      short loc_18001A6B6
0x18001a6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6b2  test    al, al
0x18001a6b4  jmp     short loc_18001A6C4
0x18001a6b6  call    cs:__imp_IsDebuggerPresent
0x18001a6bd  nop     dword ptr [rax+rax+00h]
0x18001a6c2  test    eax, eax
0x18001a6c4  jz      short loc_18001A6CC
0x18001a6c6  test    byte ptr [rbx+4], 2
0x18001a6ca  jz      short loc_18001A6F0
0x18001a6cc  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a6d3  test    rax, rax
0x18001a6d6  jz      short loc_18001A73A
0x18001a6d8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001a6df  jnz     short loc_18001A73A
0x18001a6e1  xor     r8d, r8d
0x18001a6e4  xor     edx, edx
0x18001a6e6  mov     rcx, rbx
0x18001a6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6ee  jmp     short loc_18001A73A
0x18001a6f0  mov     ebp, 800h
0x18001a6f5  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a6fc  test    rax, rax
0x18001a6ff  jz      short loc_18001A718
0x18001a701  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001a708  jnz     short loc_18001A718
0x18001a70a  mov     r8d, ebp
0x18001a70d  mov     rdx, rsi
0x18001a710  mov     rcx, rbx
0x18001a713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a718  cmp     [rsi], di
0x18001a71b  jnz     short loc_18001A72B
0x18001a71d  mov     r8, rbx; unsigned __int64
0x18001a720  mov     rdx, rbp; unsigned __int16 *
0x18001a723  mov     rcx, rsi; this
0x18001a726  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001a72b  mov     rcx, rsi; lpOutputString
0x18001a72e  call    cs:__imp_OutputDebugStringW
0x18001a735  nop     dword ptr [rax+rax+00h]
0x18001a73a  test    byte ptr [rbx+4], 4
0x18001a73e  jnz     short loc_18001A749
0x18001a740  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001a747  jz      short loc_18001A75B
0x18001a749  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001a750  test    rax, rax
0x18001a753  jz      short loc_18001A75B
0x18001a755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a75a  nop
0x18001a75b  mov     rbx, [rsp+78h+arg_10]
0x18001a763  add     rsp, 40h
0x18001a767  pop     r15
0x18001a769  pop     r14
0x18001a76b  pop     r13
0x18001a76d  pop     r12
0x18001a76f  pop     rdi
0x18001a770  pop     rsi
0x18001a771  pop     rbp
0x18001a772  retn
```
