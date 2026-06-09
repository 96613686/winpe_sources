# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180021054`
- end: `0x18002134c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001f100`

## callees

- `0x18001eb3c`
- `0x1800204e4`
- `0x180020d50`
- `0x180021054`
- `0x180021c98`
- `0x180021cc0`
- `0x180021e44`
- `0x180021e60`
- `0x18002350c`
- `0x180064010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180021308`
- `KERNEL32!OutputDebugStringW` at `0x180021308`
- `KERNEL32!IsDebuggerPresent` at `0x180021296`
- `KERNEL32!IsDebuggerPresent` at `0x180021296`
- `KERNEL32!GetCurrentThreadId` at `0x180021177`
- `KERNEL32!GetCurrentThreadId` at `0x180021177`

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
0x180021054  mov     [rsp+arg_10], rbx
0x180021059  mov     [rsp+arg_8], edx
0x18002105d  mov     [rsp+arg_0], rcx
0x180021062  push    rbp
0x180021063  push    rsi
0x180021064  push    rdi
0x180021065  push    r12
0x180021067  push    r13
0x180021069  push    r14
0x18002106b  push    r15
0x18002106d  sub     rsp, 40h
0x180021071  mov     r14, [rsp+78h+arg_38]
0x180021079  xor     eax, eax
0x18002107b  mov     rbx, [rsp+78h+arg_78]
0x180021083  xor     ebp, ebp
0x180021085  mov     r15d, [rsp+78h+arg_30]
0x18002108d  mov     r10, rcx
0x180021090  mov     rsi, [rsp+78h+lpOutputString]
0x180021098  mov     r12, r9
0x18002109b  mov     r13, r8
0x18002109e  mov     ecx, r15d
0x1800210a1  mov     [rsi], ax
0x1800210a4  mov     rax, [rsp+78h+arg_60]
0x1800210ac  mov     byte ptr [rax], 0
0x1800210af  mov     edi, [r14]
0x1800210b2  mov     [rbx+8], edi
0x1800210b5  mov     eax, [r14+4]
0x1800210b9  mov     [rbx+0Ch], eax
0x1800210bc  test    r15d, r15d
0x1800210bf  jz      short loc_180021127
0x1800210c1  sub     ecx, 1
0x1800210c4  jz      short loc_18002111E
0x1800210c6  sub     ecx, 1
0x1800210c9  jz      short loc_1800210D9
0x1800210cb  cmp     ecx, 1
0x1800210ce  jnz     short loc_180021130
0x1800210d0  mov     ecx, edi; this
0x1800210d2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800210d7  jmp     short loc_18002112E
0x1800210d9  test    edi, edi
0x1800210db  js      short loc_180021115
0x1800210dd  mov     rax, [rsp+78h+arg_28]
0x1800210e5  mov     edi, 8007029Ch
0x1800210ea  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800210ee  mov     rcx, r10; int
0x1800210f1  mov     [rsp+78h+var_50], rax; __int64
0x1800210f6  mov     rax, [rsp+78h+arg_20]
0x1800210fe  mov     [rsp+78h+var_58], rax; __int64
0x180021103  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180021108  mov     ecx, edi; this
0x18002110a  mov     [rbx+8], edi
0x18002110d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180021112  mov     [rbx+0Ch], eax
0x180021115  mov     ecx, edi; this
0x180021117  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18002111c  jmp     short loc_18002112E
0x18002111e  mov     ecx, edi; this
0x180021120  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180021125  jmp     short loc_18002112E
0x180021127  mov     ecx, edi; this
0x180021129  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002112e  mov     ebp, eax
0x180021130  mov     eax, [rsp+78h+arg_70]
0x180021137  mov     [rbx+4], eax
0x18002113a  mov     [rbx], r15d
0x18002113d  cmp     dword ptr [r14+8], 1
0x180021142  jnz     short loc_18002114A
0x180021144  or      eax, 8
0x180021147  mov     [rbx+4], eax
0x18002114a  mov     eax, 1
0x18002114f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180021157  inc     eax
0x180021159  xor     edi, edi
0x18002115b  mov     [rbx+10h], eax
0x18002115e  mov     rax, [rsp+78h+arg_40]
0x180021166  test    rax, rax
0x180021169  jz      short loc_180021170
0x18002116b  cmp     [rax], di
0x18002116e  jnz     short loc_180021173
0x180021170  mov     rax, rdi
0x180021173  mov     [rbx+18h], rax
0x180021177  call    cs:__imp_GetCurrentThreadId
0x18002117d  mov     [rbx+38h], r13
0x180021181  xorps   xmm0, xmm0
0x180021184  mov     [rbx+20h], eax
0x180021187  mov     eax, [rsp+78h+arg_8]
0x18002118e  mov     [rbx+40h], eax
0x180021191  mov     rax, [rsp+78h+arg_20]
0x180021199  mov     [rbx+28h], rax
0x18002119d  mov     rax, [rsp+78h+arg_28]
0x1800211a5  mov     [rbx+88h], rax
0x1800211ac  mov     rax, [rsp+78h+arg_0]
0x1800211b4  mov     [rbx+90h], rax
0x1800211bb  xor     eax, eax
0x1800211bd  mov     [rbx+44h], ebp
0x1800211c0  mov     [rbx+30h], r12
0x1800211c4  mov     [rbx+48h], rdi
0x1800211c8  movups  xmmword ptr [rbx+68h], xmm0
0x1800211cc  mov     [rbx+78h], rax
0x1800211d0  movups  xmmword ptr [rbx+50h], xmm0
0x1800211d4  mov     [rbx+60h], rax
0x1800211d8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800211df  test    rax, rax
0x1800211e2  jz      short loc_1800211EB
0x1800211e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211e9  jmp     short loc_1800211EE
0x1800211eb  mov     rax, rdi
0x1800211ee  mov     [rbx+80h], rax
0x1800211f5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800211fc  test    rax, rax
0x1800211ff  jz      short loc_180021209
0x180021201  mov     rcx, rbx
0x180021204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021209  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180021210  test    rax, rax
0x180021213  jz      short loc_18002122B
0x180021215  mov     rdx, [rsp+78h+arg_60]
0x18002121d  mov     r8d, 400h
0x180021223  mov     rcx, rbx
0x180021226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002122b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021232  test    rax, rax
0x180021235  jz      short loc_18002123F
0x180021237  mov     rcx, rbx
0x18002123a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002123f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021246  test    rax, rax
0x180021249  jz      short loc_180021259
0x18002124b  test    byte ptr [rbx+4], 2
0x18002124f  jnz     short loc_180021259
0x180021251  mov     rcx, rbx
0x180021254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021259  cmp     [rbx+8], edi
0x18002125c  jl      short loc_180021278
0x18002125e  cmp     r15d, 3
0x180021262  jnz     loc_180021346
0x180021268  mov     ecx, 8000FFFFh; this
0x18002126d  mov     [rbx+8], ecx
0x180021270  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180021275  mov     [rbx+0Ch], eax
0x180021278  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002127f  jnz     short loc_1800212A0
0x180021281  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180021288  test    rax, rax
0x18002128b  jz      short loc_180021296
0x18002128d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021292  test    al, al
0x180021294  jmp     short loc_18002129E
0x180021296  call    cs:__imp_IsDebuggerPresent
0x18002129c  test    eax, eax
0x18002129e  jz      short loc_1800212A6
0x1800212a0  test    byte ptr [rbx+4], 2
0x1800212a4  jz      short loc_1800212CA
0x1800212a6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800212ad  test    rax, rax
0x1800212b0  jz      short loc_18002130E
0x1800212b2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800212b9  jnz     short loc_18002130E
0x1800212bb  xor     r8d, r8d
0x1800212be  xor     edx, edx
0x1800212c0  mov     rcx, rbx
0x1800212c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212c8  jmp     short loc_18002130E
0x1800212ca  mov     rax, cs:g_pfnResultLoggingCallback
0x1800212d1  mov     ebp, 800h
0x1800212d6  test    rax, rax
0x1800212d9  jz      short loc_1800212F2
0x1800212db  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800212e2  jnz     short loc_1800212F2
0x1800212e4  mov     r8d, ebp
0x1800212e7  mov     rdx, rsi
0x1800212ea  mov     rcx, rbx
0x1800212ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212f2  cmp     [rsi], di
0x1800212f5  jnz     short loc_180021305
0x1800212f7  mov     r8, rbx; unsigned __int64
0x1800212fa  mov     rdx, rbp; unsigned __int16 *
0x1800212fd  mov     rcx, rsi; this
0x180021300  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180021305  mov     rcx, rsi; lpOutputString
0x180021308  call    cs:__imp_OutputDebugStringW
0x18002130e  test    byte ptr [rbx+4], 4
0x180021312  jnz     short loc_18002131D
0x180021314  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18002131b  jz      short loc_18002132E
0x18002131d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180021324  test    rax, rax
0x180021327  jz      short loc_18002132E
0x180021329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002132e  mov     rbx, [rsp+78h+arg_10]
0x180021336  add     rsp, 40h
0x18002133a  pop     r15
0x18002133c  pop     r14
0x18002133e  pop     r13
0x180021340  pop     r12
0x180021342  pop     rdi
0x180021343  pop     rsi
0x180021344  pop     rbp
0x180021345  retn
0x180021346  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
