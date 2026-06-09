# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004efc`
- end: `0x180005189`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004bc0`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180004efc`
- `0x180005d94`
- `0x180006dc0`
- `0x1800078d8`
- `0x180007a94`
- `0x18002fd70`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004faa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004faa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000509e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000509e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005128`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005128`

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
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180004efc  push    rbp
0x180004efe  push    rbx
0x180004eff  push    rsi
0x180004f00  push    rdi
0x180004f01  push    r12
0x180004f03  push    r14
0x180004f05  push    r15
0x180004f07  lea     rbp, [rsp-13D0h]
0x180004f0f  mov     eax, 14D0h
0x180004f14  call    _alloca_probe
0x180004f19  sub     rsp, rax
0x180004f1c  mov     rax, cs:__security_cookie
0x180004f23  xor     rax, rsp
0x180004f26  mov     [rbp+1400h+var_40], rax
0x180004f2d  mov     r14, r8
0x180004f30  mov     esi, edx
0x180004f32  mov     r15, rcx
0x180004f35  mov     rdi, [rbp+1400h+arg_28]
0x180004f3c  xor     edx, edx; Val
0x180004f3e  mov     r8d, 98h; Size
0x180004f44  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004f49  call    memset_0
0x180004f4e  nop
0x180004f4f  xor     r12d, r12d
0x180004f52  mov     [rbp+1400h+OutputString], r12w
0x180004f5a  mov     [rbp+1400h+var_1440], r12b
0x180004f5e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180004f65  mov     ecx, [rdx]; this
0x180004f67  mov     [rsp+1500h+var_14D8], ecx
0x180004f6b  mov     eax, [rdx+4]
0x180004f6e  mov     [rsp+1500h+var_14D4], eax
0x180004f72  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004f77  mov     ebx, eax
0x180004f79  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004f81  mov     ecx, r12d
0x180004f84  lea     eax, [r12+8]
0x180004f89  cmp     dword ptr [rdx+8], 1
0x180004f8d  cmovz   ecx, eax
0x180004f90  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004f94  lea     ecx, [rax-7]
0x180004f97  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004f9f  inc     ecx
0x180004fa1  mov     [rsp+1500h+var_14D0], ecx
0x180004fa5  mov     [rsp+1500h+var_14C8], r12
0x180004faa  call    cs:__imp_GetCurrentThreadId
0x180004fb0  mov     [rsp+1500h+var_14C0], eax
0x180004fb4  mov     [rsp+1500h+var_14A8], r14
0x180004fb9  mov     [rsp+1500h+var_14A0], esi
0x180004fbd  mov     [rsp+1500h+var_149C], ebx
0x180004fc1  mov     [rsp+1500h+var_14B8], r12
0x180004fc6  mov     [rsp+1500h+var_14B0], r12
0x180004fcb  mov     [rbp+1400h+var_1458], rdi
0x180004fcf  mov     [rbp+1400h+var_1450], r15
0x180004fd3  mov     [rsp+1500h+var_1498], r12
0x180004fd8  xorps   xmm0, xmm0
0x180004fdb  xor     eax, eax
0x180004fdd  movups  [rbp+1400h+var_1478], xmm0
0x180004fe1  mov     [rbp+1400h+var_1468], rax
0x180004fe5  xorps   xmm1, xmm1
0x180004fe8  movups  [rsp+1500h+var_1490], xmm1
0x180004fed  mov     [rbp+1400h+var_1480], rax
0x180004ff1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004ff8  test    rax, rax
0x180004ffb  jz      short loc_180005008
0x180004ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005002  mov     [rbp+1400h+var_1460], rax
0x180005006  jmp     short loc_18000500C
0x180005008  mov     [rbp+1400h+var_1460], r12
0x18000500c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005013  test    rax, rax
0x180005016  jz      short loc_180005022
0x180005018  lea     rcx, [rsp+1500h+var_14E0]
0x18000501d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005022  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005029  test    rax, rax
0x18000502c  jz      short loc_180005042
0x18000502e  mov     r8d, 400h
0x180005034  lea     rdx, [rbp+1400h+var_1440]
0x180005038  lea     rcx, [rsp+1500h+var_14E0]
0x18000503d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005042  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005049  test    rax, rax
0x18000504c  jz      short loc_180005058
0x18000504e  lea     rcx, [rsp+1500h+var_14E0]
0x180005053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005058  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000505f  test    rax, rax
0x180005062  jz      short loc_180005075
0x180005064  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005069  jnz     short loc_180005075
0x18000506b  lea     rcx, [rsp+1500h+var_14E0]
0x180005070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005075  cmp     [rsp+1500h+var_14D8], r12d
0x18000507a  jge     loc_180005183
0x180005080  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005087  jnz     short loc_1800050A8
0x180005089  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005090  test    rax, rax
0x180005093  jz      short loc_18000509E
0x180005095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000509a  test    al, al
0x18000509c  jmp     short loc_1800050A6
0x18000509e  call    cs:__imp_IsDebuggerPresent
0x1800050a4  test    eax, eax
0x1800050a6  jz      short loc_1800050AF
0x1800050a8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800050ad  jz      short loc_1800050D5
0x1800050af  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050b6  test    rax, rax
0x1800050b9  jz      short loc_18000512E
0x1800050bb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800050c2  jnz     short loc_18000512E
0x1800050c4  xor     r8d, r8d
0x1800050c7  xor     edx, edx
0x1800050c9  lea     rcx, [rsp+1500h+var_14E0]
0x1800050ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d3  jmp     short loc_18000512E
0x1800050d5  mov     ebx, 800h
0x1800050da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050e1  test    rax, rax
0x1800050e4  jz      short loc_180005103
0x1800050e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800050ed  jnz     short loc_180005103
0x1800050ef  mov     r8d, ebx
0x1800050f2  lea     rdx, [rbp+1400h+OutputString]
0x1800050f9  lea     rcx, [rsp+1500h+var_14E0]
0x1800050fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005103  cmp     [rbp+1400h+OutputString], r12w
0x18000510b  jnz     short loc_180005121
0x18000510d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180005112  mov     rdx, rbx; unsigned __int16 *
0x180005115  lea     rcx, [rbp+1400h+OutputString]; this
0x18000511c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005121  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180005128  call    cs:__imp_OutputDebugStringW
0x18000512e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005133  jnz     short loc_18000513E
0x180005135  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000513c  jz      short loc_180005150
0x18000513e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005145  test    rax, rax
0x180005148  jz      short loc_180005150
0x18000514a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000514f  nop
0x180005150  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005155  jnz     short loc_180005178
0x180005157  mov     rcx, [rbp+1400h+var_40]
0x18000515e  xor     rcx, rsp; StackCookie
0x180005161  call    __security_check_cookie
0x180005166  add     rsp, 14D0h
0x18000516d  pop     r15
0x18000516f  pop     r14
0x180005171  pop     r12
0x180005173  pop     rdi
0x180005174  pop     rsi
0x180005175  pop     rbx
0x180005176  pop     rbp
0x180005177  retn
0x180005178  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000517d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005183  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
