# PIXStrDup(ushort const *,ushort * *)

- ea: `0x180007b20`
- end: `0x180007c8d`
- name: `?PIXStrDup@@YAJPEBGPEAPEAG@Z`
- size: `365`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `9`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800044f0`
- `0x180006da4`
- `0x1800078cc`
- `0x18000b684`
- `0x1800111d0`
- `0x1800136c0`
- `0x18001f274`
- `0x18001f2c0`
- `0x18001f660`

## callees

- `0x180007b20`
- `0x1800169b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007c65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007c65`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180007b20  push    rbx
0x180007b22  push    rsi
0x180007b23  push    r14
0x180007b25  sub     rsp, 30h
0x180007b29  mov     r14, rdx
0x180007b2c  mov     rbx, rcx
0x180007b2f  test    rdx, rdx
0x180007b32  jz      loc_180007C52
0x180007b38  mov     [rsp+48h+arg_0], rbp
0x180007b3d  mov     [rsp+48h+arg_10], rdi
0x180007b42  mov     [rsp+48h+var_20], r12
0x180007b47  xor     r12d, r12d
0x180007b4a  mov     [rsp+48h+var_28], r15
0x180007b4f  mov     [rdx], r12
0x180007b52  test    rcx, rcx
0x180007b55  jz      loc_180007C60
0x180007b5b  cmp     [rcx], r12w
0x180007b5f  jz      loc_180007C60
0x180007b65  mov     r15d, r12d
0x180007b68  mov     ecx, 7FFFFFFFh
0x180007b6d  mov     rax, rbx
0x180007b70  cmp     [rax], r12w
0x180007b74  jz      short loc_180007B80
0x180007b76  add     rax, 2
0x180007b7a  sub     rcx, 1
0x180007b7e  jnz     short loc_180007B70
0x180007b80  mov     esi, 80070057h
0x180007b85  test    rcx, rcx
0x180007b88  mov     edx, esi
0x180007b8a  cmovnz  edx, r12d
0x180007b8e  jz      loc_180007C83
0x180007b94  mov     edi, 80000000h
0x180007b99  mov     eax, 2
0x180007b9e  sub     rdi, rcx
0x180007ba1  mul     rdi
0x180007ba4  mov     rbp, rax
0x180007ba7  test    rdx, rdx
0x180007baa  jnz     loc_180007C4B
0x180007bb0  mov     rcx, rax; cb
0x180007bb3  call    cs:__imp_CoTaskMemAlloc
0x180007bb9  mov     r15, rax
0x180007bbc  test    rax, rax
0x180007bbf  jz      loc_180007C7C
0x180007bc5  mov     r8, rbp; Size
0x180007bc8  xor     edx, edx; Val
0x180007bca  mov     rcx, rax; void *
0x180007bcd  call    memset_0
0x180007bd2  test    rdi, rdi
0x180007bd5  jz      short loc_180007C29
0x180007bd7  cmp     rdi, 7FFFFFFFh
0x180007bde  ja      loc_180007C87
0x180007be4  mov     eax, 7FFFFFFEh
0x180007be9  mov     rdx, r15
0x180007bec  nop     dword ptr [rax+00h]
0x180007bf0  test    rax, rax
0x180007bf3  jz      short loc_180007C11
0x180007bf5  movzx   ecx, word ptr [rbx]
0x180007bf8  test    cx, cx
0x180007bfb  jz      short loc_180007C11
0x180007bfd  mov     [rdx], cx
0x180007c00  add     rbx, 2
0x180007c04  add     rdx, 2
0x180007c08  dec     rax
0x180007c0b  sub     rdi, 1
0x180007c0f  jnz     short loc_180007BF0
0x180007c11  test    rdi, rdi
0x180007c14  lea     rcx, [rdx-2]
0x180007c18  mov     esi, 8007007Ah
0x180007c1d  cmovnz  rcx, rdx
0x180007c21  cmovnz  esi, r12d
0x180007c25  mov     [rcx], r12w
0x180007c29  mov     r12, [rsp+48h+var_20]
0x180007c2e  mov     eax, esi
0x180007c30  mov     rdi, [rsp+48h+arg_10]
0x180007c35  mov     rbp, [rsp+48h+arg_0]
0x180007c3a  mov     [r14], r15
0x180007c3d  mov     r15, [rsp+48h+var_28]
0x180007c42  add     rsp, 30h
0x180007c46  pop     r14
0x180007c48  pop     rsi
0x180007c49  pop     rbx
0x180007c4a  retn
0x180007c4b  mov     esi, 80070216h
0x180007c50  jmp     short loc_180007C29
0x180007c52  mov     eax, 80070057h
0x180007c57  add     rsp, 30h
0x180007c5b  pop     r14
0x180007c5d  pop     rsi
0x180007c5e  pop     rbx
0x180007c5f  retn
0x180007c60  mov     ecx, 2; cb
0x180007c65  call    cs:__imp_CoTaskMemAlloc
0x180007c6b  mov     r15, rax
0x180007c6e  test    rax, rax
0x180007c71  jz      short loc_180007C7C
0x180007c73  mov     [rax], r12w
0x180007c77  mov     esi, r12d
0x180007c7a  jmp     short loc_180007C29
0x180007c7c  mov     esi, 8007000Eh
0x180007c81  jmp     short loc_180007C29
0x180007c83  mov     esi, edx
0x180007c85  jmp     short loc_180007C29
0x180007c87  mov     [r15], r12w
0x180007c8b  jmp     short loc_180007C29
```
