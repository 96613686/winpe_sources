# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18002b400`
- end: `0x18002b6f9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180027878`

## callees

- `0x1800272bc`
- `0x18002a784`
- `0x18002afc8`
- `0x18002b400`
- `0x18002c784`
- `0x18002c7a0`
- `0x18002c8cc`
- `0x18002c8e8`
- `0x18002febc`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b523`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b523`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002b642`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002b642`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002b6b4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002b6b4`

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
0x18002b400  mov     [rsp+arg_10], rbx
0x18002b405  mov     [rsp+arg_8], edx
0x18002b409  mov     [rsp+arg_0], rcx
0x18002b40e  push    rbp
0x18002b40f  push    rsi
0x18002b410  push    rdi
0x18002b411  push    r12
0x18002b413  push    r13
0x18002b415  push    r14
0x18002b417  push    r15
0x18002b419  sub     rsp, 40h
0x18002b41d  mov     r12, r9
0x18002b420  mov     r13, r8
0x18002b423  mov     r10, rcx
0x18002b426  xor     eax, eax
0x18002b428  mov     rsi, [rsp+78h+lpOutputString]
0x18002b430  mov     [rsi], ax
0x18002b433  mov     rax, [rsp+78h+arg_60]
0x18002b43b  mov     byte ptr [rax], 0
0x18002b43e  mov     r14, [rsp+78h+arg_38]
0x18002b446  mov     edi, [r14]
0x18002b449  mov     rbx, [rsp+78h+arg_78]
0x18002b451  mov     [rbx+8], edi
0x18002b454  mov     eax, [r14+4]
0x18002b458  mov     [rbx+0Ch], eax
0x18002b45b  xor     ebp, ebp
0x18002b45d  mov     r15d, [rsp+78h+arg_30]
0x18002b465  mov     ecx, r15d
0x18002b468  test    r15d, r15d
0x18002b46b  jz      short loc_18002B4D3
0x18002b46d  sub     ecx, 1
0x18002b470  jz      short loc_18002B4CA
0x18002b472  sub     ecx, 1
0x18002b475  jz      short loc_18002B485
0x18002b477  cmp     ecx, 1
0x18002b47a  jnz     short loc_18002B4DC
0x18002b47c  mov     ecx, edi; this
0x18002b47e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002b483  jmp     short loc_18002B4DA
0x18002b485  test    edi, edi
0x18002b487  js      short loc_18002B4C1
0x18002b489  mov     edi, 8007029Ch
0x18002b48e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18002b492  mov     rax, [rsp+78h+arg_28]
0x18002b49a  mov     [rsp+78h+var_50], rax; __int64
0x18002b49f  mov     rax, [rsp+78h+arg_20]
0x18002b4a7  mov     [rsp+78h+var_58], rax; __int64
0x18002b4ac  mov     rcx, r10; int
0x18002b4af  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002b4b4  mov     [rbx+8], edi
0x18002b4b7  mov     ecx, edi; this
0x18002b4b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002b4be  mov     [rbx+0Ch], eax
0x18002b4c1  mov     ecx, edi; this
0x18002b4c3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18002b4c8  jmp     short loc_18002B4DA
0x18002b4ca  mov     ecx, edi; this
0x18002b4cc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002b4d1  jmp     short loc_18002B4DA
0x18002b4d3  mov     ecx, edi; this
0x18002b4d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002b4da  mov     ebp, eax
0x18002b4dc  mov     [rbx], r15d
0x18002b4df  mov     eax, [rsp+78h+arg_70]
0x18002b4e6  mov     [rbx+4], eax
0x18002b4e9  cmp     dword ptr [r14+8], 1
0x18002b4ee  jnz     short loc_18002B4F6
0x18002b4f0  or      eax, 8
0x18002b4f3  mov     [rbx+4], eax
0x18002b4f6  mov     eax, 1
0x18002b4fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002b503  inc     eax
0x18002b505  mov     [rbx+10h], eax
0x18002b508  mov     rax, [rsp+78h+arg_40]
0x18002b510  xor     edi, edi
0x18002b512  test    rax, rax
0x18002b515  jz      short loc_18002B51C
0x18002b517  cmp     [rax], di
0x18002b51a  jnz     short loc_18002B51F
0x18002b51c  mov     rax, rdi
0x18002b51f  mov     [rbx+18h], rax
0x18002b523  call    cs:__imp_GetCurrentThreadId
0x18002b529  mov     [rbx+20h], eax
0x18002b52c  mov     [rbx+38h], r13
0x18002b530  mov     eax, [rsp+78h+arg_8]
0x18002b537  mov     [rbx+40h], eax
0x18002b53a  mov     [rbx+44h], ebp
0x18002b53d  mov     rax, [rsp+78h+arg_20]
0x18002b545  mov     [rbx+28h], rax
0x18002b549  mov     [rbx+30h], r12
0x18002b54d  mov     rax, [rsp+78h+arg_28]
0x18002b555  mov     [rbx+88h], rax
0x18002b55c  mov     rax, [rsp+78h+arg_0]
0x18002b564  mov     [rbx+90h], rax
0x18002b56b  mov     [rbx+48h], rdi
0x18002b56f  xorps   xmm0, xmm0
0x18002b572  xor     eax, eax
0x18002b574  movups  xmmword ptr [rbx+68h], xmm0
0x18002b578  mov     [rbx+78h], rax
0x18002b57c  movups  xmmword ptr [rbx+50h], xmm0
0x18002b580  mov     [rbx+60h], rax
0x18002b584  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002b58b  test    rax, rax
0x18002b58e  jz      short loc_18002B597
0x18002b590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b595  jmp     short loc_18002B59A
0x18002b597  mov     rax, rdi
0x18002b59a  mov     [rbx+80h], rax
0x18002b5a1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002b5a8  test    rax, rax
0x18002b5ab  jz      short loc_18002B5B5
0x18002b5ad  mov     rcx, rbx
0x18002b5b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5b5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002b5bc  test    rax, rax
0x18002b5bf  jz      short loc_18002B5D7
0x18002b5c1  mov     r8d, 400h
0x18002b5c7  mov     rdx, [rsp+78h+arg_60]
0x18002b5cf  mov     rcx, rbx
0x18002b5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5d7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002b5de  test    rax, rax
0x18002b5e1  jz      short loc_18002B5EB
0x18002b5e3  mov     rcx, rbx
0x18002b5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5eb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002b5f2  test    rax, rax
0x18002b5f5  jz      short loc_18002B605
0x18002b5f7  test    byte ptr [rbx+4], 2
0x18002b5fb  jnz     short loc_18002B605
0x18002b5fd  mov     rcx, rbx
0x18002b600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b605  cmp     [rbx+8], edi
0x18002b608  jl      short loc_18002B624
0x18002b60a  cmp     r15d, 3
0x18002b60e  jnz     loc_18002B6F3
0x18002b614  mov     ecx, 8000FFFFh; this
0x18002b619  mov     [rbx+8], ecx
0x18002b61c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002b621  mov     [rbx+0Ch], eax
0x18002b624  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002b62b  jnz     short loc_18002B64C
0x18002b62d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002b634  test    rax, rax
0x18002b637  jz      short loc_18002B642
0x18002b639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b63e  test    al, al
0x18002b640  jmp     short loc_18002B64A
0x18002b642  call    cs:__imp_IsDebuggerPresent
0x18002b648  test    eax, eax
0x18002b64a  jz      short loc_18002B652
0x18002b64c  test    byte ptr [rbx+4], 2
0x18002b650  jz      short loc_18002B676
0x18002b652  mov     rax, cs:g_pfnResultLoggingCallback
0x18002b659  test    rax, rax
0x18002b65c  jz      short loc_18002B6BA
0x18002b65e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002b665  jnz     short loc_18002B6BA
0x18002b667  xor     r8d, r8d
0x18002b66a  xor     edx, edx
0x18002b66c  mov     rcx, rbx
0x18002b66f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b674  jmp     short loc_18002B6BA
0x18002b676  mov     ebp, 800h
0x18002b67b  mov     rax, cs:g_pfnResultLoggingCallback
0x18002b682  test    rax, rax
0x18002b685  jz      short loc_18002B69E
0x18002b687  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002b68e  jnz     short loc_18002B69E
0x18002b690  mov     r8d, ebp
0x18002b693  mov     rdx, rsi
0x18002b696  mov     rcx, rbx
0x18002b699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b69e  cmp     [rsi], di
0x18002b6a1  jnz     short loc_18002B6B1
0x18002b6a3  mov     r8, rbx; unsigned __int64
0x18002b6a6  mov     rdx, rbp; unsigned __int16 *
0x18002b6a9  mov     rcx, rsi; this
0x18002b6ac  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002b6b1  mov     rcx, rsi; lpOutputString
0x18002b6b4  call    cs:__imp_OutputDebugStringW
0x18002b6ba  test    byte ptr [rbx+4], 4
0x18002b6be  jnz     short loc_18002B6C9
0x18002b6c0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18002b6c7  jz      short loc_18002B6DB
0x18002b6c9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002b6d0  test    rax, rax
0x18002b6d3  jz      short loc_18002B6DB
0x18002b6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6da  nop
0x18002b6db  mov     rbx, [rsp+78h+arg_10]
0x18002b6e3  add     rsp, 40h
0x18002b6e7  pop     r15
0x18002b6e9  pop     r14
0x18002b6eb  pop     r13
0x18002b6ed  pop     r12
0x18002b6ef  pop     rdi
0x18002b6f0  pop     rsi
0x18002b6f1  pop     rbp
0x18002b6f2  retn
0x18002b6f3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
