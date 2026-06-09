# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000d1e8`
- end: `0x18000d4e5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `765`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000a8e4`
- `0x18000ac50`
- `0x18001709c`

## callees

- `0x18000a81c`
- `0x18000c584`
- `0x18000cde0`
- `0x18000d1e8`
- `0x18000e08c`
- `0x18000e0b0`
- `0x18000e234`
- `0x18000e250`
- `0x180010010`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d30f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d30f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d42e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d42e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d4a0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d4a0`

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
0x18000d1e8  mov     [rsp+arg_10], rbx
0x18000d1ed  mov     [rsp+arg_8], edx
0x18000d1f1  mov     [rsp+arg_0], rcx
0x18000d1f6  push    rbp
0x18000d1f7  push    rsi
0x18000d1f8  push    rdi
0x18000d1f9  push    r12
0x18000d1fb  push    r13
0x18000d1fd  push    r14
0x18000d1ff  push    r15
0x18000d201  sub     rsp, 40h
0x18000d205  mov     r12, r9
0x18000d208  mov     r13, r8
0x18000d20b  mov     r10, rcx
0x18000d20e  xor     eax, eax
0x18000d210  mov     rsi, [rsp+78h+lpOutputString]
0x18000d218  mov     [rsi], ax
0x18000d21b  mov     rax, [rsp+78h+arg_60]
0x18000d223  mov     byte ptr [rax], 0
0x18000d226  mov     r14, [rsp+78h+arg_38]
0x18000d22e  mov     edi, [r14]
0x18000d231  mov     rbx, [rsp+78h+arg_78]
0x18000d239  mov     [rbx+8], edi
0x18000d23c  mov     eax, [r14+4]
0x18000d240  mov     [rbx+0Ch], eax
0x18000d243  xor     ebp, ebp
0x18000d245  mov     r15d, [rsp+78h+arg_30]
0x18000d24d  mov     ecx, r15d
0x18000d250  test    r15d, r15d
0x18000d253  jz      short loc_18000D2BF
0x18000d255  sub     ecx, 1
0x18000d258  jz      short loc_18000D2B6
0x18000d25a  sub     ecx, 1
0x18000d25d  jz      short loc_18000D26D
0x18000d25f  cmp     ecx, 1
0x18000d262  jnz     short loc_18000D2C8
0x18000d264  mov     ecx, edi; this
0x18000d266  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000d26b  jmp     short loc_18000D2C6
0x18000d26d  test    edi, edi
0x18000d26f  js      short loc_18000D2AD
0x18000d271  mov     [rsp+78h+var_40], ebp
0x18000d275  mov     edi, 8007029Ch
0x18000d27a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000d27e  mov     rax, [rsp+78h+arg_28]
0x18000d286  mov     [rsp+78h+var_50], rax; __int64
0x18000d28b  mov     rax, [rsp+78h+arg_20]
0x18000d293  mov     [rsp+78h+var_58], rax; __int64
0x18000d298  mov     rcx, r10; int
0x18000d29b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000d2a0  mov     [rbx+8], edi
0x18000d2a3  mov     ecx, edi; this
0x18000d2a5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d2aa  mov     [rbx+0Ch], eax
0x18000d2ad  mov     ecx, edi; this
0x18000d2af  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000d2b4  jmp     short loc_18000D2C6
0x18000d2b6  mov     ecx, edi; this
0x18000d2b8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000d2bd  jmp     short loc_18000D2C6
0x18000d2bf  mov     ecx, edi; this
0x18000d2c1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000d2c6  mov     ebp, eax
0x18000d2c8  mov     [rbx], r15d
0x18000d2cb  mov     eax, [rsp+78h+arg_70]
0x18000d2d2  mov     [rbx+4], eax
0x18000d2d5  cmp     dword ptr [r14+8], 1
0x18000d2da  jnz     short loc_18000D2E2
0x18000d2dc  or      eax, 8
0x18000d2df  mov     [rbx+4], eax
0x18000d2e2  mov     eax, 1
0x18000d2e7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000d2ef  inc     eax
0x18000d2f1  mov     [rbx+10h], eax
0x18000d2f4  mov     rax, [rsp+78h+arg_40]
0x18000d2fc  xor     edi, edi
0x18000d2fe  test    rax, rax
0x18000d301  jz      short loc_18000D308
0x18000d303  cmp     [rax], di
0x18000d306  jnz     short loc_18000D30B
0x18000d308  mov     rax, rdi
0x18000d30b  mov     [rbx+18h], rax
0x18000d30f  call    cs:__imp_GetCurrentThreadId
0x18000d315  mov     [rbx+20h], eax
0x18000d318  mov     [rbx+38h], r13
0x18000d31c  mov     eax, [rsp+78h+arg_8]
0x18000d323  mov     [rbx+40h], eax
0x18000d326  mov     [rbx+44h], ebp
0x18000d329  mov     rax, [rsp+78h+arg_20]
0x18000d331  mov     [rbx+28h], rax
0x18000d335  mov     [rbx+30h], r12
0x18000d339  mov     rax, [rsp+78h+arg_28]
0x18000d341  mov     [rbx+88h], rax
0x18000d348  mov     rax, [rsp+78h+arg_0]
0x18000d350  mov     [rbx+90h], rax
0x18000d357  mov     [rbx+48h], rdi
0x18000d35b  xorps   xmm0, xmm0
0x18000d35e  xor     eax, eax
0x18000d360  movups  xmmword ptr [rbx+68h], xmm0
0x18000d364  mov     [rbx+78h], rax
0x18000d368  movups  xmmword ptr [rbx+50h], xmm0
0x18000d36c  mov     [rbx+60h], rax
0x18000d370  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000d377  test    rax, rax
0x18000d37a  jz      short loc_18000D383
0x18000d37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d381  jmp     short loc_18000D386
0x18000d383  mov     rax, rdi
0x18000d386  mov     [rbx+80h], rax
0x18000d38d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000d394  test    rax, rax
0x18000d397  jz      short loc_18000D3A1
0x18000d399  mov     rcx, rbx
0x18000d39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000d3a8  test    rax, rax
0x18000d3ab  jz      short loc_18000D3C3
0x18000d3ad  mov     r8d, 400h
0x18000d3b3  mov     rdx, [rsp+78h+arg_60]
0x18000d3bb  mov     rcx, rbx
0x18000d3be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3c3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d3ca  test    rax, rax
0x18000d3cd  jz      short loc_18000D3D7
0x18000d3cf  mov     rcx, rbx
0x18000d3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3d7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d3de  test    rax, rax
0x18000d3e1  jz      short loc_18000D3F1
0x18000d3e3  test    byte ptr [rbx+4], 2
0x18000d3e7  jnz     short loc_18000D3F1
0x18000d3e9  mov     rcx, rbx
0x18000d3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3f1  cmp     [rbx+8], edi
0x18000d3f4  jl      short loc_18000D410
0x18000d3f6  cmp     r15d, 3
0x18000d3fa  jnz     loc_18000D4DF
0x18000d400  mov     ecx, 8000FFFFh; this
0x18000d405  mov     [rbx+8], ecx
0x18000d408  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d40d  mov     [rbx+0Ch], eax
0x18000d410  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000d417  jnz     short loc_18000D438
0x18000d419  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000d420  test    rax, rax
0x18000d423  jz      short loc_18000D42E
0x18000d425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d42a  test    al, al
0x18000d42c  jmp     short loc_18000D436
0x18000d42e  call    cs:__imp_IsDebuggerPresent
0x18000d434  test    eax, eax
0x18000d436  jz      short loc_18000D43E
0x18000d438  test    byte ptr [rbx+4], 2
0x18000d43c  jz      short loc_18000D462
0x18000d43e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d445  test    rax, rax
0x18000d448  jz      short loc_18000D4A6
0x18000d44a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000d451  jnz     short loc_18000D4A6
0x18000d453  xor     r8d, r8d
0x18000d456  xor     edx, edx
0x18000d458  mov     rcx, rbx
0x18000d45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d460  jmp     short loc_18000D4A6
0x18000d462  mov     ebp, 800h
0x18000d467  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d46e  test    rax, rax
0x18000d471  jz      short loc_18000D48A
0x18000d473  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000d47a  jnz     short loc_18000D48A
0x18000d47c  mov     r8d, ebp
0x18000d47f  mov     rdx, rsi
0x18000d482  mov     rcx, rbx
0x18000d485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d48a  cmp     [rsi], di
0x18000d48d  jnz     short loc_18000D49D
0x18000d48f  mov     r8, rbx; unsigned __int64
0x18000d492  mov     rdx, rbp; unsigned __int16 *
0x18000d495  mov     rcx, rsi; this
0x18000d498  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000d49d  mov     rcx, rsi; lpOutputString
0x18000d4a0  call    cs:__imp_OutputDebugStringW
0x18000d4a6  test    byte ptr [rbx+4], 4
0x18000d4aa  jnz     short loc_18000D4B5
0x18000d4ac  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000d4b3  jz      short loc_18000D4C7
0x18000d4b5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d4bc  test    rax, rax
0x18000d4bf  jz      short loc_18000D4C7
0x18000d4c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4c6  nop
0x18000d4c7  mov     rbx, [rsp+78h+arg_10]
0x18000d4cf  add     rsp, 40h
0x18000d4d3  pop     r15
0x18000d4d5  pop     r14
0x18000d4d7  pop     r13
0x18000d4d9  pop     r12
0x18000d4db  pop     rdi
0x18000d4dc  pop     rsi
0x18000d4dd  pop     rbp
0x18000d4de  retn
0x18000d4df  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
