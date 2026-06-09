# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000cb88`
- end: `0x18000ce80`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180006a10`

## callees

- `0x180005010`
- `0x180006454`
- `0x18000a70c`
- `0x18000c5fc`
- `0x18000cb88`
- `0x18000e29c`
- `0x18000e2b8`
- `0x18000e2d4`
- `0x1800107a0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cdca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cdca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ce3c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ce3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ccab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ccab`

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
0x18000cb88  mov     [rsp+arg_10], rbx
0x18000cb8d  mov     [rsp+arg_8], edx
0x18000cb91  mov     [rsp+arg_0], rcx
0x18000cb96  push    rbp
0x18000cb97  push    rsi
0x18000cb98  push    rdi
0x18000cb99  push    r12
0x18000cb9b  push    r13
0x18000cb9d  push    r14
0x18000cb9f  push    r15
0x18000cba1  sub     rsp, 40h
0x18000cba5  mov     r14, [rsp+78h+arg_38]
0x18000cbad  xor     eax, eax
0x18000cbaf  mov     rbx, [rsp+78h+arg_78]
0x18000cbb7  xor     ebp, ebp
0x18000cbb9  mov     r15d, [rsp+78h+arg_30]
0x18000cbc1  mov     r10, rcx
0x18000cbc4  mov     rsi, [rsp+78h+lpOutputString]
0x18000cbcc  mov     r12, r9
0x18000cbcf  mov     r13, r8
0x18000cbd2  mov     ecx, r15d
0x18000cbd5  mov     [rsi], ax
0x18000cbd8  mov     rax, [rsp+78h+arg_60]
0x18000cbe0  mov     byte ptr [rax], 0
0x18000cbe3  mov     edi, [r14]
0x18000cbe6  mov     [rbx+8], edi
0x18000cbe9  mov     eax, [r14+4]
0x18000cbed  mov     [rbx+0Ch], eax
0x18000cbf0  test    r15d, r15d
0x18000cbf3  jz      short loc_18000CC5B
0x18000cbf5  sub     ecx, 1
0x18000cbf8  jz      short loc_18000CC52
0x18000cbfa  sub     ecx, 1
0x18000cbfd  jz      short loc_18000CC0D
0x18000cbff  cmp     ecx, 1
0x18000cc02  jnz     short loc_18000CC64
0x18000cc04  mov     ecx, edi; this
0x18000cc06  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000cc0b  jmp     short loc_18000CC62
0x18000cc0d  test    edi, edi
0x18000cc0f  js      short loc_18000CC49
0x18000cc11  mov     rax, [rsp+78h+arg_28]
0x18000cc19  mov     edi, 8007029Ch
0x18000cc1e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000cc22  mov     rcx, r10; int
0x18000cc25  mov     [rsp+78h+var_50], rax; __int64
0x18000cc2a  mov     rax, [rsp+78h+arg_20]
0x18000cc32  mov     [rsp+78h+var_58], rax; __int64
0x18000cc37  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000cc3c  mov     ecx, edi; this
0x18000cc3e  mov     [rbx+8], edi
0x18000cc41  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000cc46  mov     [rbx+0Ch], eax
0x18000cc49  mov     ecx, edi; this
0x18000cc4b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000cc50  jmp     short loc_18000CC62
0x18000cc52  mov     ecx, edi; this
0x18000cc54  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000cc59  jmp     short loc_18000CC62
0x18000cc5b  mov     ecx, edi; this
0x18000cc5d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000cc62  mov     ebp, eax
0x18000cc64  mov     eax, [rsp+78h+arg_70]
0x18000cc6b  mov     [rbx+4], eax
0x18000cc6e  mov     [rbx], r15d
0x18000cc71  cmp     dword ptr [r14+8], 1
0x18000cc76  jnz     short loc_18000CC7E
0x18000cc78  or      eax, 8
0x18000cc7b  mov     [rbx+4], eax
0x18000cc7e  mov     eax, 1
0x18000cc83  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000cc8b  inc     eax
0x18000cc8d  xor     edi, edi
0x18000cc8f  mov     [rbx+10h], eax
0x18000cc92  mov     rax, [rsp+78h+arg_40]
0x18000cc9a  test    rax, rax
0x18000cc9d  jz      short loc_18000CCA4
0x18000cc9f  cmp     [rax], di
0x18000cca2  jnz     short loc_18000CCA7
0x18000cca4  mov     rax, rdi
0x18000cca7  mov     [rbx+18h], rax
0x18000ccab  call    cs:__imp_GetCurrentThreadId
0x18000ccb1  mov     [rbx+38h], r13
0x18000ccb5  xorps   xmm0, xmm0
0x18000ccb8  mov     [rbx+20h], eax
0x18000ccbb  mov     eax, [rsp+78h+arg_8]
0x18000ccc2  mov     [rbx+40h], eax
0x18000ccc5  mov     rax, [rsp+78h+arg_20]
0x18000cccd  mov     [rbx+28h], rax
0x18000ccd1  mov     rax, [rsp+78h+arg_28]
0x18000ccd9  mov     [rbx+88h], rax
0x18000cce0  mov     rax, [rsp+78h+arg_0]
0x18000cce8  mov     [rbx+90h], rax
0x18000ccef  xor     eax, eax
0x18000ccf1  mov     [rbx+44h], ebp
0x18000ccf4  mov     [rbx+30h], r12
0x18000ccf8  mov     [rbx+48h], rdi
0x18000ccfc  movups  xmmword ptr [rbx+68h], xmm0
0x18000cd00  mov     [rbx+78h], rax
0x18000cd04  movups  xmmword ptr [rbx+50h], xmm0
0x18000cd08  mov     [rbx+60h], rax
0x18000cd0c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000cd13  test    rax, rax
0x18000cd16  jz      short loc_18000CD1F
0x18000cd18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd1d  jmp     short loc_18000CD22
0x18000cd1f  mov     rax, rdi
0x18000cd22  mov     [rbx+80h], rax
0x18000cd29  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000cd30  test    rax, rax
0x18000cd33  jz      short loc_18000CD3D
0x18000cd35  mov     rcx, rbx
0x18000cd38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd3d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000cd44  test    rax, rax
0x18000cd47  jz      short loc_18000CD5F
0x18000cd49  mov     rdx, [rsp+78h+arg_60]
0x18000cd51  mov     r8d, 400h
0x18000cd57  mov     rcx, rbx
0x18000cd5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd5f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cd66  test    rax, rax
0x18000cd69  jz      short loc_18000CD73
0x18000cd6b  mov     rcx, rbx
0x18000cd6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd73  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cd7a  test    rax, rax
0x18000cd7d  jz      short loc_18000CD8D
0x18000cd7f  test    byte ptr [rbx+4], 2
0x18000cd83  jnz     short loc_18000CD8D
0x18000cd85  mov     rcx, rbx
0x18000cd88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd8d  cmp     [rbx+8], edi
0x18000cd90  jl      short loc_18000CDAC
0x18000cd92  cmp     r15d, 3
0x18000cd96  jnz     loc_18000CE7A
0x18000cd9c  mov     ecx, 8000FFFFh; this
0x18000cda1  mov     [rbx+8], ecx
0x18000cda4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000cda9  mov     [rbx+0Ch], eax
0x18000cdac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000cdb3  jnz     short loc_18000CDD4
0x18000cdb5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000cdbc  test    rax, rax
0x18000cdbf  jz      short loc_18000CDCA
0x18000cdc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdc6  test    al, al
0x18000cdc8  jmp     short loc_18000CDD2
0x18000cdca  call    cs:__imp_IsDebuggerPresent
0x18000cdd0  test    eax, eax
0x18000cdd2  jz      short loc_18000CDDA
0x18000cdd4  test    byte ptr [rbx+4], 2
0x18000cdd8  jz      short loc_18000CDFE
0x18000cdda  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cde1  test    rax, rax
0x18000cde4  jz      short loc_18000CE42
0x18000cde6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000cded  jnz     short loc_18000CE42
0x18000cdef  xor     r8d, r8d
0x18000cdf2  xor     edx, edx
0x18000cdf4  mov     rcx, rbx
0x18000cdf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdfc  jmp     short loc_18000CE42
0x18000cdfe  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ce05  mov     ebp, 800h
0x18000ce0a  test    rax, rax
0x18000ce0d  jz      short loc_18000CE26
0x18000ce0f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ce16  jnz     short loc_18000CE26
0x18000ce18  mov     r8d, ebp
0x18000ce1b  mov     rdx, rsi
0x18000ce1e  mov     rcx, rbx
0x18000ce21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce26  cmp     [rsi], di
0x18000ce29  jnz     short loc_18000CE39
0x18000ce2b  mov     r8, rbx; unsigned __int64
0x18000ce2e  mov     rdx, rbp; unsigned __int16 *
0x18000ce31  mov     rcx, rsi; this
0x18000ce34  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000ce39  mov     rcx, rsi; lpOutputString
0x18000ce3c  call    cs:__imp_OutputDebugStringW
0x18000ce42  test    byte ptr [rbx+4], 4
0x18000ce46  jnz     short loc_18000CE51
0x18000ce48  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000ce4f  jz      short loc_18000CE62
0x18000ce51  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000ce58  test    rax, rax
0x18000ce5b  jz      short loc_18000CE62
0x18000ce5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce62  mov     rbx, [rsp+78h+arg_10]
0x18000ce6a  add     rsp, 40h
0x18000ce6e  pop     r15
0x18000ce70  pop     r14
0x18000ce72  pop     r13
0x18000ce74  pop     r12
0x18000ce76  pop     rdi
0x18000ce77  pop     rsi
0x18000ce78  pop     rbp
0x18000ce79  retn
0x18000ce7a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
