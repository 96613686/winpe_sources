# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800050a0`
- end: `0x1800053ab`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003da0`

## callees

- `0x1800037a8`
- `0x180004624`
- `0x180004edc`
- `0x1800050a0`
- `0x180005874`
- `0x1800058a0`
- `0x1800058b4`
- `0x1800058d4`
- `0x180006464`
- `0x180011010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1800052e8`
- `KERNEL32!IsDebuggerPresent` at `0x1800052e8`
- `KERNEL32!OutputDebugStringW` at `0x180005360`
- `KERNEL32!OutputDebugStringW` at `0x180005360`
- `KERNEL32!GetCurrentThreadId` at `0x1800051c3`
- `KERNEL32!GetCurrentThreadId` at `0x1800051c3`

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
0x1800050a0  mov     [rsp+arg_10], rbx
0x1800050a5  mov     [rsp+arg_8], edx
0x1800050a9  mov     [rsp+arg_0], rcx
0x1800050ae  push    rbp
0x1800050af  push    rsi
0x1800050b0  push    rdi
0x1800050b1  push    r12
0x1800050b3  push    r13
0x1800050b5  push    r14
0x1800050b7  push    r15
0x1800050b9  sub     rsp, 40h
0x1800050bd  mov     r14, [rsp+78h+arg_38]
0x1800050c5  xor     eax, eax
0x1800050c7  mov     rbx, [rsp+78h+arg_78]
0x1800050cf  xor     ebp, ebp
0x1800050d1  mov     r15d, [rsp+78h+arg_30]
0x1800050d9  mov     r10, rcx
0x1800050dc  mov     rsi, [rsp+78h+lpOutputString]
0x1800050e4  mov     r12, r9
0x1800050e7  mov     r13, r8
0x1800050ea  mov     ecx, r15d
0x1800050ed  mov     [rsi], ax
0x1800050f0  mov     rax, [rsp+78h+arg_60]
0x1800050f8  mov     byte ptr [rax], 0
0x1800050fb  mov     edi, [r14]
0x1800050fe  mov     [rbx+8], edi
0x180005101  mov     eax, [r14+4]
0x180005105  mov     [rbx+0Ch], eax
0x180005108  test    r15d, r15d
0x18000510b  jz      short loc_180005173
0x18000510d  sub     ecx, 1
0x180005110  jz      short loc_18000516A
0x180005112  sub     ecx, 1
0x180005115  jz      short loc_180005125
0x180005117  cmp     ecx, 1
0x18000511a  jnz     short loc_18000517C
0x18000511c  mov     ecx, edi; this
0x18000511e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005123  jmp     short loc_18000517A
0x180005125  test    edi, edi
0x180005127  js      short loc_180005161
0x180005129  mov     rax, [rsp+78h+arg_28]
0x180005131  mov     edi, 8007029Ch
0x180005136  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000513a  mov     rcx, r10; int
0x18000513d  mov     [rsp+78h+var_50], rax; __int64
0x180005142  mov     rax, [rsp+78h+arg_20]
0x18000514a  mov     [rsp+78h+var_58], rax; __int64
0x18000514f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005154  mov     ecx, edi; this
0x180005156  mov     [rbx+8], edi
0x180005159  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000515e  mov     [rbx+0Ch], eax
0x180005161  mov     ecx, edi; this
0x180005163  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005168  jmp     short loc_18000517A
0x18000516a  mov     ecx, edi; this
0x18000516c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005171  jmp     short loc_18000517A
0x180005173  mov     ecx, edi; this
0x180005175  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000517a  mov     ebp, eax
0x18000517c  mov     eax, [rsp+78h+arg_70]
0x180005183  mov     [rbx+4], eax
0x180005186  mov     [rbx], r15d
0x180005189  cmp     dword ptr [r14+8], 1
0x18000518e  jnz     short loc_180005196
0x180005190  or      eax, 8
0x180005193  mov     [rbx+4], eax
0x180005196  mov     eax, 1
0x18000519b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800051a3  inc     eax
0x1800051a5  xor     edi, edi
0x1800051a7  mov     [rbx+10h], eax
0x1800051aa  mov     rax, [rsp+78h+arg_40]
0x1800051b2  test    rax, rax
0x1800051b5  jz      short loc_1800051BC
0x1800051b7  cmp     [rax], di
0x1800051ba  jnz     short loc_1800051BF
0x1800051bc  mov     rax, rdi
0x1800051bf  mov     [rbx+18h], rax
0x1800051c3  call    cs:__imp_GetCurrentThreadId
0x1800051ca  nop     dword ptr [rax+rax+00h]
0x1800051cf  mov     [rbx+38h], r13
0x1800051d3  xorps   xmm0, xmm0
0x1800051d6  mov     [rbx+20h], eax
0x1800051d9  mov     eax, [rsp+78h+arg_8]
0x1800051e0  mov     [rbx+40h], eax
0x1800051e3  mov     rax, [rsp+78h+arg_20]
0x1800051eb  mov     [rbx+28h], rax
0x1800051ef  mov     rax, [rsp+78h+arg_28]
0x1800051f7  mov     [rbx+88h], rax
0x1800051fe  mov     rax, [rsp+78h+arg_0]
0x180005206  mov     [rbx+90h], rax
0x18000520d  xor     eax, eax
0x18000520f  mov     [rbx+44h], ebp
0x180005212  mov     [rbx+30h], r12
0x180005216  mov     [rbx+48h], rdi
0x18000521a  movups  xmmword ptr [rbx+68h], xmm0
0x18000521e  mov     [rbx+78h], rax
0x180005222  movups  xmmword ptr [rbx+50h], xmm0
0x180005226  mov     [rbx+60h], rax
0x18000522a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005231  test    rax, rax
0x180005234  jz      short loc_18000523D
0x180005236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000523b  jmp     short loc_180005240
0x18000523d  mov     rax, rdi
0x180005240  mov     [rbx+80h], rax
0x180005247  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000524e  test    rax, rax
0x180005251  jz      short loc_18000525B
0x180005253  mov     rcx, rbx
0x180005256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000525b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005262  test    rax, rax
0x180005265  jz      short loc_18000527D
0x180005267  mov     rdx, [rsp+78h+arg_60]
0x18000526f  mov     r8d, 400h
0x180005275  mov     rcx, rbx
0x180005278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000527d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005284  test    rax, rax
0x180005287  jz      short loc_180005291
0x180005289  mov     rcx, rbx
0x18000528c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005291  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005298  test    rax, rax
0x18000529b  jz      short loc_1800052AB
0x18000529d  test    byte ptr [rbx+4], 2
0x1800052a1  jnz     short loc_1800052AB
0x1800052a3  mov     rcx, rbx
0x1800052a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052ab  cmp     [rbx+8], edi
0x1800052ae  jl      short loc_1800052CA
0x1800052b0  cmp     r15d, 3
0x1800052b4  jnz     loc_1800053A5
0x1800052ba  mov     ecx, 8000FFFFh; this
0x1800052bf  mov     [rbx+8], ecx
0x1800052c2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800052c7  mov     [rbx+0Ch], eax
0x1800052ca  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800052d1  jnz     short loc_1800052F8
0x1800052d3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800052da  test    rax, rax
0x1800052dd  jz      short loc_1800052E8
0x1800052df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052e4  test    al, al
0x1800052e6  jmp     short loc_1800052F6
0x1800052e8  call    cs:__imp_IsDebuggerPresent
0x1800052ef  nop     dword ptr [rax+rax+00h]
0x1800052f4  test    eax, eax
0x1800052f6  jz      short loc_1800052FE
0x1800052f8  test    byte ptr [rbx+4], 2
0x1800052fc  jz      short loc_180005322
0x1800052fe  mov     rax, cs:g_pfnResultLoggingCallback
0x180005305  test    rax, rax
0x180005308  jz      short loc_18000536C
0x18000530a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005311  jnz     short loc_18000536C
0x180005313  xor     r8d, r8d
0x180005316  xor     edx, edx
0x180005318  mov     rcx, rbx
0x18000531b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005320  jmp     short loc_18000536C
0x180005322  mov     rax, cs:g_pfnResultLoggingCallback
0x180005329  mov     ebp, 800h
0x18000532e  test    rax, rax
0x180005331  jz      short loc_18000534A
0x180005333  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000533a  jnz     short loc_18000534A
0x18000533c  mov     r8d, ebp
0x18000533f  mov     rdx, rsi
0x180005342  mov     rcx, rbx
0x180005345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000534a  cmp     [rsi], di
0x18000534d  jnz     short loc_18000535D
0x18000534f  mov     r8, rbx; unsigned __int64
0x180005352  mov     rdx, rbp; unsigned __int16 *
0x180005355  mov     rcx, rsi; this
0x180005358  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000535d  mov     rcx, rsi; lpOutputString
0x180005360  call    cs:__imp_OutputDebugStringW
0x180005367  nop     dword ptr [rax+rax+00h]
0x18000536c  test    byte ptr [rbx+4], 4
0x180005370  jnz     short loc_18000537B
0x180005372  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005379  jz      short loc_18000538C
0x18000537b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005382  test    rax, rax
0x180005385  jz      short loc_18000538C
0x180005387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000538c  mov     rbx, [rsp+78h+arg_10]
0x180005394  add     rsp, 40h
0x180005398  pop     r15
0x18000539a  pop     r14
0x18000539c  pop     r13
0x18000539e  pop     r12
0x1800053a0  pop     rdi
0x1800053a1  pop     rsi
0x1800053a2  pop     rbp
0x1800053a3  retn
0x1800053a5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
