# std::thread::_Invoke<std::tuple<std::_Front_binder<void (CMidi2KSAggregateMidiEndpointManager2::*)(std::stop_token),CMidi2KSAggregateMidiEndpointManager2 *>,std::stop_token>,0,1>(void *)

- ea: `0x18002e400`
- end: `0x18002e465`
- name: `??$_Invoke@V?$tuple@V?$_Front_binder@P8CMidi2KSAggregateMidiEndpointManager2@@EAAXVstop_token@std@@@ZPEAV1@@std@@Vstop_token@2@@std@@$0A@$00@thread@std@@CAIPEAX@Z`
- size: `101`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180005044`
- `0x18002e400`
- `0x18005e010`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18002e42e`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18002e42e`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke<std::tuple<std::_Front_binder<void (CMidi2KSAggregateMidiEndpointManager2::*)(std::stop_token),CMidi2KSAggregateMidiEndpointManager2 *>,std::stop_token>,0,1>(
        int *Block)
{
  __int64 v2; // rcx
  void (__fastcall *v3)(__int64, __int64 *); // rax
  __int64 v4; // rdx
  void *v5; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_QWORD *)Block + 3) + Block[4];
  v3 = (void (__fastcall *)(__int64, __int64 *))*((_QWORD *)Block + 1);
  v4 = *(_QWORD *)Block;
  *(_QWORD *)Block = 0;
  v7 = v4;
  v3(v2, &v7);
  _Cnd_do_broadcast_at_thread_exit();
  v5 = *(void **)Block;
  if ( *(_QWORD *)Block && _InterlockedExchangeAdd((volatile signed __int32 *)v5, 0xFFFFFFFF) == 1 )
    operator delete(v5);
  operator delete(Block);
  return 0;
}

```

## disassembly

```asm
0x18002e400  push    rbx
0x18002e402  sub     rsp, 20h
0x18002e406  mov     rbx, rcx
0x18002e409  movsxd  rcx, dword ptr [rcx+10h]
0x18002e40d  add     rcx, [rbx+18h]
0x18002e411  mov     rax, [rbx+8]
0x18002e415  mov     rdx, [rbx]
0x18002e418  mov     qword ptr [rbx], 0
0x18002e41f  mov     [rsp+28h+arg_0], rdx
0x18002e424  lea     rdx, [rsp+28h+arg_0]
0x18002e429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e42e  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x18002e434  mov     rcx, [rbx]; Block
0x18002e437  test    rcx, rcx
0x18002e43a  jz      short loc_18002E450
0x18002e43c  or      eax, 0FFFFFFFFh
0x18002e43f  lock xadd [rcx], eax
0x18002e443  cmp     eax, 1
0x18002e446  jnz     short loc_18002E450
0x18002e448  lea     edx, [rax+1Fh]
0x18002e44b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e450  mov     edx, 20h ; ' '
0x18002e455  mov     rcx, rbx; Block
0x18002e458  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e45d  xor     eax, eax
0x18002e45f  add     rsp, 20h
0x18002e463  pop     rbx
0x18002e464  retn
```
