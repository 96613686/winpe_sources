# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180016550`
- end: `0x180016868`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `792`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180016020`

## callees

- `0x180015fe0`
- `0x180016000`
- `0x180016110`
- `0x180016180`
- `0x1800161a0`
- `0x1800161b0`
- `0x180016290`
- `0x180016550`
- `0x180016c60`
- `0x18005e260`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180016822`
- `KERNEL32!OutputDebugStringW` at `0x180016822`
- `KERNEL32!GetCurrentThreadId` at `0x180016674`
- `KERNEL32!GetCurrentThreadId` at `0x180016674`
- `KERNEL32!IsDebuggerPresent` at `0x1800167a6`
- `KERNEL32!IsDebuggerPresent` at `0x1800167a6`

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
        WCHAR *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  int IsDebuggerPresent; // esi
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  wil::details *v27; // [rsp+30h] [rbp-48h]

  IsDebuggerPresent = 0;
  *lpOutputString = 0;
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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
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
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24)),
         IsDebuggerPresent))
    && (*(_BYTE *)(a16 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW(lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a16, 0, 0);
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
0x180016550  mov     [rsp+arg_18], rbx
0x180016555  mov     [rsp+arg_10], r8
0x18001655a  mov     [rsp+arg_8], edx
0x18001655e  mov     [rsp+arg_0], rcx
0x180016563  push    rbp
0x180016564  push    rsi
0x180016565  push    rdi
0x180016566  push    r12
0x180016568  push    r13
0x18001656a  push    r14
0x18001656c  push    r15
0x18001656e  sub     rsp, 40h
0x180016572  mov     r13, r9
0x180016575  mov     r10, rcx
0x180016578  xor     esi, esi
0x18001657a  mov     r14, [rsp+78h+lpOutputString]
0x180016582  mov     [r14], si
0x180016586  mov     rax, [rsp+78h+arg_60]
0x18001658e  mov     [rax], sil
0x180016591  mov     r15, [rsp+78h+arg_38]
0x180016599  mov     edi, [r15]
0x18001659c  mov     rbx, [rsp+78h+arg_78]
0x1800165a4  mov     [rbx+8], edi
0x1800165a7  mov     eax, [r15+4]
0x1800165ab  mov     [rbx+0Ch], eax
0x1800165ae  mov     ebp, esi
0x1800165b0  mov     r12d, [rsp+78h+arg_30]
0x1800165b8  mov     ecx, r12d
0x1800165bb  test    r12d, r12d
0x1800165be  jz      short loc_180016626
0x1800165c0  sub     ecx, 1
0x1800165c3  jz      short loc_18001661D
0x1800165c5  sub     ecx, 1
0x1800165c8  jz      short loc_1800165D8
0x1800165ca  cmp     ecx, 1
0x1800165cd  jnz     short loc_18001662F
0x1800165cf  mov     ecx, edi; this
0x1800165d1  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800165d6  jmp     short loc_18001662D
0x1800165d8  test    edi, edi
0x1800165da  js      short loc_180016614
0x1800165dc  mov     edi, 8007029Ch
0x1800165e1  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800165e5  mov     rax, [rsp+78h+arg_28]
0x1800165ed  mov     [rsp+78h+var_50], rax; __int64
0x1800165f2  mov     rax, [rsp+78h+arg_20]
0x1800165fa  mov     [rsp+78h+var_58], rax; __int64
0x1800165ff  mov     rcx, r10; int
0x180016602  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180016607  mov     [rbx+8], edi
0x18001660a  mov     ecx, edi; this
0x18001660c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180016611  mov     [rbx+0Ch], eax
0x180016614  mov     ecx, edi; this
0x180016616  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001661b  jmp     short loc_18001662D
0x18001661d  mov     ecx, edi; this
0x18001661f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180016624  jmp     short loc_18001662D
0x180016626  mov     ecx, edi; this
0x180016628  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001662d  mov     ebp, eax
0x18001662f  mov     [rbx], r12d
0x180016632  mov     eax, [rsp+78h+arg_70]
0x180016639  mov     [rbx+4], eax
0x18001663c  cmp     dword ptr [r15+8], 1
0x180016641  jnz     short loc_180016649
0x180016643  or      eax, 8
0x180016646  mov     [rbx+4], eax
0x180016649  mov     eax, 1
0x18001664e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180016656  inc     eax
0x180016658  mov     [rbx+10h], eax
0x18001665b  mov     rax, [rsp+78h+arg_40]
0x180016663  test    rax, rax
0x180016666  jz      short loc_18001666D
0x180016668  cmp     [rax], si
0x18001666b  jnz     short loc_180016670
0x18001666d  mov     rax, rsi
0x180016670  mov     [rbx+18h], rax
0x180016674  call    cs:__imp_GetCurrentThreadId
0x18001667a  mov     [rbx+20h], eax
0x18001667d  mov     rax, [rsp+78h+arg_10]
0x180016685  mov     [rbx+38h], rax
0x180016689  mov     eax, [rsp+78h+arg_8]
0x180016690  mov     [rbx+40h], eax
0x180016693  mov     [rbx+44h], ebp
0x180016696  mov     rax, [rsp+78h+arg_20]
0x18001669e  mov     [rbx+28h], rax
0x1800166a2  mov     [rbx+30h], r13
0x1800166a6  mov     rax, [rsp+78h+arg_28]
0x1800166ae  mov     [rbx+88h], rax
0x1800166b5  mov     rax, [rsp+78h+arg_0]
0x1800166bd  mov     [rbx+90h], rax
0x1800166c4  mov     [rbx+48h], rsi
0x1800166c8  xorps   xmm0, xmm0
0x1800166cb  xor     eax, eax
0x1800166cd  movups  xmmword ptr [rbx+68h], xmm0
0x1800166d1  mov     [rbx+78h], rax
0x1800166d5  movups  xmmword ptr [rbx+50h], xmm0
0x1800166d9  mov     [rbx+60h], rax
0x1800166dd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800166e4  test    rax, rax
0x1800166e7  jz      short loc_1800166F1
0x1800166e9  call    cs:__guard_dispatch_icall_fptr
0x1800166ef  jmp     short loc_1800166F4
0x1800166f1  mov     rax, rsi
0x1800166f4  mov     [rbx+80h], rax
0x1800166fb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180016702  test    rax, rax
0x180016705  jz      short loc_180016710
0x180016707  mov     rcx, rbx
0x18001670a  call    cs:__guard_dispatch_icall_fptr
0x180016710  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180016717  test    rax, rax
0x18001671a  jz      short loc_180016733
0x18001671c  mov     r8d, 400h
0x180016722  mov     rdx, [rsp+78h+arg_60]
0x18001672a  mov     rcx, rbx
0x18001672d  call    cs:__guard_dispatch_icall_fptr
0x180016733  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001673a  test    rax, rax
0x18001673d  jz      short loc_180016748
0x18001673f  mov     rcx, rbx
0x180016742  call    cs:__guard_dispatch_icall_fptr
0x180016748  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001674f  test    rax, rax
0x180016752  jz      short loc_180016763
0x180016754  test    byte ptr [rbx+4], 2
0x180016758  jnz     short loc_180016763
0x18001675a  mov     rcx, rbx
0x18001675d  call    cs:__guard_dispatch_icall_fptr
0x180016763  cmp     [rbx+8], esi
0x180016766  jl      short loc_180016786
0x180016768  cmp     r12d, 3
0x18001676c  jnz     loc_180016862
0x180016772  mov     dword ptr [rbx+8], 8000FFFFh
0x180016779  mov     ecx, 8000FFFFh; this
0x18001677e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180016783  mov     [rbx+0Ch], eax
0x180016786  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, sil; bool wil::g_fIsDebuggerPresent
0x18001678d  jnz     short loc_1800167B6
0x18001678f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180016796  test    rax, rax
0x180016799  jz      short loc_1800167A6
0x18001679b  call    cs:__guard_dispatch_icall_fptr
0x1800167a1  movzx   esi, al
0x1800167a4  jmp     short loc_1800167B2
0x1800167a6  call    cs:__imp_IsDebuggerPresent
0x1800167ac  test    eax, eax
0x1800167ae  setnz   sil
0x1800167b2  test    esi, esi
0x1800167b4  jz      short loc_1800167BC
0x1800167b6  test    byte ptr [rbx+4], 2
0x1800167ba  jz      short loc_1800167E1
0x1800167bc  mov     rax, cs:g_pfnResultLoggingCallback
0x1800167c3  test    rax, rax
0x1800167c6  jz      short loc_180016828
0x1800167c8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1800167cf  jnz     short loc_180016828
0x1800167d1  xor     r8d, r8d
0x1800167d4  xor     edx, edx
0x1800167d6  mov     rcx, rbx
0x1800167d9  call    cs:__guard_dispatch_icall_fptr
0x1800167df  jmp     short loc_180016828
0x1800167e1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800167e8  test    rax, rax
0x1800167eb  jz      short loc_180016808
0x1800167ed  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1800167f4  jnz     short loc_180016808
0x1800167f6  mov     r8d, 800h
0x1800167fc  mov     rdx, r14
0x1800167ff  mov     rcx, rbx
0x180016802  call    cs:__guard_dispatch_icall_fptr
0x180016808  cmp     word ptr [r14], 0
0x18001680d  jnz     short loc_18001681F
0x18001680f  mov     r8, rbx; unsigned __int64
0x180016812  mov     edx, 800h; wchar_t *
0x180016817  mov     rcx, r14; Buffer
0x18001681a  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18001681f  mov     rcx, r14; lpOutputString
0x180016822  call    cs:__imp_OutputDebugStringW
0x180016828  test    byte ptr [rbx+4], 4
0x18001682c  jnz     short loc_180016837
0x18001682e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x180016835  jz      short loc_18001684A
0x180016837  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001683e  test    rax, rax
0x180016841  jz      short loc_18001684A
0x180016843  call    cs:__guard_dispatch_icall_fptr
0x180016849  nop
0x18001684a  mov     rbx, [rsp+78h+arg_18]
0x180016852  add     rsp, 40h
0x180016856  pop     r15
0x180016858  pop     r14
0x18001685a  pop     r13
0x18001685c  pop     r12
0x18001685e  pop     rdi
0x18001685f  pop     rsi
0x180016860  pop     rbp
0x180016861  retn
0x180016862  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
