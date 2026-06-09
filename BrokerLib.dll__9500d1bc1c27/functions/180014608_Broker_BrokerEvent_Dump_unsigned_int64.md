# Broker::BrokerEvent::Dump(unsigned __int64)

- ea: `0x180014608`
- end: `0x1800146ab`
- name: `?Dump@BrokerEvent@Broker@@QEAAX_K@Z`
- size: `163`
- prototype: `void __fastcall(Broker::BrokerEvent *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014558`

## callees

- `0x180005b50`
- `0x180009e94`
- `0x180014608`
- `0x1800146b4`
- `0x18001471c`

## pseudocode

```c
void __fastcall Broker::BrokerEvent::Dump(Broker::BrokerEvent *this, __int64 a2)
{
  WPP_SF__guid_(a2, 10, &WPP_43141e9839bb3327de9c92b5114338a2_Traceguids, *((_QWORD *)this + 2));
  WPP_SF_DD(a2);
  WPP_SF_S(a2, 12);
  WPP_SF_S(a2, 13);
  WPP_SF_d(a2, 14, &WPP_43141e9839bb3327de9c92b5114338a2_Traceguids, *((unsigned int *)this + 7));
}

```

## disassembly

```asm
0x180014608  mov     [rsp+arg_0], rbx
0x18001460d  push    rdi
0x18001460e  sub     rsp, 30h
0x180014612  mov     rbx, rdx
0x180014615  mov     rdi, rcx
0x180014618  mov     r9, [rcx+10h]
0x18001461c  lea     r8, WPP_43141e9839bb3327de9c92b5114338a2_Traceguids
0x180014623  mov     rcx, rbx
0x180014626  mov     edx, 0Ah
0x18001462b  call    WPP_SF__guid_
0x180014630  mov     r9, [rdi+10h]
0x180014634  mov     rcx, rbx
0x180014637  mov     r9, [r9+10h]
0x18001463b  mov     rax, r9
0x18001463e  shr     rax, 20h
0x180014642  mov     [rsp+38h+var_18], eax
0x180014646  call    WPP_SF_DD
0x18001464b  mov     r9, [rdi+30h]
0x18001464f  add     r9, 38h ; '8'
0x180014653  cmp     qword ptr [r9+18h], 7
0x180014658  jbe     short loc_18001465D
0x18001465a  mov     r9, [r9]
0x18001465d  mov     edx, 0Ch
0x180014662  mov     rcx, rbx
0x180014665  call    WPP_SF_S
0x18001466a  mov     r9, [rdi+30h]
0x18001466e  add     r9, 18h
0x180014672  cmp     qword ptr [r9+18h], 7
0x180014677  jbe     short loc_18001467C
0x180014679  mov     r9, [r9]
0x18001467c  mov     edx, 0Dh
0x180014681  mov     rcx, rbx
0x180014684  call    WPP_SF_S
0x180014689  mov     r9d, [rdi+1Ch]
0x18001468d  lea     r8, WPP_43141e9839bb3327de9c92b5114338a2_Traceguids
0x180014694  mov     edx, 0Eh
0x180014699  mov     rcx, rbx
0x18001469c  mov     rbx, [rsp+38h+arg_0]
0x1800146a1  add     rsp, 30h
0x1800146a5  pop     rdi
0x1800146a6  jmp     WPP_SF_d
```
