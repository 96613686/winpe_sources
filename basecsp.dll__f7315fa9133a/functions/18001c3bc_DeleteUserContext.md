# DeleteUserContext

- ea: `0x18001c3bc`
- end: `0x18001c41b`
- name: `DeleteUserContext`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a398`
- `0x18001bcc0`

## callees

- `0x18000de80`
- `0x18001c3bc`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18001c3fa`
- `RPCRT4!RpcStringFreeW` at `0x18001c3fa`

## pseudocode

```c
__int64 __fastcall DeleteUserContext(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  v2 = *(_QWORD *)(a1 + 32);
  if ( v2 && *(_QWORD *)(a1 + 16) != v2 )
  {
    CspFreeH(v2);
    *(_QWORD *)(a1 + 32) = 0;
  }
  v3 = *(_QWORD *)(a1 + 16);
  if ( v3 )
  {
    if ( *(_DWORD *)(a1 + 24) )
      RpcStringFreeW((RPC_WSTR *)(a1 + 16));
    else
      CspFreeH(v3);
    *(_QWORD *)(a1 + 16) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18001c3bc  mov     [rsp+arg_0], rbx
0x18001c3c1  push    rdi
0x18001c3c2  sub     rsp, 20h
0x18001c3c6  mov     rbx, rcx
0x18001c3c9  mov     rcx, [rcx+20h]
0x18001c3cd  test    rcx, rcx
0x18001c3d0  jz      short loc_18001C3E5
0x18001c3d2  cmp     [rbx+10h], rcx
0x18001c3d6  jz      short loc_18001C3E5
0x18001c3d8  call    CspFreeH
0x18001c3dd  mov     qword ptr [rbx+20h], 0
0x18001c3e5  lea     rdi, [rbx+10h]
0x18001c3e9  mov     rcx, [rdi]
0x18001c3ec  test    rcx, rcx
0x18001c3ef  jz      short loc_18001C40E
0x18001c3f1  cmp     dword ptr [rbx+18h], 0
0x18001c3f5  jz      short loc_18001C402
0x18001c3f7  mov     rcx, rdi; String
0x18001c3fa  call    cs:__imp_RpcStringFreeW
0x18001c400  jmp     short loc_18001C407
0x18001c402  call    CspFreeH
0x18001c407  mov     qword ptr [rdi], 0
0x18001c40e  mov     rbx, [rsp+28h+arg_0]
0x18001c413  xor     eax, eax
0x18001c415  add     rsp, 20h
0x18001c419  pop     rdi
0x18001c41a  retn
```
