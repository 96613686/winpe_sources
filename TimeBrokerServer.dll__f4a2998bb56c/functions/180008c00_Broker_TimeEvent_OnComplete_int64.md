# Broker::TimeEvent::OnComplete(__int64)

- ea: `0x180008c00`
- end: `0x180008c5d`
- name: `?OnComplete@TimeEvent@Broker@@UEAAX_J@Z`
- size: `93`
- prototype: `void __fastcall(Broker::TimeEvent *this, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180008c00`
- `0x180009710`
- `0x18001c010`

## pseudocode

```c
void __fastcall Broker::TimeEvent::OnComplete(Broker::TimeEvent *this, __int64 a2, __int64 a3)
{
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, a3, *((_QWORD *)this + 31));
  if ( *((_DWORD *)this + 22) == 2 )
    (*(void (__fastcall **)(Broker::TimeEvent *, __int64))(*(_QWORD *)this + 72LL))(this, a2);
}

```

## disassembly

```asm
0x180008c00  mov     [rsp+arg_0], rbx
0x180008c05  push    rdi
0x180008c06  sub     rsp, 20h
0x180008c0a  mov     rdi, rdx
0x180008c0d  mov     rbx, rcx
0x180008c10  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c17  test    byte ptr [rcx+1Ch], 40h
0x180008c1b  jnz     short loc_180008C40
0x180008c1d  cmp     dword ptr [rbx+58h], 2
0x180008c21  jnz     short loc_180008C35
0x180008c23  mov     rax, [rbx]
0x180008c26  mov     rdx, rdi
0x180008c29  mov     rcx, rbx
0x180008c2c  mov     rax, [rax+48h]
0x180008c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c35  mov     rbx, [rsp+28h+arg_0]
0x180008c3a  add     rsp, 20h
0x180008c3e  pop     rdi
0x180008c3f  retn
0x180008c40  cmp     byte ptr [rcx+19h], 5
0x180008c44  jb      short loc_180008C1D
0x180008c46  mov     r9, [rbx+0F8h]
0x180008c4d  mov     edx, 11h
0x180008c52  mov     rcx, [rcx+10h]
0x180008c56  call    WPP_SF__guid_
0x180008c5b  jmp     short loc_180008C1D
```
