# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x180011894`
- end: `0x180011b97`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `771`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800117a0`
- `0x18001da10`
- `0x18001dac4`

## callees

- `0x180011894`
- `0x180012090`
- `0x18001328c`
- `0x18001d960`
- `0x180020c4c`
- `0x180021c08`
- `0x180021c30`
- `0x180021d38`
- `0x180024368`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800119b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800119b3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011ad9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011ad9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011b52`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011b52`

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
        unsigned __int64 a15)
{
  int v17; // esi
  unsigned int v18; // edi
  int v19; // eax
  int v20; // edx
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  v17 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a15 + 8) = *a8;
  *(_DWORD *)(a15 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a15 + 8) = -2147024228;
          *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v20);
        }
        v19 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v17 = v19;
LABEL_12:
  *(_DWORD *)a15 = a7;
  *(_DWORD *)(a15 + 4) = 0;
  if ( a8[2] == 1 )
    *(_DWORD *)(a15 + 4) = 8;
  *(_DWORD *)(a15 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a15 + 24) = v21;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a15 + 56) = a3;
  *(_DWORD *)(a15 + 32) = CurrentThreadId;
  *(_DWORD *)(a15 + 64) = a2;
  *(_QWORD *)(a15 + 40) = a5;
  *(_QWORD *)(a15 + 136) = a6;
  *(_QWORD *)(a15 + 144) = a1;
  *(_DWORD *)(a15 + 68) = v17;
  *(_QWORD *)(a15 + 48) = a4;
  *(_QWORD *)(a15 + 72) = 0;
  *(_OWORD *)(a15 + 104) = 0;
  *(_QWORD *)(a15 + 120) = 0;
  *(_OWORD *)(a15 + 80) = 0;
  *(_QWORD *)(a15 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a15 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a15, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a15);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a15 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a15);
  if ( *(int *)(a15 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a15 + 8) = -2147418113;
    *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
    || (*(_BYTE *)(a15 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a15, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a15 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180011894  mov     [rsp+arg_10], rbx
0x180011899  mov     [rsp+arg_8], edx
0x18001189d  mov     [rsp+arg_0], rcx
0x1800118a2  push    rbp
0x1800118a3  push    rsi
0x1800118a4  push    rdi
0x1800118a5  push    r12
0x1800118a7  push    r13
0x1800118a9  push    r14
0x1800118ab  push    r15
0x1800118ad  sub     rsp, 40h
0x1800118b1  mov     rax, [rsp+78h+arg_60]
0x1800118b9  mov     r13, r8
0x1800118bc  mov     r15, [rsp+78h+arg_38]
0x1800118c4  xor     r8d, r8d
0x1800118c7  mov     rbx, [rsp+78h+arg_70]
0x1800118cf  mov     r10, rcx
0x1800118d2  mov     ebp, [rsp+78h+arg_30]
0x1800118d9  mov     r12, r9
0x1800118dc  mov     r14, [rsp+78h+lpOutputString]
0x1800118e4  mov     esi, r8d
0x1800118e7  mov     ecx, ebp
0x1800118e9  mov     [r14], r8w
0x1800118ed  mov     [rax], r8b
0x1800118f0  mov     edi, [r15]
0x1800118f3  mov     [rbx+8], edi
0x1800118f6  mov     eax, [r15+4]
0x1800118fa  mov     [rbx+0Ch], eax
0x1800118fd  test    ebp, ebp
0x1800118ff  jz      short loc_18001196A
0x180011901  sub     ecx, 1
0x180011904  jz      short loc_180011961
0x180011906  sub     ecx, 1
0x180011909  jz      short loc_180011919
0x18001190b  cmp     ecx, 1
0x18001190e  jnz     short loc_180011973
0x180011910  mov     ecx, edi; this
0x180011912  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180011917  jmp     short loc_180011971
0x180011919  test    edi, edi
0x18001191b  js      short loc_180011958
0x18001191d  mov     rax, [rsp+78h+arg_28]
0x180011925  mov     edi, 8007029Ch
0x18001192a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001192e  mov     r8, r13; int
0x180011931  mov     [rsp+78h+var_50], rax; __int64
0x180011936  mov     rcx, r10; int
0x180011939  mov     rax, [rsp+78h+arg_20]
0x180011941  mov     [rsp+78h+var_58], rax; __int64
0x180011946  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x18001194b  mov     ecx, edi; this
0x18001194d  mov     [rbx+8], edi
0x180011950  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011955  mov     [rbx+0Ch], eax
0x180011958  mov     ecx, edi; this
0x18001195a  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001195f  jmp     short loc_180011971
0x180011961  mov     ecx, edi; this
0x180011963  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180011968  jmp     short loc_180011971
0x18001196a  mov     ecx, edi; this
0x18001196c  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180011971  mov     esi, eax
0x180011973  xor     edi, edi
0x180011975  mov     [rbx], ebp
0x180011977  mov     [rbx+4], edi
0x18001197a  cmp     dword ptr [r15+8], 1
0x18001197f  jnz     short loc_180011988
0x180011981  mov     dword ptr [rbx+4], 8
0x180011988  mov     eax, 1
0x18001198d  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180011995  inc     eax
0x180011997  mov     [rbx+10h], eax
0x18001199a  mov     rax, [rsp+78h+arg_40]
0x1800119a2  test    rax, rax
0x1800119a5  jz      short loc_1800119AC
0x1800119a7  cmp     [rax], di
0x1800119aa  jnz     short loc_1800119AF
0x1800119ac  mov     rax, rdi
0x1800119af  mov     [rbx+18h], rax
0x1800119b3  call    cs:__imp_GetCurrentThreadId
0x1800119ba  nop     dword ptr [rax+rax+00h]
0x1800119bf  mov     [rbx+38h], r13
0x1800119c3  xorps   xmm0, xmm0
0x1800119c6  mov     [rbx+20h], eax
0x1800119c9  mov     eax, [rsp+78h+arg_8]
0x1800119d0  mov     [rbx+40h], eax
0x1800119d3  mov     rax, [rsp+78h+arg_20]
0x1800119db  mov     [rbx+28h], rax
0x1800119df  mov     rax, [rsp+78h+arg_28]
0x1800119e7  mov     [rbx+88h], rax
0x1800119ee  mov     rax, [rsp+78h+arg_0]
0x1800119f6  mov     [rbx+90h], rax
0x1800119fd  xor     eax, eax
0x1800119ff  mov     [rbx+44h], esi
0x180011a02  mov     [rbx+30h], r12
0x180011a06  mov     [rbx+48h], rdi
0x180011a0a  movups  xmmword ptr [rbx+68h], xmm0
0x180011a0e  mov     [rbx+78h], rax
0x180011a12  movups  xmmword ptr [rbx+50h], xmm0
0x180011a16  mov     [rbx+60h], rax
0x180011a1a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011a21  test    rax, rax
0x180011a24  jz      short loc_180011A2D
0x180011a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a2b  jmp     short loc_180011A30
0x180011a2d  mov     rax, rdi
0x180011a30  mov     [rbx+80h], rax
0x180011a37  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180011a3e  test    rax, rax
0x180011a41  jz      short loc_180011A4B
0x180011a43  mov     rcx, rbx
0x180011a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a4b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011a52  test    rax, rax
0x180011a55  jz      short loc_180011A6D
0x180011a57  mov     rdx, [rsp+78h+arg_60]
0x180011a5f  mov     r8d, 400h
0x180011a65  mov     rcx, rbx
0x180011a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a6d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011a74  test    rax, rax
0x180011a77  jz      short loc_180011A81
0x180011a79  mov     rcx, rbx
0x180011a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a81  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011a88  test    rax, rax
0x180011a8b  jz      short loc_180011A9B
0x180011a8d  test    byte ptr [rbx+4], 2
0x180011a91  jnz     short loc_180011A9B
0x180011a93  mov     rcx, rbx
0x180011a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a9b  cmp     [rbx+8], edi
0x180011a9e  jl      short loc_180011ABB
0x180011aa0  cmp     ebp, 3
0x180011aa3  jz      short loc_180011AAB
0x180011aa5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180011aab  mov     ecx, 8000FFFFh; this
0x180011ab0  mov     [rbx+8], ecx
0x180011ab3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011ab8  mov     [rbx+0Ch], eax
0x180011abb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180011ac2  jnz     short loc_180011AE9
0x180011ac4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180011acb  test    rax, rax
0x180011ace  jz      short loc_180011AD9
0x180011ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ad5  test    al, al
0x180011ad7  jmp     short loc_180011AE7
0x180011ad9  call    cs:__imp_IsDebuggerPresent
0x180011ae0  nop     dword ptr [rax+rax+00h]
0x180011ae5  test    eax, eax
0x180011ae7  jz      short loc_180011AEF
0x180011ae9  test    byte ptr [rbx+4], 2
0x180011aed  jz      short loc_180011B13
0x180011aef  mov     rax, cs:g_pfnResultLoggingCallback
0x180011af6  test    rax, rax
0x180011af9  jz      short loc_180011B5E
0x180011afb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011b02  jnz     short loc_180011B5E
0x180011b04  xor     r8d, r8d
0x180011b07  xor     edx, edx
0x180011b09  mov     rcx, rbx
0x180011b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b11  jmp     short loc_180011B5E
0x180011b13  mov     rax, cs:g_pfnResultLoggingCallback
0x180011b1a  mov     esi, 800h
0x180011b1f  test    rax, rax
0x180011b22  jz      short loc_180011B3B
0x180011b24  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011b2b  jnz     short loc_180011B3B
0x180011b2d  mov     r8d, esi
0x180011b30  mov     rdx, r14
0x180011b33  mov     rcx, rbx
0x180011b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b3b  cmp     [r14], di
0x180011b3f  jnz     short loc_180011B4F
0x180011b41  mov     r8, rbx; unsigned __int64
0x180011b44  mov     rdx, rsi; unsigned __int16 *
0x180011b47  mov     rcx, r14; this
0x180011b4a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180011b4f  mov     rcx, r14; lpOutputString
0x180011b52  call    cs:__imp_OutputDebugStringW
0x180011b59  nop     dword ptr [rax+rax+00h]
0x180011b5e  test    byte ptr [rbx+4], 4
0x180011b62  jnz     short loc_180011B6D
0x180011b64  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180011b6b  jz      short loc_180011B7E
0x180011b6d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180011b74  test    rax, rax
0x180011b77  jz      short loc_180011B7E
0x180011b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b7e  mov     rbx, [rsp+78h+arg_10]
0x180011b86  add     rsp, 40h
0x180011b8a  pop     r15
0x180011b8c  pop     r14
0x180011b8e  pop     r13
0x180011b90  pop     r12
0x180011b92  pop     rdi
0x180011b93  pop     rsi
0x180011b94  pop     rbp
0x180011b95  retn
```
