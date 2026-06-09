# ??$_Invoke@V?$tuple@P8DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@EAAXX_EPEAV12345@@std@@$0A@$00@thread@std@@CAIPEAX@Z

- ea: `0x18001aa90`
- end: `0x18001aac0`
- name: `??$_Invoke@V?$tuple@P8DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@EAAXX_EPEAV12345@@std@@$0A@$00@thread@std@@CAIPEAX@Z`
- size: `48`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001b6b0`
- `0x18005f010`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18001aaa9`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18001aaa9`

## pseudocode

```c
__int64 __fastcall ____Invoke_V__tuple_P8DedicatedThreadRequestDispatcher_Details_Foundation_Bluetooth_Microsoft__EAAXX_EPEAV12345__std___0A__00_thread_std__CAIPEAX_Z(
        __int64 a1)
{
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  (*(void (__fastcall **)(_QWORD))(a1 + 8))(*(_QWORD *)a1);
  _Cnd_do_broadcast_at_thread_exit();
  __1__unique_ptr_V__tuple_P8DedicatedThreadRequestDispatcher_Details_Foundation_Bluetooth_Microsoft__EAAXX_EPEAV12345__std__U__default_delete_V__tuple_P8DedicatedThreadRequestDispatcher_Details_Foundation_Bluetooth_Microsoft__EAAXX_EPEAV12345__std___2__std__QEAA_XZ(&v2);
  return 0;
}

```

## disassembly

```asm
0x18001aa90  sub     rsp, 28h
0x18001aa94  mov     rax, rcx
0x18001aa97  mov     [rsp+28h+arg_0], rcx
0x18001aa9c  mov     rcx, [rcx]
0x18001aa9f  mov     rax, [rax+8]
0x18001aaa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaa8  nop
0x18001aaa9  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x18001aaaf  lea     rcx, [rsp+28h+arg_0]
0x18001aab4  call    ??1?$unique_ptr@V?$tuple@P8DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@EAAXX_EPEAV12345@@std@@U?$default_delete@V?$tuple@P8DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@EAAXX_EPEAV12345@@std@@@2@@std@@QEAA@XZ
0x18001aab9  xor     eax, eax
0x18001aabb  add     rsp, 28h
0x18001aabf  retn
```
