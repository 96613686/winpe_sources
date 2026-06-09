# Broker::AlarmTimeEvent::OnSystemTimeChange(__int64,__int64)

- ea: `0x18000a2f0`
- end: `0x18000a31e`
- name: `?OnSystemTimeChange@AlarmTimeEvent@Broker@@UEAAX_J0@Z`
- size: `46`
- prototype: `void __fastcall(Broker::AlarmTimeEvent *this, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000a000`
- `0x18000a2f0`
- `0x18001c010`

## pseudocode

```c
void __fastcall Broker::AlarmTimeEvent::OnSystemTimeChange(Broker::AlarmTimeEvent *this, __int64 a2, __int64 a3)
{
  if ( a2 )
  {
    Broker::TimeEvent::OnSystemTimeChange(this, a2, a3);
  }
  else if ( *((_BYTE *)this + 300) )
  {
    (*(void (__fastcall **)(Broker::AlarmTimeEvent *, __int64))(*(_QWORD *)this + 72LL))(this, a3);
  }
}

```

## disassembly

```asm
0x18000a2f0  sub     rsp, 28h
0x18000a2f4  test    rdx, rdx
0x18000a2f7  jnz     short loc_18000A314
0x18000a2f9  cmp     [rcx+12Ch], dl
0x18000a2ff  jz      short loc_18000A319
0x18000a301  mov     rax, [rcx]
0x18000a304  mov     rdx, r8; __int64
0x18000a307  mov     rax, [rax+48h]
0x18000a30b  add     rsp, 28h
0x18000a30f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000a314  call    ?OnSystemTimeChange@TimeEvent@Broker@@UEAAX_J0@Z; Broker::TimeEvent::OnSystemTimeChange(__int64,__int64)
0x18000a319  add     rsp, 28h
0x18000a31d  retn
```
