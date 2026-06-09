# std::thread::_Invoke<std::tuple<void (Spectre::Engine::Display::*)(void),Spectre::Engine::Display *>,0,1>(void *)

- ea: `0x180052a20`
- end: `0x180052a4f`
- name: `??$_Invoke@V?$tuple@P8Display@Engine@Spectre@@EAAXXZPEAV123@@std@@$0A@$00@thread@std@@CAIPEAX@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180052e08`
- `0x1800e7010`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x180052a38`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x180052a38`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke<std::tuple<void (Spectre::Engine::Display::*)(void),Spectre::Engine::Display *>,0,1>(
        __int64 a1)
{
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  (*(void (__fastcall **)(_QWORD))(a1 + 8))(*(_QWORD *)a1);
  _Cnd_do_broadcast_at_thread_exit();
  std::unique_ptr<std::tuple<void (Spectre::Engine::Display::*)(void),Spectre::Engine::Display *>>::~unique_ptr<std::tuple<void (Spectre::Engine::Display::*)(void),Spectre::Engine::Display *>>(&v2);
  return 0;
}

```

## disassembly

```asm
0x180052a20  sub     rsp, 28h
0x180052a24  mov     rax, rcx
0x180052a27  mov     [rsp+28h+arg_0], rcx
0x180052a2c  mov     rcx, [rcx]
0x180052a2f  mov     rax, [rax+8]
0x180052a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a38  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x180052a3e  lea     rcx, [rsp+28h+arg_0]
0x180052a43  call    ??1?$unique_ptr@V?$tuple@P8Display@Engine@Spectre@@EAAXXZPEAV123@@std@@U?$default_delete@V?$tuple@P8Display@Engine@Spectre@@EAAXXZPEAV123@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<void (Spectre::Engine::Display::*)(void),Spectre::Engine::Display *>>::~unique_ptr<std::tuple<void (Spectre::Engine::Display::*)(void),Spectre::Engine::Display *>>(void)
0x180052a48  xor     eax, eax
0x180052a4a  add     rsp, 28h
0x180052a4e  retn
```
