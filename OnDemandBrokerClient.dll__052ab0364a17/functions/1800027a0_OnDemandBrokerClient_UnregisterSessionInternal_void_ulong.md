# OnDemandBrokerClient::UnregisterSessionInternal(void *,ulong)

- ea: `0x1800027a0`
- end: `0x1800028dc`
- name: `?UnregisterSessionInternal@OnDemandBrokerClient@@AEAAJPEAXK@Z`
- size: `316`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180006210`

## callees

- `0x1800027a0`
- `0x18000437c`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800027f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800027f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002824`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002824`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800027c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800027c5`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800028bd`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800028bd`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000280c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000280c`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::UnregisterSessionInternal(
        OnDemandBrokerClient *this,
        void *a2,
        unsigned int a3)
{
  unsigned int v6; // edi
  OnDemandBrokerClient *v7; // rax
  OnDemandBrokerClient *v8; // rbx
  __int64 v9; // r14
  DWORD CurrentThreadId; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  OnDemandBrokerClient *v17; // rax
  OnDemandBrokerClient **v18; // rcx
  __int64 v19; // rcx

  v6 = -2147023728;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v7 = (OnDemandBrokerClient *)*((_QWORD *)this + 11);
  while ( v7 != (OnDemandBrokerClient *)((char *)this + 88) )
  {
    v8 = v7;
    v7 = *(OnDemandBrokerClient **)v7;
    if ( *((_DWORD *)v8 + 4) == a3 )
    {
      v9 = *((_QWORD *)v8 + 3);
      if ( *(_QWORD *)(v9 + 88) )
      {
        CurrentThreadId = GetCurrentThreadId();
        v11 = *(_QWORD *)(v9 + 88);
        if ( *(_DWORD *)(v9 + 96) == CurrentThreadId )
          v12 = RtlUnsubscribeWnfStateChangeNotification(v11);
        else
          v12 = RtlUnsubscribeWnfNotificationWaitForCompletion(v11);
        v6 = v12 | 0x10000000;
        if ( v12 < 0 )
          break;
        *(_QWORD *)(v9 + 88) = 0;
      }
      v14 = (__int64 *)*((_QWORD *)this + 10);
      v15 = *v14;
      if ( a2 )
        v16 = (*(__int64 (__fastcall **)(__int64 *, void *, _QWORD))(v15 + 40))(v14, a2, a3);
      else
        v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v15 + 48))(v14, a3);
      v6 = v16;
      if ( v16 >= 0 )
      {
        v17 = *(OnDemandBrokerClient **)v8;
        if ( *(OnDemandBrokerClient **)(*(_QWORD *)v8 + 8LL) != v8
          || (v18 = (OnDemandBrokerClient **)*((_QWORD *)v8 + 1), *v18 != v8) )
        {
          __fastfail(3u);
        }
        *v18 = v17;
        *((_QWORD *)v17 + 1) = v18;
        v19 = *((_QWORD *)v8 + 3);
        if ( v19 )
        {
          *((_QWORD *)v8 + 3) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        operator delete(v8);
        v6 = 0;
      }
      break;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v6;
}

```

## disassembly

```asm
0x1800027a0  mov     [rsp+arg_10], rbp
0x1800027a5  mov     [rsp+arg_18], rsi
0x1800027aa  push    rdi
0x1800027ab  push    r12
0x1800027ad  push    r15
0x1800027af  sub     rsp, 20h
0x1800027b3  mov     r15, rcx
0x1800027b6  mov     ebp, r8d
0x1800027b9  add     rcx, 18h; lpCriticalSection
0x1800027bd  mov     r12, rdx
0x1800027c0  mov     edi, 80070490h
0x1800027c5  call    cs:__imp_EnterCriticalSection
0x1800027cb  mov     rax, [r15+58h]
0x1800027cf  lea     r9, [r15+58h]
0x1800027d3  mov     [rsp+38h+arg_0], rbx
0x1800027d8  mov     [rsp+38h+arg_8], r14
0x1800027dd  cmp     rax, r9
0x1800027e0  jz      short loc_180002820
0x1800027e2  mov     rbx, rax
0x1800027e5  mov     rax, [rax]
0x1800027e8  cmp     [rbx+10h], ebp
0x1800027eb  jnz     short loc_1800027DD
0x1800027ed  mov     r14, [rbx+18h]
0x1800027f1  cmp     qword ptr [r14+58h], 0
0x1800027f6  jz      short loc_18000284A
0x1800027f8  call    cs:__imp_GetCurrentThreadId
0x1800027fe  mov     rcx, [r14+58h]
0x180002802  cmp     [r14+60h], eax
0x180002806  jz      loc_1800028BD
0x18000280c  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180002812  mov     edi, eax
0x180002814  or      edi, 10000000h
0x18000281a  jge     loc_1800028C8
0x180002820  lea     rcx, [r15+18h]; lpCriticalSection
0x180002824  call    cs:__imp_LeaveCriticalSection
0x18000282a  mov     r14, [rsp+38h+arg_8]
0x18000282f  mov     eax, edi
0x180002831  mov     rbx, [rsp+38h+arg_0]
0x180002836  mov     rbp, [rsp+38h+arg_10]
0x18000283b  mov     rsi, [rsp+38h+arg_18]
0x180002840  add     rsp, 20h
0x180002844  pop     r15
0x180002846  pop     r12
0x180002848  pop     rdi
0x180002849  retn
0x18000284a  mov     rcx, [r15+50h]
0x18000284e  mov     rax, [rcx]
0x180002851  test    r12, r12
0x180002854  jz      short loc_1800028B0
0x180002856  mov     rax, [rax+28h]
0x18000285a  mov     r8d, ebp
0x18000285d  mov     rdx, r12
0x180002860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002865  mov     edi, eax
0x180002867  test    eax, eax
0x180002869  js      short loc_180002820
0x18000286b  mov     rax, [rbx]
0x18000286e  cmp     [rax+8], rbx
0x180002872  jnz     short loc_1800028D5
0x180002874  mov     rcx, [rbx+8]
0x180002878  cmp     [rcx], rbx
0x18000287b  jnz     short loc_1800028D5
0x18000287d  mov     [rcx], rax
0x180002880  mov     [rax+8], rcx
0x180002884  mov     rcx, [rbx+18h]
0x180002888  test    rcx, rcx
0x18000288b  jz      short loc_1800028A1
0x18000288d  mov     qword ptr [rbx+18h], 0
0x180002895  mov     rax, [rcx]
0x180002898  mov     rax, [rax+10h]
0x18000289c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028a1  mov     rcx, rbx; Block
0x1800028a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800028a9  xor     edi, edi
0x1800028ab  jmp     loc_180002820
0x1800028b0  mov     rax, [rax+30h]
0x1800028b4  mov     edx, ebp
0x1800028b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028bb  jmp     short loc_180002865
0x1800028bd  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x1800028c3  jmp     loc_180002812
0x1800028c8  mov     qword ptr [r14+58h], 0
0x1800028d0  jmp     loc_18000284A
0x1800028d5  mov     ecx, 3
0x1800028da  int     29h; Win8: RtlFailFast(ecx)
```
