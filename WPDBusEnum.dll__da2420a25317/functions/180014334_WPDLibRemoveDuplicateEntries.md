# WPDLibRemoveDuplicateEntries

- ea: `0x180014334`
- end: `0x1800143f1`
- name: `WPDLibRemoveDuplicateEntries`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004f10`
- `0x1800069d0`

## callees

- `0x180014334`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800143a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800143b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800143bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800143a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800143b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800143bc`

## pseudocode

```c
_QWORD *__fastcall WPDLibRemoveDuplicateEntries(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v2; // rdi
  _QWORD *v5; // r14
  _QWORD *v6; // rbx
  _QWORD *i; // rax
  __int64 v8; // rcx
  int v9; // ebp
  _QWORD *v10; // rsi
  void *v11; // rcx
  void *v12; // rcx
  _QWORD *v13; // rax

  v2 = a2;
  if ( !a2 )
    return 0;
  v5 = 0;
  v6 = a2;
  do
  {
    for ( i = a1; ; i = (_QWORD *)*i )
    {
      if ( !i )
      {
        v13 = v6;
        v9 = 0;
        v6 = (_QWORD *)*v6;
        goto LABEL_19;
      }
      v8 = *(_QWORD *)((char *)i + 28) - *(_QWORD *)((char *)v6 + 28);
      if ( !v8 )
        v8 = *(_QWORD *)((char *)i + 36) - *(_QWORD *)((char *)v6 + 36);
      if ( !v8 )
        break;
    }
    v9 = 1;
    v10 = v6;
    if ( v5 )
    {
      *v5 = *v6;
      v6 = (_QWORD *)*v6;
    }
    else
    {
      v6 = (_QWORD *)*v2;
      v2 = (_QWORD *)*v2;
    }
    v11 = (void *)v10[2];
    if ( v11 )
      LocalFree(v11);
    v12 = (void *)v10[1];
    if ( v12 )
      LocalFree(v12);
    LocalFree(v10);
    v13 = v6;
LABEL_19:
    if ( v9 )
      v13 = v5;
    v5 = v13;
  }
  while ( v6 );
  return v2;
}

```

## disassembly

```asm
0x180014334  push    rbx
0x180014336  push    rbp
0x180014337  push    rsi
0x180014338  push    rdi
0x180014339  push    r14
0x18001433b  push    r15
0x18001433d  sub     rsp, 28h
0x180014341  mov     rdi, rdx
0x180014344  mov     r15, rcx
0x180014347  test    rdx, rdx
0x18001434a  jnz     short loc_180014353
0x18001434c  xor     eax, eax
0x18001434e  jmp     loc_1800143E4
0x180014353  xor     r14d, r14d
0x180014356  mov     rbx, rdx
0x180014359  mov     rax, r15
0x18001435c  test    rax, rax
0x18001435f  jz      short loc_1800143C7
0x180014361  mov     rcx, [rax+1Ch]
0x180014365  sub     rcx, [rbx+1Ch]
0x180014369  jnz     short loc_180014373
0x18001436b  mov     rcx, [rax+24h]
0x18001436f  sub     rcx, [rbx+24h]
0x180014373  test    rcx, rcx
0x180014376  jz      short loc_18001437D
0x180014378  mov     rax, [rax]
0x18001437b  jmp     short loc_18001435C
0x18001437d  mov     ebp, 1
0x180014382  mov     rsi, rbx
0x180014385  test    r14, r14
0x180014388  jnz     short loc_180014392
0x18001438a  mov     rbx, [rdi]
0x18001438d  mov     rdi, rbx
0x180014390  jmp     short loc_18001439B
0x180014392  mov     rax, [rbx]
0x180014395  mov     [r14], rax
0x180014398  mov     rbx, [rbx]
0x18001439b  mov     rcx, [rsi+10h]; hMem
0x18001439f  test    rcx, rcx
0x1800143a2  jz      short loc_1800143AA
0x1800143a4  call    cs:__imp_LocalFree
0x1800143aa  mov     rcx, [rsi+8]; hMem
0x1800143ae  test    rcx, rcx
0x1800143b1  jz      short loc_1800143B9
0x1800143b3  call    cs:__imp_LocalFree
0x1800143b9  mov     rcx, rsi; hMem
0x1800143bc  call    cs:__imp_LocalFree
0x1800143c2  mov     rax, rbx
0x1800143c5  jmp     short loc_1800143CF
0x1800143c7  mov     rax, rbx
0x1800143ca  xor     ebp, ebp
0x1800143cc  mov     rbx, [rbx]
0x1800143cf  test    ebp, ebp
0x1800143d1  cmovnz  rax, r14
0x1800143d5  mov     r14, rax
0x1800143d8  test    rbx, rbx
0x1800143db  jnz     loc_180014359
0x1800143e1  mov     rax, rdi
0x1800143e4  add     rsp, 28h
0x1800143e8  pop     r15
0x1800143ea  pop     r14
0x1800143ec  pop     rdi
0x1800143ed  pop     rsi
0x1800143ee  pop     rbp
0x1800143ef  pop     rbx
0x1800143f0  retn
```
