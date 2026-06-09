# std::thread::_Invoke_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____0_

- ea: `0x180004c30`
- end: `0x180004c5c`
- name: `std::thread::_Invoke_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____0_`
- size: `44`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1800057d4`
- `0x1800081ac`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x180004c45`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x180004c45`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____0_(__int64 a1)
{
  __int64 *v1; // rdx
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(__int64 **)(a1 + 8);
  v3 = a1;
  TimeUpdate::NlmThread(*(HANDLE **)a1, v1);
  _Cnd_do_broadcast_at_thread_exit();
  std::unique_ptr_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____std::default_delete_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d_______::_unique_ptr_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____std::default_delete_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d_______(&v3);
  return 0;
}

```

## disassembly

```asm
0x180004c30  sub     rsp, 28h
0x180004c34  mov     rdx, [rcx+8]
0x180004c38  mov     [rsp+28h+arg_0], rcx
0x180004c3d  mov     rcx, [rcx]; this
0x180004c40  call    ?NlmThread@TimeUpdate@@AEAAXAEAV?$promise@J@std@@@Z; TimeUpdate::NlmThread(std::promise<long> &)
0x180004c45  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x180004c4b  lea     rcx, [rsp+28h+arg_0]
0x180004c50  call    std__unique_ptr_std__tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____std__default_delete_std__tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d__________unique_ptr_std__tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____std__default_delete_std__tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d_______
0x180004c55  xor     eax, eax
0x180004c57  add     rsp, 28h
0x180004c5b  retn
```
