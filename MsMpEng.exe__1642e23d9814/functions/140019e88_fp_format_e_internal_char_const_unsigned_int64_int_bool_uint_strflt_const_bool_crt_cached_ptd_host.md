# fp_format_e_internal(char * const,unsigned __int64,int,bool,uint,_strflt * const,bool,__crt_cached_ptd_host &)

- ea: `0x140019e88`
- end: `0x14001a069`
- name: `?fp_format_e_internal@@YAHQEAD_KH_NIQEAU_strflt@@2AEAV__crt_cached_ptd_host@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(char *const, unsigned __int64, int, char, unsigned int, struct _strflt *const, bool, struct __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140019d84`
- `0x14001a294`

## callees

- `0x140014130`
- `0x140015fe4`
- `0x1400160bc`
- `0x1400191a0`
- `0x140019e88`
- `0x140029c50`

## pseudocode

```c
__int64 __fastcall fp_format_e_internal(
        char *const a1,
        unsigned __int64 a2,
        int a3,
        char a4,
        unsigned int a5,
        struct _strflt *const a6,
        bool a7,
        struct __crt_cached_ptd_host *a8)
{
  int v8; // eax
  __int64 v9; // rbp
  char *v14; // rdx
  __int64 v15; // r8
  char *v16; // rbx
  char *v17; // rbx
  __int64 v18; // rdx
  _BYTE *v19; // rcx
  int v20; // r8d

  v8 = 0;
  v9 = a3;
  if ( a3 > 0 )
    v8 = a3;
  if ( a2 > v8 + 9 )
  {
    if ( a7 )
    {
      v14 = &a1[*(_DWORD *)a6 == 45];
      if ( a3 > 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( v14[v15] );
        sub_140029C50(v14 + 1, v14, v15 + 1);
      }
    }
    v16 = a1;
    if ( *(_DWORD *)a6 == 45 )
    {
      *a1 = 45;
      v16 = a1 + 1;
    }
    if ( (int)v9 > 0 )
    {
      *v16 = v16[1];
      ++v16;
      if ( !*((_BYTE *)a8 + 40) )
        __crt_cached_ptd_host::update_locale_slow(a8);
      *v16 = ***(_BYTE ***)(*((_QWORD *)a8 + 3) + 248LL);
    }
    v17 = &v16[v9 + !a7];
    v18 = a2 + a1 - v17;
    if ( a2 == -1 )
      v18 = -1;
    if ( (unsigned int)sub_1400191A0(v17, v18, "e+000") )
      invoke_watson(0, 0, 0, 0, 0);
    v19 = v17 + 2;
    if ( a4 )
      *v17 = 69;
    if ( **((_BYTE **)a6 + 1) != 48 )
    {
      v20 = *((_DWORD *)a6 + 1) - 1;
      if ( v20 < 0 )
      {
        v20 = 1 - *((_DWORD *)a6 + 1);
        v17[1] = 45;
      }
      if ( v20 >= 100 )
      {
        v17[2] += v20 / 100;
        v20 %= 100;
      }
      if ( v20 >= 10 )
      {
        v17[3] += v20 / 10;
        LOBYTE(v20) = v20 % 10;
      }
      v17[4] += v20;
    }
    if ( a5 == 2 && *v19 == 48 )
      sub_140029C50(v19, v17 + 3, 3);
    return 0;
  }
  else
  {
    *((_BYTE *)a8 + 48) = 1;
    *((_DWORD *)a8 + 11) = 34;
    sub_140015FE4(0, 0, 0, 0, 0, a8);
    return 34;
  }
}

```

## disassembly

```asm
0x140019e88  mov     r11, rsp
0x140019e8b  mov     [r11+8], rbx
0x140019e8f  mov     [r11+10h], rbp
0x140019e93  mov     [r11+18h], rsi
0x140019e97  mov     [r11+20h], rdi
0x140019e9b  push    r13
0x140019e9d  push    r14
0x140019e9f  push    r15
0x140019ea1  sub     rsp, 30h
0x140019ea5  xor     eax, eax
0x140019ea7  movsxd  rbp, r8d
0x140019eaa  test    r8d, r8d
0x140019ead  mov     r13b, r9b
0x140019eb0  mov     r15, rdx
0x140019eb3  mov     rdi, rcx
0x140019eb6  cmovg   eax, ebp
0x140019eb9  add     eax, 9
0x140019ebc  cdqe
0x140019ebe  cmp     rdx, rax
0x140019ec1  ja      short loc_140019F10
0x140019ec3  mov     rcx, [rsp+48h+arg_38]
0x140019ecb  mov     ebx, 22h ; '"'
0x140019ed0  mov     [r11-20h], rcx
0x140019ed4  xor     r9d, r9d; LineNo
0x140019ed7  and     qword ptr [r11-28h], 0
0x140019edc  xor     r8d, r8d; FileName
0x140019edf  xor     edx, edx; FunctionName
0x140019ee1  mov     byte ptr [rcx+30h], 1
0x140019ee5  mov     [rcx+2Ch], ebx
0x140019ee8  xor     ecx, ecx; Expression
0x140019eea  call    sub_140015FE4
0x140019eef  mov     eax, ebx
0x140019ef1  mov     rbx, [rsp+48h+arg_0]
0x140019ef6  mov     rbp, [rsp+48h+arg_8]
0x140019efb  mov     rsi, [rsp+48h+arg_10]
0x140019f00  mov     rdi, [rsp+48h+arg_18]
0x140019f05  add     rsp, 30h
0x140019f09  pop     r15
0x140019f0b  pop     r14
0x140019f0d  pop     r13
0x140019f0f  retn
0x140019f10  cmp     [rsp+48h+arg_30], 0
0x140019f18  mov     rsi, [rsp+48h+arg_28]
0x140019f1d  jz      short loc_140019F49
0x140019f1f  xor     edx, edx
0x140019f21  cmp     dword ptr [rsi], 2Dh ; '-'
0x140019f24  setz    dl
0x140019f27  add     rdx, rdi
0x140019f2a  test    r8d, r8d
0x140019f2d  jle     short loc_140019F49
0x140019f2f  or      r8, 0FFFFFFFFFFFFFFFFh
0x140019f33  inc     r8
0x140019f36  cmp     byte ptr [rdx+r8], 0
0x140019f3b  jnz     short loc_140019F33
0x140019f3d  inc     r8
0x140019f40  lea     rcx, [rdx+1]
0x140019f44  call    sub_140029C50
0x140019f49  cmp     dword ptr [rsi], 2Dh ; '-'
0x140019f4c  mov     rbx, rdi
0x140019f4f  jnz     short loc_140019F58
0x140019f51  mov     byte ptr [rdi], 2Dh ; '-'
0x140019f54  lea     rbx, [rdi+1]
0x140019f58  test    ebp, ebp
0x140019f5a  jle     short loc_140019F8D
0x140019f5c  mov     al, [rbx+1]
0x140019f5f  mov     r14, [rsp+48h+arg_38]
0x140019f67  mov     [rbx], al
0x140019f69  inc     rbx
0x140019f6c  cmp     byte ptr [r14+28h], 0
0x140019f71  jnz     short loc_140019F7B
0x140019f73  mov     rcx, r14; this
0x140019f76  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x140019f7b  mov     rax, [r14+18h]
0x140019f7f  mov     rcx, [rax+0F8h]
0x140019f86  mov     rax, [rcx]
0x140019f89  mov     cl, [rax]
0x140019f8b  mov     [rbx], cl
0x140019f8d  movzx   ecx, [rsp+48h+arg_30]
0x140019f95  lea     r8, aE000
0x140019f9c  xor     rcx, 1
0x140019fa0  add     rbx, rbp
0x140019fa3  add     rbx, rcx
0x140019fa6  sub     rdi, rbx
0x140019fa9  mov     rcx, rbx
0x140019fac  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x140019fb0  lea     rdx, [r15+rdi]
0x140019fb4  cmovz   rdx, r15
0x140019fb8  call    sub_1400191A0
0x140019fbd  test    eax, eax
0x140019fbf  jnz     loc_14001A053
0x140019fc5  lea     rcx, [rbx+2]
0x140019fc9  test    r13b, r13b
0x140019fcc  jz      short loc_140019FD1
0x140019fce  mov     byte ptr [rbx], 45h ; 'E'
0x140019fd1  mov     rax, [rsi+8]
0x140019fd5  cmp     byte ptr [rax], 30h ; '0'
0x140019fd8  jz      short loc_14001A031
0x140019fda  mov     r8d, [rsi+4]
0x140019fde  sub     r8d, 1
0x140019fe2  jns     short loc_140019FEB
0x140019fe4  neg     r8d
0x140019fe7  mov     byte ptr [rbx+1], 2Dh ; '-'
0x140019feb  cmp     r8d, 64h ; 'd'
0x140019fef  jl      short loc_14001A00C
0x140019ff1  mov     eax, 51EB851Fh
0x140019ff6  imul    r8d
0x140019ff9  sar     edx, 5
0x140019ffc  mov     eax, edx
0x140019ffe  shr     eax, 1Fh
0x14001a001  add     edx, eax
0x14001a003  add     [rbx+2], dl
0x14001a006  imul    eax, edx, -64h
0x14001a009  add     r8d, eax
0x14001a00c  cmp     r8d, 0Ah
0x14001a010  jl      short loc_14001A02D
0x14001a012  mov     eax, 66666667h
0x14001a017  imul    r8d
0x14001a01a  sar     edx, 2
0x14001a01d  mov     eax, edx
0x14001a01f  shr     eax, 1Fh
0x14001a022  add     edx, eax
0x14001a024  add     [rbx+3], dl
0x14001a027  imul    eax, edx, -0Ah
0x14001a02a  add     r8d, eax
0x14001a02d  add     [rbx+4], r8b
0x14001a031  cmp     [rsp+48h+arg_20], 2
0x14001a036  jnz     short loc_14001A04C
0x14001a038  cmp     byte ptr [rcx], 30h ; '0'
0x14001a03b  jnz     short loc_14001A04C
0x14001a03d  lea     rdx, [rcx+1]
0x14001a041  mov     r8d, 3
0x14001a047  call    sub_140029C50
0x14001a04c  xor     eax, eax
0x14001a04e  jmp     loc_140019EF1
0x14001a053  and     [rsp+48h+var_28], 0
0x14001a059  xor     r9d, r9d; LineNo
0x14001a05c  xor     r8d, r8d; FileName
0x14001a05f  xor     edx, edx; FunctionName
0x14001a061  xor     ecx, ecx; Expression
0x14001a063  call    _invoke_watson
```
