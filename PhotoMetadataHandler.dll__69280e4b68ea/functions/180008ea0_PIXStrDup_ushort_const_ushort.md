# PIXStrDup(ushort const *,ushort * *)

- ea: `0x180008ea0`
- end: `0x180009017`
- name: `?PIXStrDup@@YAJPEBGPEAPEAG@Z`
- size: `375`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `9`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004540`
- `0x180008098`
- `0x180008c28`
- `0x18000bbe8`
- `0x180011990`
- `0x18001405c`
- `0x18002019c`
- `0x1800201e8`
- `0x1800205a8`

## callees

- `0x180008ea0`
- `0x180017408`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008f33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008fe9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008f33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008fe9`

## pseudocode

```c
__int64 __fastcall PIXStrDup(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  const unsigned __int16 *v3; // rbx
  unsigned __int16 *v4; // r15
  __int64 v5; // rcx
  const unsigned __int16 *v6; // rax
  unsigned int v7; // esi
  unsigned __int64 v8; // rdi
  size_t v9; // rbp
  unsigned __int16 *v10; // rax
  __int64 v11; // rax
  unsigned __int16 *v12; // rdx
  unsigned __int16 *v13; // rcx
  __int64 result; // rax
  unsigned __int16 *v15; // rax

  v3 = a1;
  if ( a2 )
  {
    *a2 = 0;
    if ( a1 && *a1 )
    {
      v4 = 0;
      v5 = 0x7FFFFFFF;
      v6 = v3;
      do
      {
        if ( !*v6 )
          break;
        ++v6;
        --v5;
      }
      while ( v5 );
      v7 = -2147024809;
      if ( !v5 )
      {
        v7 = -2147024809;
        goto LABEL_19;
      }
      v8 = 0x80000000LL - v5;
      v9 = 2 * (0x80000000LL - v5);
      if ( is_mul_ok(0x80000000LL - v5, 2u) )
      {
        v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * (0x80000000LL - v5));
        v4 = v10;
        if ( v10 )
        {
          memset_0(v10, 0, v9);
          if ( v8 )
          {
            if ( v8 > 0x7FFFFFFF )
            {
              *v4 = 0;
            }
            else
            {
              v11 = 2147483646;
              v12 = v4;
              do
              {
                if ( !v11 )
                  break;
                if ( !*v3 )
                  break;
                *v12++ = *v3++;
                --v11;
                --v8;
              }
              while ( v8 );
              v13 = v12 - 1;
              v7 = -2147024774;
              if ( v8 )
              {
                v13 = v12;
                v7 = 0;
              }
              *v13 = 0;
            }
          }
          goto LABEL_19;
        }
        goto LABEL_24;
      }
      v7 = -2147024362;
    }
    else
    {
      v15 = (unsigned __int16 *)CoTaskMemAlloc(2u);
      v4 = v15;
      if ( !v15 )
      {
LABEL_24:
        v7 = -2147024882;
        goto LABEL_19;
      }
      *v15 = 0;
      v7 = 0;
    }
LABEL_19:
    result = v7;
    *a2 = v4;
    return result;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180008ea0  push    rbx
0x180008ea2  push    rsi
0x180008ea3  push    r14
0x180008ea5  sub     rsp, 30h
0x180008ea9  mov     r14, rdx
0x180008eac  mov     rbx, rcx
0x180008eaf  test    rdx, rdx
0x180008eb2  jz      loc_180008FD5
0x180008eb8  mov     [rsp+48h+arg_0], rbp
0x180008ebd  mov     [rsp+48h+arg_10], rdi
0x180008ec2  mov     [rsp+48h+var_20], r12
0x180008ec7  xor     r12d, r12d
0x180008eca  mov     [rsp+48h+var_28], r15
0x180008ecf  mov     [rdx], r12
0x180008ed2  test    rcx, rcx
0x180008ed5  jz      loc_180008FE4
0x180008edb  cmp     [rcx], r12w
0x180008edf  jz      loc_180008FE4
0x180008ee5  mov     r15d, r12d
0x180008ee8  mov     ecx, 7FFFFFFFh
0x180008eed  mov     rax, rbx
0x180008ef0  cmp     [rax], r12w
0x180008ef4  jz      short loc_180008F00
0x180008ef6  add     rax, 2
0x180008efa  sub     rcx, 1
0x180008efe  jnz     short loc_180008EF0
0x180008f00  mov     esi, 80070057h
0x180008f05  test    rcx, rcx
0x180008f08  mov     edx, esi
0x180008f0a  cmovnz  edx, r12d
0x180008f0e  jz      loc_18000900D
0x180008f14  mov     edi, 80000000h
0x180008f19  mov     eax, 2
0x180008f1e  sub     rdi, rcx
0x180008f21  mul     rdi
0x180008f24  mov     rbp, rax
0x180008f27  test    rdx, rdx
0x180008f2a  jnz     loc_180008FCE
0x180008f30  mov     rcx, rax; cb
0x180008f33  call    cs:__imp_CoTaskMemAlloc
0x180008f3a  nop     dword ptr [rax+rax+00h]
0x180008f3f  mov     r15, rax
0x180008f42  test    rax, rax
0x180008f45  jz      loc_180009006
0x180008f4b  mov     r8, rbp; Size
0x180008f4e  xor     edx, edx; Val
0x180008f50  mov     rcx, rax; void *
0x180008f53  call    memset_0
0x180008f58  test    rdi, rdi
0x180008f5b  jz      short loc_180008FAB
0x180008f5d  cmp     rdi, 7FFFFFFFh
0x180008f64  ja      loc_180009011
0x180008f6a  mov     eax, 7FFFFFFEh
0x180008f6f  mov     rdx, r15
0x180008f72  test    rax, rax
0x180008f75  jz      short loc_180008F93
0x180008f77  movzx   ecx, word ptr [rbx]
0x180008f7a  test    cx, cx
0x180008f7d  jz      short loc_180008F93
0x180008f7f  mov     [rdx], cx
0x180008f82  add     rbx, 2
0x180008f86  add     rdx, 2
0x180008f8a  dec     rax
0x180008f8d  sub     rdi, 1
0x180008f91  jnz     short loc_180008F72
0x180008f93  test    rdi, rdi
0x180008f96  lea     rcx, [rdx-2]
0x180008f9a  mov     esi, 8007007Ah
0x180008f9f  cmovnz  rcx, rdx
0x180008fa3  cmovnz  esi, r12d
0x180008fa7  mov     [rcx], r12w
0x180008fab  mov     r12, [rsp+48h+var_20]
0x180008fb0  mov     eax, esi
0x180008fb2  mov     rdi, [rsp+48h+arg_10]
0x180008fb7  mov     rbp, [rsp+48h+arg_0]
0x180008fbc  mov     [r14], r15
0x180008fbf  mov     r15, [rsp+48h+var_28]
0x180008fc4  add     rsp, 30h
0x180008fc8  pop     r14
0x180008fca  pop     rsi
0x180008fcb  pop     rbx
0x180008fcc  retn
0x180008fce  mov     esi, 80070216h
0x180008fd3  jmp     short loc_180008FAB
0x180008fd5  mov     eax, 80070057h
0x180008fda  add     rsp, 30h
0x180008fde  pop     r14
0x180008fe0  pop     rsi
0x180008fe1  pop     rbx
0x180008fe2  retn
0x180008fe4  mov     ecx, 2; cb
0x180008fe9  call    cs:__imp_CoTaskMemAlloc
0x180008ff0  nop     dword ptr [rax+rax+00h]
0x180008ff5  mov     r15, rax
0x180008ff8  test    rax, rax
0x180008ffb  jz      short loc_180009006
0x180008ffd  mov     [rax], r12w
0x180009001  mov     esi, r12d
0x180009004  jmp     short loc_180008FAB
0x180009006  mov     esi, 8007000Eh
0x18000900b  jmp     short loc_180008FAB
0x18000900d  mov     esi, edx
0x18000900f  jmp     short loc_180008FAB
0x180009011  mov     [r15], r12w
0x180009015  jmp     short loc_180008FAB
```
