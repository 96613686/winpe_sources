# Broker::KeepAliveEvent::OnUpdateEvent(_TbiTimeEventCreationParameters &,__int64)

- ea: `0x18000cca0`
- end: `0x18000cd51`
- name: `?OnUpdateEvent@KeepAliveEvent@Broker@@UEAAXAEAU_TbiTimeEventCreationParameters@@_J@Z`
- size: `177`
- prototype: `void __fastcall(Broker::KeepAliveEvent *__hidden this, struct _TbiTimeEventCreationParameters *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000cca0`
- `0x18000cd58`
- `0x18001c010`

## import_xrefs

- `BrokerLib!BrGetBrokeredEventState` at `0x18000cd1e`
- `BrokerLib!BrGetBrokeredEventState` at `0x18000cd1e`

## pseudocode

```c
void __fastcall Broker::KeepAliveEvent::OnUpdateEvent(
        Broker::KeepAliveEvent *this,
        struct _TbiTimeEventCreationParameters *a2,
        __int64 a3)
{
  __int64 v3; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  bool v9; // al
  int v10; // [rsp+30h] [rbp+8h] BYREF

  v3 = *((unsigned int *)a2 + 2);
  *((_DWORD *)this + 70) = v3;
  v10 = 0;
  *((_QWORD *)this + 8) = 10000000 * v3;
  *((_QWORD *)this + 7) = 10000000LL
                        * (unsigned int)Broker::KeepAliveEvent::GetEventWindow(*((_DWORD *)a2 + 3), *((_DWORD *)a2 + 2));
  v7 = *((_QWORD *)this + 31);
  *((_QWORD *)this + 6) = 10000000LL * *((unsigned int *)a2 + 4);
  v8 = *((_QWORD *)this + 30);
  v9 = *((_DWORD *)a2 + 5) == 0;
  *((_BYTE *)this + 284) = 0;
  *((_BYTE *)this + 92) = v9;
  if ( !(unsigned int)BrGetBrokeredEventState(v8, v7, &v10) && v10 == 1 )
    (*(void (__fastcall **)(Broker::KeepAliveEvent *, __int64))(*(_QWORD *)this + 72LL))(this, a3);
}

```

## disassembly

```asm
0x18000cca0  mov     [rsp+arg_8], rbx
0x18000cca5  mov     [rsp+arg_10], rsi
0x18000ccaa  push    rdi
0x18000ccab  sub     rsp, 20h
0x18000ccaf  mov     eax, [rdx+8]
0x18000ccb2  mov     rbx, rdx
0x18000ccb5  mov     [rcx+118h], eax
0x18000ccbb  mov     rdi, rcx
0x18000ccbe  imul    r9, rax, 989680h
0x18000ccc5  mov     rsi, r8
0x18000ccc8  mov     [rsp+28h+arg_0], 0
0x18000ccd0  mov     [rcx+40h], r9
0x18000ccd4  mov     edx, [rdx+8]; unsigned int
0x18000ccd7  mov     ecx, [rbx+0Ch]; unsigned int
0x18000ccda  call    ?GetEventWindow@KeepAliveEvent@Broker@@CAKKK@Z; Broker::KeepAliveEvent::GetEventWindow(ulong,ulong)
0x18000ccdf  mov     eax, eax
0x18000cce1  lea     r8, [rsp+28h+arg_0]
0x18000cce6  imul    rdx, rax, 989680h
0x18000cced  mov     [rdi+38h], rdx
0x18000ccf1  mov     eax, [rbx+10h]
0x18000ccf4  mov     rdx, [rdi+0F8h]
0x18000ccfb  imul    rcx, rax, 989680h
0x18000cd02  mov     [rdi+30h], rcx
0x18000cd06  cmp     dword ptr [rbx+14h], 0
0x18000cd0a  mov     rcx, [rdi+0F0h]
0x18000cd11  setz    al
0x18000cd14  mov     byte ptr [rdi+11Ch], 0
0x18000cd1b  mov     [rdi+5Ch], al
0x18000cd1e  call    cs:__imp_BrGetBrokeredEventState
0x18000cd24  test    eax, eax
0x18000cd26  jnz     short loc_18000CD41
0x18000cd28  cmp     [rsp+28h+arg_0], 1
0x18000cd2d  jnz     short loc_18000CD41
0x18000cd2f  mov     rax, [rdi]
0x18000cd32  mov     rdx, rsi
0x18000cd35  mov     rcx, rdi
0x18000cd38  mov     rax, [rax+48h]
0x18000cd3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd41  mov     rbx, [rsp+28h+arg_8]
0x18000cd46  mov     rsi, [rsp+28h+arg_10]
0x18000cd4b  add     rsp, 20h
0x18000cd4f  pop     rdi
0x18000cd50  retn
```
