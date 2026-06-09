# std::thread::_Invoke<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData,std::default_delete<SpecializationData>> &&),ThreadManager *,std::nullptr_t>,0,1,2>(void *)

- ea: `0x18000a1e0`
- end: `0x18000a244`
- name: `??$_Invoke@V?$tuple@P8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@ZPEAV1@$$T@std@@$0A@$00$01@thread@std@@CAIPEAX@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002b20`
- `0x18000dccc`
- `0x18000e104`
- `0x18005a010`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18000a220`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18000a220`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::nullptr_t>,0,1,2>(
        __int64 a1)
{
  __int64 v2; // [rsp+20h] [rbp-28h] BYREF
  __int64 v3; // [rsp+28h] [rbp-20h] BYREF

  v3 = a1;
  v2 = 0;
  (*(void (__fastcall **)(_QWORD, __int64 *))(a1 + 16))(*(_QWORD *)(a1 + 8), &v2);
  std::unique_ptr<SpecializationData>::~unique_ptr<SpecializationData>(&v2);
  _Cnd_do_broadcast_at_thread_exit();
  Microsoft::WRL::Details::MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>::~MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>(&v3);
  return 0;
}

```

## disassembly

```asm
0x18000a1e0  sub     rsp, 48h
0x18000a1e4  mov     rax, cs:__security_cookie
0x18000a1eb  xor     rax, rsp
0x18000a1ee  mov     [rsp+48h+var_18], rax
0x18000a1f3  mov     rax, rcx
0x18000a1f6  mov     [rsp+48h+var_20], rcx
0x18000a1fb  mov     [rsp+48h+var_28], 0
0x18000a204  lea     rdx, [rsp+48h+var_28]
0x18000a209  mov     rcx, [rcx+8]
0x18000a20d  mov     rax, [rax+10h]
0x18000a211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a216  lea     rcx, [rsp+48h+var_28]
0x18000a21b  call    ??1?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@QEAA@XZ; std::unique_ptr<SpecializationData>::~unique_ptr<SpecializationData>(void)
0x18000a220  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x18000a226  lea     rcx, [rsp+48h+var_20]
0x18000a22b  call    ??1?$MakeAllocator@V?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>::~MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>(void)
0x18000a230  xor     eax, eax
0x18000a232  mov     rcx, [rsp+48h+var_18]
0x18000a237  xor     rcx, rsp; StackCookie
0x18000a23a  call    __security_check_cookie
0x18000a23f  add     rsp, 48h
0x18000a243  retn
```
