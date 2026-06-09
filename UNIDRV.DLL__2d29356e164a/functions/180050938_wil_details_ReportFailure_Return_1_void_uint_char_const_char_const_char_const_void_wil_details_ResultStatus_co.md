# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180050938`
- end: `0x180050bcc`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180048170`

## callees

- `0x1800487e0`
- `0x1800491dc`
- `0x180050938`
- `0x1800526e4`
- `0x180054900`
- `0x1800561a8`
- `0x1800563a8`
- `0x1800744f0`
- `0x180075010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180050add`
- `KERNEL32!IsDebuggerPresent` at `0x180050add`
- `KERNEL32!OutputDebugStringW` at `0x180050b67`
- `KERNEL32!OutputDebugStringW` at `0x180050b67`
- `KERNEL32!GetCurrentThreadId` at `0x1800509e2`
- `KERNEL32!GetCurrentThreadId` at `0x1800509e2`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180050938  mov     [rsp-8+arg_10], rbx
0x18005093d  push    rbp
0x18005093e  push    rsi
0x18005093f  push    rdi
0x180050940  push    r14
0x180050942  push    r15
0x180050944  lea     rbp, [rsp-13D0h]
0x18005094c  mov     eax, 14D0h
0x180050951  call    _alloca_probe
0x180050956  sub     rsp, rax
0x180050959  mov     rax, cs:__security_cookie
0x180050960  xor     rax, rsp
0x180050963  mov     [rbp+13F0h+var_30], rax
0x18005096a  mov     rdi, [rbp+13F0h+arg_28]
0x180050971  mov     esi, edx
0x180050973  mov     r14, rcx
0x180050976  xor     edx, edx; Val
0x180050978  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18005097d  mov     r8d, 98h; Size
0x180050983  call    memset_0
0x180050988  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18005098f  xor     r15d, r15d
0x180050992  mov     [rbp+13F0h+OutputString], r15w
0x18005099a  mov     [rbp+13F0h+var_1430], r15b
0x18005099e  mov     ecx, [rdx]; this
0x1800509a0  mov     eax, [rdx+4]
0x1800509a3  mov     [rsp+14F0h+var_14C8], ecx
0x1800509a7  mov     [rsp+14F0h+var_14C4], eax
0x1800509ab  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800509b0  cmp     dword ptr [rdx+8], 1
0x1800509b4  mov     ebx, eax
0x1800509b6  lea     eax, [r15+8]
0x1800509ba  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800509c2  mov     ecx, r15d
0x1800509c5  cmovz   ecx, eax
0x1800509c8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800509cc  lea     ecx, [rax-7]
0x1800509cf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800509d7  inc     ecx
0x1800509d9  mov     [rsp+14F0h+var_14B8], r15
0x1800509de  mov     [rsp+14F0h+var_14C0], ecx
0x1800509e2  call    cs:__imp_GetCurrentThreadId
0x1800509e8  xorps   xmm0, xmm0
0x1800509eb  mov     [rsp+14F0h+var_1490], esi
0x1800509ef  mov     [rsp+14F0h+var_14B0], eax
0x1800509f3  xorps   xmm1, xmm1
0x1800509f6  lea     rax, aWil; "wil"
0x1800509fd  mov     [rsp+14F0h+var_148C], ebx
0x180050a01  mov     [rsp+14F0h+var_1498], rax
0x180050a06  xor     eax, eax
0x180050a08  mov     [rbp+13F0h+var_1458], rax
0x180050a0c  mov     [rbp+13F0h+var_1470], rax
0x180050a10  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180050a17  mov     [rsp+14F0h+var_14A8], r15
0x180050a1c  mov     [rsp+14F0h+var_14A0], r15
0x180050a21  mov     [rbp+13F0h+var_1448], rdi
0x180050a25  mov     [rbp+13F0h+var_1440], r14
0x180050a29  mov     [rsp+14F0h+var_1488], r15
0x180050a2e  movups  [rbp+13F0h+var_1468], xmm0
0x180050a32  movups  [rsp+14F0h+var_1480], xmm1
0x180050a37  test    rax, rax
0x180050a3a  jz      short loc_180050A47
0x180050a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a41  mov     [rbp+13F0h+var_1450], rax
0x180050a45  jmp     short loc_180050A4B
0x180050a47  mov     [rbp+13F0h+var_1450], r15
0x180050a4b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180050a52  test    rax, rax
0x180050a55  jz      short loc_180050A61
0x180050a57  lea     rcx, [rsp+14F0h+var_14D0]
0x180050a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a61  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180050a68  test    rax, rax
0x180050a6b  jz      short loc_180050A81
0x180050a6d  mov     r8d, 400h
0x180050a73  lea     rdx, [rbp+13F0h+var_1430]
0x180050a77  lea     rcx, [rsp+14F0h+var_14D0]
0x180050a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a81  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180050a88  test    rax, rax
0x180050a8b  jz      short loc_180050A97
0x180050a8d  lea     rcx, [rsp+14F0h+var_14D0]
0x180050a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a97  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180050a9e  test    rax, rax
0x180050aa1  jz      short loc_180050AB4
0x180050aa3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180050aa8  jnz     short loc_180050AB4
0x180050aaa  lea     rcx, [rsp+14F0h+var_14D0]
0x180050aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ab4  cmp     [rsp+14F0h+var_14C8], r15d
0x180050ab9  jge     loc_180050BBB
0x180050abf  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180050ac6  jnz     short loc_180050AE7
0x180050ac8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180050acf  test    rax, rax
0x180050ad2  jz      short loc_180050ADD
0x180050ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ad9  test    al, al
0x180050adb  jmp     short loc_180050AE5
0x180050add  call    cs:__imp_IsDebuggerPresent
0x180050ae3  test    eax, eax
0x180050ae5  jz      short loc_180050AEE
0x180050ae7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180050aec  jz      short loc_180050B14
0x180050aee  mov     rax, cs:g_pfnResultLoggingCallback
0x180050af5  test    rax, rax
0x180050af8  jz      short loc_180050B6D
0x180050afa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180050b01  jnz     short loc_180050B6D
0x180050b03  xor     r8d, r8d
0x180050b06  lea     rcx, [rsp+14F0h+var_14D0]
0x180050b0b  xor     edx, edx
0x180050b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b12  jmp     short loc_180050B6D
0x180050b14  mov     rax, cs:g_pfnResultLoggingCallback
0x180050b1b  mov     ebx, 800h
0x180050b20  test    rax, rax
0x180050b23  jz      short loc_180050B42
0x180050b25  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180050b2c  jnz     short loc_180050B42
0x180050b2e  mov     r8d, ebx
0x180050b31  lea     rdx, [rbp+13F0h+OutputString]
0x180050b38  lea     rcx, [rsp+14F0h+var_14D0]
0x180050b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b42  cmp     [rbp+13F0h+OutputString], r15w
0x180050b4a  jnz     short loc_180050B60
0x180050b4c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180050b51  mov     rdx, rbx; unsigned __int16 *
0x180050b54  lea     rcx, [rbp+13F0h+OutputString]; this
0x180050b5b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180050b60  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180050b67  call    cs:__imp_OutputDebugStringW
0x180050b6d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180050b72  jnz     short loc_180050B7D
0x180050b74  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180050b7b  jz      short loc_180050B8E
0x180050b7d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180050b84  test    rax, rax
0x180050b87  jz      short loc_180050B8E
0x180050b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b8e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180050b93  jnz     short loc_180050BC1
0x180050b95  mov     rcx, [rbp+13F0h+var_30]
0x180050b9c  xor     rcx, rsp; StackCookie
0x180050b9f  call    __security_check_cookie
0x180050ba4  mov     rbx, [rsp+14F0h+arg_10]
0x180050bac  add     rsp, 14D0h
0x180050bb3  pop     r15
0x180050bb5  pop     r14
0x180050bb7  pop     rdi
0x180050bb8  pop     rsi
0x180050bb9  pop     rbp
0x180050bba  retn
0x180050bbb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180050bc1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180050bc6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
