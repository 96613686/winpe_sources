# CArea::ProcessTheJunction(void)

- ea: `0x1004304d0`
- end: `0x100430573`
- name: `?ProcessTheJunction@CArea@@UEAAJXZ`
- size: `163`
- prototype: `__int64 __fastcall(CArea *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path`

## callees

- `0x1004304d0`
- `0x100441c90`

## pseudocode

```c
__int64 __fastcall CArea::ProcessTheJunction(CArea *this)
{
  __int64 v1; // rsi
  __int64 v3; // rbx
  __int64 v4; // r8

  v1 = *((_QWORD *)this + 39);
  CScanner::ClassifyFillOnly(this);
  v3 = *((_QWORD *)this + 38);
  if ( !v3 )
    return 0;
  do
  {
    if ( (*(_WORD *)(v3 + 72) & 0x2600) == 0 )
    {
      v4 = *(_QWORD *)(v3 + 8);
      if ( v4 == *(_QWORD *)(v3 + 16) )
        v4 = *(_QWORD *)(v4 + 32);
      (*(void (__fastcall **)(CArea *, __int64, __int64))(*(_QWORD *)this + 104LL))(this, v3, v4);
    }
    if ( v3 == v1 )
      break;
    v3 = *(_QWORD *)(v3 + 24);
  }
  while ( v3 );
  return 0;
}

```

## disassembly

```asm
0x1004304d0  mov     [rsp+arg_10], rbx
0x1004304d5  mov     [rsp+arg_18], rsi
0x1004304da  push    rdi
0x1004304db  sub     rsp, 20h
0x1004304df  mov     rsi, [rcx+138h]
0x1004304e6  mov     rdi, rcx
0x1004304e9  call    ?ClassifyFillOnly@CScanner@@QEAAXXZ; CScanner::ClassifyFillOnly(void)
0x1004304ee  mov     rbx, [rdi+130h]
0x1004304f5  test    rbx, rbx
0x1004304f8  jz      short loc_100430561
0x1004304fa  mov     [rsp+28h+arg_0], rbp
0x1004304ff  mov     ebp, 2600h
0x100430504  mov     [rsp+28h+arg_8], r14
0x100430509  xor     r14d, r14d
0x10043050c  nop     dword ptr [rax+00h]
0x100430510  movzx   eax, word ptr [rbx+48h]
0x100430514  and     ax, bp
0x100430517  cmp     r14w, ax
0x10043051b  jnz     short loc_100430537
0x10043051d  mov     r8, [rbx+8]
0x100430521  mov     rdx, rbx
0x100430524  mov     rcx, rdi
0x100430527  mov     rax, [rdi]
0x10043052a  cmp     r8, [rbx+10h]
0x10043052e  jnz     short loc_100430534
0x100430530  mov     r8, [r8+20h]
0x100430534  call    qword ptr [rax+68h]
0x100430537  cmp     rbx, rsi
0x10043053a  jz      short loc_100430545
0x10043053c  mov     rbx, [rbx+18h]
0x100430540  test    rbx, rbx
0x100430543  jnz     short loc_100430510
0x100430545  mov     rbp, [rsp+28h+arg_0]
0x10043054a  xor     eax, eax
0x10043054c  mov     r14, [rsp+28h+arg_8]
0x100430551  mov     rbx, [rsp+28h+arg_10]
0x100430556  mov     rsi, [rsp+28h+arg_18]
0x10043055b  add     rsp, 20h
0x10043055f  pop     rdi
0x100430560  retn
0x100430561  mov     rbx, [rsp+28h+arg_10]
0x100430566  xor     eax, eax
0x100430568  mov     rsi, [rsp+28h+arg_18]
0x10043056d  add     rsp, 20h
0x100430571  pop     rdi
0x100430572  retn
```
