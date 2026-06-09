# CProgramConfig_Check

- ea: `0x1800477e4`
- end: `0x18004798b`
- name: `CProgramConfig_Check`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800127d8`

## callees

- `0x1800477e4`
- `0x18004d320`

## pseudocode

```c
__int64 __fastcall CProgramConfig_Check(unsigned __int8 *a1)
{
  int v1; // esi
  _BYTE *v2; // rbx
  _BYTE *v3; // r14
  unsigned int v4; // r8d
  __int64 v5; // r11
  _BYTE *v6; // r10
  unsigned __int8 *v7; // rdi
  __int64 v8; // rdx
  BOOL v9; // eax
  int v10; // esi
  unsigned __int8 *v11; // rdi
  __int64 v12; // r11
  __int64 v13; // rdx
  BOOL v14; // eax
  int v15; // esi
  unsigned __int8 *v16; // rdi
  __int64 v17; // r11
  __int64 v18; // rdx
  BOOL v19; // eax
  int i; // r9d
  int v21; // ecx
  int v23; // ecx
  int v25; // ecx
  __int64 v28; // [rsp+0h] [rbp-48h]
  int v29; // [rsp+8h] [rbp-40h]
  __int64 v30; // [rsp+10h] [rbp-38h]
  int v31; // [rsp+18h] [rbp-30h]
  __int64 v32; // [rsp+20h] [rbp-28h]
  int v33; // [rsp+28h] [rbp-20h]

  v1 = a1[5];
  v2 = a1 + 16;
  v3 = a1 + 64;
  v4 = 0;
  v32 = 0;
  v5 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  v6 = a1 + 112;
  v28 = 0;
  v29 = 0;
  v7 = a1 + 144;
  if ( v1 )
  {
    do
    {
      v8 = *v7++;
      v9 = a1[v5 + 112] != 0;
      v5 = (unsigned int)(v5 + 1);
      *((_DWORD *)&v32 + v8) += v9 + 1;
    }
    while ( (int)v5 < v1 );
  }
  v10 = a1[4];
  v11 = a1 + 96;
  v12 = 0;
  if ( a1[4] )
  {
    do
    {
      v13 = *v11++;
      v14 = a1[v12 + 64] != 0;
      v12 = (unsigned int)(v12 + 1);
      *((_DWORD *)&v30 + v13) += v14 + 1;
    }
    while ( (int)v12 < v10 );
  }
  v15 = a1[3];
  v16 = a1 + 48;
  v17 = 0;
  if ( a1[3] )
  {
    do
    {
      v18 = *v16++;
      v19 = a1[v17 + 16] != 0;
      v17 = (unsigned int)(v17 + 1);
      *((_DWORD *)&v28 + v18) += v19 + 1;
    }
    while ( (int)v17 < v15 );
  }
  for ( i = 0; i < 3; ++i )
  {
    v21 = *((_DWORD *)&v28 + i);
    if ( (v21 & 1) != 0 )
    {
      if ( *v2 != 1 )
      {
        ++v2;
        --v21;
        goto LABEL_12;
      }
      return 1;
    }
    while ( v21 > 0 )
    {
      if ( !*v2++ )
      {
        if ( *v2 == 1 )
          return 1;
        ++v2;
      }
      v21 -= 2;
LABEL_12:
      *((_DWORD *)&v28 + i) = v21;
    }
    if ( i == 1 )
      goto LABEL_25;
    v23 = *((_DWORD *)&v30 + i);
    if ( (v23 & 1) != 0 )
      return 1;
    while ( v23 > 0 )
    {
      if ( !*v3++ )
      {
        if ( *v3 == 1 )
          return 1;
        ++v3;
      }
      v23 -= 2;
      *((_DWORD *)&v30 + i) = v23;
    }
LABEL_25:
    while ( 1 )
    {
      v25 = *((_DWORD *)&v32 + i);
      if ( v25 <= 1 )
        break;
      if ( !*v6++ )
      {
        if ( *v6 == 1 )
          return 1;
        ++v6;
      }
      *((_DWORD *)&v32 + i) = v25 - 2;
    }
    if ( v25 )
    {
      if ( *v6 == 1 )
        return 1;
      ++v6;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800477e4  push    rbp
0x1800477e6  push    rbx
0x1800477e7  push    rsi
0x1800477e8  push    rdi
0x1800477e9  push    r14
0x1800477eb  push    r15
0x1800477ed  mov     rbp, rsp
0x1800477f0  sub     rsp, 48h
0x1800477f4  mov     rax, cs:__security_cookie
0x1800477fb  xor     rax, rsp
0x1800477fe  mov     [rbp+var_18], rax
0x180047802  movzx   esi, byte ptr [rcx+5]
0x180047806  lea     rbx, [rcx+10h]
0x18004780a  xor     eax, eax
0x18004780c  lea     r14, [rcx+40h]
0x180047810  xor     r8d, r8d
0x180047813  mov     [rbp+var_28], rax
0x180047817  xor     r11d, r11d
0x18004781a  mov     [rbp+var_20], eax
0x18004781d  mov     [rbp+var_38], rax
0x180047821  mov     r9, rcx
0x180047824  mov     [rbp+var_30], eax
0x180047827  lea     r10, [rcx+70h]
0x18004782b  mov     [rbp+var_48], rax
0x18004782f  lea     r15d, [r8+1]
0x180047833  mov     [rbp+var_40], eax
0x180047836  lea     rdi, [rcx+90h]
0x18004783d  test    esi, esi
0x18004783f  jz      short loc_180047861
0x180047841  mov     cl, [r11+r9+70h]
0x180047846  movzx   edx, byte ptr [rdi]
0x180047849  neg     cl
0x18004784b  sbb     eax, eax
0x18004784d  add     rdi, r15
0x180047850  neg     eax
0x180047852  add     r11d, r15d
0x180047855  add     eax, r15d
0x180047858  add     dword ptr [rbp+rdx*4+var_28], eax
0x18004785c  cmp     r11d, esi
0x18004785f  jl      short loc_180047841
0x180047861  movzx   esi, byte ptr [r9+4]
0x180047866  lea     rdi, [r9+60h]
0x18004786a  xor     r11d, r11d
0x18004786d  test    esi, esi
0x18004786f  jz      short loc_180047891
0x180047871  mov     cl, [r11+r9+40h]
0x180047876  movzx   edx, byte ptr [rdi]
0x180047879  neg     cl
0x18004787b  sbb     eax, eax
0x18004787d  add     rdi, r15
0x180047880  neg     eax
0x180047882  add     r11d, r15d
0x180047885  add     eax, r15d
0x180047888  add     dword ptr [rbp+rdx*4+var_38], eax
0x18004788c  cmp     r11d, esi
0x18004788f  jl      short loc_180047871
0x180047891  movzx   esi, byte ptr [r9+3]
0x180047896  lea     rdi, [r9+30h]
0x18004789a  xor     r11d, r11d
0x18004789d  test    esi, esi
0x18004789f  jz      short loc_1800478C1
0x1800478a1  mov     cl, [r11+r9+10h]
0x1800478a6  movzx   edx, byte ptr [rdi]
0x1800478a9  neg     cl
0x1800478ab  sbb     eax, eax
0x1800478ad  add     rdi, r15
0x1800478b0  neg     eax
0x1800478b2  add     r11d, r15d
0x1800478b5  add     eax, r15d
0x1800478b8  add     dword ptr [rbp+rdx*4+var_48], eax
0x1800478bc  cmp     r11d, esi
0x1800478bf  jl      short loc_1800478A1
0x1800478c1  xor     r9d, r9d
0x1800478c4  cmp     r9d, 3
0x1800478c8  jge     loc_18004796E
0x1800478ce  movsxd  rdx, r9d
0x1800478d1  mov     ecx, dword ptr [rbp+rdx*4+var_48]
0x1800478d5  test    r15b, cl
0x1800478d8  jz      short loc_1800478EC
0x1800478da  cmp     [rbx], r15b
0x1800478dd  jz      loc_18004796B
0x1800478e3  add     rbx, r15
0x1800478e6  dec     ecx
0x1800478e8  mov     dword ptr [rbp+rdx*4+var_48], ecx
0x1800478ec  test    ecx, ecx
0x1800478ee  jle     short loc_180047906
0x1800478f0  mov     al, [rbx]
0x1800478f2  add     rbx, r15
0x1800478f5  test    al, al
0x1800478f7  jnz     short loc_180047901
0x1800478f9  cmp     [rbx], r15b
0x1800478fc  jz      short loc_18004796B
0x1800478fe  add     rbx, r15
0x180047901  sub     ecx, 2
0x180047904  jmp     short loc_1800478E8
0x180047906  cmp     r9d, r15d
0x180047909  jz      short loc_180047933
0x18004790b  mov     ecx, dword ptr [rbp+rdx*4+var_38]
0x18004790f  test    r15b, cl
0x180047912  jnz     short loc_18004796B
0x180047914  test    ecx, ecx
0x180047916  jle     short loc_180047933
0x180047918  mov     al, [r14]
0x18004791b  add     r14, r15
0x18004791e  test    al, al
0x180047920  jnz     short loc_18004792A
0x180047922  cmp     [r14], r15b
0x180047925  jz      short loc_18004796B
0x180047927  add     r14, r15
0x18004792a  sub     ecx, 2
0x18004792d  mov     dword ptr [rbp+rdx*4+var_38], ecx
0x180047931  jmp     short loc_180047914
0x180047933  mov     ecx, dword ptr [rbp+rdx*4+var_28]
0x180047937  cmp     ecx, r15d
0x18004793a  jle     short loc_180047957
0x18004793c  mov     al, [r10]
0x18004793f  add     r10, r15
0x180047942  test    al, al
0x180047944  jnz     short loc_18004794E
0x180047946  cmp     [r10], r15b
0x180047949  jz      short loc_18004796B
0x18004794b  add     r10, r15
0x18004794e  lea     eax, [rcx-2]
0x180047951  mov     dword ptr [rbp+rdx*4+var_28], eax
0x180047955  jmp     short loc_180047933
0x180047957  test    ecx, ecx
0x180047959  jz      short loc_180047963
0x18004795b  cmp     [r10], r15b
0x18004795e  jz      short loc_18004796B
0x180047960  add     r10, r15
0x180047963  add     r9d, r15d
0x180047966  jmp     loc_1800478C4
0x18004796b  mov     r8d, r15d
0x18004796e  mov     eax, r8d
0x180047971  mov     rcx, [rbp+var_18]
0x180047975  xor     rcx, rsp; StackCookie
0x180047978  call    __security_check_cookie
0x18004797d  add     rsp, 48h
0x180047981  pop     r15
0x180047983  pop     r14
0x180047985  pop     rdi
0x180047986  pop     rsi
0x180047987  pop     rbx
0x180047988  pop     rbp
0x180047989  retn
```
