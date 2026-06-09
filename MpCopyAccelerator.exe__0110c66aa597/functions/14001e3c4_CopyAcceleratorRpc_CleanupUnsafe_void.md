# CopyAcceleratorRpc::CleanupUnsafe(void)

- ea: `0x14001e3c4`
- end: `0x14001e4d1`
- name: `?CleanupUnsafe@CopyAcceleratorRpc@@AEAAJXZ`
- size: `269`
- prototype: `__int64 __fastcall(CopyAcceleratorRpc *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001e350`

## callees

- `0x140005c20`
- `0x14001da70`
- `0x14001e3c4`

## import_xrefs

- `RPCRT4!RpcServerInqBindings` at `0x14001e400`
- `RPCRT4!RpcServerInqBindings` at `0x14001e400`
- `RPCRT4!RpcEpUnregister` at `0x14001e420`
- `RPCRT4!RpcEpUnregister` at `0x14001e420`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x14001e476`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x14001e476`
- `RPCRT4!RpcBindingVectorFree` at `0x14001e463`
- `RPCRT4!RpcBindingVectorFree` at `0x14001e463`

## pseudocode

```c
__int64 __fastcall CopyAcceleratorRpc::CleanupUnsafe(CopyAcceleratorRpc *this)
{
  RPC_STATUS v2; // eax
  RPC_STATUS v3; // eax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+20h] [rbp-18h] BYREF

  if ( _InterlockedExchange((volatile __int32 *)this + 8, 1) )
  {
    BindingVector = 0;
    if ( !RpcServerInqBindings(&BindingVector) )
    {
      v2 = RpcEpUnregister(qword_140035250, BindingVector, 0);
      if ( v2 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids,
          v2 | 0x80010000);
      if ( BindingVector )
        RpcBindingVectorFree(&BindingVector);
    }
    v3 = RpcServerUnregisterIfEx(qword_140035250, 0, 1);
    if ( v3 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids,
        v3 | 0x80010000);
  }
  _InterlockedExchange((volatile __int32 *)this + 8, 0);
  return 0;
}

```

## disassembly

```asm
0x14001e3c4  mov     r11, rsp
0x14001e3c7  mov     [r11+10h], rbx
0x14001e3cb  mov     [r11+18h], rbp
0x14001e3cf  push    rdi
0x14001e3d0  sub     rsp, 30h
0x14001e3d4  mov     rax, cs:__security_cookie
0x14001e3db  xor     rax, rsp
0x14001e3de  mov     [rsp+38h+var_10], rax
0x14001e3e3  mov     eax, 1
0x14001e3e8  xor     ebx, ebx
0x14001e3ea  xchg    eax, [rcx+20h]
0x14001e3ed  mov     rdi, rcx
0x14001e3f0  test    eax, eax
0x14001e3f2  jz      loc_14001E4AF
0x14001e3f8  lea     rcx, [r11-18h]; BindingVector
0x14001e3fc  mov     [r11-18h], rbx
0x14001e400  call    cs:__imp_RpcServerInqBindings
0x14001e406  lea     rbp, WPP_GLOBAL_Control
0x14001e40d  test    eax, eax
0x14001e40f  jnz     short loc_14001E469
0x14001e411  mov     rdx, [rsp+38h+BindingVector]; BindingVector
0x14001e416  lea     rcx, qword_140035250; IfSpec
0x14001e41d  xor     r8d, r8d; UuidVector
0x14001e420  call    cs:__imp_RpcEpUnregister
0x14001e426  test    eax, eax
0x14001e428  jz      short loc_14001E457
0x14001e42a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e431  cmp     rcx, rbp
0x14001e434  jz      short loc_14001E457
0x14001e436  test    byte ptr [rcx+1Ch], 2
0x14001e43a  jz      short loc_14001E457
0x14001e43c  mov     rcx, [rcx+10h]
0x14001e440  lea     edx, [rbx+19h]
0x14001e443  or      eax, 80010000h
0x14001e448  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001e44f  mov     r9d, eax
0x14001e452  call    WPP_SF_d
0x14001e457  cmp     [rsp+38h+BindingVector], rbx
0x14001e45c  jz      short loc_14001E469
0x14001e45e  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x14001e463  call    cs:__imp_RpcBindingVectorFree
0x14001e469  xor     edx, edx; MgrTypeUuid
0x14001e46b  lea     rcx, qword_140035250; IfSpec
0x14001e472  lea     r8d, [rdx+1]; RundownContextHandles
0x14001e476  call    cs:__imp_RpcServerUnregisterIfEx
0x14001e47c  test    eax, eax
0x14001e47e  jz      short loc_14001E4AF
0x14001e480  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e487  cmp     rcx, rbp
0x14001e48a  jz      short loc_14001E4AF
0x14001e48c  test    byte ptr [rcx+1Ch], 1
0x14001e490  jz      short loc_14001E4AF
0x14001e492  mov     rcx, [rcx+10h]
0x14001e496  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001e49d  or      eax, 80010000h
0x14001e4a2  mov     edx, 1Ah
0x14001e4a7  mov     r9d, eax
0x14001e4aa  call    WPP_SF_d
0x14001e4af  xchg    ebx, [rdi+20h]
0x14001e4b2  xor     eax, eax
0x14001e4b4  mov     rcx, [rsp+38h+var_10]
0x14001e4b9  xor     rcx, rsp; StackCookie
0x14001e4bc  call    __security_check_cookie
0x14001e4c1  mov     rbx, [rsp+38h+arg_8]
0x14001e4c6  mov     rbp, [rsp+38h+arg_10]
0x14001e4cb  add     rsp, 30h
0x14001e4cf  pop     rdi
0x14001e4d0  retn
```
