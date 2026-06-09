# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000b5b4`
- end: `0x14000b8ad`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140007648`

## callees

- `0x140007084`
- `0x14000a4a4`
- `0x14000ac7c`
- `0x14000b5b4`
- `0x14000c334`
- `0x14000c350`
- `0x14000c47c`
- `0x14000c498`
- `0x14000ecd4`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b6d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b6d7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000b7f6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000b7f6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000b868`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000b868`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x14000b5b4  mov     [rsp+arg_10], rbx
0x14000b5b9  mov     [rsp+arg_8], edx
0x14000b5bd  mov     [rsp+arg_0], rcx
0x14000b5c2  push    rbp
0x14000b5c3  push    rsi
0x14000b5c4  push    rdi
0x14000b5c5  push    r12
0x14000b5c7  push    r13
0x14000b5c9  push    r14
0x14000b5cb  push    r15
0x14000b5cd  sub     rsp, 40h
0x14000b5d1  mov     r12, r9
0x14000b5d4  mov     r13, r8
0x14000b5d7  mov     r10, rcx
0x14000b5da  xor     eax, eax
0x14000b5dc  mov     rsi, [rsp+78h+lpOutputString]
0x14000b5e4  mov     [rsi], ax
0x14000b5e7  mov     rax, [rsp+78h+arg_60]
0x14000b5ef  mov     byte ptr [rax], 0
0x14000b5f2  mov     r14, [rsp+78h+arg_38]
0x14000b5fa  mov     edi, [r14]
0x14000b5fd  mov     rbx, [rsp+78h+arg_78]
0x14000b605  mov     [rbx+8], edi
0x14000b608  mov     eax, [r14+4]
0x14000b60c  mov     [rbx+0Ch], eax
0x14000b60f  xor     ebp, ebp
0x14000b611  mov     r15d, [rsp+78h+arg_30]
0x14000b619  mov     ecx, r15d
0x14000b61c  test    r15d, r15d
0x14000b61f  jz      short loc_14000B687
0x14000b621  sub     ecx, 1
0x14000b624  jz      short loc_14000B67E
0x14000b626  sub     ecx, 1
0x14000b629  jz      short loc_14000B639
0x14000b62b  cmp     ecx, 1
0x14000b62e  jnz     short loc_14000B690
0x14000b630  mov     ecx, edi; this
0x14000b632  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000b637  jmp     short loc_14000B68E
0x14000b639  test    edi, edi
0x14000b63b  js      short loc_14000B675
0x14000b63d  mov     edi, 8007029Ch
0x14000b642  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000b646  mov     rax, [rsp+78h+arg_28]
0x14000b64e  mov     [rsp+78h+var_50], rax; __int64
0x14000b653  mov     rax, [rsp+78h+arg_20]
0x14000b65b  mov     [rsp+78h+var_58], rax; __int64
0x14000b660  mov     rcx, r10; int
0x14000b663  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000b668  mov     [rbx+8], edi
0x14000b66b  mov     ecx, edi; this
0x14000b66d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000b672  mov     [rbx+0Ch], eax
0x14000b675  mov     ecx, edi; this
0x14000b677  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000b67c  jmp     short loc_14000B68E
0x14000b67e  mov     ecx, edi; this
0x14000b680  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000b685  jmp     short loc_14000B68E
0x14000b687  mov     ecx, edi; this
0x14000b689  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000b68e  mov     ebp, eax
0x14000b690  mov     [rbx], r15d
0x14000b693  mov     eax, [rsp+78h+arg_70]
0x14000b69a  mov     [rbx+4], eax
0x14000b69d  cmp     dword ptr [r14+8], 1
0x14000b6a2  jnz     short loc_14000B6AA
0x14000b6a4  or      eax, 8
0x14000b6a7  mov     [rbx+4], eax
0x14000b6aa  mov     eax, 1
0x14000b6af  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000b6b7  inc     eax
0x14000b6b9  mov     [rbx+10h], eax
0x14000b6bc  mov     rax, [rsp+78h+arg_40]
0x14000b6c4  xor     edi, edi
0x14000b6c6  test    rax, rax
0x14000b6c9  jz      short loc_14000B6D0
0x14000b6cb  cmp     [rax], di
0x14000b6ce  jnz     short loc_14000B6D3
0x14000b6d0  mov     rax, rdi
0x14000b6d3  mov     [rbx+18h], rax
0x14000b6d7  call    cs:__imp_GetCurrentThreadId
0x14000b6dd  mov     [rbx+20h], eax
0x14000b6e0  mov     [rbx+38h], r13
0x14000b6e4  mov     eax, [rsp+78h+arg_8]
0x14000b6eb  mov     [rbx+40h], eax
0x14000b6ee  mov     [rbx+44h], ebp
0x14000b6f1  mov     rax, [rsp+78h+arg_20]
0x14000b6f9  mov     [rbx+28h], rax
0x14000b6fd  mov     [rbx+30h], r12
0x14000b701  mov     rax, [rsp+78h+arg_28]
0x14000b709  mov     [rbx+88h], rax
0x14000b710  mov     rax, [rsp+78h+arg_0]
0x14000b718  mov     [rbx+90h], rax
0x14000b71f  mov     [rbx+48h], rdi
0x14000b723  xorps   xmm0, xmm0
0x14000b726  xor     eax, eax
0x14000b728  movups  xmmword ptr [rbx+68h], xmm0
0x14000b72c  mov     [rbx+78h], rax
0x14000b730  movups  xmmword ptr [rbx+50h], xmm0
0x14000b734  mov     [rbx+60h], rax
0x14000b738  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000b73f  test    rax, rax
0x14000b742  jz      short loc_14000B74B
0x14000b744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b749  jmp     short loc_14000B74E
0x14000b74b  mov     rax, rdi
0x14000b74e  mov     [rbx+80h], rax
0x14000b755  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000b75c  test    rax, rax
0x14000b75f  jz      short loc_14000B769
0x14000b761  mov     rcx, rbx
0x14000b764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b769  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000b770  test    rax, rax
0x14000b773  jz      short loc_14000B78B
0x14000b775  mov     r8d, 400h
0x14000b77b  mov     rdx, [rsp+78h+arg_60]
0x14000b783  mov     rcx, rbx
0x14000b786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b78b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000b792  test    rax, rax
0x14000b795  jz      short loc_14000B79F
0x14000b797  mov     rcx, rbx
0x14000b79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b79f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000b7a6  test    rax, rax
0x14000b7a9  jz      short loc_14000B7B9
0x14000b7ab  test    byte ptr [rbx+4], 2
0x14000b7af  jnz     short loc_14000B7B9
0x14000b7b1  mov     rcx, rbx
0x14000b7b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b7b9  cmp     [rbx+8], edi
0x14000b7bc  jl      short loc_14000B7D8
0x14000b7be  cmp     r15d, 3
0x14000b7c2  jnz     loc_14000B8A7
0x14000b7c8  mov     ecx, 8000FFFFh; this
0x14000b7cd  mov     [rbx+8], ecx
0x14000b7d0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000b7d5  mov     [rbx+0Ch], eax
0x14000b7d8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000b7df  jnz     short loc_14000B800
0x14000b7e1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000b7e8  test    rax, rax
0x14000b7eb  jz      short loc_14000B7F6
0x14000b7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b7f2  test    al, al
0x14000b7f4  jmp     short loc_14000B7FE
0x14000b7f6  call    cs:__imp_IsDebuggerPresent
0x14000b7fc  test    eax, eax
0x14000b7fe  jz      short loc_14000B806
0x14000b800  test    byte ptr [rbx+4], 2
0x14000b804  jz      short loc_14000B82A
0x14000b806  mov     rax, cs:g_pfnResultLoggingCallback
0x14000b80d  test    rax, rax
0x14000b810  jz      short loc_14000B86E
0x14000b812  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000b819  jnz     short loc_14000B86E
0x14000b81b  xor     r8d, r8d
0x14000b81e  xor     edx, edx
0x14000b820  mov     rcx, rbx
0x14000b823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b828  jmp     short loc_14000B86E
0x14000b82a  mov     ebp, 800h
0x14000b82f  mov     rax, cs:g_pfnResultLoggingCallback
0x14000b836  test    rax, rax
0x14000b839  jz      short loc_14000B852
0x14000b83b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000b842  jnz     short loc_14000B852
0x14000b844  mov     r8d, ebp
0x14000b847  mov     rdx, rsi
0x14000b84a  mov     rcx, rbx
0x14000b84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b852  cmp     [rsi], di
0x14000b855  jnz     short loc_14000B865
0x14000b857  mov     r8, rbx; unsigned __int64
0x14000b85a  mov     rdx, rbp; unsigned __int16 *
0x14000b85d  mov     rcx, rsi; this
0x14000b860  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000b865  mov     rcx, rsi; lpOutputString
0x14000b868  call    cs:__imp_OutputDebugStringW
0x14000b86e  test    byte ptr [rbx+4], 4
0x14000b872  jnz     short loc_14000B87D
0x14000b874  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000b87b  jz      short loc_14000B88F
0x14000b87d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000b884  test    rax, rax
0x14000b887  jz      short loc_14000B88F
0x14000b889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b88e  nop
0x14000b88f  mov     rbx, [rsp+78h+arg_10]
0x14000b897  add     rsp, 40h
0x14000b89b  pop     r15
0x14000b89d  pop     r14
0x14000b89f  pop     r13
0x14000b8a1  pop     r12
0x14000b8a3  pop     rdi
0x14000b8a4  pop     rsi
0x14000b8a5  pop     rbp
0x14000b8a6  retn
0x14000b8a7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
