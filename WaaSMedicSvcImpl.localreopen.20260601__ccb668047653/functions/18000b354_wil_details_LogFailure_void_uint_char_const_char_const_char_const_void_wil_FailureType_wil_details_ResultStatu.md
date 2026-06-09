# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000b354`
- end: `0x18000b64d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180009750`

## callees

- `0x18000915c`
- `0x18000a944`
- `0x18000b190`
- `0x18000b354`
- `0x18000b8d4`
- `0x18000b8f0`
- `0x18000b904`
- `0x18000b920`
- `0x18000cba8`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b477`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b477`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b608`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b608`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b596`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b596`

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
0x18000b354  mov     [rsp+arg_10], rbx
0x18000b359  mov     [rsp+arg_8], edx
0x18000b35d  mov     [rsp+arg_0], rcx
0x18000b362  push    rbp
0x18000b363  push    rsi
0x18000b364  push    rdi
0x18000b365  push    r12
0x18000b367  push    r13
0x18000b369  push    r14
0x18000b36b  push    r15
0x18000b36d  sub     rsp, 40h
0x18000b371  mov     r12, r9
0x18000b374  mov     r13, r8
0x18000b377  mov     r10, rcx
0x18000b37a  xor     eax, eax
0x18000b37c  mov     rsi, [rsp+78h+lpOutputString]
0x18000b384  mov     [rsi], ax
0x18000b387  mov     rax, [rsp+78h+arg_60]
0x18000b38f  mov     byte ptr [rax], 0
0x18000b392  mov     r14, [rsp+78h+arg_38]
0x18000b39a  mov     edi, [r14]
0x18000b39d  mov     rbx, [rsp+78h+arg_78]
0x18000b3a5  mov     [rbx+8], edi
0x18000b3a8  mov     eax, [r14+4]
0x18000b3ac  mov     [rbx+0Ch], eax
0x18000b3af  xor     ebp, ebp
0x18000b3b1  mov     r15d, [rsp+78h+arg_30]
0x18000b3b9  mov     ecx, r15d
0x18000b3bc  test    r15d, r15d
0x18000b3bf  jz      short loc_18000B427
0x18000b3c1  sub     ecx, 1
0x18000b3c4  jz      short loc_18000B41E
0x18000b3c6  sub     ecx, 1
0x18000b3c9  jz      short loc_18000B3D9
0x18000b3cb  cmp     ecx, 1
0x18000b3ce  jnz     short loc_18000B430
0x18000b3d0  mov     ecx, edi; this
0x18000b3d2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000b3d7  jmp     short loc_18000B42E
0x18000b3d9  test    edi, edi
0x18000b3db  js      short loc_18000B415
0x18000b3dd  mov     edi, 8007029Ch
0x18000b3e2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000b3e6  mov     rax, [rsp+78h+arg_28]
0x18000b3ee  mov     [rsp+78h+var_50], rax; __int64
0x18000b3f3  mov     rax, [rsp+78h+arg_20]
0x18000b3fb  mov     [rsp+78h+var_58], rax; __int64
0x18000b400  mov     rcx, r10; int
0x18000b403  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000b408  mov     [rbx+8], edi
0x18000b40b  mov     ecx, edi; this
0x18000b40d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b412  mov     [rbx+0Ch], eax
0x18000b415  mov     ecx, edi; this
0x18000b417  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000b41c  jmp     short loc_18000B42E
0x18000b41e  mov     ecx, edi; this
0x18000b420  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000b425  jmp     short loc_18000B42E
0x18000b427  mov     ecx, edi; this
0x18000b429  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000b42e  mov     ebp, eax
0x18000b430  mov     [rbx], r15d
0x18000b433  mov     eax, [rsp+78h+arg_70]
0x18000b43a  mov     [rbx+4], eax
0x18000b43d  cmp     dword ptr [r14+8], 1
0x18000b442  jnz     short loc_18000B44A
0x18000b444  or      eax, 8
0x18000b447  mov     [rbx+4], eax
0x18000b44a  mov     eax, 1
0x18000b44f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b457  inc     eax
0x18000b459  mov     [rbx+10h], eax
0x18000b45c  mov     rax, [rsp+78h+arg_40]
0x18000b464  xor     edi, edi
0x18000b466  test    rax, rax
0x18000b469  jz      short loc_18000B470
0x18000b46b  cmp     [rax], di
0x18000b46e  jnz     short loc_18000B473
0x18000b470  mov     rax, rdi
0x18000b473  mov     [rbx+18h], rax
0x18000b477  call    cs:__imp_GetCurrentThreadId
0x18000b47d  mov     [rbx+20h], eax
0x18000b480  mov     [rbx+38h], r13
0x18000b484  mov     eax, [rsp+78h+arg_8]
0x18000b48b  mov     [rbx+40h], eax
0x18000b48e  mov     [rbx+44h], ebp
0x18000b491  mov     rax, [rsp+78h+arg_20]
0x18000b499  mov     [rbx+28h], rax
0x18000b49d  mov     [rbx+30h], r12
0x18000b4a1  mov     rax, [rsp+78h+arg_28]
0x18000b4a9  mov     [rbx+88h], rax
0x18000b4b0  mov     rax, [rsp+78h+arg_0]
0x18000b4b8  mov     [rbx+90h], rax
0x18000b4bf  mov     [rbx+48h], rdi
0x18000b4c3  xorps   xmm0, xmm0
0x18000b4c6  xor     eax, eax
0x18000b4c8  movups  xmmword ptr [rbx+68h], xmm0
0x18000b4cc  mov     [rbx+78h], rax
0x18000b4d0  movups  xmmword ptr [rbx+50h], xmm0
0x18000b4d4  mov     [rbx+60h], rax
0x18000b4d8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000b4df  test    rax, rax
0x18000b4e2  jz      short loc_18000B4EB
0x18000b4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4e9  jmp     short loc_18000B4EE
0x18000b4eb  mov     rax, rdi
0x18000b4ee  mov     [rbx+80h], rax
0x18000b4f5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000b4fc  test    rax, rax
0x18000b4ff  jz      short loc_18000B509
0x18000b501  mov     rcx, rbx
0x18000b504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b509  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000b510  test    rax, rax
0x18000b513  jz      short loc_18000B52B
0x18000b515  mov     r8d, 400h
0x18000b51b  mov     rdx, [rsp+78h+arg_60]
0x18000b523  mov     rcx, rbx
0x18000b526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b52b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b532  test    rax, rax
0x18000b535  jz      short loc_18000B53F
0x18000b537  mov     rcx, rbx
0x18000b53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b53f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b546  test    rax, rax
0x18000b549  jz      short loc_18000B559
0x18000b54b  test    byte ptr [rbx+4], 2
0x18000b54f  jnz     short loc_18000B559
0x18000b551  mov     rcx, rbx
0x18000b554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b559  cmp     [rbx+8], edi
0x18000b55c  jl      short loc_18000B578
0x18000b55e  cmp     r15d, 3
0x18000b562  jnz     loc_18000B647
0x18000b568  mov     ecx, 8000FFFFh; this
0x18000b56d  mov     [rbx+8], ecx
0x18000b570  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b575  mov     [rbx+0Ch], eax
0x18000b578  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000b57f  jnz     short loc_18000B5A0
0x18000b581  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b588  test    rax, rax
0x18000b58b  jz      short loc_18000B596
0x18000b58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b592  test    al, al
0x18000b594  jmp     short loc_18000B59E
0x18000b596  call    cs:__imp_IsDebuggerPresent
0x18000b59c  test    eax, eax
0x18000b59e  jz      short loc_18000B5A6
0x18000b5a0  test    byte ptr [rbx+4], 2
0x18000b5a4  jz      short loc_18000B5CA
0x18000b5a6  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b5ad  test    rax, rax
0x18000b5b0  jz      short loc_18000B60E
0x18000b5b2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000b5b9  jnz     short loc_18000B60E
0x18000b5bb  xor     r8d, r8d
0x18000b5be  xor     edx, edx
0x18000b5c0  mov     rcx, rbx
0x18000b5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5c8  jmp     short loc_18000B60E
0x18000b5ca  mov     ebp, 800h
0x18000b5cf  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b5d6  test    rax, rax
0x18000b5d9  jz      short loc_18000B5F2
0x18000b5db  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000b5e2  jnz     short loc_18000B5F2
0x18000b5e4  mov     r8d, ebp
0x18000b5e7  mov     rdx, rsi
0x18000b5ea  mov     rcx, rbx
0x18000b5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5f2  cmp     [rsi], di
0x18000b5f5  jnz     short loc_18000B605
0x18000b5f7  mov     r8, rbx; unsigned __int64
0x18000b5fa  mov     rdx, rbp; unsigned __int16 *
0x18000b5fd  mov     rcx, rsi; this
0x18000b600  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b605  mov     rcx, rsi; lpOutputString
0x18000b608  call    cs:__imp_OutputDebugStringW
0x18000b60e  test    byte ptr [rbx+4], 4
0x18000b612  jnz     short loc_18000B61D
0x18000b614  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000b61b  jz      short loc_18000B62F
0x18000b61d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b624  test    rax, rax
0x18000b627  jz      short loc_18000B62F
0x18000b629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b62e  nop
0x18000b62f  mov     rbx, [rsp+78h+arg_10]
0x18000b637  add     rsp, 40h
0x18000b63b  pop     r15
0x18000b63d  pop     r14
0x18000b63f  pop     r13
0x18000b641  pop     r12
0x18000b643  pop     rdi
0x18000b644  pop     rsi
0x18000b645  pop     rbp
0x18000b646  retn
0x18000b647  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
