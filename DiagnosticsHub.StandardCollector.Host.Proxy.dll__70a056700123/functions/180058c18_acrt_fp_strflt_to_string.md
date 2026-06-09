# __acrt_fp_strflt_to_string

- ea: `0x180058c18`
- end: `0x180058d28`
- name: `__acrt_fp_strflt_to_string`
- size: `272`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, int, int, __crt_cached_ptd_host *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800572c8`
- `0x1800575b0`
- `0x1800577d8`

## callees

- `0x1800073e8`
- `0x180058b48`
- `0x180058c18`
- `0x180060630`

## pseudocode

```c
__int64 __fastcall _acrt_fp_strflt_to_string(
        char *a1,
        unsigned __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        __crt_cached_ptd_host *a7)
{
  unsigned int v9; // ebx
  int v11; // eax
  char *v12; // rcx
  char *v13; // rbx
  char *v14; // rdx
  char v15; // al
  __int64 v16; // r8

  if ( !a1 || !a2 )
    goto LABEL_2;
  v11 = 0;
  *a1 = 0;
  if ( a3 > 0 )
    v11 = a3;
  if ( a2 <= v11 + 1 )
  {
    v9 = 34;
    goto LABEL_3;
  }
  if ( !a4 )
  {
LABEL_2:
    v9 = 22;
LABEL_3:
    *((_DWORD *)a7 + 11) = v9;
    *((_BYTE *)a7 + 48) = 1;
    invalid_parameter_internal(0, 0, 0, 0, 0, a7);
    return v9;
  }
  v12 = *(char **)(a4 + 8);
  v13 = a1 + 1;
  v14 = v12;
  *a1 = 48;
  while ( a3 > 0 )
  {
    v15 = *v14;
    if ( *v14 )
      ++v14;
    else
      v15 = 48;
    *v13++ = v15;
    --a3;
  }
  *v13 = 0;
  if ( a3 >= 0 && (unsigned __int8)should_round_up_0((_DWORD)v12, (_DWORD)v14, *(_DWORD *)a4, a5, a6) )
  {
    while ( *--v13 == 57 )
      *v13 = 48;
    ++*v13;
  }
  if ( *a1 == 49 )
  {
    ++*(_DWORD *)(a4 + 4);
  }
  else
  {
    v16 = -1;
    do
      ++v16;
    while ( a1[v16 + 1] );
    memmove(a1, a1 + 1, v16 + 1);
  }
  return 0;
}

```

## disassembly

```asm
0x180058c18  mov     [rsp+arg_0], rbx
0x180058c1d  mov     [rsp+arg_8], rbp
0x180058c22  mov     [rsp+arg_10], rsi
0x180058c27  push    rdi
0x180058c28  sub     rsp, 30h
0x180058c2c  mov     rdi, r9
0x180058c2f  mov     rsi, rcx
0x180058c32  test    rcx, rcx
0x180058c35  jnz     short loc_180058C69
0x180058c37  mov     ebx, 16h
0x180058c3c  mov     rax, [rsp+38h+arg_30]
0x180058c41  xor     r9d, r9d; LineNo
0x180058c44  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x180058c49  xor     r8d, r8d; FileName
0x180058c4c  and     [rsp+38h+var_18], 0
0x180058c52  xor     edx, edx; FunctionName
0x180058c54  xor     ecx, ecx; Expression
0x180058c56  mov     [rax+2Ch], ebx
0x180058c59  mov     byte ptr [rax+30h], 1
0x180058c5d  call    _invalid_parameter_internal
0x180058c62  mov     eax, ebx
0x180058c64  jmp     loc_180058D13
0x180058c69  test    rdx, rdx
0x180058c6c  jz      short loc_180058C37
0x180058c6e  xor     eax, eax
0x180058c70  mov     byte ptr [rcx], 0
0x180058c73  test    r8d, r8d
0x180058c76  cmovg   eax, r8d
0x180058c7a  inc     eax
0x180058c7c  cdqe
0x180058c7e  cmp     rdx, rax
0x180058c81  ja      short loc_180058C8A
0x180058c83  mov     ebx, 22h ; '"'
0x180058c88  jmp     short loc_180058C3C
0x180058c8a  test    rdi, rdi
0x180058c8d  jz      short loc_180058C37
0x180058c8f  mov     rcx, [r9+8]
0x180058c93  lea     rbx, [rsi+1]
0x180058c97  mov     rdx, rcx
0x180058c9a  mov     byte ptr [rsi], 30h ; '0'
0x180058c9d  jmp     short loc_180058CB4
0x180058c9f  mov     al, [rdx]
0x180058ca1  test    al, al
0x180058ca3  jz      short loc_180058CAA
0x180058ca5  inc     rdx
0x180058ca8  jmp     short loc_180058CAC
0x180058caa  mov     al, 30h ; '0'
0x180058cac  mov     [rbx], al
0x180058cae  inc     rbx
0x180058cb1  dec     r8d
0x180058cb4  test    r8d, r8d
0x180058cb7  jg      short loc_180058C9F
0x180058cb9  mov     byte ptr [rbx], 0
0x180058cbc  js      short loc_180058CE9
0x180058cbe  mov     eax, [rsp+38h+arg_28]
0x180058cc2  mov     r9d, [rsp+38h+arg_20]
0x180058cc7  mov     r8d, [rdi]
0x180058cca  mov     dword ptr [rsp+38h+var_18], eax
0x180058cce  call    should_round_up_0
0x180058cd3  test    al, al
0x180058cd5  jz      short loc_180058CE9
0x180058cd7  jmp     short loc_180058CDC
0x180058cd9  mov     byte ptr [rbx], 30h ; '0'
0x180058cdc  dec     rbx
0x180058cdf  mov     al, [rbx]
0x180058ce1  cmp     al, 39h ; '9'
0x180058ce3  jz      short loc_180058CD9
0x180058ce5  inc     al
0x180058ce7  mov     [rbx], al
0x180058ce9  cmp     byte ptr [rsi], 31h ; '1'
0x180058cec  jnz     short loc_180058CF3
0x180058cee  inc     dword ptr [rdi+4]
0x180058cf1  jmp     short loc_180058D11
0x180058cf3  or      r8, 0FFFFFFFFFFFFFFFFh
0x180058cf7  inc     r8
0x180058cfa  cmp     byte ptr [r8+rsi+1], 0
0x180058d00  jnz     short loc_180058CF7
0x180058d02  inc     r8; Size
0x180058d05  lea     rdx, [rsi+1]; Src
0x180058d09  mov     rcx, rsi; void *
0x180058d0c  call    memmove
0x180058d11  xor     eax, eax
0x180058d13  mov     rbx, [rsp+38h+arg_0]
0x180058d18  mov     rbp, [rsp+38h+arg_8]
0x180058d1d  mov     rsi, [rsp+38h+arg_10]
0x180058d22  add     rsp, 30h
0x180058d26  pop     rdi
0x180058d27  retn
```
