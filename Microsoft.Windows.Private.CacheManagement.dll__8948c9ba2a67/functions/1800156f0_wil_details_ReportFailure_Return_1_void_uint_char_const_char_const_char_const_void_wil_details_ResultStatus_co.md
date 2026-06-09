# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800156f0`
- end: `0x18001598b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `667`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180015470`

## callees

- `0x180002790`
- `0x180002b50`
- `0x180002c80`
- `0x180002f90`
- `0x1800156f0`
- `0x1800181b0`
- `0x180018ce0`
- `0x18001cdf0`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180015929`
- `KERNEL32!OutputDebugStringW` at `0x180015929`
- `KERNEL32!GetCurrentThreadId` at `0x18001579e`
- `KERNEL32!GetCurrentThreadId` at `0x18001579e`
- `KERNEL32!IsDebuggerPresent` at `0x180015898`
- `KERNEL32!IsDebuggerPresent` at `0x180015898`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  int IsDebuggerPresent; // ebx
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // r8
  bool v15; // zf
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  _WORD *v24; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
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

  IsDebuggerPresent = 0;
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v12 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, a2);
  v19 = 1;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v20 = v13;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v15 = *a8 == 0, v24 = a8, v15) )
    v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = a3;
  v29 = a2;
  v30 = v12;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17)),
         IsDebuggerPresent))
    && (v20 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v19, v18);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v16);
}

```

## disassembly

```asm
0x1800156f0  push    rbp
0x1800156f2  push    rbx
0x1800156f3  push    rsi
0x1800156f4  push    rdi
0x1800156f5  push    r12
0x1800156f7  push    r14
0x1800156f9  push    r15
0x1800156fb  lea     rbp, [rsp-13D0h]
0x180015703  mov     eax, 14D0h
0x180015708  call    _alloca_probe
0x18001570d  sub     rsp, rax
0x180015710  mov     rax, cs:__security_cookie
0x180015717  xor     rax, rsp
0x18001571a  mov     [rbp+1400h+var_40], rax
0x180015721  mov     r14, r8
0x180015724  mov     esi, edx
0x180015726  mov     rdi, rcx
0x180015729  mov     r15, [rbp+1400h+arg_28]
0x180015730  xor     ebx, ebx
0x180015732  mov     [rbp+1400h+OutputString], bx
0x180015739  mov     [rbp+1400h+var_1440], bl
0x18001573c  mov     r8, [rbp+1400h+arg_30]
0x180015743  mov     ecx, [r8]; this
0x180015746  mov     [rsp+1500h+var_14D8], ecx
0x18001574a  mov     eax, [r8+4]
0x18001574e  mov     [rsp+1500h+var_14D4], eax
0x180015752  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180015757  mov     r12d, eax
0x18001575a  mov     edx, 1
0x18001575f  mov     dword ptr [rsp+1500h+var_14E0], edx
0x180015763  mov     ecx, ebx
0x180015765  mov     eax, 8
0x18001576a  cmp     [r8+8], edx
0x18001576e  cmovz   ecx, eax
0x180015771  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180015775  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7PEAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18001577d  inc     edx
0x18001577f  mov     [rsp+1500h+var_14D0], edx
0x180015783  mov     rcx, [rbp+1400h+arg_38]
0x18001578a  test    rcx, rcx
0x18001578d  jz      short loc_180015799
0x18001578f  cmp     [rcx], bx
0x180015792  mov     [rsp+1500h+var_14C8], rcx
0x180015797  jnz     short loc_18001579E
0x180015799  mov     [rsp+1500h+var_14C8], rbx
0x18001579e  call    cs:__imp_GetCurrentThreadId
0x1800157a4  mov     [rsp+1500h+var_14C0], eax
0x1800157a8  mov     [rsp+1500h+var_14A8], r14
0x1800157ad  mov     [rsp+1500h+var_14A0], esi
0x1800157b1  mov     [rsp+1500h+var_149C], r12d
0x1800157b6  mov     [rsp+1500h+var_14B8], rbx
0x1800157bb  mov     [rsp+1500h+var_14B0], rbx
0x1800157c0  mov     [rbp+1400h+var_1458], r15
0x1800157c4  mov     [rbp+1400h+var_1450], rdi
0x1800157c8  mov     [rsp+1500h+var_1498], rbx
0x1800157cd  xorps   xmm0, xmm0
0x1800157d0  xor     eax, eax
0x1800157d2  movups  [rbp+1400h+var_1478], xmm0
0x1800157d6  mov     [rbp+1400h+var_1468], rax
0x1800157da  xorps   xmm1, xmm1
0x1800157dd  movups  [rsp+1500h+var_1490], xmm1
0x1800157e2  mov     [rbp+1400h+var_1480], rax
0x1800157e6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800157ed  test    rax, rax
0x1800157f0  jz      short loc_1800157FE
0x1800157f2  call    cs:__guard_dispatch_icall_fptr
0x1800157f8  mov     [rbp+1400h+var_1460], rax
0x1800157fc  jmp     short loc_180015802
0x1800157fe  mov     [rbp+1400h+var_1460], rbx
0x180015802  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180015809  test    rax, rax
0x18001580c  jz      short loc_180015819
0x18001580e  lea     rcx, [rsp+1500h+var_14E0]
0x180015813  call    cs:__guard_dispatch_icall_fptr
0x180015819  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180015820  test    rax, rax
0x180015823  jz      short loc_18001583A
0x180015825  mov     r8d, 400h
0x18001582b  lea     rdx, [rbp+1400h+var_1440]
0x18001582f  lea     rcx, [rsp+1500h+var_14E0]
0x180015834  call    cs:__guard_dispatch_icall_fptr
0x18001583a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015841  test    rax, rax
0x180015844  jz      short loc_180015851
0x180015846  lea     rcx, [rsp+1500h+var_14E0]
0x18001584b  call    cs:__guard_dispatch_icall_fptr
0x180015851  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015858  test    rax, rax
0x18001585b  jz      short loc_18001586F
0x18001585d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180015862  jnz     short loc_18001586F
0x180015864  lea     rcx, [rsp+1500h+var_14E0]
0x180015869  call    cs:__guard_dispatch_icall_fptr
0x18001586f  cmp     [rsp+1500h+var_14D8], ebx
0x180015873  jge     loc_180015985
0x180015879  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x18001587f  jnz     short loc_1800158A7
0x180015881  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180015888  test    rax, rax
0x18001588b  jz      short loc_180015898
0x18001588d  call    cs:__guard_dispatch_icall_fptr
0x180015893  movzx   ebx, al
0x180015896  jmp     short loc_1800158A3
0x180015898  call    cs:__imp_IsDebuggerPresent
0x18001589e  test    eax, eax
0x1800158a0  setnz   bl
0x1800158a3  test    ebx, ebx
0x1800158a5  jz      short loc_1800158AE
0x1800158a7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800158ac  jz      short loc_1800158D5
0x1800158ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800158b5  test    rax, rax
0x1800158b8  jz      short loc_18001592F
0x1800158ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1800158c1  jnz     short loc_18001592F
0x1800158c3  xor     r8d, r8d
0x1800158c6  xor     edx, edx
0x1800158c8  lea     rcx, [rsp+1500h+var_14E0]
0x1800158cd  call    cs:__guard_dispatch_icall_fptr
0x1800158d3  jmp     short loc_18001592F
0x1800158d5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800158dc  test    rax, rax
0x1800158df  jz      short loc_180015902
0x1800158e1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1800158e8  jnz     short loc_180015902
0x1800158ea  mov     r8d, 800h
0x1800158f0  lea     rdx, [rbp+1400h+OutputString]
0x1800158f7  lea     rcx, [rsp+1500h+var_14E0]
0x1800158fc  call    cs:__guard_dispatch_icall_fptr
0x180015902  cmp     [rbp+1400h+OutputString], 0
0x18001590a  jnz     short loc_180015922
0x18001590c  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180015911  mov     edx, 800h; wchar_t *
0x180015916  lea     rcx, [rbp+1400h+OutputString]; this
0x18001591d  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180015922  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180015929  call    cs:__imp_OutputDebugStringW
0x18001592f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180015934  jnz     short loc_18001593F
0x180015936  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x18001593d  jz      short loc_180015952
0x18001593f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180015946  test    rax, rax
0x180015949  jz      short loc_180015952
0x18001594b  call    cs:__guard_dispatch_icall_fptr
0x180015951  nop
0x180015952  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180015957  jnz     short loc_18001597A
0x180015959  mov     rcx, [rbp+1400h+var_40]
0x180015960  xor     rcx, rsp; StackCookie
0x180015963  call    __security_check_cookie
0x180015968  add     rsp, 14D0h
0x18001596f  pop     r15
0x180015971  pop     r14
0x180015973  pop     r12
0x180015975  pop     rdi
0x180015976  pop     rsi
0x180015977  pop     rbx
0x180015978  pop     rbp
0x180015979  retn
0x18001597a  lea     rcx, [rsp+1500h+var_14E0]; this
0x18001597f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180015985  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
