# std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>::~vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>(void)

- ea: `0x140003a90`
- end: `0x140003b02`
- name: `??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `114`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140006b70`
- `0x14000e3f3`
- `0x14000ec0f`

## callees

- `0x140003a90`
- `0x140010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140003ad5`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003ad5`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(__int64 a1)
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
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v1 + 64LL))(*v1, 1);
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
0x140003a90  mov     [rsp+arg_0], rbx
0x140003a95  mov     [rsp+arg_8], rsi
0x140003a9a  push    rdi
0x140003a9b  sub     rsp, 20h
0x140003a9f  mov     rdi, [rcx]
0x140003aa2  mov     rbx, rcx
0x140003aa5  test    rdi, rdi
0x140003aa8  jz      short loc_140003AF2
0x140003aaa  mov     rsi, [rcx+8]
0x140003aae  jmp     short loc_140003ACD
0x140003ab0  mov     rcx, [rdi]
0x140003ab3  test    rcx, rcx
0x140003ab6  jz      short loc_140003AC9
0x140003ab8  mov     rax, [rcx]
0x140003abb  mov     edx, 1
0x140003ac0  mov     rax, [rax+40h]
0x140003ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ac9  add     rdi, 8
0x140003acd  cmp     rdi, rsi
0x140003ad0  jnz     short loc_140003AB0
0x140003ad2  mov     rcx, [rbx]
0x140003ad5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003adb  mov     qword ptr [rbx], 0
0x140003ae2  mov     qword ptr [rbx+8], 0
0x140003aea  mov     qword ptr [rbx+10h], 0
0x140003af2  mov     rbx, [rsp+28h+arg_0]
0x140003af7  mov     rsi, [rsp+28h+arg_8]
0x140003afc  add     rsp, 20h
0x140003b00  pop     rdi
0x140003b01  retn
```
