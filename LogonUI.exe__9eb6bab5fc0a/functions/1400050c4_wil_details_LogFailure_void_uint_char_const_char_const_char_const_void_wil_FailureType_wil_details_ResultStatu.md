# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400050c4`
- end: `0x1400053b8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1400036fc`
- `0x1400037ac`
- `0x1400038a0`

## callees

- `0x140002194`
- `0x140003650`
- `0x140004884`
- `0x1400050c4`
- `0x140005bb8`
- `0x140005be0`
- `0x140005c9c`
- `0x140005cb8`
- `0x140006f58`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400051e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400051e7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000537a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000537a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005308`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005308`

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
0x1400050c4  mov     [rsp+arg_10], rbx
0x1400050c9  mov     [rsp+arg_8], edx
0x1400050cd  mov     [rsp+arg_0], rcx
0x1400050d2  push    rbp
0x1400050d3  push    rsi
0x1400050d4  push    rdi
0x1400050d5  push    r12
0x1400050d7  push    r13
0x1400050d9  push    r14
0x1400050db  push    r15
0x1400050dd  sub     rsp, 40h
0x1400050e1  mov     r14, [rsp+78h+arg_38]
0x1400050e9  xor     eax, eax
0x1400050eb  mov     rbx, [rsp+78h+arg_78]
0x1400050f3  xor     ebp, ebp
0x1400050f5  mov     r15d, [rsp+78h+arg_30]
0x1400050fd  mov     r10, rcx
0x140005100  mov     rsi, [rsp+78h+lpOutputString]
0x140005108  mov     r12, r9
0x14000510b  mov     r13, r8
0x14000510e  mov     ecx, r15d
0x140005111  mov     [rsi], ax
0x140005114  mov     rax, [rsp+78h+arg_60]
0x14000511c  mov     byte ptr [rax], 0
0x14000511f  mov     edi, [r14]
0x140005122  mov     [rbx+8], edi
0x140005125  mov     eax, [r14+4]
0x140005129  mov     [rbx+0Ch], eax
0x14000512c  test    r15d, r15d
0x14000512f  jz      short loc_140005197
0x140005131  sub     ecx, 1
0x140005134  jz      short loc_14000518E
0x140005136  sub     ecx, 1
0x140005139  jz      short loc_140005149
0x14000513b  cmp     ecx, 1
0x14000513e  jnz     short loc_1400051A0
0x140005140  mov     ecx, edi; this
0x140005142  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140005147  jmp     short loc_14000519E
0x140005149  test    edi, edi
0x14000514b  js      short loc_140005185
0x14000514d  mov     rax, [rsp+78h+arg_28]
0x140005155  mov     edi, 8007029Ch
0x14000515a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000515e  mov     rcx, r10; int
0x140005161  mov     [rsp+78h+var_50], rax; __int64
0x140005166  mov     rax, [rsp+78h+arg_20]
0x14000516e  mov     [rsp+78h+var_58], rax; __int64
0x140005173  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140005178  mov     ecx, edi; this
0x14000517a  mov     [rbx+8], edi
0x14000517d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005182  mov     [rbx+0Ch], eax
0x140005185  mov     ecx, edi; this
0x140005187  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000518c  jmp     short loc_14000519E
0x14000518e  mov     ecx, edi; this
0x140005190  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140005195  jmp     short loc_14000519E
0x140005197  mov     ecx, edi; this
0x140005199  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000519e  mov     ebp, eax
0x1400051a0  mov     eax, [rsp+78h+arg_70]
0x1400051a7  mov     [rbx+4], eax
0x1400051aa  mov     [rbx], r15d
0x1400051ad  cmp     dword ptr [r14+8], 1
0x1400051b2  jnz     short loc_1400051BA
0x1400051b4  or      eax, 8
0x1400051b7  mov     [rbx+4], eax
0x1400051ba  mov     eax, 1
0x1400051bf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400051c7  inc     eax
0x1400051c9  xor     edi, edi
0x1400051cb  mov     [rbx+10h], eax
0x1400051ce  mov     rax, [rsp+78h+arg_40]
0x1400051d6  test    rax, rax
0x1400051d9  jz      short loc_1400051E0
0x1400051db  cmp     [rax], di
0x1400051de  jnz     short loc_1400051E3
0x1400051e0  mov     rax, rdi
0x1400051e3  mov     [rbx+18h], rax
0x1400051e7  call    cs:__imp_GetCurrentThreadId
0x1400051ed  mov     [rbx+38h], r13
0x1400051f1  xorps   xmm0, xmm0
0x1400051f4  mov     [rbx+20h], eax
0x1400051f7  mov     eax, [rsp+78h+arg_8]
0x1400051fe  mov     [rbx+40h], eax
0x140005201  mov     rax, [rsp+78h+arg_20]
0x140005209  mov     [rbx+28h], rax
0x14000520d  mov     rax, [rsp+78h+arg_28]
0x140005215  mov     [rbx+88h], rax
0x14000521c  mov     rax, [rsp+78h+arg_0]
0x140005224  mov     [rbx+90h], rax
0x14000522b  xor     eax, eax
0x14000522d  mov     [rbx+44h], ebp
0x140005230  mov     [rbx+30h], r12
0x140005234  mov     [rbx+48h], rdi
0x140005238  movups  xmmword ptr [rbx+68h], xmm0
0x14000523c  mov     [rbx+78h], rax
0x140005240  movups  xmmword ptr [rbx+50h], xmm0
0x140005244  mov     [rbx+60h], rax
0x140005248  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000524f  test    rax, rax
0x140005252  jz      short loc_14000525B
0x140005254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005259  jmp     short loc_14000525E
0x14000525b  mov     rax, rdi
0x14000525e  mov     [rbx+80h], rax
0x140005265  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000526c  test    rax, rax
0x14000526f  jz      short loc_140005279
0x140005271  mov     rcx, rbx
0x140005274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005279  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005280  test    rax, rax
0x140005283  jz      short loc_14000529B
0x140005285  mov     rdx, [rsp+78h+arg_60]
0x14000528d  mov     r8d, 400h
0x140005293  mov     rcx, rbx
0x140005296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000529b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400052a2  test    rax, rax
0x1400052a5  jz      short loc_1400052AF
0x1400052a7  mov     rcx, rbx
0x1400052aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052af  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400052b6  test    rax, rax
0x1400052b9  jz      short loc_1400052C9
0x1400052bb  test    byte ptr [rbx+4], 2
0x1400052bf  jnz     short loc_1400052C9
0x1400052c1  mov     rcx, rbx
0x1400052c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052c9  cmp     [rbx+8], edi
0x1400052cc  jl      short loc_1400052EA
0x1400052ce  cmp     r15d, 3
0x1400052d2  jz      short loc_1400052DA
0x1400052d4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400052da  mov     ecx, 8000FFFFh; this
0x1400052df  mov     [rbx+8], ecx
0x1400052e2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400052e7  mov     [rbx+0Ch], eax
0x1400052ea  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400052f1  jnz     short loc_140005312
0x1400052f3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400052fa  test    rax, rax
0x1400052fd  jz      short loc_140005308
0x1400052ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005304  test    al, al
0x140005306  jmp     short loc_140005310
0x140005308  call    cs:__imp_IsDebuggerPresent
0x14000530e  test    eax, eax
0x140005310  jz      short loc_140005318
0x140005312  test    byte ptr [rbx+4], 2
0x140005316  jz      short loc_14000533C
0x140005318  mov     rax, cs:g_pfnResultLoggingCallback
0x14000531f  test    rax, rax
0x140005322  jz      short loc_140005380
0x140005324  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000532b  jnz     short loc_140005380
0x14000532d  xor     r8d, r8d
0x140005330  xor     edx, edx
0x140005332  mov     rcx, rbx
0x140005335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000533a  jmp     short loc_140005380
0x14000533c  mov     rax, cs:g_pfnResultLoggingCallback
0x140005343  mov     ebp, 800h
0x140005348  test    rax, rax
0x14000534b  jz      short loc_140005364
0x14000534d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005354  jnz     short loc_140005364
0x140005356  mov     r8d, ebp
0x140005359  mov     rdx, rsi
0x14000535c  mov     rcx, rbx
0x14000535f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005364  cmp     [rsi], di
0x140005367  jnz     short loc_140005377
0x140005369  mov     r8, rbx; unsigned __int64
0x14000536c  mov     rdx, rbp; unsigned __int16 *
0x14000536f  mov     rcx, rsi; this
0x140005372  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140005377  mov     rcx, rsi; lpOutputString
0x14000537a  call    cs:__imp_OutputDebugStringW
0x140005380  test    byte ptr [rbx+4], 4
0x140005384  jnz     short loc_14000538F
0x140005386  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000538d  jz      short loc_1400053A0
0x14000538f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140005396  test    rax, rax
0x140005399  jz      short loc_1400053A0
0x14000539b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400053a0  mov     rbx, [rsp+78h+arg_10]
0x1400053a8  add     rsp, 40h
0x1400053ac  pop     r15
0x1400053ae  pop     r14
0x1400053b0  pop     r13
0x1400053b2  pop     r12
0x1400053b4  pop     rdi
0x1400053b5  pop     rsi
0x1400053b6  pop     rbp
0x1400053b7  retn
```
