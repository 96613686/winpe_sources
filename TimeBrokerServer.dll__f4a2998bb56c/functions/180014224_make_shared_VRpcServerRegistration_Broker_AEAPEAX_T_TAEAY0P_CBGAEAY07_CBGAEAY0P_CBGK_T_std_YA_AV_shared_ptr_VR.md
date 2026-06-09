# ??$make_shared@VRpcServerRegistration@Broker@@AEAPEAX$$T$$TAEAY0P@$$CBGAEAY07$$CBGAEAY0P@$$CBGK$$T@std@@YA?AV?$shared_ptr@VRpcServerRegistration@Broker@@@0@AEAPEAX$$QEA$$T1AEAY0P@$$CBGAEAY07$$CBG2$$QEAK1@Z

- ea: `0x180014224`
- end: `0x1800142ea`
- name: `??$make_shared@VRpcServerRegistration@Broker@@AEAPEAX$$T$$TAEAY0P@$$CBGAEAY07$$CBGAEAY0P@$$CBGK$$T@std@@YA?AV?$shared_ptr@VRpcServerRegistration@Broker@@@0@AEAPEAX$$QEA$$T1AEAY0P@$$CBGAEAY07$$CBG2$$QEAK1@Z`
- size: `198`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, struct _GUID **, struct _GUID **, int, int, int, unsigned int *, int (**)(void *, void *))`
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
_QWORD *__fastcall std::make_shared<Broker::RpcServerRegistration,void * &,std::nullptr_t,std::nullptr_t,unsigned short const (&)[15],unsigned short const (&)[8],unsigned short const (&)[15],unsigned long,std::nullptr_t>(
        _QWORD *a1,
        __int64 a2,
        struct _GUID **a3,
        struct _GUID **a4,
        int a5,
        int a6,
        int a7,
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
    TimeBrokerTestHook_v1_0_s_ifspec,
    *a3,
    *a4,
    L"D:(A;;GR;;;BA)",
    L"ncalrpc",
    L"D:(A;;GR;;;BA)",
    *a8,
    *a9);
  *a1 = v13 + 4;
  a1[1] = v13;
  return a1;
}

```

## disassembly

```asm
0x180014224  mov     [rsp+arg_0], rbx
0x180014229  mov     [rsp+arg_10], rsi
0x18001422e  mov     [rsp+arg_8], rdx
0x180014233  push    rdi
0x180014234  push    r14
0x180014236  push    r15
0x180014238  sub     rsp, 60h
0x18001423c  mov     rsi, r9
0x18001423f  mov     r14, r8
0x180014242  mov     r15, rcx
0x180014245  mov     ecx, 30h ; '0'; Size
0x18001424a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001424f  mov     rdi, rax
0x180014252  mov     [rsp+78h+arg_8], rax
0x18001425a  xorps   xmm0, xmm0
0x18001425d  movups  xmmword ptr [rax], xmm0
0x180014260  mov     eax, 1
0x180014265  mov     [rdi+8], eax
0x180014268  mov     [rdi+0Ch], eax
0x18001426b  lea     rax, ??_7?$_Ref_count_obj2@VRpcServerRegistration@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::RpcServerRegistration>::`vftable'
0x180014272  mov     [rdi], rax
0x180014275  lea     rbx, [rdi+10h]
0x180014279  mov     rcx, [rsp+78h+arg_40]
0x180014281  mov     rax, [rcx]
0x180014284  mov     [rsp+78h+var_38], rax; int (*)(void *, void *)
0x180014289  mov     rax, [rsp+78h+arg_38]
0x180014291  mov     ecx, [rax]
0x180014293  mov     [rsp+78h+var_40], ecx; unsigned int
0x180014297  lea     rcx, aDAGrBa; "D:(A;;GR;;;BA)"
0x18001429e  mov     [rsp+78h+var_48], rcx; unsigned __int16 *
0x1800142a3  lea     rax, aNcalrpc; "ncalrpc"
0x1800142aa  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x1800142af  mov     [rsp+78h+var_58], rcx; unsigned __int16 *
0x1800142b4  mov     r9, [rsi]; struct _GUID *
0x1800142b7  mov     r8, [r14]; struct _GUID *
0x1800142ba  mov     rdx, cs:_TimeBrokerTestHook_v1_0_s_ifspec; void *
0x1800142c1  mov     rcx, rbx; this
0x1800142c4  call    ??0RpcServerRegistration@Broker@@QEAA@PEAXPEBU_GUID@@1PEBG22KP6AJ00@Z_N@Z; Broker::RpcServerRegistration::RpcServerRegistration(void *,_GUID const *,_GUID const *,ushort const *,ushort const *,ushort const *,ulong,long (*)(void *,void *),bool)
0x1800142c9  nop
0x1800142ca  mov     [r15], rbx
0x1800142cd  mov     [r15+8], rdi
0x1800142d1  mov     rax, r15
0x1800142d4  lea     r11, [rsp+78h+var_18]
0x1800142d9  mov     rbx, [r11+20h]
0x1800142dd  mov     rsi, [r11+30h]
0x1800142e1  mov     rsp, r11
0x1800142e4  pop     r15
0x1800142e6  pop     r14
0x1800142e8  pop     rdi
0x1800142e9  retn
```
