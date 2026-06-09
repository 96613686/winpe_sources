# std::thread::_Invoke<std::tuple<void (Spectre::Engine::Engine::*)(void),Spectre::Engine::Engine *>,0,1>(void *)

- ea: `0x18002e0e0`
- end: `0x18002e113`
- name: `??$_Invoke@V?$tuple@P8Engine@1Spectre@@EAAXXZPEAV112@@std@@$0A@$00@thread@std@@CAIPEAX@Z`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800305b8`
- `0x1800e7010`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18002e0fc`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18002e0fc`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke<std::tuple<void (Spectre::Engine::Engine::*)(void),Spectre::Engine::Engine *>,0,1>(
        __int64 a1)
{
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  (*(void (__fastcall **)(_QWORD))(a1 + 8))(*(_QWORD *)a1 + *(int *)(a1 + 16));
  _Cnd_do_broadcast_at_thread_exit();
  std::unique_ptr<std::tuple<void (Spectre::Engine::Engine::*)(void),Spectre::Engine::Engine *>>::~unique_ptr<std::tuple<void (Spectre::Engine::Engine::*)(void),Spectre::Engine::Engine *>>(&v2);
  return 0;
}

```

## disassembly

```asm
0x18002e0e0  sub     rsp, 28h
0x18002e0e4  mov     rax, rcx
0x18002e0e7  mov     [rsp+28h+arg_0], rcx
0x18002e0ec  movsxd  rcx, dword ptr [rcx+10h]
0x18002e0f0  add     rcx, [rax]
0x18002e0f3  mov     rax, [rax+8]
0x18002e0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0fc  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x18002e102  lea     rcx, [rsp+28h+arg_0]
0x18002e107  call    ??1?$unique_ptr@V?$tuple@P8Engine@1Spectre@@EAAXXZPEAV112@@std@@U?$default_delete@V?$tuple@P8Engine@1Spectre@@EAAXXZPEAV112@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<void (Spectre::Engine::Engine::*)(void),Spectre::Engine::Engine *>>::~unique_ptr<std::tuple<void (Spectre::Engine::Engine::*)(void),Spectre::Engine::Engine *>>(void)
0x18002e10c  xor     eax, eax
0x18002e10e  add     rsp, 28h
0x18002e112  retn
```
