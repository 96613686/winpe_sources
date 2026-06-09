# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800055ac`
- end: `0x1800058a4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180003c28`
- `0x180003f6c`

## callees

- `0x180003b68`
- `0x180004b24`
- `0x180005344`
- `0x1800055ac`
- `0x180005c74`
- `0x180005c90`
- `0x180005ca4`
- `0x180005cc0`
- `0x180006ba4`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056cf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800057ee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800057ee`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005860`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005860`

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
0x1800055ac  mov     [rsp+arg_10], rbx
0x1800055b1  mov     [rsp+arg_8], edx
0x1800055b5  mov     [rsp+arg_0], rcx
0x1800055ba  push    rbp
0x1800055bb  push    rsi
0x1800055bc  push    rdi
0x1800055bd  push    r12
0x1800055bf  push    r13
0x1800055c1  push    r14
0x1800055c3  push    r15
0x1800055c5  sub     rsp, 40h
0x1800055c9  mov     r14, [rsp+78h+arg_38]
0x1800055d1  xor     eax, eax
0x1800055d3  mov     rbx, [rsp+78h+arg_78]
0x1800055db  xor     ebp, ebp
0x1800055dd  mov     r15d, [rsp+78h+arg_30]
0x1800055e5  mov     r10, rcx
0x1800055e8  mov     rsi, [rsp+78h+lpOutputString]
0x1800055f0  mov     r12, r9
0x1800055f3  mov     r13, r8
0x1800055f6  mov     ecx, r15d
0x1800055f9  mov     [rsi], ax
0x1800055fc  mov     rax, [rsp+78h+arg_60]
0x180005604  mov     byte ptr [rax], 0
0x180005607  mov     edi, [r14]
0x18000560a  mov     [rbx+8], edi
0x18000560d  mov     eax, [r14+4]
0x180005611  mov     [rbx+0Ch], eax
0x180005614  test    r15d, r15d
0x180005617  jz      short loc_18000567F
0x180005619  sub     ecx, 1
0x18000561c  jz      short loc_180005676
0x18000561e  sub     ecx, 1
0x180005621  jz      short loc_180005631
0x180005623  cmp     ecx, 1
0x180005626  jnz     short loc_180005688
0x180005628  mov     ecx, edi; this
0x18000562a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000562f  jmp     short loc_180005686
0x180005631  test    edi, edi
0x180005633  js      short loc_18000566D
0x180005635  mov     rax, [rsp+78h+arg_28]
0x18000563d  mov     edi, 8007029Ch
0x180005642  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005646  mov     rcx, r10; int
0x180005649  mov     [rsp+78h+var_50], rax; __int64
0x18000564e  mov     rax, [rsp+78h+arg_20]
0x180005656  mov     [rsp+78h+var_58], rax; __int64
0x18000565b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005660  mov     ecx, edi; this
0x180005662  mov     [rbx+8], edi
0x180005665  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000566a  mov     [rbx+0Ch], eax
0x18000566d  mov     ecx, edi; this
0x18000566f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005674  jmp     short loc_180005686
0x180005676  mov     ecx, edi; this
0x180005678  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000567d  jmp     short loc_180005686
0x18000567f  mov     ecx, edi; this
0x180005681  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005686  mov     ebp, eax
0x180005688  mov     eax, [rsp+78h+arg_70]
0x18000568f  mov     [rbx+4], eax
0x180005692  mov     [rbx], r15d
0x180005695  cmp     dword ptr [r14+8], 1
0x18000569a  jnz     short loc_1800056A2
0x18000569c  or      eax, 8
0x18000569f  mov     [rbx+4], eax
0x1800056a2  mov     eax, 1
0x1800056a7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800056af  inc     eax
0x1800056b1  xor     edi, edi
0x1800056b3  mov     [rbx+10h], eax
0x1800056b6  mov     rax, [rsp+78h+arg_40]
0x1800056be  test    rax, rax
0x1800056c1  jz      short loc_1800056C8
0x1800056c3  cmp     [rax], di
0x1800056c6  jnz     short loc_1800056CB
0x1800056c8  mov     rax, rdi
0x1800056cb  mov     [rbx+18h], rax
0x1800056cf  call    cs:__imp_GetCurrentThreadId
0x1800056d5  mov     [rbx+38h], r13
0x1800056d9  xorps   xmm0, xmm0
0x1800056dc  mov     [rbx+20h], eax
0x1800056df  mov     eax, [rsp+78h+arg_8]
0x1800056e6  mov     [rbx+40h], eax
0x1800056e9  mov     rax, [rsp+78h+arg_20]
0x1800056f1  mov     [rbx+28h], rax
0x1800056f5  mov     rax, [rsp+78h+arg_28]
0x1800056fd  mov     [rbx+88h], rax
0x180005704  mov     rax, [rsp+78h+arg_0]
0x18000570c  mov     [rbx+90h], rax
0x180005713  xor     eax, eax
0x180005715  mov     [rbx+44h], ebp
0x180005718  mov     [rbx+30h], r12
0x18000571c  mov     [rbx+48h], rdi
0x180005720  movups  xmmword ptr [rbx+68h], xmm0
0x180005724  mov     [rbx+78h], rax
0x180005728  movups  xmmword ptr [rbx+50h], xmm0
0x18000572c  mov     [rbx+60h], rax
0x180005730  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005737  test    rax, rax
0x18000573a  jz      short loc_180005743
0x18000573c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005741  jmp     short loc_180005746
0x180005743  mov     rax, rdi
0x180005746  mov     [rbx+80h], rax
0x18000574d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005754  test    rax, rax
0x180005757  jz      short loc_180005761
0x180005759  mov     rcx, rbx
0x18000575c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005761  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005768  test    rax, rax
0x18000576b  jz      short loc_180005783
0x18000576d  mov     rdx, [rsp+78h+arg_60]
0x180005775  mov     r8d, 400h
0x18000577b  mov     rcx, rbx
0x18000577e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005783  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000578a  test    rax, rax
0x18000578d  jz      short loc_180005797
0x18000578f  mov     rcx, rbx
0x180005792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005797  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000579e  test    rax, rax
0x1800057a1  jz      short loc_1800057B1
0x1800057a3  test    byte ptr [rbx+4], 2
0x1800057a7  jnz     short loc_1800057B1
0x1800057a9  mov     rcx, rbx
0x1800057ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b1  cmp     [rbx+8], edi
0x1800057b4  jl      short loc_1800057D0
0x1800057b6  cmp     r15d, 3
0x1800057ba  jnz     loc_18000589E
0x1800057c0  mov     ecx, 8000FFFFh; this
0x1800057c5  mov     [rbx+8], ecx
0x1800057c8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800057cd  mov     [rbx+0Ch], eax
0x1800057d0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800057d7  jnz     short loc_1800057F8
0x1800057d9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800057e0  test    rax, rax
0x1800057e3  jz      short loc_1800057EE
0x1800057e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ea  test    al, al
0x1800057ec  jmp     short loc_1800057F6
0x1800057ee  call    cs:__imp_IsDebuggerPresent
0x1800057f4  test    eax, eax
0x1800057f6  jz      short loc_1800057FE
0x1800057f8  test    byte ptr [rbx+4], 2
0x1800057fc  jz      short loc_180005822
0x1800057fe  mov     rax, cs:g_pfnResultLoggingCallback
0x180005805  test    rax, rax
0x180005808  jz      short loc_180005866
0x18000580a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005811  jnz     short loc_180005866
0x180005813  xor     r8d, r8d
0x180005816  xor     edx, edx
0x180005818  mov     rcx, rbx
0x18000581b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005820  jmp     short loc_180005866
0x180005822  mov     rax, cs:g_pfnResultLoggingCallback
0x180005829  mov     ebp, 800h
0x18000582e  test    rax, rax
0x180005831  jz      short loc_18000584A
0x180005833  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000583a  jnz     short loc_18000584A
0x18000583c  mov     r8d, ebp
0x18000583f  mov     rdx, rsi
0x180005842  mov     rcx, rbx
0x180005845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000584a  cmp     [rsi], di
0x18000584d  jnz     short loc_18000585D
0x18000584f  mov     r8, rbx; unsigned __int64
0x180005852  mov     rdx, rbp; unsigned __int16 *
0x180005855  mov     rcx, rsi; this
0x180005858  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000585d  mov     rcx, rsi; lpOutputString
0x180005860  call    cs:__imp_OutputDebugStringW
0x180005866  test    byte ptr [rbx+4], 4
0x18000586a  jnz     short loc_180005875
0x18000586c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005873  jz      short loc_180005886
0x180005875  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000587c  test    rax, rax
0x18000587f  jz      short loc_180005886
0x180005881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005886  mov     rbx, [rsp+78h+arg_10]
0x18000588e  add     rsp, 40h
0x180005892  pop     r15
0x180005894  pop     r14
0x180005896  pop     r13
0x180005898  pop     r12
0x18000589a  pop     rdi
0x18000589b  pop     rsi
0x18000589c  pop     rbp
0x18000589d  retn
0x18000589e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
