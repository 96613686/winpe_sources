# std::thread::_Invoke<std::tuple<void (CMidi2SchedulerMidiTransform::*)(void),CMidi2SchedulerMidiTransform *>,0,1>(void *)

- ea: `0x18000a050`
- end: `0x18000a084`
- name: `??$_Invoke@V?$tuple@P8CMidi2SchedulerMidiTransform@@EAAXXZPEAV1@@std@@$0A@$00@thread@std@@CAIPEAX@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002024`
- `0x18000e010`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18000a069`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18000a069`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke<std::tuple<void (CMidi2SchedulerMidiTransform::*)(void),CMidi2SchedulerMidiTransform *>,0,1>(
        int *Block)
{
  (*((void (__fastcall **)(_QWORD))Block + 1))(*(_QWORD *)Block + Block[4]);
  _Cnd_do_broadcast_at_thread_exit();
  operator delete(Block);
  return 0;
}

```

## disassembly

```asm
0x18000a050  push    rbx
0x18000a052  sub     rsp, 20h
0x18000a056  mov     rbx, rcx
0x18000a059  movsxd  rcx, dword ptr [rcx+10h]
0x18000a05d  add     rcx, [rbx]
0x18000a060  mov     rax, [rbx+8]
0x18000a064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a069  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x18000a06f  mov     edx, 18h
0x18000a074  mov     rcx, rbx; Block
0x18000a077  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a07c  xor     eax, eax
0x18000a07e  add     rsp, 20h
0x18000a082  pop     rbx
0x18000a083  retn
```
