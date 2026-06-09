# DsmRpcrClientSecurityCallBack(void *,void *)

- ea: `0x18002d610`
- end: `0x18002d6e3`
- name: `?DsmRpcrClientSecurityCallBack@@YAJPEAX0@Z`
- size: `211`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180022070`
- `0x18002d2c8`
- `0x18002d610`
- `0x18002d6ec`

## import_xrefs

- `RPCRT4!RpcBindingInqAuthClientW` at `0x18002d64c`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x18002d64c`
- `RPCRT4!RpcImpersonateClient` at `0x18002d675`
- `RPCRT4!RpcImpersonateClient` at `0x18002d675`
- `RPCRT4!RpcRevertToSelf` at `0x18002d69f`
- `RPCRT4!RpcRevertToSelf` at `0x18002d69f`

## pseudocode

```c
__int64 __fastcall DsmRpcrClientSecurityCallBack(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int v3; // ebx
  RPC_AUTHZ_HANDLE v5; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v6; // [rsp+60h] [rbp+18h] BYREF
  WINBOOL IsMember; // [rsp+68h] [rbp+20h] BYREF

  v5 = 0;
  v6 = 0;
  v3 = RpcBindingInqAuthClientW(Context, &v5, 0, &v6, 0, 0);
  if ( !v3 )
  {
    if ( v6 >= 6 )
    {
      v3 = DsmClientCheckProtSeq(Context);
      if ( !v3 )
      {
        v3 = RpcImpersonateClient(Context);
        if ( !v3 )
        {
          IsMember = 0;
          v3 = 5;
          if ( IsUserAdmin(&IsMember) >= 0 && IsMember )
            v3 = 0;
          RpcRevertToSelf();
        }
      }
    }
    else
    {
      v3 = 5;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_5382ed2977f13c9d8b4aa53ff18b2f0c_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18002d610  mov     rax, rsp
0x18002d613  mov     [rax+8], rbx
0x18002d617  push    rdi
0x18002d618  sub     rsp, 40h
0x18002d61c  mov     rdi, rdx
0x18002d61f  mov     qword ptr [rax-20h], 0
0x18002d627  mov     rcx, rdi; ClientBinding
0x18002d62a  mov     qword ptr [rax-18h], 0
0x18002d632  lea     r9, [rax+18h]; AuthnLevel
0x18002d636  mov     dword ptr [rax+18h], 0
0x18002d63d  xor     r8d, r8d; ServerPrincName
0x18002d640  mov     qword ptr [rax-28h], 0
0x18002d648  lea     rdx, [rax-18h]; Privs
0x18002d64c  call    cs:__imp_RpcBindingInqAuthClientW
0x18002d652  mov     ebx, eax
0x18002d654  test    eax, eax
0x18002d656  jnz     short loc_18002D6A5
0x18002d658  cmp     [rsp+48h+arg_10], 6
0x18002d65d  jnb     short loc_18002D664
0x18002d65f  lea     ebx, [rax+5]
0x18002d662  jmp     short loc_18002D6A5
0x18002d664  mov     rcx, rdi; void *
0x18002d667  call    ?DsmClientCheckProtSeq@@YAJPEAX@Z; DsmClientCheckProtSeq(void *)
0x18002d66c  mov     ebx, eax
0x18002d66e  test    eax, eax
0x18002d670  jnz     short loc_18002D6A5
0x18002d672  mov     rcx, rdi; BindingHandle
0x18002d675  call    cs:__imp_RpcImpersonateClient
0x18002d67b  mov     ebx, eax
0x18002d67d  test    eax, eax
0x18002d67f  jnz     short loc_18002D6A5
0x18002d681  lea     rcx, [rsp+48h+IsMember]; IsMember
0x18002d686  mov     [rsp+48h+IsMember], eax
0x18002d68a  lea     ebx, [rax+5]
0x18002d68d  call    ?IsUserAdmin@@YAJPEAH@Z; IsUserAdmin(int *)
0x18002d692  test    eax, eax
0x18002d694  js      short loc_18002D69F
0x18002d696  xor     eax, eax
0x18002d698  cmp     [rsp+48h+IsMember], eax
0x18002d69c  cmovnz  ebx, eax
0x18002d69f  call    cs:__imp_RpcRevertToSelf
0x18002d6a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d6ac  lea     rax, WPP_GLOBAL_Control
0x18002d6b3  cmp     rcx, rax
0x18002d6b6  jz      short loc_18002D6D6
0x18002d6b8  test    byte ptr [rcx+1Ch], 1
0x18002d6bc  jz      short loc_18002D6D6
0x18002d6be  mov     rcx, [rcx+10h]
0x18002d6c2  lea     r8, WPP_5382ed2977f13c9d8b4aa53ff18b2f0c_Traceguids
0x18002d6c9  mov     edx, 0Ch
0x18002d6ce  mov     r9d, ebx
0x18002d6d1  call    WPP_SF_d
0x18002d6d6  mov     eax, ebx
0x18002d6d8  mov     rbx, [rsp+48h+arg_0]
0x18002d6dd  add     rsp, 40h
0x18002d6e1  pop     rdi
0x18002d6e2  retn
```
