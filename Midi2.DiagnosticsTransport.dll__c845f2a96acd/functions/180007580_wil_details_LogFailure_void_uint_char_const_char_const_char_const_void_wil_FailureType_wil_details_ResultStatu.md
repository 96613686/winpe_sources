# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007580`
- end: `0x180007879`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800049a8`

## callees

- `0x1800043ec`
- `0x180006ab4`
- `0x180007254`
- `0x180007580`
- `0x180007ef8`
- `0x180007f20`
- `0x180007f34`
- `0x180007f50`
- `0x18000a104`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800076a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800076a3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800077c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800077c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007834`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007834`

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
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x180007580  mov     [rsp+arg_10], rbx
0x180007585  mov     [rsp+arg_8], edx
0x180007589  mov     [rsp+arg_0], rcx
0x18000758e  push    rbp
0x18000758f  push    rsi
0x180007590  push    rdi
0x180007591  push    r12
0x180007593  push    r13
0x180007595  push    r14
0x180007597  push    r15
0x180007599  sub     rsp, 40h
0x18000759d  mov     r12, r9
0x1800075a0  mov     r13, r8
0x1800075a3  mov     r10, rcx
0x1800075a6  xor     eax, eax
0x1800075a8  mov     rsi, [rsp+78h+lpOutputString]
0x1800075b0  mov     [rsi], ax
0x1800075b3  mov     rax, [rsp+78h+arg_60]
0x1800075bb  mov     byte ptr [rax], 0
0x1800075be  mov     r14, [rsp+78h+arg_38]
0x1800075c6  mov     edi, [r14]
0x1800075c9  mov     rbx, [rsp+78h+arg_78]
0x1800075d1  mov     [rbx+8], edi
0x1800075d4  mov     eax, [r14+4]
0x1800075d8  mov     [rbx+0Ch], eax
0x1800075db  xor     ebp, ebp
0x1800075dd  mov     r15d, [rsp+78h+arg_30]
0x1800075e5  mov     ecx, r15d
0x1800075e8  test    r15d, r15d
0x1800075eb  jz      short loc_180007653
0x1800075ed  sub     ecx, 1
0x1800075f0  jz      short loc_18000764A
0x1800075f2  sub     ecx, 1
0x1800075f5  jz      short loc_180007605
0x1800075f7  cmp     ecx, 1
0x1800075fa  jnz     short loc_18000765C
0x1800075fc  mov     ecx, edi; this
0x1800075fe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007603  jmp     short loc_18000765A
0x180007605  test    edi, edi
0x180007607  js      short loc_180007641
0x180007609  mov     edi, 8007029Ch
0x18000760e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007612  mov     rax, [rsp+78h+arg_28]
0x18000761a  mov     [rsp+78h+var_50], rax; __int64
0x18000761f  mov     rax, [rsp+78h+arg_20]
0x180007627  mov     [rsp+78h+var_58], rax; __int64
0x18000762c  mov     rcx, r10; int
0x18000762f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007634  mov     [rbx+8], edi
0x180007637  mov     ecx, edi; this
0x180007639  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000763e  mov     [rbx+0Ch], eax
0x180007641  mov     ecx, edi; this
0x180007643  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007648  jmp     short loc_18000765A
0x18000764a  mov     ecx, edi; this
0x18000764c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007651  jmp     short loc_18000765A
0x180007653  mov     ecx, edi; this
0x180007655  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000765a  mov     ebp, eax
0x18000765c  mov     [rbx], r15d
0x18000765f  mov     eax, [rsp+78h+arg_70]
0x180007666  mov     [rbx+4], eax
0x180007669  cmp     dword ptr [r14+8], 1
0x18000766e  jnz     short loc_180007676
0x180007670  or      eax, 8
0x180007673  mov     [rbx+4], eax
0x180007676  mov     eax, 1
0x18000767b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007683  inc     eax
0x180007685  mov     [rbx+10h], eax
0x180007688  mov     rax, [rsp+78h+arg_40]
0x180007690  xor     edi, edi
0x180007692  test    rax, rax
0x180007695  jz      short loc_18000769C
0x180007697  cmp     [rax], di
0x18000769a  jnz     short loc_18000769F
0x18000769c  mov     rax, rdi
0x18000769f  mov     [rbx+18h], rax
0x1800076a3  call    cs:__imp_GetCurrentThreadId
0x1800076a9  mov     [rbx+20h], eax
0x1800076ac  mov     [rbx+38h], r13
0x1800076b0  mov     eax, [rsp+78h+arg_8]
0x1800076b7  mov     [rbx+40h], eax
0x1800076ba  mov     [rbx+44h], ebp
0x1800076bd  mov     rax, [rsp+78h+arg_20]
0x1800076c5  mov     [rbx+28h], rax
0x1800076c9  mov     [rbx+30h], r12
0x1800076cd  mov     rax, [rsp+78h+arg_28]
0x1800076d5  mov     [rbx+88h], rax
0x1800076dc  mov     rax, [rsp+78h+arg_0]
0x1800076e4  mov     [rbx+90h], rax
0x1800076eb  mov     [rbx+48h], rdi
0x1800076ef  xorps   xmm0, xmm0
0x1800076f2  xor     eax, eax
0x1800076f4  movups  xmmword ptr [rbx+68h], xmm0
0x1800076f8  mov     [rbx+78h], rax
0x1800076fc  movups  xmmword ptr [rbx+50h], xmm0
0x180007700  mov     [rbx+60h], rax
0x180007704  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000770b  test    rax, rax
0x18000770e  jz      short loc_180007717
0x180007710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007715  jmp     short loc_18000771A
0x180007717  mov     rax, rdi
0x18000771a  mov     [rbx+80h], rax
0x180007721  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007728  test    rax, rax
0x18000772b  jz      short loc_180007735
0x18000772d  mov     rcx, rbx
0x180007730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007735  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000773c  test    rax, rax
0x18000773f  jz      short loc_180007757
0x180007741  mov     r8d, 400h
0x180007747  mov     rdx, [rsp+78h+arg_60]
0x18000774f  mov     rcx, rbx
0x180007752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007757  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000775e  test    rax, rax
0x180007761  jz      short loc_18000776B
0x180007763  mov     rcx, rbx
0x180007766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000776b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007772  test    rax, rax
0x180007775  jz      short loc_180007785
0x180007777  test    byte ptr [rbx+4], 2
0x18000777b  jnz     short loc_180007785
0x18000777d  mov     rcx, rbx
0x180007780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007785  cmp     [rbx+8], edi
0x180007788  jl      short loc_1800077A4
0x18000778a  cmp     r15d, 3
0x18000778e  jnz     loc_180007873
0x180007794  mov     ecx, 8000FFFFh; this
0x180007799  mov     [rbx+8], ecx
0x18000779c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800077a1  mov     [rbx+0Ch], eax
0x1800077a4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800077ab  jnz     short loc_1800077CC
0x1800077ad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800077b4  test    rax, rax
0x1800077b7  jz      short loc_1800077C2
0x1800077b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077be  test    al, al
0x1800077c0  jmp     short loc_1800077CA
0x1800077c2  call    cs:__imp_IsDebuggerPresent
0x1800077c8  test    eax, eax
0x1800077ca  jz      short loc_1800077D2
0x1800077cc  test    byte ptr [rbx+4], 2
0x1800077d0  jz      short loc_1800077F6
0x1800077d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800077d9  test    rax, rax
0x1800077dc  jz      short loc_18000783A
0x1800077de  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800077e5  jnz     short loc_18000783A
0x1800077e7  xor     r8d, r8d
0x1800077ea  xor     edx, edx
0x1800077ec  mov     rcx, rbx
0x1800077ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077f4  jmp     short loc_18000783A
0x1800077f6  mov     ebp, 800h
0x1800077fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180007802  test    rax, rax
0x180007805  jz      short loc_18000781E
0x180007807  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000780e  jnz     short loc_18000781E
0x180007810  mov     r8d, ebp
0x180007813  mov     rdx, rsi
0x180007816  mov     rcx, rbx
0x180007819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000781e  cmp     [rsi], di
0x180007821  jnz     short loc_180007831
0x180007823  mov     r8, rbx; unsigned __int64
0x180007826  mov     rdx, rbp; unsigned __int16 *
0x180007829  mov     rcx, rsi; this
0x18000782c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007831  mov     rcx, rsi; lpOutputString
0x180007834  call    cs:__imp_OutputDebugStringW
0x18000783a  test    byte ptr [rbx+4], 4
0x18000783e  jnz     short loc_180007849
0x180007840  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007847  jz      short loc_18000785B
0x180007849  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007850  test    rax, rax
0x180007853  jz      short loc_18000785B
0x180007855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000785a  nop
0x18000785b  mov     rbx, [rsp+78h+arg_10]
0x180007863  add     rsp, 40h
0x180007867  pop     r15
0x180007869  pop     r14
0x18000786b  pop     r13
0x18000786d  pop     r12
0x18000786f  pop     rdi
0x180007870  pop     rsi
0x180007871  pop     rbp
0x180007872  retn
0x180007873  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
