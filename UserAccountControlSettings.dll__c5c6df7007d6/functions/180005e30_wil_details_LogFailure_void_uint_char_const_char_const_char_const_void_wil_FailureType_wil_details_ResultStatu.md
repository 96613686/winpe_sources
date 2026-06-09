# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005e30`
- end: `0x180006128`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, WCHAR *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180004520`
- `0x180004870`

## callees

- `0x180004468`
- `0x1800053f4`
- `0x180005bc4`
- `0x180005e30`
- `0x1800064ec`
- `0x180006510`
- `0x180006524`
- `0x180006540`
- `0x180007050`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f53`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800060e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800060e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006072`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006072`

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
        WCHAR *lpOutputString,
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
  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW(lpOutputString);
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
0x180005e30  mov     [rsp+arg_10], rbx
0x180005e35  mov     [rsp+arg_8], edx
0x180005e39  mov     [rsp+arg_0], rcx
0x180005e3e  push    rbp
0x180005e3f  push    rsi
0x180005e40  push    rdi
0x180005e41  push    r12
0x180005e43  push    r13
0x180005e45  push    r14
0x180005e47  push    r15
0x180005e49  sub     rsp, 40h
0x180005e4d  mov     r14, [rsp+78h+arg_38]
0x180005e55  xor     eax, eax
0x180005e57  mov     rbx, [rsp+78h+arg_78]
0x180005e5f  xor     ebp, ebp
0x180005e61  mov     r15d, [rsp+78h+arg_30]
0x180005e69  mov     r10, rcx
0x180005e6c  mov     rsi, [rsp+78h+lpOutputString]
0x180005e74  mov     r12, r9
0x180005e77  mov     r13, r8
0x180005e7a  mov     ecx, r15d
0x180005e7d  mov     [rsi], ax
0x180005e80  mov     rax, [rsp+78h+arg_60]
0x180005e88  mov     byte ptr [rax], 0
0x180005e8b  mov     edi, [r14]
0x180005e8e  mov     [rbx+8], edi
0x180005e91  mov     eax, [r14+4]
0x180005e95  mov     [rbx+0Ch], eax
0x180005e98  test    r15d, r15d
0x180005e9b  jz      short loc_180005F03
0x180005e9d  sub     ecx, 1
0x180005ea0  jz      short loc_180005EFA
0x180005ea2  sub     ecx, 1
0x180005ea5  jz      short loc_180005EB5
0x180005ea7  cmp     ecx, 1
0x180005eaa  jnz     short loc_180005F0C
0x180005eac  mov     ecx, edi; this
0x180005eae  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005eb3  jmp     short loc_180005F0A
0x180005eb5  test    edi, edi
0x180005eb7  js      short loc_180005EF1
0x180005eb9  mov     rax, [rsp+78h+arg_28]
0x180005ec1  mov     edi, 8007029Ch
0x180005ec6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005eca  mov     rcx, r10; int
0x180005ecd  mov     [rsp+78h+var_50], rax; __int64
0x180005ed2  mov     rax, [rsp+78h+arg_20]
0x180005eda  mov     [rsp+78h+var_58], rax; __int64
0x180005edf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005ee4  mov     ecx, edi; this
0x180005ee6  mov     [rbx+8], edi
0x180005ee9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005eee  mov     [rbx+0Ch], eax
0x180005ef1  mov     ecx, edi; this
0x180005ef3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005ef8  jmp     short loc_180005F0A
0x180005efa  mov     ecx, edi; this
0x180005efc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005f01  jmp     short loc_180005F0A
0x180005f03  mov     ecx, edi; this
0x180005f05  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005f0a  mov     ebp, eax
0x180005f0c  mov     eax, [rsp+78h+arg_70]
0x180005f13  mov     [rbx+4], eax
0x180005f16  mov     [rbx], r15d
0x180005f19  cmp     dword ptr [r14+8], 1
0x180005f1e  jnz     short loc_180005F26
0x180005f20  or      eax, 8
0x180005f23  mov     [rbx+4], eax
0x180005f26  mov     eax, 1
0x180005f2b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005f33  inc     eax
0x180005f35  xor     edi, edi
0x180005f37  mov     [rbx+10h], eax
0x180005f3a  mov     rax, [rsp+78h+arg_40]
0x180005f42  test    rax, rax
0x180005f45  jz      short loc_180005F4C
0x180005f47  cmp     [rax], di
0x180005f4a  jnz     short loc_180005F4F
0x180005f4c  mov     rax, rdi
0x180005f4f  mov     [rbx+18h], rax
0x180005f53  call    cs:__imp_GetCurrentThreadId
0x180005f59  mov     [rbx+38h], r13
0x180005f5d  xorps   xmm0, xmm0
0x180005f60  mov     [rbx+20h], eax
0x180005f63  mov     eax, [rsp+78h+arg_8]
0x180005f6a  mov     [rbx+40h], eax
0x180005f6d  mov     rax, [rsp+78h+arg_20]
0x180005f75  mov     [rbx+28h], rax
0x180005f79  mov     rax, [rsp+78h+arg_28]
0x180005f81  mov     [rbx+88h], rax
0x180005f88  mov     rax, [rsp+78h+arg_0]
0x180005f90  mov     [rbx+90h], rax
0x180005f97  xor     eax, eax
0x180005f99  mov     [rbx+44h], ebp
0x180005f9c  mov     [rbx+30h], r12
0x180005fa0  mov     [rbx+48h], rdi
0x180005fa4  movups  xmmword ptr [rbx+68h], xmm0
0x180005fa8  mov     [rbx+78h], rax
0x180005fac  movups  xmmword ptr [rbx+50h], xmm0
0x180005fb0  mov     [rbx+60h], rax
0x180005fb4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005fbb  test    rax, rax
0x180005fbe  jz      short loc_180005FC7
0x180005fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fc5  jmp     short loc_180005FCA
0x180005fc7  mov     rax, rdi
0x180005fca  mov     [rbx+80h], rax
0x180005fd1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005fd8  test    rax, rax
0x180005fdb  jz      short loc_180005FE5
0x180005fdd  mov     rcx, rbx
0x180005fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fe5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005fec  test    rax, rax
0x180005fef  jz      short loc_180006007
0x180005ff1  mov     rdx, [rsp+78h+arg_60]
0x180005ff9  mov     r8d, 400h
0x180005fff  mov     rcx, rbx
0x180006002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006007  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000600e  test    rax, rax
0x180006011  jz      short loc_18000601B
0x180006013  mov     rcx, rbx
0x180006016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000601b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006022  test    rax, rax
0x180006025  jz      short loc_180006035
0x180006027  test    byte ptr [rbx+4], 2
0x18000602b  jnz     short loc_180006035
0x18000602d  mov     rcx, rbx
0x180006030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006035  cmp     [rbx+8], edi
0x180006038  jl      short loc_180006054
0x18000603a  cmp     r15d, 3
0x18000603e  jnz     loc_180006122
0x180006044  mov     ecx, 8000FFFFh; this
0x180006049  mov     [rbx+8], ecx
0x18000604c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006051  mov     [rbx+0Ch], eax
0x180006054  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000605b  jnz     short loc_18000607C
0x18000605d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006064  test    rax, rax
0x180006067  jz      short loc_180006072
0x180006069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000606e  test    al, al
0x180006070  jmp     short loc_18000607A
0x180006072  call    cs:__imp_IsDebuggerPresent
0x180006078  test    eax, eax
0x18000607a  jz      short loc_180006082
0x18000607c  test    byte ptr [rbx+4], 2
0x180006080  jz      short loc_1800060A6
0x180006082  mov     rax, cs:g_pfnResultLoggingCallback
0x180006089  test    rax, rax
0x18000608c  jz      short loc_1800060EA
0x18000608e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006095  jnz     short loc_1800060EA
0x180006097  xor     r8d, r8d
0x18000609a  xor     edx, edx
0x18000609c  mov     rcx, rbx
0x18000609f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060a4  jmp     short loc_1800060EA
0x1800060a6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800060ad  mov     ebp, 800h
0x1800060b2  test    rax, rax
0x1800060b5  jz      short loc_1800060CE
0x1800060b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800060be  jnz     short loc_1800060CE
0x1800060c0  mov     r8d, ebp
0x1800060c3  mov     rdx, rsi
0x1800060c6  mov     rcx, rbx
0x1800060c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ce  cmp     [rsi], di
0x1800060d1  jnz     short loc_1800060E1
0x1800060d3  mov     r8, rbx; unsigned __int64
0x1800060d6  mov     rdx, rbp; unsigned __int16 *
0x1800060d9  mov     rcx, rsi; pszDest
0x1800060dc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800060e1  mov     rcx, rsi; lpOutputString
0x1800060e4  call    cs:__imp_OutputDebugStringW
0x1800060ea  test    byte ptr [rbx+4], 4
0x1800060ee  jnz     short loc_1800060F9
0x1800060f0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800060f7  jz      short loc_18000610A
0x1800060f9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006100  test    rax, rax
0x180006103  jz      short loc_18000610A
0x180006105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000610a  mov     rbx, [rsp+78h+arg_10]
0x180006112  add     rsp, 40h
0x180006116  pop     r15
0x180006118  pop     r14
0x18000611a  pop     r13
0x18000611c  pop     r12
0x18000611e  pop     rdi
0x18000611f  pop     rsi
0x180006120  pop     rbp
0x180006121  retn
0x180006122  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
