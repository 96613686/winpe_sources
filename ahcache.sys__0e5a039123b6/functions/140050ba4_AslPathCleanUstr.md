# AslPathCleanUstr

- ea: `0x140050ba4`
- end: `0x140050e8e`
- name: `AslPathCleanUstr`
- size: `746`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14005ac18`

## callees

- `0x14000448d`
- `0x1400079c8`
- `0x14003e364`
- `0x140050ba4`

## string_xrefs

- `0x140050e58`: `AslpPathGetFormatInfo failed [%x]`
- `0x140050e3e`: `AslPathCleanUstr`
- `0x140050e69`: `AslPathCleanUstr`
- `0x140050e31`: `AslPathCleanUstr failed with source pointer behind destination pointer.`

## pseudocode

```c
__int64 __fastcall AslPathCleanUstr(unsigned __int16 *a1)
{
  int v2; // r14d
  const wchar_t *v3; // rcx
  int v4; // ebx
  const wchar_t *v5; // rbp
  unsigned __int16 v6; // r11
  unsigned __int64 v7; // rcx
  __int16 v8; // dx
  unsigned __int16 v9; // r9
  unsigned __int16 v10; // r10
  __int64 v11; // rcx
  __int16 v12; // dx
  __int16 v13; // ax
  __int16 v14; // ax
  __int16 v15; // dx
  __int64 v16; // rdx
  __int16 v17; // cx
  __int64 v18; // rdx
  __int16 v19; // cx
  unsigned __int16 v20; // ax
  __int64 v21; // rax
  unsigned int v22; // ebx

  v2 = *a1 >> 1;
  if ( *a1 < 2u || (v3 = (const wchar_t *)*((_QWORD *)a1 + 1), !*v3) )
  {
    v22 = -1073741582;
    AslLogCallPrintf(1, "AslPathCleanUstr", 730, "AslpPathGetFormatInfo failed [%x]", -1073741582);
    return v22;
  }
  if ( (unsigned __int16)v2 < 8u || wcsnicmp_0(v3, L"\\??\\UNC\\", 8u) )
  {
    v4 = 4;
    if ( (unsigned __int16)v2 >= 4u )
    {
      v5 = (const wchar_t *)*((_QWORD *)a1 + 1);
      if ( !wcsncmp_0(v5, L"\\??\\", 4u) )
      {
        v4 = 3;
        goto LABEL_14;
      }
      if ( !wcsncmp_0(v5, L"\\\\?\\", 4u) || !wcsncmp_0(v5, L"\\\\.\\", 4u) )
        goto LABEL_14;
    }
    if ( (unsigned __int16)v2 <= 2u || wcsncmp_0(*((const wchar_t **)a1 + 1), L"\\\\", 2u) )
      v4 = 1;
  }
  else
  {
    v4 = 5;
  }
LABEL_14:
  v6 = 0;
  do
  {
    v7 = 2LL * v6;
    if ( v7 >= *a1 )
      break;
    v8 = *(_WORD *)(v7 + *((_QWORD *)a1 + 1));
    if ( v8 == 92 || v8 == 47 )
      --v4;
    ++v6;
  }
  while ( v4 > 0 );
  v9 = v6;
  v10 = v6;
  if ( v6 >= (unsigned __int16)v2 )
  {
LABEL_54:
    v22 = 0;
    *(_WORD *)(*((_QWORD *)a1 + 1) + 2LL * v9) = 0;
    *a1 = 2 * v9;
  }
  else
  {
    while ( v10 >= v9 )
    {
      v11 = *((_QWORD *)a1 + 1);
      v12 = *(_WORD *)(v11 + 2LL * v10);
      if ( v12 == 92 || v12 == 47 )
      {
        if ( !v9 || *(_WORD *)(v11 + 2LL * v9 - 2) != 92 )
        {
          v21 = v9++;
          *(_WORD *)(v11 + 2 * v21) = 92;
        }
      }
      else if ( v12 == 46 )
      {
        if ( v10 + 1 == v2 )
          goto LABEL_54;
        v13 = *(_WORD *)(v11 + 2LL * v10 + 2);
        if ( v13 == 92 || v13 == 47 )
        {
          ++v10;
        }
        else if ( v13 == 46 )
        {
          if ( v10 + 2 == v2 || (v14 = *(_WORD *)(v11 + 2LL * v10 + 4), v14 == 92) || v14 == 47 )
          {
            while ( v9 >= v6 )
            {
              v16 = *((_QWORD *)a1 + 1);
              v17 = *(_WORD *)(v16 + 2LL * v9);
              *(_WORD *)(v16 + 2LL * v9) = 0;
              if ( v17 == 92 )
              {
                do
                {
                  v18 = *((_QWORD *)a1 + 1);
                  v19 = *(_WORD *)(v18 + 2LL * v9);
                  *(_WORD *)(v18 + 2LL * v9) = 0;
                  if ( v19 == 92 )
                    break;
                  --v9;
                }
                while ( v9 >= v6 );
                break;
              }
              --v9;
            }
            v20 = v9 + 1;
            ++v10;
            if ( v9 >= v6 )
              v20 = v9;
            v9 = v20;
          }
        }
      }
      else
      {
        while ( v10 < (unsigned __int16)v2 )
        {
          v15 = *(_WORD *)(v11 + 2LL * v10);
          if ( v15 == 92 || v15 == 47 )
            break;
          if ( v10 != v9 )
          {
            *(_WORD *)(v11 + 2LL * v9) = v15;
            v11 = *((_QWORD *)a1 + 1);
          }
          ++v9;
          ++v10;
        }
        --v10;
      }
      if ( ++v10 >= (unsigned __int16)v2 )
        goto LABEL_54;
    }
    AslLogCallPrintf(
      1,
      "AslPathCleanUstr",
      742,
      "AslPathCleanUstr failed with source pointer behind destination pointer.");
    return (unsigned int)-1073741595;
  }
  return v22;
}

```

## disassembly

```asm
0x140050ba4  push    rbx
0x140050ba6  push    rbp
0x140050ba7  push    rsi
0x140050ba8  push    rdi
0x140050ba9  push    r12
0x140050bab  push    r13
0x140050bad  push    r14
0x140050baf  push    r15
0x140050bb1  sub     rsp, 38h
0x140050bb5  movzx   edx, word ptr [rcx]
0x140050bb8  mov     r12d, 2
0x140050bbe  movzx   eax, dx
0x140050bc1  mov     rsi, rcx
0x140050bc4  shr     ax, 1
0x140050bc7  movzx   r14d, ax
0x140050bcb  cmp     dx, r12w
0x140050bcf  jb      loc_140050E53
0x140050bd5  mov     rcx, [rcx+8]; Str1
0x140050bd9  xor     r15d, r15d
0x140050bdc  cmp     [rcx], r15w
0x140050be0  jz      loc_140050E53
0x140050be6  lea     r8d, [r12+6]; MaxCount
0x140050beb  lea     edi, [r12-1]
0x140050bf0  cmp     r14w, r8w
0x140050bf4  jb      short loc_140050C0B
0x140050bf6  lea     rdx, aUnc; "\\??\\UNC\\"
0x140050bfd  call    _wcsnicmp_0
0x140050c02  test    eax, eax
0x140050c04  jnz     short loc_140050C0B
0x140050c06  lea     ebx, [rdi+4]
0x140050c09  jmp     short loc_140050C80
0x140050c0b  mov     ebx, 4
0x140050c10  cmp     r14w, bx
0x140050c14  jb      short loc_140050C61
0x140050c16  mov     rbp, [rsi+8]
0x140050c1a  lea     rdx, asc_14000EAD8; "\\??\\"
0x140050c21  mov     rcx, rbp; Str1
0x140050c24  mov     r8d, ebx; MaxCount
0x140050c27  call    wcsncmp_0
0x140050c2c  test    eax, eax
0x140050c2e  jnz     short loc_140050C35
0x140050c30  lea     ebx, [rax+3]
0x140050c33  jmp     short loc_140050C80
0x140050c35  mov     r8d, ebx; MaxCount
0x140050c38  lea     rdx, asc_1400177C8; "\\\\?\\"
0x140050c3f  mov     rcx, rbp; Str1
0x140050c42  call    wcsncmp_0
0x140050c47  test    eax, eax
0x140050c49  jz      short loc_140050C80
0x140050c4b  mov     r8d, ebx; MaxCount
0x140050c4e  lea     rdx, asc_1400177D8; "\\\\.\\"
0x140050c55  mov     rcx, rbp; Str1
0x140050c58  call    wcsncmp_0
0x140050c5d  test    eax, eax
0x140050c5f  jz      short loc_140050C80
0x140050c61  cmp     r14w, r12w
0x140050c65  jbe     short loc_140050C7E
0x140050c67  mov     rcx, [rsi+8]; Str1
0x140050c6b  lea     rdx, asc_1400177E4; "\\\\"
0x140050c72  mov     r8d, r12d; MaxCount
0x140050c75  call    wcsncmp_0
0x140050c7a  test    eax, eax
0x140050c7c  jz      short loc_140050C80
0x140050c7e  mov     ebx, edi
0x140050c80  movzx   r8d, word ptr [rsi]
0x140050c84  mov     r11d, r15d
0x140050c87  mov     ebp, 5Ch ; '\'
0x140050c8c  mov     r12w, 2Fh ; '/'
0x140050c91  movzx   eax, r11w
0x140050c95  lea     rcx, [rax+rax]
0x140050c99  cmp     rcx, r8
0x140050c9c  jnb     short loc_140050CBB
0x140050c9e  mov     rax, [rsi+8]
0x140050ca2  movzx   edx, word ptr [rcx+rax]
0x140050ca6  cmp     dx, bp
0x140050ca9  jz      short loc_140050CB1
0x140050cab  cmp     dx, r12w
0x140050caf  jnz     short loc_140050CB3
0x140050cb1  sub     ebx, edi
0x140050cb3  add     r11w, di
0x140050cb7  test    ebx, ebx
0x140050cb9  jg      short loc_140050C91
0x140050cbb  movzx   r9d, r11w
0x140050cbf  movzx   r10d, r11w
0x140050cc3  cmp     r11w, r14w
0x140050cc7  jnb     loc_140050E17
0x140050ccd  mov     r13d, 0FFFFh
0x140050cd3  cmp     r10w, r9w
0x140050cd7  jb      loc_140050E31
0x140050cdd  mov     rcx, [rsi+8]
0x140050ce1  movzx   eax, r10w
0x140050ce5  movzx   edx, word ptr [rcx+rax*2]
0x140050ce9  cmp     dx, bp
0x140050cec  jz      loc_140050DEC
0x140050cf2  cmp     dx, r12w
0x140050cf6  jz      loc_140050DEC
0x140050cfc  cmp     dx, 2Eh ; '.'
0x140050d00  jnz     short loc_140050D7F
0x140050d02  movzx   edx, r10w
0x140050d06  lea     eax, [rdx+1]
0x140050d09  cmp     eax, r14d
0x140050d0c  jz      loc_140050E17
0x140050d12  movzx   eax, word ptr [rcx+rdx*2+2]
0x140050d17  cmp     ax, bp
0x140050d1a  jz      loc_140050DE6
0x140050d20  cmp     ax, r12w
0x140050d24  jz      loc_140050DE6
0x140050d2a  cmp     ax, 2Eh ; '.'
0x140050d2e  jnz     loc_140050E09
0x140050d34  lea     eax, [rdx+2]
0x140050d37  cmp     eax, r14d
0x140050d3a  jz      short loc_140050DA6
0x140050d3c  movzx   eax, word ptr [rcx+rdx*2+4]
0x140050d41  cmp     ax, bp
0x140050d44  jz      short loc_140050DA6
0x140050d46  cmp     ax, r12w
0x140050d4a  jnz     loc_140050E09
0x140050d50  jmp     short loc_140050DA6
0x140050d52  movzx   eax, r10w
0x140050d56  movzx   edx, word ptr [rcx+rax*2]
0x140050d5a  cmp     dx, bp
0x140050d5d  jz      short loc_140050D85
0x140050d5f  cmp     dx, r12w
0x140050d63  jz      short loc_140050D85
0x140050d65  cmp     r10w, r9w
0x140050d69  jz      short loc_140050D77
0x140050d6b  movzx   eax, r9w
0x140050d6f  mov     [rcx+rax*2], dx
0x140050d73  mov     rcx, [rsi+8]
0x140050d77  add     r9w, di
0x140050d7b  add     r10w, di
0x140050d7f  cmp     r10w, r14w
0x140050d83  jb      short loc_140050D52
0x140050d85  add     r10w, r13w
0x140050d89  jmp     short loc_140050E09
0x140050d8b  mov     rdx, [rsi+8]
0x140050d8f  movzx   r8d, r9w
0x140050d93  movzx   ecx, word ptr [rdx+r8*2]
0x140050d98  mov     [rdx+r8*2], r15w
0x140050d9d  cmp     cx, bp
0x140050da0  jz      short loc_140050DAE
0x140050da2  add     r9w, r13w
0x140050da6  cmp     r9w, r11w
0x140050daa  jnb     short loc_140050D8B
0x140050dac  jmp     short loc_140050DCF
0x140050dae  mov     rdx, [rsi+8]
0x140050db2  movzx   r8d, r9w
0x140050db6  movzx   ecx, word ptr [rdx+r8*2]
0x140050dbb  mov     [rdx+r8*2], r15w
0x140050dc0  cmp     cx, bp
0x140050dc3  jz      short loc_140050DCF
0x140050dc5  add     r9w, r13w
0x140050dc9  cmp     r9w, r11w
0x140050dcd  jnb     short loc_140050DAE
0x140050dcf  lea     eax, [rdi+r9]
0x140050dd3  add     r10w, di
0x140050dd7  cmp     r9w, r11w
0x140050ddb  cmovnb  ax, r9w
0x140050de0  movzx   r9d, ax
0x140050de4  jmp     short loc_140050E09
0x140050de6  add     r10w, di
0x140050dea  jmp     short loc_140050E09
0x140050dec  test    r9w, r9w
0x140050df0  jz      short loc_140050DFD
0x140050df2  movzx   eax, r9w
0x140050df6  cmp     [rcx+rax*2-2], bp
0x140050dfb  jz      short loc_140050E09
0x140050dfd  movzx   eax, r9w
0x140050e01  add     r9w, di
0x140050e05  mov     [rcx+rax*2], bp
0x140050e09  add     r10w, di
0x140050e0d  cmp     r10w, r14w
0x140050e11  jb      loc_140050CD3
0x140050e17  mov     rcx, [rsi+8]
0x140050e1b  mov     ebx, r15d
0x140050e1e  movzx   edx, r9w
0x140050e22  add     r9w, r9w
0x140050e26  mov     [rcx+rdx*2], r15w
0x140050e2b  mov     [rsi], r9w
0x140050e2f  jmp     short loc_140050E7A
0x140050e31  lea     r9, aAslpathcleanus_1; "AslPathCleanUstr failed with source poi"...
0x140050e38  mov     r8d, 2E6h
0x140050e3e  lea     rdx, aAslpathcleanus_0; "AslPathCleanUstr"
0x140050e45  mov     ecx, edi
0x140050e47  call    AslLogCallPrintf
0x140050e4c  mov     ebx, 0C00000E5h
0x140050e51  jmp     short loc_140050E7A
0x140050e53  mov     ebx, 0C00000F2h
0x140050e58  lea     r9, aAslppathgetfor; "AslpPathGetFormatInfo failed [%x]"
0x140050e5f  mov     r8d, 2DAh
0x140050e65  mov     [rsp+78h+var_58], ebx
0x140050e69  lea     rdx, aAslpathcleanus_0; "AslPathCleanUstr"
0x140050e70  mov     ecx, 1
0x140050e75  call    AslLogCallPrintf
0x140050e7a  mov     eax, ebx
0x140050e7c  add     rsp, 38h
0x140050e80  pop     r15
0x140050e82  pop     r14
0x140050e84  pop     r13
0x140050e86  pop     r12
0x140050e88  pop     rdi
0x140050e89  pop     rsi
0x140050e8a  pop     rbp
0x140050e8b  pop     rbx
0x140050e8c  retn
```
