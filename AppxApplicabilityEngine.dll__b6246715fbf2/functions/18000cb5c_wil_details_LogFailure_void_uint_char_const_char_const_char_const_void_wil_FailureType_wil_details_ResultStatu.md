# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000cb5c`
- end: `0x18000ce5d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000c9a4`
- `0x180013afc`
- `0x180013e70`

## callees

- `0x18000c030`
- `0x18000cb5c`
- `0x180013a34`
- `0x180014984`
- `0x18001547c`
- `0x1800154a0`
- `0x1800154b4`
- `0x1800154d0`
- `0x180016098`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc87`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cda6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cda6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ce18`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ce18`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-58h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x18000cb5c  mov     rax, rsp
0x18000cb5f  mov     [rax+10h], edx
0x18000cb62  mov     [rax+8], rcx
0x18000cb66  push    rbp
0x18000cb67  push    rsi
0x18000cb68  push    rdi
0x18000cb69  push    r12
0x18000cb6b  push    r13
0x18000cb6d  push    r14
0x18000cb6f  push    r15
0x18000cb71  sub     rsp, 50h
0x18000cb75  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18000cb7d  mov     [rax+18h], rbx
0x18000cb81  mov     r12, r9
0x18000cb84  mov     r13, r8
0x18000cb87  mov     r10, rcx
0x18000cb8a  xor     eax, eax
0x18000cb8c  mov     rsi, [rsp+88h+lpOutputString]
0x18000cb94  mov     [rsi], ax
0x18000cb97  mov     rax, [rsp+88h+arg_60]
0x18000cb9f  mov     byte ptr [rax], 0
0x18000cba2  mov     r14, [rsp+88h+arg_38]
0x18000cbaa  mov     edi, [r14]
0x18000cbad  mov     rbx, [rsp+88h+arg_78]
0x18000cbb5  mov     [rbx+8], edi
0x18000cbb8  mov     eax, [r14+4]
0x18000cbbc  mov     [rbx+0Ch], eax
0x18000cbbf  xor     ebp, ebp
0x18000cbc1  mov     r15d, [rsp+88h+arg_30]
0x18000cbc9  mov     ecx, r15d
0x18000cbcc  test    r15d, r15d
0x18000cbcf  jz      short loc_18000CC37
0x18000cbd1  sub     ecx, 1
0x18000cbd4  jz      short loc_18000CC2E
0x18000cbd6  sub     ecx, 1
0x18000cbd9  jz      short loc_18000CBE9
0x18000cbdb  cmp     ecx, 1
0x18000cbde  jnz     short loc_18000CC40
0x18000cbe0  mov     ecx, edi; this
0x18000cbe2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000cbe7  jmp     short loc_18000CC3E
0x18000cbe9  test    edi, edi
0x18000cbeb  js      short loc_18000CC25
0x18000cbed  mov     edi, 8007029Ch
0x18000cbf2  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x18000cbf6  mov     rax, [rsp+88h+arg_28]
0x18000cbfe  mov     [rsp+88h+var_60], rax; __int64
0x18000cc03  mov     rax, [rsp+88h+arg_20]
0x18000cc0b  mov     [rsp+88h+var_68], rax; __int64
0x18000cc10  mov     rcx, r10; int
0x18000cc13  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000cc18  mov     [rbx+8], edi
0x18000cc1b  mov     ecx, edi; this
0x18000cc1d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000cc22  mov     [rbx+0Ch], eax
0x18000cc25  mov     ecx, edi; this
0x18000cc27  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000cc2c  jmp     short loc_18000CC3E
0x18000cc2e  mov     ecx, edi; this
0x18000cc30  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000cc35  jmp     short loc_18000CC3E
0x18000cc37  mov     ecx, edi; this
0x18000cc39  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000cc3e  mov     ebp, eax
0x18000cc40  mov     [rbx], r15d
0x18000cc43  mov     eax, [rsp+88h+arg_70]
0x18000cc4a  mov     [rbx+4], eax
0x18000cc4d  cmp     dword ptr [r14+8], 1
0x18000cc52  jnz     short loc_18000CC5A
0x18000cc54  or      eax, 8
0x18000cc57  mov     [rbx+4], eax
0x18000cc5a  mov     eax, 1
0x18000cc5f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000cc67  inc     eax
0x18000cc69  mov     [rbx+10h], eax
0x18000cc6c  mov     rax, [rsp+88h+arg_40]
0x18000cc74  xor     edi, edi
0x18000cc76  test    rax, rax
0x18000cc79  jz      short loc_18000CC80
0x18000cc7b  cmp     [rax], di
0x18000cc7e  jnz     short loc_18000CC83
0x18000cc80  mov     rax, rdi
0x18000cc83  mov     [rbx+18h], rax
0x18000cc87  call    cs:__imp_GetCurrentThreadId
0x18000cc8d  mov     [rbx+20h], eax
0x18000cc90  mov     [rbx+38h], r13
0x18000cc94  mov     eax, [rsp+88h+arg_8]
0x18000cc9b  mov     [rbx+40h], eax
0x18000cc9e  mov     [rbx+44h], ebp
0x18000cca1  mov     rax, [rsp+88h+arg_20]
0x18000cca9  mov     [rbx+28h], rax
0x18000ccad  mov     [rbx+30h], r12
0x18000ccb1  mov     rax, [rsp+88h+arg_28]
0x18000ccb9  mov     [rbx+88h], rax
0x18000ccc0  mov     rax, [rsp+88h+arg_0]
0x18000ccc8  mov     [rbx+90h], rax
0x18000cccf  mov     [rbx+48h], rdi
0x18000ccd3  xorps   xmm0, xmm0
0x18000ccd6  xor     eax, eax
0x18000ccd8  movups  xmmword ptr [rbx+68h], xmm0
0x18000ccdc  mov     [rbx+78h], rax
0x18000cce0  movups  xmmword ptr [rbx+50h], xmm0
0x18000cce4  mov     [rbx+60h], rax
0x18000cce8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ccef  test    rax, rax
0x18000ccf2  jz      short loc_18000CCFB
0x18000ccf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccf9  jmp     short loc_18000CCFE
0x18000ccfb  mov     rax, rdi
0x18000ccfe  mov     [rbx+80h], rax
0x18000cd05  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000cd0c  test    rax, rax
0x18000cd0f  jz      short loc_18000CD19
0x18000cd11  mov     rcx, rbx
0x18000cd14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd19  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000cd20  test    rax, rax
0x18000cd23  jz      short loc_18000CD3B
0x18000cd25  mov     r8d, 400h
0x18000cd2b  mov     rdx, [rsp+88h+arg_60]
0x18000cd33  mov     rcx, rbx
0x18000cd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd3b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cd42  test    rax, rax
0x18000cd45  jz      short loc_18000CD4F
0x18000cd47  mov     rcx, rbx
0x18000cd4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd4f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cd56  test    rax, rax
0x18000cd59  jz      short loc_18000CD69
0x18000cd5b  test    byte ptr [rbx+4], 2
0x18000cd5f  jnz     short loc_18000CD69
0x18000cd61  mov     rcx, rbx
0x18000cd64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd69  cmp     [rbx+8], edi
0x18000cd6c  jl      short loc_18000CD88
0x18000cd6e  cmp     r15d, 3
0x18000cd72  jnz     loc_18000CE57
0x18000cd78  mov     ecx, 8000FFFFh; this
0x18000cd7d  mov     [rbx+8], ecx
0x18000cd80  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000cd85  mov     [rbx+0Ch], eax
0x18000cd88  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000cd8f  jnz     short loc_18000CDB0
0x18000cd91  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000cd98  test    rax, rax
0x18000cd9b  jz      short loc_18000CDA6
0x18000cd9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cda2  test    al, al
0x18000cda4  jmp     short loc_18000CDAE
0x18000cda6  call    cs:__imp_IsDebuggerPresent
0x18000cdac  test    eax, eax
0x18000cdae  jz      short loc_18000CDB6
0x18000cdb0  test    byte ptr [rbx+4], 2
0x18000cdb4  jz      short loc_18000CDDA
0x18000cdb6  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cdbd  test    rax, rax
0x18000cdc0  jz      short loc_18000CE1E
0x18000cdc2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000cdc9  jnz     short loc_18000CE1E
0x18000cdcb  xor     r8d, r8d
0x18000cdce  xor     edx, edx
0x18000cdd0  mov     rcx, rbx
0x18000cdd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdd8  jmp     short loc_18000CE1E
0x18000cdda  mov     ebp, 800h
0x18000cddf  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cde6  test    rax, rax
0x18000cde9  jz      short loc_18000CE02
0x18000cdeb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000cdf2  jnz     short loc_18000CE02
0x18000cdf4  mov     r8d, ebp
0x18000cdf7  mov     rdx, rsi
0x18000cdfa  mov     rcx, rbx
0x18000cdfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce02  cmp     [rsi], di
0x18000ce05  jnz     short loc_18000CE15
0x18000ce07  mov     r8, rbx; unsigned __int64
0x18000ce0a  mov     rdx, rbp; unsigned __int16 *
0x18000ce0d  mov     rcx, rsi; this
0x18000ce10  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000ce15  mov     rcx, rsi; lpOutputString
0x18000ce18  call    cs:__imp_OutputDebugStringW
0x18000ce1e  test    byte ptr [rbx+4], 4
0x18000ce22  jnz     short loc_18000CE2D
0x18000ce24  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000ce2b  jz      short loc_18000CE3F
0x18000ce2d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000ce34  test    rax, rax
0x18000ce37  jz      short loc_18000CE3F
0x18000ce39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce3e  nop
0x18000ce3f  mov     rbx, [rsp+88h+arg_10]
0x18000ce47  add     rsp, 50h
0x18000ce4b  pop     r15
0x18000ce4d  pop     r14
0x18000ce4f  pop     r13
0x18000ce51  pop     r12
0x18000ce53  pop     rdi
0x18000ce54  pop     rsi
0x18000ce55  pop     rbp
0x18000ce56  retn
0x18000ce57  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
