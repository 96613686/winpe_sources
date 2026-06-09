# RunFlowThread(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),THREAD_CONTEXT *)

- ea: `0x14001fc88`
- end: `0x14001fde1`
- name: `?RunFlowThread@@YAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@ZPEAUTHREAD_CONTEXT@@@Z`
- size: `345`
- prototype: `__int64 __fastcall(PTP_WORK_CALLBACK pfnwk, unsigned int *pv)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14001b6c4`
- `0x140076d44`

## callees

- `0x14000e624`
- `0x14001fc88`
- `0x14002dd70`
- `0x14002de74`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x14001fca1`
- `KERNEL32!TlsGetValue` at `0x14001fca1`
- `KERNEL32!CreateThreadpoolWork` at `0x14001fd42`
- `KERNEL32!CreateThreadpoolWork` at `0x14001fd42`
- `KERNEL32!SubmitThreadpoolWork` at `0x14001fd61`
- `KERNEL32!SubmitThreadpoolWork` at `0x14001fd61`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x14001fd6c`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x14001fd6c`
- `KERNEL32!CloseThreadpoolWork` at `0x14001fd75`
- `KERNEL32!CloseThreadpoolWork` at `0x14001fd75`
- `KERNEL32!TlsSetValue` at `0x14001fcda`
- `KERNEL32!TlsSetValue` at `0x14001fcda`
- `USER32!ChangeWindowMessageFilter` at `0x14001fd58`
- `USER32!ChangeWindowMessageFilter` at `0x14001fd58`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RunFlowThread(PTP_WORK_CALLBACK pfnwk, unsigned int *pv)
{
  _DWORD *Value; // rax
  _DWORD *v5; // rbx
  int v6; // eax
  __int64 v7; // rcx
  struct _TP_WORK *ThreadpoolWork; // rsi
  unsigned int v9; // esi
  unsigned int v10; // edx
  __int64 v11; // rdi
  _QWORD TlsValue[9]; // [rsp+30h] [rbp-48h] BYREF
  DWORD v14; // [rsp+88h] [rbp+10h] BYREF

  Value = TlsGetValue(__g_tracingTlsSlot);
  v14 = -1;
  v5 = Value;
  TlsValue[0] = 0;
  if ( !Value )
  {
    v14 = __g_tracingTlsSlot;
    v5 = TlsValue;
    TlsSetValue(__g_tracingTlsSlot, TlsValue);
  }
  v6 = ++*v5;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    if ( (unsigned int)(5 * v6) > 0x1E1 )
      v7 = 0;
    else
      v7 = 479LL - (unsigned int)(5 * v6);
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      104,
      &WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids,
      &asc_1400849C0[v7]);
  }
  ThreadpoolWork = CreateThreadpoolWork(pfnwk, pv, 0);
  if ( ThreadpoolWork )
  {
    ChangeWindowMessageFilter(0x10u, 1u);
    SubmitThreadpoolWork(ThreadpoolWork);
    WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 0);
    CloseThreadpoolWork(ThreadpoolWork);
  }
  v9 = pv[8];
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v10 = 5 * *v5;
    if ( v10 > 0x1E1 )
      v11 = 0;
    else
      v11 = 479LL - v10;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      105,
      (unsigned int)&WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids,
      (unsigned int)&asc_1400849C0[v11],
      pv[8]);
  }
  --*v5;
  TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(&v14);
  return v9;
}

```

## disassembly

```asm
0x14001fc88  push    rbx
0x14001fc8a  push    rbp
0x14001fc8b  push    rsi
0x14001fc8c  push    rdi
0x14001fc8d  push    r12
0x14001fc8f  push    r13
0x14001fc91  sub     rsp, 48h
0x14001fc95  mov     rsi, rcx
0x14001fc98  mov     rbp, rdx
0x14001fc9b  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x14001fca1  call    cs:__imp_TlsGetValue
0x14001fca7  mov     [rsp+78h+arg_8], 0FFFFFFFFh
0x14001fcb2  mov     rbx, rax
0x14001fcb5  mov     [rsp+78h+TlsValue], 0
0x14001fcbe  test    rax, rax
0x14001fcc1  jnz     short loc_14001FCE0
0x14001fcc3  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x14001fcc9  lea     rdx, [rsp+78h+TlsValue]; lpTlsValue
0x14001fcce  mov     [rsp+78h+arg_8], ecx
0x14001fcd5  lea     rbx, [rsp+78h+TlsValue]
0x14001fcda  call    cs:__imp_TlsSetValue
0x14001fce0  inc     dword ptr [rbx]
0x14001fce2  mov     eax, [rbx]
0x14001fce4  mov     r10, cs:WPP_GLOBAL_Control
0x14001fceb  lea     r12, WPP_GLOBAL_Control
0x14001fcf2  lea     r13, asc_1400849C0; "                                       "...
0x14001fcf9  mov     edi, 1DFh
0x14001fcfe  cmp     r10, r12
0x14001fd01  jz      short loc_14001FD39
0x14001fd03  test    byte ptr [r10+1Ch], 80h
0x14001fd08  jz      short loc_14001FD39
0x14001fd0a  lea     ecx, [rax+rax*4]
0x14001fd0d  cmp     ecx, 1E1h
0x14001fd13  ja      short loc_14001FD1E
0x14001fd15  mov     eax, ecx
0x14001fd17  mov     ecx, edi
0x14001fd19  sub     rcx, rax
0x14001fd1c  jmp     short loc_14001FD20
0x14001fd1e  xor     ecx, ecx
0x14001fd20  lea     r9, [rcx+r13]
0x14001fd24  mov     edx, 68h ; 'h'
0x14001fd29  mov     rcx, [r10+10h]
0x14001fd2d  lea     r8, WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids
0x14001fd34  call    WPP_SF_s
0x14001fd39  xor     r8d, r8d; pcbe
0x14001fd3c  mov     rdx, rbp; pv
0x14001fd3f  mov     rcx, rsi; pfnwk
0x14001fd42  call    cs:__imp_CreateThreadpoolWork
0x14001fd48  mov     rsi, rax
0x14001fd4b  test    rax, rax
0x14001fd4e  jz      short loc_14001FD7B
0x14001fd50  mov     edx, 1; dwFlag
0x14001fd55  lea     ecx, [rdx+0Fh]; message
0x14001fd58  call    cs:__imp_ChangeWindowMessageFilter
0x14001fd5e  mov     rcx, rsi; pwk
0x14001fd61  call    cs:__imp_SubmitThreadpoolWork
0x14001fd67  xor     edx, edx; fCancelPendingCallbacks
0x14001fd69  mov     rcx, rsi; pwk
0x14001fd6c  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x14001fd72  mov     rcx, rsi; pwk
0x14001fd75  call    cs:__imp_CloseThreadpoolWork
0x14001fd7b  mov     esi, [rbp+20h]
0x14001fd7e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fd85  cmp     rcx, r12
0x14001fd88  jz      short loc_14001FDC3
0x14001fd8a  test    byte ptr [rcx+1Ch], 80h
0x14001fd8e  jz      short loc_14001FDC3
0x14001fd90  mov     eax, [rbx]
0x14001fd92  lea     edx, [rax+rax*4]
0x14001fd95  cmp     edx, 1E1h
0x14001fd9b  ja      short loc_14001FDA4
0x14001fd9d  mov     eax, edx
0x14001fd9f  sub     rdi, rax
0x14001fda2  jmp     short loc_14001FDA6
0x14001fda4  xor     edi, edi
0x14001fda6  mov     rcx, [rcx+10h]
0x14001fdaa  lea     r9, [rdi+r13]
0x14001fdae  mov     edx, 69h ; 'i'
0x14001fdb3  mov     [rsp+78h+var_58], esi
0x14001fdb7  lea     r8, WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids
0x14001fdbe  call    WPP_SF_sd
0x14001fdc3  dec     dword ptr [rbx]
0x14001fdc5  lea     rcx, [rsp+78h+arg_8]
0x14001fdcd  call    ??1?$AutoTlsPtr@UTracingContext@TracingInternal@@@TracingInternal@@QEAA@XZ; TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(void)
0x14001fdd2  mov     eax, esi
0x14001fdd4  add     rsp, 48h
0x14001fdd8  pop     r13
0x14001fdda  pop     r12
0x14001fddc  pop     rdi
0x14001fddd  pop     rsi
0x14001fdde  pop     rbp
0x14001fddf  pop     rbx
0x14001fde0  retn
```
