# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140005778`
- end: `0x140005a05`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400055c0`

## callees

- `0x1400015d0`
- `0x14000202c`
- `0x140005778`
- `0x140005b60`
- `0x140006bb0`
- `0x140006d60`
- `0x140006e3c`
- `0x140012180`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005826`
- `KERNEL32!GetCurrentThreadId` at `0x140005826`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400059a4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400059a4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000591a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000591a`

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
0x140005778  push    rbp
0x14000577a  push    rbx
0x14000577b  push    rsi
0x14000577c  push    rdi
0x14000577d  push    r12
0x14000577f  push    r14
0x140005781  push    r15
0x140005783  lea     rbp, [rsp-13D0h]
0x14000578b  mov     eax, 14D0h
0x140005790  call    _alloca_probe
0x140005795  sub     rsp, rax
0x140005798  mov     rax, cs:__security_cookie
0x14000579f  xor     rax, rsp
0x1400057a2  mov     [rbp+1400h+var_40], rax
0x1400057a9  mov     r14, r8
0x1400057ac  mov     esi, edx
0x1400057ae  mov     r15, rcx
0x1400057b1  mov     rdi, [rbp+1400h+arg_28]
0x1400057b8  xor     edx, edx; Val
0x1400057ba  mov     r8d, 98h; Size
0x1400057c0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400057c5  call    memset_0
0x1400057ca  nop
0x1400057cb  xor     r12d, r12d
0x1400057ce  mov     [rbp+1400h+OutputString], r12w
0x1400057d6  mov     [rbp+1400h+var_1440], r12b
0x1400057da  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1400057e1  mov     ecx, [rdx]; this
0x1400057e3  mov     [rsp+1500h+var_14D8], ecx
0x1400057e7  mov     eax, [rdx+4]
0x1400057ea  mov     [rsp+1500h+var_14D4], eax
0x1400057ee  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400057f3  mov     ebx, eax
0x1400057f5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1400057fd  mov     ecx, r12d
0x140005800  lea     eax, [r12+8]
0x140005805  cmp     dword ptr [rdx+8], 1
0x140005809  cmovz   ecx, eax
0x14000580c  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140005810  lea     ecx, [rax-7]
0x140005813  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000581b  inc     ecx
0x14000581d  mov     [rsp+1500h+var_14D0], ecx
0x140005821  mov     [rsp+1500h+var_14C8], r12
0x140005826  call    cs:__imp_GetCurrentThreadId
0x14000582c  mov     [rsp+1500h+var_14C0], eax
0x140005830  mov     [rsp+1500h+var_14A8], r14
0x140005835  mov     [rsp+1500h+var_14A0], esi
0x140005839  mov     [rsp+1500h+var_149C], ebx
0x14000583d  mov     [rsp+1500h+var_14B8], r12
0x140005842  mov     [rsp+1500h+var_14B0], r12
0x140005847  mov     [rbp+1400h+var_1458], rdi
0x14000584b  mov     [rbp+1400h+var_1450], r15
0x14000584f  mov     [rsp+1500h+var_1498], r12
0x140005854  xorps   xmm0, xmm0
0x140005857  xor     eax, eax
0x140005859  movups  [rbp+1400h+var_1478], xmm0
0x14000585d  mov     [rbp+1400h+var_1468], rax
0x140005861  xorps   xmm1, xmm1
0x140005864  movups  [rsp+1500h+var_1490], xmm1
0x140005869  mov     [rbp+1400h+var_1480], rax
0x14000586d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005874  test    rax, rax
0x140005877  jz      short loc_140005884
0x140005879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000587e  mov     [rbp+1400h+var_1460], rax
0x140005882  jmp     short loc_140005888
0x140005884  mov     [rbp+1400h+var_1460], r12
0x140005888  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000588f  test    rax, rax
0x140005892  jz      short loc_14000589E
0x140005894  lea     rcx, [rsp+1500h+var_14E0]
0x140005899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000589e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400058a5  test    rax, rax
0x1400058a8  jz      short loc_1400058BE
0x1400058aa  mov     r8d, 400h
0x1400058b0  lea     rdx, [rbp+1400h+var_1440]
0x1400058b4  lea     rcx, [rsp+1500h+var_14E0]
0x1400058b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058be  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400058c5  test    rax, rax
0x1400058c8  jz      short loc_1400058D4
0x1400058ca  lea     rcx, [rsp+1500h+var_14E0]
0x1400058cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058d4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400058db  test    rax, rax
0x1400058de  jz      short loc_1400058F1
0x1400058e0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400058e5  jnz     short loc_1400058F1
0x1400058e7  lea     rcx, [rsp+1500h+var_14E0]
0x1400058ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058f1  cmp     [rsp+1500h+var_14D8], r12d
0x1400058f6  jge     loc_1400059FF
0x1400058fc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140005903  jnz     short loc_140005924
0x140005905  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000590c  test    rax, rax
0x14000590f  jz      short loc_14000591A
0x140005911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005916  test    al, al
0x140005918  jmp     short loc_140005922
0x14000591a  call    cs:__imp_IsDebuggerPresent
0x140005920  test    eax, eax
0x140005922  jz      short loc_14000592B
0x140005924  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140005929  jz      short loc_140005951
0x14000592b  mov     rax, cs:g_pfnResultLoggingCallback
0x140005932  test    rax, rax
0x140005935  jz      short loc_1400059AA
0x140005937  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000593e  jnz     short loc_1400059AA
0x140005940  xor     r8d, r8d
0x140005943  xor     edx, edx
0x140005945  lea     rcx, [rsp+1500h+var_14E0]
0x14000594a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000594f  jmp     short loc_1400059AA
0x140005951  mov     ebx, 800h
0x140005956  mov     rax, cs:g_pfnResultLoggingCallback
0x14000595d  test    rax, rax
0x140005960  jz      short loc_14000597F
0x140005962  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140005969  jnz     short loc_14000597F
0x14000596b  mov     r8d, ebx
0x14000596e  lea     rdx, [rbp+1400h+OutputString]
0x140005975  lea     rcx, [rsp+1500h+var_14E0]
0x14000597a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000597f  cmp     [rbp+1400h+OutputString], r12w
0x140005987  jnz     short loc_14000599D
0x140005989  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x14000598e  mov     rdx, rbx; unsigned __int16 *
0x140005991  lea     rcx, [rbp+1400h+OutputString]; this
0x140005998  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000599d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1400059a4  call    cs:__imp_OutputDebugStringW
0x1400059aa  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400059af  jnz     short loc_1400059BA
0x1400059b1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400059b8  jz      short loc_1400059CC
0x1400059ba  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400059c1  test    rax, rax
0x1400059c4  jz      short loc_1400059CC
0x1400059c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059cb  nop
0x1400059cc  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1400059d1  jnz     short loc_1400059F4
0x1400059d3  mov     rcx, [rbp+1400h+var_40]
0x1400059da  xor     rcx, rsp; StackCookie
0x1400059dd  call    __security_check_cookie
0x1400059e2  add     rsp, 14D0h
0x1400059e9  pop     r15
0x1400059eb  pop     r14
0x1400059ed  pop     r12
0x1400059ef  pop     rdi
0x1400059f0  pop     rsi
0x1400059f1  pop     rbx
0x1400059f2  pop     rbp
0x1400059f3  retn
0x1400059f4  lea     rcx, [rsp+1500h+var_14E0]; this
0x1400059f9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400059ff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
