# std::thread::_Invoke<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData,std::default_delete<SpecializationData>> &&),ThreadManager *,std::unique_ptr<SpecializationData,std::default_delete<SpecializationData>>>,0,1,2>(void *)

- ea: `0x18000a250`
- end: `0x18000a29f`
- name: `??$_Invoke@V?$tuple@P8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@ZPEAV1@V23@@std@@$0A@$00$01@thread@std@@CAIPEAX@Z`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002b20`
- `0x18000e15c`
- `0x18005a010`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18000a27b`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18000a27b`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::unique_ptr<SpecializationData>>,0,1,2>(
        __int64 a1)
{
  __int64 v2; // [rsp+20h] [rbp-18h] BYREF

  v2 = a1;
  (*(void (__fastcall **)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 8));
  _Cnd_do_broadcast_at_thread_exit();
  std::unique_ptr<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::unique_ptr<SpecializationData>>>::~unique_ptr<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::unique_ptr<SpecializationData>>>(&v2);
  return 0;
}

```

## disassembly

```asm
0x18000a250  sub     rsp, 38h
0x18000a254  mov     rax, cs:__security_cookie
0x18000a25b  xor     rax, rsp
0x18000a25e  mov     [rsp+38h+var_10], rax
0x18000a263  mov     rax, rcx
0x18000a266  mov     [rsp+38h+var_18], rcx
0x18000a26b  mov     rdx, rcx
0x18000a26e  mov     rcx, [rcx+8]
0x18000a272  mov     rax, [rdx+10h]
0x18000a276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a27b  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x18000a281  lea     rcx, [rsp+38h+var_18]
0x18000a286  call    ??1?$unique_ptr@V?$tuple@P8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@ZPEAV1@V23@@std@@U?$default_delete@V?$tuple@P8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@ZPEAV1@V23@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::unique_ptr<SpecializationData>>>::~unique_ptr<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::unique_ptr<SpecializationData>>>(void)
0x18000a28b  xor     eax, eax
0x18000a28d  mov     rcx, [rsp+38h+var_10]
0x18000a292  xor     rcx, rsp; StackCookie
0x18000a295  call    __security_check_cookie
0x18000a29a  add     rsp, 38h
0x18000a29e  retn
```
