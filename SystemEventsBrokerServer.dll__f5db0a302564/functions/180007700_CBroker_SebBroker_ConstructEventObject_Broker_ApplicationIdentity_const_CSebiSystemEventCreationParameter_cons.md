# CBroker::SebBroker::ConstructEventObject(Broker::ApplicationIdentity const &,_CSebiSystemEventCreationParameter const &,CBroker::_CustomData const *,_BROKER *,_BROKERED_EVENT *)

- ea: `0x180007700`
- end: `0x18000786f`
- name: `?ConstructEventObject@SebBroker@CBroker@@AEAA?AV?$unique_ptr@VSebEvent@CBroker@@U?$default_delete@VSebEvent@CBroker@@@std@@@std@@AEBUApplicationIdentity@Broker@@AEBU_CSebiSystemEventCreationParameter@@PEBU_CustomData@2@PEAU_BROKER@@PEAU_BROKERED_EVENT@@@Z`
- size: `367`
- prototype: `__int64 *__fastcall(__int64, __int64 *, _QWORD *, __int64, __int64, __int64 (__fastcall **)(_QWORD, __int64), __int64 (__fastcall **)(_QWORD, __int64))`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006e00`
- `0x18000f680`

## callees

- `0x180007700`
- `0x180008230`
- `0x18001743c`
- `0x18001cf74`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800077dd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000783b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800077dd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000783b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800077f6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000785c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800077f6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000785c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800077e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007841`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800077e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007841`

## pseudocode

```c
__int64 *__fastcall CBroker::SebBroker::ConstructEventObject(
        __int64 a1,
        __int64 *a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        __int64 (__fastcall **a6)(_QWORD, __int64),
        __int64 (__fastcall **a7)(_QWORD, __int64))
{
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 (__fastcall ***v14)(_QWORD, __int64); // rdx
  __int64 (__fastcall ***v15)(_QWORD, __int64); // rbx
  __int64 (__fastcall ***v17)(_QWORD, __int64); // rdi
  void *v18; // [rsp+D8h] [rbp+20h]

  *a2 = 0;
  v11 = *(_QWORD *)a4;
  v18 = operator new(0x108u);
  v12 = CBroker::SebEvent::SebEvent(
          (__int64)v18,
          a3,
          v11,
          *(_DWORD *)(a4 + 8),
          *(_DWORD *)(a4 + 12),
          *(_DWORD *)(a4 + 24),
          *(_DWORD *)(a4 + 16),
          *(_DWORD *)(a4 + 20),
          a5,
          *(_DWORD *)(a4 + 28),
          *(_DWORD *)(a4 + 32),
          *(_DWORD *)(a4 + 36),
          *(_DWORD *)(a4 + 40),
          *(_DWORD *)(a4 + 44),
          *(_DWORD *)(a4 + 48),
          *(_DWORD *)(a4 + 52),
          a1);
  v14 = (__int64 (__fastcall ***)(_QWORD, __int64))*a2;
  *a2 = v12;
  if ( v14 )
    std::default_delete<CBroker::SebEvent>::operator()(v13, v14);
  v15 = (__int64 (__fastcall ***)(_QWORD, __int64))*a2;
  RtlAcquireSRWLockExclusive(*a2 + 240);
  GetCurrentThreadId();
  ++*((_DWORD *)v15 + 63);
  RtlReleaseSRWLockExclusive(v15 + 30);
  if ( a6 && a7 )
  {
    v17 = (__int64 (__fastcall ***)(_QWORD, __int64))*a2;
    RtlAcquireSRWLockExclusive(*a2 + 240);
    GetCurrentThreadId();
    v17[17] = a6;
    v17[18] = a7;
    RtlReleaseSRWLockExclusive(v17 + 30);
  }
  return a2;
}

```

## disassembly

```asm
0x180007700  mov     r11, rsp
0x180007703  mov     [r11+8], rbx
0x180007707  mov     [r11+18h], rbp
0x18000770b  mov     [r11+10h], rdx
0x18000770f  push    rsi
0x180007710  push    rdi
0x180007711  push    r14
0x180007713  sub     rsp, 0A0h
0x18000771a  mov     rsi, r9
0x18000771d  mov     rbp, r8
0x180007720  mov     r14, rdx
0x180007723  mov     rdi, rcx
0x180007726  xor     eax, eax
0x180007728  mov     [r11-28h], eax
0x18000772c  mov     [rdx], rax
0x18000772f  mov     dword ptr [r11-28h], 1
0x180007737  mov     rbx, [r9]
0x18000773a  mov     ecx, 108h; Size
0x18000773f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007744  mov     r10, rax
0x180007747  mov     [rsp+0B8h+arg_18], rax
0x18000774f  mov     [rsp+0B8h+var_38], rdi
0x180007757  mov     ecx, [rsi+34h]
0x18000775a  mov     [rsp+0B8h+var_40], ecx
0x18000775e  mov     ecx, [rsi+30h]
0x180007761  mov     [rsp+0B8h+var_48], ecx
0x180007765  mov     ecx, [rsi+2Ch]
0x180007768  mov     [rsp+0B8h+var_50], ecx
0x18000776c  mov     ecx, [rsi+28h]
0x18000776f  mov     [rsp+0B8h+var_58], ecx
0x180007773  mov     ecx, [rsi+24h]
0x180007776  mov     [rsp+0B8h+var_60], ecx
0x18000777a  mov     eax, [rsi+20h]
0x18000777d  mov     [rsp+0B8h+var_68], eax
0x180007781  mov     eax, [rsi+1Ch]
0x180007784  mov     [rsp+0B8h+var_70], eax
0x180007788  mov     rax, [rsp+0B8h+arg_20]
0x180007790  mov     [rsp+0B8h+var_78], rax
0x180007795  mov     eax, [rsi+14h]
0x180007798  mov     [rsp+0B8h+var_80], eax
0x18000779c  mov     eax, [rsi+10h]
0x18000779f  mov     [rsp+0B8h+var_88], eax
0x1800077a3  mov     eax, [rsi+18h]
0x1800077a6  mov     [rsp+0B8h+var_90], eax
0x1800077aa  mov     eax, [rsi+0Ch]
0x1800077ad  mov     [rsp+0B8h+var_98], eax
0x1800077b1  mov     r9d, [rsi+8]
0x1800077b5  mov     r8, rbx
0x1800077b8  mov     rdx, rbp
0x1800077bb  mov     rcx, r10
0x1800077be  call    ??0SebEvent@CBroker@@QEAA@AEBUApplicationIdentity@Broker@@U_WNF_STATE_NAME@@W4_CSebiEventType@@W4_CSebiTriggerType@@HW4_CSebConditionOperator@@KPEBU_CustomData@1@KHHKKKKPEAVSebBroker@1@@Z; CBroker::SebEvent::SebEvent(Broker::ApplicationIdentity const &,_WNF_STATE_NAME,_CSebiEventType,_CSebiTriggerType,int,_CSebConditionOperator,ulong,CBroker::_CustomData const *,ulong,int,int,ulong,ulong,ulong,ulong,CBroker::SebBroker *)
0x1800077c3  nop
0x1800077c4  mov     rdx, [r14]
0x1800077c7  mov     [r14], rax
0x1800077ca  test    rdx, rdx
0x1800077cd  jnz     loc_180007864
0x1800077d3  mov     rbx, [r14]
0x1800077d6  lea     rcx, [rbx+0F0h]
0x1800077dd  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800077e3  call    cs:__imp_GetCurrentThreadId
0x1800077e9  inc     dword ptr [rbx+0FCh]
0x1800077ef  lea     rcx, [rbx+0F0h]
0x1800077f6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800077fc  mov     rbx, [rsp+0B8h+arg_28]
0x180007804  test    rbx, rbx
0x180007807  jnz     short loc_180007824
0x180007809  mov     rax, r14
0x18000780c  lea     r11, [rsp+0B8h+var_18]
0x180007814  mov     rbx, [r11+20h]
0x180007818  mov     rbp, [r11+30h]
0x18000781c  mov     rsp, r11
0x18000781f  pop     r14
0x180007821  pop     rdi
0x180007822  pop     rsi
0x180007823  retn
0x180007824  mov     rbp, [rsp+0B8h+arg_30]
0x18000782c  test    rbp, rbp
0x18000782f  jz      short loc_180007809
0x180007831  mov     rdi, [r14]
0x180007834  lea     rcx, [rdi+0F0h]
0x18000783b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180007841  call    cs:__imp_GetCurrentThreadId
0x180007847  mov     [rdi+88h], rbx
0x18000784e  mov     [rdi+90h], rbp
0x180007855  lea     rcx, [rdi+0F0h]
0x18000785c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180007862  jmp     short loc_180007809
0x180007864  call    ??R?$default_delete@VSebEvent@CBroker@@@std@@QEBAXPEAVSebEvent@CBroker@@@Z; std::default_delete<CBroker::SebEvent>::operator()(CBroker::SebEvent *)
0x180007869  jmp     loc_1800077D3
```
