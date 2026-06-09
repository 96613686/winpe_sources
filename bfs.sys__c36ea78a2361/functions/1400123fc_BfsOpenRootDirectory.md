# BfsOpenRootDirectory

- ea: `0x1400123fc`
- end: `0x1400125a1`
- name: `BfsOpenRootDirectory`
- size: `421`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140010cc8`

## callees

- `0x140001008`
- `0x140011994`
- `0x1400123fc`
- `0x1400125a8`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001256d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001256d`
- `ntoskrnl!ExAllocatePool2` at `0x140012442`
- `ntoskrnl!ExAllocatePool2` at `0x140012470`
- `ntoskrnl!ExAllocatePool2` at `0x140012496`
- `ntoskrnl!ExAllocatePool2` at `0x140012442`
- `ntoskrnl!ExAllocatePool2` at `0x140012470`
- `ntoskrnl!ExAllocatePool2` at `0x140012496`

## pseudocode

```c
__int64 __fastcall BfsOpenRootDirectory(__int64 a1)
{
  int v2; // r15d
  _QWORD *Pool2; // rax
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rsi
  _DWORD *v7; // rax
  _DWORD *v8; // r14
  int v9; // ecx
  NTSTATUS Block; // edi
  __int64 v11; // rcx
  __int64 *v12; // rax
  __int64 v13; // rcx
  int v15; // [rsp+20h] [rbp-50h]
  int v16; // [rsp+30h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+38h] [rbp-38h] BYREF
  int *v18; // [rsp+58h] [rbp-18h]
  __int64 v19; // [rsp+60h] [rbp-10h]

  v2 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 12LL);
  Pool2 = (_QWORD *)ExAllocatePool2(256, 16, 1215522370);
  *(_QWORD *)(a1 + 64) = Pool2;
  if ( Pool2 )
  {
    Pool2[1] = Pool2;
    *Pool2 = Pool2;
    while ( 1 )
    {
      v6 = ExAllocatePool2(256, 32, 1282631234);
      if ( !v6 )
        break;
      v7 = (_DWORD *)ExAllocatePool2(256, 0x4000, 1651729986);
      v8 = v7;
      if ( !v7 )
        break;
      *(_QWORD *)(v6 + 16) = v7;
      *(_DWORD *)(v6 + 24) = v2;
      Block = BfsReadBlock(a1, v2, v7);
      if ( Block < 0 )
      {
        if ( (unsigned int)dword_140019000 <= 3 )
          goto LABEL_15;
        v16 = Block;
        v18 = &v16;
        goto LABEL_14;
      }
      v11 = *(_QWORD *)(a1 + 64);
      v12 = *(__int64 **)(v11 + 8);
      if ( *v12 != v11 )
        __fastfail(3u);
      *(_QWORD *)v6 = v11;
      *(_QWORD *)(v6 + 8) = v12;
      *v12 = v6;
      *(_QWORD *)(v11 + 8) = v6;
      v2 = v8[1];
      if ( !v2 )
      {
        *(_QWORD *)(a1 + 56) = a1;
        return (unsigned int)Block;
      }
    }
  }
  v9 = -1073741801;
  Block = -1073741801;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v18 = &v16;
    v16 = -1073741801;
LABEL_14:
    v19 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v9, (int)&byte_140016D91, v4, v5, v15, &v17);
  }
LABEL_15:
  v13 = *(_QWORD *)(a1 + 64);
  if ( v13 )
  {
    BfsFreeDirectoryBlockList(v13);
    ExFreePoolWithTag(*(PVOID *)(a1 + 64), 0);
  }
  return (unsigned int)Block;
}

```

## disassembly

```asm
0x1400123fc  mov     [rsp-28h+arg_8], rbx
0x140012401  mov     [rsp-28h+arg_10], rsi
0x140012406  push    rbp
0x140012407  push    rdi
0x140012408  push    r13
0x14001240a  push    r14
0x14001240c  push    r15
0x14001240e  mov     rbp, rsp
0x140012411  sub     rsp, 70h
0x140012415  mov     rax, cs:__security_cookie
0x14001241c  xor     rax, rsp
0x14001241f  mov     [rbp+var_8], rax
0x140012423  mov     rax, [rcx+10h]
0x140012427  mov     rbx, rcx
0x14001242a  mov     r13d, 100h
0x140012430  mov     edx, 10h
0x140012435  mov     r8d, 48736642h
0x14001243b  mov     ecx, r13d
0x14001243e  mov     r15d, [rax+0Ch]
0x140012442  call    cs:__imp_ExAllocatePool2
0x140012449  nop     dword ptr [rax+rax+00h]
0x14001244e  mov     [rbx+40h], rax
0x140012452  test    rax, rax
0x140012455  jz      loc_14001251F
0x14001245b  mov     [rax+8], rax
0x14001245f  mov     [rax], rax
0x140012462  mov     edx, 20h ; ' '
0x140012467  mov     r8d, 4C736642h
0x14001246d  mov     rcx, r13
0x140012470  call    cs:__imp_ExAllocatePool2
0x140012477  nop     dword ptr [rax+rax+00h]
0x14001247c  mov     rsi, rax
0x14001247f  test    rax, rax
0x140012482  jz      loc_14001251F
0x140012488  mov     edx, 4000h
0x14001248d  mov     r8d, 62736642h
0x140012493  mov     rcx, r13
0x140012496  call    cs:__imp_ExAllocatePool2
0x14001249d  nop     dword ptr [rax+rax+00h]
0x1400124a2  mov     r14, rax
0x1400124a5  test    rax, rax
0x1400124a8  jz      short loc_14001251F
0x1400124aa  mov     r8, rax
0x1400124ad  mov     [rsi+10h], rax
0x1400124b1  mov     edx, r15d
0x1400124b4  mov     [rsi+18h], r15d
0x1400124b8  mov     rcx, rbx
0x1400124bb  call    BfsReadBlock
0x1400124c0  mov     edi, eax
0x1400124c2  test    eax, eax
0x1400124c4  js      short loc_1400124FE
0x1400124c6  mov     rcx, [rbx+40h]
0x1400124ca  mov     rax, [rcx+8]
0x1400124ce  cmp     [rax], rcx
0x1400124d1  jnz     short loc_1400124F7
0x1400124d3  mov     [rsi], rcx
0x1400124d6  mov     [rsi+8], rax
0x1400124da  mov     [rax], rsi
0x1400124dd  mov     [rcx+8], rsi
0x1400124e1  mov     r15d, [r14+4]
0x1400124e5  test    r15d, r15d
0x1400124e8  jnz     loc_140012462
0x1400124ee  mov     [rbx+38h], rbx
0x1400124f2  jmp     loc_140012579
0x1400124f7  mov     ecx, 3
0x1400124fc  int     29h; Win8: RtlFailFast(ecx)
0x1400124fe  mov     eax, cs:dword_140019000
0x140012504  cmp     eax, 3
0x140012507  jbe     short loc_140012559
0x140012509  lea     rax, [rbp+var_40]
0x14001250d  mov     [rbp+var_40], edi
0x140012510  mov     [rbp+var_18], rax
0x140012514  lea     rax, [rbp+var_38]
0x140012518  mov     [rsp+70h+var_48], rax
0x14001251d  jmp     short loc_140012545
0x14001251f  mov     eax, cs:dword_140019000
0x140012525  mov     ecx, 0C0000017h; int
0x14001252a  mov     edi, ecx
0x14001252c  cmp     eax, 3
0x14001252f  jbe     short loc_140012559
0x140012531  lea     rax, [rbp+var_40]
0x140012535  mov     [rbp+var_18], rax
0x140012539  lea     rax, [rbp+var_38]
0x14001253d  mov     [rsp+70h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x140012542  mov     [rbp+var_40], ecx
0x140012545  lea     rdx, byte_140016D91; int
0x14001254c  mov     [rbp+var_10], 4
0x140012554  call    _tlgWriteTransfer_EtwWriteTransfer
0x140012559  mov     rcx, [rbx+40h]
0x14001255d  test    rcx, rcx
0x140012560  jz      short loc_140012579
0x140012562  call    BfsFreeDirectoryBlockList
0x140012567  mov     rcx, [rbx+40h]; P
0x14001256b  xor     edx, edx; Tag
0x14001256d  call    cs:__imp_ExFreePoolWithTag
0x140012574  nop     dword ptr [rax+rax+00h]
0x140012579  mov     eax, edi
0x14001257b  mov     rcx, [rbp+var_8]
0x14001257f  xor     rcx, rsp; StackCookie
0x140012582  call    __security_check_cookie
0x140012587  lea     r11, [rsp+70h+var_s0]
0x14001258c  mov     rbx, [r11+38h]
0x140012590  mov     rsi, [r11+40h]
0x140012594  mov     rsp, r11
0x140012597  pop     r15
0x140012599  pop     r14
0x14001259b  pop     r13
0x14001259d  pop     rdi
0x14001259e  pop     rbp
0x14001259f  retn
```
