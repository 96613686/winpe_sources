# PRIVATE_NAMESPACE_Triggers_H::TriggerSystemEvent::Set(void *,_TASK_TRIGGER *,_TASK_RUNTIME_DATA *,TimeValue const &,TimeValue const &,uchar,ulong)

- ea: `0x18001d390`
- end: `0x18001d4e0`
- name: `?Set@TriggerSystemEvent@PRIVATE_NAMESPACE_Triggers_H@@EEAAJPEAXPEAU_TASK_TRIGGER@@PEAU_TASK_RUNTIME_DATA@@AEBVTimeValue@@3EK@Z`
- size: `336`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerSystemEvent *this, void *, struct _TASK_TRIGGER *, struct _TASK_RUNTIME_DATA *, const struct TimeValue *, const struct TimeValue *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000e9c8`
- `0x18001d390`
- `0x180020c30`

## import_xrefs

- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x18001d3f4`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x18001d3f4`
- `EventAggregation!EACreateAggregateEvent` at `0x18001d4b0`
- `EventAggregation!EACreateAggregateEvent` at `0x18001d4b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerSystemEvent::Set(
        PRIVATE_NAMESPACE_Triggers_H::TriggerSystemEvent *this,
        void *a2,
        struct _TASK_TRIGGER *a3,
        struct _TASK_RUNTIME_DATA *a4,
        const struct TimeValue *a5,
        const struct TimeValue *a6,
        char a7)
{
  _QWORD *v8; // rsi
  int v9; // edi
  int v10; // ecx
  int v11; // eax
  _DWORD v13[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v14; // [rsp+38h] [rbp-40h]
  __int64 v15; // [rsp+40h] [rbp-38h]
  __int64 v16; // [rsp+48h] [rbp-30h]
  void (__fastcall *v17)(__int64, __int64, __int64, const void *, unsigned int); // [rsp+50h] [rbp-28h]
  __int64 v18; // [rsp+58h] [rbp-20h]
  __int64 v19; // [rsp+60h] [rbp-18h]

  if ( !a3 || !a2 )
    return 2147500035LL;
  v8 = *(_QWORD **)&a3->wBeginDay;
  if ( v8 )
  {
    *((_QWORD *)this + 22) = a2;
    v10 = *((_DWORD *)this + 50);
    if ( *((_DWORD *)this + 51) | v10 )
    {
      v11 = CSebDeleteEvent(*((_QWORD *)this + 25));
      v9 = v11;
      if ( v11 < 0 && (byte_180030D06 & 8) != 0 )
        McTemplateU0qqq_EventWriteTransfer(
          *((_DWORD *)this + 51),
          (unsigned int)ErrorDeleteCSebEvent,
          v11,
          *((_DWORD *)this + 50),
          *((_DWORD *)this + 51));
      *((_QWORD *)this + 25) = 0;
      v10 = 0;
    }
    else
    {
      v9 = 0;
    }
    *((_DWORD *)this + 46) = 0;
    *((_QWORD *)this + 24) = *v8;
    if ( v9 >= 0 && !a7 )
    {
      v13[0] = v10;
      v17 = CScheduleMgr::BaseCentralEventAggregateCallback;
      v19 = *((_QWORD *)this + 22);
      v13[1] = *((_DWORD *)this + 51);
      v14 = 0;
      v15 = 0;
      v16 = 0;
      v18 = 0;
      return (unsigned int)EACreateAggregateEvent(v13, (char *)this + 208);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001d390  mov     [rsp+arg_8], rbx
0x18001d395  mov     [rsp+arg_10], rsi
0x18001d39a  push    rdi
0x18001d39b  sub     rsp, 70h
0x18001d39f  mov     rax, cs:__security_cookie
0x18001d3a6  xor     rax, rsp
0x18001d3a9  mov     [rsp+78h+var_10], rax
0x18001d3ae  mov     rbx, rcx
0x18001d3b1  test    r8, r8
0x18001d3b4  jz      loc_18001D4BC
0x18001d3ba  test    rdx, rdx
0x18001d3bd  jz      loc_18001D4BC
0x18001d3c3  mov     rsi, [r8+8]
0x18001d3c7  test    rsi, rsi
0x18001d3ca  jnz     short loc_18001D3D6
0x18001d3cc  mov     edi, 80070057h
0x18001d3d1  jmp     loc_18001D4B8
0x18001d3d6  mov     [rcx+0B0h], rdx
0x18001d3dd  mov     ecx, [rcx+0C8h]
0x18001d3e3  mov     eax, ecx
0x18001d3e5  or      eax, [rbx+0CCh]
0x18001d3eb  jz      short loc_18001D436
0x18001d3ed  mov     rcx, [rbx+0C8h]
0x18001d3f4  call    cs:__imp_CSebDeleteEvent
0x18001d3fa  mov     edi, eax
0x18001d3fc  test    eax, eax
0x18001d3fe  jns     short loc_18001D429
0x18001d400  test    cs:byte_180030D06, 8
0x18001d407  jz      short loc_18001D429
0x18001d409  mov     ecx, [rbx+0CCh]
0x18001d40f  lea     rdx, ErrorDeleteCSebEvent
0x18001d416  mov     r9d, [rbx+0C8h]
0x18001d41d  mov     r8d, eax
0x18001d420  mov     [rsp+78h+var_58], ecx
0x18001d424  call    McTemplateU0qqq_EventWriteTransfer
0x18001d429  xor     eax, eax
0x18001d42b  mov     [rbx+0C8h], rax
0x18001d432  xor     ecx, ecx
0x18001d434  jmp     short loc_18001D438
0x18001d436  xor     edi, edi
0x18001d438  mov     dword ptr [rbx+0B8h], 0
0x18001d442  mov     rax, [rsi]
0x18001d445  mov     [rbx+0C0h], rax
0x18001d44c  test    edi, edi
0x18001d44e  js      short loc_18001D4B8
0x18001d450  cmp     [rsp+78h+arg_30], 0
0x18001d458  jnz     short loc_18001D4B8
0x18001d45a  lea     rax, ?BaseCentralEventAggregateCallback@CScheduleMgr@@SAXPEAXU_CBROKERED_EVENT_ID@@00K@Z; CScheduleMgr::BaseCentralEventAggregateCallback(void *,_CBROKERED_EVENT_ID,void *,void *,ulong)
0x18001d461  mov     [rsp+78h+var_48], ecx
0x18001d465  mov     [rsp+78h+var_28], rax
0x18001d46a  lea     rdx, [rbx+0D0h]
0x18001d471  mov     rax, [rbx+0B0h]
0x18001d478  lea     rcx, [rsp+78h+var_48]
0x18001d47d  mov     [rsp+78h+var_18], rax
0x18001d482  mov     eax, [rbx+0CCh]
0x18001d488  mov     [rsp+78h+var_44], eax
0x18001d48c  mov     [rsp+78h+var_40], 0
0x18001d495  mov     [rsp+78h+var_38], 0
0x18001d49e  mov     [rsp+78h+var_30], 0
0x18001d4a7  mov     [rsp+78h+var_20], 0
0x18001d4b0  call    cs:__imp_EACreateAggregateEvent
0x18001d4b6  mov     edi, eax
0x18001d4b8  mov     eax, edi
0x18001d4ba  jmp     short loc_18001D4C1
0x18001d4bc  mov     eax, 80004003h
0x18001d4c1  mov     rcx, [rsp+78h+var_10]
0x18001d4c6  xor     rcx, rsp; StackCookie
0x18001d4c9  call    __security_check_cookie
0x18001d4ce  lea     r11, [rsp+78h+var_8]
0x18001d4d3  mov     rbx, [r11+18h]
0x18001d4d7  mov     rsi, [r11+20h]
0x18001d4db  mov     rsp, r11
0x18001d4de  pop     rdi
0x18001d4df  retn
```
