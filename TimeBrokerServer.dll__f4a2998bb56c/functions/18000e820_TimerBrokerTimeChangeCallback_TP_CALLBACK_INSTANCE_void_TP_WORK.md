# TimerBrokerTimeChangeCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18000e820`
- end: `0x18000e88a`
- name: `?TimerBrokerTimeChangeCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `106`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, __int64 *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005760`
- `0x180005b30`
- `0x18000e820`
- `0x1800131e4`

## pseudocode

```c
void __fastcall TimerBrokerTimeChangeCallback(struct _TP_CALLBACK_INSTANCE *a1, __int64 *a2, struct _TP_WORK *a3)
{
  std::_Ref_count_base *v4; // rbx

  v4 = *(&Broker::TimeBroker::Instance + 1);
  if ( *(&Broker::TimeBroker::Instance + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1) + 2);
    v4 = *(&Broker::TimeBroker::Instance + 1);
  }
  if ( Broker::TimeBroker::Instance )
  {
    Broker::TimeBroker::OnSystemTimeChange(Broker::TimeBroker::Instance, *a2);
    operator delete(a2);
  }
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
}

```

## disassembly

```asm
0x18000e820  mov     [rsp+arg_0], rbx
0x18000e825  push    rdi
0x18000e826  sub     rsp, 30h
0x18000e82a  mov     rdi, rdx
0x18000e82d  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000e834  test    rbx, rbx
0x18000e837  jz      short loc_18000E844
0x18000e839  lock inc dword ptr [rbx+8]
0x18000e83d  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000e844  mov     rcx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; this
0x18000e84b  mov     [rsp+38h+var_18], rcx
0x18000e850  mov     [rsp+38h+var_10], rbx
0x18000e855  test    rcx, rcx
0x18000e858  jnz     short loc_18000E872
0x18000e85a  test    rbx, rbx
0x18000e85d  jz      short loc_18000E867
0x18000e85f  mov     rcx, rbx; this
0x18000e862  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000e867  mov     rbx, [rsp+38h+arg_0]
0x18000e86c  add     rsp, 30h
0x18000e870  pop     rdi
0x18000e871  retn
0x18000e872  mov     rdx, [rdx]; __int64
0x18000e875  call    ?OnSystemTimeChange@TimeBroker@Broker@@QEAAX_J@Z; Broker::TimeBroker::OnSystemTimeChange(__int64)
0x18000e87a  mov     edx, 8; unsigned __int64
0x18000e87f  mov     rcx, rdi; void *
0x18000e882  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e887  jmp     short loc_18000E85A
```
