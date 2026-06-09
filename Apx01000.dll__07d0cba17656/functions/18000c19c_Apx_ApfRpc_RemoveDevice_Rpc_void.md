# Apx::ApfRpc::RemoveDevice_Rpc(void * *)

- ea: `0x18000c19c`
- end: `0x18000c266`
- name: `?RemoveDevice_Rpc@ApfRpc@Apx@@SAXPEAPEAX@Z`
- size: `202`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ff54`

## callees

- `0x18000a12c`
- `0x18000c19c`

## import_xrefs

- `RPCRT4!RpcSsDestroyClientContext` at `0x18000c221`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18000c221`
- `RPCRT4!NdrClientCall3` at `0x18000c208`
- `RPCRT4!NdrClientCall3` at `0x18000c208`

## pseudocode

```c
void __fastcall Apx::ApfRpc::RemoveDevice_Rpc(void **a1)
{
  _QWORD *v2; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_035003ffd5543b5c3de6eea8533c511b_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, a1);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_(v2[2], 18, &WPP_035003ffd5543b5c3de6eea8533c511b_Traceguids);
}

```

## disassembly

```asm
0x18000c19c  mov     [rsp+arg_10], rbx
0x18000c1a1  mov     [rsp+ContextHandle], rcx
0x18000c1a6  push    rdi
0x18000c1a7  sub     rsp, 20h
0x18000c1ab  mov     rdi, rcx
0x18000c1ae  lea     rbx, WPP_GLOBAL_Control
0x18000c1b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1bc  cmp     rcx, rbx
0x18000c1bf  jz      short loc_18000C1E9
0x18000c1c1  test    byte ptr [rcx+1Ch], 1
0x18000c1c5  jz      short loc_18000C1E9
0x18000c1c7  cmp     byte ptr [rcx+19h], 5
0x18000c1cb  jb      short loc_18000C1E9
0x18000c1cd  mov     edx, 11h
0x18000c1d2  lea     r8, WPP_035003ffd5543b5c3de6eea8533c511b_Traceguids
0x18000c1d9  mov     rcx, [rcx+10h]
0x18000c1dd  call    WPP_SF_
0x18000c1e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1e9  test    rdi, rdi
0x18000c1ec  jz      short loc_18000C235
0x18000c1ee  mov     [rsp+28h+arg_8], 0
0x18000c1f7  mov     r9, rdi
0x18000c1fa  xor     r8d, r8d; pReturnValue
0x18000c1fd  lea     edx, [r8+1]; nProcNum
0x18000c201  lea     rcx, pProxyInfo; pProxyInfo
0x18000c208  call    cs:__imp_NdrClientCall3
0x18000c20e  mov     [rsp+28h+arg_8], rax
0x18000c213  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c21a  jmp     short loc_18000C235
0x18000c21c  mov     rcx, [rsp+28h+ContextHandle]; ContextHandle
0x18000c221  call    cs:__imp_RpcSsDestroyClientContext
0x18000c227  lea     rbx, WPP_GLOBAL_Control
0x18000c22e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c235  cmp     rcx, rbx
0x18000c238  jz      short loc_18000C25B
0x18000c23a  test    byte ptr [rcx+1Ch], 1
0x18000c23e  jz      short loc_18000C25B
0x18000c240  cmp     byte ptr [rcx+19h], 5
0x18000c244  jb      short loc_18000C25B
0x18000c246  mov     edx, 12h
0x18000c24b  lea     r8, WPP_035003ffd5543b5c3de6eea8533c511b_Traceguids
0x18000c252  mov     rcx, [rcx+10h]
0x18000c256  call    WPP_SF_
0x18000c25b  mov     rbx, [rsp+28h+arg_10]
0x18000c260  add     rsp, 20h
0x18000c264  pop     rdi
0x18000c265  retn
```
