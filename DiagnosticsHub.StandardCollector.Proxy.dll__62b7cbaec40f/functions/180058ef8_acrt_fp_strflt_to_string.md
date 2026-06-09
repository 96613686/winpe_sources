# __acrt_fp_strflt_to_string

- ea: `0x180058ef8`
- end: `0x180059008`
- name: `__acrt_fp_strflt_to_string`
- size: `272`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, int, int, __crt_cached_ptd_host *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800575a8`
- `0x180057890`
- `0x180057ab8`

## callees

- `0x180007b48`
- `0x180058e28`
- `0x180058ef8`
- `0x180060910`

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
0x180058ef8  mov     [rsp+arg_0], rbx
0x180058efd  mov     [rsp+arg_8], rbp
0x180058f02  mov     [rsp+arg_10], rsi
0x180058f07  push    rdi
0x180058f08  sub     rsp, 30h
0x180058f0c  mov     rdi, r9
0x180058f0f  mov     rsi, rcx
0x180058f12  test    rcx, rcx
0x180058f15  jnz     short loc_180058F49
0x180058f17  mov     ebx, 16h
0x180058f1c  mov     rax, [rsp+38h+arg_30]
0x180058f21  xor     r9d, r9d; LineNo
0x180058f24  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x180058f29  xor     r8d, r8d; FileName
0x180058f2c  and     [rsp+38h+var_18], 0
0x180058f32  xor     edx, edx; FunctionName
0x180058f34  xor     ecx, ecx; Expression
0x180058f36  mov     [rax+2Ch], ebx
0x180058f39  mov     byte ptr [rax+30h], 1
0x180058f3d  call    _invalid_parameter_internal
0x180058f42  mov     eax, ebx
0x180058f44  jmp     loc_180058FF3
0x180058f49  test    rdx, rdx
0x180058f4c  jz      short loc_180058F17
0x180058f4e  xor     eax, eax
0x180058f50  mov     byte ptr [rcx], 0
0x180058f53  test    r8d, r8d
0x180058f56  cmovg   eax, r8d
0x180058f5a  inc     eax
0x180058f5c  cdqe
0x180058f5e  cmp     rdx, rax
0x180058f61  ja      short loc_180058F6A
0x180058f63  mov     ebx, 22h ; '"'
0x180058f68  jmp     short loc_180058F1C
0x180058f6a  test    rdi, rdi
0x180058f6d  jz      short loc_180058F17
0x180058f6f  mov     rcx, [r9+8]
0x180058f73  lea     rbx, [rsi+1]
0x180058f77  mov     rdx, rcx
0x180058f7a  mov     byte ptr [rsi], 30h ; '0'
0x180058f7d  jmp     short loc_180058F94
0x180058f7f  mov     al, [rdx]
0x180058f81  test    al, al
0x180058f83  jz      short loc_180058F8A
0x180058f85  inc     rdx
0x180058f88  jmp     short loc_180058F8C
0x180058f8a  mov     al, 30h ; '0'
0x180058f8c  mov     [rbx], al
0x180058f8e  inc     rbx
0x180058f91  dec     r8d
0x180058f94  test    r8d, r8d
0x180058f97  jg      short loc_180058F7F
0x180058f99  mov     byte ptr [rbx], 0
0x180058f9c  js      short loc_180058FC9
0x180058f9e  mov     eax, [rsp+38h+arg_28]
0x180058fa2  mov     r9d, [rsp+38h+arg_20]
0x180058fa7  mov     r8d, [rdi]
0x180058faa  mov     dword ptr [rsp+38h+var_18], eax
0x180058fae  call    should_round_up_0
0x180058fb3  test    al, al
0x180058fb5  jz      short loc_180058FC9
0x180058fb7  jmp     short loc_180058FBC
0x180058fb9  mov     byte ptr [rbx], 30h ; '0'
0x180058fbc  dec     rbx
0x180058fbf  mov     al, [rbx]
0x180058fc1  cmp     al, 39h ; '9'
0x180058fc3  jz      short loc_180058FB9
0x180058fc5  inc     al
0x180058fc7  mov     [rbx], al
0x180058fc9  cmp     byte ptr [rsi], 31h ; '1'
0x180058fcc  jnz     short loc_180058FD3
0x180058fce  inc     dword ptr [rdi+4]
0x180058fd1  jmp     short loc_180058FF1
0x180058fd3  or      r8, 0FFFFFFFFFFFFFFFFh
0x180058fd7  inc     r8
0x180058fda  cmp     byte ptr [r8+rsi+1], 0
0x180058fe0  jnz     short loc_180058FD7
0x180058fe2  inc     r8; Size
0x180058fe5  lea     rdx, [rsi+1]; Src
0x180058fe9  mov     rcx, rsi; void *
0x180058fec  call    memmove
0x180058ff1  xor     eax, eax
0x180058ff3  mov     rbx, [rsp+38h+arg_0]
0x180058ff8  mov     rbp, [rsp+38h+arg_8]
0x180058ffd  mov     rsi, [rsp+38h+arg_10]
0x180059002  add     rsp, 30h
0x180059006  pop     rdi
0x180059007  retn
```
