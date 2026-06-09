# Broker::RpcServerRegistration::~RpcServerRegistration(void)

- ea: `0x18001969c`
- end: `0x180019766`
- name: `??1RpcServerRegistration@Broker@@QEAA@XZ`
- size: `202`
- prototype: `void __fastcall(Broker::RpcServerRegistration *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800146c0`

## callees

- `0x180003800`
- `0x1800131e4`
- `0x180019648`
- `0x18001969c`

## import_xrefs

- `RPCRT4!RpcBindingVectorFree` at `0x180019708`
- `RPCRT4!RpcBindingVectorFree` at `0x180019708`
- `RPCRT4!RpcEpUnregister` at `0x1800196b4`
- `RPCRT4!RpcEpUnregister` at `0x1800196b4`

## pseudocode

```c
void __fastcall Broker::RpcServerRegistration::~RpcServerRegistration(Broker::RpcServerRegistration *this)
{
  unsigned int v2; // eax
  void *v3; // rcx
  unsigned int v4; // eax
  Broker::RpcIfRegistration *v5; // rbx

  v2 = RpcEpUnregister(*(RPC_IF_HANDLE *)this, *((RPC_BINDING_VECTOR **)this + 2), *((UUID_VECTOR **)this + 3));
  if ( v2 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    operator delete(v3, 1u);
    *((_QWORD *)this + 3) = 0;
  }
  v4 = RpcBindingVectorFree((RPC_BINDING_VECTOR **)this + 2);
  if ( v4 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v4);
  v5 = (Broker::RpcIfRegistration *)*((_QWORD *)this + 1);
  if ( v5 )
  {
    Broker::RpcIfRegistration::~RpcIfRegistration(v5);
    operator delete(v5, 0x18u);
  }
}

```

## disassembly

```asm
0x18001969c  mov     [rsp+arg_0], rbx
0x1800196a1  push    rdi
0x1800196a2  sub     rsp, 20h
0x1800196a6  mov     r8, [rcx+18h]; UuidVector
0x1800196aa  mov     rbx, rcx
0x1800196ad  mov     rdx, [rcx+10h]; BindingVector
0x1800196b1  mov     rcx, [rcx]; IfSpec
0x1800196b4  call    cs:__imp_RpcEpUnregister
0x1800196ba  test    eax, eax
0x1800196bc  jz      short loc_1800196E9
0x1800196be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196c5  test    byte ptr [rcx+1Ch], 8
0x1800196c9  jz      short loc_1800196E9
0x1800196cb  cmp     byte ptr [rcx+19h], 2
0x1800196cf  jb      short loc_1800196E9
0x1800196d1  mov     rcx, [rcx+10h]
0x1800196d5  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x1800196dc  mov     edx, 20h ; ' '
0x1800196e1  mov     r9d, eax
0x1800196e4  call    WPP_SF_d
0x1800196e9  mov     rcx, [rbx+18h]; void *
0x1800196ed  test    rcx, rcx
0x1800196f0  jz      short loc_180019704
0x1800196f2  mov     edx, 1; unsigned __int64
0x1800196f7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800196fc  mov     qword ptr [rbx+18h], 0
0x180019704  lea     rcx, [rbx+10h]; BindingVector
0x180019708  call    cs:__imp_RpcBindingVectorFree
0x18001970e  test    eax, eax
0x180019710  jz      short loc_18001973D
0x180019712  mov     rcx, cs:WPP_GLOBAL_Control
0x180019719  test    byte ptr [rcx+1Ch], 8
0x18001971d  jz      short loc_18001973D
0x18001971f  cmp     byte ptr [rcx+19h], 2
0x180019723  jb      short loc_18001973D
0x180019725  mov     rcx, [rcx+10h]
0x180019729  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180019730  mov     edx, 21h ; '!'
0x180019735  mov     r9d, eax
0x180019738  call    WPP_SF_d
0x18001973d  mov     rbx, [rbx+8]
0x180019741  test    rbx, rbx
0x180019744  jz      short loc_18001975B
0x180019746  mov     rcx, rbx; this
0x180019749  call    ??1RpcIfRegistration@Broker@@QEAA@XZ; Broker::RpcIfRegistration::~RpcIfRegistration(void)
0x18001974e  mov     edx, 18h; unsigned __int64
0x180019753  mov     rcx, rbx; void *
0x180019756  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001975b  mov     rbx, [rsp+28h+arg_0]
0x180019760  add     rsp, 20h
0x180019764  pop     rdi
0x180019765  retn
```
