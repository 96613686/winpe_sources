# AutoImpersonate<1>::ImpersonateClient(void)

- ea: `0x18000dee8`
- end: `0x18000df2d`
- name: `?ImpersonateClient@?$AutoImpersonate@$00@@QEAAJXZ`
- size: `69`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000ca4c`
- `0x18000da68`
- `0x18000ddb8`
- `0x1800124b0`
- `0x1800125c4`
- `0x180012748`

## callees

- `0x18000dee8`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000defd`
- `RPCRT4!RpcImpersonateClient` at `0x18000defd`

## pseudocode

```c
__int64 __fastcall AutoImpersonate<1>::ImpersonateClient(_DWORD *a1)
{
  unsigned int v1; // ebx
  RPC_STATUS v3; // eax

  v1 = 0;
  if ( !*a1 )
  {
    v3 = RpcImpersonateClient(0);
    if ( v3 )
    {
      if ( v3 > 0 )
        return (unsigned __int16)v3 | 0x80070000;
      else
        return (unsigned int)v3;
    }
    else
    {
      *a1 = 1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000dee8  mov     [rsp+arg_0], rbx
0x18000deed  push    rdi
0x18000deee  sub     rsp, 20h
0x18000def2  xor     ebx, ebx
0x18000def4  mov     rdi, rcx
0x18000def7  cmp     [rcx], ebx
0x18000def9  jnz     short loc_18000DF20
0x18000defb  xor     ecx, ecx; BindingHandle
0x18000defd  call    cs:__imp_RpcImpersonateClient
0x18000df03  test    eax, eax
0x18000df05  jz      short loc_18000DF1A
0x18000df07  jg      short loc_18000DF0D
0x18000df09  mov     ebx, eax
0x18000df0b  jmp     short loc_18000DF16
0x18000df0d  movzx   ebx, ax
0x18000df10  or      ebx, 80070000h
0x18000df16  test    ebx, ebx
0x18000df18  js      short loc_18000DF20
0x18000df1a  mov     dword ptr [rdi], 1
0x18000df20  mov     eax, ebx
0x18000df22  mov     rbx, [rsp+28h+arg_0]
0x18000df27  add     rsp, 20h
0x18000df2b  pop     rdi
0x18000df2c  retn
```
