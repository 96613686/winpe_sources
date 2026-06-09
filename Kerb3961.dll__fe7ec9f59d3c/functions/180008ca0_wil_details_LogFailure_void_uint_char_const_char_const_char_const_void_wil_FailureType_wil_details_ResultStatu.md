# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008ca0`
- end: `0x180008f98`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800045b8`

## callees

- `0x180004290`
- `0x180008018`
- `0x1800086f4`
- `0x180008ca0`
- `0x180009404`
- `0x180009420`
- `0x180009434`
- `0x180009450`
- `0x18000a074`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008ee2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008ee2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008f54`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008f54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008dc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008dc3`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180008ca0  mov     [rsp+arg_10], rbx
0x180008ca5  mov     [rsp+arg_8], edx
0x180008ca9  mov     [rsp+arg_0], rcx
0x180008cae  push    rbp
0x180008caf  push    rsi
0x180008cb0  push    rdi
0x180008cb1  push    r12
0x180008cb3  push    r13
0x180008cb5  push    r14
0x180008cb7  push    r15
0x180008cb9  sub     rsp, 40h
0x180008cbd  mov     r14, [rsp+78h+arg_38]
0x180008cc5  xor     eax, eax
0x180008cc7  mov     rbx, [rsp+78h+arg_78]
0x180008ccf  xor     ebp, ebp
0x180008cd1  mov     r15d, [rsp+78h+arg_30]
0x180008cd9  mov     r10, rcx
0x180008cdc  mov     rsi, [rsp+78h+lpOutputString]
0x180008ce4  mov     r12, r9
0x180008ce7  mov     r13, r8
0x180008cea  mov     ecx, r15d
0x180008ced  mov     [rsi], ax
0x180008cf0  mov     rax, [rsp+78h+arg_60]
0x180008cf8  mov     byte ptr [rax], 0
0x180008cfb  mov     edi, [r14]
0x180008cfe  mov     [rbx+8], edi
0x180008d01  mov     eax, [r14+4]
0x180008d05  mov     [rbx+0Ch], eax
0x180008d08  test    r15d, r15d
0x180008d0b  jz      short loc_180008D73
0x180008d0d  sub     ecx, 1
0x180008d10  jz      short loc_180008D6A
0x180008d12  sub     ecx, 1
0x180008d15  jz      short loc_180008D25
0x180008d17  cmp     ecx, 1
0x180008d1a  jnz     short loc_180008D7C
0x180008d1c  mov     ecx, edi; this
0x180008d1e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008d23  jmp     short loc_180008D7A
0x180008d25  test    edi, edi
0x180008d27  js      short loc_180008D61
0x180008d29  mov     rax, [rsp+78h+arg_28]
0x180008d31  mov     edi, 8007029Ch
0x180008d36  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008d3a  mov     rcx, r10; int
0x180008d3d  mov     [rsp+78h+var_50], rax; __int64
0x180008d42  mov     rax, [rsp+78h+arg_20]
0x180008d4a  mov     [rsp+78h+var_58], rax; __int64
0x180008d4f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008d54  mov     ecx, edi; this
0x180008d56  mov     [rbx+8], edi
0x180008d59  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008d5e  mov     [rbx+0Ch], eax
0x180008d61  mov     ecx, edi; this
0x180008d63  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008d68  jmp     short loc_180008D7A
0x180008d6a  mov     ecx, edi; this
0x180008d6c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008d71  jmp     short loc_180008D7A
0x180008d73  mov     ecx, edi; this
0x180008d75  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008d7a  mov     ebp, eax
0x180008d7c  mov     eax, [rsp+78h+arg_70]
0x180008d83  mov     [rbx+4], eax
0x180008d86  mov     [rbx], r15d
0x180008d89  cmp     dword ptr [r14+8], 1
0x180008d8e  jnz     short loc_180008D96
0x180008d90  or      eax, 8
0x180008d93  mov     [rbx+4], eax
0x180008d96  mov     eax, 1
0x180008d9b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008da3  inc     eax
0x180008da5  xor     edi, edi
0x180008da7  mov     [rbx+10h], eax
0x180008daa  mov     rax, [rsp+78h+arg_40]
0x180008db2  test    rax, rax
0x180008db5  jz      short loc_180008DBC
0x180008db7  cmp     [rax], di
0x180008dba  jnz     short loc_180008DBF
0x180008dbc  mov     rax, rdi
0x180008dbf  mov     [rbx+18h], rax
0x180008dc3  call    cs:__imp_GetCurrentThreadId
0x180008dc9  mov     [rbx+38h], r13
0x180008dcd  xorps   xmm0, xmm0
0x180008dd0  mov     [rbx+20h], eax
0x180008dd3  mov     eax, [rsp+78h+arg_8]
0x180008dda  mov     [rbx+40h], eax
0x180008ddd  mov     rax, [rsp+78h+arg_20]
0x180008de5  mov     [rbx+28h], rax
0x180008de9  mov     rax, [rsp+78h+arg_28]
0x180008df1  mov     [rbx+88h], rax
0x180008df8  mov     rax, [rsp+78h+arg_0]
0x180008e00  mov     [rbx+90h], rax
0x180008e07  xor     eax, eax
0x180008e09  mov     [rbx+44h], ebp
0x180008e0c  mov     [rbx+30h], r12
0x180008e10  mov     [rbx+48h], rdi
0x180008e14  movups  xmmword ptr [rbx+68h], xmm0
0x180008e18  mov     [rbx+78h], rax
0x180008e1c  movups  xmmword ptr [rbx+50h], xmm0
0x180008e20  mov     [rbx+60h], rax
0x180008e24  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008e2b  test    rax, rax
0x180008e2e  jz      short loc_180008E37
0x180008e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e35  jmp     short loc_180008E3A
0x180008e37  mov     rax, rdi
0x180008e3a  mov     [rbx+80h], rax
0x180008e41  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008e48  test    rax, rax
0x180008e4b  jz      short loc_180008E55
0x180008e4d  mov     rcx, rbx
0x180008e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e55  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008e5c  test    rax, rax
0x180008e5f  jz      short loc_180008E77
0x180008e61  mov     rdx, [rsp+78h+arg_60]
0x180008e69  mov     r8d, 400h
0x180008e6f  mov     rcx, rbx
0x180008e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e77  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008e7e  test    rax, rax
0x180008e81  jz      short loc_180008E8B
0x180008e83  mov     rcx, rbx
0x180008e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e8b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008e92  test    rax, rax
0x180008e95  jz      short loc_180008EA5
0x180008e97  test    byte ptr [rbx+4], 2
0x180008e9b  jnz     short loc_180008EA5
0x180008e9d  mov     rcx, rbx
0x180008ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ea5  cmp     [rbx+8], edi
0x180008ea8  jl      short loc_180008EC4
0x180008eaa  cmp     r15d, 3
0x180008eae  jnz     loc_180008F92
0x180008eb4  mov     ecx, 8000FFFFh; this
0x180008eb9  mov     [rbx+8], ecx
0x180008ebc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008ec1  mov     [rbx+0Ch], eax
0x180008ec4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008ecb  jnz     short loc_180008EEC
0x180008ecd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008ed4  test    rax, rax
0x180008ed7  jz      short loc_180008EE2
0x180008ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ede  test    al, al
0x180008ee0  jmp     short loc_180008EEA
0x180008ee2  call    cs:__imp_IsDebuggerPresent
0x180008ee8  test    eax, eax
0x180008eea  jz      short loc_180008EF2
0x180008eec  test    byte ptr [rbx+4], 2
0x180008ef0  jz      short loc_180008F16
0x180008ef2  mov     rax, cs:g_pfnResultLoggingCallback
0x180008ef9  test    rax, rax
0x180008efc  jz      short loc_180008F5A
0x180008efe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008f05  jnz     short loc_180008F5A
0x180008f07  xor     r8d, r8d
0x180008f0a  xor     edx, edx
0x180008f0c  mov     rcx, rbx
0x180008f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f14  jmp     short loc_180008F5A
0x180008f16  mov     rax, cs:g_pfnResultLoggingCallback
0x180008f1d  mov     ebp, 800h
0x180008f22  test    rax, rax
0x180008f25  jz      short loc_180008F3E
0x180008f27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008f2e  jnz     short loc_180008F3E
0x180008f30  mov     r8d, ebp
0x180008f33  mov     rdx, rsi
0x180008f36  mov     rcx, rbx
0x180008f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f3e  cmp     [rsi], di
0x180008f41  jnz     short loc_180008F51
0x180008f43  mov     r8, rbx; unsigned __int64
0x180008f46  mov     rdx, rbp; unsigned __int16 *
0x180008f49  mov     rcx, rsi; this
0x180008f4c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008f51  mov     rcx, rsi; lpOutputString
0x180008f54  call    cs:__imp_OutputDebugStringW
0x180008f5a  test    byte ptr [rbx+4], 4
0x180008f5e  jnz     short loc_180008F69
0x180008f60  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008f67  jz      short loc_180008F7A
0x180008f69  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008f70  test    rax, rax
0x180008f73  jz      short loc_180008F7A
0x180008f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f7a  mov     rbx, [rsp+78h+arg_10]
0x180008f82  add     rsp, 40h
0x180008f86  pop     r15
0x180008f88  pop     r14
0x180008f8a  pop     r13
0x180008f8c  pop     r12
0x180008f8e  pop     rdi
0x180008f8f  pop     rsi
0x180008f90  pop     rbp
0x180008f91  retn
0x180008f92  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
