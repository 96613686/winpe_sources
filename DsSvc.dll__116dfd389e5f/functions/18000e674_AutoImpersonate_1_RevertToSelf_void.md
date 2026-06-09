# AutoImpersonate<1>::RevertToSelf(void)

- ea: `0x18000e674`
- end: `0x18000e6b7`
- name: `?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ`
- size: `67`
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

- `0x18000e674`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18000e687`
- `RPCRT4!RpcRevertToSelf` at `0x18000e687`

## pseudocode

```c
__int64 __fastcall AutoImpersonate<1>::RevertToSelf(_DWORD *a1)
{
  unsigned int v1; // ebx
  RPC_STATUS v3; // eax

  v1 = 0;
  if ( *a1 )
  {
    v3 = RpcRevertToSelf();
    if ( v3 )
    {
      if ( v3 > 0 )
        return (unsigned __int16)v3 | 0x80070000;
      else
        return (unsigned int)v3;
    }
    else
    {
      *a1 = 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000e674  mov     [rsp+arg_0], rbx
0x18000e679  push    rdi
0x18000e67a  sub     rsp, 20h
0x18000e67e  xor     ebx, ebx
0x18000e680  mov     rdi, rcx
0x18000e683  cmp     [rcx], ebx
0x18000e685  jz      short loc_18000E6AA
0x18000e687  call    cs:__imp_RpcRevertToSelf
0x18000e68d  test    eax, eax
0x18000e68f  jz      short loc_18000E6A4
0x18000e691  jg      short loc_18000E697
0x18000e693  mov     ebx, eax
0x18000e695  jmp     short loc_18000E6A0
0x18000e697  movzx   ebx, ax
0x18000e69a  or      ebx, 80070000h
0x18000e6a0  test    ebx, ebx
0x18000e6a2  js      short loc_18000E6AA
0x18000e6a4  mov     dword ptr [rdi], 0
0x18000e6aa  mov     eax, ebx
0x18000e6ac  mov     rbx, [rsp+28h+arg_0]
0x18000e6b1  add     rsp, 20h
0x18000e6b5  pop     rdi
0x18000e6b6  retn
```
