# BrSignalBrokerEvent2Ex

- ea: `0x180005580`
- end: `0x18000571d`
- name: `BrSignalBrokerEvent2Ex`
- size: `413`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180004f70`

## callees

- `0x180005580`
- `0x180005724`
- `0x1800058e0`
- `0x180005a80`
- `0x180005b90`
- `0x180009e94`
- `0x18001e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BrSignalBrokerEvent2Ex(
        const void *a1,
        __int64 a2,
        const unsigned __int8 *a3,
        struct _GUID *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        struct _GUID *a7)
{
  int v10; // r8d
  __int64 v11; // rbx
  volatile signed __int32 *v12; // rbx
  volatile signed __int32 *v13; // rbx
  Broker::BrokerEvent *v15; // [rsp+40h] [rbp-38h] BYREF
  volatile signed __int32 *v16; // [rsp+48h] [rbp-30h]
  __int64 v17; // [rsp+50h] [rbp-28h] BYREF
  volatile signed __int32 *v18; // [rsp+58h] [rbp-20h]
  __int64 v19; // [rsp+80h] [rbp+8h] BYREF

  Broker::BrokerBase::GetInstance(&v17, a1);
  v11 = v17;
  v19 = a2;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, v10, *(_QWORD *)(v17 + 8), a2);
  Broker::BrokeredEventTable::Find(v11 + 208, &v15, &v19);
  Broker::BrokerEvent::Signal(v15, a3, a4, a6, a5, a7);
  v12 = v16;
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  v13 = v18;
  if ( v18 )
  {
    if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180005580  mov     [rsp+arg_8], rbx
0x180005585  mov     [rsp+arg_10], rsi
0x18000558a  push    rdi
0x18000558b  push    r14
0x18000558d  push    r15
0x18000558f  sub     rsp, 60h
0x180005593  mov     r14, r9
0x180005596  mov     r15, r8
0x180005599  mov     rdi, rdx
0x18000559c  xor     esi, esi
0x18000559e  mov     rdx, rcx
0x1800055a1  lea     rcx, [rsp+78h+var_28]
0x1800055a6  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x1800055ab  nop
0x1800055ac  mov     rbx, [rsp+78h+var_28]
0x1800055b1  mov     [rsp+78h+arg_0], rdi
0x1800055b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055c0  test    dword ptr [rcx+1Ch], 800h
0x1800055c7  jz      short loc_1800055E6
0x1800055c9  cmp     byte ptr [rcx+19h], 5
0x1800055cd  jb      short loc_1800055E6
0x1800055cf  mov     r9, [rbx+8]
0x1800055d3  mov     edx, 48h ; 'H'
0x1800055d8  mov     qword ptr [rsp+78h+var_58], rdi
0x1800055dd  mov     rcx, [rcx+10h]
0x1800055e1  call    WPP_SF__guid__guid_
0x1800055e6  lea     rcx, [rbx+0D0h]
0x1800055ed  lea     r8, [rsp+78h+arg_0]
0x1800055f5  lea     rdx, [rsp+78h+var_38]
0x1800055fa  call    ?Find@BrokeredEventTable@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@AEBQEAU_BROKERED_EVENT@@@Z; Broker::BrokeredEventTable::Find(_BROKERED_EVENT * const &)
0x1800055ff  nop
0x180005600  mov     rax, [rsp+78h+arg_30]
0x180005608  mov     [rsp+78h+var_50], rax; struct _GUID *
0x18000560d  mov     eax, [rsp+78h+arg_20]
0x180005614  mov     [rsp+78h+var_58], eax; unsigned int
0x180005618  mov     r9, [rsp+78h+arg_28]; unsigned __int8 *
0x180005620  mov     r8, r14; struct _GUID *
0x180005623  mov     rdx, r15; unsigned __int8 *
0x180005626  mov     rcx, [rsp+78h+var_38]; this
0x18000562b  call    ?Signal@BrokerEvent@Broker@@QEAAXPEBEPEBU_GUID@@0K1@Z; Broker::BrokerEvent::Signal(uchar const *,_GUID const *,uchar const *,ulong,_GUID const *)
0x180005630  nop
0x180005631  mov     rbx, [rsp+78h+var_30]
0x180005636  mov     edi, 0FFFFFFFFh
0x18000563b  test    rbx, rbx
0x18000563e  jz      short loc_180005676
0x180005640  mov     eax, edi
0x180005642  lock xadd [rbx+8], eax
0x180005647  cmp     eax, 1
0x18000564a  jnz     short loc_180005676
0x18000564c  mov     rax, [rbx]
0x18000564f  mov     rcx, rbx
0x180005652  mov     rax, [rax]
0x180005655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000565a  mov     eax, edi
0x18000565c  lock xadd [rbx+0Ch], eax
0x180005661  cmp     eax, 1
0x180005664  jnz     short loc_180005676
0x180005666  mov     rax, [rbx]
0x180005669  mov     rcx, rbx
0x18000566c  mov     rax, [rax+8]
0x180005670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005675  nop
0x180005676  mov     rbx, [rsp+78h+var_20]
0x18000567b  test    rbx, rbx
0x18000567e  jz      short loc_1800056B4
0x180005680  mov     eax, edi
0x180005682  lock xadd [rbx+8], eax
0x180005687  cmp     eax, 1
0x18000568a  jnz     short loc_1800056B4
0x18000568c  mov     rax, [rbx]
0x18000568f  mov     rcx, rbx
0x180005692  mov     rax, [rax]
0x180005695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000569a  lock xadd [rbx+0Ch], edi
0x18000569f  cmp     edi, 1
0x1800056a2  jnz     short loc_1800056B4
0x1800056a4  mov     rax, [rbx]
0x1800056a7  mov     rcx, rbx
0x1800056aa  mov     rax, [rax+8]
0x1800056ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056b3  nop
0x1800056b4  mov     eax, esi
0x1800056b6  lea     r11, [rsp+78h+var_18]
0x1800056bb  mov     rbx, [r11+28h]
0x1800056bf  mov     rsi, [r11+30h]
0x1800056c3  mov     rsp, r11
0x1800056c6  pop     r15
0x1800056c8  pop     r14
0x1800056ca  pop     rdi
0x1800056cb  retn
0x1800056cc  jmp     loc_1800055D3
0x1800056d1  jmp     short loc_1800056E4
0x1800056d3  jmp     short loc_1800056E4
0x1800056d5  jmp     short $+2
0x1800056d7  mov     ebx, dword ptr [rsp+78h+arg_0]
0x1800056de  test    ebx, ebx
0x1800056e0  jz      short loc_180005719
0x1800056e2  jmp     short loc_1800056EB
0x1800056e4  mov     ebx, dword ptr [rsp+78h+arg_0]
0x1800056eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056f2  test    dword ptr [rcx+1Ch], 800h
0x1800056f9  jz      short loc_180005719
0x1800056fb  cmp     byte ptr [rcx+19h], 2
0x1800056ff  jb      short loc_180005719
0x180005701  mov     edx, 1Eh
0x180005706  mov     r9d, ebx
0x180005709  lea     r8, WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids
0x180005710  mov     rcx, [rcx+10h]
0x180005714  call    WPP_SF_d
0x180005719  mov     eax, ebx
0x18000571b  jmp     short loc_1800056B6
```
