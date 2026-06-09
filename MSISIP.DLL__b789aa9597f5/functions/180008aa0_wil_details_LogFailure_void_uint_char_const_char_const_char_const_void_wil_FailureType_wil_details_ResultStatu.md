# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008aa0`
- end: `0x180008da1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180008914`
- `0x18000aa28`

## callees

- `0x1800061ac`
- `0x180008aa0`
- `0x180009788`
- `0x1800097a4`
- `0x180009aec`
- `0x18000a6c0`
- `0x18000b0c4`
- `0x18000bdcc`
- `0x18000bdf0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008bcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008bcb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008d5c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008d5c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008cea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008cea`

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
  wil::details *v28; // [rsp+30h] [rbp-58h]

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
0x180008aa0  mov     rax, rsp
0x180008aa3  mov     [rax+10h], edx
0x180008aa6  mov     [rax+8], rcx
0x180008aaa  push    rbp
0x180008aab  push    rsi
0x180008aac  push    rdi
0x180008aad  push    r12
0x180008aaf  push    r13
0x180008ab1  push    r14
0x180008ab3  push    r15
0x180008ab5  sub     rsp, 50h
0x180008ab9  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180008ac1  mov     [rax+18h], rbx
0x180008ac5  mov     r12, r9
0x180008ac8  mov     r13, r8
0x180008acb  mov     r10, rcx
0x180008ace  xor     eax, eax
0x180008ad0  mov     rsi, [rsp+88h+lpOutputString]
0x180008ad8  mov     [rsi], ax
0x180008adb  mov     rax, [rsp+88h+arg_60]
0x180008ae3  mov     byte ptr [rax], 0
0x180008ae6  mov     r14, [rsp+88h+arg_38]
0x180008aee  mov     edi, [r14]
0x180008af1  mov     rbx, [rsp+88h+arg_78]
0x180008af9  mov     [rbx+8], edi
0x180008afc  mov     eax, [r14+4]
0x180008b00  mov     [rbx+0Ch], eax
0x180008b03  xor     ebp, ebp
0x180008b05  mov     r15d, [rsp+88h+arg_30]
0x180008b0d  mov     ecx, r15d
0x180008b10  test    r15d, r15d
0x180008b13  jz      short loc_180008B7B
0x180008b15  sub     ecx, 1
0x180008b18  jz      short loc_180008B72
0x180008b1a  sub     ecx, 1
0x180008b1d  jz      short loc_180008B2D
0x180008b1f  cmp     ecx, 1
0x180008b22  jnz     short loc_180008B84
0x180008b24  mov     ecx, edi; this
0x180008b26  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008b2b  jmp     short loc_180008B82
0x180008b2d  test    edi, edi
0x180008b2f  js      short loc_180008B69
0x180008b31  mov     edi, 8007029Ch
0x180008b36  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x180008b3a  mov     rax, [rsp+88h+arg_28]
0x180008b42  mov     [rsp+88h+var_60], rax; __int64
0x180008b47  mov     rax, [rsp+88h+arg_20]
0x180008b4f  mov     [rsp+88h+var_68], rax; __int64
0x180008b54  mov     rcx, r10; int
0x180008b57  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008b5c  mov     [rbx+8], edi
0x180008b5f  mov     ecx, edi; this
0x180008b61  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008b66  mov     [rbx+0Ch], eax
0x180008b69  mov     ecx, edi; this
0x180008b6b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008b70  jmp     short loc_180008B82
0x180008b72  mov     ecx, edi; this
0x180008b74  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008b79  jmp     short loc_180008B82
0x180008b7b  mov     ecx, edi; this
0x180008b7d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008b82  mov     ebp, eax
0x180008b84  mov     [rbx], r15d
0x180008b87  mov     eax, [rsp+88h+arg_70]
0x180008b8e  mov     [rbx+4], eax
0x180008b91  cmp     dword ptr [r14+8], 1
0x180008b96  jnz     short loc_180008B9E
0x180008b98  or      eax, 8
0x180008b9b  mov     [rbx+4], eax
0x180008b9e  mov     eax, 1
0x180008ba3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008bab  inc     eax
0x180008bad  mov     [rbx+10h], eax
0x180008bb0  mov     rax, [rsp+88h+arg_40]
0x180008bb8  xor     edi, edi
0x180008bba  test    rax, rax
0x180008bbd  jz      short loc_180008BC4
0x180008bbf  cmp     [rax], di
0x180008bc2  jnz     short loc_180008BC7
0x180008bc4  mov     rax, rdi
0x180008bc7  mov     [rbx+18h], rax
0x180008bcb  call    cs:__imp_GetCurrentThreadId
0x180008bd1  mov     [rbx+20h], eax
0x180008bd4  mov     [rbx+38h], r13
0x180008bd8  mov     eax, [rsp+88h+arg_8]
0x180008bdf  mov     [rbx+40h], eax
0x180008be2  mov     [rbx+44h], ebp
0x180008be5  mov     rax, [rsp+88h+arg_20]
0x180008bed  mov     [rbx+28h], rax
0x180008bf1  mov     [rbx+30h], r12
0x180008bf5  mov     rax, [rsp+88h+arg_28]
0x180008bfd  mov     [rbx+88h], rax
0x180008c04  mov     rax, [rsp+88h+arg_0]
0x180008c0c  mov     [rbx+90h], rax
0x180008c13  mov     [rbx+48h], rdi
0x180008c17  xorps   xmm0, xmm0
0x180008c1a  xor     eax, eax
0x180008c1c  movups  xmmword ptr [rbx+68h], xmm0
0x180008c20  mov     [rbx+78h], rax
0x180008c24  movups  xmmword ptr [rbx+50h], xmm0
0x180008c28  mov     [rbx+60h], rax
0x180008c2c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008c33  test    rax, rax
0x180008c36  jz      short loc_180008C3F
0x180008c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c3d  jmp     short loc_180008C42
0x180008c3f  mov     rax, rdi
0x180008c42  mov     [rbx+80h], rax
0x180008c49  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008c50  test    rax, rax
0x180008c53  jz      short loc_180008C5D
0x180008c55  mov     rcx, rbx
0x180008c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c5d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008c64  test    rax, rax
0x180008c67  jz      short loc_180008C7F
0x180008c69  mov     r8d, 400h
0x180008c6f  mov     rdx, [rsp+88h+arg_60]
0x180008c77  mov     rcx, rbx
0x180008c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c7f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008c86  test    rax, rax
0x180008c89  jz      short loc_180008C93
0x180008c8b  mov     rcx, rbx
0x180008c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c93  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008c9a  test    rax, rax
0x180008c9d  jz      short loc_180008CAD
0x180008c9f  test    byte ptr [rbx+4], 2
0x180008ca3  jnz     short loc_180008CAD
0x180008ca5  mov     rcx, rbx
0x180008ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cad  cmp     [rbx+8], edi
0x180008cb0  jl      short loc_180008CCC
0x180008cb2  cmp     r15d, 3
0x180008cb6  jnz     loc_180008D9B
0x180008cbc  mov     ecx, 8000FFFFh; this
0x180008cc1  mov     [rbx+8], ecx
0x180008cc4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008cc9  mov     [rbx+0Ch], eax
0x180008ccc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008cd3  jnz     short loc_180008CF4
0x180008cd5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008cdc  test    rax, rax
0x180008cdf  jz      short loc_180008CEA
0x180008ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ce6  test    al, al
0x180008ce8  jmp     short loc_180008CF2
0x180008cea  call    cs:__imp_IsDebuggerPresent
0x180008cf0  test    eax, eax
0x180008cf2  jz      short loc_180008CFA
0x180008cf4  test    byte ptr [rbx+4], 2
0x180008cf8  jz      short loc_180008D1E
0x180008cfa  mov     rax, cs:g_pfnResultLoggingCallback
0x180008d01  test    rax, rax
0x180008d04  jz      short loc_180008D62
0x180008d06  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008d0d  jnz     short loc_180008D62
0x180008d0f  xor     r8d, r8d
0x180008d12  xor     edx, edx
0x180008d14  mov     rcx, rbx
0x180008d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d1c  jmp     short loc_180008D62
0x180008d1e  mov     ebp, 800h
0x180008d23  mov     rax, cs:g_pfnResultLoggingCallback
0x180008d2a  test    rax, rax
0x180008d2d  jz      short loc_180008D46
0x180008d2f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008d36  jnz     short loc_180008D46
0x180008d38  mov     r8d, ebp
0x180008d3b  mov     rdx, rsi
0x180008d3e  mov     rcx, rbx
0x180008d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d46  cmp     [rsi], di
0x180008d49  jnz     short loc_180008D59
0x180008d4b  mov     r8, rbx; unsigned __int64
0x180008d4e  mov     rdx, rbp; unsigned __int16 *
0x180008d51  mov     rcx, rsi; this
0x180008d54  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008d59  mov     rcx, rsi; lpOutputString
0x180008d5c  call    cs:__imp_OutputDebugStringW
0x180008d62  test    byte ptr [rbx+4], 4
0x180008d66  jnz     short loc_180008D71
0x180008d68  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008d6f  jz      short loc_180008D83
0x180008d71  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008d78  test    rax, rax
0x180008d7b  jz      short loc_180008D83
0x180008d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d82  nop
0x180008d83  mov     rbx, [rsp+88h+arg_10]
0x180008d8b  add     rsp, 50h
0x180008d8f  pop     r15
0x180008d91  pop     r14
0x180008d93  pop     r13
0x180008d95  pop     r12
0x180008d97  pop     rdi
0x180008d98  pop     rsi
0x180008d99  pop     rbp
0x180008d9a  retn
0x180008d9b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
