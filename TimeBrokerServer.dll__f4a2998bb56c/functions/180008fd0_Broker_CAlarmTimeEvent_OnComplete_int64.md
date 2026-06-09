# Broker::CAlarmTimeEvent::OnComplete(__int64)

- ea: `0x180008fd0`
- end: `0x180009092`
- name: `?OnComplete@CAlarmTimeEvent@Broker@@MEAAX_J@Z`
- size: `194`
- prototype: `void __fastcall(Broker::CAlarmTimeEvent *__hidden this, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180008fd0`
- `0x180009f70`
- `0x18001c010`

## pseudocode

```c
void __fastcall Broker::CAlarmTimeEvent::OnComplete(Broker::CAlarmTimeEvent *this, __int64 a2)
{
  __int64 v4; // rbx
  _QWORD *v5; // rcx

  v4 = *(_QWORD *)(*((_QWORD *)this + 31) + 16LL);
  v5 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids,
      (unsigned int)v4,
      HIDWORD(v4));
    v5 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 22) == 2 )
  {
    (*(void (__fastcall **)(Broker::CAlarmTimeEvent *, __int64))(*(_QWORD *)this + 72LL))(this, a2);
    v5 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 4u )
    WPP_SF_DD(v5[2], 28, &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids, (unsigned int)v4, HIDWORD(v4));
}

```

## disassembly

```asm
0x180008fd0  mov     [rsp+arg_8], rbx
0x180008fd5  mov     [rsp+arg_10], rsi
0x180008fda  push    rdi
0x180008fdb  sub     rsp, 30h
0x180008fdf  mov     rbx, [rcx+0F8h]
0x180008fe6  mov     rsi, rdx
0x180008fe9  mov     rdi, rcx
0x180008fec  mov     rbx, [rbx+10h]
0x180008ff0  mov     [rsp+38h+arg_0], rbx
0x180008ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ffc  test    byte ptr [rcx+1Ch], 1
0x180009000  jnz     short loc_18000905D
0x180009002  cmp     dword ptr [rdi+58h], 2
0x180009006  jnz     short loc_180009021
0x180009008  mov     rax, [rdi]
0x18000900b  mov     rdx, rsi
0x18000900e  mov     rcx, rdi
0x180009011  mov     rax, [rax+48h]
0x180009015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000901a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009021  test    byte ptr [rcx+1Ch], 1
0x180009025  jz      short loc_18000904D
0x180009027  cmp     byte ptr [rcx+19h], 4
0x18000902b  jb      short loc_18000904D
0x18000902d  mov     eax, dword ptr [rsp+38h+arg_0+4]
0x180009031  lea     r8, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x180009038  mov     rcx, [rcx+10h]
0x18000903c  mov     edx, 1Ch
0x180009041  mov     r9d, ebx
0x180009044  mov     [rsp+38h+var_18], eax
0x180009048  call    WPP_SF_DD
0x18000904d  mov     rbx, [rsp+38h+arg_8]
0x180009052  mov     rsi, [rsp+38h+arg_10]
0x180009057  add     rsp, 30h
0x18000905b  pop     rdi
0x18000905c  retn
0x18000905d  cmp     byte ptr [rcx+19h], 4
0x180009061  jb      short loc_180009002
0x180009063  mov     rcx, [rcx+10h]
0x180009067  lea     r8, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x18000906e  mov     rax, rbx
0x180009071  mov     edx, 1Bh
0x180009076  shr     rax, 20h
0x18000907a  mov     r9d, ebx
0x18000907d  mov     [rsp+38h+var_18], eax
0x180009081  call    WPP_SF_DD
0x180009086  mov     rcx, cs:WPP_GLOBAL_Control
0x18000908d  jmp     loc_180009002
```
