# IContextMenu_InvokeCommand_Proxy

- ea: `0x18000a320`
- end: `0x18000a40f`
- name: `IContextMenu_InvokeCommand_Proxy`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800045ba`
- `0x18000a320`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000a3f4`
- `RPCRT4!NdrClientCall3` at `0x18000a3f4`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall IContextMenu_InvokeCommand_Proxy(__int64 a1, __int64 a2)
{
  unsigned int v4; // edx
  int v5; // r8d
  unsigned __int64 v6; // rax
  _DWORD v8[2]; // [rsp+30h] [rbp-19h] BYREF
  __int64 v9; // [rsp+38h] [rbp-11h]
  unsigned __int64 v10; // [rsp+40h] [rbp-9h]
  __int64 v11; // [rsp+48h] [rbp-1h]
  __int64 v12; // [rsp+50h] [rbp+7h]
  int v13; // [rsp+58h] [rbp+Fh]
  int v14; // [rsp+5Ch] [rbp+13h]
  __int64 v15; // [rsp+60h] [rbp+17h]
  __int64 v16; // [rsp+68h] [rbp+1Fh]
  __int64 v17; // [rsp+70h] [rbp+27h]
  __int64 v18; // [rsp+78h] [rbp+2Fh]
  __int64 v19; // [rsp+80h] [rbp+37h]
  __int64 v20; // [rsp+88h] [rbp+3Fh]
  int v21; // [rsp+90h] [rbp+47h]
  int v22; // [rsp+94h] [rbp+4Bh]

  memset_0(v8, 0, 0x68u);
  v4 = *(_DWORD *)a2;
  v5 = *(_DWORD *)(a2 + 4);
  v9 = *(_QWORD *)(a2 + 8);
  v13 = *(_DWORD *)(a2 + 40);
  v14 = *(_DWORD *)(a2 + 44);
  v11 = *(_QWORD *)(a2 + 24);
  v12 = *(_QWORD *)(a2 + 32);
  v6 = *(_QWORD *)(a2 + 16);
  v8[0] = v4;
  v8[1] = v5;
  if ( v6 >= 0x10000 )
    v10 = v6;
  else
    v21 = v6;
  if ( v4 >= 0x68 )
  {
    v15 = *(_QWORD *)(a2 + 56);
    v20 = *(_QWORD *)(a2 + 96);
    if ( (v5 & 0x4000) != 0 )
    {
      v17 = *(_QWORD *)(a2 + 72);
      v18 = *(_QWORD *)(a2 + 80);
      v19 = *(_QWORD *)(a2 + 88);
      if ( *(_QWORD *)(a2 + 64) >= 0x10000u )
        v16 = *(_QWORD *)(a2 + 64);
      else
        v22 = *(_QWORD *)(a2 + 64);
    }
  }
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1801FD350, 4u, 0, a1, v8);
}

```

## disassembly

```asm
0x18000a320  mov     [rsp-8+arg_0], rbx
0x18000a325  mov     [rsp-8+arg_8], rdi
0x18000a32a  push    rbp
0x18000a32b  lea     rbp, [rsp-57h]
0x18000a330  sub     rsp, 0A0h
0x18000a337  mov     rbx, rdx
0x18000a33a  mov     rdi, rcx
0x18000a33d  xor     edx, edx; Val
0x18000a33f  lea     rcx, [rbp+57h+var_70]; void *
0x18000a343  lea     r8d, [rdx+68h]; Size
0x18000a347  call    memset_0
0x18000a34c  mov     rax, [rbx+8]
0x18000a350  mov     ecx, 10000h
0x18000a355  mov     edx, [rbx]
0x18000a357  mov     r8d, [rbx+4]
0x18000a35b  mov     [rbp+57h+var_68], rax
0x18000a35f  mov     eax, [rbx+28h]
0x18000a362  mov     [rbp+57h+var_48], eax
0x18000a365  mov     eax, [rbx+2Ch]
0x18000a368  mov     [rbp+57h+var_44], eax
0x18000a36b  mov     rax, [rbx+18h]
0x18000a36f  mov     [rbp+57h+var_58], rax
0x18000a373  mov     rax, [rbx+20h]
0x18000a377  mov     [rbp+57h+var_50], rax
0x18000a37b  mov     rax, [rbx+10h]
0x18000a37f  mov     [rbp+57h+var_70], edx
0x18000a382  mov     [rbp+57h+var_6C], r8d
0x18000a386  cmp     rax, rcx
0x18000a389  jnb     short loc_18000A390
0x18000a38b  mov     [rbp+57h+var_10], eax
0x18000a38e  jmp     short loc_18000A394
0x18000a390  mov     [rbp+57h+var_60], rax
0x18000a394  cmp     edx, 68h ; 'h'
0x18000a397  jb      short loc_18000A3DA
0x18000a399  mov     rax, [rbx+38h]
0x18000a39d  mov     [rbp+57h+var_40], rax
0x18000a3a1  mov     rax, [rbx+60h]
0x18000a3a5  mov     [rbp+57h+var_18], rax
0x18000a3a9  bt      r8d, 0Eh
0x18000a3ae  jnb     short loc_18000A3DA
0x18000a3b0  mov     rax, [rbx+48h]
0x18000a3b4  mov     [rbp+57h+var_30], rax
0x18000a3b8  mov     rax, [rbx+50h]
0x18000a3bc  mov     [rbp+57h+var_28], rax
0x18000a3c0  mov     rax, [rbx+58h]
0x18000a3c4  mov     [rbp+57h+var_20], rax
0x18000a3c8  mov     rax, [rbx+40h]
0x18000a3cc  cmp     rax, rcx
0x18000a3cf  jnb     short loc_18000A3D6
0x18000a3d1  mov     [rbp+57h+var_C], eax
0x18000a3d4  jmp     short loc_18000A3DA
0x18000a3d6  mov     [rbp+57h+var_38], rax
0x18000a3da  xor     r8d, r8d; pReturnValue
0x18000a3dd  lea     rax, [rbp+57h+var_70]
0x18000a3e1  mov     r9, rdi
0x18000a3e4  mov     [rsp+0A0h+var_80], rax
0x18000a3e9  lea     rcx, stru_1801FD350; pProxyInfo
0x18000a3f0  lea     edx, [r8+4]; nProcNum
0x18000a3f4  call    cs:__imp_NdrClientCall3
0x18000a3fa  lea     r11, [rsp+0A0h+var_s0]
0x18000a402  mov     rbx, [r11+10h]
0x18000a406  mov     rdi, [r11+18h]
0x18000a40a  mov     rsp, r11
0x18000a40d  pop     rbp
0x18000a40e  retn
```
