# __crt_stdio_output::string_output_adapter<wchar_t>::write_string(wchar_t const * const,int,int * const,__crt_deferred_errno_cache &)

- ea: `0x18000d5fc`
- end: `0x18000d6a1`
- name: `?write_string@?$string_output_adapter@_W@__crt_stdio_output@@QEBAXQEB_WHQEAHAEAV__crt_deferred_errno_cache@@@Z`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cbfc`
- `0x18000d514`

## callees

- `0x18000d5fc`
- `0x1800245e0`

## pseudocode

```c
void __fastcall __crt_stdio_output::string_output_adapter<wchar_t>::write_string(
        __int64 a1,
        const void *a2,
        int a3,
        _DWORD *a4)
{
  __int64 v5; // rsi
  _QWORD *v6; // rcx
  __int64 v8; // rax
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // r14
  void *v11; // rcx

  if ( a3 )
  {
    v5 = a3;
    v6 = *(_QWORD **)a1;
    v8 = v6[1];
    if ( v6[2] == v8 )
    {
      if ( *((_BYTE *)v6 + 24) )
        *a4 += a3;
      else
        *a4 = -1;
    }
    else
    {
      v9 = v8 - v6[2];
      v10 = a3;
      v11 = (void *)*v6;
      if ( v9 < a3 )
        v10 = v9;
      memmove(v11, a2, 2 * v10);
      **(_QWORD **)a1 += 2 * v10;
      *(_QWORD *)(*(_QWORD *)a1 + 16LL) += v10;
      if ( *(_BYTE *)(*(_QWORD *)a1 + 24LL) )
      {
        *a4 += v5;
      }
      else if ( v10 == v5 )
      {
        *a4 += v10;
      }
      else
      {
        *a4 = -1;
      }
    }
  }
}

```

## disassembly

```asm
0x18000d5fc  test    r8d, r8d
0x18000d5ff  jz      locret_18000D6A0
0x18000d605  mov     [rsp+arg_0], rbx
0x18000d60a  mov     [rsp+arg_8], rbp
0x18000d60f  mov     [rsp+arg_10], rsi
0x18000d614  push    rdi
0x18000d615  push    r14
0x18000d617  push    r15
0x18000d619  sub     rsp, 20h
0x18000d61d  mov     r15, rcx
0x18000d620  movsxd  rsi, r8d
0x18000d623  mov     rcx, [rcx]
0x18000d626  mov     rdi, r9
0x18000d629  mov     rax, [rcx+8]
0x18000d62d  cmp     [rcx+10h], rax
0x18000d631  jnz     short loc_18000D644
0x18000d633  cmp     byte ptr [rcx+18h], 0
0x18000d637  jz      short loc_18000D63E
0x18000d639  add     [r9], esi
0x18000d63c  jmp     short loc_18000D688
0x18000d63e  or      dword ptr [r9], 0FFFFFFFFh
0x18000d642  jmp     short loc_18000D688
0x18000d644  sub     rax, [rcx+10h]
0x18000d648  mov     r14, rsi
0x18000d64b  mov     rcx, [rcx]; void *
0x18000d64e  cmp     rax, rsi
0x18000d651  cmovb   r14, rax
0x18000d655  lea     rbx, [r14+r14]
0x18000d659  mov     r8, rbx; Size
0x18000d65c  call    memmove
0x18000d661  mov     rax, [r15]
0x18000d664  add     [rax], rbx
0x18000d667  mov     rax, [r15]
0x18000d66a  add     [rax+10h], r14
0x18000d66e  mov     rax, [r15]
0x18000d671  cmp     byte ptr [rax+18h], 0
0x18000d675  jz      short loc_18000D67B
0x18000d677  add     [rdi], esi
0x18000d679  jmp     short loc_18000D688
0x18000d67b  cmp     r14, rsi
0x18000d67e  jz      short loc_18000D685
0x18000d680  or      dword ptr [rdi], 0FFFFFFFFh
0x18000d683  jmp     short loc_18000D688
0x18000d685  add     [rdi], r14d
0x18000d688  mov     rbx, [rsp+38h+arg_0]
0x18000d68d  mov     rbp, [rsp+38h+arg_8]
0x18000d692  mov     rsi, [rsp+38h+arg_10]
0x18000d697  add     rsp, 20h
0x18000d69b  pop     r15
0x18000d69d  pop     r14
0x18000d69f  pop     rdi
0x18000d6a0  retn
```
