# __acrt_fp_strflt_to_string

- ea: `0x14007beb8`
- end: `0x14007bfc8`
- name: `__acrt_fp_strflt_to_string`
- size: `272`
- prototype: `__int64 __fastcall(_BYTE *, unsigned __int64, int, unsigned int *, unsigned int, int, __crt_cached_ptd_host *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400727ac`
- `0x140072a94`
- `0x140072cbc`

## callees

- `0x14006147c`
- `0x14007bde8`
- `0x14007beb8`
- `0x14007fc30`

## pseudocode

```c
__int64 __fastcall _acrt_fp_strflt_to_string(
        _BYTE *a1,
        unsigned __int64 a2,
        int a3,
        unsigned int *a4,
        unsigned int a5,
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
    sub_14006147C(0, 0, 0, 0, 0, a7);
    return v9;
  }
  v12 = (char *)*((_QWORD *)a4 + 1);
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
  if ( a3 >= 0 && (unsigned __int8)should_round_up(v12, v14, *a4, a5, a6) )
  {
    while ( *--v13 == 57 )
      *v13 = 48;
    ++*v13;
  }
  if ( *a1 == 49 )
  {
    ++a4[1];
  }
  else
  {
    v16 = -1;
    do
      ++v16;
    while ( a1[v16 + 1] );
    sub_14007FC30(a1, a1 + 1, v16 + 1);
  }
  return 0;
}

```

## disassembly

```asm
0x14007beb8  mov     [rsp+arg_0], rbx
0x14007bebd  mov     [rsp+arg_8], rbp
0x14007bec2  mov     [rsp+arg_10], rsi
0x14007bec7  push    rdi
0x14007bec8  sub     rsp, 30h
0x14007becc  mov     rdi, r9
0x14007becf  mov     rsi, rcx
0x14007bed2  test    rcx, rcx
0x14007bed5  jnz     short loc_14007BF09
0x14007bed7  mov     ebx, 16h
0x14007bedc  mov     rax, [rsp+38h+arg_30]
0x14007bee1  xor     r9d, r9d; LineNo
0x14007bee4  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x14007bee9  xor     r8d, r8d; FileName
0x14007beec  and     [rsp+38h+var_18], 0
0x14007bef2  xor     edx, edx; FunctionName
0x14007bef4  xor     ecx, ecx; Expression
0x14007bef6  mov     [rax+2Ch], ebx
0x14007bef9  mov     byte ptr [rax+30h], 1
0x14007befd  call    sub_14006147C
0x14007bf02  mov     eax, ebx
0x14007bf04  jmp     loc_14007BFB3
0x14007bf09  test    rdx, rdx
0x14007bf0c  jz      short loc_14007BED7
0x14007bf0e  xor     eax, eax
0x14007bf10  mov     byte ptr [rcx], 0
0x14007bf13  test    r8d, r8d
0x14007bf16  cmovg   eax, r8d
0x14007bf1a  inc     eax
0x14007bf1c  cdqe
0x14007bf1e  cmp     rdx, rax
0x14007bf21  ja      short loc_14007BF2A
0x14007bf23  mov     ebx, 22h ; '"'
0x14007bf28  jmp     short loc_14007BEDC
0x14007bf2a  test    rdi, rdi
0x14007bf2d  jz      short loc_14007BED7
0x14007bf2f  mov     rcx, [r9+8]
0x14007bf33  lea     rbx, [rsi+1]
0x14007bf37  mov     rdx, rcx
0x14007bf3a  mov     byte ptr [rsi], 30h ; '0'
0x14007bf3d  jmp     short loc_14007BF54
0x14007bf3f  mov     al, [rdx]
0x14007bf41  test    al, al
0x14007bf43  jz      short loc_14007BF4A
0x14007bf45  inc     rdx
0x14007bf48  jmp     short loc_14007BF4C
0x14007bf4a  mov     al, 30h ; '0'
0x14007bf4c  mov     [rbx], al
0x14007bf4e  inc     rbx
0x14007bf51  dec     r8d
0x14007bf54  test    r8d, r8d
0x14007bf57  jg      short loc_14007BF3F
0x14007bf59  mov     byte ptr [rbx], 0
0x14007bf5c  js      short loc_14007BF89
0x14007bf5e  mov     eax, [rsp+38h+arg_28]
0x14007bf62  mov     r9d, [rsp+38h+arg_20]
0x14007bf67  mov     r8d, [rdi]
0x14007bf6a  mov     dword ptr [rsp+38h+var_18], eax
0x14007bf6e  call    ?should_round_up@@YA_NQEBD0HW4__acrt_has_trailing_digits@@W4__acrt_rounding_mode@@@Z
0x14007bf73  test    al, al
0x14007bf75  jz      short loc_14007BF89
0x14007bf77  jmp     short loc_14007BF7C
0x14007bf79  mov     byte ptr [rbx], 30h ; '0'
0x14007bf7c  dec     rbx
0x14007bf7f  mov     al, [rbx]
0x14007bf81  cmp     al, 39h ; '9'
0x14007bf83  jz      short loc_14007BF79
0x14007bf85  inc     al
0x14007bf87  mov     [rbx], al
0x14007bf89  cmp     byte ptr [rsi], 31h ; '1'
0x14007bf8c  jnz     short loc_14007BF93
0x14007bf8e  inc     dword ptr [rdi+4]
0x14007bf91  jmp     short loc_14007BFB1
0x14007bf93  or      r8, 0FFFFFFFFFFFFFFFFh
0x14007bf97  inc     r8
0x14007bf9a  cmp     byte ptr [r8+rsi+1], 0
0x14007bfa0  jnz     short loc_14007BF97
0x14007bfa2  inc     r8
0x14007bfa5  lea     rdx, [rsi+1]
0x14007bfa9  mov     rcx, rsi
0x14007bfac  call    sub_14007FC30
0x14007bfb1  xor     eax, eax
0x14007bfb3  mov     rbx, [rsp+38h+arg_0]
0x14007bfb8  mov     rbp, [rsp+38h+arg_8]
0x14007bfbd  mov     rsi, [rsp+38h+arg_10]
0x14007bfc2  add     rsp, 30h
0x14007bfc6  pop     rdi
0x14007bfc7  retn
```
