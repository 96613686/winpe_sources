# fp_format_e_internal(char * const,unsigned __int64,int,bool,uint,_strflt * const,bool,__crt_cached_ptd_host &)

- ea: `0x14001253c`
- end: `0x14001271d`
- name: `?fp_format_e_internal@@YAHQEAD_KH_NIQEAU_strflt@@2AEAV__crt_cached_ptd_host@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(char *const, unsigned __int64, int, char, unsigned int, struct _strflt *const, bool, struct __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140012438`
- `0x140012950`

## callees

- `0x140004614`
- `0x14000471c`
- `0x14000ad70`
- `0x14001253c`
- `0x140016470`
- `0x14001db10`

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
  size_t v18; // rdx
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
        memmove(v14 + 1, v14, v15 + 1);
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
    if ( strcpy_s(v17, v18, "e+000") )
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
      memmove(v19, v17 + 3, 3u);
    return 0;
  }
  else
  {
    *((_BYTE *)a8 + 48) = 1;
    *((_DWORD *)a8 + 11) = 34;
    sub_140004614(0, 0, 0, 0, 0, a8);
    return 34;
  }
}

```

## disassembly

```asm
0x14001253c  mov     r11, rsp
0x14001253f  mov     [r11+8], rbx
0x140012543  mov     [r11+10h], rbp
0x140012547  mov     [r11+18h], rsi
0x14001254b  mov     [r11+20h], rdi
0x14001254f  push    r13
0x140012551  push    r14
0x140012553  push    r15
0x140012555  sub     rsp, 30h
0x140012559  xor     eax, eax
0x14001255b  movsxd  rbp, r8d
0x14001255e  test    r8d, r8d
0x140012561  mov     r13b, r9b
0x140012564  mov     r15, rdx
0x140012567  mov     rdi, rcx
0x14001256a  cmovg   eax, ebp
0x14001256d  add     eax, 9
0x140012570  cdqe
0x140012572  cmp     rdx, rax
0x140012575  ja      short loc_1400125C4
0x140012577  mov     rcx, [rsp+48h+arg_38]
0x14001257f  mov     ebx, 22h ; '"'
0x140012584  mov     [r11-20h], rcx
0x140012588  xor     r9d, r9d; LineNo
0x14001258b  and     qword ptr [r11-28h], 0
0x140012590  xor     r8d, r8d; FileName
0x140012593  xor     edx, edx; FunctionName
0x140012595  mov     byte ptr [rcx+30h], 1
0x140012599  mov     [rcx+2Ch], ebx
0x14001259c  xor     ecx, ecx; Expression
0x14001259e  call    sub_140004614
0x1400125a3  mov     eax, ebx
0x1400125a5  mov     rbx, [rsp+48h+arg_0]
0x1400125aa  mov     rbp, [rsp+48h+arg_8]
0x1400125af  mov     rsi, [rsp+48h+arg_10]
0x1400125b4  mov     rdi, [rsp+48h+arg_18]
0x1400125b9  add     rsp, 30h
0x1400125bd  pop     r15
0x1400125bf  pop     r14
0x1400125c1  pop     r13
0x1400125c3  retn
0x1400125c4  cmp     [rsp+48h+arg_30], 0
0x1400125cc  mov     rsi, [rsp+48h+arg_28]
0x1400125d1  jz      short loc_1400125FD
0x1400125d3  xor     edx, edx
0x1400125d5  cmp     dword ptr [rsi], 2Dh ; '-'
0x1400125d8  setz    dl
0x1400125db  add     rdx, rdi; Src
0x1400125de  test    r8d, r8d
0x1400125e1  jle     short loc_1400125FD
0x1400125e3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400125e7  inc     r8
0x1400125ea  cmp     byte ptr [rdx+r8], 0
0x1400125ef  jnz     short loc_1400125E7
0x1400125f1  inc     r8; MaxCount
0x1400125f4  lea     rcx, [rdx+1]; Dst
0x1400125f8  call    memmove
0x1400125fd  cmp     dword ptr [rsi], 2Dh ; '-'
0x140012600  mov     rbx, rdi
0x140012603  jnz     short loc_14001260C
0x140012605  mov     byte ptr [rdi], 2Dh ; '-'
0x140012608  lea     rbx, [rdi+1]
0x14001260c  test    ebp, ebp
0x14001260e  jle     short loc_140012641
0x140012610  mov     al, [rbx+1]
0x140012613  mov     r14, [rsp+48h+arg_38]
0x14001261b  mov     [rbx], al
0x14001261d  inc     rbx
0x140012620  cmp     byte ptr [r14+28h], 0
0x140012625  jnz     short loc_14001262F
0x140012627  mov     rcx, r14; this
0x14001262a  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x14001262f  mov     rax, [r14+18h]
0x140012633  mov     rcx, [rax+0F8h]
0x14001263a  mov     rax, [rcx]
0x14001263d  mov     cl, [rax]
0x14001263f  mov     [rbx], cl
0x140012641  movzx   ecx, [rsp+48h+arg_30]
0x140012649  lea     r8, Src
0x140012650  xor     rcx, 1
0x140012654  add     rbx, rbp
0x140012657  add     rbx, rcx
0x14001265a  sub     rdi, rbx
0x14001265d  mov     rcx, rbx; Dst
0x140012660  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x140012664  lea     rdx, [r15+rdi]
0x140012668  cmovz   rdx, r15; Size
0x14001266c  call    strcpy_s
0x140012671  test    eax, eax
0x140012673  jnz     loc_140012707
0x140012679  lea     rcx, [rbx+2]; Dst
0x14001267d  test    r13b, r13b
0x140012680  jz      short loc_140012685
0x140012682  mov     byte ptr [rbx], 45h ; 'E'
0x140012685  mov     rax, [rsi+8]
0x140012689  cmp     byte ptr [rax], 30h ; '0'
0x14001268c  jz      short loc_1400126E5
0x14001268e  mov     r8d, [rsi+4]
0x140012692  sub     r8d, 1
0x140012696  jns     short loc_14001269F
0x140012698  neg     r8d
0x14001269b  mov     byte ptr [rbx+1], 2Dh ; '-'
0x14001269f  cmp     r8d, 64h ; 'd'
0x1400126a3  jl      short loc_1400126C0
0x1400126a5  mov     eax, 51EB851Fh
0x1400126aa  imul    r8d
0x1400126ad  sar     edx, 5
0x1400126b0  mov     eax, edx
0x1400126b2  shr     eax, 1Fh
0x1400126b5  add     edx, eax
0x1400126b7  add     [rbx+2], dl
0x1400126ba  imul    eax, edx, -64h
0x1400126bd  add     r8d, eax
0x1400126c0  cmp     r8d, 0Ah
0x1400126c4  jl      short loc_1400126E1
0x1400126c6  mov     eax, 66666667h
0x1400126cb  imul    r8d
0x1400126ce  sar     edx, 2
0x1400126d1  mov     eax, edx
0x1400126d3  shr     eax, 1Fh
0x1400126d6  add     edx, eax
0x1400126d8  add     [rbx+3], dl
0x1400126db  imul    eax, edx, -0Ah
0x1400126de  add     r8d, eax
0x1400126e1  add     [rbx+4], r8b
0x1400126e5  cmp     [rsp+48h+arg_20], 2
0x1400126ea  jnz     short loc_140012700
0x1400126ec  cmp     byte ptr [rcx], 30h ; '0'
0x1400126ef  jnz     short loc_140012700
0x1400126f1  lea     rdx, [rcx+1]; Src
0x1400126f5  mov     r8d, 3; MaxCount
0x1400126fb  call    memmove
0x140012700  xor     eax, eax
0x140012702  jmp     loc_1400125A5
0x140012707  and     [rsp+48h+var_28], 0
0x14001270d  xor     r9d, r9d; LineNo
0x140012710  xor     r8d, r8d; FileName
0x140012713  xor     edx, edx; FunctionName
0x140012715  xor     ecx, ecx; Expression
0x140012717  call    _invoke_watson
```
