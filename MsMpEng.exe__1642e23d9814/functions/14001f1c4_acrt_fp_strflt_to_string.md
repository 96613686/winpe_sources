# __acrt_fp_strflt_to_string

- ea: `0x14001f1c4`
- end: `0x14001f2d4`
- name: `__acrt_fp_strflt_to_string`
- size: `272`
- prototype: `__int64 __fastcall(_BYTE *, unsigned __int64, int, unsigned int *, unsigned int, int, __crt_cached_ptd_host *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140019d84`
- `0x14001a06c`
- `0x14001a294`

## callees

- `0x140015fe4`
- `0x14001f0f4`
- `0x14001f1c4`
- `0x140029c50`

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
    sub_140015FE4(0, 0, 0, 0, 0, a7);
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
    sub_140029C50(a1, a1 + 1, v16 + 1);
  }
  return 0;
}

```

## disassembly

```asm
0x14001f1c4  mov     [rsp+arg_0], rbx
0x14001f1c9  mov     [rsp+arg_8], rbp
0x14001f1ce  mov     [rsp+arg_10], rsi
0x14001f1d3  push    rdi
0x14001f1d4  sub     rsp, 30h
0x14001f1d8  mov     rdi, r9
0x14001f1db  mov     rsi, rcx
0x14001f1de  test    rcx, rcx
0x14001f1e1  jnz     short loc_14001F215
0x14001f1e3  mov     ebx, 16h
0x14001f1e8  mov     rax, [rsp+38h+arg_30]
0x14001f1ed  xor     r9d, r9d; LineNo
0x14001f1f0  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x14001f1f5  xor     r8d, r8d; FileName
0x14001f1f8  and     [rsp+38h+var_18], 0
0x14001f1fe  xor     edx, edx; FunctionName
0x14001f200  xor     ecx, ecx; Expression
0x14001f202  mov     [rax+2Ch], ebx
0x14001f205  mov     byte ptr [rax+30h], 1
0x14001f209  call    sub_140015FE4
0x14001f20e  mov     eax, ebx
0x14001f210  jmp     loc_14001F2BF
0x14001f215  test    rdx, rdx
0x14001f218  jz      short loc_14001F1E3
0x14001f21a  xor     eax, eax
0x14001f21c  mov     byte ptr [rcx], 0
0x14001f21f  test    r8d, r8d
0x14001f222  cmovg   eax, r8d
0x14001f226  inc     eax
0x14001f228  cdqe
0x14001f22a  cmp     rdx, rax
0x14001f22d  ja      short loc_14001F236
0x14001f22f  mov     ebx, 22h ; '"'
0x14001f234  jmp     short loc_14001F1E8
0x14001f236  test    rdi, rdi
0x14001f239  jz      short loc_14001F1E3
0x14001f23b  mov     rcx, [r9+8]
0x14001f23f  lea     rbx, [rsi+1]
0x14001f243  mov     rdx, rcx
0x14001f246  mov     byte ptr [rsi], 30h ; '0'
0x14001f249  jmp     short loc_14001F260
0x14001f24b  mov     al, [rdx]
0x14001f24d  test    al, al
0x14001f24f  jz      short loc_14001F256
0x14001f251  inc     rdx
0x14001f254  jmp     short loc_14001F258
0x14001f256  mov     al, 30h ; '0'
0x14001f258  mov     [rbx], al
0x14001f25a  inc     rbx
0x14001f25d  dec     r8d
0x14001f260  test    r8d, r8d
0x14001f263  jg      short loc_14001F24B
0x14001f265  mov     byte ptr [rbx], 0
0x14001f268  js      short loc_14001F295
0x14001f26a  mov     eax, [rsp+38h+arg_28]
0x14001f26e  mov     r9d, [rsp+38h+arg_20]
0x14001f273  mov     r8d, [rdi]
0x14001f276  mov     dword ptr [rsp+38h+var_18], eax
0x14001f27a  call    ?should_round_up@@YA_NQEBD0HW4__acrt_has_trailing_digits@@W4__acrt_rounding_mode@@@Z
0x14001f27f  test    al, al
0x14001f281  jz      short loc_14001F295
0x14001f283  jmp     short loc_14001F288
0x14001f285  mov     byte ptr [rbx], 30h ; '0'
0x14001f288  dec     rbx
0x14001f28b  mov     al, [rbx]
0x14001f28d  cmp     al, 39h ; '9'
0x14001f28f  jz      short loc_14001F285
0x14001f291  inc     al
0x14001f293  mov     [rbx], al
0x14001f295  cmp     byte ptr [rsi], 31h ; '1'
0x14001f298  jnz     short loc_14001F29F
0x14001f29a  inc     dword ptr [rdi+4]
0x14001f29d  jmp     short loc_14001F2BD
0x14001f29f  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001f2a3  inc     r8
0x14001f2a6  cmp     byte ptr [r8+rsi+1], 0
0x14001f2ac  jnz     short loc_14001F2A3
0x14001f2ae  inc     r8
0x14001f2b1  lea     rdx, [rsi+1]
0x14001f2b5  mov     rcx, rsi
0x14001f2b8  call    sub_140029C50
0x14001f2bd  xor     eax, eax
0x14001f2bf  mov     rbx, [rsp+38h+arg_0]
0x14001f2c4  mov     rbp, [rsp+38h+arg_8]
0x14001f2c9  mov     rsi, [rsp+38h+arg_10]
0x14001f2ce  add     rsp, 30h
0x14001f2d2  pop     rdi
0x14001f2d3  retn
```
