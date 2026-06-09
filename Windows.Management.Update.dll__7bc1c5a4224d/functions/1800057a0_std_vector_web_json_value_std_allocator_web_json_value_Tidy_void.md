# std::vector<web::json::value,std::allocator<web::json::value>>::_Tidy(void)

- ea: `0x1800057a0`
- end: `0x180005851`
- name: `?_Tidy@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAXXZ`
- size: `177`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180004df0`
- `0x180005420`

## callees

- `0x180002cc0`
- `0x1800057a0`
- `0x18002a010`

## pseudocode

```c
void __fastcall std::vector<web::json::value>::_Tidy(__int64 a1)
{
  char *v1; // rbx
  char *i; // rsi
  char *v4; // rcx
  char *v5; // rax

  v1 = *(char **)a1;
  if ( *(_QWORD *)a1 )
  {
    for ( i = *(char **)(a1 + 8); v1 != i; v1 += 8 )
    {
      if ( *(_QWORD *)v1 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v1 + 192LL))(*(_QWORD *)v1, 1);
    }
    v4 = *(char **)a1;
    if ( (unsigned __int64)(8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3)) < 0x1000 )
    {
      v5 = *(char **)a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)(v4 - v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x1800057a0  mov     [rsp+arg_8], rbx
0x1800057a5  push    rdi
0x1800057a6  sub     rsp, 20h
0x1800057aa  mov     rbx, [rcx]
0x1800057ad  mov     rdi, rcx
0x1800057b0  test    rbx, rbx
0x1800057b3  jz      loc_180005846
0x1800057b9  mov     [rsp+28h+arg_0], rsi
0x1800057be  mov     rsi, [rcx+8]
0x1800057c2  cmp     rbx, rsi
0x1800057c5  jz      short loc_1800057EC
0x1800057c7  mov     rcx, [rbx]
0x1800057ca  test    rcx, rcx
0x1800057cd  jz      short loc_1800057E3
0x1800057cf  mov     rax, [rcx]
0x1800057d2  mov     edx, 1
0x1800057d7  mov     rax, [rax+0C0h]
0x1800057de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057e3  add     rbx, 8
0x1800057e7  cmp     rbx, rsi
0x1800057ea  jnz     short loc_1800057C7
0x1800057ec  mov     rcx, [rdi]
0x1800057ef  mov     rax, [rdi+10h]
0x1800057f3  mov     rsi, [rsp+28h+arg_0]
0x1800057f8  sub     rax, rcx
0x1800057fb  sar     rax, 3
0x1800057ff  lea     rdx, ds:0[rax*8]; unsigned __int64
0x180005807  cmp     rdx, 1000h
0x18000580e  jb      short loc_18000582E
0x180005810  mov     rax, [rcx-8]
0x180005814  sub     rcx, rax
0x180005817  sub     rcx, 8
0x18000581b  cmp     rcx, 1Fh
0x18000581f  ja      short loc_180005827
0x180005821  add     rdx, 27h ; '''
0x180005825  jmp     short loc_180005831
0x180005827  mov     ecx, 5
0x18000582c  int     29h; Win8: RtlFailFast(ecx)
0x18000582e  mov     rax, rcx
0x180005831  mov     rcx, rax; void *
0x180005834  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005839  xor     eax, eax
0x18000583b  mov     [rdi], rax
0x18000583e  mov     [rdi+8], rax
0x180005842  mov     [rdi+10h], rax
0x180005846  mov     rbx, [rsp+28h+arg_8]
0x18000584b  add     rsp, 20h
0x18000584f  pop     rdi
0x180005850  retn
```
