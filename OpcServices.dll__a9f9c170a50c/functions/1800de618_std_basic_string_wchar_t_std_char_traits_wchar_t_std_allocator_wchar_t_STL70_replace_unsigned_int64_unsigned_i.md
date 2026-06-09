# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>::replace(unsigned __int64,unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,unsigned __int64,unsigned __int64)

- ea: `0x1800de618`
- end: `0x1800de958`
- name: `?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_K0AEBV12@00@Z`
- size: `832`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180083e64`

## callees

- `0x18001c4b0`
- `0x1800cdb60`
- `0x1800cdbbc`
- `0x1800de618`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800de706`
- `msvcrt!memmove_s` at `0x1800de774`
- `msvcrt!memmove_s` at `0x1800de7ef`
- `msvcrt!memmove_s` at `0x1800de85b`
- `msvcrt!memmove_s` at `0x1800de8a7`
- `msvcrt!memmove_s` at `0x1800de8e5`
- `msvcrt!memmove_s` at `0x1800de922`
- `msvcrt!memmove_s` at `0x1800de706`
- `msvcrt!memmove_s` at `0x1800de774`
- `msvcrt!memmove_s` at `0x1800de7ef`
- `msvcrt!memmove_s` at `0x1800de85b`
- `msvcrt!memmove_s` at `0x1800de8a7`
- `msvcrt!memmove_s` at `0x1800de8e5`
- `msvcrt!memmove_s` at `0x1800de922`
- `msvcrt!memcpy_s` at `0x1800de73e`
- `msvcrt!memcpy_s` at `0x1800de73e`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        _QWORD *a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  unsigned __int64 v7; // r15
  unsigned __int64 v8; // r12
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rbp
  unsigned __int64 v16; // rdx
  _QWORD *v17; // rbx
  _QWORD *v18; // rcx
  _QWORD *v19; // r8
  _QWORD *v20; // rax
  unsigned __int64 v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  _QWORD *v24; // rcx
  unsigned __int64 v25; // rdx
  _QWORD *v26; // rcx
  _QWORD *v27; // r8
  char *v28; // r8
  unsigned __int64 v29; // rdx
  char *v30; // rcx
  rsize_t v31; // r9
  _QWORD *v32; // rcx
  _QWORD *v33; // r8
  unsigned __int64 v34; // rdx
  _QWORD *v35; // rax
  _QWORD *v36; // rcx
  unsigned __int64 v37; // r13
  _QWORD *v38; // rcx
  _QWORD *v39; // rax
  _QWORD *v40; // rax
  _QWORD *v41; // rcx
  unsigned __int64 v42; // rdx
  __int64 v43; // r13
  _QWORD *v44; // rax
  _QWORD *v45; // rcx
  unsigned __int64 v46; // rdx
  _QWORD *v47; // rcx
  _QWORD *v48; // r8
  unsigned __int64 v50; // [rsp+98h] [rbp+30h]

  v7 = a5;
  v8 = a3;
  if ( a1[3] < a2 || (v11 = a4[3], v11 < a5) )
    std::_String_base::_Xran();
  v12 = a6;
  if ( a1[3] - a2 < a3 )
    v8 = a1[3] - a2;
  v13 = v11 - a5;
  if ( v13 < a6 )
    v12 = v13;
  if ( ~v12 <= a1[3] - v8 )
    std::_String_base::_Xlen();
  v14 = a1[3];
  v15 = v14 - a2 - v8;
  v50 = v14 + v12 - v8;
  if ( v14 < v50 )
    std::wstring::_Grow(a1, v14 + v12 - v8, 0);
  v16 = a1[4];
  v17 = a1 + 1;
  if ( a1 == a4 )
  {
    if ( v12 > v8 )
    {
      if ( a5 > a2 )
      {
        v37 = a2 + v8;
        if ( a2 + v8 > a5 )
        {
          if ( v16 < 8 )
          {
            v40 = a1 + 1;
            v41 = a1 + 1;
          }
          else
          {
            v40 = (_QWORD *)*v17;
            v41 = (_QWORD *)*v17;
          }
          memmove_s((char *)v40 + 2 * a2, 2 * (v16 - a2), (char *)v41 + 2 * a5, 2 * v8);
          v42 = a1[4];
          v43 = 2 * v37;
          if ( v42 < 8 )
          {
            v45 = a1 + 1;
            v44 = a1 + 1;
          }
          else
          {
            v44 = (_QWORD *)*v17;
            v45 = (_QWORD *)*v17;
          }
          memmove_s((char *)v45 + 2 * a2 + 2 * v12, 2 * (v42 - a2 - v12), (char *)v44 + v43, 2 * v15);
          v46 = a1[4];
          if ( v46 < 8 )
          {
            v47 = a1 + 1;
            v48 = a1 + 1;
          }
          else
          {
            v47 = (_QWORD *)*v17;
            v48 = (_QWORD *)*v17;
          }
          v28 = (char *)v48 + 2 * a5 + 2 * v12;
          v31 = 2 * (v12 - v8);
          v29 = v46 - a2 - v8;
          v30 = (char *)v47 + v43;
          goto LABEL_56;
        }
        if ( v16 < 8 )
        {
          v38 = a1 + 1;
          v39 = a1 + 1;
        }
        else
        {
          v38 = (_QWORD *)*v17;
          v39 = (_QWORD *)*v17;
        }
        memmove_s((char *)v38 + 2 * a2 + 2 * v12, 2 * (v16 - a2 - v12), (char *)v39 + 2 * v37, 2 * v15);
        v34 = a1[4];
        if ( v34 < 8 )
        {
          v35 = a1 + 1;
          v36 = a1 + 1;
        }
        else
        {
          v35 = (_QWORD *)*v17;
          v36 = (_QWORD *)*v17;
        }
        v7 = v12 + a5 - v8;
      }
      else
      {
        if ( v16 < 8 )
        {
          v32 = a1 + 1;
          v33 = a1 + 1;
        }
        else
        {
          v32 = (_QWORD *)*v17;
          v33 = (_QWORD *)*v17;
        }
        memmove_s((char *)v32 + 2 * a2 + 2 * v12, 2 * (v16 - a2 - v12), (char *)v33 + 2 * a2 + 2 * v8, 2 * v15);
        v34 = a1[4];
        if ( v34 < 8 )
        {
          v35 = a1 + 1;
          v36 = a1 + 1;
        }
        else
        {
          v35 = (_QWORD *)*v17;
          v36 = (_QWORD *)*v17;
        }
      }
      v28 = (char *)v36 + 2 * v7;
      v29 = v34 - a2;
      v30 = (char *)v35 + 2 * a2;
      v31 = 2 * v12;
    }
    else
    {
      if ( v16 < 8 )
      {
        v23 = a1 + 1;
        v24 = a1 + 1;
      }
      else
      {
        v23 = (_QWORD *)*v17;
        v24 = (_QWORD *)*v17;
      }
      memmove_s((char *)v23 + 2 * a2, 2 * (v16 - a2), (char *)v24 + 2 * a5, 2 * v12);
      v25 = a1[4];
      if ( v25 < 8 )
      {
        v26 = a1 + 1;
        v27 = a1 + 1;
      }
      else
      {
        v26 = (_QWORD *)*v17;
        v27 = (_QWORD *)*v17;
      }
      v28 = (char *)v27 + 2 * a2 + 2 * v8;
      v29 = v25 - a2 - v12;
      v30 = (char *)v26 + 2 * a2 + 2 * v12;
      v31 = 2 * v15;
    }
LABEL_56:
    memmove_s(v30, 2 * v29, v28, v31);
    goto LABEL_57;
  }
  if ( v16 < 8 )
  {
    v18 = a1 + 1;
    v19 = a1 + 1;
  }
  else
  {
    v18 = (_QWORD *)*v17;
    v19 = (_QWORD *)*v17;
  }
  memmove_s((char *)v18 + 2 * a2 + 2 * v12, 2 * (v16 - a2 - v12), (char *)v19 + 2 * a2 + 2 * v8, 2 * v15);
  v20 = a4 + 1;
  if ( a4[4] >= 8u )
    v20 = (_QWORD *)*v20;
  v21 = a1[4];
  if ( v21 < 8 )
    v22 = a1 + 1;
  else
    v22 = (_QWORD *)*v17;
  memcpy_s((char *)v22 + 2 * a2, 2 * (v21 - a2), (char *)v20 + 2 * a5, 2 * v12);
LABEL_57:
  if ( a1[4] >= 8u )
    v17 = (_QWORD *)*v17;
  a1[3] = v50;
  *((_WORD *)v17 + v50) = 0;
  return a1;
}

```

## disassembly

```asm
0x1800de618  push    rbx
0x1800de61a  push    rbp
0x1800de61b  push    rsi
0x1800de61c  push    rdi
0x1800de61d  push    r12
0x1800de61f  push    r13
0x1800de621  push    r14
0x1800de623  push    r15
0x1800de625  sub     rsp, 28h
0x1800de629  mov     r13, r9
0x1800de62c  mov     r15, [rsp+68h+arg_20]
0x1800de634  mov     r12, r8
0x1800de637  mov     rdi, rdx
0x1800de63a  mov     rsi, rcx
0x1800de63d  cmp     [rcx+18h], rdx
0x1800de641  jb      short loc_1800DE64C
0x1800de643  mov     rdx, [r9+18h]
0x1800de647  cmp     rdx, r15
0x1800de64a  jnb     short loc_1800DE655
0x1800de64c  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x1800de651  mov     rdx, [r13+18h]
0x1800de655  mov     rcx, [rsi+18h]
0x1800de659  mov     r14, [rsp+68h+arg_28]
0x1800de661  mov     rax, rcx
0x1800de664  sub     rax, rdi
0x1800de667  cmp     rax, r12
0x1800de66a  cmovb   r12, rax
0x1800de66e  sub     rdx, r15
0x1800de671  cmp     rdx, r14
0x1800de674  cmovb   r14, rdx
0x1800de678  sub     rcx, r12
0x1800de67b  mov     rax, r14
0x1800de67e  not     rax
0x1800de681  cmp     rax, rcx
0x1800de684  ja      short loc_1800DE68B
0x1800de686  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x1800de68b  mov     rax, [rsi+18h]
0x1800de68f  mov     rcx, r14
0x1800de692  sub     rcx, r12
0x1800de695  mov     rbp, rax
0x1800de698  sub     rbp, rdi
0x1800de69b  mov     [rsp+68h+arg_20], rcx
0x1800de6a3  add     rcx, rax
0x1800de6a6  sub     rbp, r12
0x1800de6a9  mov     [rsp+68h+arg_28], rcx
0x1800de6b1  cmp     rax, rcx
0x1800de6b4  jnb     short loc_1800DE6C4
0x1800de6b6  mov     rdx, rcx
0x1800de6b9  xor     r8d, r8d
0x1800de6bc  mov     rcx, rsi
0x1800de6bf  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x1800de6c4  mov     rdx, [rsi+20h]
0x1800de6c8  lea     rbx, [rsi+8]
0x1800de6cc  cmp     rsi, r13
0x1800de6cf  jz      short loc_1800DE749
0x1800de6d1  cmp     rdx, 8
0x1800de6d5  jb      short loc_1800DE6DF
0x1800de6d7  mov     rcx, [rbx]
0x1800de6da  mov     r8, rcx
0x1800de6dd  jmp     short loc_1800DE6E5
0x1800de6df  mov     rcx, rbx
0x1800de6e2  mov     r8, rbx
0x1800de6e5  sub     rdx, rdi
0x1800de6e8  lea     rax, [rdi+r12]
0x1800de6ec  lea     r8, [r8+rax*2]; Source
0x1800de6f0  sub     rdx, r14
0x1800de6f3  lea     rax, [rdi+r14]
0x1800de6f7  add     rdx, rdx; DestinationSize
0x1800de6fa  lea     rcx, [rcx+rax*2]; Destination
0x1800de6fe  lea     r9, ds:0[rbp*2]; SourceSize
0x1800de706  call    cs:__imp_memmove_s
0x1800de70c  cmp     qword ptr [r13+20h], 8
0x1800de711  lea     rax, [r13+8]
0x1800de715  jb      short loc_1800DE71A
0x1800de717  mov     rax, [rax]
0x1800de71a  mov     rdx, [rsi+20h]
0x1800de71e  cmp     rdx, 8
0x1800de722  jb      short loc_1800DE729
0x1800de724  mov     rcx, [rbx]
0x1800de727  jmp     short loc_1800DE72C
0x1800de729  mov     rcx, rbx
0x1800de72c  sub     rdx, rdi
0x1800de72f  lea     r9, [r14+r14]; SourceSize
0x1800de733  add     rdx, rdx; DestinationSize
0x1800de736  lea     r8, [rax+r15*2]; Source
0x1800de73a  lea     rcx, [rcx+rdi*2]; Destination
0x1800de73e  call    cs:__imp_memcpy_s
0x1800de744  jmp     loc_1800DE928
0x1800de749  cmp     r14, r12
0x1800de74c  ja      short loc_1800DE7B5
0x1800de74e  cmp     rdx, 8
0x1800de752  jb      short loc_1800DE75C
0x1800de754  mov     rax, [rbx]
0x1800de757  mov     rcx, rax
0x1800de75a  jmp     short loc_1800DE762
0x1800de75c  mov     rax, rbx
0x1800de75f  mov     rcx, rbx
0x1800de762  sub     rdx, rdi
0x1800de765  lea     r8, [rcx+r15*2]; Source
0x1800de769  add     rdx, rdx; DestinationSize
0x1800de76c  lea     r9, [r14+r14]; SourceSize
0x1800de770  lea     rcx, [rax+rdi*2]; Destination
0x1800de774  call    cs:__imp_memmove_s
0x1800de77a  mov     rdx, [rsi+20h]
0x1800de77e  cmp     rdx, 8
0x1800de782  jb      short loc_1800DE78C
0x1800de784  mov     rcx, [rbx]
0x1800de787  mov     r8, rcx
0x1800de78a  jmp     short loc_1800DE792
0x1800de78c  mov     rcx, rbx
0x1800de78f  mov     r8, rbx
0x1800de792  lea     rax, [rdi+r12]
0x1800de796  sub     rdx, rdi
0x1800de799  lea     r8, [r8+rax*2]
0x1800de79d  sub     rdx, r14
0x1800de7a0  lea     rax, [rdi+r14]
0x1800de7a4  lea     rcx, [rcx+rax*2]
0x1800de7a8  lea     r9, ds:0[rbp*2]
0x1800de7b0  jmp     loc_1800DE91F
0x1800de7b5  cmp     r15, rdi
0x1800de7b8  ja      short loc_1800DE821
0x1800de7ba  cmp     rdx, 8
0x1800de7be  jb      short loc_1800DE7C8
0x1800de7c0  mov     rcx, [rbx]
0x1800de7c3  mov     r8, rcx
0x1800de7c6  jmp     short loc_1800DE7CE
0x1800de7c8  mov     rcx, rbx
0x1800de7cb  mov     r8, rbx
0x1800de7ce  sub     rdx, rdi
0x1800de7d1  lea     rax, [rdi+r12]
0x1800de7d5  lea     r8, [r8+rax*2]; Source
0x1800de7d9  sub     rdx, r14
0x1800de7dc  lea     rax, [rdi+r14]
0x1800de7e0  add     rdx, rdx; DestinationSize
0x1800de7e3  lea     rcx, [rcx+rax*2]; Destination
0x1800de7e7  lea     r9, ds:0[rbp*2]; SourceSize
0x1800de7ef  call    cs:__imp_memmove_s
0x1800de7f5  mov     rdx, [rsi+20h]
0x1800de7f9  cmp     rdx, 8
0x1800de7fd  jb      short loc_1800DE807
0x1800de7ff  mov     rax, [rbx]
0x1800de802  mov     rcx, rax
0x1800de805  jmp     short loc_1800DE80D
0x1800de807  mov     rax, rbx
0x1800de80a  mov     rcx, rbx
0x1800de80d  lea     r8, [rcx+r15*2]
0x1800de811  sub     rdx, rdi
0x1800de814  lea     rcx, [rax+rdi*2]
0x1800de818  lea     r9, [r14+r14]
0x1800de81c  jmp     loc_1800DE91F
0x1800de821  lea     r13, [rdi+r12]
0x1800de825  cmp     r13, r15
0x1800de828  ja      short loc_1800DE881
0x1800de82a  cmp     rdx, 8
0x1800de82e  jb      short loc_1800DE838
0x1800de830  mov     rcx, [rbx]
0x1800de833  mov     rax, rcx
0x1800de836  jmp     short loc_1800DE83E
0x1800de838  mov     rcx, rbx
0x1800de83b  mov     rax, rbx
0x1800de83e  sub     rdx, rdi
0x1800de841  lea     r8, [rax+r13*2]; Source
0x1800de845  sub     rdx, r14
0x1800de848  lea     rax, [rdi+r14]
0x1800de84c  add     rdx, rdx; DestinationSize
0x1800de84f  lea     r9, ds:0[rbp*2]; SourceSize
0x1800de857  lea     rcx, [rcx+rax*2]; Destination
0x1800de85b  call    cs:__imp_memmove_s
0x1800de861  mov     rdx, [rsi+20h]
0x1800de865  cmp     rdx, 8
0x1800de869  jb      short loc_1800DE873
0x1800de86b  mov     rax, [rbx]
0x1800de86e  mov     rcx, rax
0x1800de871  jmp     short loc_1800DE879
0x1800de873  mov     rax, rbx
0x1800de876  mov     rcx, rbx
0x1800de879  sub     r15, r12
0x1800de87c  add     r15, r14
0x1800de87f  jmp     short loc_1800DE80D
0x1800de881  cmp     rdx, 8
0x1800de885  jb      short loc_1800DE88F
0x1800de887  mov     rax, [rbx]
0x1800de88a  mov     rcx, rax
0x1800de88d  jmp     short loc_1800DE895
0x1800de88f  mov     rax, rbx
0x1800de892  mov     rcx, rbx
0x1800de895  sub     rdx, rdi
0x1800de898  lea     r8, [rcx+r15*2]; Source
0x1800de89c  add     rdx, rdx; DestinationSize
0x1800de89f  lea     r9, [r12+r12]; SourceSize
0x1800de8a3  lea     rcx, [rax+rdi*2]; Destination
0x1800de8a7  call    cs:__imp_memmove_s
0x1800de8ad  mov     rdx, [rsi+20h]
0x1800de8b1  add     r13, r13
0x1800de8b4  cmp     rdx, 8
0x1800de8b8  jb      short loc_1800DE8C2
0x1800de8ba  mov     rax, [rbx]
0x1800de8bd  mov     rcx, rax
0x1800de8c0  jmp     short loc_1800DE8C8
0x1800de8c2  mov     rcx, rbx
0x1800de8c5  mov     rax, rbx
0x1800de8c8  sub     rdx, rdi
0x1800de8cb  lea     r8, [rax+r13]; Source
0x1800de8cf  sub     rdx, r14
0x1800de8d2  lea     rax, [rdi+r14]
0x1800de8d6  add     rdx, rdx; DestinationSize
0x1800de8d9  lea     r9, ds:0[rbp*2]; SourceSize
0x1800de8e1  lea     rcx, [rcx+rax*2]; Destination
0x1800de8e5  call    cs:__imp_memmove_s
0x1800de8eb  mov     rdx, [rsi+20h]
0x1800de8ef  cmp     rdx, 8
0x1800de8f3  jb      short loc_1800DE8FD
0x1800de8f5  mov     rcx, [rbx]
0x1800de8f8  mov     r8, rcx
0x1800de8fb  jmp     short loc_1800DE903
0x1800de8fd  mov     rcx, rbx
0x1800de900  mov     r8, rbx
0x1800de903  mov     r9, [rsp+68h+arg_20]
0x1800de90b  lea     rax, [r15+r14]
0x1800de90f  sub     rdx, rdi
0x1800de912  lea     r8, [r8+rax*2]; Source
0x1800de916  add     r9, r9; SourceSize
0x1800de919  sub     rdx, r12
0x1800de91c  add     rcx, r13; Destination
0x1800de91f  add     rdx, rdx; DestinationSize
0x1800de922  call    cs:__imp_memmove_s
0x1800de928  cmp     qword ptr [rsi+20h], 8
0x1800de92d  jb      short loc_1800DE932
0x1800de92f  mov     rbx, [rbx]
0x1800de932  mov     rax, [rsp+68h+arg_28]
0x1800de93a  xor     ecx, ecx
0x1800de93c  mov     [rsi+18h], rax
0x1800de940  mov     [rbx+rax*2], cx
0x1800de944  mov     rax, rsi
0x1800de947  add     rsp, 28h
0x1800de94b  pop     r15
0x1800de94d  pop     r14
0x1800de94f  pop     r13
0x1800de951  pop     r12
0x1800de953  pop     rdi
0x1800de954  pop     rsi
0x1800de955  pop     rbp
0x1800de956  pop     rbx
0x1800de957  retn
```
