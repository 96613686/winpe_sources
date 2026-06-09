# OnDemandBrokerClient::UnregisterSession(ulong)

- ea: `0x180001e60`
- end: `0x180001f4c`
- name: `?UnregisterSession@OnDemandBrokerClient@@UEAAJK@Z`
- size: `236`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001e60`
- `0x180002090`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001eb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001eb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001ed4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001ed4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e7d`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180001f33`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180001f33`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180001ec0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180001ec0`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::UnregisterSession(OnDemandBrokerClient *this, unsigned int a2)
{
  int v4; // ebx
  OnDemandBrokerClient *v5; // rax
  OnDemandBrokerClient *v6; // rdi
  __int64 v7; // rbp
  DWORD CurrentThreadId; // eax
  __int64 v9; // rcx
  int v10; // eax
  OnDemandBrokerClient *v12; // rax
  OnDemandBrokerClient **v13; // rcx

  v4 = -2147023728;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v5 = (OnDemandBrokerClient *)*((_QWORD *)this + 11);
  while ( v5 != (OnDemandBrokerClient *)((char *)this + 88) )
  {
    v6 = v5;
    v5 = *(OnDemandBrokerClient **)v5;
    if ( *((_DWORD *)v6 + 4) == a2 )
    {
      v7 = *((_QWORD *)v6 + 3);
      if ( *(_QWORD *)(v7 + 88) )
      {
        CurrentThreadId = GetCurrentThreadId();
        v9 = *(_QWORD *)(v7 + 88);
        if ( *(_DWORD *)(v7 + 96) == CurrentThreadId )
          v10 = RtlUnsubscribeWnfStateChangeNotification(v9);
        else
          v10 = RtlUnsubscribeWnfNotificationWaitForCompletion(v9);
        v4 = v10 | 0x10000000;
        if ( v10 < 0 )
          break;
        *(_QWORD *)(v7 + 88) = 0;
      }
      v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10), a2);
      if ( v4 >= 0 )
      {
        v12 = *(OnDemandBrokerClient **)v6;
        if ( *(OnDemandBrokerClient **)(*(_QWORD *)v6 + 8LL) != v6
          || (v13 = (OnDemandBrokerClient **)*((_QWORD *)v6 + 1), *v13 != v6) )
        {
          __fastfail(3u);
        }
        *v13 = v12;
        *((_QWORD *)v12 + 1) = v13;
        _ODB_SESSION_ENTRY::`scalar deleting destructor'(v6);
        v4 = 0;
      }
      break;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001e60  mov     [rsp+arg_10], rbx
0x180001e65  push    rsi
0x180001e66  push    r14
0x180001e68  push    r15
0x180001e6a  sub     rsp, 20h
0x180001e6e  mov     r14, rcx
0x180001e71  mov     r15d, edx
0x180001e74  add     rcx, 18h; lpCriticalSection
0x180001e78  mov     ebx, 80070490h
0x180001e7d  call    cs:__imp_EnterCriticalSection
0x180001e83  mov     rax, [r14+58h]
0x180001e87  lea     r8, [r14+58h]
0x180001e8b  mov     [rsp+38h+arg_0], rbp
0x180001e90  mov     [rsp+38h+arg_8], rdi
0x180001e95  cmp     rax, r8
0x180001e98  jz      short loc_180001ED0
0x180001e9a  mov     rdi, rax
0x180001e9d  mov     rax, [rax]
0x180001ea0  cmp     [rdi+10h], r15d
0x180001ea4  jnz     short loc_180001E95
0x180001ea6  mov     rbp, [rdi+18h]
0x180001eaa  cmp     qword ptr [rbp+58h], 0
0x180001eaf  jz      short loc_180001EF5
0x180001eb1  call    cs:__imp_GetCurrentThreadId
0x180001eb7  mov     rcx, [rbp+58h]
0x180001ebb  cmp     [rbp+60h], eax
0x180001ebe  jz      short loc_180001F33
0x180001ec0  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180001ec6  mov     ebx, eax
0x180001ec8  or      ebx, 10000000h
0x180001ece  jge     short loc_180001F3B
0x180001ed0  lea     rcx, [r14+18h]; lpCriticalSection
0x180001ed4  call    cs:__imp_LeaveCriticalSection
0x180001eda  mov     rdi, [rsp+38h+arg_8]
0x180001edf  mov     eax, ebx
0x180001ee1  mov     rbx, [rsp+38h+arg_10]
0x180001ee6  mov     rbp, [rsp+38h+arg_0]
0x180001eeb  add     rsp, 20h
0x180001eef  pop     r15
0x180001ef1  pop     r14
0x180001ef3  pop     rsi
0x180001ef4  retn
0x180001ef5  mov     rcx, [r14+50h]
0x180001ef9  mov     edx, r15d
0x180001efc  mov     rax, [rcx]
0x180001eff  mov     rax, [rax+30h]
0x180001f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f08  mov     ebx, eax
0x180001f0a  test    eax, eax
0x180001f0c  js      short loc_180001ED0
0x180001f0e  mov     rax, [rdi]
0x180001f11  cmp     [rax+8], rdi
0x180001f15  jnz     short loc_180001F45
0x180001f17  mov     rcx, [rdi+8]
0x180001f1b  cmp     [rcx], rdi
0x180001f1e  jnz     short loc_180001F45
0x180001f20  mov     [rcx], rax
0x180001f23  mov     [rax+8], rcx
0x180001f27  mov     rcx, rdi; this
0x180001f2a  call    ??_G_ODB_SESSION_ENTRY@@QEAAPEAXI@Z; _ODB_SESSION_ENTRY::`scalar deleting destructor'(uint)
0x180001f2f  xor     ebx, ebx
0x180001f31  jmp     short loc_180001ED0
0x180001f33  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x180001f39  jmp     short loc_180001EC6
0x180001f3b  mov     qword ptr [rbp+58h], 0
0x180001f43  jmp     short loc_180001EF5
0x180001f45  mov     ecx, 3
0x180001f4a  int     29h; Win8: RtlFailFast(ecx)
```
