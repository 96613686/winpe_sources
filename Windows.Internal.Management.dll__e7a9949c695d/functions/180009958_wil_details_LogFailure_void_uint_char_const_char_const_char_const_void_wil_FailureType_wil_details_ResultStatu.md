# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180009958`
- end: `0x180009c51`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180007f64`
- `0x1800082d0`
- `0x18001e164`

## callees

- `0x180007e9c`
- `0x180008f84`
- `0x180009768`
- `0x180009958`
- `0x18000a040`
- `0x18000a060`
- `0x18000a074`
- `0x18000a090`
- `0x18000aef4`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a7b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009c0c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009c0c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009b9a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009b9a`

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
0x180009958  mov     [rsp+arg_10], rbx
0x18000995d  mov     [rsp+arg_8], edx
0x180009961  mov     [rsp+arg_0], rcx
0x180009966  push    rbp
0x180009967  push    rsi
0x180009968  push    rdi
0x180009969  push    r12
0x18000996b  push    r13
0x18000996d  push    r14
0x18000996f  push    r15
0x180009971  sub     rsp, 40h
0x180009975  mov     r12, r9
0x180009978  mov     r13, r8
0x18000997b  mov     r10, rcx
0x18000997e  xor     eax, eax
0x180009980  mov     rsi, [rsp+78h+lpOutputString]
0x180009988  mov     [rsi], ax
0x18000998b  mov     rax, [rsp+78h+arg_60]
0x180009993  mov     byte ptr [rax], 0
0x180009996  mov     r14, [rsp+78h+arg_38]
0x18000999e  mov     edi, [r14]
0x1800099a1  mov     rbx, [rsp+78h+arg_78]
0x1800099a9  mov     [rbx+8], edi
0x1800099ac  mov     eax, [r14+4]
0x1800099b0  mov     [rbx+0Ch], eax
0x1800099b3  xor     ebp, ebp
0x1800099b5  mov     r15d, [rsp+78h+arg_30]
0x1800099bd  mov     ecx, r15d
0x1800099c0  test    r15d, r15d
0x1800099c3  jz      short loc_180009A2B
0x1800099c5  sub     ecx, 1
0x1800099c8  jz      short loc_180009A22
0x1800099ca  sub     ecx, 1
0x1800099cd  jz      short loc_1800099DD
0x1800099cf  cmp     ecx, 1
0x1800099d2  jnz     short loc_180009A34
0x1800099d4  mov     ecx, edi; this
0x1800099d6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800099db  jmp     short loc_180009A32
0x1800099dd  test    edi, edi
0x1800099df  js      short loc_180009A19
0x1800099e1  mov     edi, 8007029Ch
0x1800099e6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800099ea  mov     rax, [rsp+78h+arg_28]
0x1800099f2  mov     [rsp+78h+var_50], rax; __int64
0x1800099f7  mov     rax, [rsp+78h+arg_20]
0x1800099ff  mov     [rsp+78h+var_58], rax; __int64
0x180009a04  mov     rcx, r10; int
0x180009a07  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009a0c  mov     [rbx+8], edi
0x180009a0f  mov     ecx, edi; this
0x180009a11  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009a16  mov     [rbx+0Ch], eax
0x180009a19  mov     ecx, edi; this
0x180009a1b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009a20  jmp     short loc_180009A32
0x180009a22  mov     ecx, edi; this
0x180009a24  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009a29  jmp     short loc_180009A32
0x180009a2b  mov     ecx, edi; this
0x180009a2d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009a32  mov     ebp, eax
0x180009a34  mov     [rbx], r15d
0x180009a37  mov     eax, [rsp+78h+arg_70]
0x180009a3e  mov     [rbx+4], eax
0x180009a41  cmp     dword ptr [r14+8], 1
0x180009a46  jnz     short loc_180009A4E
0x180009a48  or      eax, 8
0x180009a4b  mov     [rbx+4], eax
0x180009a4e  mov     eax, 1
0x180009a53  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009a5b  inc     eax
0x180009a5d  mov     [rbx+10h], eax
0x180009a60  mov     rax, [rsp+78h+arg_40]
0x180009a68  xor     edi, edi
0x180009a6a  test    rax, rax
0x180009a6d  jz      short loc_180009A74
0x180009a6f  cmp     [rax], di
0x180009a72  jnz     short loc_180009A77
0x180009a74  mov     rax, rdi
0x180009a77  mov     [rbx+18h], rax
0x180009a7b  call    cs:__imp_GetCurrentThreadId
0x180009a81  mov     [rbx+20h], eax
0x180009a84  mov     [rbx+38h], r13
0x180009a88  mov     eax, [rsp+78h+arg_8]
0x180009a8f  mov     [rbx+40h], eax
0x180009a92  mov     [rbx+44h], ebp
0x180009a95  mov     rax, [rsp+78h+arg_20]
0x180009a9d  mov     [rbx+28h], rax
0x180009aa1  mov     [rbx+30h], r12
0x180009aa5  mov     rax, [rsp+78h+arg_28]
0x180009aad  mov     [rbx+88h], rax
0x180009ab4  mov     rax, [rsp+78h+arg_0]
0x180009abc  mov     [rbx+90h], rax
0x180009ac3  mov     [rbx+48h], rdi
0x180009ac7  xorps   xmm0, xmm0
0x180009aca  xor     eax, eax
0x180009acc  movups  xmmword ptr [rbx+68h], xmm0
0x180009ad0  mov     [rbx+78h], rax
0x180009ad4  movups  xmmword ptr [rbx+50h], xmm0
0x180009ad8  mov     [rbx+60h], rax
0x180009adc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009ae3  test    rax, rax
0x180009ae6  jz      short loc_180009AEF
0x180009ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aed  jmp     short loc_180009AF2
0x180009aef  mov     rax, rdi
0x180009af2  mov     [rbx+80h], rax
0x180009af9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009b00  test    rax, rax
0x180009b03  jz      short loc_180009B0D
0x180009b05  mov     rcx, rbx
0x180009b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b0d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009b14  test    rax, rax
0x180009b17  jz      short loc_180009B2F
0x180009b19  mov     r8d, 400h
0x180009b1f  mov     rdx, [rsp+78h+arg_60]
0x180009b27  mov     rcx, rbx
0x180009b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b2f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009b36  test    rax, rax
0x180009b39  jz      short loc_180009B43
0x180009b3b  mov     rcx, rbx
0x180009b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b43  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009b4a  test    rax, rax
0x180009b4d  jz      short loc_180009B5D
0x180009b4f  test    byte ptr [rbx+4], 2
0x180009b53  jnz     short loc_180009B5D
0x180009b55  mov     rcx, rbx
0x180009b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b5d  cmp     [rbx+8], edi
0x180009b60  jl      short loc_180009B7C
0x180009b62  cmp     r15d, 3
0x180009b66  jnz     loc_180009C4B
0x180009b6c  mov     ecx, 8000FFFFh; this
0x180009b71  mov     [rbx+8], ecx
0x180009b74  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009b79  mov     [rbx+0Ch], eax
0x180009b7c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180009b83  jnz     short loc_180009BA4
0x180009b85  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009b8c  test    rax, rax
0x180009b8f  jz      short loc_180009B9A
0x180009b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b96  test    al, al
0x180009b98  jmp     short loc_180009BA2
0x180009b9a  call    cs:__imp_IsDebuggerPresent
0x180009ba0  test    eax, eax
0x180009ba2  jz      short loc_180009BAA
0x180009ba4  test    byte ptr [rbx+4], 2
0x180009ba8  jz      short loc_180009BCE
0x180009baa  mov     rax, cs:g_pfnResultLoggingCallback
0x180009bb1  test    rax, rax
0x180009bb4  jz      short loc_180009C12
0x180009bb6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009bbd  jnz     short loc_180009C12
0x180009bbf  xor     r8d, r8d
0x180009bc2  xor     edx, edx
0x180009bc4  mov     rcx, rbx
0x180009bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bcc  jmp     short loc_180009C12
0x180009bce  mov     ebp, 800h
0x180009bd3  mov     rax, cs:g_pfnResultLoggingCallback
0x180009bda  test    rax, rax
0x180009bdd  jz      short loc_180009BF6
0x180009bdf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009be6  jnz     short loc_180009BF6
0x180009be8  mov     r8d, ebp
0x180009beb  mov     rdx, rsi
0x180009bee  mov     rcx, rbx
0x180009bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bf6  cmp     [rsi], di
0x180009bf9  jnz     short loc_180009C09
0x180009bfb  mov     r8, rbx; unsigned __int64
0x180009bfe  mov     rdx, rbp; unsigned __int16 *
0x180009c01  mov     rcx, rsi; this
0x180009c04  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009c09  mov     rcx, rsi; lpOutputString
0x180009c0c  call    cs:__imp_OutputDebugStringW
0x180009c12  test    byte ptr [rbx+4], 4
0x180009c16  jnz     short loc_180009C21
0x180009c18  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009c1f  jz      short loc_180009C33
0x180009c21  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009c28  test    rax, rax
0x180009c2b  jz      short loc_180009C33
0x180009c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c32  nop
0x180009c33  mov     rbx, [rsp+78h+arg_10]
0x180009c3b  add     rsp, 40h
0x180009c3f  pop     r15
0x180009c41  pop     r14
0x180009c43  pop     r13
0x180009c45  pop     r12
0x180009c47  pop     rdi
0x180009c48  pop     rsi
0x180009c49  pop     rbp
0x180009c4a  retn
0x180009c4b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
