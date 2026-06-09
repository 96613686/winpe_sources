# AiRpcConnect

- ea: `0x14002b2a0`
- end: `0x14002b329`
- name: `AiRpcConnect`
- size: `137`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140025e3c`

## callees

- `0x14002b2a0`

## import_xrefs

- `msrpc!RpcBindingBind` at `0x14002b2ea`
- `msrpc!RpcBindingBind` at `0x14002b2ea`
- `msrpc!RpcBindingFree` at `0x14002b308`
- `msrpc!RpcBindingFree` at `0x14002b308`
- `msrpc!RpcBindingCreateW` at `0x14002b2cc`
- `msrpc!RpcBindingCreateW` at `0x14002b2cc`

## pseudocode

```c
__int64 __fastcall AiRpcConnect(RPC_BINDING_HANDLE *Binding)
{
  unsigned int v2; // ebx

  *Binding = 0;
  if ( RpcBindingCreateW(
         (RPC_BINDING_HANDLE_TEMPLATE_V1_W *)&Template,
         (RPC_BINDING_HANDLE_SECURITY_V1_W *)&Security,
         (RPC_BINDING_HANDLE_OPTIONS_V1 *)&Options,
         Binding)
    || (v2 = 0, RpcBindingBind(0, *Binding, qword_140009C00)) )
  {
    v2 = -1073741823;
    if ( *Binding )
    {
      RpcBindingFree(Binding);
      *Binding = 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14002b2a0  mov     [rsp+arg_0], rbx
0x14002b2a5  push    rdi
0x14002b2a6  sub     rsp, 20h
0x14002b2aa  mov     rdi, rcx
0x14002b2ad  mov     qword ptr [rcx], 0
0x14002b2b4  mov     r9, rcx; Binding
0x14002b2b7  lea     r8, Options; Options
0x14002b2be  lea     rcx, Template; Template
0x14002b2c5  lea     rdx, Security; Security
0x14002b2cc  call    cs:__imp_RpcBindingCreateW
0x14002b2d3  nop     dword ptr [rax+rax+00h]
0x14002b2d8  test    eax, eax
0x14002b2da  jnz     short loc_14002B2FA
0x14002b2dc  mov     rdx, [rdi]; Binding
0x14002b2df  lea     r8, qword_140009C00; IfSpec
0x14002b2e6  xor     ecx, ecx; pAsync
0x14002b2e8  xor     ebx, ebx
0x14002b2ea  call    cs:__imp_RpcBindingBind
0x14002b2f1  nop     dword ptr [rax+rax+00h]
0x14002b2f6  test    eax, eax
0x14002b2f8  jz      short loc_14002B31B
0x14002b2fa  mov     ebx, 0C0000001h
0x14002b2ff  cmp     qword ptr [rdi], 0
0x14002b303  jz      short loc_14002B31B
0x14002b305  mov     rcx, rdi; Binding
0x14002b308  call    cs:__imp_RpcBindingFree
0x14002b30f  nop     dword ptr [rax+rax+00h]
0x14002b314  mov     qword ptr [rdi], 0
0x14002b31b  mov     eax, ebx
0x14002b31d  mov     rbx, [rsp+28h+arg_0]
0x14002b322  add     rsp, 20h
0x14002b326  pop     rdi
0x14002b327  retn
```
