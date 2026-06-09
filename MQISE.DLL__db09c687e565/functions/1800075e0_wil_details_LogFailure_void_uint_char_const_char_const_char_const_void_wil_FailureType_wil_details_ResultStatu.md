# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800075e0`
- end: `0x1800078d9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002a68`

## callees

- `0x1800024a4`
- `0x1800062b4`
- `0x180007318`
- `0x1800075e0`
- `0x1800086d4`
- `0x1800086f0`
- `0x18000881c`
- `0x180008838`
- `0x18000b3b8`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180007703`
- `KERNEL32!GetCurrentThreadId` at `0x180007703`
- `KERNEL32!IsDebuggerPresent` at `0x180007822`
- `KERNEL32!IsDebuggerPresent` at `0x180007822`
- `KERNEL32!OutputDebugStringW` at `0x180007894`
- `KERNEL32!OutputDebugStringW` at `0x180007894`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x1800075e0  mov     [rsp+arg_10], rbx
0x1800075e5  mov     [rsp+arg_8], edx
0x1800075e9  mov     [rsp+arg_0], rcx
0x1800075ee  push    rbp
0x1800075ef  push    rsi
0x1800075f0  push    rdi
0x1800075f1  push    r12
0x1800075f3  push    r13
0x1800075f5  push    r14
0x1800075f7  push    r15
0x1800075f9  sub     rsp, 40h
0x1800075fd  mov     r12, r9
0x180007600  mov     r13, r8
0x180007603  mov     r10, rcx
0x180007606  xor     eax, eax
0x180007608  mov     rsi, [rsp+78h+lpOutputString]
0x180007610  mov     [rsi], ax
0x180007613  mov     rax, [rsp+78h+arg_60]
0x18000761b  mov     byte ptr [rax], 0
0x18000761e  mov     r14, [rsp+78h+arg_38]
0x180007626  mov     edi, [r14]
0x180007629  mov     rbx, [rsp+78h+arg_78]
0x180007631  mov     [rbx+8], edi
0x180007634  mov     eax, [r14+4]
0x180007638  mov     [rbx+0Ch], eax
0x18000763b  xor     ebp, ebp
0x18000763d  mov     r15d, [rsp+78h+arg_30]
0x180007645  mov     ecx, r15d
0x180007648  test    r15d, r15d
0x18000764b  jz      short loc_1800076B3
0x18000764d  sub     ecx, 1
0x180007650  jz      short loc_1800076AA
0x180007652  sub     ecx, 1
0x180007655  jz      short loc_180007665
0x180007657  cmp     ecx, 1
0x18000765a  jnz     short loc_1800076BC
0x18000765c  mov     ecx, edi; this
0x18000765e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007663  jmp     short loc_1800076BA
0x180007665  test    edi, edi
0x180007667  js      short loc_1800076A1
0x180007669  mov     edi, 8007029Ch
0x18000766e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007672  mov     rax, [rsp+78h+arg_28]
0x18000767a  mov     [rsp+78h+var_50], rax; __int64
0x18000767f  mov     rax, [rsp+78h+arg_20]
0x180007687  mov     [rsp+78h+var_58], rax; __int64
0x18000768c  mov     rcx, r10; int
0x18000768f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007694  mov     [rbx+8], edi
0x180007697  mov     ecx, edi; this
0x180007699  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000769e  mov     [rbx+0Ch], eax
0x1800076a1  mov     ecx, edi; this
0x1800076a3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800076a8  jmp     short loc_1800076BA
0x1800076aa  mov     ecx, edi; this
0x1800076ac  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800076b1  jmp     short loc_1800076BA
0x1800076b3  mov     ecx, edi; this
0x1800076b5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800076ba  mov     ebp, eax
0x1800076bc  mov     [rbx], r15d
0x1800076bf  mov     eax, [rsp+78h+arg_70]
0x1800076c6  mov     [rbx+4], eax
0x1800076c9  cmp     dword ptr [r14+8], 1
0x1800076ce  jnz     short loc_1800076D6
0x1800076d0  or      eax, 8
0x1800076d3  mov     [rbx+4], eax
0x1800076d6  mov     eax, 1
0x1800076db  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800076e3  inc     eax
0x1800076e5  mov     [rbx+10h], eax
0x1800076e8  mov     rax, [rsp+78h+arg_40]
0x1800076f0  xor     edi, edi
0x1800076f2  test    rax, rax
0x1800076f5  jz      short loc_1800076FC
0x1800076f7  cmp     [rax], di
0x1800076fa  jnz     short loc_1800076FF
0x1800076fc  mov     rax, rdi
0x1800076ff  mov     [rbx+18h], rax
0x180007703  call    cs:__imp_GetCurrentThreadId
0x180007709  mov     [rbx+20h], eax
0x18000770c  mov     [rbx+38h], r13
0x180007710  mov     eax, [rsp+78h+arg_8]
0x180007717  mov     [rbx+40h], eax
0x18000771a  mov     [rbx+44h], ebp
0x18000771d  mov     rax, [rsp+78h+arg_20]
0x180007725  mov     [rbx+28h], rax
0x180007729  mov     [rbx+30h], r12
0x18000772d  mov     rax, [rsp+78h+arg_28]
0x180007735  mov     [rbx+88h], rax
0x18000773c  mov     rax, [rsp+78h+arg_0]
0x180007744  mov     [rbx+90h], rax
0x18000774b  mov     [rbx+48h], rdi
0x18000774f  xorps   xmm0, xmm0
0x180007752  xor     eax, eax
0x180007754  movups  xmmword ptr [rbx+68h], xmm0
0x180007758  mov     [rbx+78h], rax
0x18000775c  movups  xmmword ptr [rbx+50h], xmm0
0x180007760  mov     [rbx+60h], rax
0x180007764  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000776b  test    rax, rax
0x18000776e  jz      short loc_180007777
0x180007770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007775  jmp     short loc_18000777A
0x180007777  mov     rax, rdi
0x18000777a  mov     [rbx+80h], rax
0x180007781  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007788  test    rax, rax
0x18000778b  jz      short loc_180007795
0x18000778d  mov     rcx, rbx
0x180007790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007795  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000779c  test    rax, rax
0x18000779f  jz      short loc_1800077B7
0x1800077a1  mov     r8d, 400h
0x1800077a7  mov     rdx, [rsp+78h+arg_60]
0x1800077af  mov     rcx, rbx
0x1800077b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077b7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800077be  test    rax, rax
0x1800077c1  jz      short loc_1800077CB
0x1800077c3  mov     rcx, rbx
0x1800077c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077cb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800077d2  test    rax, rax
0x1800077d5  jz      short loc_1800077E5
0x1800077d7  test    byte ptr [rbx+4], 2
0x1800077db  jnz     short loc_1800077E5
0x1800077dd  mov     rcx, rbx
0x1800077e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077e5  cmp     [rbx+8], edi
0x1800077e8  jl      short loc_180007804
0x1800077ea  cmp     r15d, 3
0x1800077ee  jnz     loc_1800078D3
0x1800077f4  mov     ecx, 8000FFFFh; this
0x1800077f9  mov     [rbx+8], ecx
0x1800077fc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007801  mov     [rbx+0Ch], eax
0x180007804  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000780b  jnz     short loc_18000782C
0x18000780d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007814  test    rax, rax
0x180007817  jz      short loc_180007822
0x180007819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000781e  test    al, al
0x180007820  jmp     short loc_18000782A
0x180007822  call    cs:__imp_IsDebuggerPresent
0x180007828  test    eax, eax
0x18000782a  jz      short loc_180007832
0x18000782c  test    byte ptr [rbx+4], 2
0x180007830  jz      short loc_180007856
0x180007832  mov     rax, cs:g_pfnResultLoggingCallback
0x180007839  test    rax, rax
0x18000783c  jz      short loc_18000789A
0x18000783e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007845  jnz     short loc_18000789A
0x180007847  xor     r8d, r8d
0x18000784a  xor     edx, edx
0x18000784c  mov     rcx, rbx
0x18000784f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007854  jmp     short loc_18000789A
0x180007856  mov     ebp, 800h
0x18000785b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007862  test    rax, rax
0x180007865  jz      short loc_18000787E
0x180007867  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000786e  jnz     short loc_18000787E
0x180007870  mov     r8d, ebp
0x180007873  mov     rdx, rsi
0x180007876  mov     rcx, rbx
0x180007879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000787e  cmp     [rsi], di
0x180007881  jnz     short loc_180007891
0x180007883  mov     r8, rbx; unsigned __int64
0x180007886  mov     rdx, rbp; wchar_t *
0x180007889  mov     rcx, rsi; this
0x18000788c  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180007891  mov     rcx, rsi; lpOutputString
0x180007894  call    cs:__imp_OutputDebugStringW
0x18000789a  test    byte ptr [rbx+4], 4
0x18000789e  jnz     short loc_1800078A9
0x1800078a0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800078a7  jz      short loc_1800078BB
0x1800078a9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800078b0  test    rax, rax
0x1800078b3  jz      short loc_1800078BB
0x1800078b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078ba  nop
0x1800078bb  mov     rbx, [rsp+78h+arg_10]
0x1800078c3  add     rsp, 40h
0x1800078c7  pop     r15
0x1800078c9  pop     r14
0x1800078cb  pop     r13
0x1800078cd  pop     r12
0x1800078cf  pop     rdi
0x1800078d0  pop     rsi
0x1800078d1  pop     rbp
0x1800078d2  retn
0x1800078d3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
