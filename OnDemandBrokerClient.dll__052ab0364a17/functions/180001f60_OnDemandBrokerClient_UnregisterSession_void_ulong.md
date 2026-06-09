# OnDemandBrokerClient::UnregisterSession(void *,ulong)

- ea: `0x180001f60`
- end: `0x18000207c`
- name: `?UnregisterSession@OnDemandBrokerClient@@UEAAJPEAXK@Z`
- size: `284`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001f60`
- `0x180002090`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001fba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001fba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001fe5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001fe5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001f86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001f86`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180002060`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180002060`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180001fcd`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180001fcd`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::UnregisterSession(OnDemandBrokerClient *this, void *a2, unsigned int a3)
{
  unsigned int v6; // ebx
  OnDemandBrokerClient *v7; // rax
  OnDemandBrokerClient *v8; // rdi
  __int64 v9; // rbp
  DWORD CurrentThreadId; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  OnDemandBrokerClient *v17; // rax
  OnDemandBrokerClient **v18; // rcx

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
        _ODB_SESSION_ENTRY::`scalar deleting destructor'(v8);
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
0x180001f60  mov     [rsp+arg_10], rbx
0x180001f65  mov     [rsp+arg_18], rsi
0x180001f6a  push    r12
0x180001f6c  push    r14
0x180001f6e  push    r15
0x180001f70  sub     rsp, 20h
0x180001f74  mov     r14, rcx
0x180001f77  mov     r15d, r8d
0x180001f7a  add     rcx, 18h; lpCriticalSection
0x180001f7e  mov     r12, rdx
0x180001f81  mov     ebx, 80070490h
0x180001f86  call    cs:__imp_EnterCriticalSection
0x180001f8c  mov     rax, [r14+58h]
0x180001f90  lea     r9, [r14+58h]
0x180001f94  mov     [rsp+38h+arg_0], rbp
0x180001f99  mov     [rsp+38h+arg_8], rdi
0x180001f9e  cmp     rax, r9
0x180001fa1  jz      short loc_180001FE1
0x180001fa3  mov     rdi, rax
0x180001fa6  mov     rax, [rax]
0x180001fa9  cmp     [rdi+10h], r15d
0x180001fad  jnz     short loc_180001F9E
0x180001faf  mov     rbp, [rdi+18h]
0x180001fb3  cmp     qword ptr [rbp+58h], 0
0x180001fb8  jz      short loc_18000200C
0x180001fba  call    cs:__imp_GetCurrentThreadId
0x180001fc0  mov     rcx, [rbp+58h]
0x180001fc4  cmp     [rbp+60h], eax
0x180001fc7  jz      loc_180002060
0x180001fcd  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180001fd3  mov     ebx, eax
0x180001fd5  or      ebx, 10000000h
0x180001fdb  jge     loc_18000206B
0x180001fe1  lea     rcx, [r14+18h]; lpCriticalSection
0x180001fe5  call    cs:__imp_LeaveCriticalSection
0x180001feb  mov     rdi, [rsp+38h+arg_8]
0x180001ff0  mov     eax, ebx
0x180001ff2  mov     rbx, [rsp+38h+arg_10]
0x180001ff7  mov     rbp, [rsp+38h+arg_0]
0x180001ffc  mov     rsi, [rsp+38h+arg_18]
0x180002001  add     rsp, 20h
0x180002005  pop     r15
0x180002007  pop     r14
0x180002009  pop     r12
0x18000200b  retn
0x18000200c  mov     rcx, [r14+50h]
0x180002010  mov     rax, [rcx]
0x180002013  test    r12, r12
0x180002016  jz      short loc_180002052
0x180002018  mov     rax, [rax+28h]
0x18000201c  mov     r8d, r15d
0x18000201f  mov     rdx, r12
0x180002022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002027  mov     ebx, eax
0x180002029  test    eax, eax
0x18000202b  js      short loc_180001FE1
0x18000202d  mov     rax, [rdi]
0x180002030  cmp     [rax+8], rdi
0x180002034  jnz     short loc_180002075
0x180002036  mov     rcx, [rdi+8]
0x18000203a  cmp     [rcx], rdi
0x18000203d  jnz     short loc_180002075
0x18000203f  mov     [rcx], rax
0x180002042  mov     [rax+8], rcx
0x180002046  mov     rcx, rdi; this
0x180002049  call    ??_G_ODB_SESSION_ENTRY@@QEAAPEAXI@Z; _ODB_SESSION_ENTRY::`scalar deleting destructor'(uint)
0x18000204e  xor     ebx, ebx
0x180002050  jmp     short loc_180001FE1
0x180002052  mov     rax, [rax+30h]
0x180002056  mov     edx, r15d
0x180002059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000205e  jmp     short loc_180002027
0x180002060  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x180002066  jmp     loc_180001FD3
0x18000206b  mov     qword ptr [rbp+58h], 0
0x180002073  jmp     short loc_18000200C
0x180002075  mov     ecx, 3
0x18000207a  int     29h; Win8: RtlFailFast(ecx)
```
