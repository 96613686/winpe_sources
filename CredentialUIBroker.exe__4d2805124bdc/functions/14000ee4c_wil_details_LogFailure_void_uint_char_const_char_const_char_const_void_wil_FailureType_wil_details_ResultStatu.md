# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000ee4c`
- end: `0x14000f144`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140006a08`
- `0x140006d5c`

## callees

- `0x140006810`
- `0x14000d4d8`
- `0x14000e45c`
- `0x14000ee4c`
- `0x1400121e0`
- `0x140012200`
- `0x140012350`
- `0x14001236c`
- `0x140017d60`
- `0x14001f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000ef6f`
- `KERNEL32!GetCurrentThreadId` at `0x14000ef6f`
- `KERNEL32!OutputDebugStringW` at `0x14000f100`
- `KERNEL32!OutputDebugStringW` at `0x14000f100`
- `KERNEL32!IsDebuggerPresent` at `0x14000f08e`
- `KERNEL32!IsDebuggerPresent` at `0x14000f08e`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x14000ee4c  mov     [rsp+arg_10], rbx
0x14000ee51  mov     [rsp+arg_8], edx
0x14000ee55  mov     [rsp+arg_0], rcx
0x14000ee5a  push    rbp
0x14000ee5b  push    rsi
0x14000ee5c  push    rdi
0x14000ee5d  push    r12
0x14000ee5f  push    r13
0x14000ee61  push    r14
0x14000ee63  push    r15
0x14000ee65  sub     rsp, 40h
0x14000ee69  mov     r14, [rsp+78h+arg_38]
0x14000ee71  xor     eax, eax
0x14000ee73  mov     rbx, [rsp+78h+arg_78]
0x14000ee7b  xor     ebp, ebp
0x14000ee7d  mov     r15d, [rsp+78h+arg_30]
0x14000ee85  mov     r10, rcx
0x14000ee88  mov     rsi, [rsp+78h+lpOutputString]
0x14000ee90  mov     r12, r9
0x14000ee93  mov     r13, r8
0x14000ee96  mov     ecx, r15d
0x14000ee99  mov     [rsi], ax
0x14000ee9c  mov     rax, [rsp+78h+arg_60]
0x14000eea4  mov     byte ptr [rax], 0
0x14000eea7  mov     edi, [r14]
0x14000eeaa  mov     [rbx+8], edi
0x14000eead  mov     eax, [r14+4]
0x14000eeb1  mov     [rbx+0Ch], eax
0x14000eeb4  test    r15d, r15d
0x14000eeb7  jz      short loc_14000EF1F
0x14000eeb9  sub     ecx, 1
0x14000eebc  jz      short loc_14000EF16
0x14000eebe  sub     ecx, 1
0x14000eec1  jz      short loc_14000EED1
0x14000eec3  cmp     ecx, 1
0x14000eec6  jnz     short loc_14000EF28
0x14000eec8  mov     ecx, edi; this
0x14000eeca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000eecf  jmp     short loc_14000EF26
0x14000eed1  test    edi, edi
0x14000eed3  js      short loc_14000EF0D
0x14000eed5  mov     rax, [rsp+78h+arg_28]
0x14000eedd  mov     edi, 8007029Ch
0x14000eee2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000eee6  mov     rcx, r10; int
0x14000eee9  mov     [rsp+78h+var_50], rax; __int64
0x14000eeee  mov     rax, [rsp+78h+arg_20]
0x14000eef6  mov     [rsp+78h+var_58], rax; __int64
0x14000eefb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000ef00  mov     ecx, edi; this
0x14000ef02  mov     [rbx+8], edi
0x14000ef05  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000ef0a  mov     [rbx+0Ch], eax
0x14000ef0d  mov     ecx, edi; this
0x14000ef0f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000ef14  jmp     short loc_14000EF26
0x14000ef16  mov     ecx, edi; this
0x14000ef18  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000ef1d  jmp     short loc_14000EF26
0x14000ef1f  mov     ecx, edi; this
0x14000ef21  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000ef26  mov     ebp, eax
0x14000ef28  mov     eax, [rsp+78h+arg_70]
0x14000ef2f  mov     [rbx+4], eax
0x14000ef32  mov     [rbx], r15d
0x14000ef35  cmp     dword ptr [r14+8], 1
0x14000ef3a  jnz     short loc_14000EF42
0x14000ef3c  or      eax, 8
0x14000ef3f  mov     [rbx+4], eax
0x14000ef42  mov     eax, 1
0x14000ef47  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000ef4f  inc     eax
0x14000ef51  xor     edi, edi
0x14000ef53  mov     [rbx+10h], eax
0x14000ef56  mov     rax, [rsp+78h+arg_40]
0x14000ef5e  test    rax, rax
0x14000ef61  jz      short loc_14000EF68
0x14000ef63  cmp     [rax], di
0x14000ef66  jnz     short loc_14000EF6B
0x14000ef68  mov     rax, rdi
0x14000ef6b  mov     [rbx+18h], rax
0x14000ef6f  call    cs:__imp_GetCurrentThreadId
0x14000ef75  mov     [rbx+38h], r13
0x14000ef79  xorps   xmm0, xmm0
0x14000ef7c  mov     [rbx+20h], eax
0x14000ef7f  mov     eax, [rsp+78h+arg_8]
0x14000ef86  mov     [rbx+40h], eax
0x14000ef89  mov     rax, [rsp+78h+arg_20]
0x14000ef91  mov     [rbx+28h], rax
0x14000ef95  mov     rax, [rsp+78h+arg_28]
0x14000ef9d  mov     [rbx+88h], rax
0x14000efa4  mov     rax, [rsp+78h+arg_0]
0x14000efac  mov     [rbx+90h], rax
0x14000efb3  xor     eax, eax
0x14000efb5  mov     [rbx+44h], ebp
0x14000efb8  mov     [rbx+30h], r12
0x14000efbc  mov     [rbx+48h], rdi
0x14000efc0  movups  xmmword ptr [rbx+68h], xmm0
0x14000efc4  mov     [rbx+78h], rax
0x14000efc8  movups  xmmword ptr [rbx+50h], xmm0
0x14000efcc  mov     [rbx+60h], rax
0x14000efd0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000efd7  test    rax, rax
0x14000efda  jz      short loc_14000EFE3
0x14000efdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000efe1  jmp     short loc_14000EFE6
0x14000efe3  mov     rax, rdi
0x14000efe6  mov     [rbx+80h], rax
0x14000efed  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000eff4  test    rax, rax
0x14000eff7  jz      short loc_14000F001
0x14000eff9  mov     rcx, rbx
0x14000effc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f001  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000f008  test    rax, rax
0x14000f00b  jz      short loc_14000F023
0x14000f00d  mov     rdx, [rsp+78h+arg_60]
0x14000f015  mov     r8d, 400h
0x14000f01b  mov     rcx, rbx
0x14000f01e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f023  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000f02a  test    rax, rax
0x14000f02d  jz      short loc_14000F037
0x14000f02f  mov     rcx, rbx
0x14000f032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f037  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000f03e  test    rax, rax
0x14000f041  jz      short loc_14000F051
0x14000f043  test    byte ptr [rbx+4], 2
0x14000f047  jnz     short loc_14000F051
0x14000f049  mov     rcx, rbx
0x14000f04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f051  cmp     [rbx+8], edi
0x14000f054  jl      short loc_14000F070
0x14000f056  cmp     r15d, 3
0x14000f05a  jnz     loc_14000F13E
0x14000f060  mov     ecx, 8000FFFFh; this
0x14000f065  mov     [rbx+8], ecx
0x14000f068  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000f06d  mov     [rbx+0Ch], eax
0x14000f070  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000f077  jnz     short loc_14000F098
0x14000f079  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000f080  test    rax, rax
0x14000f083  jz      short loc_14000F08E
0x14000f085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f08a  test    al, al
0x14000f08c  jmp     short loc_14000F096
0x14000f08e  call    cs:__imp_IsDebuggerPresent
0x14000f094  test    eax, eax
0x14000f096  jz      short loc_14000F09E
0x14000f098  test    byte ptr [rbx+4], 2
0x14000f09c  jz      short loc_14000F0C2
0x14000f09e  mov     rax, cs:g_pfnResultLoggingCallback
0x14000f0a5  test    rax, rax
0x14000f0a8  jz      short loc_14000F106
0x14000f0aa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000f0b1  jnz     short loc_14000F106
0x14000f0b3  xor     r8d, r8d
0x14000f0b6  xor     edx, edx
0x14000f0b8  mov     rcx, rbx
0x14000f0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f0c0  jmp     short loc_14000F106
0x14000f0c2  mov     rax, cs:g_pfnResultLoggingCallback
0x14000f0c9  mov     ebp, 800h
0x14000f0ce  test    rax, rax
0x14000f0d1  jz      short loc_14000F0EA
0x14000f0d3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000f0da  jnz     short loc_14000F0EA
0x14000f0dc  mov     r8d, ebp
0x14000f0df  mov     rdx, rsi
0x14000f0e2  mov     rcx, rbx
0x14000f0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f0ea  cmp     [rsi], di
0x14000f0ed  jnz     short loc_14000F0FD
0x14000f0ef  mov     r8, rbx; unsigned __int64
0x14000f0f2  mov     rdx, rbp; unsigned __int16 *
0x14000f0f5  mov     rcx, rsi; this
0x14000f0f8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000f0fd  mov     rcx, rsi; lpOutputString
0x14000f100  call    cs:__imp_OutputDebugStringW
0x14000f106  test    byte ptr [rbx+4], 4
0x14000f10a  jnz     short loc_14000F115
0x14000f10c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000f113  jz      short loc_14000F126
0x14000f115  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000f11c  test    rax, rax
0x14000f11f  jz      short loc_14000F126
0x14000f121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f126  mov     rbx, [rsp+78h+arg_10]
0x14000f12e  add     rsp, 40h
0x14000f132  pop     r15
0x14000f134  pop     r14
0x14000f136  pop     r13
0x14000f138  pop     r12
0x14000f13a  pop     rdi
0x14000f13b  pop     rsi
0x14000f13c  pop     rbp
0x14000f13d  retn
0x14000f13e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
