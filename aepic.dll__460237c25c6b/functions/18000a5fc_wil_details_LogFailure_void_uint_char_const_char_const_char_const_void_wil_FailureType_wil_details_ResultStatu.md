# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a5fc`
- end: `0x18000a8f1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180007b68`
- `0x180007c18`
- `0x180007d08`
- `0x1800c1b54`

## callees

- `0x180007ab8`
- `0x180009a84`
- `0x18000a110`
- `0x18000a5fc`
- `0x18000b5dc`
- `0x18000b600`
- `0x18000b878`
- `0x18000b894`
- `0x18000d888`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a71f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a71f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a8b2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a8b2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a840`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a840`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
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
0x18000a5fc  mov     [rsp+arg_10], rbx
0x18000a601  mov     [rsp+arg_8], edx
0x18000a605  mov     [rsp+arg_0], rcx
0x18000a60a  push    rbp
0x18000a60b  push    rsi
0x18000a60c  push    rdi
0x18000a60d  push    r12
0x18000a60f  push    r13
0x18000a611  push    r14
0x18000a613  push    r15
0x18000a615  sub     rsp, 40h
0x18000a619  mov     r12, r9
0x18000a61c  mov     r13, r8
0x18000a61f  mov     r10, rcx
0x18000a622  xor     eax, eax
0x18000a624  mov     rsi, [rsp+78h+lpOutputString]
0x18000a62c  mov     [rsi], ax
0x18000a62f  mov     rax, [rsp+78h+arg_60]
0x18000a637  mov     byte ptr [rax], 0
0x18000a63a  mov     r14, [rsp+78h+arg_38]
0x18000a642  mov     edi, [r14]
0x18000a645  mov     rbx, [rsp+78h+arg_78]
0x18000a64d  mov     [rbx+8], edi
0x18000a650  mov     eax, [r14+4]
0x18000a654  mov     [rbx+0Ch], eax
0x18000a657  xor     ebp, ebp
0x18000a659  mov     r15d, [rsp+78h+arg_30]
0x18000a661  mov     ecx, r15d
0x18000a664  test    r15d, r15d
0x18000a667  jz      short loc_18000A6CF
0x18000a669  sub     ecx, 1
0x18000a66c  jz      short loc_18000A6C6
0x18000a66e  sub     ecx, 1
0x18000a671  jz      short loc_18000A681
0x18000a673  cmp     ecx, 1
0x18000a676  jnz     short loc_18000A6D8
0x18000a678  mov     ecx, edi; this
0x18000a67a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a67f  jmp     short loc_18000A6D6
0x18000a681  test    edi, edi
0x18000a683  js      short loc_18000A6BD
0x18000a685  mov     edi, 8007029Ch
0x18000a68a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a68e  mov     rax, [rsp+78h+arg_28]
0x18000a696  mov     [rsp+78h+var_50], rax; __int64
0x18000a69b  mov     rax, [rsp+78h+arg_20]
0x18000a6a3  mov     [rsp+78h+var_58], rax; __int64
0x18000a6a8  mov     rcx, r10; int
0x18000a6ab  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a6b0  mov     [rbx+8], edi
0x18000a6b3  mov     ecx, edi; this
0x18000a6b5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a6ba  mov     [rbx+0Ch], eax
0x18000a6bd  mov     ecx, edi; this
0x18000a6bf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a6c4  jmp     short loc_18000A6D6
0x18000a6c6  mov     ecx, edi; this
0x18000a6c8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a6cd  jmp     short loc_18000A6D6
0x18000a6cf  mov     ecx, edi; this
0x18000a6d1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a6d6  mov     ebp, eax
0x18000a6d8  mov     [rbx], r15d
0x18000a6db  mov     eax, [rsp+78h+arg_70]
0x18000a6e2  mov     [rbx+4], eax
0x18000a6e5  cmp     dword ptr [r14+8], 1
0x18000a6ea  jnz     short loc_18000A6F2
0x18000a6ec  or      eax, 8
0x18000a6ef  mov     [rbx+4], eax
0x18000a6f2  mov     eax, 1
0x18000a6f7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a6ff  inc     eax
0x18000a701  mov     [rbx+10h], eax
0x18000a704  mov     rax, [rsp+78h+arg_40]
0x18000a70c  xor     edi, edi
0x18000a70e  test    rax, rax
0x18000a711  jz      short loc_18000A718
0x18000a713  cmp     [rax], di
0x18000a716  jnz     short loc_18000A71B
0x18000a718  mov     rax, rdi
0x18000a71b  mov     [rbx+18h], rax
0x18000a71f  call    cs:__imp_GetCurrentThreadId
0x18000a725  mov     [rbx+20h], eax
0x18000a728  mov     [rbx+38h], r13
0x18000a72c  mov     eax, [rsp+78h+arg_8]
0x18000a733  mov     [rbx+40h], eax
0x18000a736  mov     [rbx+44h], ebp
0x18000a739  mov     rax, [rsp+78h+arg_20]
0x18000a741  mov     [rbx+28h], rax
0x18000a745  mov     [rbx+30h], r12
0x18000a749  mov     rax, [rsp+78h+arg_28]
0x18000a751  mov     [rbx+88h], rax
0x18000a758  mov     rax, [rsp+78h+arg_0]
0x18000a760  mov     [rbx+90h], rax
0x18000a767  mov     [rbx+48h], rdi
0x18000a76b  xorps   xmm0, xmm0
0x18000a76e  xor     eax, eax
0x18000a770  movups  xmmword ptr [rbx+68h], xmm0
0x18000a774  mov     [rbx+78h], rax
0x18000a778  movups  xmmword ptr [rbx+50h], xmm0
0x18000a77c  mov     [rbx+60h], rax
0x18000a780  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a787  test    rax, rax
0x18000a78a  jz      short loc_18000A793
0x18000a78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a791  jmp     short loc_18000A796
0x18000a793  mov     rax, rdi
0x18000a796  mov     [rbx+80h], rax
0x18000a79d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a7a4  test    rax, rax
0x18000a7a7  jz      short loc_18000A7B1
0x18000a7a9  mov     rcx, rbx
0x18000a7ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7b1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a7b8  test    rax, rax
0x18000a7bb  jz      short loc_18000A7D3
0x18000a7bd  mov     r8d, 400h
0x18000a7c3  mov     rdx, [rsp+78h+arg_60]
0x18000a7cb  mov     rcx, rbx
0x18000a7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7d3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a7da  test    rax, rax
0x18000a7dd  jz      short loc_18000A7E7
0x18000a7df  mov     rcx, rbx
0x18000a7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7e7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a7ee  test    rax, rax
0x18000a7f1  jz      short loc_18000A801
0x18000a7f3  test    byte ptr [rbx+4], 2
0x18000a7f7  jnz     short loc_18000A801
0x18000a7f9  mov     rcx, rbx
0x18000a7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a801  cmp     [rbx+8], edi
0x18000a804  jl      short loc_18000A822
0x18000a806  cmp     r15d, 3
0x18000a80a  jz      short loc_18000A812
0x18000a80c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a812  mov     ecx, 8000FFFFh; this
0x18000a817  mov     [rbx+8], ecx
0x18000a81a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a81f  mov     [rbx+0Ch], eax
0x18000a822  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a829  jnz     short loc_18000A84A
0x18000a82b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a832  test    rax, rax
0x18000a835  jz      short loc_18000A840
0x18000a837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a83c  test    al, al
0x18000a83e  jmp     short loc_18000A848
0x18000a840  call    cs:__imp_IsDebuggerPresent
0x18000a846  test    eax, eax
0x18000a848  jz      short loc_18000A850
0x18000a84a  test    byte ptr [rbx+4], 2
0x18000a84e  jz      short loc_18000A874
0x18000a850  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a857  test    rax, rax
0x18000a85a  jz      short loc_18000A8B8
0x18000a85c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a863  jnz     short loc_18000A8B8
0x18000a865  xor     r8d, r8d
0x18000a868  xor     edx, edx
0x18000a86a  mov     rcx, rbx
0x18000a86d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a872  jmp     short loc_18000A8B8
0x18000a874  mov     ebp, 800h
0x18000a879  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a880  test    rax, rax
0x18000a883  jz      short loc_18000A89C
0x18000a885  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a88c  jnz     short loc_18000A89C
0x18000a88e  mov     r8d, ebp
0x18000a891  mov     rdx, rsi
0x18000a894  mov     rcx, rbx
0x18000a897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a89c  cmp     [rsi], di
0x18000a89f  jnz     short loc_18000A8AF
0x18000a8a1  mov     r8, rbx; unsigned __int64
0x18000a8a4  mov     rdx, rbp; unsigned __int16 *
0x18000a8a7  mov     rcx, rsi; this
0x18000a8aa  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a8af  mov     rcx, rsi; lpOutputString
0x18000a8b2  call    cs:__imp_OutputDebugStringW
0x18000a8b8  test    byte ptr [rbx+4], 4
0x18000a8bc  jnz     short loc_18000A8C7
0x18000a8be  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a8c5  jz      short loc_18000A8D9
0x18000a8c7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a8ce  test    rax, rax
0x18000a8d1  jz      short loc_18000A8D9
0x18000a8d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8d8  nop
0x18000a8d9  mov     rbx, [rsp+78h+arg_10]
0x18000a8e1  add     rsp, 40h
0x18000a8e5  pop     r15
0x18000a8e7  pop     r14
0x18000a8e9  pop     r13
0x18000a8eb  pop     r12
0x18000a8ed  pop     rdi
0x18000a8ee  pop     rsi
0x18000a8ef  pop     rbp
0x18000a8f0  retn
```
