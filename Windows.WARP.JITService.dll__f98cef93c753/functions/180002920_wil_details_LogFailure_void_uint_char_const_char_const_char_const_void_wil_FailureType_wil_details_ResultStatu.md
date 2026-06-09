# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180002920`
- end: `0x180002c21`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180007708`

## callees

- `0x180001514`
- `0x18000196c`
- `0x180001988`
- `0x1800019a4`
- `0x1800019c0`
- `0x180001c50`
- `0x180002920`
- `0x180002e94`
- `0x180006c04`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a43`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002b63`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002b63`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002bdc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002bdc`

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
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  wil::details *v25; // [rsp+30h] [rbp-48h]

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
          LODWORD(v25) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v25);
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
    ModuleName = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (*(_BYTE *)(a16 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a16, 0, 0);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  }
}

```

## disassembly

```asm
0x180002920  mov     [rsp+arg_10], rbx
0x180002925  mov     [rsp+arg_8], edx
0x180002929  mov     [rsp+arg_0], rcx
0x18000292e  push    rbp
0x18000292f  push    rsi
0x180002930  push    rdi
0x180002931  push    r12
0x180002933  push    r13
0x180002935  push    r14
0x180002937  push    r15
0x180002939  sub     rsp, 40h
0x18000293d  mov     r12, r9
0x180002940  mov     r13, r8
0x180002943  mov     r10, rcx
0x180002946  xor     eax, eax
0x180002948  mov     rsi, [rsp+78h+lpOutputString]
0x180002950  mov     [rsi], ax
0x180002953  mov     rax, [rsp+78h+arg_60]
0x18000295b  mov     byte ptr [rax], 0
0x18000295e  mov     r14, [rsp+78h+arg_38]
0x180002966  mov     edi, [r14]
0x180002969  mov     rbx, [rsp+78h+arg_78]
0x180002971  mov     [rbx+8], edi
0x180002974  mov     eax, [r14+4]
0x180002978  mov     [rbx+0Ch], eax
0x18000297b  xor     ebp, ebp
0x18000297d  mov     r15d, [rsp+78h+arg_30]
0x180002985  mov     ecx, r15d
0x180002988  test    r15d, r15d
0x18000298b  jz      short loc_1800029F3
0x18000298d  sub     ecx, 1
0x180002990  jz      short loc_1800029EA
0x180002992  sub     ecx, 1
0x180002995  jz      short loc_1800029A5
0x180002997  cmp     ecx, 1
0x18000299a  jnz     short loc_1800029FC
0x18000299c  mov     ecx, edi; this
0x18000299e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800029a3  jmp     short loc_1800029FA
0x1800029a5  test    edi, edi
0x1800029a7  js      short loc_1800029E1
0x1800029a9  mov     edi, 8007029Ch
0x1800029ae  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800029b2  mov     rax, [rsp+78h+arg_28]
0x1800029ba  mov     [rsp+78h+var_50], rax; __int64
0x1800029bf  mov     rax, [rsp+78h+arg_20]
0x1800029c7  mov     [rsp+78h+var_58], rax; __int64
0x1800029cc  mov     rcx, r10; int
0x1800029cf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800029d4  mov     [rbx+8], edi
0x1800029d7  mov     ecx, edi; this
0x1800029d9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800029de  mov     [rbx+0Ch], eax
0x1800029e1  mov     ecx, edi; this
0x1800029e3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800029e8  jmp     short loc_1800029FA
0x1800029ea  mov     ecx, edi; this
0x1800029ec  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800029f1  jmp     short loc_1800029FA
0x1800029f3  mov     ecx, edi; this
0x1800029f5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800029fa  mov     ebp, eax
0x1800029fc  mov     [rbx], r15d
0x1800029ff  mov     eax, [rsp+78h+arg_70]
0x180002a06  mov     [rbx+4], eax
0x180002a09  cmp     dword ptr [r14+8], 1
0x180002a0e  jnz     short loc_180002A16
0x180002a10  or      eax, 8
0x180002a13  mov     [rbx+4], eax
0x180002a16  mov     eax, 1
0x180002a1b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002a23  inc     eax
0x180002a25  mov     [rbx+10h], eax
0x180002a28  mov     rax, [rsp+78h+arg_40]
0x180002a30  xor     edi, edi
0x180002a32  test    rax, rax
0x180002a35  jz      short loc_180002A3C
0x180002a37  cmp     [rax], di
0x180002a3a  jnz     short loc_180002A3F
0x180002a3c  mov     rax, rdi
0x180002a3f  mov     [rbx+18h], rax
0x180002a43  call    cs:__imp_GetCurrentThreadId
0x180002a49  mov     [rbx+20h], eax
0x180002a4c  mov     [rbx+38h], r13
0x180002a50  mov     eax, [rsp+78h+arg_8]
0x180002a57  mov     [rbx+40h], eax
0x180002a5a  mov     [rbx+44h], ebp
0x180002a5d  mov     rax, [rsp+78h+arg_20]
0x180002a65  mov     [rbx+28h], rax
0x180002a69  mov     [rbx+30h], r12
0x180002a6d  mov     rax, [rsp+78h+arg_28]
0x180002a75  mov     [rbx+88h], rax
0x180002a7c  mov     rax, [rsp+78h+arg_0]
0x180002a84  mov     [rbx+90h], rax
0x180002a8b  mov     [rbx+48h], rdi
0x180002a8f  xorps   xmm0, xmm0
0x180002a92  xor     eax, eax
0x180002a94  movups  xmmword ptr [rbx+68h], xmm0
0x180002a98  mov     [rbx+78h], rax
0x180002a9c  movups  xmmword ptr [rbx+50h], xmm0
0x180002aa0  mov     [rbx+60h], rax
0x180002aa4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002aab  test    rax, rax
0x180002aae  jz      short loc_180002AB7
0x180002ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ab5  jmp     short loc_180002ABA
0x180002ab7  mov     rax, rdi
0x180002aba  mov     [rbx+80h], rax
0x180002ac1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002ac8  test    rax, rax
0x180002acb  jz      short loc_180002AD5
0x180002acd  mov     rcx, rbx
0x180002ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ad5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002adc  test    rax, rax
0x180002adf  jz      short loc_180002AF7
0x180002ae1  mov     r8d, 400h
0x180002ae7  mov     rdx, [rsp+78h+arg_60]
0x180002aef  mov     rcx, rbx
0x180002af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002af7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002afe  test    rax, rax
0x180002b01  jz      short loc_180002B0B
0x180002b03  mov     rcx, rbx
0x180002b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b0b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002b12  test    rax, rax
0x180002b15  jz      short loc_180002B25
0x180002b17  test    byte ptr [rbx+4], 2
0x180002b1b  jnz     short loc_180002B25
0x180002b1d  mov     rcx, rbx
0x180002b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b25  cmp     [rbx+8], edi
0x180002b28  jl      short loc_180002B44
0x180002b2a  cmp     r15d, 3
0x180002b2e  jnz     loc_180002C1B
0x180002b34  mov     ecx, 8000FFFFh; this
0x180002b39  mov     [rbx+8], ecx
0x180002b3c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002b41  mov     [rbx+0Ch], eax
0x180002b44  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180002b4b  jnz     short loc_180002B74
0x180002b4d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002b54  test    rax, rax
0x180002b57  jz      short loc_180002B63
0x180002b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b5e  movzx   ecx, al
0x180002b61  jmp     short loc_180002B70
0x180002b63  call    cs:__imp_IsDebuggerPresent
0x180002b69  mov     ecx, edi
0x180002b6b  test    eax, eax
0x180002b6d  setnz   cl
0x180002b70  test    ecx, ecx
0x180002b72  jz      short loc_180002B7A
0x180002b74  test    byte ptr [rbx+4], 2
0x180002b78  jz      short loc_180002B9E
0x180002b7a  mov     rax, cs:g_pfnResultLoggingCallback
0x180002b81  test    rax, rax
0x180002b84  jz      short loc_180002BE2
0x180002b86  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180002b8d  jnz     short loc_180002BE2
0x180002b8f  xor     r8d, r8d
0x180002b92  xor     edx, edx
0x180002b94  mov     rcx, rbx
0x180002b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b9c  jmp     short loc_180002BE2
0x180002b9e  mov     ebp, 800h
0x180002ba3  mov     rax, cs:g_pfnResultLoggingCallback
0x180002baa  test    rax, rax
0x180002bad  jz      short loc_180002BC6
0x180002baf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180002bb6  jnz     short loc_180002BC6
0x180002bb8  mov     r8d, ebp
0x180002bbb  mov     rdx, rsi
0x180002bbe  mov     rcx, rbx
0x180002bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bc6  cmp     [rsi], di
0x180002bc9  jnz     short loc_180002BD9
0x180002bcb  mov     r8, rbx; unsigned __int64
0x180002bce  mov     rdx, rbp; unsigned __int16 *
0x180002bd1  mov     rcx, rsi; this
0x180002bd4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002bd9  mov     rcx, rsi; lpOutputString
0x180002bdc  call    cs:__imp_OutputDebugStringW
0x180002be2  test    byte ptr [rbx+4], 4
0x180002be6  jnz     short loc_180002BF1
0x180002be8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180002bef  jz      short loc_180002C03
0x180002bf1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002bf8  test    rax, rax
0x180002bfb  jz      short loc_180002C03
0x180002bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c02  nop
0x180002c03  mov     rbx, [rsp+78h+arg_10]
0x180002c0b  add     rsp, 40h
0x180002c0f  pop     r15
0x180002c11  pop     r14
0x180002c13  pop     r13
0x180002c15  pop     r12
0x180002c17  pop     rdi
0x180002c18  pop     rsi
0x180002c19  pop     rbp
0x180002c1a  retn
0x180002c1b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
