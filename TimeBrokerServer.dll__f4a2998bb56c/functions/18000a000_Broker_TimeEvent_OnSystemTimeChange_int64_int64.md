# Broker::TimeEvent::OnSystemTimeChange(__int64,__int64)

- ea: `0x18000a000`
- end: `0x18000a0a6`
- name: `?OnSystemTimeChange@TimeEvent@Broker@@UEAAX_J0@Z`
- size: `166`
- prototype: `void __fastcall(Broker::TimeEvent *__hidden this, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a2f0`

## callees

- `0x18000a000`
- `0x18000a0b0`
- `0x18001c010`

## pseudocode

```c
void __fastcall Broker::TimeEvent::OnSystemTimeChange(Broker::TimeEvent *this, __int64 a2, __int64 a3)
{
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids,
      *((_QWORD *)this + 31),
      (int)a2 / 10000000);
  *((_QWORD *)this + 10) += a2;
  if ( *((_DWORD *)this + 22) == 1 && -*((_QWORD *)this + 10) > *((_QWORD *)this + 8) )
    (*(void (__fastcall **)(Broker::TimeEvent *, __int64))(*(_QWORD *)this + 72LL))(this, a3);
}

```

## disassembly

```asm
0x18000a000  mov     [rsp+arg_0], rbx
0x18000a005  mov     [rsp+arg_8], rsi
0x18000a00a  push    rdi
0x18000a00b  sub     rsp, 30h
0x18000a00f  mov     rsi, r8
0x18000a012  mov     rdi, rdx
0x18000a015  mov     rbx, rcx
0x18000a018  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a01f  test    byte ptr [rcx+1Ch], 40h
0x18000a023  jz      short loc_18000A06B
0x18000a025  cmp     byte ptr [rcx+19h], 5
0x18000a029  jb      short loc_18000A06B
0x18000a02b  mov     r9, [rbx+0F8h]
0x18000a032  mov     rax, 0D6BF94D5E57A42BDh
0x18000a03c  mov     rcx, [rcx+10h]
0x18000a040  imul    rdi
0x18000a043  lea     r8, [rdi+rdx]
0x18000a047  mov     edx, 12h
0x18000a04c  sar     r8, 17h
0x18000a050  mov     rax, r8
0x18000a053  shr     rax, 3Fh
0x18000a057  add     r8, rax
0x18000a05a  mov     [rsp+38h+var_18], r8d
0x18000a05f  lea     r8, WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids
0x18000a066  call    WPP_SF__guid_d
0x18000a06b  add     [rbx+50h], rdi
0x18000a06f  cmp     dword ptr [rbx+58h], 1
0x18000a073  mov     rax, [rbx+50h]
0x18000a077  jnz     short loc_18000A082
0x18000a079  neg     rax
0x18000a07c  cmp     rax, [rbx+40h]
0x18000a080  jg      short loc_18000A092
0x18000a082  mov     rbx, [rsp+38h+arg_0]
0x18000a087  mov     rsi, [rsp+38h+arg_8]
0x18000a08c  add     rsp, 30h
0x18000a090  pop     rdi
0x18000a091  retn
0x18000a092  mov     rax, [rbx]
0x18000a095  mov     rdx, rsi
0x18000a098  mov     rcx, rbx
0x18000a09b  mov     rax, [rax+48h]
0x18000a09f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0a4  jmp     short loc_18000A082
```
