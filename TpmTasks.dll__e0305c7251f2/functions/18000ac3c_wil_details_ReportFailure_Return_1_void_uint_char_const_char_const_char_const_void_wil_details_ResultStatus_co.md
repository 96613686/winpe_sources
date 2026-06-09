# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000ac3c`
- end: `0x18000aee2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000a330`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18000ac3c`
- `0x180013e18`
- `0x180018480`
- `0x18001e498`
- `0x180023250`
- `0x180059200`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad02`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ae81`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ae81`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000adf7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000adf7`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x18000ac3c  push    rbp
0x18000ac3e  push    rbx
0x18000ac3f  push    rsi
0x18000ac40  push    rdi
0x18000ac41  push    r12
0x18000ac43  push    r14
0x18000ac45  push    r15
0x18000ac47  lea     rbp, [rsp-13D0h]
0x18000ac4f  mov     eax, 14D0h
0x18000ac54  call    _alloca_probe
0x18000ac59  sub     rsp, rax
0x18000ac5c  mov     rax, cs:__security_cookie
0x18000ac63  xor     rax, rsp
0x18000ac66  mov     [rbp+1400h+var_40], rax
0x18000ac6d  mov     rsi, r8
0x18000ac70  mov     edi, edx
0x18000ac72  mov     rbx, rcx
0x18000ac75  mov     r14, [rbp+1400h+arg_28]
0x18000ac7c  xor     edx, edx; Val
0x18000ac7e  mov     r8d, 98h; Size
0x18000ac84  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000ac89  call    memset_0
0x18000ac8e  nop
0x18000ac8f  xor     r12d, r12d
0x18000ac92  mov     [rbp+1400h+OutputString], r12w
0x18000ac9a  mov     [rbp+1400h+var_1440], r12b
0x18000ac9e  mov     rdx, [rbp+1400h+arg_30]; int
0x18000aca5  mov     ecx, [rdx]; this
0x18000aca7  mov     [rsp+1500h+var_14D8], ecx
0x18000acab  mov     eax, [rdx+4]
0x18000acae  mov     [rsp+1500h+var_14D4], eax
0x18000acb2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000acb7  mov     r15d, eax
0x18000acba  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000acc2  mov     ecx, r12d
0x18000acc5  lea     eax, [r12+8]
0x18000acca  cmp     dword ptr [rdx+8], 1
0x18000acce  cmovz   ecx, eax
0x18000acd1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000acd5  lea     ecx, [rax-7]
0x18000acd8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ace0  inc     ecx
0x18000ace2  mov     [rsp+1500h+var_14D0], ecx
0x18000ace6  mov     rcx, [rbp+1400h+arg_38]
0x18000aced  test    rcx, rcx
0x18000acf0  jz      short loc_18000ACFD
0x18000acf2  cmp     [rcx], r12w
0x18000acf6  mov     [rsp+1500h+var_14C8], rcx
0x18000acfb  jnz     short loc_18000AD02
0x18000acfd  mov     [rsp+1500h+var_14C8], r12
0x18000ad02  call    cs:__imp_GetCurrentThreadId
0x18000ad08  mov     [rsp+1500h+var_14C0], eax
0x18000ad0c  mov     [rsp+1500h+var_14A8], rsi
0x18000ad11  mov     [rsp+1500h+var_14A0], edi
0x18000ad15  mov     [rsp+1500h+var_149C], r15d
0x18000ad1a  mov     [rsp+1500h+var_14B8], r12
0x18000ad1f  mov     [rsp+1500h+var_14B0], r12
0x18000ad24  mov     [rbp+1400h+var_1458], r14
0x18000ad28  mov     [rbp+1400h+var_1450], rbx
0x18000ad2c  mov     [rsp+1500h+var_1498], r12
0x18000ad31  xorps   xmm0, xmm0
0x18000ad34  xor     eax, eax
0x18000ad36  movups  [rbp+1400h+var_1478], xmm0
0x18000ad3a  mov     [rbp+1400h+var_1468], rax
0x18000ad3e  xorps   xmm1, xmm1
0x18000ad41  movups  [rsp+1500h+var_1490], xmm1
0x18000ad46  mov     [rbp+1400h+var_1480], rax
0x18000ad4a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ad51  test    rax, rax
0x18000ad54  jz      short loc_18000AD61
0x18000ad56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad5b  mov     [rbp+1400h+var_1460], rax
0x18000ad5f  jmp     short loc_18000AD65
0x18000ad61  mov     [rbp+1400h+var_1460], r12
0x18000ad65  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000ad6c  test    rax, rax
0x18000ad6f  jz      short loc_18000AD7B
0x18000ad71  lea     rcx, [rsp+1500h+var_14E0]
0x18000ad76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad7b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000ad82  test    rax, rax
0x18000ad85  jz      short loc_18000AD9B
0x18000ad87  mov     r8d, 400h
0x18000ad8d  lea     rdx, [rbp+1400h+var_1440]
0x18000ad91  lea     rcx, [rsp+1500h+var_14E0]
0x18000ad96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad9b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ada2  test    rax, rax
0x18000ada5  jz      short loc_18000ADB1
0x18000ada7  lea     rcx, [rsp+1500h+var_14E0]
0x18000adac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adb1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000adb8  test    rax, rax
0x18000adbb  jz      short loc_18000ADCE
0x18000adbd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000adc2  jnz     short loc_18000ADCE
0x18000adc4  lea     rcx, [rsp+1500h+var_14E0]
0x18000adc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adce  cmp     [rsp+1500h+var_14D8], r12d
0x18000add3  jge     loc_18000AEDC
0x18000add9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000ade0  jnz     short loc_18000AE01
0x18000ade2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000ade9  test    rax, rax
0x18000adec  jz      short loc_18000ADF7
0x18000adee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adf3  test    al, al
0x18000adf5  jmp     short loc_18000ADFF
0x18000adf7  call    cs:__imp_IsDebuggerPresent
0x18000adfd  test    eax, eax
0x18000adff  jz      short loc_18000AE08
0x18000ae01  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000ae06  jz      short loc_18000AE2E
0x18000ae08  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ae0f  test    rax, rax
0x18000ae12  jz      short loc_18000AE87
0x18000ae14  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000ae1b  jnz     short loc_18000AE87
0x18000ae1d  xor     r8d, r8d
0x18000ae20  xor     edx, edx
0x18000ae22  lea     rcx, [rsp+1500h+var_14E0]
0x18000ae27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae2c  jmp     short loc_18000AE87
0x18000ae2e  mov     ebx, 800h
0x18000ae33  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ae3a  test    rax, rax
0x18000ae3d  jz      short loc_18000AE5C
0x18000ae3f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000ae46  jnz     short loc_18000AE5C
0x18000ae48  mov     r8d, ebx
0x18000ae4b  lea     rdx, [rbp+1400h+OutputString]
0x18000ae52  lea     rcx, [rsp+1500h+var_14E0]
0x18000ae57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae5c  cmp     [rbp+1400h+OutputString], r12w
0x18000ae64  jnz     short loc_18000AE7A
0x18000ae66  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000ae6b  mov     rdx, rbx; unsigned __int16 *
0x18000ae6e  lea     rcx, [rbp+1400h+OutputString]; this
0x18000ae75  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000ae7a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000ae81  call    cs:__imp_OutputDebugStringW
0x18000ae87  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000ae8c  jnz     short loc_18000AE97
0x18000ae8e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000ae95  jz      short loc_18000AEA9
0x18000ae97  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000ae9e  test    rax, rax
0x18000aea1  jz      short loc_18000AEA9
0x18000aea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aea8  nop
0x18000aea9  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000aeae  jnz     short loc_18000AED1
0x18000aeb0  mov     rcx, [rbp+1400h+var_40]
0x18000aeb7  xor     rcx, rsp; StackCookie
0x18000aeba  call    __security_check_cookie
0x18000aebf  add     rsp, 14D0h
0x18000aec6  pop     r15
0x18000aec8  pop     r14
0x18000aeca  pop     r12
0x18000aecc  pop     rdi
0x18000aecd  pop     rsi
0x18000aece  pop     rbx
0x18000aecf  pop     rbp
0x18000aed0  retn
0x18000aed1  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000aed6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000aedc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
