# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007900`
- end: `0x180007c0c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180004a00`
- `0x180004d80`
- `0x18000e9c0`

## callees

- `0x180004938`
- `0x180006bb4`
- `0x1800074d0`
- `0x180007900`
- `0x1800088d8`
- `0x180008900`
- `0x180008a64`
- `0x180008a84`
- `0x18000acb4`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a23`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007b48`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007b48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007bc0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007bc0`

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
0x180007900  mov     [rsp+arg_10], rbx
0x180007905  mov     [rsp+arg_8], edx
0x180007909  mov     [rsp+arg_0], rcx
0x18000790e  push    rbp
0x18000790f  push    rsi
0x180007910  push    rdi
0x180007911  push    r12
0x180007913  push    r13
0x180007915  push    r14
0x180007917  push    r15
0x180007919  sub     rsp, 40h
0x18000791d  mov     r12, r9
0x180007920  mov     r13, r8
0x180007923  mov     r10, rcx
0x180007926  xor     eax, eax
0x180007928  mov     rsi, [rsp+78h+lpOutputString]
0x180007930  mov     [rsi], ax
0x180007933  mov     rax, [rsp+78h+arg_60]
0x18000793b  mov     byte ptr [rax], 0
0x18000793e  mov     r14, [rsp+78h+arg_38]
0x180007946  mov     edi, [r14]
0x180007949  mov     rbx, [rsp+78h+arg_78]
0x180007951  mov     [rbx+8], edi
0x180007954  mov     eax, [r14+4]
0x180007958  mov     [rbx+0Ch], eax
0x18000795b  xor     ebp, ebp
0x18000795d  mov     r15d, [rsp+78h+arg_30]
0x180007965  mov     ecx, r15d
0x180007968  test    r15d, r15d
0x18000796b  jz      short loc_1800079D3
0x18000796d  sub     ecx, 1
0x180007970  jz      short loc_1800079CA
0x180007972  sub     ecx, 1
0x180007975  jz      short loc_180007985
0x180007977  cmp     ecx, 1
0x18000797a  jnz     short loc_1800079DC
0x18000797c  mov     ecx, edi; this
0x18000797e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007983  jmp     short loc_1800079DA
0x180007985  test    edi, edi
0x180007987  js      short loc_1800079C1
0x180007989  mov     edi, 8007029Ch
0x18000798e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007992  mov     rax, [rsp+78h+arg_28]
0x18000799a  mov     [rsp+78h+var_50], rax; __int64
0x18000799f  mov     rax, [rsp+78h+arg_20]
0x1800079a7  mov     [rsp+78h+var_58], rax; __int64
0x1800079ac  mov     rcx, r10; int
0x1800079af  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800079b4  mov     [rbx+8], edi
0x1800079b7  mov     ecx, edi; this
0x1800079b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800079be  mov     [rbx+0Ch], eax
0x1800079c1  mov     ecx, edi; this
0x1800079c3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800079c8  jmp     short loc_1800079DA
0x1800079ca  mov     ecx, edi; this
0x1800079cc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800079d1  jmp     short loc_1800079DA
0x1800079d3  mov     ecx, edi; this
0x1800079d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800079da  mov     ebp, eax
0x1800079dc  mov     [rbx], r15d
0x1800079df  mov     eax, [rsp+78h+arg_70]
0x1800079e6  mov     [rbx+4], eax
0x1800079e9  cmp     dword ptr [r14+8], 1
0x1800079ee  jnz     short loc_1800079F6
0x1800079f0  or      eax, 8
0x1800079f3  mov     [rbx+4], eax
0x1800079f6  mov     eax, 1
0x1800079fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007a03  inc     eax
0x180007a05  mov     [rbx+10h], eax
0x180007a08  mov     rax, [rsp+78h+arg_40]
0x180007a10  xor     edi, edi
0x180007a12  test    rax, rax
0x180007a15  jz      short loc_180007A1C
0x180007a17  cmp     [rax], di
0x180007a1a  jnz     short loc_180007A1F
0x180007a1c  mov     rax, rdi
0x180007a1f  mov     [rbx+18h], rax
0x180007a23  call    cs:__imp_GetCurrentThreadId
0x180007a2a  nop     dword ptr [rax+rax+00h]
0x180007a2f  mov     [rbx+20h], eax
0x180007a32  mov     [rbx+38h], r13
0x180007a36  mov     eax, [rsp+78h+arg_8]
0x180007a3d  mov     [rbx+40h], eax
0x180007a40  mov     [rbx+44h], ebp
0x180007a43  mov     rax, [rsp+78h+arg_20]
0x180007a4b  mov     [rbx+28h], rax
0x180007a4f  mov     [rbx+30h], r12
0x180007a53  mov     rax, [rsp+78h+arg_28]
0x180007a5b  mov     [rbx+88h], rax
0x180007a62  mov     rax, [rsp+78h+arg_0]
0x180007a6a  mov     [rbx+90h], rax
0x180007a71  mov     [rbx+48h], rdi
0x180007a75  xorps   xmm0, xmm0
0x180007a78  xor     eax, eax
0x180007a7a  movups  xmmword ptr [rbx+68h], xmm0
0x180007a7e  mov     [rbx+78h], rax
0x180007a82  movups  xmmword ptr [rbx+50h], xmm0
0x180007a86  mov     [rbx+60h], rax
0x180007a8a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007a91  test    rax, rax
0x180007a94  jz      short loc_180007A9D
0x180007a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a9b  jmp     short loc_180007AA0
0x180007a9d  mov     rax, rdi
0x180007aa0  mov     [rbx+80h], rax
0x180007aa7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007aae  test    rax, rax
0x180007ab1  jz      short loc_180007ABB
0x180007ab3  mov     rcx, rbx
0x180007ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007abb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007ac2  test    rax, rax
0x180007ac5  jz      short loc_180007ADD
0x180007ac7  mov     r8d, 400h
0x180007acd  mov     rdx, [rsp+78h+arg_60]
0x180007ad5  mov     rcx, rbx
0x180007ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007add  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007ae4  test    rax, rax
0x180007ae7  jz      short loc_180007AF1
0x180007ae9  mov     rcx, rbx
0x180007aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007af8  test    rax, rax
0x180007afb  jz      short loc_180007B0B
0x180007afd  test    byte ptr [rbx+4], 2
0x180007b01  jnz     short loc_180007B0B
0x180007b03  mov     rcx, rbx
0x180007b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b0b  cmp     [rbx+8], edi
0x180007b0e  jl      short loc_180007B2A
0x180007b10  cmp     r15d, 3
0x180007b14  jnz     loc_180007C06
0x180007b1a  mov     ecx, 8000FFFFh; this
0x180007b1f  mov     [rbx+8], ecx
0x180007b22  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007b27  mov     [rbx+0Ch], eax
0x180007b2a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007b31  jnz     short loc_180007B58
0x180007b33  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007b3a  test    rax, rax
0x180007b3d  jz      short loc_180007B48
0x180007b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b44  test    al, al
0x180007b46  jmp     short loc_180007B56
0x180007b48  call    cs:__imp_IsDebuggerPresent
0x180007b4f  nop     dword ptr [rax+rax+00h]
0x180007b54  test    eax, eax
0x180007b56  jz      short loc_180007B5E
0x180007b58  test    byte ptr [rbx+4], 2
0x180007b5c  jz      short loc_180007B82
0x180007b5e  mov     rax, cs:g_pfnResultLoggingCallback
0x180007b65  test    rax, rax
0x180007b68  jz      short loc_180007BCC
0x180007b6a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007b71  jnz     short loc_180007BCC
0x180007b73  xor     r8d, r8d
0x180007b76  xor     edx, edx
0x180007b78  mov     rcx, rbx
0x180007b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b80  jmp     short loc_180007BCC
0x180007b82  mov     ebp, 800h
0x180007b87  mov     rax, cs:g_pfnResultLoggingCallback
0x180007b8e  test    rax, rax
0x180007b91  jz      short loc_180007BAA
0x180007b93  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007b9a  jnz     short loc_180007BAA
0x180007b9c  mov     r8d, ebp
0x180007b9f  mov     rdx, rsi
0x180007ba2  mov     rcx, rbx
0x180007ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007baa  cmp     [rsi], di
0x180007bad  jnz     short loc_180007BBD
0x180007baf  mov     r8, rbx; unsigned __int64
0x180007bb2  mov     rdx, rbp; unsigned __int16 *
0x180007bb5  mov     rcx, rsi; this
0x180007bb8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007bbd  mov     rcx, rsi; lpOutputString
0x180007bc0  call    cs:__imp_OutputDebugStringW
0x180007bc7  nop     dword ptr [rax+rax+00h]
0x180007bcc  test    byte ptr [rbx+4], 4
0x180007bd0  jnz     short loc_180007BDB
0x180007bd2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007bd9  jz      short loc_180007BED
0x180007bdb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007be2  test    rax, rax
0x180007be5  jz      short loc_180007BED
0x180007be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bec  nop
0x180007bed  mov     rbx, [rsp+78h+arg_10]
0x180007bf5  add     rsp, 40h
0x180007bf9  pop     r15
0x180007bfb  pop     r14
0x180007bfd  pop     r13
0x180007bff  pop     r12
0x180007c01  pop     rdi
0x180007c02  pop     rsi
0x180007c03  pop     rbp
0x180007c04  retn
0x180007c06  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
