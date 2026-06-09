# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180009c8c`
- end: `0x180009f84`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800085a4`
- `0x180008910`

## callees

- `0x1800084d8`
- `0x1800092e4`
- `0x180009ac8`
- `0x180009c8c`
- `0x18000a2b8`
- `0x18000a2e0`
- `0x18000a2f4`
- `0x18000a310`
- `0x18000ad74`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009daf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009daf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009ece`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009ece`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009f40`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009f40`

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
0x180009c8c  mov     [rsp+arg_10], rbx
0x180009c91  mov     [rsp+arg_8], edx
0x180009c95  mov     [rsp+arg_0], rcx
0x180009c9a  push    rbp
0x180009c9b  push    rsi
0x180009c9c  push    rdi
0x180009c9d  push    r12
0x180009c9f  push    r13
0x180009ca1  push    r14
0x180009ca3  push    r15
0x180009ca5  sub     rsp, 40h
0x180009ca9  mov     r14, [rsp+78h+arg_38]
0x180009cb1  xor     eax, eax
0x180009cb3  mov     rbx, [rsp+78h+arg_78]
0x180009cbb  xor     ebp, ebp
0x180009cbd  mov     r15d, [rsp+78h+arg_30]
0x180009cc5  mov     r10, rcx
0x180009cc8  mov     rsi, [rsp+78h+lpOutputString]
0x180009cd0  mov     r12, r9
0x180009cd3  mov     r13, r8
0x180009cd6  mov     ecx, r15d
0x180009cd9  mov     [rsi], ax
0x180009cdc  mov     rax, [rsp+78h+arg_60]
0x180009ce4  mov     byte ptr [rax], 0
0x180009ce7  mov     edi, [r14]
0x180009cea  mov     [rbx+8], edi
0x180009ced  mov     eax, [r14+4]
0x180009cf1  mov     [rbx+0Ch], eax
0x180009cf4  test    r15d, r15d
0x180009cf7  jz      short loc_180009D5F
0x180009cf9  sub     ecx, 1
0x180009cfc  jz      short loc_180009D56
0x180009cfe  sub     ecx, 1
0x180009d01  jz      short loc_180009D11
0x180009d03  cmp     ecx, 1
0x180009d06  jnz     short loc_180009D68
0x180009d08  mov     ecx, edi; this
0x180009d0a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009d0f  jmp     short loc_180009D66
0x180009d11  test    edi, edi
0x180009d13  js      short loc_180009D4D
0x180009d15  mov     rax, [rsp+78h+arg_28]
0x180009d1d  mov     edi, 8007029Ch
0x180009d22  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180009d26  mov     rcx, r10; int
0x180009d29  mov     [rsp+78h+var_50], rax; __int64
0x180009d2e  mov     rax, [rsp+78h+arg_20]
0x180009d36  mov     [rsp+78h+var_58], rax; __int64
0x180009d3b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009d40  mov     ecx, edi; this
0x180009d42  mov     [rbx+8], edi
0x180009d45  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009d4a  mov     [rbx+0Ch], eax
0x180009d4d  mov     ecx, edi; this
0x180009d4f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009d54  jmp     short loc_180009D66
0x180009d56  mov     ecx, edi; this
0x180009d58  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009d5d  jmp     short loc_180009D66
0x180009d5f  mov     ecx, edi; this
0x180009d61  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009d66  mov     ebp, eax
0x180009d68  mov     eax, [rsp+78h+arg_70]
0x180009d6f  mov     [rbx+4], eax
0x180009d72  mov     [rbx], r15d
0x180009d75  cmp     dword ptr [r14+8], 1
0x180009d7a  jnz     short loc_180009D82
0x180009d7c  or      eax, 8
0x180009d7f  mov     [rbx+4], eax
0x180009d82  mov     eax, 1
0x180009d87  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009d8f  inc     eax
0x180009d91  xor     edi, edi
0x180009d93  mov     [rbx+10h], eax
0x180009d96  mov     rax, [rsp+78h+arg_40]
0x180009d9e  test    rax, rax
0x180009da1  jz      short loc_180009DA8
0x180009da3  cmp     [rax], di
0x180009da6  jnz     short loc_180009DAB
0x180009da8  mov     rax, rdi
0x180009dab  mov     [rbx+18h], rax
0x180009daf  call    cs:__imp_GetCurrentThreadId
0x180009db5  mov     [rbx+38h], r13
0x180009db9  xorps   xmm0, xmm0
0x180009dbc  mov     [rbx+20h], eax
0x180009dbf  mov     eax, [rsp+78h+arg_8]
0x180009dc6  mov     [rbx+40h], eax
0x180009dc9  mov     rax, [rsp+78h+arg_20]
0x180009dd1  mov     [rbx+28h], rax
0x180009dd5  mov     rax, [rsp+78h+arg_28]
0x180009ddd  mov     [rbx+88h], rax
0x180009de4  mov     rax, [rsp+78h+arg_0]
0x180009dec  mov     [rbx+90h], rax
0x180009df3  xor     eax, eax
0x180009df5  mov     [rbx+44h], ebp
0x180009df8  mov     [rbx+30h], r12
0x180009dfc  mov     [rbx+48h], rdi
0x180009e00  movups  xmmword ptr [rbx+68h], xmm0
0x180009e04  mov     [rbx+78h], rax
0x180009e08  movups  xmmword ptr [rbx+50h], xmm0
0x180009e0c  mov     [rbx+60h], rax
0x180009e10  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009e17  test    rax, rax
0x180009e1a  jz      short loc_180009E23
0x180009e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e21  jmp     short loc_180009E26
0x180009e23  mov     rax, rdi
0x180009e26  mov     [rbx+80h], rax
0x180009e2d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009e34  test    rax, rax
0x180009e37  jz      short loc_180009E41
0x180009e39  mov     rcx, rbx
0x180009e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e41  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009e48  test    rax, rax
0x180009e4b  jz      short loc_180009E63
0x180009e4d  mov     rdx, [rsp+78h+arg_60]
0x180009e55  mov     r8d, 400h
0x180009e5b  mov     rcx, rbx
0x180009e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e63  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009e6a  test    rax, rax
0x180009e6d  jz      short loc_180009E77
0x180009e6f  mov     rcx, rbx
0x180009e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e77  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009e7e  test    rax, rax
0x180009e81  jz      short loc_180009E91
0x180009e83  test    byte ptr [rbx+4], 2
0x180009e87  jnz     short loc_180009E91
0x180009e89  mov     rcx, rbx
0x180009e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e91  cmp     [rbx+8], edi
0x180009e94  jl      short loc_180009EB0
0x180009e96  cmp     r15d, 3
0x180009e9a  jnz     loc_180009F7E
0x180009ea0  mov     ecx, 8000FFFFh; this
0x180009ea5  mov     [rbx+8], ecx
0x180009ea8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009ead  mov     [rbx+0Ch], eax
0x180009eb0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180009eb7  jnz     short loc_180009ED8
0x180009eb9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009ec0  test    rax, rax
0x180009ec3  jz      short loc_180009ECE
0x180009ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eca  test    al, al
0x180009ecc  jmp     short loc_180009ED6
0x180009ece  call    cs:__imp_IsDebuggerPresent
0x180009ed4  test    eax, eax
0x180009ed6  jz      short loc_180009EDE
0x180009ed8  test    byte ptr [rbx+4], 2
0x180009edc  jz      short loc_180009F02
0x180009ede  mov     rax, cs:g_pfnResultLoggingCallback
0x180009ee5  test    rax, rax
0x180009ee8  jz      short loc_180009F46
0x180009eea  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009ef1  jnz     short loc_180009F46
0x180009ef3  xor     r8d, r8d
0x180009ef6  xor     edx, edx
0x180009ef8  mov     rcx, rbx
0x180009efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f00  jmp     short loc_180009F46
0x180009f02  mov     rax, cs:g_pfnResultLoggingCallback
0x180009f09  mov     ebp, 800h
0x180009f0e  test    rax, rax
0x180009f11  jz      short loc_180009F2A
0x180009f13  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009f1a  jnz     short loc_180009F2A
0x180009f1c  mov     r8d, ebp
0x180009f1f  mov     rdx, rsi
0x180009f22  mov     rcx, rbx
0x180009f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f2a  cmp     [rsi], di
0x180009f2d  jnz     short loc_180009F3D
0x180009f2f  mov     r8, rbx; unsigned __int64
0x180009f32  mov     rdx, rbp; unsigned __int16 *
0x180009f35  mov     rcx, rsi; this
0x180009f38  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009f3d  mov     rcx, rsi; lpOutputString
0x180009f40  call    cs:__imp_OutputDebugStringW
0x180009f46  test    byte ptr [rbx+4], 4
0x180009f4a  jnz     short loc_180009F55
0x180009f4c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009f53  jz      short loc_180009F66
0x180009f55  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009f5c  test    rax, rax
0x180009f5f  jz      short loc_180009F66
0x180009f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f66  mov     rbx, [rsp+78h+arg_10]
0x180009f6e  add     rsp, 40h
0x180009f72  pop     r15
0x180009f74  pop     r14
0x180009f76  pop     r13
0x180009f78  pop     r12
0x180009f7a  pop     rdi
0x180009f7b  pop     rsi
0x180009f7c  pop     rbp
0x180009f7d  retn
0x180009f7e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
