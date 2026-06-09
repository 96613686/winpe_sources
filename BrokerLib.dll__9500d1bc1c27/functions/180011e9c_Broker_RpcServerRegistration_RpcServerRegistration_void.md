# Broker::RpcServerRegistration::~RpcServerRegistration(void)

- ea: `0x180011e9c`
- end: `0x180011f56`
- name: `??1RpcServerRegistration@Broker@@QEAA@XZ`
- size: `186`
- prototype: `void __fastcall(Broker::RpcServerRegistration *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017854`

## callees

- `0x180009e94`
- `0x180011e9c`
- `0x180015b58`
- `0x180017828`

## import_xrefs

- `RPCRT4!RpcEpUnregister` at `0x180011eb4`
- `RPCRT4!RpcEpUnregister` at `0x180011eb4`
- `RPCRT4!RpcBindingVectorFree` at `0x180011f08`
- `RPCRT4!RpcBindingVectorFree` at `0x180011f08`

## pseudocode

```c
void __fastcall Broker::RpcServerRegistration::~RpcServerRegistration(Broker::RpcServerRegistration *this)
{
  unsigned int v2; // eax
  void *v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // edx
  Broker::RpcIfRegistration *v6; // rcx

  v2 = RpcEpUnregister(*(RPC_IF_HANDLE *)this, *((RPC_BINDING_VECTOR **)this + 2), *((UUID_VECTOR **)this + 3));
  if ( v2 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    operator delete(v3);
    *((_QWORD *)this + 3) = 0;
  }
  v4 = RpcBindingVectorFree((RPC_BINDING_VECTOR **)this + 2);
  if ( v4 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v4);
  v6 = (Broker::RpcIfRegistration *)*((_QWORD *)this + 1);
  if ( v6 )
    Broker::RpcIfRegistration::`scalar deleting destructor'(v6, v5);
}

```

## disassembly

```asm
0x180011e9c  mov     [rsp+arg_0], rbx
0x180011ea1  push    rdi
0x180011ea2  sub     rsp, 20h
0x180011ea6  mov     r8, [rcx+18h]; UuidVector
0x180011eaa  mov     rbx, rcx
0x180011ead  mov     rdx, [rcx+10h]; BindingVector
0x180011eb1  mov     rcx, [rcx]; IfSpec
0x180011eb4  call    cs:__imp_RpcEpUnregister
0x180011eba  test    eax, eax
0x180011ebc  jz      short loc_180011EE9
0x180011ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ec5  test    byte ptr [rcx+1Ch], 8
0x180011ec9  jz      short loc_180011EE9
0x180011ecb  cmp     byte ptr [rcx+19h], 2
0x180011ecf  jb      short loc_180011EE9
0x180011ed1  mov     rcx, [rcx+10h]
0x180011ed5  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180011edc  mov     edx, 20h ; ' '
0x180011ee1  mov     r9d, eax
0x180011ee4  call    WPP_SF_d
0x180011ee9  mov     rcx, [rbx+18h]; void *
0x180011eed  test    rcx, rcx
0x180011ef0  jz      short loc_180011F04
0x180011ef2  mov     edx, 1; unsigned __int64
0x180011ef7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011efc  mov     qword ptr [rbx+18h], 0
0x180011f04  lea     rcx, [rbx+10h]; BindingVector
0x180011f08  call    cs:__imp_RpcBindingVectorFree
0x180011f0e  test    eax, eax
0x180011f10  jz      short loc_180011F3D
0x180011f12  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f19  test    byte ptr [rcx+1Ch], 8
0x180011f1d  jz      short loc_180011F3D
0x180011f1f  cmp     byte ptr [rcx+19h], 2
0x180011f23  jb      short loc_180011F3D
0x180011f25  mov     rcx, [rcx+10h]
0x180011f29  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180011f30  mov     edx, 21h ; '!'
0x180011f35  mov     r9d, eax
0x180011f38  call    WPP_SF_d
0x180011f3d  mov     rcx, [rbx+8]; this
0x180011f41  test    rcx, rcx
0x180011f44  jz      short loc_180011F4B
0x180011f46  call    ??_GRpcIfRegistration@Broker@@QEAAPEAXI@Z; Broker::RpcIfRegistration::`scalar deleting destructor'(uint)
0x180011f4b  mov     rbx, [rsp+28h+arg_0]
0x180011f50  add     rsp, 20h
0x180011f54  pop     rdi
0x180011f55  retn
```
