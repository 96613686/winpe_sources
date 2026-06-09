# Broker::GetBrokerEndpointByBinding(void *,_BROKER * *)

- ea: `0x18000b190`
- end: `0x18000b27f`
- name: `?GetBrokerEndpointByBinding@Broker@@YAKPEAXPEAPEAU_BROKER@@@Z`
- size: `239`
- prototype: `unsigned int __fastcall(RPC_BINDING_HANDLE Binding, void *, struct _BROKER **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180010080`

## callees

- `0x180004ae0`
- `0x1800058e0`
- `0x180009e94`
- `0x18000b190`
- `0x18000b3a4`
- `0x180015af0`

## import_xrefs

- `RPCRT4!RpcBindingInqObject` at `0x18000b1ea`
- `RPCRT4!RpcBindingInqObject` at `0x18000b1ea`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
RPC_STATUS __fastcall Broker::GetBrokerEndpointByBinding(RPC_BINDING_HANDLE Binding, _QWORD *a2, struct _BROKER **a3)
{
  RPC_STATUS result; // eax
  __int64 v6; // [rsp+30h] [rbp-38h] BYREF
  std::_Ref_count_base *v7; // [rsp+38h] [rbp-30h]
  UUID ObjectUuid; // [rsp+40h] [rbp-28h] BYREF

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_aedb1da3e26b324cbac6301bae0d271e_Traceguids);
  ObjectUuid = 0;
  result = RpcBindingInqObject(Binding, &ObjectUuid);
  if ( !result )
  {
    *a2 = *(_QWORD *)(*Broker::BrokerBase::GetInstance(&v6, &ObjectUuid) + 8LL);
    if ( v7 )
      std::_Ref_count_base::_Decref(v7);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b190  mov     [rsp+arg_10], rbx
0x18000b195  push    rdi
0x18000b196  sub     rsp, 60h
0x18000b19a  mov     rax, cs:__security_cookie
0x18000b1a1  xor     rax, rsp
0x18000b1a4  mov     [rsp+68h+var_18], rax
0x18000b1a9  mov     rdi, rdx
0x18000b1ac  mov     rbx, rcx
0x18000b1af  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1b6  test    dword ptr [rcx+1Ch], 800h
0x18000b1bd  jz      short loc_18000B1DA
0x18000b1bf  cmp     byte ptr [rcx+19h], 5
0x18000b1c3  jb      short loc_18000B1DA
0x18000b1c5  mov     edx, 0Ah
0x18000b1ca  lea     r8, WPP_aedb1da3e26b324cbac6301bae0d271e_Traceguids
0x18000b1d1  mov     rcx, [rcx+10h]
0x18000b1d5  call    WPP_SF_
0x18000b1da  xorps   xmm0, xmm0
0x18000b1dd  movups  xmmword ptr [rsp+68h+ObjectUuid.Data1], xmm0
0x18000b1e2  lea     rdx, [rsp+68h+ObjectUuid]; ObjectUuid
0x18000b1e7  mov     rcx, rbx; Binding
0x18000b1ea  call    cs:__imp_RpcBindingInqObject
0x18000b1f0  test    eax, eax
0x18000b1f2  jz      short loc_18000B20F
0x18000b1f4  mov     rcx, [rsp+68h+var_18]
0x18000b1f9  xor     rcx, rsp; StackCookie
0x18000b1fc  call    __security_check_cookie
0x18000b201  mov     rbx, [rsp+68h+arg_10]
0x18000b209  add     rsp, 60h
0x18000b20d  pop     rdi
0x18000b20e  retn
0x18000b20f  lea     rdx, [rsp+68h+ObjectUuid]
0x18000b214  lea     rcx, [rsp+68h+var_38]
0x18000b219  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x18000b21e  mov     rax, [rax]
0x18000b221  mov     rcx, [rax+8]
0x18000b225  mov     [rdi], rcx
0x18000b228  mov     rcx, [rsp+68h+var_30]; this
0x18000b22d  test    rcx, rcx
0x18000b230  jz      short loc_18000B237
0x18000b232  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000b237  xor     ebx, ebx
0x18000b239  mov     eax, ebx
0x18000b23b  jmp     short loc_18000B1F4
0x18000b23d  jmp     short loc_18000B24B
0x18000b23f  jmp     short loc_18000B24B
0x18000b241  mov     ebx, [rsp+68h+var_48]
0x18000b245  test    ebx, ebx
0x18000b247  jz      short loc_18000B239
0x18000b249  jmp     short loc_18000B24F
0x18000b24b  mov     ebx, [rsp+68h+var_48]
0x18000b24f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b256  test    dword ptr [rcx+1Ch], 800h
0x18000b25d  jz      short loc_18000B239
0x18000b25f  cmp     byte ptr [rcx+19h], 2
0x18000b263  jb      short loc_18000B239
0x18000b265  mov     edx, 0Bh
0x18000b26a  mov     r9d, ebx
0x18000b26d  lea     r8, WPP_aedb1da3e26b324cbac6301bae0d271e_Traceguids
0x18000b274  mov     rcx, [rcx+10h]
0x18000b278  call    WPP_SF_d
0x18000b27d  jmp     short loc_18000B239
```
