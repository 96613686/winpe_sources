# VndCompletionThreadpool::AllocateAndStartNewThread(uint,int)

- ea: `0x14027dfbc`
- end: `0x14027e185`
- name: `?AllocateAndStartNewThread@VndCompletionThreadpool@@AEAAPEAVVndCompletionThread@@IH@Z`
- size: `457`
- prototype: `struct VndCompletionThread *__fastcall(VndCompletionThreadpool *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400da214`

## callees

- `0x140031c88`
- `0x14003364c`
- `0x140042240`
- `0x140054af0`
- `0x140055de0`
- `0x14005ddd0`
- `0x14006af38`
- `0x1400d2d7c`
- `0x140132940`
- `0x140132cec`
- `0x1401335fc`
- `0x14027dfbc`
- `0x14027e2cc`
- `0x14027e640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027e09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027e11b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027e09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027e11b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriorityBoost` at `0x14027e0f5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriorityBoost` at `0x14027e0f5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14027e10b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14027e10b`
- `vid!VidMessageSlotMap` at `0x14027e08d`
- `vid!VidMessageSlotMap` at `0x14027e08d`

## string_xrefs

- `0x14027e00e`: `VndCompletionThreadpoolThread prio %d index %d`
- `0x14027e0c4`: `onecore\vm\worker\vidpartition\vndcompletionthreadpool.cpp`
- `0x14027e13c`: `Failed to set VND thread priority! Error = %u\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct VndCompletionThread *__fastcall VndCompletionThreadpool::AllocateAndStartNewThread(
        VndCompletionThreadpool *this,
        unsigned int a2,
        int a3)
{
  VndCompletionThread *v5; // rax
  Vml::VmThread *v6; // rbx
  __int64 v7; // rdi
  signed int LastError; // eax
  const unsigned __int16 *v9; // rdx
  DWORD v10; // edi
  int v12; // [rsp+20h] [rbp-50h]
  Vml::VmThread *v13; // [rsp+30h] [rbp-40h] BYREF
  void *v14; // [rsp+38h] [rbp-38h]
  unsigned __int16 *v15[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v16; // [rsp+50h] [rbp-20h]
  unsigned __int64 v17; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v13 = 0;
  *(_OWORD *)v15 = 0;
  v16 = 0;
  v17 = 7;
  LOWORD(v15[0]) = 0;
  Vml::FormatString(v15, L"VndCompletionThreadpoolThread prio %d index %d", *((unsigned int *)this + 32), a2);
  v14 = operator new(0xF0u);
  memset_0(v14, 0, 0xF0u);
  v5 = VndCompletionThread::VndCompletionThread((VndCompletionThread *)v14, this, a3);
  Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(&v13, v5);
  v6 = v13;
  v7 = **(_QWORD **)(*((_QWORD *)v13 + 15) + 120LL);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)v13 + 152,
    0);
  if ( *((int *)v6 + 36) < 0 || (unsigned int)VidMessageSlotMap(*(_QWORD *)(v7 + 40), (char *)v6 + 128) )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  if ( LastError < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecore\\vm\\worker\\vidpartition\\vndcompletionthreadpool.cpp",
      (const char *)(unsigned int)LastError,
      v12);
  v9 = (const unsigned __int16 *)v15;
  if ( v17 > 7 )
    v9 = v15[0];
  Vml::VmThread::Start(v6, v9);
  SetThreadPriorityBoost(*((HANDLE *)v6 + 8), 1);
  if ( !SetThreadPriority(*((HANDLE *)v6 + 8), *((_DWORD *)this + 32)) )
  {
    v10 = GetLastError();
    if ( (unsigned int)VmlIsDebugTraceEnabled(32804) )
      VmlDebugTrace(32804, L"Failed to set VND thread priority! Error = %u\n", v10);
  }
  v13 = 0;
  std::wstring::_Tidy_deallocate(v15);
  Vml::VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>::~VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>(&v13);
  return v6;
}

```

## disassembly

```asm
0x14027dfbc  mov     [rsp-18h+arg_18], rbx
0x14027dfc1  push    rbp
0x14027dfc2  push    rsi
0x14027dfc3  push    rdi
0x14027dfc4  mov     rbp, rsp
0x14027dfc7  sub     rsp, 70h
0x14027dfcb  mov     rax, cs:__security_cookie
0x14027dfd2  xor     rax, rsp
0x14027dfd5  mov     [rbp+var_10], rax
0x14027dfd9  mov     edi, r8d
0x14027dfdc  mov     rsi, rcx
0x14027dfdf  mov     [rbp+var_40], 0
0x14027dfe7  xorps   xmm0, xmm0
0x14027dfea  movups  xmmword ptr [rbp+var_30], xmm0
0x14027dfee  mov     [rbp+var_20], 0
0x14027dff6  mov     [rbp+var_18], 7
0x14027dffe  xor     eax, eax
0x14027e000  mov     word ptr [rbp+var_30], ax
0x14027e004  mov     r9d, edx
0x14027e007  mov     r8d, [rcx+80h]
0x14027e00e  lea     rdx, aVndcompletiont; "VndCompletionThreadpoolThread prio %d i"...
0x14027e015  lea     rcx, [rbp+var_30]
0x14027e019  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x14027e01e  mov     ecx, 0F0h; Size
0x14027e023  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14027e028  mov     rbx, rax
0x14027e02b  mov     [rbp+var_38], rax
0x14027e02f  xor     edx, edx; Val
0x14027e031  mov     r8d, 0F0h; Size
0x14027e037  mov     rcx, rax; void *
0x14027e03a  call    memset_0
0x14027e03f  mov     r8d, edi; int
0x14027e042  mov     rdx, rsi; struct VndCompletionThreadpool *
0x14027e045  mov     rcx, rbx; this
0x14027e048  call    ??0VndCompletionThread@@QEAA@PEAVVndCompletionThreadpool@@H@Z; VndCompletionThread::VndCompletionThread(VndCompletionThreadpool *,int)
0x14027e04d  mov     rdx, rax
0x14027e050  lea     rcx, [rbp+var_40]
0x14027e054  call    ?Reset@?$VmReferencePtr@VVndCompletionThread@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVVndCompletionThread@@@Z; Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(VndCompletionThread *)
0x14027e059  mov     rbx, [rbp+var_40]
0x14027e05d  mov     rax, [rbx+78h]
0x14027e061  mov     rcx, [rax+78h]
0x14027e065  mov     rdi, [rcx]
0x14027e068  lea     rcx, [rbx+98h]
0x14027e06f  xor     edx, edx
0x14027e071  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14027e076  mov     r8d, [rbx+90h]
0x14027e07d  test    r8d, r8d
0x14027e080  js      short loc_14027E0B7
0x14027e082  lea     rdx, [rbx+80h]
0x14027e089  mov     rcx, [rdi+28h]
0x14027e08d  call    cs:__imp_VidMessageSlotMap
0x14027e094  nop     dword ptr [rax+rax+00h]
0x14027e099  test    eax, eax
0x14027e09b  jnz     short loc_14027E0B7
0x14027e09d  call    cs:__imp_GetLastError
0x14027e0a4  nop     dword ptr [rax+rax+00h]
0x14027e0a9  test    eax, eax
0x14027e0ab  jle     short loc_14027E0B9
0x14027e0ad  movzx   eax, ax
0x14027e0b0  or      eax, 80070000h
0x14027e0b5  jmp     short loc_14027E0B9
0x14027e0b7  xor     eax, eax
0x14027e0b9  mov     rcx, [rbp+18h]; this
0x14027e0bd  test    eax, eax
0x14027e0bf  jns     short loc_14027E0D6
0x14027e0c1  mov     r9d, eax; char *
0x14027e0c4  lea     r8, aOnecoreVmWorke_58; "onecore\\vm\\worker\\vidpartition\\vndc"...
0x14027e0cb  mov     edx, 102h; void *
0x14027e0d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14027e0d6  lea     rdx, [rbp+var_30]
0x14027e0da  cmp     [rbp+var_18], 7
0x14027e0df  cmova   rdx, [rbp+var_30]; unsigned __int16 *
0x14027e0e4  mov     rcx, rbx; this
0x14027e0e7  call    ?Start@VmThread@Vml@@QEAAXPEBG@Z; Vml::VmThread::Start(ushort const *)
0x14027e0ec  mov     edx, 1; bDisablePriorityBoost
0x14027e0f1  mov     rcx, [rbx+40h]; hThread
0x14027e0f5  call    cs:__imp_SetThreadPriorityBoost
0x14027e0fc  nop     dword ptr [rax+rax+00h]
0x14027e101  mov     edx, [rsi+80h]; nPriority
0x14027e107  mov     rcx, [rbx+40h]; hThread
0x14027e10b  call    cs:__imp_SetThreadPriority
0x14027e112  nop     dword ptr [rax+rax+00h]
0x14027e117  test    eax, eax
0x14027e119  jnz     short loc_14027E14A
0x14027e11b  call    cs:__imp_GetLastError
0x14027e122  nop     dword ptr [rax+rax+00h]
0x14027e127  mov     edi, eax
0x14027e129  mov     esi, 8024h
0x14027e12e  mov     ecx, esi
0x14027e130  call    VmlIsDebugTraceEnabled
0x14027e135  test    eax, eax
0x14027e137  jz      short loc_14027E14A
0x14027e139  mov     r8d, edi
0x14027e13c  lea     rdx, aFailedToSetVnd; "Failed to set VND thread priority! Erro"...
0x14027e143  mov     ecx, esi
0x14027e145  call    VmlDebugTrace
0x14027e14a  mov     [rbp+var_40], 0
0x14027e152  lea     rcx, [rbp+var_30]
0x14027e156  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14027e15b  nop
0x14027e15c  lea     rcx, [rbp+var_40]
0x14027e160  call    ??1?$VmReferencePtr@UIMemoryContentsFileSizeChangeCallback@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>::~VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>(void)
0x14027e165  mov     rax, rbx
0x14027e168  mov     rcx, [rbp+var_10]
0x14027e16c  xor     rcx, rsp; StackCookie
0x14027e16f  call    __security_check_cookie
0x14027e174  mov     rbx, [rsp+70h+arg_18]
0x14027e17c  add     rsp, 70h
0x14027e180  pop     rdi
0x14027e181  pop     rsi
0x14027e182  pop     rbp
0x14027e183  retn
```
