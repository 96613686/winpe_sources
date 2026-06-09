# CopyString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort * *)

- ea: `0x180007080`
- end: `0x18000712e`
- name: `?CopyString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAPEAG@Z`
- size: `174`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007dc0`
- `0x18000a7d0`
- `0x18000ace0`
- `0x18000af70`

## callees

- `0x180002138`
- `0x180007080`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180007114`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007114`
- `msvcrt!wcscpy_s` at `0x1800070f6`
- `msvcrt!wcscpy_s` at `0x1800070f6`

## pseudocode

```c
errno_t __fastcall CopyString(__int64 a1, void **a2)
{
  errno_t result; // eax
  __int64 v5; // rcx
  wchar_t *v6; // rax

  if ( !a2 )
    return -2147024809;
  v5 = *(_QWORD *)(a1 + 8);
  v6 = (wchar_t *)*a2;
  if ( *(_QWORD *)a1 == v5 )
  {
    if ( v6 )
    {
      operator delete[](*a2);
      *a2 = 0;
    }
    return 0;
  }
  if ( !v6 )
  {
    v6 = (wchar_t *)operator new[](saturated_mul(((v5 - *(_QWORD *)a1) >> 1) + 1, 2u));
    *a2 = v6;
    if ( !v6 )
      return -2147024888;
  }
  result = wcscpy_s(v6, ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 1) + 1, *(const wchar_t **)a1);
  if ( !result )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180007080  mov     [rsp+arg_0], rbx
0x180007085  push    rdi
0x180007086  sub     rsp, 20h
0x18000708a  mov     rbx, rdx
0x18000708d  mov     rdi, rcx
0x180007090  test    rdx, rdx
0x180007093  jnz     short loc_18000709F
0x180007095  mov     eax, 80070057h
0x18000709a  jmp     loc_180007123
0x18000709f  mov     rcx, [rcx+8]
0x1800070a3  mov     rax, [rdx]
0x1800070a6  cmp     [rdi], rcx
0x1800070a9  jz      short loc_18000710C
0x1800070ab  test    rax, rax
0x1800070ae  jnz     short loc_1800070E3
0x1800070b0  sub     rcx, [rdi]
0x1800070b3  mov     eax, 2
0x1800070b8  sar     rcx, 1
0x1800070bb  inc     rcx
0x1800070be  mul     rcx
0x1800070c1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800070c8  cmovb   rax, rcx
0x1800070cc  mov     rcx, rax; unsigned __int64
0x1800070cf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800070d4  mov     [rbx], rax
0x1800070d7  test    rax, rax
0x1800070da  jnz     short loc_1800070E3
0x1800070dc  mov     eax, 80070008h
0x1800070e1  jmp     short loc_180007123
0x1800070e3  mov     rdx, [rdi+8]
0x1800070e7  mov     rcx, rax; Destination
0x1800070ea  sub     rdx, [rdi]
0x1800070ed  mov     r8, [rdi]; Source
0x1800070f0  sar     rdx, 1
0x1800070f3  inc     rdx; SizeInWords
0x1800070f6  call    cs:__imp_wcscpy_s
0x1800070fc  test    eax, eax
0x1800070fe  jz      short loc_180007121
0x180007100  jle     short loc_180007123
0x180007102  movzx   eax, ax
0x180007105  or      eax, 80070000h
0x18000710a  jmp     short loc_180007123
0x18000710c  test    rax, rax
0x18000710f  jz      short loc_180007121
0x180007111  mov     rcx, rax
0x180007114  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000711a  mov     qword ptr [rbx], 0
0x180007121  xor     eax, eax
0x180007123  mov     rbx, [rsp+28h+arg_0]
0x180007128  add     rsp, 20h
0x18000712c  pop     rdi
0x18000712d  retn
```
