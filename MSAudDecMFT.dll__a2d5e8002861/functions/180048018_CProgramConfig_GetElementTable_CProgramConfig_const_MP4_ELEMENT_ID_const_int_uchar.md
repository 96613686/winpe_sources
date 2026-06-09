# CProgramConfig_GetElementTable(CProgramConfig const *,MP4_ELEMENT_ID * const,int,uchar *)

- ea: `0x180048018`
- end: `0x1800482cd`
- name: `?CProgramConfig_GetElementTable@@YAHPEBUCProgramConfig@@QEAW4MP4_ELEMENT_ID@@HPEAE@Z`
- size: `693`
- prototype: `__int64 __fastcall(const struct CProgramConfig *, enum MP4_ELEMENT_ID *const, int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800069ec`
- `0x18000c510`

## callees

- `0x180046ebc`
- `0x180048018`
- `0x18004b854`
- `0x18004d320`

## pseudocode

```c
__int64 __fastcall CProgramConfig_GetElementTable(
        const struct CProgramConfig *a1,
        enum MP4_ELEMENT_ID *const a2,
        __int64 a3,
        unsigned __int8 *a4)
{
  int v7; // edi
  __int64 v8; // rcx
  BOOL v9; // eax
  int v10; // edx
  __int64 v11; // rax
  BOOL v12; // ecx
  int v13; // edx
  __int64 v14; // rax
  BOOL v15; // ecx
  int v16; // ecx
  __int64 v17; // rax
  unsigned __int8 v18; // si
  __int64 k; // rsi
  unsigned __int8 v20; // r14
  char v21; // al
  unsigned __int8 v22; // cl
  __int64 j; // rsi
  unsigned __int8 v24; // r14
  __int64 i; // rsi
  unsigned __int8 v26; // r14
  _DWORD v28[4]; // [rsp+20h] [rbp-E0h]
  _BYTE v29[480]; // [rsp+30h] [rbp-D0h] BYREF

  *a4 = 0;
  if ( *((unsigned __int8 *)a1 + 4)
     + *((unsigned __int8 *)a1 + 3)
     + *((unsigned __int8 *)a1 + 6)
     + (unsigned int)*((unsigned __int8 *)a1 + 5) > 0x10
    || !*((_BYTE *)a1 + 462) )
  {
    return 0;
  }
  v7 = 0;
  if ( *((_BYTE *)a1 + 3) )
  {
    do
    {
      v8 = v7;
      v9 = *((_BYTE *)a1 + v7++ + 16) != 0;
      *((_DWORD *)a2 + v8) = v9;
    }
    while ( v7 < *((unsigned __int8 *)a1 + 3) );
  }
  v10 = 0;
  if ( *((_BYTE *)a1 + 4) )
  {
    do
    {
      v11 = v7;
      v12 = *((_BYTE *)a1 + v10 + 64) != 0;
      ++v7;
      ++v10;
      *((_DWORD *)a2 + v11) = v12;
    }
    while ( v10 < *((unsigned __int8 *)a1 + 4) );
  }
  v13 = 0;
  if ( *((_BYTE *)a1 + 5) )
  {
    do
    {
      v14 = v7;
      v15 = *((_BYTE *)a1 + v13 + 112) != 0;
      ++v7;
      ++v13;
      *((_DWORD *)a2 + v14) = v15;
    }
    while ( v13 < *((unsigned __int8 *)a1 + 5) );
  }
  v16 = 0;
  if ( *((_BYTE *)a1 + 6) )
  {
    do
    {
      v17 = v7;
      ++v16;
      ++v7;
      *((_DWORD *)a2 + v17) = 3;
    }
    while ( v16 < *((unsigned __int8 *)a1 + 6) );
  }
  v18 = *((_BYTE *)a1 + 462);
  if ( v18 == 1 || *((_BYTE *)a1 + 462) == 2 )
  {
    *a4 = v18;
  }
  else
  {
    switch ( *((_BYTE *)a1 + 462) )
    {
      case 3:
        v28[0] = 798;
        for ( i = 0; i != 2; ++i )
        {
          v26 = *((_BYTE *)v28 + i);
          CProgramConfig_GetDefault((struct CProgramConfig *)v29, v26);
          if ( (CProgramConfig_Compare(a1, (const struct CProgramConfig *const)v29) & 0xE) == 0 )
          {
            if ( v26 == 30 )
              v26 = 9;
            *a4 = v26;
          }
        }
        break;
      case 4:
        v28[0] = 1045;
        for ( j = 0; j != 2; ++j )
        {
          v24 = *((_BYTE *)v28 + j);
          CProgramConfig_GetDefault((struct CProgramConfig *)v29, v24);
          if ( (CProgramConfig_Compare(a1, (const struct CProgramConfig *const)v29) & 0xE) == 0 )
          {
            if ( v24 == 21 )
              v24 = 10;
            *a4 = v24;
          }
        }
        break;
      case 5:
      case 6:
        CProgramConfig_GetDefault((struct CProgramConfig *)v29, *((unsigned __int8 *)a1 + 462));
        v21 = CProgramConfig_Compare(a1, (const struct CProgramConfig *const)v29);
        v22 = v18;
        if ( (v21 & 0xE) != 0 )
          v22 = 0;
        *a4 = v22;
        break;
      case 7:
        CProgramConfig_GetDefault((struct CProgramConfig *)v29, 0xBu);
        *a4 = (CProgramConfig_Compare(a1, (const struct CProgramConfig *const)v29) & 0xE) == 0 ? 0xB : 0;
        break;
      case 8:
        v28[0] = 118230560;
        for ( k = 0; k != 4; ++k )
        {
          v20 = *((_BYTE *)v28 + k);
          CProgramConfig_GetDefault((struct CProgramConfig *)v29, v20);
          if ( (CProgramConfig_Compare(a1, (const struct CProgramConfig *const)v29) & 0xE) == 0 )
          {
            if ( v20 == 32 )
              v20 = 12;
            *a4 = v20;
          }
        }
        break;
      default:
        *a4 = 0;
        break;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180048018  push    rbp
0x18004801a  push    rbx
0x18004801b  push    rsi
0x18004801c  push    rdi
0x18004801d  push    r13
0x18004801f  push    r14
0x180048021  push    r15
0x180048023  lea     rbp, [rsp-120h]
0x18004802b  sub     rsp, 220h
0x180048032  mov     rax, cs:__security_cookie
0x180048039  xor     rax, rsp
0x18004803c  mov     [rbp+150h+var_40], rax
0x180048043  mov     rbx, rcx
0x180048046  mov     r8, rdx
0x180048049  xor     r14d, r14d
0x18004804c  mov     r15, r9
0x18004804f  mov     [r9], r14b
0x180048052  movzx   r9d, byte ptr [rcx+3]
0x180048057  movzx   edx, byte ptr [rbx+6]
0x18004805b  movzx   ecx, byte ptr [rcx+4]
0x18004805f  add     edx, r9d
0x180048062  movzx   eax, byte ptr [rbx+5]
0x180048066  add     edx, ecx
0x180048068  add     eax, edx
0x18004806a  cmp     eax, 10h
0x18004806d  ja      loc_1800482A9
0x180048073  cmp     [rbx+1CEh], r14b
0x18004807a  jz      loc_1800482A9
0x180048080  mov     edi, r14d
0x180048083  test    r9d, r9d
0x180048086  jz      short loc_1800480A4
0x180048088  movsxd  rcx, edi
0x18004808b  mov     eax, r14d
0x18004808e  cmp     [rcx+rbx+10h], r14b
0x180048093  setnz   al
0x180048096  inc     edi
0x180048098  mov     [r8+rcx*4], eax
0x18004809c  movzx   eax, byte ptr [rbx+3]
0x1800480a0  cmp     edi, eax
0x1800480a2  jl      short loc_180048088
0x1800480a4  mov     edx, r14d
0x1800480a7  cmp     [rbx+4], r14b
0x1800480ab  jbe     short loc_1800480CE
0x1800480ad  movsxd  rax, edx
0x1800480b0  mov     ecx, r14d
0x1800480b3  cmp     [rax+rbx+40h], r14b
0x1800480b8  movsxd  rax, edi
0x1800480bb  setnz   cl
0x1800480be  inc     edi
0x1800480c0  inc     edx
0x1800480c2  mov     [r8+rax*4], ecx
0x1800480c6  movzx   eax, byte ptr [rbx+4]
0x1800480ca  cmp     edx, eax
0x1800480cc  jl      short loc_1800480AD
0x1800480ce  mov     edx, r14d
0x1800480d1  cmp     [rbx+5], r14b
0x1800480d5  jbe     short loc_1800480F8
0x1800480d7  movsxd  rax, edx
0x1800480da  mov     ecx, r14d
0x1800480dd  cmp     [rax+rbx+70h], r14b
0x1800480e2  movsxd  rax, edi
0x1800480e5  setnz   cl
0x1800480e8  inc     edi
0x1800480ea  inc     edx
0x1800480ec  mov     [r8+rax*4], ecx
0x1800480f0  movzx   eax, byte ptr [rbx+5]
0x1800480f4  cmp     edx, eax
0x1800480f6  jl      short loc_1800480D7
0x1800480f8  mov     ecx, r14d
0x1800480fb  cmp     [rbx+6], r14b
0x1800480ff  jbe     short loc_180048118
0x180048101  movsxd  rax, edi
0x180048104  inc     ecx
0x180048106  inc     edi
0x180048108  mov     dword ptr [r8+rax*4], 3
0x180048110  movzx   eax, byte ptr [rbx+6]
0x180048114  cmp     ecx, eax
0x180048116  jl      short loc_180048101
0x180048118  movzx   esi, byte ptr [rbx+1CEh]
0x18004811f  mov     ecx, esi
0x180048121  sub     ecx, 1
0x180048124  jz      loc_1800482A2
0x18004812a  sub     ecx, 1
0x18004812d  jz      loc_1800482A2
0x180048133  sub     ecx, 1
0x180048136  jz      loc_180048258
0x18004813c  sub     ecx, 1
0x18004813f  jz      loc_18004820E
0x180048145  sub     ecx, 1
0x180048148  jz      loc_1800481E5
0x18004814e  sub     ecx, 1
0x180048151  jz      loc_1800481E5
0x180048157  sub     ecx, 1
0x18004815a  jz      short loc_1800481B7
0x18004815c  cmp     ecx, 1
0x18004815f  jz      short loc_180048169
0x180048161  mov     [r15], r14b
0x180048164  jmp     loc_1800482A5
0x180048169  mov     [rsp+250h+var_230], 70C0E20h
0x180048171  mov     r13d, 0Ch
0x180048177  mov     rsi, r14
0x18004817a  movzx   r14d, byte ptr [rsp+rsi+250h+var_230]
0x180048180  lea     rcx, [rsp+250h+var_220]; struct CProgramConfig *
0x180048185  mov     edx, r14d; unsigned int
0x180048188  call    ?CProgramConfig_GetDefault@@YAXPEAUCProgramConfig@@I@Z; CProgramConfig_GetDefault(CProgramConfig *,uint)
0x18004818d  lea     rdx, [rsp+250h+var_220]; struct CProgramConfig *
0x180048192  mov     rcx, rbx; struct CProgramConfig *
0x180048195  call    ?CProgramConfig_Compare@@YAHQEBUCProgramConfig@@0@Z; CProgramConfig_Compare(CProgramConfig const * const,CProgramConfig const * const)
0x18004819a  test    al, 0Eh
0x18004819c  jnz     short loc_1800481A9
0x18004819e  cmp     r14b, 20h ; ' '
0x1800481a2  cmovz   r14d, r13d
0x1800481a6  mov     [r15], r14b
0x1800481a9  inc     rsi
0x1800481ac  cmp     rsi, 4
0x1800481b0  jnz     short loc_18004817A
0x1800481b2  jmp     loc_1800482A5
0x1800481b7  mov     edx, 0Bh; unsigned int
0x1800481bc  lea     rcx, [rsp+250h+var_220]; struct CProgramConfig *
0x1800481c1  call    ?CProgramConfig_GetDefault@@YAXPEAUCProgramConfig@@I@Z; CProgramConfig_GetDefault(CProgramConfig *,uint)
0x1800481c6  lea     rdx, [rsp+250h+var_220]; struct CProgramConfig *
0x1800481cb  mov     rcx, rbx; struct CProgramConfig *
0x1800481ce  call    ?CProgramConfig_Compare@@YAHQEBUCProgramConfig@@0@Z; CProgramConfig_Compare(CProgramConfig const * const,CProgramConfig const * const)
0x1800481d3  and     al, 0Eh
0x1800481d5  neg     al
0x1800481d7  sbb     al, al
0x1800481d9  not     al
0x1800481db  and     al, 0Bh
0x1800481dd  mov     [r15], al
0x1800481e0  jmp     loc_1800482A5
0x1800481e5  mov     edx, esi; unsigned int
0x1800481e7  lea     rcx, [rsp+250h+var_220]; struct CProgramConfig *
0x1800481ec  call    ?CProgramConfig_GetDefault@@YAXPEAUCProgramConfig@@I@Z; CProgramConfig_GetDefault(CProgramConfig *,uint)
0x1800481f1  lea     rdx, [rsp+250h+var_220]; struct CProgramConfig *
0x1800481f6  mov     rcx, rbx; struct CProgramConfig *
0x1800481f9  call    ?CProgramConfig_Compare@@YAHQEBUCProgramConfig@@0@Z; CProgramConfig_Compare(CProgramConfig const * const,CProgramConfig const * const)
0x1800481fe  test    al, 0Eh
0x180048200  mov     ecx, esi
0x180048202  cmovnz  ecx, r14d
0x180048206  mov     [r15], cl
0x180048209  jmp     loc_1800482A5
0x18004820e  mov     [rsp+250h+var_230], 415h
0x180048216  mov     rsi, r14
0x180048219  movzx   r14d, byte ptr [rsp+rsi+250h+var_230]
0x18004821f  lea     rcx, [rsp+250h+var_220]; struct CProgramConfig *
0x180048224  mov     edx, r14d; unsigned int
0x180048227  call    ?CProgramConfig_GetDefault@@YAXPEAUCProgramConfig@@I@Z; CProgramConfig_GetDefault(CProgramConfig *,uint)
0x18004822c  lea     rdx, [rsp+250h+var_220]; struct CProgramConfig *
0x180048231  mov     rcx, rbx; struct CProgramConfig *
0x180048234  call    ?CProgramConfig_Compare@@YAHQEBUCProgramConfig@@0@Z; CProgramConfig_Compare(CProgramConfig const * const,CProgramConfig const * const)
0x180048239  test    al, 0Eh
0x18004823b  jnz     short loc_18004824D
0x18004823d  cmp     r14b, 15h
0x180048241  mov     eax, 0Ah
0x180048246  cmovz   r14d, eax
0x18004824a  mov     [r15], r14b
0x18004824d  inc     rsi
0x180048250  cmp     rsi, 2
0x180048254  jnz     short loc_180048219
0x180048256  jmp     short loc_1800482A5
0x180048258  mov     [rsp+250h+var_230], 31Eh
0x180048260  mov     rsi, r14
0x180048263  movzx   r14d, byte ptr [rsp+rsi+250h+var_230]
0x180048269  lea     rcx, [rsp+250h+var_220]; struct CProgramConfig *
0x18004826e  mov     edx, r14d; unsigned int
0x180048271  call    ?CProgramConfig_GetDefault@@YAXPEAUCProgramConfig@@I@Z; CProgramConfig_GetDefault(CProgramConfig *,uint)
0x180048276  lea     rdx, [rsp+250h+var_220]; struct CProgramConfig *
0x18004827b  mov     rcx, rbx; struct CProgramConfig *
0x18004827e  call    ?CProgramConfig_Compare@@YAHQEBUCProgramConfig@@0@Z; CProgramConfig_Compare(CProgramConfig const * const,CProgramConfig const * const)
0x180048283  test    al, 0Eh
0x180048285  jnz     short loc_180048297
0x180048287  cmp     r14b, 1Eh
0x18004828b  mov     eax, 9
0x180048290  cmovz   r14d, eax
0x180048294  mov     [r15], r14b
0x180048297  inc     rsi
0x18004829a  cmp     rsi, 2
0x18004829e  jnz     short loc_180048263
0x1800482a0  jmp     short loc_1800482A5
0x1800482a2  mov     [r15], sil
0x1800482a5  mov     eax, edi
0x1800482a7  jmp     short loc_1800482AB
0x1800482a9  xor     eax, eax
0x1800482ab  mov     rcx, [rbp+150h+var_40]
0x1800482b2  xor     rcx, rsp; StackCookie
0x1800482b5  call    __security_check_cookie
0x1800482ba  add     rsp, 220h
0x1800482c1  pop     r15
0x1800482c3  pop     r14
0x1800482c5  pop     r13
0x1800482c7  pop     rdi
0x1800482c8  pop     rsi
0x1800482c9  pop     rbx
0x1800482ca  pop     rbp
0x1800482cb  retn
```
