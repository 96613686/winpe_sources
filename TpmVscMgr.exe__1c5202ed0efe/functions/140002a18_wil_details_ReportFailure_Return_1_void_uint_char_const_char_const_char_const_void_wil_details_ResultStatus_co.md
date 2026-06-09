# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002a18`
- end: `0x140002cae`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400024c4`

## callees

- `0x1400016a0`
- `0x140002456`
- `0x140002a18`
- `0x140003b54`
- `0x140004a80`
- `0x140005ad0`
- `0x140005bac`
- `0x1400114d0`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002ac3`
- `KERNEL32!GetCurrentThreadId` at `0x140002ac3`
- `KERNEL32!OutputDebugStringW` at `0x140002c48`
- `KERNEL32!OutputDebugStringW` at `0x140002c48`
- `KERNEL32!IsDebuggerPresent` at `0x140002bbe`
- `KERNEL32!IsDebuggerPresent` at `0x140002bbe`

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
0x140002a18  mov     [rsp-8+arg_10], rbx
0x140002a1d  push    rbp
0x140002a1e  push    rsi
0x140002a1f  push    rdi
0x140002a20  push    r14
0x140002a22  push    r15
0x140002a24  lea     rbp, [rsp-13D0h]
0x140002a2c  mov     eax, 14D0h
0x140002a31  call    _alloca_probe
0x140002a36  sub     rsp, rax
0x140002a39  mov     rax, cs:__security_cookie
0x140002a40  xor     rax, rsp
0x140002a43  mov     [rbp+13F0h+var_30], rax
0x140002a4a  mov     esi, edx
0x140002a4c  mov     r14, rcx
0x140002a4f  mov     rdi, [rbp+13F0h+arg_28]
0x140002a56  xor     edx, edx; Val
0x140002a58  mov     r8d, 98h; Size
0x140002a5e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140002a63  call    memset_0
0x140002a68  nop
0x140002a69  xor     r15d, r15d
0x140002a6c  mov     [rbp+13F0h+OutputString], r15w
0x140002a74  mov     [rbp+13F0h+var_1430], r15b
0x140002a78  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140002a7f  mov     ecx, [rdx]; this
0x140002a81  mov     [rsp+14F0h+var_14C8], ecx
0x140002a85  mov     eax, [rdx+4]
0x140002a88  mov     [rsp+14F0h+var_14C4], eax
0x140002a8c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002a91  mov     ebx, eax
0x140002a93  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140002a9b  mov     ecx, r15d
0x140002a9e  lea     eax, [r15+8]
0x140002aa2  cmp     dword ptr [rdx+8], 1
0x140002aa6  cmovz   ecx, eax
0x140002aa9  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002aad  lea     ecx, [rax-7]
0x140002ab0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002ab8  inc     ecx
0x140002aba  mov     [rsp+14F0h+var_14C0], ecx
0x140002abe  mov     [rsp+14F0h+var_14B8], r15
0x140002ac3  call    cs:__imp_GetCurrentThreadId
0x140002ac9  mov     [rsp+14F0h+var_14B0], eax
0x140002acd  lea     rax, aWil; "wil"
0x140002ad4  mov     [rsp+14F0h+var_1498], rax
0x140002ad9  mov     [rsp+14F0h+var_1490], esi
0x140002add  mov     [rsp+14F0h+var_148C], ebx
0x140002ae1  mov     [rsp+14F0h+var_14A8], r15
0x140002ae6  mov     [rsp+14F0h+var_14A0], r15
0x140002aeb  mov     [rbp+13F0h+var_1448], rdi
0x140002aef  mov     [rbp+13F0h+var_1440], r14
0x140002af3  mov     [rsp+14F0h+var_1488], r15
0x140002af8  xorps   xmm0, xmm0
0x140002afb  xor     eax, eax
0x140002afd  movups  [rbp+13F0h+var_1468], xmm0
0x140002b01  mov     [rbp+13F0h+var_1458], rax
0x140002b05  xorps   xmm1, xmm1
0x140002b08  movups  [rsp+14F0h+var_1480], xmm1
0x140002b0d  mov     [rbp+13F0h+var_1470], rax
0x140002b11  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002b18  test    rax, rax
0x140002b1b  jz      short loc_140002B28
0x140002b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b22  mov     [rbp+13F0h+var_1450], rax
0x140002b26  jmp     short loc_140002B2C
0x140002b28  mov     [rbp+13F0h+var_1450], r15
0x140002b2c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002b33  test    rax, rax
0x140002b36  jz      short loc_140002B42
0x140002b38  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b42  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002b49  test    rax, rax
0x140002b4c  jz      short loc_140002B62
0x140002b4e  mov     r8d, 400h
0x140002b54  lea     rdx, [rbp+13F0h+var_1430]
0x140002b58  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b62  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002b69  test    rax, rax
0x140002b6c  jz      short loc_140002B78
0x140002b6e  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b78  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002b7f  test    rax, rax
0x140002b82  jz      short loc_140002B95
0x140002b84  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002b89  jnz     short loc_140002B95
0x140002b8b  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b95  cmp     [rsp+14F0h+var_14C8], r15d
0x140002b9a  jge     loc_140002CA8
0x140002ba0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140002ba7  jnz     short loc_140002BC8
0x140002ba9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002bb0  test    rax, rax
0x140002bb3  jz      short loc_140002BBE
0x140002bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bba  test    al, al
0x140002bbc  jmp     short loc_140002BC6
0x140002bbe  call    cs:__imp_IsDebuggerPresent
0x140002bc4  test    eax, eax
0x140002bc6  jz      short loc_140002BCF
0x140002bc8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002bcd  jz      short loc_140002BF5
0x140002bcf  mov     rax, cs:g_pfnResultLoggingCallback
0x140002bd6  test    rax, rax
0x140002bd9  jz      short loc_140002C4E
0x140002bdb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002be2  jnz     short loc_140002C4E
0x140002be4  xor     r8d, r8d
0x140002be7  xor     edx, edx
0x140002be9  lea     rcx, [rsp+14F0h+var_14D0]
0x140002bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bf3  jmp     short loc_140002C4E
0x140002bf5  mov     ebx, 800h
0x140002bfa  mov     rax, cs:g_pfnResultLoggingCallback
0x140002c01  test    rax, rax
0x140002c04  jz      short loc_140002C23
0x140002c06  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002c0d  jnz     short loc_140002C23
0x140002c0f  mov     r8d, ebx
0x140002c12  lea     rdx, [rbp+13F0h+OutputString]
0x140002c19  lea     rcx, [rsp+14F0h+var_14D0]
0x140002c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c23  cmp     [rbp+13F0h+OutputString], r15w
0x140002c2b  jnz     short loc_140002C41
0x140002c2d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002c32  mov     rdx, rbx; unsigned __int16 *
0x140002c35  lea     rcx, [rbp+13F0h+OutputString]; this
0x140002c3c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002c41  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002c48  call    cs:__imp_OutputDebugStringW
0x140002c4e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002c53  jnz     short loc_140002C5E
0x140002c55  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140002c5c  jz      short loc_140002C70
0x140002c5e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002c65  test    rax, rax
0x140002c68  jz      short loc_140002C70
0x140002c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c6f  nop
0x140002c70  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140002c75  jnz     short loc_140002C9D
0x140002c77  mov     rcx, [rbp+13F0h+var_30]
0x140002c7e  xor     rcx, rsp; StackCookie
0x140002c81  call    __security_check_cookie
0x140002c86  mov     rbx, [rsp+14F0h+arg_10]
0x140002c8e  add     rsp, 14D0h
0x140002c95  pop     r15
0x140002c97  pop     r14
0x140002c99  pop     rdi
0x140002c9a  pop     rsi
0x140002c9b  pop     rbp
0x140002c9c  retn
0x140002c9d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002ca2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002ca8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
