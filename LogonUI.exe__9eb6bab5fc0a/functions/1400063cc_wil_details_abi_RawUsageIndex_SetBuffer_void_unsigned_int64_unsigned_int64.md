# wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)

- ea: `0x1400063cc`
- end: `0x1400064b1`
- name: `?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z`
- size: `229`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140001d6c`
- `0x140005da4`

## callees

- `0x14000469c`
- `0x1400063cc`
- `0x140006f84`

## pseudocode

```c
void __fastcall wil::details_abi::RawUsageIndex::SetBuffer(
        wil::details_abi::RawUsageIndex *this,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  wil::details *v8; // rcx
  _WORD *v9; // rcx
  char v10; // al
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( (unsigned __int64)a4 < 0xA )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, a2, a3, a4);
  v8 = (wil::details *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v8 )
    wil::details::FreeProcessHeap(v8, a2);
  *((_QWORD *)this + 3) = a2;
  *((_QWORD *)this + 4) = &a2[a3];
  *((_QWORD *)this + 5) = &a4[(_QWORD)a2];
  *((_BYTE *)this + 57) = 0;
  if ( a3 < 0xA )
    goto LABEL_15;
  v9 = a2 + 2;
  if ( *(_WORD *)a2 || (v10 = 0, *v9 > *(_WORD *)this) )
    v10 = 1;
  *((_BYTE *)this + 57) = v10;
  if ( *(_WORD *)a2
    || *v9 != *(_WORD *)this
    || *((_WORD *)a2 + 2) != *((_WORD *)this + 1)
    || a2[8] != *((_BYTE *)this + 4)
    || *((_WORD *)a2 + 3) != *((_WORD *)this + 3)
    || a2[9] != *((_BYTE *)this + 8) )
  {
LABEL_15:
    *(_WORD *)a2 = 0;
    *((_WORD *)a2 + 1) = *(_WORD *)this;
    *((_WORD *)a2 + 2) = *((_WORD *)this + 1);
    a2[8] = *((_BYTE *)this + 4);
    *((_WORD *)a2 + 3) = *((_WORD *)this + 3);
    a2[9] = *((_BYTE *)this + 8);
    *((_QWORD *)this + 4) = *((_QWORD *)this + 3) + 10LL;
  }
}

```

## disassembly

```asm
0x1400063cc  push    rbx
0x1400063ce  push    rbp
0x1400063cf  push    rsi
0x1400063d0  push    rdi
0x1400063d1  push    r14
0x1400063d3  sub     rsp, 20h
0x1400063d7  mov     rsi, r9
0x1400063da  mov     rbp, r8
0x1400063dd  mov     rdi, rdx
0x1400063e0  mov     rbx, rcx
0x1400063e3  cmp     r9, 0Ah
0x1400063e7  jnb     short loc_1400063F4
0x1400063e9  mov     rcx, [rsp+48h]; this
0x1400063ee  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400063f4  mov     rcx, [rcx+30h]; this
0x1400063f8  xor     r14d, r14d
0x1400063fb  mov     [rbx+30h], r14
0x1400063ff  test    rcx, rcx
0x140006402  jz      short loc_140006409
0x140006404  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140006409  mov     [rbx+18h], rdi
0x14000640d  lea     rax, [rdi+rbp]
0x140006411  mov     [rbx+20h], rax
0x140006415  lea     rax, [rdi+rsi]
0x140006419  mov     [rbx+28h], rax
0x14000641d  mov     [rbx+39h], r14b
0x140006421  cmp     rbp, 0Ah
0x140006425  jb      short loc_140006473
0x140006427  lea     rcx, [rdi+2]
0x14000642b  cmp     [rdi], r14w
0x14000642f  ja      short loc_14000643C
0x140006431  movzx   eax, word ptr [rbx]
0x140006434  cmp     [rcx], ax
0x140006437  mov     al, r14b
0x14000643a  jbe     short loc_14000643E
0x14000643c  mov     al, 1
0x14000643e  mov     [rbx+39h], al
0x140006441  cmp     [rdi], r14w
0x140006445  jnz     short loc_140006473
0x140006447  movzx   eax, word ptr [rbx]
0x14000644a  cmp     [rcx], ax
0x14000644d  jnz     short loc_140006473
0x14000644f  movzx   eax, word ptr [rbx+2]
0x140006453  cmp     [rdi+4], ax
0x140006457  jnz     short loc_140006473
0x140006459  mov     al, [rbx+4]
0x14000645c  cmp     [rdi+8], al
0x14000645f  jnz     short loc_140006473
0x140006461  movzx   eax, word ptr [rbx+6]
0x140006465  cmp     [rdi+6], ax
0x140006469  jnz     short loc_140006473
0x14000646b  mov     al, [rbx+8]
0x14000646e  cmp     [rdi+9], al
0x140006471  jz      short loc_1400064A6
0x140006473  mov     [rdi], r14w
0x140006477  movzx   eax, word ptr [rbx]
0x14000647a  mov     [rdi+2], ax
0x14000647e  movzx   eax, word ptr [rbx+2]
0x140006482  mov     [rdi+4], ax
0x140006486  mov     al, [rbx+4]
0x140006489  mov     [rdi+8], al
0x14000648c  movzx   eax, word ptr [rbx+6]
0x140006490  mov     [rdi+6], ax
0x140006494  mov     al, [rbx+8]
0x140006497  mov     [rdi+9], al
0x14000649a  mov     rax, [rbx+18h]
0x14000649e  add     rax, 0Ah
0x1400064a2  mov     [rbx+20h], rax
0x1400064a6  add     rsp, 20h
0x1400064aa  pop     r14
0x1400064ac  pop     rdi
0x1400064ad  pop     rsi
0x1400064ae  pop     rbp
0x1400064af  pop     rbx
0x1400064b0  retn
```
