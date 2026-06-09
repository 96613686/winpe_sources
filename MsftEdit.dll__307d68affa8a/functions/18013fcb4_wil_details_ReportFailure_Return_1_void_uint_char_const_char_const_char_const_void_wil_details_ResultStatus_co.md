# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18013fcb4`
- end: `0x18013ff3f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1801379b0`

## callees

- `0x18013bad0`
- `0x18013c916`
- `0x18013fcb4`
- `0x180141464`
- `0x180142d50`
- `0x180144518`
- `0x180144724`
- `0x180278c00`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013fd61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013fd61`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18013fedf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18013fedf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18013fe55`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18013fe55`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x18013fcb4  push    rbp
0x18013fcb6  push    rbx
0x18013fcb7  push    rsi
0x18013fcb8  push    rdi
0x18013fcb9  push    r12
0x18013fcbb  push    r14
0x18013fcbd  push    r15
0x18013fcbf  lea     rbp, [rsp-13D0h]
0x18013fcc7  mov     eax, 14D0h
0x18013fccc  call    _alloca_probe
0x18013fcd1  sub     rsp, rax
0x18013fcd4  mov     rax, cs:__security_cookie
0x18013fcdb  xor     rax, rsp
0x18013fcde  mov     [rbp+1400h+var_40], rax
0x18013fce5  mov     rdi, [rbp+1400h+arg_28]
0x18013fcec  mov     r14, r8
0x18013fcef  mov     esi, edx
0x18013fcf1  mov     r15, rcx
0x18013fcf4  xor     edx, edx; Val
0x18013fcf6  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18013fcfb  mov     r8d, 98h; Size
0x18013fd01  call    memset_0
0x18013fd06  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18013fd0d  xor     r12d, r12d
0x18013fd10  mov     [rbp+1400h+OutputString], r12w
0x18013fd18  mov     [rbp+1400h+var_1440], r12b
0x18013fd1c  mov     ecx, [rdx]; this
0x18013fd1e  mov     eax, [rdx+4]
0x18013fd21  mov     [rsp+1500h+var_14D8], ecx
0x18013fd25  mov     [rsp+1500h+var_14D4], eax
0x18013fd29  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18013fd2e  cmp     dword ptr [rdx+8], 1
0x18013fd32  mov     ebx, eax
0x18013fd34  lea     eax, [r12+8]
0x18013fd39  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18013fd41  mov     ecx, r12d
0x18013fd44  cmovz   ecx, eax
0x18013fd47  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18013fd4b  lea     ecx, [rax-7]
0x18013fd4e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18013fd56  inc     ecx
0x18013fd58  mov     [rsp+1500h+var_14C8], r12
0x18013fd5d  mov     [rsp+1500h+var_14D0], ecx
0x18013fd61  call    cs:__imp_GetCurrentThreadId
0x18013fd67  xorps   xmm0, xmm0
0x18013fd6a  mov     [rsp+1500h+var_14A8], r14
0x18013fd6f  mov     [rsp+1500h+var_14C0], eax
0x18013fd73  xorps   xmm1, xmm1
0x18013fd76  xor     eax, eax
0x18013fd78  mov     [rsp+1500h+var_14A0], esi
0x18013fd7c  mov     [rbp+1400h+var_1468], rax
0x18013fd80  mov     [rbp+1400h+var_1480], rax
0x18013fd84  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18013fd8b  mov     [rsp+1500h+var_149C], ebx
0x18013fd8f  mov     [rsp+1500h+var_14B8], r12
0x18013fd94  mov     [rsp+1500h+var_14B0], r12
0x18013fd99  mov     [rbp+1400h+var_1458], rdi
0x18013fd9d  mov     [rbp+1400h+var_1450], r15
0x18013fda1  mov     [rsp+1500h+var_1498], r12
0x18013fda6  movups  [rbp+1400h+var_1478], xmm0
0x18013fdaa  movups  [rsp+1500h+var_1490], xmm1
0x18013fdaf  test    rax, rax
0x18013fdb2  jz      short loc_18013FDBF
0x18013fdb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fdb9  mov     [rbp+1400h+var_1460], rax
0x18013fdbd  jmp     short loc_18013FDC3
0x18013fdbf  mov     [rbp+1400h+var_1460], r12
0x18013fdc3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18013fdca  test    rax, rax
0x18013fdcd  jz      short loc_18013FDD9
0x18013fdcf  lea     rcx, [rsp+1500h+var_14E0]
0x18013fdd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fdd9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18013fde0  test    rax, rax
0x18013fde3  jz      short loc_18013FDF9
0x18013fde5  mov     r8d, 400h
0x18013fdeb  lea     rdx, [rbp+1400h+var_1440]
0x18013fdef  lea     rcx, [rsp+1500h+var_14E0]
0x18013fdf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fdf9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18013fe00  test    rax, rax
0x18013fe03  jz      short loc_18013FE0F
0x18013fe05  lea     rcx, [rsp+1500h+var_14E0]
0x18013fe0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fe0f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18013fe16  test    rax, rax
0x18013fe19  jz      short loc_18013FE2C
0x18013fe1b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18013fe20  jnz     short loc_18013FE2C
0x18013fe22  lea     rcx, [rsp+1500h+var_14E0]
0x18013fe27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fe2c  cmp     [rsp+1500h+var_14D8], r12d
0x18013fe31  jge     loc_18013FF2E
0x18013fe37  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18013fe3e  jnz     short loc_18013FE5F
0x18013fe40  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18013fe47  test    rax, rax
0x18013fe4a  jz      short loc_18013FE55
0x18013fe4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fe51  test    al, al
0x18013fe53  jmp     short loc_18013FE5D
0x18013fe55  call    cs:__imp_IsDebuggerPresent
0x18013fe5b  test    eax, eax
0x18013fe5d  jz      short loc_18013FE66
0x18013fe5f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18013fe64  jz      short loc_18013FE8C
0x18013fe66  mov     rax, cs:g_pfnResultLoggingCallback
0x18013fe6d  test    rax, rax
0x18013fe70  jz      short loc_18013FEE5
0x18013fe72  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18013fe79  jnz     short loc_18013FEE5
0x18013fe7b  xor     r8d, r8d
0x18013fe7e  lea     rcx, [rsp+1500h+var_14E0]
0x18013fe83  xor     edx, edx
0x18013fe85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fe8a  jmp     short loc_18013FEE5
0x18013fe8c  mov     rax, cs:g_pfnResultLoggingCallback
0x18013fe93  mov     ebx, 800h
0x18013fe98  test    rax, rax
0x18013fe9b  jz      short loc_18013FEBA
0x18013fe9d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18013fea4  jnz     short loc_18013FEBA
0x18013fea6  mov     r8d, ebx
0x18013fea9  lea     rdx, [rbp+1400h+OutputString]
0x18013feb0  lea     rcx, [rsp+1500h+var_14E0]
0x18013feb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013feba  cmp     [rbp+1400h+OutputString], r12w
0x18013fec2  jnz     short loc_18013FED8
0x18013fec4  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18013fec9  mov     rdx, rbx; unsigned __int16 *
0x18013fecc  lea     rcx, [rbp+1400h+OutputString]; pszDest
0x18013fed3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18013fed8  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18013fedf  call    cs:__imp_OutputDebugStringW
0x18013fee5  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18013feea  jnz     short loc_18013FEF5
0x18013feec  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18013fef3  jz      short loc_18013FF06
0x18013fef5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18013fefc  test    rax, rax
0x18013feff  jz      short loc_18013FF06
0x18013ff01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013ff06  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18013ff0b  jnz     short loc_18013FF34
0x18013ff0d  mov     rcx, [rbp+1400h+var_40]
0x18013ff14  xor     rcx, rsp; StackCookie
0x18013ff17  call    __security_check_cookie
0x18013ff1c  add     rsp, 14D0h
0x18013ff23  pop     r15
0x18013ff25  pop     r14
0x18013ff27  pop     r12
0x18013ff29  pop     rdi
0x18013ff2a  pop     rsi
0x18013ff2b  pop     rbx
0x18013ff2c  pop     rbp
0x18013ff2d  retn
0x18013ff2e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18013ff34  lea     rcx, [rsp+1500h+var_14E0]; this
0x18013ff39  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
