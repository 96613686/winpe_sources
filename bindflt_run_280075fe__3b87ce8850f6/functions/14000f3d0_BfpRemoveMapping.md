# BfpRemoveMapping

- ea: `0x14000f3d0`
- end: `0x14000f53c`
- name: `BfpRemoveMapping`
- size: `364`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x140003304`
- `0x14000f3d0`
- `0x14000f544`
- `0x140017bb8`
- `0x14001e854`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x14000f4f1`
- `ntoskrnl!RtlRbRemoveNode` at `0x14000f511`
- `ntoskrnl!RtlRbRemoveNode` at `0x14000f4f1`
- `ntoskrnl!RtlRbRemoveNode` at `0x14000f511`

## pseudocode

```c
__int64 __fastcall BfpRemoveMapping(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  unsigned __int64 v5; // rbx
  int v6; // edx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rax
  char v9; // dl
  unsigned int v10; // ebx
  __int64 v11; // rdx
  char v13; // [rsp+68h] [rbp+10h] BYREF

  v2 = *(_QWORD *)(a2 + 72);
  v13 = 1;
  if ( (unsigned __int8)BfpPathTreeEmpty(v2) )
    goto LABEL_24;
  v5 = *(_QWORD *)v2;
  if ( !*(_QWORD *)v2 )
    goto LABEL_24;
  while ( (int)BfpCanRemoveMapping(v5, &v13) >= 0 )
  {
    v7 = *(_QWORD *)v5;
    if ( !*(_QWORD *)v5 )
    {
      v7 = *(_QWORD *)(v5 + 8);
      if ( !v7 )
      {
        v8 = v5;
        v9 = *(_BYTE *)(v2 + 8) & 1;
        while ( 1 )
        {
          v8 = *(_QWORD *)(v8 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
          if ( v9 )
          {
            if ( !v8 )
              goto LABEL_20;
            v8 ^= v5;
          }
          if ( !v8 )
            goto LABEL_20;
          v7 = *(_QWORD *)(v8 + 8);
          if ( v9 )
          {
            if ( !v7 )
              goto LABEL_18;
            v7 ^= v8;
          }
          if ( v7 && v7 != v5 )
            goto LABEL_19;
LABEL_18:
          v5 = v8;
        }
      }
    }
    if ( (*(_BYTE *)(v2 + 8) & 1) != 0 )
      v5 ^= v7;
    else
LABEL_19:
      v5 = v7;
  }
LABEL_20:
  if ( v13 )
  {
LABEL_24:
    v11 = *(_QWORD *)(a2 + 80);
    v10 = 0;
    if ( v11 )
    {
      if ( a1 )
        RtlRbRemoveNode(a1, v11 + 8);
      BfpDeletePathTierNode(*(PVOID *)(a2 + 80));
    }
    if ( a1 )
      RtlRbRemoveNode(a1, a2);
    BfpDeletePathTierNode((PVOID)(a2 - 8));
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        8,
        26,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        35);
    }
    return (unsigned int)-1073741790;
  }
  return v10;
}

```

## disassembly

```asm
0x14000f3d0  mov     [rsp+arg_0], rbx
0x14000f3d5  mov     [rsp+arg_10], rbp
0x14000f3da  push    rsi
0x14000f3db  push    rdi
0x14000f3dc  push    r14
0x14000f3de  sub     rsp, 40h
0x14000f3e2  mov     rdi, [rdx+48h]
0x14000f3e6  mov     rsi, rcx
0x14000f3e9  mov     rcx, rdi
0x14000f3ec  mov     [rsp+58h+arg_8], 1
0x14000f3f1  mov     r14, rdx
0x14000f3f4  call    BfpPathTreeEmpty
0x14000f3f9  test    al, al
0x14000f3fb  jnz     loc_14000F4DA
0x14000f401  mov     rbx, [rdi]
0x14000f404  test    rbx, rbx
0x14000f407  jz      loc_14000F4DA
0x14000f40d  lea     rdx, [rsp+58h+arg_8]
0x14000f412  mov     rcx, rbx
0x14000f415  call    BfpCanRemoveMapping
0x14000f41a  test    eax, eax
0x14000f41c  js      short loc_14000F480
0x14000f41e  mov     rcx, [rbx]
0x14000f421  test    rcx, rcx
0x14000f424  jz      short loc_14000F431
0x14000f426  test    byte ptr [rdi+8], 1
0x14000f42a  jz      short loc_14000F47B
0x14000f42c  xor     rbx, rcx
0x14000f42f  jmp     short loc_14000F40D
0x14000f431  mov     rcx, [rbx+8]
0x14000f435  test    rcx, rcx
0x14000f438  jnz     short loc_14000F426
0x14000f43a  mov     dl, [rdi+8]
0x14000f43d  mov     rax, rbx
0x14000f440  and     dl, 1
0x14000f443  mov     rax, [rax+10h]
0x14000f447  and     rax, 0FFFFFFFFFFFFFFFCh
0x14000f44b  test    dl, dl
0x14000f44d  jz      short loc_14000F457
0x14000f44f  test    rax, rax
0x14000f452  jz      short loc_14000F480
0x14000f454  xor     rax, rbx
0x14000f457  test    rax, rax
0x14000f45a  jz      short loc_14000F480
0x14000f45c  mov     rcx, [rax+8]
0x14000f460  test    dl, dl
0x14000f462  jz      short loc_14000F46C
0x14000f464  test    rcx, rcx
0x14000f467  jz      short loc_14000F476
0x14000f469  xor     rcx, rax
0x14000f46c  test    rcx, rcx
0x14000f46f  jz      short loc_14000F476
0x14000f471  cmp     rcx, rbx
0x14000f474  jnz     short loc_14000F47B
0x14000f476  mov     rbx, rax
0x14000f479  jmp     short loc_14000F443
0x14000f47b  mov     rbx, rcx
0x14000f47e  jmp     short loc_14000F40D
0x14000f480  cmp     [rsp+58h+arg_8], 0
0x14000f485  jnz     short loc_14000F4DA
0x14000f487  lea     rax, WPP_RECORDER_INITIALIZED
0x14000f48e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000f495  jz      short loc_14000F4D3
0x14000f497  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f49e  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14000f4a5  mov     r9d, 1Ah
0x14000f4ab  mov     [rsp+58h+var_28], 523h
0x14000f4b3  mov     [rsp+58h+var_30], rax
0x14000f4b8  mov     dl, 2
0x14000f4ba  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14000f4c1  mov     rcx, [rcx+40h]
0x14000f4c5  lea     r8d, [r9-12h]
0x14000f4c9  mov     [rsp+58h+var_38], rax
0x14000f4ce  call    WPP_RECORDER_SF_sD
0x14000f4d3  mov     ebx, 0C0000022h
0x14000f4d8  jmp     short loc_14000F526
0x14000f4da  mov     rdx, [r14+50h]
0x14000f4de  xor     ebx, ebx
0x14000f4e0  test    rdx, rdx
0x14000f4e3  jz      short loc_14000F506
0x14000f4e5  test    rsi, rsi
0x14000f4e8  jz      short loc_14000F4FD
0x14000f4ea  add     rdx, 8
0x14000f4ee  mov     rcx, rsi
0x14000f4f1  call    cs:__imp_RtlRbRemoveNode
0x14000f4f8  nop     dword ptr [rax+rax+00h]
0x14000f4fd  mov     rcx, [r14+50h]; P
0x14000f501  call    BfpDeletePathTierNode
0x14000f506  test    rsi, rsi
0x14000f509  jz      short loc_14000F51D
0x14000f50b  mov     rdx, r14
0x14000f50e  mov     rcx, rsi
0x14000f511  call    cs:__imp_RtlRbRemoveNode
0x14000f518  nop     dword ptr [rax+rax+00h]
0x14000f51d  lea     rcx, [r14-8]; P
0x14000f521  call    BfpDeletePathTierNode
0x14000f526  mov     rbp, [rsp+58h+arg_10]
0x14000f52b  mov     eax, ebx
0x14000f52d  mov     rbx, [rsp+58h+arg_0]
0x14000f532  add     rsp, 40h
0x14000f536  pop     r14
0x14000f538  pop     rdi
0x14000f539  pop     rsi
0x14000f53a  retn
```
