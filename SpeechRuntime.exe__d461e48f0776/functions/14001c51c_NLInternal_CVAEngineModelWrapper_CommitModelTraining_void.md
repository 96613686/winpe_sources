# NLInternal::CVAEngineModelWrapper::CommitModelTraining(void)

- ea: `0x14001c51c`
- end: `0x14001c5c0`
- name: `?CommitModelTraining@CVAEngineModelWrapper@NLInternal@@QEAAJXZ`
- size: `164`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001a0b0`

## callees

- `0x140011ea8`
- `0x14001c51c`
- `0x14001c5c8`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001c5a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001c5a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001c535`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001c535`

## string_xrefs

- `0x14001c580`: `NLInternal::CVAEngineModelWrapper::CommitModelTraining`

## pseudocode

```c
__int64 __fastcall NLInternal::CVAEngineModelWrapper::CommitModelTraining(LPVOID *ppv)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax

  v2 = (struct _RTL_CRITICAL_SECTION *)(ppv + 1);
  EnterCriticalSection((LPCRITICAL_SECTION)(ppv + 1));
  v3 = NLInternal::CVAEngineModelWrapper::EnsureInitialized(ppv);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*ppv + 72LL))(*ppv);
    v4 = v5;
    if ( v5 < 0 )
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"NLInternal::CVAEngineModelWrapper::CommitModelTraining",
        L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\voiceactivation\\vaenginemodelwrapper.cpp(128)",
        v5);
  }
  else
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"NLInternal::CVAEngineModelWrapper::CommitModelTraining",
      L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\voiceactivation\\vaenginemodelwrapper.cpp(127)",
      v3);
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  return v4;
}

```

## disassembly

```asm
0x14001c51c  mov     [rsp+arg_8], rbx
0x14001c521  mov     [rsp+arg_10], rsi
0x14001c526  push    rdi
0x14001c527  sub     rsp, 30h
0x14001c52b  mov     rsi, rcx
0x14001c52e  lea     rdi, [rcx+8]
0x14001c532  mov     rcx, rdi; lpCriticalSection
0x14001c535  call    cs:__imp_EnterCriticalSection
0x14001c53b  mov     [rsp+38h+arg_0], rdi
0x14001c540  mov     rcx, rsi; ppv
0x14001c543  call    ?EnsureInitialized@CVAEngineModelWrapper@NLInternal@@AEAAJXZ; NLInternal::CVAEngineModelWrapper::EnsureInitialized(void)
0x14001c548  mov     ebx, eax
0x14001c54a  test    eax, eax
0x14001c54c  jns     short loc_14001C55B
0x14001c54e  mov     [rsp+38h+var_10], eax
0x14001c552  lea     rax, aOnecoreuapEndu_10; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001c559  jmp     short loc_14001C57B
0x14001c55b  mov     rcx, [rsi]
0x14001c55e  mov     rax, [rcx]
0x14001c561  mov     rax, [rax+48h]
0x14001c565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c56a  mov     ebx, eax
0x14001c56c  test    eax, eax
0x14001c56e  jns     short loc_14001C5A0
0x14001c570  mov     [rsp+38h+var_10], eax
0x14001c574  lea     rax, aOnecoreuapEndu_45; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001c57b  mov     [rsp+38h+var_18], rax
0x14001c580  lea     r9, aNlinternalCvae_2; "NLInternal::CVAEngineModelWrapper::Comm"...
0x14001c587  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14001c58e  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14001c595  mov     ecx, 2; int
0x14001c59a  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001c59f  nop
0x14001c5a0  test    rdi, rdi
0x14001c5a3  jz      short loc_14001C5AE
0x14001c5a5  mov     rcx, rdi; lpCriticalSection
0x14001c5a8  call    cs:__imp_LeaveCriticalSection
0x14001c5ae  mov     eax, ebx
0x14001c5b0  mov     rbx, [rsp+38h+arg_8]
0x14001c5b5  mov     rsi, [rsp+38h+arg_10]
0x14001c5ba  add     rsp, 30h
0x14001c5be  pop     rdi
0x14001c5bf  retn
```
