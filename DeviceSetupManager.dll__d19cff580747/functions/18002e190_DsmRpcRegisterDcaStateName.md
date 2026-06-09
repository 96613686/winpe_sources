# DsmRpcRegisterDcaStateName

- ea: `0x18002e190`
- end: `0x18002e213`
- name: `DsmRpcRegisterDcaStateName`
- size: `131`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180021790`
- `0x18002e190`
- `0x180031a84`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18002e1dd`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002e1dd`
- `RPCRT4!RpcImpersonateClient` at `0x18002e1d1`
- `RPCRT4!RpcImpersonateClient` at `0x18002e1d1`
- `RPCRT4!RpcRevertToSelf` at `0x18002e200`
- `RPCRT4!RpcRevertToSelf` at `0x18002e200`

## pseudocode

```c
__int64 __fastcall DsmRpcRegisterDcaStateName(RPC_BINDING_HANDLE BindingHandle, unsigned __int16 *a2)
{
  RPC_STATUS v4; // eax
  int v5; // eax
  int v6; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_5382ed2977f13c9d8b4aa53ff18b2f0c_Traceguids);
  v4 = RpcImpersonateClient(BindingHandle);
  if ( !v4 )
    goto LABEL_8;
  v5 = I_RpcMapWin32Status(v4);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_8:
    v6 = RegisterDcaStateName(a2);
    RpcRevertToSelf();
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002e190  mov     [rsp+arg_0], rbx
0x18002e195  push    rdi
0x18002e196  sub     rsp, 20h
0x18002e19a  mov     rdi, rdx
0x18002e19d  mov     rbx, rcx
0x18002e1a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e1a7  lea     rax, WPP_GLOBAL_Control
0x18002e1ae  cmp     rcx, rax
0x18002e1b1  jz      short loc_18002E1CE
0x18002e1b3  test    byte ptr [rcx+1Ch], 1
0x18002e1b7  jz      short loc_18002E1CE
0x18002e1b9  mov     rcx, [rcx+10h]
0x18002e1bd  lea     r8, WPP_5382ed2977f13c9d8b4aa53ff18b2f0c_Traceguids
0x18002e1c4  mov     edx, 20h ; ' '
0x18002e1c9  call    WPP_SF_
0x18002e1ce  mov     rcx, rbx; BindingHandle
0x18002e1d1  call    cs:__imp_RpcImpersonateClient
0x18002e1d7  test    eax, eax
0x18002e1d9  jz      short loc_18002E1F6
0x18002e1db  mov     ecx, eax; Status
0x18002e1dd  call    cs:__imp_I_RpcMapWin32Status
0x18002e1e3  mov     ebx, eax
0x18002e1e5  test    eax, eax
0x18002e1e7  jle     short loc_18002E1F2
0x18002e1e9  movzx   ebx, ax
0x18002e1ec  or      ebx, 80070000h
0x18002e1f2  test    ebx, ebx
0x18002e1f4  js      short loc_18002E206
0x18002e1f6  mov     rcx, rdi; unsigned __int16 *
0x18002e1f9  call    ?RegisterDcaStateName@@YAJPEBG@Z; RegisterDcaStateName(ushort const *)
0x18002e1fe  mov     ebx, eax
0x18002e200  call    cs:__imp_RpcRevertToSelf
0x18002e206  mov     eax, ebx
0x18002e208  mov     rbx, [rsp+28h+arg_0]
0x18002e20d  add     rsp, 20h
0x18002e211  pop     rdi
0x18002e212  retn
```
