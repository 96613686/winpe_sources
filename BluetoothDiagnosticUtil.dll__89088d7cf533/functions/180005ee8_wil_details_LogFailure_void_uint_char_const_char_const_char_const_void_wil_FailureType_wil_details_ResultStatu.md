# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005ee8`
- end: `0x1800061f4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002a28`

## callees

- `0x1800020e8`
- `0x180005304`
- `0x180005bc4`
- `0x180005ee8`
- `0x180006cd4`
- `0x180006d00`
- `0x180006d14`
- `0x180006d34`
- `0x180008058`
- `0x18000b010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1800061a8`
- `KERNEL32!OutputDebugStringW` at `0x1800061a8`
- `KERNEL32!IsDebuggerPresent` at `0x180006130`
- `KERNEL32!IsDebuggerPresent` at `0x180006130`
- `KERNEL32!GetCurrentThreadId` at `0x18000600b`
- `KERNEL32!GetCurrentThreadId` at `0x18000600b`

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
0x180005ee8  mov     [rsp+arg_10], rbx
0x180005eed  mov     [rsp+arg_8], edx
0x180005ef1  mov     [rsp+arg_0], rcx
0x180005ef6  push    rbp
0x180005ef7  push    rsi
0x180005ef8  push    rdi
0x180005ef9  push    r12
0x180005efb  push    r13
0x180005efd  push    r14
0x180005eff  push    r15
0x180005f01  sub     rsp, 40h
0x180005f05  mov     r12, r9
0x180005f08  mov     r13, r8
0x180005f0b  mov     r10, rcx
0x180005f0e  xor     eax, eax
0x180005f10  mov     rsi, [rsp+78h+lpOutputString]
0x180005f18  mov     [rsi], ax
0x180005f1b  mov     rax, [rsp+78h+arg_60]
0x180005f23  mov     byte ptr [rax], 0
0x180005f26  mov     r14, [rsp+78h+arg_38]
0x180005f2e  mov     edi, [r14]
0x180005f31  mov     rbx, [rsp+78h+arg_78]
0x180005f39  mov     [rbx+8], edi
0x180005f3c  mov     eax, [r14+4]
0x180005f40  mov     [rbx+0Ch], eax
0x180005f43  xor     ebp, ebp
0x180005f45  mov     r15d, [rsp+78h+arg_30]
0x180005f4d  mov     ecx, r15d
0x180005f50  test    r15d, r15d
0x180005f53  jz      short loc_180005FBB
0x180005f55  sub     ecx, 1
0x180005f58  jz      short loc_180005FB2
0x180005f5a  sub     ecx, 1
0x180005f5d  jz      short loc_180005F6D
0x180005f5f  cmp     ecx, 1
0x180005f62  jnz     short loc_180005FC4
0x180005f64  mov     ecx, edi; this
0x180005f66  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005f6b  jmp     short loc_180005FC2
0x180005f6d  test    edi, edi
0x180005f6f  js      short loc_180005FA9
0x180005f71  mov     edi, 8007029Ch
0x180005f76  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005f7a  mov     rax, [rsp+78h+arg_28]
0x180005f82  mov     [rsp+78h+var_50], rax; __int64
0x180005f87  mov     rax, [rsp+78h+arg_20]
0x180005f8f  mov     [rsp+78h+var_58], rax; __int64
0x180005f94  mov     rcx, r10; int
0x180005f97  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005f9c  mov     [rbx+8], edi
0x180005f9f  mov     ecx, edi; this
0x180005fa1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005fa6  mov     [rbx+0Ch], eax
0x180005fa9  mov     ecx, edi; this
0x180005fab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005fb0  jmp     short loc_180005FC2
0x180005fb2  mov     ecx, edi; this
0x180005fb4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005fb9  jmp     short loc_180005FC2
0x180005fbb  mov     ecx, edi; this
0x180005fbd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005fc2  mov     ebp, eax
0x180005fc4  mov     [rbx], r15d
0x180005fc7  mov     eax, [rsp+78h+arg_70]
0x180005fce  mov     [rbx+4], eax
0x180005fd1  cmp     dword ptr [r14+8], 1
0x180005fd6  jnz     short loc_180005FDE
0x180005fd8  or      eax, 8
0x180005fdb  mov     [rbx+4], eax
0x180005fde  mov     eax, 1
0x180005fe3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005feb  inc     eax
0x180005fed  mov     [rbx+10h], eax
0x180005ff0  mov     rax, [rsp+78h+arg_40]
0x180005ff8  xor     edi, edi
0x180005ffa  test    rax, rax
0x180005ffd  jz      short loc_180006004
0x180005fff  cmp     [rax], di
0x180006002  jnz     short loc_180006007
0x180006004  mov     rax, rdi
0x180006007  mov     [rbx+18h], rax
0x18000600b  call    cs:__imp_GetCurrentThreadId
0x180006012  nop     dword ptr [rax+rax+00h]
0x180006017  mov     [rbx+20h], eax
0x18000601a  mov     [rbx+38h], r13
0x18000601e  mov     eax, [rsp+78h+arg_8]
0x180006025  mov     [rbx+40h], eax
0x180006028  mov     [rbx+44h], ebp
0x18000602b  mov     rax, [rsp+78h+arg_20]
0x180006033  mov     [rbx+28h], rax
0x180006037  mov     [rbx+30h], r12
0x18000603b  mov     rax, [rsp+78h+arg_28]
0x180006043  mov     [rbx+88h], rax
0x18000604a  mov     rax, [rsp+78h+arg_0]
0x180006052  mov     [rbx+90h], rax
0x180006059  mov     [rbx+48h], rdi
0x18000605d  xorps   xmm0, xmm0
0x180006060  xor     eax, eax
0x180006062  movups  xmmword ptr [rbx+68h], xmm0
0x180006066  mov     [rbx+78h], rax
0x18000606a  movups  xmmword ptr [rbx+50h], xmm0
0x18000606e  mov     [rbx+60h], rax
0x180006072  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006079  test    rax, rax
0x18000607c  jz      short loc_180006085
0x18000607e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006083  jmp     short loc_180006088
0x180006085  mov     rax, rdi
0x180006088  mov     [rbx+80h], rax
0x18000608f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006096  test    rax, rax
0x180006099  jz      short loc_1800060A3
0x18000609b  mov     rcx, rbx
0x18000609e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060a3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800060aa  test    rax, rax
0x1800060ad  jz      short loc_1800060C5
0x1800060af  mov     r8d, 400h
0x1800060b5  mov     rdx, [rsp+78h+arg_60]
0x1800060bd  mov     rcx, rbx
0x1800060c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800060cc  test    rax, rax
0x1800060cf  jz      short loc_1800060D9
0x1800060d1  mov     rcx, rbx
0x1800060d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060d9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800060e0  test    rax, rax
0x1800060e3  jz      short loc_1800060F3
0x1800060e5  test    byte ptr [rbx+4], 2
0x1800060e9  jnz     short loc_1800060F3
0x1800060eb  mov     rcx, rbx
0x1800060ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060f3  cmp     [rbx+8], edi
0x1800060f6  jl      short loc_180006112
0x1800060f8  cmp     r15d, 3
0x1800060fc  jnz     loc_1800061EE
0x180006102  mov     ecx, 8000FFFFh; this
0x180006107  mov     [rbx+8], ecx
0x18000610a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000610f  mov     [rbx+0Ch], eax
0x180006112  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006119  jnz     short loc_180006140
0x18000611b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006122  test    rax, rax
0x180006125  jz      short loc_180006130
0x180006127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000612c  test    al, al
0x18000612e  jmp     short loc_18000613E
0x180006130  call    cs:__imp_IsDebuggerPresent
0x180006137  nop     dword ptr [rax+rax+00h]
0x18000613c  test    eax, eax
0x18000613e  jz      short loc_180006146
0x180006140  test    byte ptr [rbx+4], 2
0x180006144  jz      short loc_18000616A
0x180006146  mov     rax, cs:g_pfnResultLoggingCallback
0x18000614d  test    rax, rax
0x180006150  jz      short loc_1800061B4
0x180006152  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006159  jnz     short loc_1800061B4
0x18000615b  xor     r8d, r8d
0x18000615e  xor     edx, edx
0x180006160  mov     rcx, rbx
0x180006163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006168  jmp     short loc_1800061B4
0x18000616a  mov     ebp, 800h
0x18000616f  mov     rax, cs:g_pfnResultLoggingCallback
0x180006176  test    rax, rax
0x180006179  jz      short loc_180006192
0x18000617b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006182  jnz     short loc_180006192
0x180006184  mov     r8d, ebp
0x180006187  mov     rdx, rsi
0x18000618a  mov     rcx, rbx
0x18000618d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006192  cmp     [rsi], di
0x180006195  jnz     short loc_1800061A5
0x180006197  mov     r8, rbx; unsigned __int64
0x18000619a  mov     rdx, rbp; unsigned __int16 *
0x18000619d  mov     rcx, rsi; this
0x1800061a0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800061a5  mov     rcx, rsi; lpOutputString
0x1800061a8  call    cs:__imp_OutputDebugStringW
0x1800061af  nop     dword ptr [rax+rax+00h]
0x1800061b4  test    byte ptr [rbx+4], 4
0x1800061b8  jnz     short loc_1800061C3
0x1800061ba  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800061c1  jz      short loc_1800061D5
0x1800061c3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800061ca  test    rax, rax
0x1800061cd  jz      short loc_1800061D5
0x1800061cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061d4  nop
0x1800061d5  mov     rbx, [rsp+78h+arg_10]
0x1800061dd  add     rsp, 40h
0x1800061e1  pop     r15
0x1800061e3  pop     r14
0x1800061e5  pop     r13
0x1800061e7  pop     r12
0x1800061e9  pop     rdi
0x1800061ea  pop     rsi
0x1800061eb  pop     rbp
0x1800061ec  retn
0x1800061ee  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
