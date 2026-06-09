# std::vector<std::unique_ptr<FilterBasicParameter,std::default_delete<FilterBasicParameter>>,std::allocator<std::unique_ptr<FilterBasicParameter,std::default_delete<FilterBasicParameter>>>>::~vector<std::unique_ptr<FilterBasicParameter,std::default_delete<FilterBasicParameter>>,std::allocator<std::unique_ptr<FilterBasicParameter,std::default_delete<FilterBasicParameter>>>>(void)

- ea: `0x18001046c`
- end: `0x1800104dd`
- name: `??1?$vector@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `113`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800104e4`
- `0x1800228d9`

## callees

- `0x18001046c`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800104b0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800104b0`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<FilterBasicParameter>>::~vector<std::unique_ptr<FilterBasicParameter>>(
        __int64 a1)
{
  _QWORD *v1; // rdi
  _QWORD *v3; // rsi

  v1 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(_QWORD **)(a1 + 8);
    while ( v1 != v3 )
    {
      if ( *v1 )
        (**(void (__fastcall ***)(_QWORD, __int64))*v1)(*v1, 1);
      ++v1;
    }
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18001046c  mov     [rsp+arg_0], rbx
0x180010471  mov     [rsp+arg_8], rsi
0x180010476  push    rdi
0x180010477  sub     rsp, 20h
0x18001047b  mov     rdi, [rcx]
0x18001047e  mov     rbx, rcx
0x180010481  test    rdi, rdi
0x180010484  jz      short loc_1800104CD
0x180010486  mov     rsi, [rcx+8]
0x18001048a  jmp     short loc_1800104A8
0x18001048c  mov     rcx, [rdi]
0x18001048f  test    rcx, rcx
0x180010492  jz      short loc_1800104A4
0x180010494  mov     rax, [rcx]
0x180010497  mov     edx, 1
0x18001049c  mov     rax, [rax]
0x18001049f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104a4  add     rdi, 8
0x1800104a8  cmp     rdi, rsi
0x1800104ab  jnz     short loc_18001048C
0x1800104ad  mov     rcx, [rbx]
0x1800104b0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800104b6  mov     qword ptr [rbx], 0
0x1800104bd  mov     qword ptr [rbx+8], 0
0x1800104c5  mov     qword ptr [rbx+10h], 0
0x1800104cd  mov     rbx, [rsp+28h+arg_0]
0x1800104d2  mov     rsi, [rsp+28h+arg_8]
0x1800104d7  add     rsp, 20h
0x1800104db  pop     rdi
0x1800104dc  retn
```
