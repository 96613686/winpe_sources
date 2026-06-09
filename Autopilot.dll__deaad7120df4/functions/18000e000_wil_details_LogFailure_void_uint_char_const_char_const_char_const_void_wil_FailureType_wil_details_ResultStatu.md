# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000e000`
- end: `0x18000e30c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000a4e0`

## callees

- `0x180009ec4`
- `0x18000d284`
- `0x18000dbf0`
- `0x18000e000`
- `0x18000f190`
- `0x18000f1b0`
- `0x18000f2f8`
- `0x18000f318`
- `0x180012210`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e123`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e123`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e248`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e248`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e2c0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e2c0`

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
0x18000e000  mov     [rsp+arg_10], rbx
0x18000e005  mov     [rsp+arg_8], edx
0x18000e009  mov     [rsp+arg_0], rcx
0x18000e00e  push    rbp
0x18000e00f  push    rsi
0x18000e010  push    rdi
0x18000e011  push    r12
0x18000e013  push    r13
0x18000e015  push    r14
0x18000e017  push    r15
0x18000e019  sub     rsp, 40h
0x18000e01d  mov     r12, r9
0x18000e020  mov     r13, r8
0x18000e023  mov     r10, rcx
0x18000e026  xor     eax, eax
0x18000e028  mov     rsi, [rsp+78h+lpOutputString]
0x18000e030  mov     [rsi], ax
0x18000e033  mov     rax, [rsp+78h+arg_60]
0x18000e03b  mov     byte ptr [rax], 0
0x18000e03e  mov     r14, [rsp+78h+arg_38]
0x18000e046  mov     edi, [r14]
0x18000e049  mov     rbx, [rsp+78h+arg_78]
0x18000e051  mov     [rbx+8], edi
0x18000e054  mov     eax, [r14+4]
0x18000e058  mov     [rbx+0Ch], eax
0x18000e05b  xor     ebp, ebp
0x18000e05d  mov     r15d, [rsp+78h+arg_30]
0x18000e065  mov     ecx, r15d
0x18000e068  test    r15d, r15d
0x18000e06b  jz      short loc_18000E0D3
0x18000e06d  sub     ecx, 1
0x18000e070  jz      short loc_18000E0CA
0x18000e072  sub     ecx, 1
0x18000e075  jz      short loc_18000E085
0x18000e077  cmp     ecx, 1
0x18000e07a  jnz     short loc_18000E0DC
0x18000e07c  mov     ecx, edi; this
0x18000e07e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000e083  jmp     short loc_18000E0DA
0x18000e085  test    edi, edi
0x18000e087  js      short loc_18000E0C1
0x18000e089  mov     edi, 8007029Ch
0x18000e08e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000e092  mov     rax, [rsp+78h+arg_28]
0x18000e09a  mov     [rsp+78h+var_50], rax; __int64
0x18000e09f  mov     rax, [rsp+78h+arg_20]
0x18000e0a7  mov     [rsp+78h+var_58], rax; __int64
0x18000e0ac  mov     rcx, r10; int
0x18000e0af  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000e0b4  mov     [rbx+8], edi
0x18000e0b7  mov     ecx, edi; this
0x18000e0b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e0be  mov     [rbx+0Ch], eax
0x18000e0c1  mov     ecx, edi; this
0x18000e0c3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000e0c8  jmp     short loc_18000E0DA
0x18000e0ca  mov     ecx, edi; this
0x18000e0cc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000e0d1  jmp     short loc_18000E0DA
0x18000e0d3  mov     ecx, edi; this
0x18000e0d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000e0da  mov     ebp, eax
0x18000e0dc  mov     [rbx], r15d
0x18000e0df  mov     eax, [rsp+78h+arg_70]
0x18000e0e6  mov     [rbx+4], eax
0x18000e0e9  cmp     dword ptr [r14+8], 1
0x18000e0ee  jnz     short loc_18000E0F6
0x18000e0f0  or      eax, 8
0x18000e0f3  mov     [rbx+4], eax
0x18000e0f6  mov     eax, 1
0x18000e0fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e103  inc     eax
0x18000e105  mov     [rbx+10h], eax
0x18000e108  mov     rax, [rsp+78h+arg_40]
0x18000e110  xor     edi, edi
0x18000e112  test    rax, rax
0x18000e115  jz      short loc_18000E11C
0x18000e117  cmp     [rax], di
0x18000e11a  jnz     short loc_18000E11F
0x18000e11c  mov     rax, rdi
0x18000e11f  mov     [rbx+18h], rax
0x18000e123  call    cs:__imp_GetCurrentThreadId
0x18000e12a  nop     dword ptr [rax+rax+00h]
0x18000e12f  mov     [rbx+20h], eax
0x18000e132  mov     [rbx+38h], r13
0x18000e136  mov     eax, [rsp+78h+arg_8]
0x18000e13d  mov     [rbx+40h], eax
0x18000e140  mov     [rbx+44h], ebp
0x18000e143  mov     rax, [rsp+78h+arg_20]
0x18000e14b  mov     [rbx+28h], rax
0x18000e14f  mov     [rbx+30h], r12
0x18000e153  mov     rax, [rsp+78h+arg_28]
0x18000e15b  mov     [rbx+88h], rax
0x18000e162  mov     rax, [rsp+78h+arg_0]
0x18000e16a  mov     [rbx+90h], rax
0x18000e171  mov     [rbx+48h], rdi
0x18000e175  xorps   xmm0, xmm0
0x18000e178  xor     eax, eax
0x18000e17a  movups  xmmword ptr [rbx+68h], xmm0
0x18000e17e  mov     [rbx+78h], rax
0x18000e182  movups  xmmword ptr [rbx+50h], xmm0
0x18000e186  mov     [rbx+60h], rax
0x18000e18a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e191  test    rax, rax
0x18000e194  jz      short loc_18000E19D
0x18000e196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e19b  jmp     short loc_18000E1A0
0x18000e19d  mov     rax, rdi
0x18000e1a0  mov     [rbx+80h], rax
0x18000e1a7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e1ae  test    rax, rax
0x18000e1b1  jz      short loc_18000E1BB
0x18000e1b3  mov     rcx, rbx
0x18000e1b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1bb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e1c2  test    rax, rax
0x18000e1c5  jz      short loc_18000E1DD
0x18000e1c7  mov     r8d, 400h
0x18000e1cd  mov     rdx, [rsp+78h+arg_60]
0x18000e1d5  mov     rcx, rbx
0x18000e1d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1dd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e1e4  test    rax, rax
0x18000e1e7  jz      short loc_18000E1F1
0x18000e1e9  mov     rcx, rbx
0x18000e1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1f1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e1f8  test    rax, rax
0x18000e1fb  jz      short loc_18000E20B
0x18000e1fd  test    byte ptr [rbx+4], 2
0x18000e201  jnz     short loc_18000E20B
0x18000e203  mov     rcx, rbx
0x18000e206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e20b  cmp     [rbx+8], edi
0x18000e20e  jl      short loc_18000E22A
0x18000e210  cmp     r15d, 3
0x18000e214  jnz     loc_18000E306
0x18000e21a  mov     ecx, 8000FFFFh; this
0x18000e21f  mov     [rbx+8], ecx
0x18000e222  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e227  mov     [rbx+0Ch], eax
0x18000e22a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000e231  jnz     short loc_18000E258
0x18000e233  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e23a  test    rax, rax
0x18000e23d  jz      short loc_18000E248
0x18000e23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e244  test    al, al
0x18000e246  jmp     short loc_18000E256
0x18000e248  call    cs:__imp_IsDebuggerPresent
0x18000e24f  nop     dword ptr [rax+rax+00h]
0x18000e254  test    eax, eax
0x18000e256  jz      short loc_18000E25E
0x18000e258  test    byte ptr [rbx+4], 2
0x18000e25c  jz      short loc_18000E282
0x18000e25e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e265  test    rax, rax
0x18000e268  jz      short loc_18000E2CC
0x18000e26a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e271  jnz     short loc_18000E2CC
0x18000e273  xor     r8d, r8d
0x18000e276  xor     edx, edx
0x18000e278  mov     rcx, rbx
0x18000e27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e280  jmp     short loc_18000E2CC
0x18000e282  mov     ebp, 800h
0x18000e287  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e28e  test    rax, rax
0x18000e291  jz      short loc_18000E2AA
0x18000e293  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e29a  jnz     short loc_18000E2AA
0x18000e29c  mov     r8d, ebp
0x18000e29f  mov     rdx, rsi
0x18000e2a2  mov     rcx, rbx
0x18000e2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2aa  cmp     [rsi], di
0x18000e2ad  jnz     short loc_18000E2BD
0x18000e2af  mov     r8, rbx; unsigned __int64
0x18000e2b2  mov     rdx, rbp; unsigned __int16 *
0x18000e2b5  mov     rcx, rsi; this
0x18000e2b8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e2bd  mov     rcx, rsi; lpOutputString
0x18000e2c0  call    cs:__imp_OutputDebugStringW
0x18000e2c7  nop     dword ptr [rax+rax+00h]
0x18000e2cc  test    byte ptr [rbx+4], 4
0x18000e2d0  jnz     short loc_18000E2DB
0x18000e2d2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000e2d9  jz      short loc_18000E2ED
0x18000e2db  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e2e2  test    rax, rax
0x18000e2e5  jz      short loc_18000E2ED
0x18000e2e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2ec  nop
0x18000e2ed  mov     rbx, [rsp+78h+arg_10]
0x18000e2f5  add     rsp, 40h
0x18000e2f9  pop     r15
0x18000e2fb  pop     r14
0x18000e2fd  pop     r13
0x18000e2ff  pop     r12
0x18000e301  pop     rdi
0x18000e302  pop     rsi
0x18000e303  pop     rbp
0x18000e304  retn
0x18000e306  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
