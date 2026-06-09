# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005794`
- end: `0x180005a8c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002df8`

## callees

- `0x180002834`
- `0x180004c84`
- `0x1800054ac`
- `0x180005794`
- `0x1800063e0`
- `0x180006400`
- `0x180006528`
- `0x180006544`
- `0x1800082c4`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800058b7`
- `KERNEL32!GetCurrentThreadId` at `0x1800058b7`
- `KERNEL32!OutputDebugStringW` at `0x180005a48`
- `KERNEL32!OutputDebugStringW` at `0x180005a48`
- `KERNEL32!IsDebuggerPresent` at `0x1800059d6`
- `KERNEL32!IsDebuggerPresent` at `0x1800059d6`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180005794  mov     [rsp+arg_10], rbx
0x180005799  mov     [rsp+arg_8], edx
0x18000579d  mov     [rsp+arg_0], rcx
0x1800057a2  push    rbp
0x1800057a3  push    rsi
0x1800057a4  push    rdi
0x1800057a5  push    r12
0x1800057a7  push    r13
0x1800057a9  push    r14
0x1800057ab  push    r15
0x1800057ad  sub     rsp, 40h
0x1800057b1  mov     r14, [rsp+78h+arg_38]
0x1800057b9  xor     eax, eax
0x1800057bb  mov     rbx, [rsp+78h+arg_78]
0x1800057c3  xor     ebp, ebp
0x1800057c5  mov     r15d, [rsp+78h+arg_30]
0x1800057cd  mov     r10, rcx
0x1800057d0  mov     rsi, [rsp+78h+lpOutputString]
0x1800057d8  mov     r12, r9
0x1800057db  mov     r13, r8
0x1800057de  mov     ecx, r15d
0x1800057e1  mov     [rsi], ax
0x1800057e4  mov     rax, [rsp+78h+arg_60]
0x1800057ec  mov     byte ptr [rax], 0
0x1800057ef  mov     edi, [r14]
0x1800057f2  mov     [rbx+8], edi
0x1800057f5  mov     eax, [r14+4]
0x1800057f9  mov     [rbx+0Ch], eax
0x1800057fc  test    r15d, r15d
0x1800057ff  jz      short loc_180005867
0x180005801  sub     ecx, 1
0x180005804  jz      short loc_18000585E
0x180005806  sub     ecx, 1
0x180005809  jz      short loc_180005819
0x18000580b  cmp     ecx, 1
0x18000580e  jnz     short loc_180005870
0x180005810  mov     ecx, edi; this
0x180005812  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005817  jmp     short loc_18000586E
0x180005819  test    edi, edi
0x18000581b  js      short loc_180005855
0x18000581d  mov     rax, [rsp+78h+arg_28]
0x180005825  mov     edi, 8007029Ch
0x18000582a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000582e  mov     rcx, r10; int
0x180005831  mov     [rsp+78h+var_50], rax; __int64
0x180005836  mov     rax, [rsp+78h+arg_20]
0x18000583e  mov     [rsp+78h+var_58], rax; __int64
0x180005843  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005848  mov     ecx, edi; this
0x18000584a  mov     [rbx+8], edi
0x18000584d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005852  mov     [rbx+0Ch], eax
0x180005855  mov     ecx, edi; this
0x180005857  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000585c  jmp     short loc_18000586E
0x18000585e  mov     ecx, edi; this
0x180005860  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005865  jmp     short loc_18000586E
0x180005867  mov     ecx, edi; this
0x180005869  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000586e  mov     ebp, eax
0x180005870  mov     eax, [rsp+78h+arg_70]
0x180005877  mov     [rbx+4], eax
0x18000587a  mov     [rbx], r15d
0x18000587d  cmp     dword ptr [r14+8], 1
0x180005882  jnz     short loc_18000588A
0x180005884  or      eax, 8
0x180005887  mov     [rbx+4], eax
0x18000588a  mov     eax, 1
0x18000588f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005897  inc     eax
0x180005899  xor     edi, edi
0x18000589b  mov     [rbx+10h], eax
0x18000589e  mov     rax, [rsp+78h+arg_40]
0x1800058a6  test    rax, rax
0x1800058a9  jz      short loc_1800058B0
0x1800058ab  cmp     [rax], di
0x1800058ae  jnz     short loc_1800058B3
0x1800058b0  mov     rax, rdi
0x1800058b3  mov     [rbx+18h], rax
0x1800058b7  call    cs:__imp_GetCurrentThreadId
0x1800058bd  mov     [rbx+38h], r13
0x1800058c1  xorps   xmm0, xmm0
0x1800058c4  mov     [rbx+20h], eax
0x1800058c7  mov     eax, [rsp+78h+arg_8]
0x1800058ce  mov     [rbx+40h], eax
0x1800058d1  mov     rax, [rsp+78h+arg_20]
0x1800058d9  mov     [rbx+28h], rax
0x1800058dd  mov     rax, [rsp+78h+arg_28]
0x1800058e5  mov     [rbx+88h], rax
0x1800058ec  mov     rax, [rsp+78h+arg_0]
0x1800058f4  mov     [rbx+90h], rax
0x1800058fb  xor     eax, eax
0x1800058fd  mov     [rbx+44h], ebp
0x180005900  mov     [rbx+30h], r12
0x180005904  mov     [rbx+48h], rdi
0x180005908  movups  xmmword ptr [rbx+68h], xmm0
0x18000590c  mov     [rbx+78h], rax
0x180005910  movups  xmmword ptr [rbx+50h], xmm0
0x180005914  mov     [rbx+60h], rax
0x180005918  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000591f  test    rax, rax
0x180005922  jz      short loc_18000592B
0x180005924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005929  jmp     short loc_18000592E
0x18000592b  mov     rax, rdi
0x18000592e  mov     [rbx+80h], rax
0x180005935  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000593c  test    rax, rax
0x18000593f  jz      short loc_180005949
0x180005941  mov     rcx, rbx
0x180005944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005949  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005950  test    rax, rax
0x180005953  jz      short loc_18000596B
0x180005955  mov     rdx, [rsp+78h+arg_60]
0x18000595d  mov     r8d, 400h
0x180005963  mov     rcx, rbx
0x180005966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000596b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005972  test    rax, rax
0x180005975  jz      short loc_18000597F
0x180005977  mov     rcx, rbx
0x18000597a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000597f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005986  test    rax, rax
0x180005989  jz      short loc_180005999
0x18000598b  test    byte ptr [rbx+4], 2
0x18000598f  jnz     short loc_180005999
0x180005991  mov     rcx, rbx
0x180005994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005999  cmp     [rbx+8], edi
0x18000599c  jl      short loc_1800059B8
0x18000599e  cmp     r15d, 3
0x1800059a2  jnz     loc_180005A86
0x1800059a8  mov     ecx, 8000FFFFh; this
0x1800059ad  mov     [rbx+8], ecx
0x1800059b0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800059b5  mov     [rbx+0Ch], eax
0x1800059b8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800059bf  jnz     short loc_1800059E0
0x1800059c1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800059c8  test    rax, rax
0x1800059cb  jz      short loc_1800059D6
0x1800059cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059d2  test    al, al
0x1800059d4  jmp     short loc_1800059DE
0x1800059d6  call    cs:__imp_IsDebuggerPresent
0x1800059dc  test    eax, eax
0x1800059de  jz      short loc_1800059E6
0x1800059e0  test    byte ptr [rbx+4], 2
0x1800059e4  jz      short loc_180005A0A
0x1800059e6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800059ed  test    rax, rax
0x1800059f0  jz      short loc_180005A4E
0x1800059f2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800059f9  jnz     short loc_180005A4E
0x1800059fb  xor     r8d, r8d
0x1800059fe  xor     edx, edx
0x180005a00  mov     rcx, rbx
0x180005a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a08  jmp     short loc_180005A4E
0x180005a0a  mov     rax, cs:g_pfnResultLoggingCallback
0x180005a11  mov     ebp, 800h
0x180005a16  test    rax, rax
0x180005a19  jz      short loc_180005A32
0x180005a1b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005a22  jnz     short loc_180005A32
0x180005a24  mov     r8d, ebp
0x180005a27  mov     rdx, rsi
0x180005a2a  mov     rcx, rbx
0x180005a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a32  cmp     [rsi], di
0x180005a35  jnz     short loc_180005A45
0x180005a37  mov     r8, rbx; unsigned __int64
0x180005a3a  mov     rdx, rbp; unsigned __int16 *
0x180005a3d  mov     rcx, rsi; this
0x180005a40  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005a45  mov     rcx, rsi; lpOutputString
0x180005a48  call    cs:__imp_OutputDebugStringW
0x180005a4e  test    byte ptr [rbx+4], 4
0x180005a52  jnz     short loc_180005A5D
0x180005a54  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005a5b  jz      short loc_180005A6E
0x180005a5d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005a64  test    rax, rax
0x180005a67  jz      short loc_180005A6E
0x180005a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a6e  mov     rbx, [rsp+78h+arg_10]
0x180005a76  add     rsp, 40h
0x180005a7a  pop     r15
0x180005a7c  pop     r14
0x180005a7e  pop     r13
0x180005a80  pop     r12
0x180005a82  pop     rdi
0x180005a83  pop     rsi
0x180005a84  pop     rbp
0x180005a85  retn
0x180005a86  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
