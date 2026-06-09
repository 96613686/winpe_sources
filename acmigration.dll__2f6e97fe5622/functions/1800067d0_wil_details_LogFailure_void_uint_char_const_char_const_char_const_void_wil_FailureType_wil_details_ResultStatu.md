# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800067d0`
- end: `0x180006ad1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003b44`

## callees

- `0x18000353c`
- `0x180005d64`
- `0x180006524`
- `0x1800067d0`
- `0x180007564`
- `0x180007580`
- `0x1800076b4`
- `0x1800076d0`
- `0x180009ccc`
- `0x18006a010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180006a1a`
- `KERNEL32!IsDebuggerPresent` at `0x180006a1a`
- `KERNEL32!OutputDebugStringW` at `0x180006a8c`
- `KERNEL32!OutputDebugStringW` at `0x180006a8c`
- `KERNEL32!GetCurrentThreadId` at `0x1800068fb`
- `KERNEL32!GetCurrentThreadId` at `0x1800068fb`

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
  wil::details *v28; // [rsp+30h] [rbp-58h]

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
0x1800067d0  mov     rax, rsp
0x1800067d3  mov     [rax+10h], edx
0x1800067d6  mov     [rax+8], rcx
0x1800067da  push    rbp
0x1800067db  push    rsi
0x1800067dc  push    rdi
0x1800067dd  push    r12
0x1800067df  push    r13
0x1800067e1  push    r14
0x1800067e3  push    r15
0x1800067e5  sub     rsp, 50h
0x1800067e9  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800067f1  mov     [rax+18h], rbx
0x1800067f5  mov     r12, r9
0x1800067f8  mov     r13, r8
0x1800067fb  mov     r10, rcx
0x1800067fe  xor     eax, eax
0x180006800  mov     rsi, [rsp+88h+lpOutputString]
0x180006808  mov     [rsi], ax
0x18000680b  mov     rax, [rsp+88h+arg_60]
0x180006813  mov     byte ptr [rax], 0
0x180006816  mov     r14, [rsp+88h+arg_38]
0x18000681e  mov     edi, [r14]
0x180006821  mov     rbx, [rsp+88h+arg_78]
0x180006829  mov     [rbx+8], edi
0x18000682c  mov     eax, [r14+4]
0x180006830  mov     [rbx+0Ch], eax
0x180006833  xor     ebp, ebp
0x180006835  mov     r15d, [rsp+88h+arg_30]
0x18000683d  mov     ecx, r15d
0x180006840  test    r15d, r15d
0x180006843  jz      short loc_1800068AB
0x180006845  sub     ecx, 1
0x180006848  jz      short loc_1800068A2
0x18000684a  sub     ecx, 1
0x18000684d  jz      short loc_18000685D
0x18000684f  cmp     ecx, 1
0x180006852  jnz     short loc_1800068B4
0x180006854  mov     ecx, edi; this
0x180006856  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000685b  jmp     short loc_1800068B2
0x18000685d  test    edi, edi
0x18000685f  js      short loc_180006899
0x180006861  mov     edi, 8007029Ch
0x180006866  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x18000686a  mov     rax, [rsp+88h+arg_28]
0x180006872  mov     [rsp+88h+var_60], rax; __int64
0x180006877  mov     rax, [rsp+88h+arg_20]
0x18000687f  mov     [rsp+88h+var_68], rax; __int64
0x180006884  mov     rcx, r10; int
0x180006887  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000688c  mov     [rbx+8], edi
0x18000688f  mov     ecx, edi; this
0x180006891  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006896  mov     [rbx+0Ch], eax
0x180006899  mov     ecx, edi; this
0x18000689b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800068a0  jmp     short loc_1800068B2
0x1800068a2  mov     ecx, edi; this
0x1800068a4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800068a9  jmp     short loc_1800068B2
0x1800068ab  mov     ecx, edi; this
0x1800068ad  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800068b2  mov     ebp, eax
0x1800068b4  mov     [rbx], r15d
0x1800068b7  mov     eax, [rsp+88h+arg_70]
0x1800068be  mov     [rbx+4], eax
0x1800068c1  cmp     dword ptr [r14+8], 1
0x1800068c6  jnz     short loc_1800068CE
0x1800068c8  or      eax, 8
0x1800068cb  mov     [rbx+4], eax
0x1800068ce  mov     eax, 1
0x1800068d3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800068db  inc     eax
0x1800068dd  mov     [rbx+10h], eax
0x1800068e0  mov     rax, [rsp+88h+arg_40]
0x1800068e8  xor     edi, edi
0x1800068ea  test    rax, rax
0x1800068ed  jz      short loc_1800068F4
0x1800068ef  cmp     [rax], di
0x1800068f2  jnz     short loc_1800068F7
0x1800068f4  mov     rax, rdi
0x1800068f7  mov     [rbx+18h], rax
0x1800068fb  call    cs:__imp_GetCurrentThreadId
0x180006901  mov     [rbx+20h], eax
0x180006904  mov     [rbx+38h], r13
0x180006908  mov     eax, [rsp+88h+arg_8]
0x18000690f  mov     [rbx+40h], eax
0x180006912  mov     [rbx+44h], ebp
0x180006915  mov     rax, [rsp+88h+arg_20]
0x18000691d  mov     [rbx+28h], rax
0x180006921  mov     [rbx+30h], r12
0x180006925  mov     rax, [rsp+88h+arg_28]
0x18000692d  mov     [rbx+88h], rax
0x180006934  mov     rax, [rsp+88h+arg_0]
0x18000693c  mov     [rbx+90h], rax
0x180006943  mov     [rbx+48h], rdi
0x180006947  xorps   xmm0, xmm0
0x18000694a  xor     eax, eax
0x18000694c  movups  xmmword ptr [rbx+68h], xmm0
0x180006950  mov     [rbx+78h], rax
0x180006954  movups  xmmword ptr [rbx+50h], xmm0
0x180006958  mov     [rbx+60h], rax
0x18000695c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006963  test    rax, rax
0x180006966  jz      short loc_18000696F
0x180006968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000696d  jmp     short loc_180006972
0x18000696f  mov     rax, rdi
0x180006972  mov     [rbx+80h], rax
0x180006979  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006980  test    rax, rax
0x180006983  jz      short loc_18000698D
0x180006985  mov     rcx, rbx
0x180006988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000698d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006994  test    rax, rax
0x180006997  jz      short loc_1800069AF
0x180006999  mov     r8d, 400h
0x18000699f  mov     rdx, [rsp+88h+arg_60]
0x1800069a7  mov     rcx, rbx
0x1800069aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069af  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800069b6  test    rax, rax
0x1800069b9  jz      short loc_1800069C3
0x1800069bb  mov     rcx, rbx
0x1800069be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069c3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800069ca  test    rax, rax
0x1800069cd  jz      short loc_1800069DD
0x1800069cf  test    byte ptr [rbx+4], 2
0x1800069d3  jnz     short loc_1800069DD
0x1800069d5  mov     rcx, rbx
0x1800069d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069dd  cmp     [rbx+8], edi
0x1800069e0  jl      short loc_1800069FC
0x1800069e2  cmp     r15d, 3
0x1800069e6  jnz     loc_180006ACB
0x1800069ec  mov     ecx, 8000FFFFh; this
0x1800069f1  mov     [rbx+8], ecx
0x1800069f4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800069f9  mov     [rbx+0Ch], eax
0x1800069fc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006a03  jnz     short loc_180006A24
0x180006a05  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006a0c  test    rax, rax
0x180006a0f  jz      short loc_180006A1A
0x180006a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a16  test    al, al
0x180006a18  jmp     short loc_180006A22
0x180006a1a  call    cs:__imp_IsDebuggerPresent
0x180006a20  test    eax, eax
0x180006a22  jz      short loc_180006A2A
0x180006a24  test    byte ptr [rbx+4], 2
0x180006a28  jz      short loc_180006A4E
0x180006a2a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006a31  test    rax, rax
0x180006a34  jz      short loc_180006A92
0x180006a36  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006a3d  jnz     short loc_180006A92
0x180006a3f  xor     r8d, r8d
0x180006a42  xor     edx, edx
0x180006a44  mov     rcx, rbx
0x180006a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a4c  jmp     short loc_180006A92
0x180006a4e  mov     ebp, 800h
0x180006a53  mov     rax, cs:g_pfnResultLoggingCallback
0x180006a5a  test    rax, rax
0x180006a5d  jz      short loc_180006A76
0x180006a5f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006a66  jnz     short loc_180006A76
0x180006a68  mov     r8d, ebp
0x180006a6b  mov     rdx, rsi
0x180006a6e  mov     rcx, rbx
0x180006a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a76  cmp     [rsi], di
0x180006a79  jnz     short loc_180006A89
0x180006a7b  mov     r8, rbx; unsigned __int64
0x180006a7e  mov     rdx, rbp; unsigned __int16 *
0x180006a81  mov     rcx, rsi; this
0x180006a84  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006a89  mov     rcx, rsi; lpOutputString
0x180006a8c  call    cs:__imp_OutputDebugStringW
0x180006a92  test    byte ptr [rbx+4], 4
0x180006a96  jnz     short loc_180006AA1
0x180006a98  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006a9f  jz      short loc_180006AB3
0x180006aa1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006aa8  test    rax, rax
0x180006aab  jz      short loc_180006AB3
0x180006aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab2  nop
0x180006ab3  mov     rbx, [rsp+88h+arg_10]
0x180006abb  add     rsp, 50h
0x180006abf  pop     r15
0x180006ac1  pop     r14
0x180006ac3  pop     r13
0x180006ac5  pop     r12
0x180006ac7  pop     rdi
0x180006ac8  pop     rsi
0x180006ac9  pop     rbp
0x180006aca  retn
0x180006acb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
