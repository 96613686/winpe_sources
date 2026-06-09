# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180012640`
- end: `0x180012938`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180011164`

## callees

- `0x180010ba0`
- `0x180011ce4`
- `0x18001247c`
- `0x180012640`
- `0x180012bd4`
- `0x180012bf0`
- `0x180012c04`
- `0x180012c20`
- `0x18001344c`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180012763`
- `KERNEL32!GetCurrentThreadId` at `0x180012763`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012882`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012882`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800128f4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800128f4`

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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x180012640  mov     [rsp+arg_10], rbx
0x180012645  mov     [rsp+arg_8], edx
0x180012649  mov     [rsp+arg_0], rcx
0x18001264e  push    rbp
0x18001264f  push    rsi
0x180012650  push    rdi
0x180012651  push    r12
0x180012653  push    r13
0x180012655  push    r14
0x180012657  push    r15
0x180012659  sub     rsp, 40h
0x18001265d  mov     r14, [rsp+78h+arg_38]
0x180012665  xor     eax, eax
0x180012667  mov     rbx, [rsp+78h+arg_78]
0x18001266f  xor     ebp, ebp
0x180012671  mov     r15d, [rsp+78h+arg_30]
0x180012679  mov     r10, rcx
0x18001267c  mov     rsi, [rsp+78h+lpOutputString]
0x180012684  mov     r12, r9
0x180012687  mov     r13, r8
0x18001268a  mov     ecx, r15d
0x18001268d  mov     [rsi], ax
0x180012690  mov     rax, [rsp+78h+arg_60]
0x180012698  mov     byte ptr [rax], 0
0x18001269b  mov     edi, [r14]
0x18001269e  mov     [rbx+8], edi
0x1800126a1  mov     eax, [r14+4]
0x1800126a5  mov     [rbx+0Ch], eax
0x1800126a8  test    r15d, r15d
0x1800126ab  jz      short loc_180012713
0x1800126ad  sub     ecx, 1
0x1800126b0  jz      short loc_18001270A
0x1800126b2  sub     ecx, 1
0x1800126b5  jz      short loc_1800126C5
0x1800126b7  cmp     ecx, 1
0x1800126ba  jnz     short loc_18001271C
0x1800126bc  mov     ecx, edi; this
0x1800126be  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800126c3  jmp     short loc_18001271A
0x1800126c5  test    edi, edi
0x1800126c7  js      short loc_180012701
0x1800126c9  mov     rax, [rsp+78h+arg_28]
0x1800126d1  mov     edi, 8007029Ch
0x1800126d6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800126da  mov     rcx, r10; int
0x1800126dd  mov     [rsp+78h+var_50], rax; __int64
0x1800126e2  mov     rax, [rsp+78h+arg_20]
0x1800126ea  mov     [rsp+78h+var_58], rax; __int64
0x1800126ef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800126f4  mov     ecx, edi; this
0x1800126f6  mov     [rbx+8], edi
0x1800126f9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800126fe  mov     [rbx+0Ch], eax
0x180012701  mov     ecx, edi; this
0x180012703  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180012708  jmp     short loc_18001271A
0x18001270a  mov     ecx, edi; this
0x18001270c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180012711  jmp     short loc_18001271A
0x180012713  mov     ecx, edi; this
0x180012715  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001271a  mov     ebp, eax
0x18001271c  mov     eax, [rsp+78h+arg_70]
0x180012723  mov     [rbx+4], eax
0x180012726  mov     [rbx], r15d
0x180012729  cmp     dword ptr [r14+8], 1
0x18001272e  jnz     short loc_180012736
0x180012730  or      eax, 8
0x180012733  mov     [rbx+4], eax
0x180012736  mov     eax, 1
0x18001273b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180012743  inc     eax
0x180012745  xor     edi, edi
0x180012747  mov     [rbx+10h], eax
0x18001274a  mov     rax, [rsp+78h+arg_40]
0x180012752  test    rax, rax
0x180012755  jz      short loc_18001275C
0x180012757  cmp     [rax], di
0x18001275a  jnz     short loc_18001275F
0x18001275c  mov     rax, rdi
0x18001275f  mov     [rbx+18h], rax
0x180012763  call    cs:__imp_GetCurrentThreadId
0x180012769  mov     [rbx+38h], r13
0x18001276d  xorps   xmm0, xmm0
0x180012770  mov     [rbx+20h], eax
0x180012773  mov     eax, [rsp+78h+arg_8]
0x18001277a  mov     [rbx+40h], eax
0x18001277d  mov     rax, [rsp+78h+arg_20]
0x180012785  mov     [rbx+28h], rax
0x180012789  mov     rax, [rsp+78h+arg_28]
0x180012791  mov     [rbx+88h], rax
0x180012798  mov     rax, [rsp+78h+arg_0]
0x1800127a0  mov     [rbx+90h], rax
0x1800127a7  xor     eax, eax
0x1800127a9  mov     [rbx+44h], ebp
0x1800127ac  mov     [rbx+30h], r12
0x1800127b0  mov     [rbx+48h], rdi
0x1800127b4  movups  xmmword ptr [rbx+68h], xmm0
0x1800127b8  mov     [rbx+78h], rax
0x1800127bc  movups  xmmword ptr [rbx+50h], xmm0
0x1800127c0  mov     [rbx+60h], rax
0x1800127c4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800127cb  test    rax, rax
0x1800127ce  jz      short loc_1800127D7
0x1800127d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127d5  jmp     short loc_1800127DA
0x1800127d7  mov     rax, rdi
0x1800127da  mov     [rbx+80h], rax
0x1800127e1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800127e8  test    rax, rax
0x1800127eb  jz      short loc_1800127F5
0x1800127ed  mov     rcx, rbx
0x1800127f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127f5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800127fc  test    rax, rax
0x1800127ff  jz      short loc_180012817
0x180012801  mov     rdx, [rsp+78h+arg_60]
0x180012809  mov     r8d, 400h
0x18001280f  mov     rcx, rbx
0x180012812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012817  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001281e  test    rax, rax
0x180012821  jz      short loc_18001282B
0x180012823  mov     rcx, rbx
0x180012826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001282b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012832  test    rax, rax
0x180012835  jz      short loc_180012845
0x180012837  test    byte ptr [rbx+4], 2
0x18001283b  jnz     short loc_180012845
0x18001283d  mov     rcx, rbx
0x180012840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012845  cmp     [rbx+8], edi
0x180012848  jl      short loc_180012864
0x18001284a  cmp     r15d, 3
0x18001284e  jnz     loc_180012932
0x180012854  mov     ecx, 8000FFFFh; this
0x180012859  mov     [rbx+8], ecx
0x18001285c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180012861  mov     [rbx+0Ch], eax
0x180012864  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001286b  jnz     short loc_18001288C
0x18001286d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180012874  test    rax, rax
0x180012877  jz      short loc_180012882
0x180012879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001287e  test    al, al
0x180012880  jmp     short loc_18001288A
0x180012882  call    cs:__imp_IsDebuggerPresent
0x180012888  test    eax, eax
0x18001288a  jz      short loc_180012892
0x18001288c  test    byte ptr [rbx+4], 2
0x180012890  jz      short loc_1800128B6
0x180012892  mov     rax, cs:g_pfnResultLoggingCallback
0x180012899  test    rax, rax
0x18001289c  jz      short loc_1800128FA
0x18001289e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800128a5  jnz     short loc_1800128FA
0x1800128a7  xor     r8d, r8d
0x1800128aa  xor     edx, edx
0x1800128ac  mov     rcx, rbx
0x1800128af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128b4  jmp     short loc_1800128FA
0x1800128b6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800128bd  mov     ebp, 800h
0x1800128c2  test    rax, rax
0x1800128c5  jz      short loc_1800128DE
0x1800128c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800128ce  jnz     short loc_1800128DE
0x1800128d0  mov     r8d, ebp
0x1800128d3  mov     rdx, rsi
0x1800128d6  mov     rcx, rbx
0x1800128d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128de  cmp     [rsi], di
0x1800128e1  jnz     short loc_1800128F1
0x1800128e3  mov     r8, rbx; unsigned __int64
0x1800128e6  mov     rdx, rbp; unsigned __int16 *
0x1800128e9  mov     rcx, rsi; this
0x1800128ec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800128f1  mov     rcx, rsi; lpOutputString
0x1800128f4  call    cs:__imp_OutputDebugStringW
0x1800128fa  test    byte ptr [rbx+4], 4
0x1800128fe  jnz     short loc_180012909
0x180012900  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180012907  jz      short loc_18001291A
0x180012909  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180012910  test    rax, rax
0x180012913  jz      short loc_18001291A
0x180012915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001291a  mov     rbx, [rsp+78h+arg_10]
0x180012922  add     rsp, 40h
0x180012926  pop     r15
0x180012928  pop     r14
0x18001292a  pop     r13
0x18001292c  pop     r12
0x18001292e  pop     rdi
0x18001292f  pop     rsi
0x180012930  pop     rbp
0x180012931  retn
0x180012932  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
