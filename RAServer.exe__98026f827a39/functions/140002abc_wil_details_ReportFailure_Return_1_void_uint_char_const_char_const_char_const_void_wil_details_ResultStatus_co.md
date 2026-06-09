# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002abc`
- end: `0x140002d52`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002784`

## callees

- `0x1400022d3`
- `0x140002abc`
- `0x1400063d4`
- `0x140008d5c`
- `0x14000b738`
- `0x14000ba28`
- `0x140015aa0`
- `0x140015b60`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002b67`
- `KERNEL32!GetCurrentThreadId` at `0x140002b67`
- `KERNEL32!OutputDebugStringW` at `0x140002cec`
- `KERNEL32!OutputDebugStringW` at `0x140002cec`
- `KERNEL32!IsDebuggerPresent` at `0x140002c62`
- `KERNEL32!IsDebuggerPresent` at `0x140002c62`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x140002abc  mov     [rsp-8+arg_10], rbx
0x140002ac1  push    rbp
0x140002ac2  push    rsi
0x140002ac3  push    rdi
0x140002ac4  push    r14
0x140002ac6  push    r15
0x140002ac8  lea     rbp, [rsp-13D0h]
0x140002ad0  mov     eax, 14D0h
0x140002ad5  call    _alloca_probe
0x140002ada  sub     rsp, rax
0x140002add  mov     rax, cs:__security_cookie
0x140002ae4  xor     rax, rsp
0x140002ae7  mov     [rbp+13F0h+var_30], rax
0x140002aee  mov     esi, edx
0x140002af0  mov     r14, rcx
0x140002af3  mov     rdi, [rbp+13F0h+arg_28]
0x140002afa  xor     edx, edx; Val
0x140002afc  mov     r8d, 98h; Size
0x140002b02  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140002b07  call    memset_0
0x140002b0c  nop
0x140002b0d  xor     r15d, r15d
0x140002b10  mov     [rbp+13F0h+OutputString], r15w
0x140002b18  mov     [rbp+13F0h+var_1430], r15b
0x140002b1c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140002b23  mov     ecx, [rdx]; this
0x140002b25  mov     [rsp+14F0h+var_14C8], ecx
0x140002b29  mov     eax, [rdx+4]
0x140002b2c  mov     [rsp+14F0h+var_14C4], eax
0x140002b30  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002b35  mov     ebx, eax
0x140002b37  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140002b3f  mov     ecx, r15d
0x140002b42  lea     eax, [r15+8]
0x140002b46  cmp     dword ptr [rdx+8], 1
0x140002b4a  cmovz   ecx, eax
0x140002b4d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002b51  lea     ecx, [rax-7]
0x140002b54  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002b5c  inc     ecx
0x140002b5e  mov     [rsp+14F0h+var_14C0], ecx
0x140002b62  mov     [rsp+14F0h+var_14B8], r15
0x140002b67  call    cs:__imp_GetCurrentThreadId
0x140002b6d  mov     [rsp+14F0h+var_14B0], eax
0x140002b71  lea     rax, aWil; "wil"
0x140002b78  mov     [rsp+14F0h+var_1498], rax
0x140002b7d  mov     [rsp+14F0h+var_1490], esi
0x140002b81  mov     [rsp+14F0h+var_148C], ebx
0x140002b85  mov     [rsp+14F0h+var_14A8], r15
0x140002b8a  mov     [rsp+14F0h+var_14A0], r15
0x140002b8f  mov     [rbp+13F0h+var_1448], rdi
0x140002b93  mov     [rbp+13F0h+var_1440], r14
0x140002b97  mov     [rsp+14F0h+var_1488], r15
0x140002b9c  xorps   xmm0, xmm0
0x140002b9f  xor     eax, eax
0x140002ba1  movups  [rbp+13F0h+var_1468], xmm0
0x140002ba5  mov     [rbp+13F0h+var_1458], rax
0x140002ba9  xorps   xmm1, xmm1
0x140002bac  movups  [rsp+14F0h+var_1480], xmm1
0x140002bb1  mov     [rbp+13F0h+var_1470], rax
0x140002bb5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002bbc  test    rax, rax
0x140002bbf  jz      short loc_140002BCC
0x140002bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bc6  mov     [rbp+13F0h+var_1450], rax
0x140002bca  jmp     short loc_140002BD0
0x140002bcc  mov     [rbp+13F0h+var_1450], r15
0x140002bd0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002bd7  test    rax, rax
0x140002bda  jz      short loc_140002BE6
0x140002bdc  lea     rcx, [rsp+14F0h+var_14D0]
0x140002be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002be6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002bed  test    rax, rax
0x140002bf0  jz      short loc_140002C06
0x140002bf2  mov     r8d, 400h
0x140002bf8  lea     rdx, [rbp+13F0h+var_1430]
0x140002bfc  lea     rcx, [rsp+14F0h+var_14D0]
0x140002c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c06  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002c0d  test    rax, rax
0x140002c10  jz      short loc_140002C1C
0x140002c12  lea     rcx, [rsp+14F0h+var_14D0]
0x140002c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c1c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002c23  test    rax, rax
0x140002c26  jz      short loc_140002C39
0x140002c28  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002c2d  jnz     short loc_140002C39
0x140002c2f  lea     rcx, [rsp+14F0h+var_14D0]
0x140002c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c39  cmp     [rsp+14F0h+var_14C8], r15d
0x140002c3e  jge     loc_140002D4C
0x140002c44  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140002c4b  jnz     short loc_140002C6C
0x140002c4d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002c54  test    rax, rax
0x140002c57  jz      short loc_140002C62
0x140002c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c5e  test    al, al
0x140002c60  jmp     short loc_140002C6A
0x140002c62  call    cs:__imp_IsDebuggerPresent
0x140002c68  test    eax, eax
0x140002c6a  jz      short loc_140002C73
0x140002c6c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002c71  jz      short loc_140002C99
0x140002c73  mov     rax, cs:g_pfnResultLoggingCallback
0x140002c7a  test    rax, rax
0x140002c7d  jz      short loc_140002CF2
0x140002c7f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002c86  jnz     short loc_140002CF2
0x140002c88  xor     r8d, r8d
0x140002c8b  xor     edx, edx
0x140002c8d  lea     rcx, [rsp+14F0h+var_14D0]
0x140002c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c97  jmp     short loc_140002CF2
0x140002c99  mov     ebx, 800h
0x140002c9e  mov     rax, cs:g_pfnResultLoggingCallback
0x140002ca5  test    rax, rax
0x140002ca8  jz      short loc_140002CC7
0x140002caa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002cb1  jnz     short loc_140002CC7
0x140002cb3  mov     r8d, ebx
0x140002cb6  lea     rdx, [rbp+13F0h+OutputString]
0x140002cbd  lea     rcx, [rsp+14F0h+var_14D0]
0x140002cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cc7  cmp     [rbp+13F0h+OutputString], r15w
0x140002ccf  jnz     short loc_140002CE5
0x140002cd1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002cd6  mov     rdx, rbx; unsigned __int16 *
0x140002cd9  lea     rcx, [rbp+13F0h+OutputString]; this
0x140002ce0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002ce5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002cec  call    cs:__imp_OutputDebugStringW
0x140002cf2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002cf7  jnz     short loc_140002D02
0x140002cf9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140002d00  jz      short loc_140002D14
0x140002d02  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002d09  test    rax, rax
0x140002d0c  jz      short loc_140002D14
0x140002d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d13  nop
0x140002d14  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140002d19  jnz     short loc_140002D41
0x140002d1b  mov     rcx, [rbp+13F0h+var_30]
0x140002d22  xor     rcx, rsp; StackCookie
0x140002d25  call    __security_check_cookie
0x140002d2a  mov     rbx, [rsp+14F0h+arg_10]
0x140002d32  add     rsp, 14D0h
0x140002d39  pop     r15
0x140002d3b  pop     r14
0x140002d3d  pop     rdi
0x140002d3e  pop     rsi
0x140002d3f  pop     rbp
0x140002d40  retn
0x140002d41  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002d46  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002d4c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
