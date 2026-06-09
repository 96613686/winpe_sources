# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000bb0c`
- end: `0x18000be05`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000a1dc`
- `0x18000a528`

## callees

- `0x18000a11c`
- `0x18000b174`
- `0x18000b948`
- `0x18000bb0c`
- `0x18000c150`
- `0x18000c170`
- `0x18000c184`
- `0x18000c1a0`
- `0x18000cd58`
- `0x18004a010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18000bd4e`
- `KERNEL32!IsDebuggerPresent` at `0x18000bd4e`
- `KERNEL32!OutputDebugStringW` at `0x18000bdc0`
- `KERNEL32!OutputDebugStringW` at `0x18000bdc0`
- `KERNEL32!GetCurrentThreadId` at `0x18000bc2f`
- `KERNEL32!GetCurrentThreadId` at `0x18000bc2f`

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
0x18000bb0c  mov     [rsp+arg_10], rbx
0x18000bb11  mov     [rsp+arg_8], edx
0x18000bb15  mov     [rsp+arg_0], rcx
0x18000bb1a  push    rbp
0x18000bb1b  push    rsi
0x18000bb1c  push    rdi
0x18000bb1d  push    r12
0x18000bb1f  push    r13
0x18000bb21  push    r14
0x18000bb23  push    r15
0x18000bb25  sub     rsp, 40h
0x18000bb29  mov     r12, r9
0x18000bb2c  mov     r13, r8
0x18000bb2f  mov     r10, rcx
0x18000bb32  xor     eax, eax
0x18000bb34  mov     rsi, [rsp+78h+lpOutputString]
0x18000bb3c  mov     [rsi], ax
0x18000bb3f  mov     rax, [rsp+78h+arg_60]
0x18000bb47  mov     byte ptr [rax], 0
0x18000bb4a  mov     r14, [rsp+78h+arg_38]
0x18000bb52  mov     edi, [r14]
0x18000bb55  mov     rbx, [rsp+78h+arg_78]
0x18000bb5d  mov     [rbx+8], edi
0x18000bb60  mov     eax, [r14+4]
0x18000bb64  mov     [rbx+0Ch], eax
0x18000bb67  xor     ebp, ebp
0x18000bb69  mov     r15d, [rsp+78h+arg_30]
0x18000bb71  mov     ecx, r15d
0x18000bb74  test    r15d, r15d
0x18000bb77  jz      short loc_18000BBDF
0x18000bb79  sub     ecx, 1
0x18000bb7c  jz      short loc_18000BBD6
0x18000bb7e  sub     ecx, 1
0x18000bb81  jz      short loc_18000BB91
0x18000bb83  cmp     ecx, 1
0x18000bb86  jnz     short loc_18000BBE8
0x18000bb88  mov     ecx, edi; this
0x18000bb8a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000bb8f  jmp     short loc_18000BBE6
0x18000bb91  test    edi, edi
0x18000bb93  js      short loc_18000BBCD
0x18000bb95  mov     edi, 8007029Ch
0x18000bb9a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000bb9e  mov     rax, [rsp+78h+arg_28]
0x18000bba6  mov     [rsp+78h+var_50], rax; __int64
0x18000bbab  mov     rax, [rsp+78h+arg_20]
0x18000bbb3  mov     [rsp+78h+var_58], rax; __int64
0x18000bbb8  mov     rcx, r10; int
0x18000bbbb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000bbc0  mov     [rbx+8], edi
0x18000bbc3  mov     ecx, edi; this
0x18000bbc5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000bbca  mov     [rbx+0Ch], eax
0x18000bbcd  mov     ecx, edi; this
0x18000bbcf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000bbd4  jmp     short loc_18000BBE6
0x18000bbd6  mov     ecx, edi; this
0x18000bbd8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000bbdd  jmp     short loc_18000BBE6
0x18000bbdf  mov     ecx, edi; this
0x18000bbe1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000bbe6  mov     ebp, eax
0x18000bbe8  mov     [rbx], r15d
0x18000bbeb  mov     eax, [rsp+78h+arg_70]
0x18000bbf2  mov     [rbx+4], eax
0x18000bbf5  cmp     dword ptr [r14+8], 1
0x18000bbfa  jnz     short loc_18000BC02
0x18000bbfc  or      eax, 8
0x18000bbff  mov     [rbx+4], eax
0x18000bc02  mov     eax, 1
0x18000bc07  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000bc0f  inc     eax
0x18000bc11  mov     [rbx+10h], eax
0x18000bc14  mov     rax, [rsp+78h+arg_40]
0x18000bc1c  xor     edi, edi
0x18000bc1e  test    rax, rax
0x18000bc21  jz      short loc_18000BC28
0x18000bc23  cmp     [rax], di
0x18000bc26  jnz     short loc_18000BC2B
0x18000bc28  mov     rax, rdi
0x18000bc2b  mov     [rbx+18h], rax
0x18000bc2f  call    cs:__imp_GetCurrentThreadId
0x18000bc35  mov     [rbx+20h], eax
0x18000bc38  mov     [rbx+38h], r13
0x18000bc3c  mov     eax, [rsp+78h+arg_8]
0x18000bc43  mov     [rbx+40h], eax
0x18000bc46  mov     [rbx+44h], ebp
0x18000bc49  mov     rax, [rsp+78h+arg_20]
0x18000bc51  mov     [rbx+28h], rax
0x18000bc55  mov     [rbx+30h], r12
0x18000bc59  mov     rax, [rsp+78h+arg_28]
0x18000bc61  mov     [rbx+88h], rax
0x18000bc68  mov     rax, [rsp+78h+arg_0]
0x18000bc70  mov     [rbx+90h], rax
0x18000bc77  mov     [rbx+48h], rdi
0x18000bc7b  xorps   xmm0, xmm0
0x18000bc7e  xor     eax, eax
0x18000bc80  movups  xmmword ptr [rbx+68h], xmm0
0x18000bc84  mov     [rbx+78h], rax
0x18000bc88  movups  xmmword ptr [rbx+50h], xmm0
0x18000bc8c  mov     [rbx+60h], rax
0x18000bc90  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000bc97  test    rax, rax
0x18000bc9a  jz      short loc_18000BCA3
0x18000bc9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bca1  jmp     short loc_18000BCA6
0x18000bca3  mov     rax, rdi
0x18000bca6  mov     [rbx+80h], rax
0x18000bcad  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000bcb4  test    rax, rax
0x18000bcb7  jz      short loc_18000BCC1
0x18000bcb9  mov     rcx, rbx
0x18000bcbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcc1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000bcc8  test    rax, rax
0x18000bccb  jz      short loc_18000BCE3
0x18000bccd  mov     r8d, 400h
0x18000bcd3  mov     rdx, [rsp+78h+arg_60]
0x18000bcdb  mov     rcx, rbx
0x18000bcde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bce3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bcea  test    rax, rax
0x18000bced  jz      short loc_18000BCF7
0x18000bcef  mov     rcx, rbx
0x18000bcf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcf7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bcfe  test    rax, rax
0x18000bd01  jz      short loc_18000BD11
0x18000bd03  test    byte ptr [rbx+4], 2
0x18000bd07  jnz     short loc_18000BD11
0x18000bd09  mov     rcx, rbx
0x18000bd0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd11  cmp     [rbx+8], edi
0x18000bd14  jl      short loc_18000BD30
0x18000bd16  cmp     r15d, 3
0x18000bd1a  jnz     loc_18000BDFF
0x18000bd20  mov     ecx, 8000FFFFh; this
0x18000bd25  mov     [rbx+8], ecx
0x18000bd28  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000bd2d  mov     [rbx+0Ch], eax
0x18000bd30  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000bd37  jnz     short loc_18000BD58
0x18000bd39  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000bd40  test    rax, rax
0x18000bd43  jz      short loc_18000BD4E
0x18000bd45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd4a  test    al, al
0x18000bd4c  jmp     short loc_18000BD56
0x18000bd4e  call    cs:__imp_IsDebuggerPresent
0x18000bd54  test    eax, eax
0x18000bd56  jz      short loc_18000BD5E
0x18000bd58  test    byte ptr [rbx+4], 2
0x18000bd5c  jz      short loc_18000BD82
0x18000bd5e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bd65  test    rax, rax
0x18000bd68  jz      short loc_18000BDC6
0x18000bd6a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000bd71  jnz     short loc_18000BDC6
0x18000bd73  xor     r8d, r8d
0x18000bd76  xor     edx, edx
0x18000bd78  mov     rcx, rbx
0x18000bd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd80  jmp     short loc_18000BDC6
0x18000bd82  mov     ebp, 800h
0x18000bd87  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bd8e  test    rax, rax
0x18000bd91  jz      short loc_18000BDAA
0x18000bd93  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000bd9a  jnz     short loc_18000BDAA
0x18000bd9c  mov     r8d, ebp
0x18000bd9f  mov     rdx, rsi
0x18000bda2  mov     rcx, rbx
0x18000bda5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdaa  cmp     [rsi], di
0x18000bdad  jnz     short loc_18000BDBD
0x18000bdaf  mov     r8, rbx; unsigned __int64
0x18000bdb2  mov     rdx, rbp; wchar_t *
0x18000bdb5  mov     rcx, rsi; this
0x18000bdb8  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000bdbd  mov     rcx, rsi; lpOutputString
0x18000bdc0  call    cs:__imp_OutputDebugStringW
0x18000bdc6  test    byte ptr [rbx+4], 4
0x18000bdca  jnz     short loc_18000BDD5
0x18000bdcc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000bdd3  jz      short loc_18000BDE7
0x18000bdd5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000bddc  test    rax, rax
0x18000bddf  jz      short loc_18000BDE7
0x18000bde1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bde6  nop
0x18000bde7  mov     rbx, [rsp+78h+arg_10]
0x18000bdef  add     rsp, 40h
0x18000bdf3  pop     r15
0x18000bdf5  pop     r14
0x18000bdf7  pop     r13
0x18000bdf9  pop     r12
0x18000bdfb  pop     rdi
0x18000bdfc  pop     rsi
0x18000bdfd  pop     rbp
0x18000bdfe  retn
0x18000bdff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
