# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800039a0`
- end: `0x180003cbe`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `798`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005300`

## callees

- `0x1800022e0`
- `0x180002760`
- `0x180002780`
- `0x1800027a0`
- `0x1800027c0`
- `0x180002990`
- `0x1800039a0`
- `0x180003f10`
- `0x180004e90`
- `0x18000b930`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180003ac9`
- `KERNEL32!GetCurrentThreadId` at `0x180003ac9`
- `KERNEL32!OutputDebugStringW` at `0x180003c7f`
- `KERNEL32!OutputDebugStringW` at `0x180003c7f`
- `KERNEL32!IsDebuggerPresent` at `0x180003c03`
- `KERNEL32!IsDebuggerPresent` at `0x180003c03`

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
  int IsDebuggerPresent; // esi
  unsigned int v17; // edi
  int v18; // ebp
  int v19; // eax
  _WORD *v20; // rax
  wil::details::in1diag3 *v21; // rcx
  const struct wil::FailureInfo *v22; // r9
  __int64 ModuleName; // rax
  wil::details *v24; // [rsp+30h] [rbp-58h]

  IsDebuggerPresent = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v17 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v18 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v17, a2);
        break;
      case 2:
        if ( (v17 & 0x80000000) == 0 )
        {
          v17 = -2147024228;
          LODWORD(v24) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v24);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
        }
        v19 = wil::details::RecordLog((wil::details *)v17, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v17, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v17, a2);
  }
  v18 = v19;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v20 = a9;
  if ( !a9 || !*a9 )
    v20 = 0;
  *(_QWORD *)(a16 + 24) = v20;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v18;
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
    ModuleName = wil::details::g_pfnGetModuleName(v21);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v21)),
         IsDebuggerPresent))
    && (*(_BYTE *)(a16 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v22);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a16, 0, 0);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v21);
  }
}

```

## disassembly

```asm
0x1800039a0  mov     [rsp+arg_18], r9
0x1800039a5  mov     [rsp+arg_10], r8
0x1800039aa  mov     [rsp+arg_8], edx
0x1800039ae  mov     [rsp+arg_0], rcx
0x1800039b3  push    rbx
0x1800039b4  push    rbp
0x1800039b5  push    rsi
0x1800039b6  push    rdi
0x1800039b7  push    r12
0x1800039b9  push    r13
0x1800039bb  push    r14
0x1800039bd  push    r15
0x1800039bf  sub     rsp, 48h
0x1800039c3  mov     r10, rcx
0x1800039c6  mov     r15d, [rsp+88h+arg_70]
0x1800039ce  xor     esi, esi
0x1800039d0  mov     r14, [rsp+88h+lpOutputString]
0x1800039d8  mov     [r14], si
0x1800039dc  mov     rax, [rsp+88h+arg_60]
0x1800039e4  mov     [rax], sil
0x1800039e7  mov     r12, [rsp+88h+arg_38]
0x1800039ef  mov     edi, [r12]
0x1800039f3  mov     rbx, [rsp+88h+arg_78]
0x1800039fb  mov     [rbx+8], edi
0x1800039fe  mov     eax, [r12+4]
0x180003a03  mov     [rbx+0Ch], eax
0x180003a06  mov     ebp, esi
0x180003a08  mov     r13d, [rsp+88h+arg_30]
0x180003a10  mov     ecx, r13d
0x180003a13  test    r13d, r13d
0x180003a16  jz      short loc_180003A7E
0x180003a18  sub     ecx, 1
0x180003a1b  jz      short loc_180003A75
0x180003a1d  sub     ecx, 1
0x180003a20  jz      short loc_180003A30
0x180003a22  cmp     ecx, 1
0x180003a25  jnz     short loc_180003A87
0x180003a27  mov     ecx, edi; this
0x180003a29  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003a2e  jmp     short loc_180003A85
0x180003a30  test    edi, edi
0x180003a32  js      short loc_180003A6C
0x180003a34  mov     edi, 8007029Ch
0x180003a39  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x180003a3d  mov     rax, [rsp+88h+arg_28]
0x180003a45  mov     [rsp+88h+var_60], rax; __int64
0x180003a4a  mov     rax, [rsp+88h+arg_20]
0x180003a52  mov     [rsp+88h+var_68], rax; __int64
0x180003a57  mov     rcx, r10; int
0x180003a5a  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003a5f  mov     [rbx+8], edi
0x180003a62  mov     ecx, edi; this
0x180003a64  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003a69  mov     [rbx+0Ch], eax
0x180003a6c  mov     ecx, edi; this
0x180003a6e  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180003a73  jmp     short loc_180003A85
0x180003a75  mov     ecx, edi; this
0x180003a77  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003a7c  jmp     short loc_180003A85
0x180003a7e  mov     ecx, edi; this
0x180003a80  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180003a85  mov     ebp, eax
0x180003a87  mov     [rbx], r13d
0x180003a8a  mov     [rbx+4], r15d
0x180003a8e  cmp     dword ptr [r12+8], 1
0x180003a94  jnz     short loc_180003A9E
0x180003a96  or      r15d, 8
0x180003a9a  mov     [rbx+4], r15d
0x180003a9e  mov     eax, 1
0x180003aa3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003aab  inc     eax
0x180003aad  mov     [rbx+10h], eax
0x180003ab0  mov     rax, [rsp+88h+arg_40]
0x180003ab8  test    rax, rax
0x180003abb  jz      short loc_180003AC2
0x180003abd  cmp     [rax], si
0x180003ac0  jnz     short loc_180003AC5
0x180003ac2  mov     rax, rsi
0x180003ac5  mov     [rbx+18h], rax
0x180003ac9  call    cs:__imp_GetCurrentThreadId
0x180003acf  mov     [rbx+20h], eax
0x180003ad2  mov     rax, [rsp+88h+arg_10]
0x180003ada  mov     [rbx+38h], rax
0x180003ade  mov     eax, [rsp+88h+arg_8]
0x180003ae5  mov     [rbx+40h], eax
0x180003ae8  mov     [rbx+44h], ebp
0x180003aeb  mov     rax, [rsp+88h+arg_20]
0x180003af3  mov     [rbx+28h], rax
0x180003af7  mov     rax, [rsp+88h+arg_18]
0x180003aff  mov     [rbx+30h], rax
0x180003b03  mov     rax, [rsp+88h+arg_28]
0x180003b0b  mov     [rbx+88h], rax
0x180003b12  mov     rax, [rsp+88h+arg_0]
0x180003b1a  mov     [rbx+90h], rax
0x180003b21  mov     [rbx+48h], rsi
0x180003b25  xorps   xmm0, xmm0
0x180003b28  xor     eax, eax
0x180003b2a  movups  xmmword ptr [rbx+68h], xmm0
0x180003b2e  mov     [rbx+78h], rax
0x180003b32  movups  xmmword ptr [rbx+50h], xmm0
0x180003b36  mov     [rbx+60h], rax
0x180003b3a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003b41  test    rax, rax
0x180003b44  jz      short loc_180003B4E
0x180003b46  call    cs:__guard_dispatch_icall_fptr
0x180003b4c  jmp     short loc_180003B51
0x180003b4e  mov     rax, rsi
0x180003b51  mov     [rbx+80h], rax
0x180003b58  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003b5f  test    rax, rax
0x180003b62  jz      short loc_180003B6D
0x180003b64  mov     rcx, rbx
0x180003b67  call    cs:__guard_dispatch_icall_fptr
0x180003b6d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003b74  test    rax, rax
0x180003b77  jz      short loc_180003B90
0x180003b79  mov     r8d, 400h
0x180003b7f  mov     rdx, [rsp+88h+arg_60]
0x180003b87  mov     rcx, rbx
0x180003b8a  call    cs:__guard_dispatch_icall_fptr
0x180003b90  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003b97  test    rax, rax
0x180003b9a  jz      short loc_180003BA5
0x180003b9c  mov     rcx, rbx
0x180003b9f  call    cs:__guard_dispatch_icall_fptr
0x180003ba5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003bac  test    rax, rax
0x180003baf  jz      short loc_180003BC0
0x180003bb1  test    byte ptr [rbx+4], 2
0x180003bb5  jnz     short loc_180003BC0
0x180003bb7  mov     rcx, rbx
0x180003bba  call    cs:__guard_dispatch_icall_fptr
0x180003bc0  cmp     [rbx+8], esi
0x180003bc3  jl      short loc_180003BE3
0x180003bc5  cmp     r13d, 3
0x180003bc9  jnz     loc_180003CB8
0x180003bcf  mov     dword ptr [rbx+8], 8000FFFFh
0x180003bd6  mov     ecx, 8000FFFFh; this
0x180003bdb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003be0  mov     [rbx+0Ch], eax
0x180003be3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, sil; bool wil::g_fIsDebuggerPresent
0x180003bea  jnz     short loc_180003C13
0x180003bec  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003bf3  test    rax, rax
0x180003bf6  jz      short loc_180003C03
0x180003bf8  call    cs:__guard_dispatch_icall_fptr
0x180003bfe  movzx   esi, al
0x180003c01  jmp     short loc_180003C0F
0x180003c03  call    cs:__imp_IsDebuggerPresent
0x180003c09  test    eax, eax
0x180003c0b  setnz   sil
0x180003c0f  test    esi, esi
0x180003c11  jz      short loc_180003C19
0x180003c13  test    byte ptr [rbx+4], 2
0x180003c17  jz      short loc_180003C3E
0x180003c19  mov     rax, cs:g_pfnResultLoggingCallback
0x180003c20  test    rax, rax
0x180003c23  jz      short loc_180003C85
0x180003c25  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180003c2c  jnz     short loc_180003C85
0x180003c2e  xor     r8d, r8d
0x180003c31  xor     edx, edx
0x180003c33  mov     rcx, rbx
0x180003c36  call    cs:__guard_dispatch_icall_fptr
0x180003c3c  jmp     short loc_180003C85
0x180003c3e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003c45  test    rax, rax
0x180003c48  jz      short loc_180003C65
0x180003c4a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180003c51  jnz     short loc_180003C65
0x180003c53  mov     r8d, 800h
0x180003c59  mov     rdx, r14
0x180003c5c  mov     rcx, rbx
0x180003c5f  call    cs:__guard_dispatch_icall_fptr
0x180003c65  cmp     word ptr [r14], 0
0x180003c6a  jnz     short loc_180003C7C
0x180003c6c  mov     r8, rbx; unsigned __int64
0x180003c6f  mov     edx, 800h; wchar_t *
0x180003c74  mov     rcx, r14; this
0x180003c77  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180003c7c  mov     rcx, r14; lpOutputString
0x180003c7f  call    cs:__imp_OutputDebugStringW
0x180003c85  test    byte ptr [rbx+4], 4
0x180003c89  jnz     short loc_180003C94
0x180003c8b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x180003c92  jz      short loc_180003CA7
0x180003c94  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003c9b  test    rax, rax
0x180003c9e  jz      short loc_180003CA7
0x180003ca0  call    cs:__guard_dispatch_icall_fptr
0x180003ca6  nop
0x180003ca7  add     rsp, 48h
0x180003cab  pop     r15
0x180003cad  pop     r14
0x180003caf  pop     r13
0x180003cb1  pop     r12
0x180003cb3  pop     rdi
0x180003cb4  pop     rsi
0x180003cb5  pop     rbp
0x180003cb6  pop     rbx
0x180003cb7  retn
0x180003cb8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
