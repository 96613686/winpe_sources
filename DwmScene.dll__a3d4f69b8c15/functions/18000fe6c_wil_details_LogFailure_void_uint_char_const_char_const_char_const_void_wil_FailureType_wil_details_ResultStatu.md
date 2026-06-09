# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000fe6c`
- end: `0x180010165`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000e328`
- `0x18000e66c`

## callees

- `0x18000e268`
- `0x18000f4b4`
- `0x18000fc7c`
- `0x18000fe6c`
- `0x1800104ec`
- `0x180010510`
- `0x180010524`
- `0x180010540`
- `0x1800112fc`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ff8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ff8f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010120`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010120`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800100ae`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800100ae`

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

  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW(lpOutputString);
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
0x18000fe6c  mov     [rsp+arg_10], rbx
0x18000fe71  mov     [rsp+arg_8], edx
0x18000fe75  mov     [rsp+arg_0], rcx
0x18000fe7a  push    rbp
0x18000fe7b  push    rsi
0x18000fe7c  push    rdi
0x18000fe7d  push    r12
0x18000fe7f  push    r13
0x18000fe81  push    r14
0x18000fe83  push    r15
0x18000fe85  sub     rsp, 40h
0x18000fe89  mov     r12, r9
0x18000fe8c  mov     r13, r8
0x18000fe8f  mov     r10, rcx
0x18000fe92  xor     eax, eax
0x18000fe94  mov     rsi, [rsp+78h+lpOutputString]
0x18000fe9c  mov     [rsi], ax
0x18000fe9f  mov     rax, [rsp+78h+arg_60]
0x18000fea7  mov     byte ptr [rax], 0
0x18000feaa  mov     r14, [rsp+78h+arg_38]
0x18000feb2  mov     edi, [r14]
0x18000feb5  mov     rbx, [rsp+78h+arg_78]
0x18000febd  mov     [rbx+8], edi
0x18000fec0  mov     eax, [r14+4]
0x18000fec4  mov     [rbx+0Ch], eax
0x18000fec7  xor     ebp, ebp
0x18000fec9  mov     r15d, [rsp+78h+arg_30]
0x18000fed1  mov     ecx, r15d
0x18000fed4  test    r15d, r15d
0x18000fed7  jz      short loc_18000FF3F
0x18000fed9  sub     ecx, 1
0x18000fedc  jz      short loc_18000FF36
0x18000fede  sub     ecx, 1
0x18000fee1  jz      short loc_18000FEF1
0x18000fee3  cmp     ecx, 1
0x18000fee6  jnz     short loc_18000FF48
0x18000fee8  mov     ecx, edi; this
0x18000feea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000feef  jmp     short loc_18000FF46
0x18000fef1  test    edi, edi
0x18000fef3  js      short loc_18000FF2D
0x18000fef5  mov     edi, 8007029Ch
0x18000fefa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000fefe  mov     rax, [rsp+78h+arg_28]
0x18000ff06  mov     [rsp+78h+var_50], rax; __int64
0x18000ff0b  mov     rax, [rsp+78h+arg_20]
0x18000ff13  mov     [rsp+78h+var_58], rax; __int64
0x18000ff18  mov     rcx, r10; int
0x18000ff1b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000ff20  mov     [rbx+8], edi
0x18000ff23  mov     ecx, edi; this
0x18000ff25  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ff2a  mov     [rbx+0Ch], eax
0x18000ff2d  mov     ecx, edi; this
0x18000ff2f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000ff34  jmp     short loc_18000FF46
0x18000ff36  mov     ecx, edi; this
0x18000ff38  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000ff3d  jmp     short loc_18000FF46
0x18000ff3f  mov     ecx, edi; this
0x18000ff41  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000ff46  mov     ebp, eax
0x18000ff48  mov     [rbx], r15d
0x18000ff4b  mov     eax, [rsp+78h+arg_70]
0x18000ff52  mov     [rbx+4], eax
0x18000ff55  cmp     dword ptr [r14+8], 1
0x18000ff5a  jnz     short loc_18000FF62
0x18000ff5c  or      eax, 8
0x18000ff5f  mov     [rbx+4], eax
0x18000ff62  mov     eax, 1
0x18000ff67  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ff6f  inc     eax
0x18000ff71  mov     [rbx+10h], eax
0x18000ff74  mov     rax, [rsp+78h+arg_40]
0x18000ff7c  xor     edi, edi
0x18000ff7e  test    rax, rax
0x18000ff81  jz      short loc_18000FF88
0x18000ff83  cmp     [rax], di
0x18000ff86  jnz     short loc_18000FF8B
0x18000ff88  mov     rax, rdi
0x18000ff8b  mov     [rbx+18h], rax
0x18000ff8f  call    cs:__imp_GetCurrentThreadId
0x18000ff95  mov     [rbx+20h], eax
0x18000ff98  mov     [rbx+38h], r13
0x18000ff9c  mov     eax, [rsp+78h+arg_8]
0x18000ffa3  mov     [rbx+40h], eax
0x18000ffa6  mov     [rbx+44h], ebp
0x18000ffa9  mov     rax, [rsp+78h+arg_20]
0x18000ffb1  mov     [rbx+28h], rax
0x18000ffb5  mov     [rbx+30h], r12
0x18000ffb9  mov     rax, [rsp+78h+arg_28]
0x18000ffc1  mov     [rbx+88h], rax
0x18000ffc8  mov     rax, [rsp+78h+arg_0]
0x18000ffd0  mov     [rbx+90h], rax
0x18000ffd7  mov     [rbx+48h], rdi
0x18000ffdb  xorps   xmm0, xmm0
0x18000ffde  xor     eax, eax
0x18000ffe0  movups  xmmword ptr [rbx+68h], xmm0
0x18000ffe4  mov     [rbx+78h], rax
0x18000ffe8  movups  xmmword ptr [rbx+50h], xmm0
0x18000ffec  mov     [rbx+60h], rax
0x18000fff0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000fff7  test    rax, rax
0x18000fffa  jz      short loc_180010003
0x18000fffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010001  jmp     short loc_180010006
0x180010003  mov     rax, rdi
0x180010006  mov     [rbx+80h], rax
0x18001000d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180010014  test    rax, rax
0x180010017  jz      short loc_180010021
0x180010019  mov     rcx, rbx
0x18001001c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010021  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180010028  test    rax, rax
0x18001002b  jz      short loc_180010043
0x18001002d  mov     r8d, 400h
0x180010033  mov     rdx, [rsp+78h+arg_60]
0x18001003b  mov     rcx, rbx
0x18001003e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010043  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001004a  test    rax, rax
0x18001004d  jz      short loc_180010057
0x18001004f  mov     rcx, rbx
0x180010052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010057  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001005e  test    rax, rax
0x180010061  jz      short loc_180010071
0x180010063  test    byte ptr [rbx+4], 2
0x180010067  jnz     short loc_180010071
0x180010069  mov     rcx, rbx
0x18001006c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010071  cmp     [rbx+8], edi
0x180010074  jl      short loc_180010090
0x180010076  cmp     r15d, 3
0x18001007a  jnz     loc_18001015F
0x180010080  mov     ecx, 8000FFFFh; this
0x180010085  mov     [rbx+8], ecx
0x180010088  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001008d  mov     [rbx+0Ch], eax
0x180010090  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180010097  jnz     short loc_1800100B8
0x180010099  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800100a0  test    rax, rax
0x1800100a3  jz      short loc_1800100AE
0x1800100a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100aa  test    al, al
0x1800100ac  jmp     short loc_1800100B6
0x1800100ae  call    cs:__imp_IsDebuggerPresent
0x1800100b4  test    eax, eax
0x1800100b6  jz      short loc_1800100BE
0x1800100b8  test    byte ptr [rbx+4], 2
0x1800100bc  jz      short loc_1800100E2
0x1800100be  mov     rax, cs:g_pfnResultLoggingCallback
0x1800100c5  test    rax, rax
0x1800100c8  jz      short loc_180010126
0x1800100ca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800100d1  jnz     short loc_180010126
0x1800100d3  xor     r8d, r8d
0x1800100d6  xor     edx, edx
0x1800100d8  mov     rcx, rbx
0x1800100db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100e0  jmp     short loc_180010126
0x1800100e2  mov     ebp, 800h
0x1800100e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800100ee  test    rax, rax
0x1800100f1  jz      short loc_18001010A
0x1800100f3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800100fa  jnz     short loc_18001010A
0x1800100fc  mov     r8d, ebp
0x1800100ff  mov     rdx, rsi
0x180010102  mov     rcx, rbx
0x180010105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001010a  cmp     [rsi], di
0x18001010d  jnz     short loc_18001011D
0x18001010f  mov     r8, rbx; unsigned __int64
0x180010112  mov     rdx, rbp; wchar_t *
0x180010115  mov     rcx, rsi; pszDest
0x180010118  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18001011d  mov     rcx, rsi; lpOutputString
0x180010120  call    cs:__imp_OutputDebugStringW
0x180010126  test    byte ptr [rbx+4], 4
0x18001012a  jnz     short loc_180010135
0x18001012c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180010133  jz      short loc_180010147
0x180010135  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001013c  test    rax, rax
0x18001013f  jz      short loc_180010147
0x180010141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010146  nop
0x180010147  mov     rbx, [rsp+78h+arg_10]
0x18001014f  add     rsp, 40h
0x180010153  pop     r15
0x180010155  pop     r14
0x180010157  pop     r13
0x180010159  pop     r12
0x18001015b  pop     rdi
0x18001015c  pop     rsi
0x18001015d  pop     rbp
0x18001015e  retn
0x18001015f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
