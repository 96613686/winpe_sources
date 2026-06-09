# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800100f8`
- end: `0x1800103f0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000dff4`
- `0x18000e33c`

## callees

- `0x18000df3c`
- `0x18000f474`
- `0x18000ff34`
- `0x1800100f8`
- `0x180010814`
- `0x180010830`
- `0x180010844`
- `0x180010860`
- `0x1800118e4`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001021b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001021b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800103ac`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800103ac`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001033a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001033a`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x1800100f8  mov     [rsp+arg_10], rbx
0x1800100fd  mov     [rsp+arg_8], edx
0x180010101  mov     [rsp+arg_0], rcx
0x180010106  push    rbp
0x180010107  push    rsi
0x180010108  push    rdi
0x180010109  push    r12
0x18001010b  push    r13
0x18001010d  push    r14
0x18001010f  push    r15
0x180010111  sub     rsp, 40h
0x180010115  mov     r14, [rsp+78h+arg_38]
0x18001011d  xor     eax, eax
0x18001011f  mov     rbx, [rsp+78h+arg_78]
0x180010127  xor     ebp, ebp
0x180010129  mov     r15d, [rsp+78h+arg_30]
0x180010131  mov     r10, rcx
0x180010134  mov     rsi, [rsp+78h+lpOutputString]
0x18001013c  mov     r12, r9
0x18001013f  mov     r13, r8
0x180010142  mov     ecx, r15d
0x180010145  mov     [rsi], ax
0x180010148  mov     rax, [rsp+78h+arg_60]
0x180010150  mov     byte ptr [rax], 0
0x180010153  mov     edi, [r14]
0x180010156  mov     [rbx+8], edi
0x180010159  mov     eax, [r14+4]
0x18001015d  mov     [rbx+0Ch], eax
0x180010160  test    r15d, r15d
0x180010163  jz      short loc_1800101CB
0x180010165  sub     ecx, 1
0x180010168  jz      short loc_1800101C2
0x18001016a  sub     ecx, 1
0x18001016d  jz      short loc_18001017D
0x18001016f  cmp     ecx, 1
0x180010172  jnz     short loc_1800101D4
0x180010174  mov     ecx, edi; this
0x180010176  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001017b  jmp     short loc_1800101D2
0x18001017d  test    edi, edi
0x18001017f  js      short loc_1800101B9
0x180010181  mov     rax, [rsp+78h+arg_28]
0x180010189  mov     edi, 8007029Ch
0x18001018e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180010192  mov     rcx, r10; int
0x180010195  mov     [rsp+78h+var_50], rax; __int64
0x18001019a  mov     rax, [rsp+78h+arg_20]
0x1800101a2  mov     [rsp+78h+var_58], rax; __int64
0x1800101a7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800101ac  mov     ecx, edi; this
0x1800101ae  mov     [rbx+8], edi
0x1800101b1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800101b6  mov     [rbx+0Ch], eax
0x1800101b9  mov     ecx, edi; this
0x1800101bb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800101c0  jmp     short loc_1800101D2
0x1800101c2  mov     ecx, edi; this
0x1800101c4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800101c9  jmp     short loc_1800101D2
0x1800101cb  mov     ecx, edi; this
0x1800101cd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800101d2  mov     ebp, eax
0x1800101d4  mov     eax, [rsp+78h+arg_70]
0x1800101db  mov     [rbx+4], eax
0x1800101de  mov     [rbx], r15d
0x1800101e1  cmp     dword ptr [r14+8], 1
0x1800101e6  jnz     short loc_1800101EE
0x1800101e8  or      eax, 8
0x1800101eb  mov     [rbx+4], eax
0x1800101ee  mov     eax, 1
0x1800101f3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800101fb  inc     eax
0x1800101fd  xor     edi, edi
0x1800101ff  mov     [rbx+10h], eax
0x180010202  mov     rax, [rsp+78h+arg_40]
0x18001020a  test    rax, rax
0x18001020d  jz      short loc_180010214
0x18001020f  cmp     [rax], di
0x180010212  jnz     short loc_180010217
0x180010214  mov     rax, rdi
0x180010217  mov     [rbx+18h], rax
0x18001021b  call    cs:__imp_GetCurrentThreadId
0x180010221  mov     [rbx+38h], r13
0x180010225  xorps   xmm0, xmm0
0x180010228  mov     [rbx+20h], eax
0x18001022b  mov     eax, [rsp+78h+arg_8]
0x180010232  mov     [rbx+40h], eax
0x180010235  mov     rax, [rsp+78h+arg_20]
0x18001023d  mov     [rbx+28h], rax
0x180010241  mov     rax, [rsp+78h+arg_28]
0x180010249  mov     [rbx+88h], rax
0x180010250  mov     rax, [rsp+78h+arg_0]
0x180010258  mov     [rbx+90h], rax
0x18001025f  xor     eax, eax
0x180010261  mov     [rbx+44h], ebp
0x180010264  mov     [rbx+30h], r12
0x180010268  mov     [rbx+48h], rdi
0x18001026c  movups  xmmword ptr [rbx+68h], xmm0
0x180010270  mov     [rbx+78h], rax
0x180010274  movups  xmmword ptr [rbx+50h], xmm0
0x180010278  mov     [rbx+60h], rax
0x18001027c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180010283  test    rax, rax
0x180010286  jz      short loc_18001028F
0x180010288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001028d  jmp     short loc_180010292
0x18001028f  mov     rax, rdi
0x180010292  mov     [rbx+80h], rax
0x180010299  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800102a0  test    rax, rax
0x1800102a3  jz      short loc_1800102AD
0x1800102a5  mov     rcx, rbx
0x1800102a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102ad  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800102b4  test    rax, rax
0x1800102b7  jz      short loc_1800102CF
0x1800102b9  mov     rdx, [rsp+78h+arg_60]
0x1800102c1  mov     r8d, 400h
0x1800102c7  mov     rcx, rbx
0x1800102ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102cf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800102d6  test    rax, rax
0x1800102d9  jz      short loc_1800102E3
0x1800102db  mov     rcx, rbx
0x1800102de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102e3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800102ea  test    rax, rax
0x1800102ed  jz      short loc_1800102FD
0x1800102ef  test    byte ptr [rbx+4], 2
0x1800102f3  jnz     short loc_1800102FD
0x1800102f5  mov     rcx, rbx
0x1800102f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102fd  cmp     [rbx+8], edi
0x180010300  jl      short loc_18001031C
0x180010302  cmp     r15d, 3
0x180010306  jnz     loc_1800103EA
0x18001030c  mov     ecx, 8000FFFFh; this
0x180010311  mov     [rbx+8], ecx
0x180010314  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180010319  mov     [rbx+0Ch], eax
0x18001031c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180010323  jnz     short loc_180010344
0x180010325  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001032c  test    rax, rax
0x18001032f  jz      short loc_18001033A
0x180010331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010336  test    al, al
0x180010338  jmp     short loc_180010342
0x18001033a  call    cs:__imp_IsDebuggerPresent
0x180010340  test    eax, eax
0x180010342  jz      short loc_18001034A
0x180010344  test    byte ptr [rbx+4], 2
0x180010348  jz      short loc_18001036E
0x18001034a  mov     rax, cs:g_pfnResultLoggingCallback
0x180010351  test    rax, rax
0x180010354  jz      short loc_1800103B2
0x180010356  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001035d  jnz     short loc_1800103B2
0x18001035f  xor     r8d, r8d
0x180010362  xor     edx, edx
0x180010364  mov     rcx, rbx
0x180010367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001036c  jmp     short loc_1800103B2
0x18001036e  mov     rax, cs:g_pfnResultLoggingCallback
0x180010375  mov     ebp, 800h
0x18001037a  test    rax, rax
0x18001037d  jz      short loc_180010396
0x18001037f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180010386  jnz     short loc_180010396
0x180010388  mov     r8d, ebp
0x18001038b  mov     rdx, rsi
0x18001038e  mov     rcx, rbx
0x180010391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010396  cmp     [rsi], di
0x180010399  jnz     short loc_1800103A9
0x18001039b  mov     r8, rbx; unsigned __int64
0x18001039e  mov     rdx, rbp; unsigned __int16 *
0x1800103a1  mov     rcx, rsi; this
0x1800103a4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800103a9  mov     rcx, rsi; lpOutputString
0x1800103ac  call    cs:__imp_OutputDebugStringW
0x1800103b2  test    byte ptr [rbx+4], 4
0x1800103b6  jnz     short loc_1800103C1
0x1800103b8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800103bf  jz      short loc_1800103D2
0x1800103c1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800103c8  test    rax, rax
0x1800103cb  jz      short loc_1800103D2
0x1800103cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103d2  mov     rbx, [rsp+78h+arg_10]
0x1800103da  add     rsp, 40h
0x1800103de  pop     r15
0x1800103e0  pop     r14
0x1800103e2  pop     r13
0x1800103e4  pop     r12
0x1800103e6  pop     rdi
0x1800103e7  pop     rsi
0x1800103e8  pop     rbp
0x1800103e9  retn
0x1800103ea  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
