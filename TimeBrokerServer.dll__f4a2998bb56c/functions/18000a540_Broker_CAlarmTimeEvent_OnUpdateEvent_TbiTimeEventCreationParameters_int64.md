# Broker::CAlarmTimeEvent::OnUpdateEvent(_TbiTimeEventCreationParameters &,__int64)

- ea: `0x18000a540`
- end: `0x18000a66b`
- name: `?OnUpdateEvent@CAlarmTimeEvent@Broker@@UEAAXAEAU_TbiTimeEventCreationParameters@@_J@Z`
- size: `299`
- prototype: `void __fastcall(Broker::CAlarmTimeEvent *__hidden this, struct _TbiTimeEventCreationParameters *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180009ea0`
- `0x180009f70`
- `0x18000a540`
- `0x18001c010`

## import_xrefs

- `BrokerLib!BrGetBrokeredEventState` at `0x18000a5fd`
- `BrokerLib!BrGetBrokeredEventState` at `0x18000a5fd`

## pseudocode

```c
void __fastcall Broker::CAlarmTimeEvent::OnUpdateEvent(
        Broker::CAlarmTimeEvent *this,
        struct _TbiTimeEventCreationParameters *a2,
        __int64 a3)
{
  __int64 v5; // rdx
  __int64 v7; // rbx
  __int64 v8; // rcx
  bool v9; // zf
  int v10; // [rsp+50h] [rbp+8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+10h]

  v5 = *((_QWORD *)this + 31);
  v7 = *(_QWORD *)(v5 + 16);
  v11 = v7;
  v10 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids,
      (unsigned int)v7,
      HIDWORD(v7));
    v5 = *((_QWORD *)this + 31);
  }
  *((_QWORD *)this + 8) = 10000000LL * *((unsigned int *)a2 + 6);
  *((_QWORD *)this + 7) = 10000000LL * *((unsigned int *)a2 + 7);
  v8 = *((_QWORD *)this + 30);
  *(_OWORD *)((char *)this + 284) = *(_OWORD *)((char *)a2 + 8);
  v9 = *((_DWORD *)a2 + 8) == 0;
  *((_BYTE *)this + 320) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_BYTE *)this + 321) = !v9;
  if ( !(unsigned int)BrGetBrokeredEventState(v8, v5, &v10) && v10 == 1 )
  {
    Broker::TimeEvent::SetState(this, 4);
    (*(void (__fastcall **)(Broker::CAlarmTimeEvent *, __int64))(*(_QWORD *)this + 72LL))(this, a3);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids,
      (unsigned int)v7,
      HIDWORD(v11));
}

```

## disassembly

```asm
0x18000a540  mov     [rsp+arg_10], rbx
0x18000a545  push    rbp
0x18000a546  push    rsi
0x18000a547  push    rdi
0x18000a548  sub     rsp, 30h
0x18000a54c  mov     rsi, rdx
0x18000a54f  mov     rbp, r8
0x18000a552  mov     rdx, [rcx+0F8h]
0x18000a559  mov     rdi, rcx
0x18000a55c  mov     rbx, [rdx+10h]
0x18000a560  mov     [rsp+48h+arg_8], rbx
0x18000a565  mov     [rsp+48h+arg_0], 0
0x18000a56d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a574  test    byte ptr [rcx+1Ch], 1
0x18000a578  jz      short loc_18000A5AA
0x18000a57a  cmp     byte ptr [rcx+19h], 4
0x18000a57e  jb      short loc_18000A5AA
0x18000a580  mov     rcx, [rcx+10h]
0x18000a584  lea     r8, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x18000a58b  mov     rax, rbx
0x18000a58e  mov     edx, 19h
0x18000a593  shr     rax, 20h
0x18000a597  mov     r9d, ebx
0x18000a59a  mov     [rsp+48h+var_28], eax
0x18000a59e  call    WPP_SF_DD
0x18000a5a3  mov     rdx, [rdi+0F8h]
0x18000a5aa  mov     eax, [rsi+18h]
0x18000a5ad  lea     r8, [rsp+48h+arg_0]
0x18000a5b2  imul    rcx, rax, 989680h
0x18000a5b9  mov     [rdi+40h], rcx
0x18000a5bd  mov     eax, [rsi+1Ch]
0x18000a5c0  imul    rcx, rax, 989680h
0x18000a5c7  mov     [rdi+38h], rcx
0x18000a5cb  movups  xmm0, xmmword ptr [rsi+8]
0x18000a5cf  mov     rcx, [rdi+0F0h]
0x18000a5d6  movdqu  xmmword ptr [rdi+11Ch], xmm0
0x18000a5de  cmp     dword ptr [rsi+20h], 0
0x18000a5e2  mov     byte ptr [rdi+140h], 0
0x18000a5e9  setnz   al
0x18000a5ec  mov     qword ptr [rdi+138h], 0
0x18000a5f7  mov     [rdi+141h], al
0x18000a5fd  call    cs:__imp_BrGetBrokeredEventState
0x18000a603  test    eax, eax
0x18000a605  jnz     short loc_18000A62B
0x18000a607  cmp     [rsp+48h+arg_0], 1
0x18000a60c  jnz     short loc_18000A62B
0x18000a60e  lea     edx, [rax+4]
0x18000a611  mov     rcx, rdi
0x18000a614  call    ?SetState@TimeEvent@Broker@@IEAAXW4States@12@@Z; Broker::TimeEvent::SetState(Broker::TimeEvent::States)
0x18000a619  mov     rax, [rdi]
0x18000a61c  mov     rdx, rbp
0x18000a61f  mov     rcx, rdi
0x18000a622  mov     rax, [rax+48h]
0x18000a626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a62b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a632  test    byte ptr [rcx+1Ch], 1
0x18000a636  jz      short loc_18000A65E
0x18000a638  cmp     byte ptr [rcx+19h], 4
0x18000a63c  jb      short loc_18000A65E
0x18000a63e  mov     eax, dword ptr [rsp+48h+arg_8+4]
0x18000a642  lea     r8, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x18000a649  mov     rcx, [rcx+10h]
0x18000a64d  mov     edx, 1Ah
0x18000a652  mov     r9d, ebx
0x18000a655  mov     [rsp+48h+var_28], eax
0x18000a659  call    WPP_SF_DD
0x18000a65e  mov     rbx, [rsp+48h+arg_10]
0x18000a663  add     rsp, 30h
0x18000a667  pop     rdi
0x18000a668  pop     rsi
0x18000a669  pop     rbp
0x18000a66a  retn
```
