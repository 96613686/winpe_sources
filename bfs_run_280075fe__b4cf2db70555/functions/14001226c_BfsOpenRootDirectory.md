# BfsOpenRootDirectory

- ea: `0x14001226c`
- end: `0x140012411`
- name: `BfsOpenRootDirectory`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140010b30`

## callees

- `0x140001008`
- `0x1400117fc`
- `0x14001226c`
- `0x140012418`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400123dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400123dd`
- `ntoskrnl!ExAllocatePool2` at `0x1400122b2`
- `ntoskrnl!ExAllocatePool2` at `0x1400122e0`
- `ntoskrnl!ExAllocatePool2` at `0x140012306`
- `ntoskrnl!ExAllocatePool2` at `0x1400122b2`
- `ntoskrnl!ExAllocatePool2` at `0x1400122e0`
- `ntoskrnl!ExAllocatePool2` at `0x140012306`

## pseudocode

```c
__int64 __fastcall BfsOpenRootDirectory(__int64 a1)
{
  int v2; // r15d
  _QWORD *Pool2; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rsi
  _DWORD *v7; // rax
  _DWORD *v8; // r14
  __int64 v9; // rcx
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
  v9 = 3221225495LL;
  Block = -1073741801;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v18 = &v16;
    v16 = -1073741801;
LABEL_14:
    v19 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v9, (unsigned __int8 *)&byte_140016D91, v4, v5, v15, &v17);
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
0x14001226c  mov     [rsp-28h+arg_8], rbx
0x140012271  mov     [rsp-28h+arg_10], rsi
0x140012276  push    rbp
0x140012277  push    rdi
0x140012278  push    r13
0x14001227a  push    r14
0x14001227c  push    r15
0x14001227e  mov     rbp, rsp
0x140012281  sub     rsp, 70h
0x140012285  mov     rax, cs:__security_cookie
0x14001228c  xor     rax, rsp
0x14001228f  mov     [rbp+var_8], rax
0x140012293  mov     rax, [rcx+10h]
0x140012297  mov     rbx, rcx
0x14001229a  mov     r13d, 100h
0x1400122a0  mov     edx, 10h
0x1400122a5  mov     r8d, 48736642h
0x1400122ab  mov     ecx, r13d
0x1400122ae  mov     r15d, [rax+0Ch]
0x1400122b2  call    cs:__imp_ExAllocatePool2
0x1400122b9  nop     dword ptr [rax+rax+00h]
0x1400122be  mov     [rbx+40h], rax
0x1400122c2  test    rax, rax
0x1400122c5  jz      loc_14001238F
0x1400122cb  mov     [rax+8], rax
0x1400122cf  mov     [rax], rax
0x1400122d2  mov     edx, 20h ; ' '
0x1400122d7  mov     r8d, 4C736642h
0x1400122dd  mov     rcx, r13
0x1400122e0  call    cs:__imp_ExAllocatePool2
0x1400122e7  nop     dword ptr [rax+rax+00h]
0x1400122ec  mov     rsi, rax
0x1400122ef  test    rax, rax
0x1400122f2  jz      loc_14001238F
0x1400122f8  mov     edx, 4000h
0x1400122fd  mov     r8d, 62736642h
0x140012303  mov     rcx, r13
0x140012306  call    cs:__imp_ExAllocatePool2
0x14001230d  nop     dword ptr [rax+rax+00h]
0x140012312  mov     r14, rax
0x140012315  test    rax, rax
0x140012318  jz      short loc_14001238F
0x14001231a  mov     r8, rax
0x14001231d  mov     [rsi+10h], rax
0x140012321  mov     edx, r15d
0x140012324  mov     [rsi+18h], r15d
0x140012328  mov     rcx, rbx
0x14001232b  call    BfsReadBlock
0x140012330  mov     edi, eax
0x140012332  test    eax, eax
0x140012334  js      short loc_14001236E
0x140012336  mov     rcx, [rbx+40h]
0x14001233a  mov     rax, [rcx+8]
0x14001233e  cmp     [rax], rcx
0x140012341  jnz     short loc_140012367
0x140012343  mov     [rsi], rcx
0x140012346  mov     [rsi+8], rax
0x14001234a  mov     [rax], rsi
0x14001234d  mov     [rcx+8], rsi
0x140012351  mov     r15d, [r14+4]
0x140012355  test    r15d, r15d
0x140012358  jnz     loc_1400122D2
0x14001235e  mov     [rbx+38h], rbx
0x140012362  jmp     loc_1400123E9
0x140012367  mov     ecx, 3
0x14001236c  int     29h; Win8: RtlFailFast(ecx)
0x14001236e  mov     eax, cs:dword_140019000
0x140012374  cmp     eax, 3
0x140012377  jbe     short loc_1400123C9
0x140012379  lea     rax, [rbp+var_40]
0x14001237d  mov     [rbp+var_40], edi
0x140012380  mov     [rbp+var_18], rax
0x140012384  lea     rax, [rbp+var_38]
0x140012388  mov     [rsp+70h+var_48], rax
0x14001238d  jmp     short loc_1400123B5
0x14001238f  mov     eax, cs:dword_140019000
0x140012395  mov     ecx, 0C0000017h; int
0x14001239a  mov     edi, ecx
0x14001239c  cmp     eax, 3
0x14001239f  jbe     short loc_1400123C9
0x1400123a1  lea     rax, [rbp+var_40]
0x1400123a5  mov     [rbp+var_18], rax
0x1400123a9  lea     rax, [rbp+var_38]
0x1400123ad  mov     [rsp+70h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x1400123b2  mov     [rbp+var_40], ecx
0x1400123b5  lea     rdx, byte_140016D91; int
0x1400123bc  mov     [rbp+var_10], 4
0x1400123c4  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400123c9  mov     rcx, [rbx+40h]
0x1400123cd  test    rcx, rcx
0x1400123d0  jz      short loc_1400123E9
0x1400123d2  call    BfsFreeDirectoryBlockList
0x1400123d7  mov     rcx, [rbx+40h]; P
0x1400123db  xor     edx, edx; Tag
0x1400123dd  call    cs:__imp_ExFreePoolWithTag
0x1400123e4  nop     dword ptr [rax+rax+00h]
0x1400123e9  mov     eax, edi
0x1400123eb  mov     rcx, [rbp+var_8]
0x1400123ef  xor     rcx, rsp; StackCookie
0x1400123f2  call    __security_check_cookie
0x1400123f7  lea     r11, [rsp+70h+var_s0]
0x1400123fc  mov     rbx, [r11+38h]
0x140012400  mov     rsi, [r11+40h]
0x140012404  mov     rsp, r11
0x140012407  pop     r15
0x140012409  pop     r14
0x14001240b  pop     r13
0x14001240d  pop     rdi
0x14001240e  pop     rbp
0x14001240f  retn
```
