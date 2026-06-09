# std::vector<web::json::value,std::allocator<web::json::value>>::_Tidy(void)

- ea: `0x180005d90`
- end: `0x180005e30`
- name: `?_Tidy@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAXXZ`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180005440`
- `0x1800059d0`

## callees

- `0x180002c74`
- `0x180005d90`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005e29`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005e29`

## pseudocode

```c
__int64 __fastcall std::vector<web::json::value>::_Tidy(__int64 a1)
{
  char *v1; // rbx
  char *i; // rsi
  char *v4; // rcx
  unsigned __int64 v5; // rdx
  char *v6; // r8
  unsigned __int64 v7; // rdx
  char *v8; // rcx
  __int64 result; // rax

  v1 = *(char **)a1;
  if ( *(_QWORD *)a1 )
  {
    for ( i = *(char **)(a1 + 8); v1 != i; v1 += 8 )
    {
      if ( *(_QWORD *)v1 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v1 + 192LL))(*(_QWORD *)v1, 1);
    }
    v4 = *(char **)a1;
    v5 = (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v5 >= 0x1000 )
    {
      v6 = (char *)*((_QWORD *)v4 - 1);
      v7 = v5 + 39;
      v8 = (char *)(v4 - v6);
      if ( (unsigned __int64)(v8 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v8, v7);
        JUMPOUT(0x180005E2FLL);
      }
      v4 = v6;
    }
    operator delete(v4);
    result = 0;
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005d90  mov     [rsp+arg_8], rbx
0x180005d95  push    rdi
0x180005d96  sub     rsp, 20h
0x180005d9a  mov     rbx, [rcx]
0x180005d9d  mov     rdi, rcx
0x180005da0  test    rbx, rbx
0x180005da3  jz      short loc_180005E1E
0x180005da5  mov     [rsp+28h+arg_0], rsi
0x180005daa  mov     rsi, [rcx+8]
0x180005dae  cmp     rbx, rsi
0x180005db1  jz      short loc_180005DD8
0x180005db3  mov     rcx, [rbx]
0x180005db6  test    rcx, rcx
0x180005db9  jz      short loc_180005DCF
0x180005dbb  mov     rax, [rcx]
0x180005dbe  mov     edx, 1
0x180005dc3  mov     rax, [rax+0C0h]
0x180005dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dcf  add     rbx, 8
0x180005dd3  cmp     rbx, rsi
0x180005dd6  jnz     short loc_180005DB3
0x180005dd8  mov     rcx, [rdi]
0x180005ddb  mov     rdx, [rdi+10h]
0x180005ddf  mov     rsi, [rsp+28h+arg_0]
0x180005de4  sub     rdx, rcx
0x180005de7  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180005deb  cmp     rdx, 1000h
0x180005df2  jb      short loc_180005E0C
0x180005df4  mov     r8, [rcx-8]
0x180005df8  add     rdx, 27h ; '''; unsigned __int64
0x180005dfc  sub     rcx, r8
0x180005dff  lea     rax, [rcx-8]
0x180005e03  cmp     rax, 1Fh
0x180005e07  ja      short loc_180005E29
0x180005e09  mov     rcx, r8; void *
0x180005e0c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005e11  xor     eax, eax
0x180005e13  mov     [rdi], rax
0x180005e16  mov     [rdi+8], rax
0x180005e1a  mov     [rdi+10h], rax
0x180005e1e  mov     rbx, [rsp+28h+arg_8]
0x180005e23  add     rsp, 20h
0x180005e27  pop     rdi
0x180005e28  retn
0x180005e29  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
```
