# IContextMenu_InvokeCommand_Stub

- ea: `0x18000a418`
- end: `0x18000a4f9`
- name: `IContextMenu_InvokeCommand_Stub`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005ae0`

## callees

- `0x1800045ba`
- `0x18000a418`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall IContextMenu_InvokeCommand_Stub(__int64 a1, __int64 a2)
{
  int v4; // ecx
  __int64 v5; // rax
  bool v6; // cf
  __int64 v7; // rax
  _DWORD v9[2]; // [rsp+20h] [rbp-19h] BYREF
  __int64 v10; // [rsp+28h] [rbp-11h]
  __int64 v11; // [rsp+30h] [rbp-9h]
  __int64 v12; // [rsp+38h] [rbp-1h]
  __int64 v13; // [rsp+40h] [rbp+7h]
  int v14; // [rsp+48h] [rbp+Fh]
  int v15; // [rsp+4Ch] [rbp+13h]
  __int64 v16; // [rsp+58h] [rbp+1Fh]
  __int64 v17; // [rsp+60h] [rbp+27h]
  __int64 v18; // [rsp+68h] [rbp+2Fh]
  __int64 v19; // [rsp+70h] [rbp+37h]
  __int64 v20; // [rsp+78h] [rbp+3Fh]
  __int64 v21; // [rsp+80h] [rbp+47h]

  memset_0(v9, 0, 0x68u);
  v4 = *(_DWORD *)(a2 + 4);
  v10 = *(_QWORD *)(a2 + 8);
  v14 = *(_DWORD *)(a2 + 40);
  v15 = *(_DWORD *)(a2 + 44);
  v12 = *(_QWORD *)(a2 + 24);
  v13 = *(_QWORD *)(a2 + 32);
  v5 = *(_QWORD *)(a2 + 16);
  v9[0] = 56;
  v9[1] = v4;
  if ( !v5 )
    v5 = *(unsigned __int16 *)(a2 + 96);
  v6 = *(_DWORD *)a2 < 0x68u;
  v11 = v5;
  if ( !v6 )
  {
    v21 = *(_QWORD *)(a2 + 88);
    v16 = *(_QWORD *)(a2 + 48);
    v9[0] = 104;
    if ( (v4 & 0x4000) != 0 )
    {
      v19 = *(_QWORD *)(a2 + 72);
      v20 = *(_QWORD *)(a2 + 80);
      v18 = *(_QWORD *)(a2 + 64);
      v7 = *(_QWORD *)(a2 + 56);
      if ( !v7 )
        v7 = *(unsigned __int16 *)(a2 + 100);
      v17 = v7;
    }
  }
  return (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)a1 + 32LL))(a1, v9);
}

```

## disassembly

```asm
0x18000a418  mov     [rsp-8+arg_0], rbx
0x18000a41d  mov     [rsp-8+arg_8], rdi
0x18000a422  push    rbp
0x18000a423  lea     rbp, [rsp-57h]
0x18000a428  sub     rsp, 90h
0x18000a42f  mov     rbx, rdx
0x18000a432  mov     rdi, rcx
0x18000a435  xor     edx, edx; Val
0x18000a437  lea     rcx, [rbp+57h+var_70]; void *
0x18000a43b  lea     r8d, [rdx+68h]; Size
0x18000a43f  call    memset_0
0x18000a444  mov     rax, [rbx+8]
0x18000a448  mov     ecx, [rbx+4]
0x18000a44b  mov     [rbp+57h+var_68], rax
0x18000a44f  mov     eax, [rbx+28h]
0x18000a452  mov     [rbp+57h+var_48], eax
0x18000a455  mov     eax, [rbx+2Ch]
0x18000a458  mov     [rbp+57h+var_44], eax
0x18000a45b  mov     rax, [rbx+18h]
0x18000a45f  mov     [rbp+57h+var_58], rax
0x18000a463  mov     rax, [rbx+20h]
0x18000a467  mov     [rbp+57h+var_50], rax
0x18000a46b  mov     rax, [rbx+10h]
0x18000a46f  mov     [rbp+57h+var_70], 38h ; '8'
0x18000a476  mov     [rbp+57h+var_6C], ecx
0x18000a479  test    rax, rax
0x18000a47c  jnz     short loc_18000A482
0x18000a47e  movzx   eax, word ptr [rbx+60h]
0x18000a482  cmp     dword ptr [rbx], 68h ; 'h'
0x18000a485  mov     [rbp+57h+var_60], rax
0x18000a489  jb      short loc_18000A4D1
0x18000a48b  mov     rax, [rbx+58h]
0x18000a48f  mov     [rbp+57h+var_10], rax
0x18000a493  mov     rax, [rbx+30h]
0x18000a497  mov     [rbp+57h+var_38], rax
0x18000a49b  mov     [rbp+57h+var_70], 68h ; 'h'
0x18000a4a2  bt      ecx, 0Eh
0x18000a4a6  jnb     short loc_18000A4D1
0x18000a4a8  mov     rax, [rbx+48h]
0x18000a4ac  mov     [rbp+57h+var_20], rax
0x18000a4b0  mov     rax, [rbx+50h]
0x18000a4b4  mov     [rbp+57h+var_18], rax
0x18000a4b8  mov     rax, [rbx+40h]
0x18000a4bc  mov     [rbp+57h+var_28], rax
0x18000a4c0  mov     rax, [rbx+38h]
0x18000a4c4  test    rax, rax
0x18000a4c7  jnz     short loc_18000A4CD
0x18000a4c9  movzx   eax, word ptr [rbx+64h]
0x18000a4cd  mov     [rbp+57h+var_30], rax
0x18000a4d1  mov     rax, [rdi]
0x18000a4d4  lea     rdx, [rbp+57h+var_70]
0x18000a4d8  mov     rcx, rdi
0x18000a4db  mov     rax, [rax+20h]
0x18000a4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4e4  lea     r11, [rsp+90h+var_s0]
0x18000a4ec  mov     rbx, [r11+10h]
0x18000a4f0  mov     rdi, [r11+18h]
0x18000a4f4  mov     rsp, r11
0x18000a4f7  pop     rbp
0x18000a4f8  retn
```
