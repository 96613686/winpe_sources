# std::thread::_Invoke_std::tuple__lambda_8adb629ae038cbc525f1291e566af1ba____0_

- ea: `0x18001d910`
- end: `0x18001d93d`
- name: `std::thread::_Invoke_std::tuple__lambda_8adb629ae038cbc525f1291e566af1ba____0_`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800206b8`
- `0x1800515a0`
- `0x180052518`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18001d926`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18001d926`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke_std::tuple__lambda_8adb629ae038cbc525f1291e566af1ba____0_(__int64 a1)
{
  SystemSettings::PenSettings::EnumerateModernAppsSingleton *Instance; // rax
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = a1;
  Instance = SystemSettings::PenSettings::EnumerateModernAppsSingleton::GetInstance();
  SystemSettings::PenSettings::EnumerateModernAppsSingleton::DoGetValueAsyncWork(Instance);
  _Cnd_do_broadcast_at_thread_exit();
  std::unique_ptr_std::tuple__lambda_8adb629ae038cbc525f1291e566af1ba____std::default_delete_std::tuple__lambda_8adb629ae038cbc525f1291e566af1ba_______::_unique_ptr_std::tuple__lambda_8adb629ae038cbc525f1291e566af1ba____std::default_delete_std::tuple__lambda_8adb629ae038cbc525f1291e566af1ba_______(&v3);
  return 0;
}

```

## disassembly

```asm
0x18001d910  sub     rsp, 28h
0x18001d914  mov     [rsp+28h+arg_0], rcx
0x18001d919  call    ?GetInstance@EnumerateModernAppsSingleton@PenSettings@SystemSettings@@SAAEAV123@XZ; SystemSettings::PenSettings::EnumerateModernAppsSingleton::GetInstance(void)
0x18001d91e  mov     rcx, rax; this
0x18001d921  call    ?DoGetValueAsyncWork@EnumerateModernAppsSingleton@PenSettings@SystemSettings@@UEAAXXZ; SystemSettings::PenSettings::EnumerateModernAppsSingleton::DoGetValueAsyncWork(void)
0x18001d926  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x18001d92c  lea     rcx, [rsp+28h+arg_0]
0x18001d931  call    std__unique_ptr_std__tuple__lambda_8adb629ae038cbc525f1291e566af1ba____std__default_delete_std__tuple__lambda_8adb629ae038cbc525f1291e566af1ba__________unique_ptr_std__tuple__lambda_8adb629ae038cbc525f1291e566af1ba____std__default_delete_std__tuple__lambda_8adb629ae038cbc525f1291e566af1ba_______
0x18001d936  xor     eax, eax
0x18001d938  add     rsp, 28h
0x18001d93c  retn
```
