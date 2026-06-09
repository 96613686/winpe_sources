# ??$make_shared@VRpcServerRegistration@Broker@@AEAPEAX$$T$$TAEAY0BL@$$CBGAEAY07$$CBGAEAY0BL@$$CBGK$$T@std@@YA?AV?$shared_ptr@VRpcServerRegistration@Broker@@@0@AEAPEAX$$QEA$$T1AEAY0BL@$$CBGAEAY07$$CBG2$$QEAK1@Z

- ea: `0x180012028`
- end: `0x1800120ee`
- name: `??$make_shared@VRpcServerRegistration@Broker@@AEAPEAX$$T$$TAEAY0BL@$$CBGAEAY07$$CBGAEAY0BL@$$CBGK$$T@std@@YA?AV?$shared_ptr@VRpcServerRegistration@Broker@@@0@AEAPEAX$$QEA$$T1AEAY0BL@$$CBGAEAY07$$CBG2$$QEAK1@Z`
- size: `198`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, struct _GUID **, struct _GUID **, __int64, __int64, __int64, unsigned int *, int (**)(void *, void *))`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011ea8`

## callees

- `0x18000e8c4`
- `0x180012df4`

## pseudocode

```c
_QWORD *__fastcall std::make_shared<Broker::RpcServerRegistration,void * &,std::nullptr_t,std::nullptr_t,unsigned short const (&)[27],unsigned short const (&)[8],unsigned short const (&)[27],unsigned long,std::nullptr_t>(
        _QWORD *a1,
        __int64 a2,
        struct _GUID **a3,
        struct _GUID **a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        unsigned int *a8,
        int (**a9)(void *, void *))
{
  _DWORD *v13; // [rsp+88h] [rbp+10h]

  v13 = operator new(0x30u);
  *(_OWORD *)v13 = 0;
  v13[2] = 1;
  v13[3] = 1;
  *(_QWORD *)v13 = &std::_Ref_count_obj2<Broker::RpcServerRegistration>::`vftable';
  Broker::RpcServerRegistration::RpcServerRegistration(
    (Broker::RpcServerRegistration *)(v13 + 4),
    TimeBrokerInternal_v1_0_s_ifspec,
    *a3,
    *a4,
    L"D:(A;;GR;;;WD)(A;;GR;;;AC)",
    L"ncalrpc",
    L"D:(A;;GR;;;WD)(A;;GR;;;AC)",
    *a8,
    *a9);
  *a1 = v13 + 4;
  a1[1] = v13;
  return a1;
}

```

## disassembly

```asm
0x180012028  mov     [rsp+arg_0], rbx
0x18001202d  mov     [rsp+arg_10], rsi
0x180012032  mov     [rsp+arg_8], rdx
0x180012037  push    rdi
0x180012038  push    r14
0x18001203a  push    r15
0x18001203c  sub     rsp, 60h
0x180012040  mov     rsi, r9
0x180012043  mov     r14, r8
0x180012046  mov     r15, rcx
0x180012049  mov     ecx, 30h ; '0'; Size
0x18001204e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012053  mov     rdi, rax
0x180012056  mov     [rsp+78h+arg_8], rax
0x18001205e  xorps   xmm0, xmm0
0x180012061  movups  xmmword ptr [rax], xmm0
0x180012064  mov     eax, 1
0x180012069  mov     [rdi+8], eax
0x18001206c  mov     [rdi+0Ch], eax
0x18001206f  lea     rax, ??_7?$_Ref_count_obj2@VRpcServerRegistration@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::RpcServerRegistration>::`vftable'
0x180012076  mov     [rdi], rax
0x180012079  lea     rbx, [rdi+10h]
0x18001207d  mov     rcx, [rsp+78h+arg_40]
0x180012085  mov     rax, [rcx]
0x180012088  mov     [rsp+78h+var_38], rax; int (*)(void *, void *)
0x18001208d  mov     rax, [rsp+78h+arg_38]
0x180012095  mov     ecx, [rax]
0x180012097  mov     [rsp+78h+var_40], ecx; unsigned int
0x18001209b  lea     rcx, aDAGrWdAGrAc; "D:(A;;GR;;;WD)(A;;GR;;;AC)"
0x1800120a2  mov     [rsp+78h+var_48], rcx; unsigned __int16 *
0x1800120a7  lea     rax, aNcalrpc; "ncalrpc"
0x1800120ae  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x1800120b3  mov     [rsp+78h+var_58], rcx; unsigned __int16 *
0x1800120b8  mov     r9, [rsi]; struct _GUID *
0x1800120bb  mov     r8, [r14]; struct _GUID *
0x1800120be  mov     rdx, cs:_TimeBrokerInternal_v1_0_s_ifspec; void *
0x1800120c5  mov     rcx, rbx; this
0x1800120c8  call    ??0RpcServerRegistration@Broker@@QEAA@PEAXPEBU_GUID@@1PEBG22KP6AJ00@Z_N@Z; Broker::RpcServerRegistration::RpcServerRegistration(void *,_GUID const *,_GUID const *,ushort const *,ushort const *,ushort const *,ulong,long (*)(void *,void *),bool)
0x1800120cd  nop
0x1800120ce  mov     [r15], rbx
0x1800120d1  mov     [r15+8], rdi
0x1800120d5  mov     rax, r15
0x1800120d8  lea     r11, [rsp+78h+var_18]
0x1800120dd  mov     rbx, [r11+20h]
0x1800120e1  mov     rsi, [r11+30h]
0x1800120e5  mov     rsp, r11
0x1800120e8  pop     r15
0x1800120ea  pop     r14
0x1800120ec  pop     rdi
0x1800120ed  retn
```
