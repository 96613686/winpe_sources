# __acrt_fp_strflt_to_string

- ea: `0x140018a64`
- end: `0x140018b74`
- name: `__acrt_fp_strflt_to_string`
- size: `272`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, int, int, __crt_cached_ptd_host *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400149e4`
- `0x140014ccc`
- `0x140014ef4`

## callees

- `0x14000bea4`
- `0x140018994`
- `0x140018a64`
- `0x140025080`

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
0x140018a64  mov     [rsp+arg_0], rbx
0x140018a69  mov     [rsp+arg_8], rbp
0x140018a6e  mov     [rsp+arg_10], rsi
0x140018a73  push    rdi
0x140018a74  sub     rsp, 30h
0x140018a78  mov     rdi, r9
0x140018a7b  mov     rsi, rcx
0x140018a7e  test    rcx, rcx
0x140018a81  jnz     short loc_140018AB5
0x140018a83  mov     ebx, 16h
0x140018a88  mov     rax, [rsp+38h+arg_30]
0x140018a8d  xor     r9d, r9d; LineNo
0x140018a90  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x140018a95  xor     r8d, r8d; FileName
0x140018a98  and     [rsp+38h+var_18], 0
0x140018a9e  xor     edx, edx; FunctionName
0x140018aa0  xor     ecx, ecx; Expression
0x140018aa2  mov     [rax+2Ch], ebx
0x140018aa5  mov     byte ptr [rax+30h], 1
0x140018aa9  call    _invalid_parameter_internal
0x140018aae  mov     eax, ebx
0x140018ab0  jmp     loc_140018B5F
0x140018ab5  test    rdx, rdx
0x140018ab8  jz      short loc_140018A83
0x140018aba  xor     eax, eax
0x140018abc  mov     byte ptr [rcx], 0
0x140018abf  test    r8d, r8d
0x140018ac2  cmovg   eax, r8d
0x140018ac6  inc     eax
0x140018ac8  cdqe
0x140018aca  cmp     rdx, rax
0x140018acd  ja      short loc_140018AD6
0x140018acf  mov     ebx, 22h ; '"'
0x140018ad4  jmp     short loc_140018A88
0x140018ad6  test    rdi, rdi
0x140018ad9  jz      short loc_140018A83
0x140018adb  mov     rcx, [r9+8]
0x140018adf  lea     rbx, [rsi+1]
0x140018ae3  mov     rdx, rcx
0x140018ae6  mov     byte ptr [rsi], 30h ; '0'
0x140018ae9  jmp     short loc_140018B00
0x140018aeb  mov     al, [rdx]
0x140018aed  test    al, al
0x140018aef  jz      short loc_140018AF6
0x140018af1  inc     rdx
0x140018af4  jmp     short loc_140018AF8
0x140018af6  mov     al, 30h ; '0'
0x140018af8  mov     [rbx], al
0x140018afa  inc     rbx
0x140018afd  dec     r8d
0x140018b00  test    r8d, r8d
0x140018b03  jg      short loc_140018AEB
0x140018b05  mov     byte ptr [rbx], 0
0x140018b08  js      short loc_140018B35
0x140018b0a  mov     eax, [rsp+38h+arg_28]
0x140018b0e  mov     r9d, [rsp+38h+arg_20]
0x140018b13  mov     r8d, [rdi]
0x140018b16  mov     dword ptr [rsp+38h+var_18], eax
0x140018b1a  call    should_round_up_0
0x140018b1f  test    al, al
0x140018b21  jz      short loc_140018B35
0x140018b23  jmp     short loc_140018B28
0x140018b25  mov     byte ptr [rbx], 30h ; '0'
0x140018b28  dec     rbx
0x140018b2b  mov     al, [rbx]
0x140018b2d  cmp     al, 39h ; '9'
0x140018b2f  jz      short loc_140018B25
0x140018b31  inc     al
0x140018b33  mov     [rbx], al
0x140018b35  cmp     byte ptr [rsi], 31h ; '1'
0x140018b38  jnz     short loc_140018B3F
0x140018b3a  inc     dword ptr [rdi+4]
0x140018b3d  jmp     short loc_140018B5D
0x140018b3f  or      r8, 0FFFFFFFFFFFFFFFFh
0x140018b43  inc     r8
0x140018b46  cmp     byte ptr [r8+rsi+1], 0
0x140018b4c  jnz     short loc_140018B43
0x140018b4e  inc     r8; Size
0x140018b51  lea     rdx, [rsi+1]; Src
0x140018b55  mov     rcx, rsi; void *
0x140018b58  call    memmove
0x140018b5d  xor     eax, eax
0x140018b5f  mov     rbx, [rsp+38h+arg_0]
0x140018b64  mov     rbp, [rsp+38h+arg_8]
0x140018b69  mov     rsi, [rsp+38h+arg_10]
0x140018b6e  add     rsp, 30h
0x140018b72  pop     rdi
0x140018b73  retn
```
