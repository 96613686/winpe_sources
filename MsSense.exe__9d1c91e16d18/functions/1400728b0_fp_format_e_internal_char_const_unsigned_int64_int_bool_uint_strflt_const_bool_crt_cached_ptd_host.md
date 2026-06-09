# fp_format_e_internal(char * const,unsigned __int64,int,bool,uint,_strflt * const,bool,__crt_cached_ptd_host &)

- ea: `0x1400728b0`
- end: `0x140072a91`
- name: `?fp_format_e_internal@@YAHQEAD_KH_NIQEAU_strflt@@2AEAV__crt_cached_ptd_host@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(char *const, unsigned __int64, int, char, unsigned int, struct _strflt *const, bool, struct __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400727ac`
- `0x140072cbc`

## callees

- `0x14006147c`
- `0x140061554`
- `0x140065e50`
- `0x140071a90`
- `0x1400728b0`
- `0x14007fc30`

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
        sub_14007FC30(v14 + 1, v14, v15 + 1);
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
    if ( (unsigned int)sub_140071A90(v17, v18, "e+000") )
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
      sub_14007FC30(v19, v17 + 3, 3);
    return 0;
  }
  else
  {
    *((_BYTE *)a8 + 48) = 1;
    *((_DWORD *)a8 + 11) = 34;
    sub_14006147C(0, 0, 0, 0, 0, a8);
    return 34;
  }
}

```

## disassembly

```asm
0x1400728b0  mov     r11, rsp
0x1400728b3  mov     [r11+8], rbx
0x1400728b7  mov     [r11+10h], rbp
0x1400728bb  mov     [r11+18h], rsi
0x1400728bf  mov     [r11+20h], rdi
0x1400728c3  push    r13
0x1400728c5  push    r14
0x1400728c7  push    r15
0x1400728c9  sub     rsp, 30h
0x1400728cd  xor     eax, eax
0x1400728cf  movsxd  rbp, r8d
0x1400728d2  test    r8d, r8d
0x1400728d5  mov     r13b, r9b
0x1400728d8  mov     r15, rdx
0x1400728db  mov     rdi, rcx
0x1400728de  cmovg   eax, ebp
0x1400728e1  add     eax, 9
0x1400728e4  cdqe
0x1400728e6  cmp     rdx, rax
0x1400728e9  ja      short loc_140072938
0x1400728eb  mov     rcx, [rsp+48h+arg_38]
0x1400728f3  mov     ebx, 22h ; '"'
0x1400728f8  mov     [r11-20h], rcx
0x1400728fc  xor     r9d, r9d; LineNo
0x1400728ff  and     qword ptr [r11-28h], 0
0x140072904  xor     r8d, r8d; FileName
0x140072907  xor     edx, edx; FunctionName
0x140072909  mov     byte ptr [rcx+30h], 1
0x14007290d  mov     [rcx+2Ch], ebx
0x140072910  xor     ecx, ecx; Expression
0x140072912  call    sub_14006147C
0x140072917  mov     eax, ebx
0x140072919  mov     rbx, [rsp+48h+arg_0]
0x14007291e  mov     rbp, [rsp+48h+arg_8]
0x140072923  mov     rsi, [rsp+48h+arg_10]
0x140072928  mov     rdi, [rsp+48h+arg_18]
0x14007292d  add     rsp, 30h
0x140072931  pop     r15
0x140072933  pop     r14
0x140072935  pop     r13
0x140072937  retn
0x140072938  cmp     [rsp+48h+arg_30], 0
0x140072940  mov     rsi, [rsp+48h+arg_28]
0x140072945  jz      short loc_140072971
0x140072947  xor     edx, edx
0x140072949  cmp     dword ptr [rsi], 2Dh ; '-'
0x14007294c  setz    dl
0x14007294f  add     rdx, rdi
0x140072952  test    r8d, r8d
0x140072955  jle     short loc_140072971
0x140072957  or      r8, 0FFFFFFFFFFFFFFFFh
0x14007295b  inc     r8
0x14007295e  cmp     byte ptr [rdx+r8], 0
0x140072963  jnz     short loc_14007295B
0x140072965  inc     r8
0x140072968  lea     rcx, [rdx+1]
0x14007296c  call    sub_14007FC30
0x140072971  cmp     dword ptr [rsi], 2Dh ; '-'
0x140072974  mov     rbx, rdi
0x140072977  jnz     short loc_140072980
0x140072979  mov     byte ptr [rdi], 2Dh ; '-'
0x14007297c  lea     rbx, [rdi+1]
0x140072980  test    ebp, ebp
0x140072982  jle     short loc_1400729B5
0x140072984  mov     al, [rbx+1]
0x140072987  mov     r14, [rsp+48h+arg_38]
0x14007298f  mov     [rbx], al
0x140072991  inc     rbx
0x140072994  cmp     byte ptr [r14+28h], 0
0x140072999  jnz     short loc_1400729A3
0x14007299b  mov     rcx, r14; this
0x14007299e  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x1400729a3  mov     rax, [r14+18h]
0x1400729a7  mov     rcx, [rax+0F8h]
0x1400729ae  mov     rax, [rcx]
0x1400729b1  mov     cl, [rax]
0x1400729b3  mov     [rbx], cl
0x1400729b5  movzx   ecx, [rsp+48h+arg_30]
0x1400729bd  lea     r8, aE000
0x1400729c4  xor     rcx, 1
0x1400729c8  add     rbx, rbp
0x1400729cb  add     rbx, rcx
0x1400729ce  sub     rdi, rbx
0x1400729d1  mov     rcx, rbx
0x1400729d4  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1400729d8  lea     rdx, [r15+rdi]
0x1400729dc  cmovz   rdx, r15
0x1400729e0  call    sub_140071A90
0x1400729e5  test    eax, eax
0x1400729e7  jnz     loc_140072A7B
0x1400729ed  lea     rcx, [rbx+2]
0x1400729f1  test    r13b, r13b
0x1400729f4  jz      short loc_1400729F9
0x1400729f6  mov     byte ptr [rbx], 45h ; 'E'
0x1400729f9  mov     rax, [rsi+8]
0x1400729fd  cmp     byte ptr [rax], 30h ; '0'
0x140072a00  jz      short loc_140072A59
0x140072a02  mov     r8d, [rsi+4]
0x140072a06  sub     r8d, 1
0x140072a0a  jns     short loc_140072A13
0x140072a0c  neg     r8d
0x140072a0f  mov     byte ptr [rbx+1], 2Dh ; '-'
0x140072a13  cmp     r8d, 64h ; 'd'
0x140072a17  jl      short loc_140072A34
0x140072a19  mov     eax, 51EB851Fh
0x140072a1e  imul    r8d
0x140072a21  sar     edx, 5
0x140072a24  mov     eax, edx
0x140072a26  shr     eax, 1Fh
0x140072a29  add     edx, eax
0x140072a2b  add     [rbx+2], dl
0x140072a2e  imul    eax, edx, -64h
0x140072a31  add     r8d, eax
0x140072a34  cmp     r8d, 0Ah
0x140072a38  jl      short loc_140072A55
0x140072a3a  mov     eax, 66666667h
0x140072a3f  imul    r8d
0x140072a42  sar     edx, 2
0x140072a45  mov     eax, edx
0x140072a47  shr     eax, 1Fh
0x140072a4a  add     edx, eax
0x140072a4c  add     [rbx+3], dl
0x140072a4f  imul    eax, edx, -0Ah
0x140072a52  add     r8d, eax
0x140072a55  add     [rbx+4], r8b
0x140072a59  cmp     [rsp+48h+arg_20], 2
0x140072a5e  jnz     short loc_140072A74
0x140072a60  cmp     byte ptr [rcx], 30h ; '0'
0x140072a63  jnz     short loc_140072A74
0x140072a65  lea     rdx, [rcx+1]
0x140072a69  mov     r8d, 3
0x140072a6f  call    sub_14007FC30
0x140072a74  xor     eax, eax
0x140072a76  jmp     loc_140072919
0x140072a7b  and     [rsp+48h+var_28], 0
0x140072a81  xor     r9d, r9d; LineNo
0x140072a84  xor     r8d, r8d; FileName
0x140072a87  xor     edx, edx; FunctionName
0x140072a89  xor     ecx, ecx; Expression
0x140072a8b  call    _invoke_watson
```
