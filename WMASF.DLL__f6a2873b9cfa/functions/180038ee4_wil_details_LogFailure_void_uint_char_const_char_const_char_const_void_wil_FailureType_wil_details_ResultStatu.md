# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180038ee4`
- end: `0x1800391d8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180032f34`
- `0x180032fe8`
- `0x1800330dc`

## callees

- `0x180032e84`
- `0x1800376b4`
- `0x18003831c`
- `0x180038ee4`
- `0x180039854`
- `0x180039870`
- `0x1800399dc`
- `0x1800399f8`
- `0x18003be5c`
- `0x180040010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18003919a`
- `KERNEL32!OutputDebugStringW` at `0x18003919a`
- `KERNEL32!IsDebuggerPresent` at `0x180039128`
- `KERNEL32!IsDebuggerPresent` at `0x180039128`
- `KERNEL32!GetCurrentThreadId` at `0x180039007`
- `KERNEL32!GetCurrentThreadId` at `0x180039007`

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
0x180038ee4  mov     [rsp+arg_10], rbx
0x180038ee9  mov     [rsp+arg_8], edx
0x180038eed  mov     [rsp+arg_0], rcx
0x180038ef2  push    rbp
0x180038ef3  push    rsi
0x180038ef4  push    rdi
0x180038ef5  push    r12
0x180038ef7  push    r13
0x180038ef9  push    r14
0x180038efb  push    r15
0x180038efd  sub     rsp, 40h
0x180038f01  mov     r14, [rsp+78h+arg_38]
0x180038f09  xor     eax, eax
0x180038f0b  mov     rbx, [rsp+78h+arg_78]
0x180038f13  xor     ebp, ebp
0x180038f15  mov     r15d, [rsp+78h+arg_30]
0x180038f1d  mov     r10, rcx
0x180038f20  mov     rsi, [rsp+78h+lpOutputString]
0x180038f28  mov     r12, r9
0x180038f2b  mov     r13, r8
0x180038f2e  mov     ecx, r15d
0x180038f31  mov     [rsi], ax
0x180038f34  mov     rax, [rsp+78h+arg_60]
0x180038f3c  mov     byte ptr [rax], 0
0x180038f3f  mov     edi, [r14]
0x180038f42  mov     [rbx+8], edi
0x180038f45  mov     eax, [r14+4]
0x180038f49  mov     [rbx+0Ch], eax
0x180038f4c  test    r15d, r15d
0x180038f4f  jz      short loc_180038FB7
0x180038f51  sub     ecx, 1
0x180038f54  jz      short loc_180038FAE
0x180038f56  sub     ecx, 1
0x180038f59  jz      short loc_180038F69
0x180038f5b  cmp     ecx, 1
0x180038f5e  jnz     short loc_180038FC0
0x180038f60  mov     ecx, edi; this
0x180038f62  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180038f67  jmp     short loc_180038FBE
0x180038f69  test    edi, edi
0x180038f6b  js      short loc_180038FA5
0x180038f6d  mov     rax, [rsp+78h+arg_28]
0x180038f75  mov     edi, 8007029Ch
0x180038f7a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180038f7e  mov     rcx, r10; int
0x180038f81  mov     [rsp+78h+var_50], rax; __int64
0x180038f86  mov     rax, [rsp+78h+arg_20]
0x180038f8e  mov     [rsp+78h+var_58], rax; __int64
0x180038f93  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180038f98  mov     ecx, edi; this
0x180038f9a  mov     [rbx+8], edi
0x180038f9d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180038fa2  mov     [rbx+0Ch], eax
0x180038fa5  mov     ecx, edi; this
0x180038fa7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180038fac  jmp     short loc_180038FBE
0x180038fae  mov     ecx, edi; this
0x180038fb0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180038fb5  jmp     short loc_180038FBE
0x180038fb7  mov     ecx, edi; this
0x180038fb9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180038fbe  mov     ebp, eax
0x180038fc0  mov     eax, [rsp+78h+arg_70]
0x180038fc7  mov     [rbx+4], eax
0x180038fca  mov     [rbx], r15d
0x180038fcd  cmp     dword ptr [r14+8], 1
0x180038fd2  jnz     short loc_180038FDA
0x180038fd4  or      eax, 8
0x180038fd7  mov     [rbx+4], eax
0x180038fda  mov     eax, 1
0x180038fdf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180038fe7  inc     eax
0x180038fe9  xor     edi, edi
0x180038feb  mov     [rbx+10h], eax
0x180038fee  mov     rax, [rsp+78h+arg_40]
0x180038ff6  test    rax, rax
0x180038ff9  jz      short loc_180039000
0x180038ffb  cmp     [rax], di
0x180038ffe  jnz     short loc_180039003
0x180039000  mov     rax, rdi
0x180039003  mov     [rbx+18h], rax
0x180039007  call    cs:__imp_GetCurrentThreadId
0x18003900d  mov     [rbx+38h], r13
0x180039011  xorps   xmm0, xmm0
0x180039014  mov     [rbx+20h], eax
0x180039017  mov     eax, [rsp+78h+arg_8]
0x18003901e  mov     [rbx+40h], eax
0x180039021  mov     rax, [rsp+78h+arg_20]
0x180039029  mov     [rbx+28h], rax
0x18003902d  mov     rax, [rsp+78h+arg_28]
0x180039035  mov     [rbx+88h], rax
0x18003903c  mov     rax, [rsp+78h+arg_0]
0x180039044  mov     [rbx+90h], rax
0x18003904b  xor     eax, eax
0x18003904d  mov     [rbx+44h], ebp
0x180039050  mov     [rbx+30h], r12
0x180039054  mov     [rbx+48h], rdi
0x180039058  movups  xmmword ptr [rbx+68h], xmm0
0x18003905c  mov     [rbx+78h], rax
0x180039060  movups  xmmword ptr [rbx+50h], xmm0
0x180039064  mov     [rbx+60h], rax
0x180039068  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003906f  test    rax, rax
0x180039072  jz      short loc_18003907B
0x180039074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039079  jmp     short loc_18003907E
0x18003907b  mov     rax, rdi
0x18003907e  mov     [rbx+80h], rax
0x180039085  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003908c  test    rax, rax
0x18003908f  jz      short loc_180039099
0x180039091  mov     rcx, rbx
0x180039094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039099  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800390a0  test    rax, rax
0x1800390a3  jz      short loc_1800390BB
0x1800390a5  mov     rdx, [rsp+78h+arg_60]
0x1800390ad  mov     r8d, 400h
0x1800390b3  mov     rcx, rbx
0x1800390b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390bb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800390c2  test    rax, rax
0x1800390c5  jz      short loc_1800390CF
0x1800390c7  mov     rcx, rbx
0x1800390ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390cf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800390d6  test    rax, rax
0x1800390d9  jz      short loc_1800390E9
0x1800390db  test    byte ptr [rbx+4], 2
0x1800390df  jnz     short loc_1800390E9
0x1800390e1  mov     rcx, rbx
0x1800390e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390e9  cmp     [rbx+8], edi
0x1800390ec  jl      short loc_18003910A
0x1800390ee  cmp     r15d, 3
0x1800390f2  jz      short loc_1800390FA
0x1800390f4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800390fa  mov     ecx, 8000FFFFh; this
0x1800390ff  mov     [rbx+8], ecx
0x180039102  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180039107  mov     [rbx+0Ch], eax
0x18003910a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180039111  jnz     short loc_180039132
0x180039113  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003911a  test    rax, rax
0x18003911d  jz      short loc_180039128
0x18003911f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039124  test    al, al
0x180039126  jmp     short loc_180039130
0x180039128  call    cs:__imp_IsDebuggerPresent
0x18003912e  test    eax, eax
0x180039130  jz      short loc_180039138
0x180039132  test    byte ptr [rbx+4], 2
0x180039136  jz      short loc_18003915C
0x180039138  mov     rax, cs:g_pfnResultLoggingCallback
0x18003913f  test    rax, rax
0x180039142  jz      short loc_1800391A0
0x180039144  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003914b  jnz     short loc_1800391A0
0x18003914d  xor     r8d, r8d
0x180039150  xor     edx, edx
0x180039152  mov     rcx, rbx
0x180039155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003915a  jmp     short loc_1800391A0
0x18003915c  mov     rax, cs:g_pfnResultLoggingCallback
0x180039163  mov     ebp, 800h
0x180039168  test    rax, rax
0x18003916b  jz      short loc_180039184
0x18003916d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180039174  jnz     short loc_180039184
0x180039176  mov     r8d, ebp
0x180039179  mov     rdx, rsi
0x18003917c  mov     rcx, rbx
0x18003917f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039184  cmp     [rsi], di
0x180039187  jnz     short loc_180039197
0x180039189  mov     r8, rbx; unsigned __int64
0x18003918c  mov     rdx, rbp; unsigned __int16 *
0x18003918f  mov     rcx, rsi; this
0x180039192  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180039197  mov     rcx, rsi; lpOutputString
0x18003919a  call    cs:__imp_OutputDebugStringW
0x1800391a0  test    byte ptr [rbx+4], 4
0x1800391a4  jnz     short loc_1800391AF
0x1800391a6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800391ad  jz      short loc_1800391C0
0x1800391af  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800391b6  test    rax, rax
0x1800391b9  jz      short loc_1800391C0
0x1800391bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391c0  mov     rbx, [rsp+78h+arg_10]
0x1800391c8  add     rsp, 40h
0x1800391cc  pop     r15
0x1800391ce  pop     r14
0x1800391d0  pop     r13
0x1800391d2  pop     r12
0x1800391d4  pop     rdi
0x1800391d5  pop     rsi
0x1800391d6  pop     rbp
0x1800391d7  retn
```
