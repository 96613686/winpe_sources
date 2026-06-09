# common_expand_argv_wildcards<wchar_t>(wchar_t * * const,wchar_t * * * const)

- ea: `0x140040870`
- end: `0x140040b0b`
- name: `??$common_expand_argv_wildcards@_W@@YAHQEAPEA_WQEAPEAPEA_W@Z_0`
- size: `667`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140005090`
- `0x140009e2c`
- `0x140040870`
- `0x1400416c0`
- `0x14005a8a0`
- `0x14005c3f0`
- `0x14005c580`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140040a9c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140040a9c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140040aa3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140040aa3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1400408ce`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1400408ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall common_expand_argv_wildcards<wchar_t>(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  char v5; // r15
  __int16 v6; // si
  _BYTE *v7; // r14
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  unsigned __int64 v10; // r8
  __int64 v11; // rax
  size_t v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  void *v18; // rcx
  _BYTE v19[2]; // [rsp+30h] [rbp-50h] BYREF
  __int16 v20; // [rsp+32h] [rbp-4Eh] BYREF
  __int64 v21; // [rsp+38h] [rbp-48h] BYREF
  __int64 v22; // [rsp+40h] [rbp-40h] BYREF
  __int64 v23; // [rsp+48h] [rbp-38h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v25; // [rsp+60h] [rbp-20h]

  v4 = *(_QWORD *)(a2 + 88);
  v5 = *(_BYTE *)(a2 + 104);
  v6 = *(_WORD *)(a2 + 96);
  if ( v4 )
  {
    v19[0] = *(_BYTE *)(a2 + 104);
    v20 = v6;
    *(_OWORD *)Block = 0;
    v25 = 0;
    v14 = -1;
    do
      ++v14;
    while ( *(_BYTE *)(v4 + v14) );
    sub_140009E2C(Block, v4);
    v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
    v15 = (__int64 *)sub_1400416C0(
                       (unsigned int)&v22,
                       (unsigned int)&v23,
                       (unsigned int)Block,
                       (unsigned int)&v20,
                       (__int64)v19);
    v16 = *v15;
    *v15 = 0;
    v21 = v16;
    v17 = *(_QWORD *)(a1 + 8);
    if ( !v17 )
      sub_140005090(507263040);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 24LL))(v17, &v21);
    if ( v21 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 8LL))(v21, 1);
    v21 = 19937;
    if ( v22 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 8LL))(v22, 1);
    v22 = 19937;
    if ( *((_QWORD *)&v25 + 1) > 0xFu )
    {
      v18 = Block[0];
      if ( (unsigned __int64)(*((_QWORD *)&v25 + 1) + 1LL) >= 0x1000 )
      {
        v18 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v18 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      free(v18);
    }
  }
  else
  {
    v7 = (_BYTE *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
    v8 = malloc(0x70u);
    v9 = v8;
    if ( v8 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v7[v10] );
      *v8 = off_1400634F8;
      v11 = *(_QWORD *)(a2 + 88);
      v9[1] = off_1400634E0;
      v9[11] = v11;
      *((_WORD *)v9 + 48) = v6;
      if ( !v7 )
        sub_140005090(505172361);
      if ( !v6 )
        sub_140005090(505172360);
      v12 = 64;
      if ( v10 < 0x40 )
        v12 = v10;
      memcpy(v9 + 2, v7, v12);
      *((_BYTE *)v9 + v12 + 16) = 0;
      v9[1] = off_1400634E0;
      *((_BYTE *)v9 + 104) = v5;
    }
    else
    {
      v9 = 0;
    }
    v21 = (__int64)v9;
    v13 = *(_QWORD *)(a1 + 8);
    if ( !v13 )
      sub_140005090(507263040);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 24LL))(v13, &v21);
    if ( v21 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 8LL))(v21, 1);
  }
}

```

## disassembly

```asm
0x140040870  mov     [rsp-38h+arg_10], rbx
0x140040875  push    rbp
0x140040876  push    rsi
0x140040877  push    rdi
0x140040878  push    r12
0x14004087a  push    r13
0x14004087c  push    r14
0x14004087e  push    r15
0x140040880  mov     rbp, rsp
0x140040883  sub     rsp, 80h
0x14004088a  mov     rax, cs:__security_cookie
0x140040891  xor     rax, rsp
0x140040894  mov     [rbp+var_10], rax
0x140040898  mov     rbx, rdx
0x14004089b  mov     r13, rcx
0x14004089e  mov     rdx, [rdx+58h]
0x1400408a2  mov     r15b, [rbx+68h]
0x1400408a6  movzx   esi, word ptr [rbx+60h]
0x1400408aa  xor     r12d, r12d
0x1400408ad  test    rdx, rdx
0x1400408b0  jnz     loc_140040996
0x1400408b6  mov     rax, [rbx]
0x1400408b9  mov     rcx, rbx
0x1400408bc  mov     rax, [rax+10h]
0x1400408c0  call    cs:__guard_dispatch_icall_fptr
0x1400408c6  mov     r14, rax
0x1400408c9  lea     ecx, [r12+70h]; Size
0x1400408ce  call    cs:__imp_malloc
0x1400408d4  mov     rdi, rax
0x1400408d7  test    rax, rax
0x1400408da  jz      short loc_14004094D
0x1400408dc  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400408e0  inc     r8
0x1400408e3  cmp     [r14+r8], r12b
0x1400408e7  jnz     short loc_1400408E0
0x1400408e9  lea     rax, off_1400634F8
0x1400408f0  mov     [rdi], rax
0x1400408f3  mov     rax, [rbx+58h]
0x1400408f7  lea     rcx, off_1400634E0
0x1400408fe  mov     [rdi+8], rcx
0x140040902  mov     [rdi+58h], rax
0x140040906  mov     [rdi+60h], si
0x14004090a  test    r14, r14
0x14004090d  jz      loc_140040AE1
0x140040913  test    si, si
0x140040916  jz      loc_140040AEE
0x14004091c  lea     rcx, [rdi+10h]; void *
0x140040920  mov     ebx, 40h ; '@'
0x140040925  cmp     r8, rbx
0x140040928  cmovb   rbx, r8
0x14004092c  mov     r8, rbx; Size
0x14004092f  mov     rdx, r14; Src
0x140040932  call    memcpy
0x140040937  mov     [rdi+rbx+10h], r12b
0x14004093c  lea     rax, off_1400634E0
0x140040943  mov     [rdi+8], rax
0x140040947  mov     [rdi+68h], r15b
0x14004094b  jmp     short loc_140040950
0x14004094d  mov     rdi, r12
0x140040950  mov     [rbp+var_48], rdi
0x140040954  mov     rcx, [r13+8]
0x140040958  test    rcx, rcx
0x14004095b  jz      loc_140040AFE
0x140040961  mov     rax, [rcx]
0x140040964  lea     rdx, [rbp+var_48]
0x140040968  mov     rax, [rax+18h]
0x14004096c  call    cs:__guard_dispatch_icall_fptr
0x140040972  mov     rcx, [rbp+var_48]
0x140040976  test    rcx, rcx
0x140040979  jz      loc_140040AAA
0x14004097f  mov     rax, [rcx]
0x140040982  mov     edx, 1
0x140040987  mov     rax, [rax+8]
0x14004098b  call    cs:__guard_dispatch_icall_fptr
0x140040991  jmp     loc_140040AAA
0x140040996  mov     [rbp+var_50], r15b
0x14004099a  mov     [rbp+var_4E], si
0x14004099e  xorps   xmm0, xmm0
0x1400409a1  movups  xmmword ptr [rbp+Block], xmm0
0x1400409a5  xorps   xmm1, xmm1
0x1400409a8  movdqu  [rbp+var_20], xmm1
0x1400409ad  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400409b1  inc     r8
0x1400409b4  cmp     [rdx+r8], r12b
0x1400409b8  jnz     short loc_1400409B1
0x1400409ba  lea     rcx, [rbp+Block]
0x1400409be  call    sub_140009E2C
0x1400409c3  mov     rax, [rbx]
0x1400409c6  mov     rcx, rbx
0x1400409c9  mov     rax, [rax+10h]
0x1400409cd  call    cs:__guard_dispatch_icall_fptr
0x1400409d3  mov     [rbp+var_38], rax
0x1400409d7  lea     rax, [rbp+var_50]
0x1400409db  mov     [rsp+80h+Reserved], rax
0x1400409e0  lea     r9, [rbp+var_4E]
0x1400409e4  lea     r8, [rbp+Block]
0x1400409e8  lea     rdx, [rbp+var_38]
0x1400409ec  lea     rcx, [rbp+var_40]
0x1400409f0  call    sub_1400416C0
0x1400409f5  mov     rcx, [rax]
0x1400409f8  mov     [rax], r12
0x1400409fb  mov     [rbp+var_48], rcx
0x1400409ff  mov     rcx, [r13+8]
0x140040a03  test    rcx, rcx
0x140040a06  jz      loc_140040AD1
0x140040a0c  mov     rax, [rcx]
0x140040a0f  lea     rdx, [rbp+var_48]
0x140040a13  mov     rax, [rax+18h]
0x140040a17  call    cs:__guard_dispatch_icall_fptr
0x140040a1d  mov     rcx, [rbp+var_48]
0x140040a21  test    rcx, rcx
0x140040a24  jz      short loc_140040A38
0x140040a26  mov     rax, [rcx]
0x140040a29  mov     edx, 1
0x140040a2e  mov     rax, [rax+8]
0x140040a32  call    cs:__guard_dispatch_icall_fptr
0x140040a38  mov     ebx, 4DE1h
0x140040a3d  mov     [rbp+var_48], rbx
0x140040a41  mov     rcx, [rbp+var_40]
0x140040a45  test    rcx, rcx
0x140040a48  jz      short loc_140040A5C
0x140040a4a  mov     rax, [rcx]
0x140040a4d  mov     edx, 1
0x140040a52  mov     rax, [rax+8]
0x140040a56  call    cs:__guard_dispatch_icall_fptr
0x140040a5c  mov     [rbp+var_40], rbx
0x140040a60  mov     rax, qword ptr [rbp+var_20+8]
0x140040a64  cmp     rax, 0Fh
0x140040a68  jbe     short loc_140040AAA
0x140040a6a  mov     rcx, [rbp+Block]; Block
0x140040a6e  mov     rdx, rcx
0x140040a71  inc     rax
0x140040a74  cmp     rax, 1000h
0x140040a7a  jb      short loc_140040AA3
0x140040a7c  mov     rcx, [rcx-8]
0x140040a80  sub     rdx, rcx
0x140040a83  lea     rax, [rdx-8]
0x140040a87  cmp     rax, 1Fh
0x140040a8b  jbe     short loc_140040AA3
0x140040a8d  mov     [rsp+80h+Reserved], r12; Reserved
0x140040a92  xor     r9d, r9d; LineNo
0x140040a95  xor     r8d, r8d; FileName
0x140040a98  xor     edx, edx; FunctionName
0x140040a9a  xor     ecx, ecx; Expression
0x140040a9c  call    cs:_invoke_watson
0x140040aa3  call    cs:__imp_free
0x140040aa9  nop
0x140040aaa  mov     rcx, [rbp+var_10]
0x140040aae  xor     rcx, rsp; StackCookie
0x140040ab1  call    __security_check_cookie
0x140040ab6  mov     rbx, [rsp+80h+arg_10]
0x140040abe  add     rsp, 80h
0x140040ac5  pop     r15
0x140040ac7  pop     r14
0x140040ac9  pop     r13
0x140040acb  pop     r12
0x140040acd  pop     rdi
0x140040ace  pop     rsi
0x140040acf  pop     rbp
0x140040ad0  retn
0x140040ad1  xor     edx, edx
0x140040ad3  mov     ecx, 1E3C3840h
0x140040ad8  call    sub_140005090
0x140040ade  jmp     short $+2
0x140040ae0  nop
0x140040ae1  xor     edx, edx
0x140040ae3  mov     ecx, 1E1C5189h
0x140040ae8  call    sub_140005090
0x140040aee  xor     edx, edx
0x140040af0  mov     ecx, 1E1C5188h
0x140040af5  call    sub_140005090
0x140040afb  jmp     short $+2
0x140040afd  nop
0x140040afe  xor     edx, edx
0x140040b00  mov     ecx, 1E3C3840h
0x140040b05  call    sub_140005090
```
