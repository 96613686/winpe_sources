# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001e53c`
- end: `0x18001e834`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180018b44`

## callees

- `0x180018580`
- `0x18001bb28`
- `0x18001cad8`
- `0x18001e53c`
- `0x180020e10`
- `0x180020e30`
- `0x180020f58`
- `0x180020f74`
- `0x1800247e4`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e65f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e65f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001e77e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001e77e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001e7f0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001e7f0`

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
0x18001e53c  mov     [rsp+arg_10], rbx
0x18001e541  mov     [rsp+arg_8], edx
0x18001e545  mov     [rsp+arg_0], rcx
0x18001e54a  push    rbp
0x18001e54b  push    rsi
0x18001e54c  push    rdi
0x18001e54d  push    r12
0x18001e54f  push    r13
0x18001e551  push    r14
0x18001e553  push    r15
0x18001e555  sub     rsp, 40h
0x18001e559  mov     r14, [rsp+78h+arg_38]
0x18001e561  xor     eax, eax
0x18001e563  mov     rbx, [rsp+78h+arg_78]
0x18001e56b  xor     ebp, ebp
0x18001e56d  mov     r15d, [rsp+78h+arg_30]
0x18001e575  mov     r10, rcx
0x18001e578  mov     rsi, [rsp+78h+lpOutputString]
0x18001e580  mov     r12, r9
0x18001e583  mov     r13, r8
0x18001e586  mov     ecx, r15d
0x18001e589  mov     [rsi], ax
0x18001e58c  mov     rax, [rsp+78h+arg_60]
0x18001e594  mov     byte ptr [rax], 0
0x18001e597  mov     edi, [r14]
0x18001e59a  mov     [rbx+8], edi
0x18001e59d  mov     eax, [r14+4]
0x18001e5a1  mov     [rbx+0Ch], eax
0x18001e5a4  test    r15d, r15d
0x18001e5a7  jz      short loc_18001E60F
0x18001e5a9  sub     ecx, 1
0x18001e5ac  jz      short loc_18001E606
0x18001e5ae  sub     ecx, 1
0x18001e5b1  jz      short loc_18001E5C1
0x18001e5b3  cmp     ecx, 1
0x18001e5b6  jnz     short loc_18001E618
0x18001e5b8  mov     ecx, edi; this
0x18001e5ba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001e5bf  jmp     short loc_18001E616
0x18001e5c1  test    edi, edi
0x18001e5c3  js      short loc_18001E5FD
0x18001e5c5  mov     rax, [rsp+78h+arg_28]
0x18001e5cd  mov     edi, 8007029Ch
0x18001e5d2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001e5d6  mov     rcx, r10; int
0x18001e5d9  mov     [rsp+78h+var_50], rax; __int64
0x18001e5de  mov     rax, [rsp+78h+arg_20]
0x18001e5e6  mov     [rsp+78h+var_58], rax; __int64
0x18001e5eb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001e5f0  mov     ecx, edi; this
0x18001e5f2  mov     [rbx+8], edi
0x18001e5f5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001e5fa  mov     [rbx+0Ch], eax
0x18001e5fd  mov     ecx, edi; this
0x18001e5ff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001e604  jmp     short loc_18001E616
0x18001e606  mov     ecx, edi; this
0x18001e608  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001e60d  jmp     short loc_18001E616
0x18001e60f  mov     ecx, edi; this
0x18001e611  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001e616  mov     ebp, eax
0x18001e618  mov     eax, [rsp+78h+arg_70]
0x18001e61f  mov     [rbx+4], eax
0x18001e622  mov     [rbx], r15d
0x18001e625  cmp     dword ptr [r14+8], 1
0x18001e62a  jnz     short loc_18001E632
0x18001e62c  or      eax, 8
0x18001e62f  mov     [rbx+4], eax
0x18001e632  mov     eax, 1
0x18001e637  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001e63f  inc     eax
0x18001e641  xor     edi, edi
0x18001e643  mov     [rbx+10h], eax
0x18001e646  mov     rax, [rsp+78h+arg_40]
0x18001e64e  test    rax, rax
0x18001e651  jz      short loc_18001E658
0x18001e653  cmp     [rax], di
0x18001e656  jnz     short loc_18001E65B
0x18001e658  mov     rax, rdi
0x18001e65b  mov     [rbx+18h], rax
0x18001e65f  call    cs:__imp_GetCurrentThreadId
0x18001e665  mov     [rbx+38h], r13
0x18001e669  xorps   xmm0, xmm0
0x18001e66c  mov     [rbx+20h], eax
0x18001e66f  mov     eax, [rsp+78h+arg_8]
0x18001e676  mov     [rbx+40h], eax
0x18001e679  mov     rax, [rsp+78h+arg_20]
0x18001e681  mov     [rbx+28h], rax
0x18001e685  mov     rax, [rsp+78h+arg_28]
0x18001e68d  mov     [rbx+88h], rax
0x18001e694  mov     rax, [rsp+78h+arg_0]
0x18001e69c  mov     [rbx+90h], rax
0x18001e6a3  xor     eax, eax
0x18001e6a5  mov     [rbx+44h], ebp
0x18001e6a8  mov     [rbx+30h], r12
0x18001e6ac  mov     [rbx+48h], rdi
0x18001e6b0  movups  xmmword ptr [rbx+68h], xmm0
0x18001e6b4  mov     [rbx+78h], rax
0x18001e6b8  movups  xmmword ptr [rbx+50h], xmm0
0x18001e6bc  mov     [rbx+60h], rax
0x18001e6c0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001e6c7  test    rax, rax
0x18001e6ca  jz      short loc_18001E6D3
0x18001e6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6d1  jmp     short loc_18001E6D6
0x18001e6d3  mov     rax, rdi
0x18001e6d6  mov     [rbx+80h], rax
0x18001e6dd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001e6e4  test    rax, rax
0x18001e6e7  jz      short loc_18001E6F1
0x18001e6e9  mov     rcx, rbx
0x18001e6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6f1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001e6f8  test    rax, rax
0x18001e6fb  jz      short loc_18001E713
0x18001e6fd  mov     rdx, [rsp+78h+arg_60]
0x18001e705  mov     r8d, 400h
0x18001e70b  mov     rcx, rbx
0x18001e70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e713  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001e71a  test    rax, rax
0x18001e71d  jz      short loc_18001E727
0x18001e71f  mov     rcx, rbx
0x18001e722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e727  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001e72e  test    rax, rax
0x18001e731  jz      short loc_18001E741
0x18001e733  test    byte ptr [rbx+4], 2
0x18001e737  jnz     short loc_18001E741
0x18001e739  mov     rcx, rbx
0x18001e73c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e741  cmp     [rbx+8], edi
0x18001e744  jl      short loc_18001E760
0x18001e746  cmp     r15d, 3
0x18001e74a  jnz     loc_18001E82E
0x18001e750  mov     ecx, 8000FFFFh; this
0x18001e755  mov     [rbx+8], ecx
0x18001e758  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001e75d  mov     [rbx+0Ch], eax
0x18001e760  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001e767  jnz     short loc_18001E788
0x18001e769  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001e770  test    rax, rax
0x18001e773  jz      short loc_18001E77E
0x18001e775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e77a  test    al, al
0x18001e77c  jmp     short loc_18001E786
0x18001e77e  call    cs:__imp_IsDebuggerPresent
0x18001e784  test    eax, eax
0x18001e786  jz      short loc_18001E78E
0x18001e788  test    byte ptr [rbx+4], 2
0x18001e78c  jz      short loc_18001E7B2
0x18001e78e  mov     rax, cs:g_pfnResultLoggingCallback
0x18001e795  test    rax, rax
0x18001e798  jz      short loc_18001E7F6
0x18001e79a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001e7a1  jnz     short loc_18001E7F6
0x18001e7a3  xor     r8d, r8d
0x18001e7a6  xor     edx, edx
0x18001e7a8  mov     rcx, rbx
0x18001e7ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7b0  jmp     short loc_18001E7F6
0x18001e7b2  mov     rax, cs:g_pfnResultLoggingCallback
0x18001e7b9  mov     ebp, 800h
0x18001e7be  test    rax, rax
0x18001e7c1  jz      short loc_18001E7DA
0x18001e7c3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001e7ca  jnz     short loc_18001E7DA
0x18001e7cc  mov     r8d, ebp
0x18001e7cf  mov     rdx, rsi
0x18001e7d2  mov     rcx, rbx
0x18001e7d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7da  cmp     [rsi], di
0x18001e7dd  jnz     short loc_18001E7ED
0x18001e7df  mov     r8, rbx; unsigned __int64
0x18001e7e2  mov     rdx, rbp; unsigned __int16 *
0x18001e7e5  mov     rcx, rsi; this
0x18001e7e8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001e7ed  mov     rcx, rsi; lpOutputString
0x18001e7f0  call    cs:__imp_OutputDebugStringW
0x18001e7f6  test    byte ptr [rbx+4], 4
0x18001e7fa  jnz     short loc_18001E805
0x18001e7fc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001e803  jz      short loc_18001E816
0x18001e805  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001e80c  test    rax, rax
0x18001e80f  jz      short loc_18001E816
0x18001e811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e816  mov     rbx, [rsp+78h+arg_10]
0x18001e81e  add     rsp, 40h
0x18001e822  pop     r15
0x18001e824  pop     r14
0x18001e826  pop     r13
0x18001e828  pop     r12
0x18001e82a  pop     rdi
0x18001e82b  pop     rsi
0x18001e82c  pop     rbp
0x18001e82d  retn
0x18001e82e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
