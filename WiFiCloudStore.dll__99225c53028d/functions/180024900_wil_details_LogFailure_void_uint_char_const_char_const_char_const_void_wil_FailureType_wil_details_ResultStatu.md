# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180024900`
- end: `0x180024bf5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18001fca8`
- `0x1800240b8`
- `0x180024654`
- `0x180024804`

## callees

- `0x18001a6e0`
- `0x18001d5b0`
- `0x180024900`
- `0x180024c00`
- `0x1800290fc`
- `0x18002bd94`
- `0x18002c728`
- `0x18002c744`
- `0x18002c9b8`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024a23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024a23`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180024bb6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180024bb6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180024b44`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180024b44`

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
      wil::details::in1diag3::FailFastImmediate_Unexpected(v24);
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
0x180024900  mov     [rsp+arg_10], rbx
0x180024905  mov     [rsp+arg_8], edx
0x180024909  mov     [rsp+arg_0], rcx
0x18002490e  push    rbp
0x18002490f  push    rsi
0x180024910  push    rdi
0x180024911  push    r12
0x180024913  push    r13
0x180024915  push    r14
0x180024917  push    r15
0x180024919  sub     rsp, 40h
0x18002491d  mov     r12, r9
0x180024920  mov     r13, r8
0x180024923  mov     r10, rcx
0x180024926  xor     eax, eax
0x180024928  mov     rsi, [rsp+78h+lpOutputString]
0x180024930  mov     [rsi], ax
0x180024933  mov     rax, [rsp+78h+arg_60]
0x18002493b  mov     byte ptr [rax], 0
0x18002493e  mov     r14, [rsp+78h+arg_38]
0x180024946  mov     edi, [r14]
0x180024949  mov     rbx, [rsp+78h+arg_78]
0x180024951  mov     [rbx+8], edi
0x180024954  mov     eax, [r14+4]
0x180024958  mov     [rbx+0Ch], eax
0x18002495b  xor     ebp, ebp
0x18002495d  mov     r15d, [rsp+78h+arg_30]
0x180024965  mov     ecx, r15d
0x180024968  test    r15d, r15d
0x18002496b  jz      short loc_1800249D3
0x18002496d  sub     ecx, 1
0x180024970  jz      short loc_1800249CA
0x180024972  sub     ecx, 1
0x180024975  jz      short loc_180024985
0x180024977  cmp     ecx, 1
0x18002497a  jnz     short loc_1800249DC
0x18002497c  mov     ecx, edi; this
0x18002497e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180024983  jmp     short loc_1800249DA
0x180024985  test    edi, edi
0x180024987  js      short loc_1800249C1
0x180024989  mov     edi, 8007029Ch
0x18002498e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180024992  mov     rax, [rsp+78h+arg_28]
0x18002499a  mov     [rsp+78h+var_50], rax; __int64
0x18002499f  mov     rax, [rsp+78h+arg_20]
0x1800249a7  mov     [rsp+78h+var_58], rax; __int64
0x1800249ac  mov     rcx, r10; int
0x1800249af  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800249b4  mov     [rbx+8], edi
0x1800249b7  mov     ecx, edi; this
0x1800249b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800249be  mov     [rbx+0Ch], eax
0x1800249c1  mov     ecx, edi; this
0x1800249c3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800249c8  jmp     short loc_1800249DA
0x1800249ca  mov     ecx, edi; this
0x1800249cc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800249d1  jmp     short loc_1800249DA
0x1800249d3  mov     ecx, edi; this
0x1800249d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800249da  mov     ebp, eax
0x1800249dc  mov     [rbx], r15d
0x1800249df  mov     eax, [rsp+78h+arg_70]
0x1800249e6  mov     [rbx+4], eax
0x1800249e9  cmp     dword ptr [r14+8], 1
0x1800249ee  jnz     short loc_1800249F6
0x1800249f0  or      eax, 8
0x1800249f3  mov     [rbx+4], eax
0x1800249f6  mov     eax, 1
0x1800249fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180024a03  inc     eax
0x180024a05  mov     [rbx+10h], eax
0x180024a08  mov     rax, [rsp+78h+arg_40]
0x180024a10  xor     edi, edi
0x180024a12  test    rax, rax
0x180024a15  jz      short loc_180024A1C
0x180024a17  cmp     [rax], di
0x180024a1a  jnz     short loc_180024A1F
0x180024a1c  mov     rax, rdi
0x180024a1f  mov     [rbx+18h], rax
0x180024a23  call    cs:__imp_GetCurrentThreadId
0x180024a29  mov     [rbx+20h], eax
0x180024a2c  mov     [rbx+38h], r13
0x180024a30  mov     eax, [rsp+78h+arg_8]
0x180024a37  mov     [rbx+40h], eax
0x180024a3a  mov     [rbx+44h], ebp
0x180024a3d  mov     rax, [rsp+78h+arg_20]
0x180024a45  mov     [rbx+28h], rax
0x180024a49  mov     [rbx+30h], r12
0x180024a4d  mov     rax, [rsp+78h+arg_28]
0x180024a55  mov     [rbx+88h], rax
0x180024a5c  mov     rax, [rsp+78h+arg_0]
0x180024a64  mov     [rbx+90h], rax
0x180024a6b  mov     [rbx+48h], rdi
0x180024a6f  xorps   xmm0, xmm0
0x180024a72  xor     eax, eax
0x180024a74  movups  xmmword ptr [rbx+68h], xmm0
0x180024a78  mov     [rbx+78h], rax
0x180024a7c  movups  xmmword ptr [rbx+50h], xmm0
0x180024a80  mov     [rbx+60h], rax
0x180024a84  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180024a8b  test    rax, rax
0x180024a8e  jz      short loc_180024A97
0x180024a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a95  jmp     short loc_180024A9A
0x180024a97  mov     rax, rdi
0x180024a9a  mov     [rbx+80h], rax
0x180024aa1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180024aa8  test    rax, rax
0x180024aab  jz      short loc_180024AB5
0x180024aad  mov     rcx, rbx
0x180024ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ab5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180024abc  test    rax, rax
0x180024abf  jz      short loc_180024AD7
0x180024ac1  mov     r8d, 400h
0x180024ac7  mov     rdx, [rsp+78h+arg_60]
0x180024acf  mov     rcx, rbx
0x180024ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ad7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180024ade  test    rax, rax
0x180024ae1  jz      short loc_180024AEB
0x180024ae3  mov     rcx, rbx
0x180024ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024aeb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180024af2  test    rax, rax
0x180024af5  jz      short loc_180024B05
0x180024af7  test    byte ptr [rbx+4], 2
0x180024afb  jnz     short loc_180024B05
0x180024afd  mov     rcx, rbx
0x180024b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b05  cmp     [rbx+8], edi
0x180024b08  jl      short loc_180024B26
0x180024b0a  cmp     r15d, 3
0x180024b0e  jz      short loc_180024B16
0x180024b10  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x180024b16  mov     ecx, 8000FFFFh; this
0x180024b1b  mov     [rbx+8], ecx
0x180024b1e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180024b23  mov     [rbx+0Ch], eax
0x180024b26  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180024b2d  jnz     short loc_180024B4E
0x180024b2f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180024b36  test    rax, rax
0x180024b39  jz      short loc_180024B44
0x180024b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b40  test    al, al
0x180024b42  jmp     short loc_180024B4C
0x180024b44  call    cs:__imp_IsDebuggerPresent
0x180024b4a  test    eax, eax
0x180024b4c  jz      short loc_180024B54
0x180024b4e  test    byte ptr [rbx+4], 2
0x180024b52  jz      short loc_180024B78
0x180024b54  mov     rax, cs:g_pfnResultLoggingCallback
0x180024b5b  test    rax, rax
0x180024b5e  jz      short loc_180024BBC
0x180024b60  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180024b67  jnz     short loc_180024BBC
0x180024b69  xor     r8d, r8d
0x180024b6c  xor     edx, edx
0x180024b6e  mov     rcx, rbx
0x180024b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b76  jmp     short loc_180024BBC
0x180024b78  mov     ebp, 800h
0x180024b7d  mov     rax, cs:g_pfnResultLoggingCallback
0x180024b84  test    rax, rax
0x180024b87  jz      short loc_180024BA0
0x180024b89  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180024b90  jnz     short loc_180024BA0
0x180024b92  mov     r8d, ebp
0x180024b95  mov     rdx, rsi
0x180024b98  mov     rcx, rbx
0x180024b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ba0  cmp     [rsi], di
0x180024ba3  jnz     short loc_180024BB3
0x180024ba5  mov     r8, rbx; unsigned __int64
0x180024ba8  mov     rdx, rbp; unsigned __int16 *
0x180024bab  mov     rcx, rsi; this
0x180024bae  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180024bb3  mov     rcx, rsi; lpOutputString
0x180024bb6  call    cs:__imp_OutputDebugStringW
0x180024bbc  test    byte ptr [rbx+4], 4
0x180024bc0  jnz     short loc_180024BCB
0x180024bc2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180024bc9  jz      short loc_180024BDD
0x180024bcb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180024bd2  test    rax, rax
0x180024bd5  jz      short loc_180024BDD
0x180024bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bdc  nop
0x180024bdd  mov     rbx, [rsp+78h+arg_10]
0x180024be5  add     rsp, 40h
0x180024be9  pop     r15
0x180024beb  pop     r14
0x180024bed  pop     r13
0x180024bef  pop     r12
0x180024bf1  pop     rdi
0x180024bf2  pop     rsi
0x180024bf3  pop     rbp
0x180024bf4  retn
```
