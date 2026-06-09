# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180009118`
- end: `0x180009411`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180006988`
- `0x180006ccc`

## callees

- `0x1800068c8`
- `0x1800084c4`
- `0x180008d30`
- `0x180009118`
- `0x180009f30`
- `0x180009f50`
- `0x18000a0a0`
- `0x18000a0bc`
- `0x18000bc54`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000923b`
- `KERNEL32!GetCurrentThreadId` at `0x18000923b`
- `KERNEL32!OutputDebugStringW` at `0x1800093cc`
- `KERNEL32!OutputDebugStringW` at `0x1800093cc`
- `KERNEL32!IsDebuggerPresent` at `0x18000935a`
- `KERNEL32!IsDebuggerPresent` at `0x18000935a`

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
0x180009118  mov     [rsp+arg_10], rbx
0x18000911d  mov     [rsp+arg_8], edx
0x180009121  mov     [rsp+arg_0], rcx
0x180009126  push    rbp
0x180009127  push    rsi
0x180009128  push    rdi
0x180009129  push    r12
0x18000912b  push    r13
0x18000912d  push    r14
0x18000912f  push    r15
0x180009131  sub     rsp, 40h
0x180009135  mov     r12, r9
0x180009138  mov     r13, r8
0x18000913b  mov     r10, rcx
0x18000913e  xor     eax, eax
0x180009140  mov     rsi, [rsp+78h+lpOutputString]
0x180009148  mov     [rsi], ax
0x18000914b  mov     rax, [rsp+78h+arg_60]
0x180009153  mov     byte ptr [rax], 0
0x180009156  mov     r14, [rsp+78h+arg_38]
0x18000915e  mov     edi, [r14]
0x180009161  mov     rbx, [rsp+78h+arg_78]
0x180009169  mov     [rbx+8], edi
0x18000916c  mov     eax, [r14+4]
0x180009170  mov     [rbx+0Ch], eax
0x180009173  xor     ebp, ebp
0x180009175  mov     r15d, [rsp+78h+arg_30]
0x18000917d  mov     ecx, r15d
0x180009180  test    r15d, r15d
0x180009183  jz      short loc_1800091EB
0x180009185  sub     ecx, 1
0x180009188  jz      short loc_1800091E2
0x18000918a  sub     ecx, 1
0x18000918d  jz      short loc_18000919D
0x18000918f  cmp     ecx, 1
0x180009192  jnz     short loc_1800091F4
0x180009194  mov     ecx, edi; this
0x180009196  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000919b  jmp     short loc_1800091F2
0x18000919d  test    edi, edi
0x18000919f  js      short loc_1800091D9
0x1800091a1  mov     edi, 8007029Ch
0x1800091a6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800091aa  mov     rax, [rsp+78h+arg_28]
0x1800091b2  mov     [rsp+78h+var_50], rax; __int64
0x1800091b7  mov     rax, [rsp+78h+arg_20]
0x1800091bf  mov     [rsp+78h+var_58], rax; __int64
0x1800091c4  mov     rcx, r10; int
0x1800091c7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800091cc  mov     [rbx+8], edi
0x1800091cf  mov     ecx, edi; this
0x1800091d1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800091d6  mov     [rbx+0Ch], eax
0x1800091d9  mov     ecx, edi; this
0x1800091db  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800091e0  jmp     short loc_1800091F2
0x1800091e2  mov     ecx, edi; this
0x1800091e4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800091e9  jmp     short loc_1800091F2
0x1800091eb  mov     ecx, edi; this
0x1800091ed  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800091f2  mov     ebp, eax
0x1800091f4  mov     [rbx], r15d
0x1800091f7  mov     eax, [rsp+78h+arg_70]
0x1800091fe  mov     [rbx+4], eax
0x180009201  cmp     dword ptr [r14+8], 1
0x180009206  jnz     short loc_18000920E
0x180009208  or      eax, 8
0x18000920b  mov     [rbx+4], eax
0x18000920e  mov     eax, 1
0x180009213  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000921b  inc     eax
0x18000921d  mov     [rbx+10h], eax
0x180009220  mov     rax, [rsp+78h+arg_40]
0x180009228  xor     edi, edi
0x18000922a  test    rax, rax
0x18000922d  jz      short loc_180009234
0x18000922f  cmp     [rax], di
0x180009232  jnz     short loc_180009237
0x180009234  mov     rax, rdi
0x180009237  mov     [rbx+18h], rax
0x18000923b  call    cs:__imp_GetCurrentThreadId
0x180009241  mov     [rbx+20h], eax
0x180009244  mov     [rbx+38h], r13
0x180009248  mov     eax, [rsp+78h+arg_8]
0x18000924f  mov     [rbx+40h], eax
0x180009252  mov     [rbx+44h], ebp
0x180009255  mov     rax, [rsp+78h+arg_20]
0x18000925d  mov     [rbx+28h], rax
0x180009261  mov     [rbx+30h], r12
0x180009265  mov     rax, [rsp+78h+arg_28]
0x18000926d  mov     [rbx+88h], rax
0x180009274  mov     rax, [rsp+78h+arg_0]
0x18000927c  mov     [rbx+90h], rax
0x180009283  mov     [rbx+48h], rdi
0x180009287  xorps   xmm0, xmm0
0x18000928a  xor     eax, eax
0x18000928c  movups  xmmword ptr [rbx+68h], xmm0
0x180009290  mov     [rbx+78h], rax
0x180009294  movups  xmmword ptr [rbx+50h], xmm0
0x180009298  mov     [rbx+60h], rax
0x18000929c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800092a3  test    rax, rax
0x1800092a6  jz      short loc_1800092AF
0x1800092a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ad  jmp     short loc_1800092B2
0x1800092af  mov     rax, rdi
0x1800092b2  mov     [rbx+80h], rax
0x1800092b9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800092c0  test    rax, rax
0x1800092c3  jz      short loc_1800092CD
0x1800092c5  mov     rcx, rbx
0x1800092c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092cd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800092d4  test    rax, rax
0x1800092d7  jz      short loc_1800092EF
0x1800092d9  mov     r8d, 400h
0x1800092df  mov     rdx, [rsp+78h+arg_60]
0x1800092e7  mov     rcx, rbx
0x1800092ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ef  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800092f6  test    rax, rax
0x1800092f9  jz      short loc_180009303
0x1800092fb  mov     rcx, rbx
0x1800092fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009303  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000930a  test    rax, rax
0x18000930d  jz      short loc_18000931D
0x18000930f  test    byte ptr [rbx+4], 2
0x180009313  jnz     short loc_18000931D
0x180009315  mov     rcx, rbx
0x180009318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000931d  cmp     [rbx+8], edi
0x180009320  jl      short loc_18000933C
0x180009322  cmp     r15d, 3
0x180009326  jnz     loc_18000940B
0x18000932c  mov     ecx, 8000FFFFh; this
0x180009331  mov     [rbx+8], ecx
0x180009334  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009339  mov     [rbx+0Ch], eax
0x18000933c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180009343  jnz     short loc_180009364
0x180009345  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000934c  test    rax, rax
0x18000934f  jz      short loc_18000935A
0x180009351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009356  test    al, al
0x180009358  jmp     short loc_180009362
0x18000935a  call    cs:__imp_IsDebuggerPresent
0x180009360  test    eax, eax
0x180009362  jz      short loc_18000936A
0x180009364  test    byte ptr [rbx+4], 2
0x180009368  jz      short loc_18000938E
0x18000936a  mov     rax, cs:g_pfnResultLoggingCallback
0x180009371  test    rax, rax
0x180009374  jz      short loc_1800093D2
0x180009376  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000937d  jnz     short loc_1800093D2
0x18000937f  xor     r8d, r8d
0x180009382  xor     edx, edx
0x180009384  mov     rcx, rbx
0x180009387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000938c  jmp     short loc_1800093D2
0x18000938e  mov     ebp, 800h
0x180009393  mov     rax, cs:g_pfnResultLoggingCallback
0x18000939a  test    rax, rax
0x18000939d  jz      short loc_1800093B6
0x18000939f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800093a6  jnz     short loc_1800093B6
0x1800093a8  mov     r8d, ebp
0x1800093ab  mov     rdx, rsi
0x1800093ae  mov     rcx, rbx
0x1800093b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093b6  cmp     [rsi], di
0x1800093b9  jnz     short loc_1800093C9
0x1800093bb  mov     r8, rbx; unsigned __int64
0x1800093be  mov     rdx, rbp; unsigned __int16 *
0x1800093c1  mov     rcx, rsi; this
0x1800093c4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800093c9  mov     rcx, rsi; lpOutputString
0x1800093cc  call    cs:__imp_OutputDebugStringW
0x1800093d2  test    byte ptr [rbx+4], 4
0x1800093d6  jnz     short loc_1800093E1
0x1800093d8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800093df  jz      short loc_1800093F3
0x1800093e1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800093e8  test    rax, rax
0x1800093eb  jz      short loc_1800093F3
0x1800093ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093f2  nop
0x1800093f3  mov     rbx, [rsp+78h+arg_10]
0x1800093fb  add     rsp, 40h
0x1800093ff  pop     r15
0x180009401  pop     r14
0x180009403  pop     r13
0x180009405  pop     r12
0x180009407  pop     rdi
0x180009408  pop     rsi
0x180009409  pop     rbp
0x18000940a  retn
0x18000940b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
