# Broker::RpcServerRegistration::~RpcServerRegistration(void)

- ea: `0x1800212e0`
- end: `0x1800213aa`
- name: `??1RpcServerRegistration@Broker@@QEAA@XZ`
- size: `202`
- prototype: `void __fastcall(Broker::RpcServerRegistration *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001e110`

## callees

- `0x1800030e0`
- `0x18001d364`
- `0x18002128c`
- `0x1800212e0`

## import_xrefs

- `RPCRT4!RpcBindingVectorFree` at `0x18002134c`
- `RPCRT4!RpcBindingVectorFree` at `0x18002134c`
- `RPCRT4!RpcEpUnregister` at `0x1800212f8`
- `RPCRT4!RpcEpUnregister` at `0x1800212f8`

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
0x1800212e0  mov     [rsp+arg_0], rbx
0x1800212e5  push    rdi
0x1800212e6  sub     rsp, 20h
0x1800212ea  mov     r8, [rcx+18h]; UuidVector
0x1800212ee  mov     rbx, rcx
0x1800212f1  mov     rdx, [rcx+10h]; BindingVector
0x1800212f5  mov     rcx, [rcx]; IfSpec
0x1800212f8  call    cs:__imp_RpcEpUnregister
0x1800212fe  test    eax, eax
0x180021300  jz      short loc_18002132D
0x180021302  mov     rcx, cs:WPP_GLOBAL_Control
0x180021309  test    byte ptr [rcx+1Ch], 8
0x18002130d  jz      short loc_18002132D
0x18002130f  cmp     byte ptr [rcx+19h], 2
0x180021313  jb      short loc_18002132D
0x180021315  mov     rcx, [rcx+10h]
0x180021319  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180021320  mov     edx, 20h ; ' '
0x180021325  mov     r9d, eax
0x180021328  call    WPP_SF_d
0x18002132d  mov     rcx, [rbx+18h]; void *
0x180021331  test    rcx, rcx
0x180021334  jz      short loc_180021348
0x180021336  mov     edx, 1; unsigned __int64
0x18002133b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021340  mov     qword ptr [rbx+18h], 0
0x180021348  lea     rcx, [rbx+10h]; BindingVector
0x18002134c  call    cs:__imp_RpcBindingVectorFree
0x180021352  test    eax, eax
0x180021354  jz      short loc_180021381
0x180021356  mov     rcx, cs:WPP_GLOBAL_Control
0x18002135d  test    byte ptr [rcx+1Ch], 8
0x180021361  jz      short loc_180021381
0x180021363  cmp     byte ptr [rcx+19h], 2
0x180021367  jb      short loc_180021381
0x180021369  mov     rcx, [rcx+10h]
0x18002136d  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180021374  mov     edx, 21h ; '!'
0x180021379  mov     r9d, eax
0x18002137c  call    WPP_SF_d
0x180021381  mov     rbx, [rbx+8]
0x180021385  test    rbx, rbx
0x180021388  jz      short loc_18002139F
0x18002138a  mov     rcx, rbx; this
0x18002138d  call    ??1RpcIfRegistration@Broker@@QEAA@XZ; Broker::RpcIfRegistration::~RpcIfRegistration(void)
0x180021392  mov     edx, 18h; unsigned __int64
0x180021397  mov     rcx, rbx; void *
0x18002139a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002139f  mov     rbx, [rsp+28h+arg_0]
0x1800213a4  add     rsp, 20h
0x1800213a8  pop     rdi
0x1800213a9  retn
```
