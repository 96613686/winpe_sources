# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18002f010`
- end: `0x18002f185`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `373`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `7`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ee10`
- `0x180013670`
- `0x18002efb0`
- `0x18002efd4`
- `0x180041438`
- `0x1800707b8`
- `0x18008f628`

## callees

- `0x18002f010`
- `0x1800475b0`
- `0x18005ba40`
- `0x18005f3b0`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f14c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f14c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f0b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f0b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f0c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f0c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f039`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f095`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f039`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f095`

## string_xrefs

- `0x18002f145`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // r14
  unsigned __int64 CurrentThreadId; // rbx
  unsigned __int64 v4; // r15
  __int64 i; // rax
  _QWORD *v6; // rcx
  HANDLE ProcessHeap; // rbp
  char *v8; // rsi
  void (__fastcall *ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z)(HANDLE, char *); // rax
  signed __int64 v10; // rax
  const struct wil::FailureInfo *v11; // rdx
  HMODULE ModuleHandleW; // rax
  _BYTE v13[216]; // [rsp+20h] [rbp-D8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v11);
  }
  v2 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = 8 * ((CurrentThreadId >> 2) % 0xA);
    for ( i = *(_QWORD *)(v4 + v2); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        v6 = (_QWORD *)(i + 16);
        goto LABEL_8;
      }
    }
    ProcessHeap = GetProcessHeap();
    v8 = (char *)HeapAlloc(ProcessHeap, 0, 0x18u);
    ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, char *))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
    if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
      || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
      && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
        ? (ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, char *))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
        : (void (__fastcall *)(HANDLE, char *))(ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, char *))___GetProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ModuleHandleW),
                                                `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z),
          `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
          ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z) )
    {
      ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ProcessHeap, v8);
    }
    if ( v8 )
    {
      *(_DWORD *)v8 = CurrentThreadId;
      *((_DWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 1) = 0;
      v6 = v8 + 16;
      *((_QWORD *)v8 + 2) = 0;
      do
      {
        v10 = *(_QWORD *)(v4 + v2);
        *((_QWORD *)v8 + 1) = v10;
      }
      while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v4 + v2), (signed __int64)v8, v10) );
    }
    else
    {
      v6 = 0;
    }
LABEL_8:
    *(_QWORD *)this = v6;
    if ( v6 )
    {
      *((_QWORD *)this + 2) = *v6;
      *v6 = this;
      *((_DWORD *)this + 6) = GetCurrentThreadId();
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18002f010  push    rbx
0x18002f012  push    rbp
0x18002f013  push    rsi
0x18002f014  push    rdi
0x18002f015  push    r14
0x18002f017  push    r15
0x18002f019  sub     rsp, 0C8h
0x18002f020  mov     rdi, rcx
0x18002f023  cmp     dword ptr [rcx+18h], 0
0x18002f027  jnz     loc_18002F11F
0x18002f02d  mov     r14, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002f034  test    r14, r14
0x18002f037  jz      short loc_18002F0AE
0x18002f039  call    cs:__imp_GetCurrentThreadId
0x18002f03f  mov     ebx, eax
0x18002f041  mov     r8d, eax
0x18002f044  shr     r8, 2
0x18002f048  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002f052  mul     r8
0x18002f055  shr     rdx, 3
0x18002f059  lea     rcx, [rdx+rdx*4]
0x18002f05d  add     rcx, rcx
0x18002f060  sub     r8, rcx
0x18002f063  lea     r15, ds:0[r8*8]
0x18002f06b  mov     rax, [r15+r14]
0x18002f06f  nop
0x18002f070  test    rax, rax
0x18002f073  jz      short loc_18002F0B5
0x18002f075  cmp     [rax], ebx
0x18002f077  jz      short loc_18002F07F
0x18002f079  mov     rax, [rax+8]
0x18002f07d  jmp     short loc_18002F070
0x18002f07f  lea     rcx, [rax+10h]
0x18002f083  mov     [rdi], rcx
0x18002f086  test    rcx, rcx
0x18002f089  jz      short loc_18002F09E
0x18002f08b  mov     rax, [rcx]
0x18002f08e  mov     [rdi+10h], rax
0x18002f092  mov     [rcx], rdi
0x18002f095  call    cs:__imp_GetCurrentThreadId
0x18002f09b  mov     [rdi+18h], eax
0x18002f09e  add     rsp, 0C8h
0x18002f0a5  pop     r15
0x18002f0a7  pop     r14
0x18002f0a9  pop     rdi
0x18002f0aa  pop     rsi
0x18002f0ab  pop     rbp
0x18002f0ac  pop     rbx
0x18002f0ad  retn
0x18002f0ae  xor     eax, eax
0x18002f0b0  mov     [rcx], rax
0x18002f0b3  jmp     short loc_18002F09E
0x18002f0b5  call    cs:__imp_GetProcessHeap
0x18002f0bb  mov     rbp, rax
0x18002f0be  xor     edx, edx; dwFlags
0x18002f0c0  mov     r8d, 18h; dwBytes
0x18002f0c6  mov     rcx, rax; hHeap
0x18002f0c9  call    cs:__imp_HeapAlloc
0x18002f0cf  mov     rsi, rax
0x18002f0d2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002f0d9  test    rax, rax
0x18002f0dc  jz      short loc_18002F13C
0x18002f0de  mov     rdx, rsi
0x18002f0e1  mov     rcx, rbp
0x18002f0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0e9  nop
0x18002f0ea  xor     eax, eax
0x18002f0ec  test    rsi, rsi
0x18002f0ef  jz      short loc_18002F117
0x18002f0f1  mov     [rsi], ebx
0x18002f0f3  mov     [rsi+4], eax
0x18002f0f6  mov     [rsi+8], rax
0x18002f0fa  lea     rcx, [rsi+10h]
0x18002f0fe  mov     [rcx], rax
0x18002f101  mov     rax, [r15+r14]
0x18002f105  mov     [rsi+8], rax
0x18002f109  lock cmpxchg [r15+r14], rsi
0x18002f10f  jz      loc_18002F083
0x18002f115  jmp     short loc_18002F101
0x18002f117  mov     rcx, rax
0x18002f11a  jmp     loc_18002F083
0x18002f11f  xor     edx, edx; Val
0x18002f121  mov     r8d, 98h; Size
0x18002f127  lea     rcx, [rsp+0F8h+var_D8]; void *
0x18002f12c  call    memset_0
0x18002f131  lea     rcx, [rsp+0F8h+var_D8]; this
0x18002f136  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18002f13c  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 0; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002f143  jnz     short loc_18002F0EA
0x18002f145  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18002f14c  call    cs:__imp_GetModuleHandleW
0x18002f152  test    rax, rax
0x18002f155  jz      short loc_18002F168
0x18002f157  mov     rcx, rax
0x18002f15a  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18002f15f  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18002f166  jmp     short loc_18002F16F
0x18002f168  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002f16f  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002f176  test    rax, rax
0x18002f179  jz      loc_18002F0EA
0x18002f17f  jmp     loc_18002F0DE
```
