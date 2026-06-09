# ParseCommandLineToStringArrayLocalAlloc

- ea: `0x140001160`
- end: `0x1400015fc`
- name: `ParseCommandLineToStringArrayLocalAlloc`
- size: `1180`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400074e4`

## callees

- `0x140001160`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400013de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400013de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400015a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400015a0`

## pseudocode

```c
__int64 __fastcall ParseCommandLineToStringArrayLocalAlloc(__int16 *a1, __int64 a2, _QWORD *a3, unsigned __int64 *a4)
{
  __int16 v4; // r10
  unsigned __int64 v5; // r12
  bool v7; // di
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // r9
  unsigned __int64 v10; // rbp
  __int64 result; // rax
  unsigned __int64 v12; // r8
  char v13; // bl
  __int16 v14; // cx
  __int64 v15; // r10
  unsigned __int64 v16; // r9
  unsigned __int64 v17; // rcx
  __int64 v18; // rax
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rcx
  bool v21; // cf
  __int16 v22; // cx
  unsigned __int64 v23; // rbp
  char *v24; // r11
  _QWORD *v25; // r14
  unsigned __int64 v26; // rdx
  bool v27; // si
  signed int v28; // ebx
  unsigned __int64 v29; // r8
  char v30; // di
  __int16 v31; // ax
  __int64 v32; // r10
  unsigned __int64 v33; // r9
  unsigned __int64 v34; // rcx
  __int64 v35; // rax
  unsigned __int64 v36; // rax
  unsigned __int64 v37; // rcx
  bool v38; // cf
  unsigned __int64 v39; // rax
  char i; // r9
  __int16 v41; // r8
  unsigned __int64 v42; // rax
  char v43; // r8
  __int16 v44; // cx
  unsigned __int64 v45; // rbx
  __int64 v46; // rax
  _QWORD *v47; // r15
  unsigned __int64 v48; // [rsp+70h] [rbp+8h]

  v4 = *a1;
  v5 = 0;
  *a3 = 0;
  *a4 = 0;
  if ( v4 == 32 || v4 == 9 )
    return 2147942487LL;
  v48 = 0;
  v7 = v4 != 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
LABEL_4:
  if ( v7 )
  {
    result = 0;
    v12 = 0;
    v13 = 0;
    while ( 1 )
    {
      v14 = a1[v8];
      v15 = 1;
      if ( v13 )
      {
        if ( !v14 )
          goto LABEL_70;
        if ( v14 == 34 )
        {
          if ( a1[v8 + 1] != 34 )
          {
            v13 = 0;
            goto LABEL_12;
          }
          v15 = 2;
        }
      }
      else
      {
        if ( !v14 || v14 == 9 || v14 == 32 )
        {
          v39 = v12 + 1;
          v21 = v12 + 1 < v12;
          if ( v12 + 1 < v12 )
            goto LABEL_15;
          if ( v39 + v10 < v10 )
            return 2147942934LL;
          ++v48;
          v10 += v39;
          for ( i = 0; ; i = 1 )
          {
            v41 = a1[v8];
            result = 0;
            if ( v41 != 9 && v41 != 32 )
              break;
            if ( v8 + 1 < v8 )
            {
              v8 = -1;
              result = 2147942934LL;
              goto LABEL_16;
            }
            ++v8;
          }
          if ( v41 )
          {
            v7 = 1;
            goto LABEL_16;
          }
          if ( i )
LABEL_70:
            result = 2147942487LL;
          else
            v7 = 0;
LABEL_16:
          if ( (int)result < 0 )
            return result;
          v9 = v48;
          goto LABEL_4;
        }
        if ( v14 == 34 )
        {
          v13 = 1;
          goto LABEL_12;
        }
      }
      v16 = v12;
      v17 = v12 + 1;
      v18 = -1;
      if ( v12 + 1 >= v12 )
        v18 = v12 + 1;
      v12 = v18;
      result = v17 < v16 ? 0x80070216 : 0;
LABEL_12:
      if ( (int)result < 0 )
        return result;
      v19 = v15 + v8;
      v20 = v8;
      if ( v15 + v8 < v8 )
      {
        v8 = -1;
        v21 = v19 < v20;
LABEL_15:
        result = v21 ? 0x80070216 : 0;
        goto LABEL_16;
      }
      v8 += v15;
      result = v19 < v20 ? 0x80070216 : 0;
    }
  }
  v45 = 8 * v9;
  if ( is_mul_ok(v9, 8u) )
  {
    v46 = 2 * v10;
    if ( is_mul_ok(v10, 2u) && v46 + v45 >= v45 )
    {
      v47 = LocalAlloc(0, v46 + v45);
      if ( !v47 )
        return 2147942414LL;
      v22 = *a1;
      if ( *a1 == 32 || v22 == 9 )
      {
        v28 = -2147024809;
        goto LABEL_53;
      }
      v23 = 0;
      v24 = (char *)&v47[v45 / 8];
      v25 = v47;
      v26 = 0;
      v27 = v22 != 0;
      v28 = 0;
LABEL_30:
      if ( !v27 )
        goto LABEL_56;
      v28 = 0;
      v29 = 0;
      v30 = 0;
      while ( 1 )
      {
        v31 = a1[v26];
        v32 = 1;
        if ( v30 )
        {
          if ( !v31 )
            goto LABEL_87;
          if ( v31 == 34 )
          {
            if ( a1[v26 + 1] != 34 )
            {
              v30 = 0;
              goto LABEL_40;
            }
            v32 = 2;
          }
        }
        else
        {
          if ( !v31 || v31 == 9 || v31 == 32 )
          {
            if ( v24 )
              *(_WORD *)&v24[2 * v29] = 0;
            v42 = v29 + 1;
            v38 = v29 + 1 < v29;
            if ( v29 + 1 < v29 )
              goto LABEL_43;
            if ( v25 )
            {
              *v25++ = v24;
              v24 += 2 * v42;
            }
            if ( v42 + v23 < v23 )
            {
              v28 = -2147024362;
              goto LABEL_55;
            }
            ++v5;
            v28 = 0;
            v43 = 0;
            v23 += v42;
            while ( 1 )
            {
              v44 = a1[v26];
              if ( v44 != 32 && v44 != 9 )
                break;
              if ( v26 + 1 < v26 )
              {
                v26 = -1;
                v28 = -2147024362;
                goto LABEL_44;
              }
              v43 = 1;
              ++v26;
              v28 = 0;
            }
            if ( v44 )
            {
              v27 = 1;
              goto LABEL_44;
            }
            if ( v43 )
LABEL_87:
              v28 = -2147024809;
            else
              v27 = 0;
LABEL_44:
            if ( v28 >= 0 )
              goto LABEL_30;
LABEL_55:
            v5 = v48;
LABEL_56:
            if ( v28 >= 0 )
            {
              *a3 = v47;
              *a4 = v5;
              return (unsigned int)v28;
            }
LABEL_53:
            LocalFree(v47);
            return (unsigned int)v28;
          }
          if ( v31 == 34 )
          {
            v30 = 1;
            goto LABEL_40;
          }
        }
        v33 = v29;
        if ( v24 )
          *(_WORD *)&v24[2 * v29] = v31;
        v34 = v29 + 1;
        v35 = -1;
        if ( v29 + 1 >= v29 )
          v35 = v29 + 1;
        v29 = v35;
        v28 = v34 < v33 ? 0x80070216 : 0;
LABEL_40:
        if ( v28 < 0 )
          goto LABEL_55;
        v36 = v32 + v26;
        v37 = v26;
        if ( v32 + v26 < v26 )
        {
          v26 = -1;
          v38 = v36 < v37;
LABEL_43:
          v28 = v38 ? 0x80070216 : 0;
          goto LABEL_44;
        }
        v26 += v32;
        v28 = v36 < v37 ? 0x80070216 : 0;
      }
    }
  }
  return 2147942934LL;
}

```

## disassembly

```asm
0x140001160  mov     [rsp+arg_8], rbx
0x140001165  mov     [rsp+arg_18], r9
0x14000116a  mov     [rsp+arg_10], r8
0x14000116f  push    rbp
0x140001170  push    rsi
0x140001171  push    rdi
0x140001172  push    r12
0x140001174  push    r13
0x140001176  push    r14
0x140001178  push    r15
0x14000117a  sub     rsp, 30h
0x14000117e  movzx   r10d, word ptr [rcx]
0x140001182  xor     r12d, r12d
0x140001185  mov     r15d, 20h ; ' '
0x14000118b  mov     [r8], r12
0x14000118e  mov     [r9], r12
0x140001191  mov     r13, rcx
0x140001194  cmp     r15w, r10w
0x140001198  jz      loc_1400012A6
0x14000119e  mov     r14d, 9
0x1400011a4  cmp     r14w, r10w
0x1400011a8  jz      loc_1400012A6
0x1400011ae  cmp     r12w, r10w
0x1400011b2  mov     [rsp+68h+arg_0], r12
0x1400011b7  mov     esi, r12d
0x1400011ba  mov     r11d, r12d
0x1400011bd  setnz   dil
0x1400011c1  mov     edx, r12d
0x1400011c4  mov     r9d, r12d
0x1400011c7  mov     ebp, r12d
0x1400011ca  nop     word ptr [rax+rax+00h]
0x1400011d0  test    dil, dil
0x1400011d3  jz      loc_14000156C
0x1400011d9  mov     eax, r12d
0x1400011dc  mov     r8, r12
0x1400011df  xor     bl, bl
0x1400011e1  movzx   ecx, word ptr [r13+rdx*2+0]
0x1400011e7  mov     r10d, 1
0x1400011ed  test    bl, bl
0x1400011ef  jz      loc_140001279
0x1400011f5  test    cx, cx
0x1400011f8  jz      loc_1400014B1
0x1400011fe  cmp     cx, 22h ; '"'
0x140001202  jz      loc_1400015BC
0x140001208  mov     r9, r8
0x14000120b  test    r11, r11
0x14000120e  jz      short loc_140001215
0x140001210  mov     [r11+r8*2], cx
0x140001215  lea     rcx, [r8+1]
0x140001219  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140001220  cmp     rcx, r8
0x140001223  cmovnb  rax, rcx
0x140001227  cmp     rcx, r9
0x14000122a  mov     r8, rax
0x14000122d  sbb     eax, eax
0x14000122f  and     eax, 80070216h
0x140001234  test    eax, eax
0x140001236  js      loc_1400012B2
0x14000123c  lea     rax, [r10+rdx]
0x140001240  mov     rcx, rdx
0x140001243  cmp     rax, rdx
0x140001246  jnb     short loc_140001267
0x140001248  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x14000124f  cmp     rax, rcx
0x140001252  sbb     eax, eax
0x140001254  and     eax, 80070216h
0x140001259  test    eax, eax
0x14000125b  js      short loc_1400012B2
0x14000125d  mov     r9, [rsp+68h+arg_0]
0x140001262  jmp     loc_1400011D0
0x140001267  cmp     rax, rcx
0x14000126a  mov     rdx, rax
0x14000126d  sbb     eax, eax
0x14000126f  and     eax, 80070216h
0x140001274  jmp     loc_1400011E1
0x140001279  test    cx, cx
0x14000127c  jz      loc_140001416
0x140001282  cmp     cx, r14w
0x140001286  jz      loc_140001416
0x14000128c  cmp     cx, r15w
0x140001290  jz      loc_140001416
0x140001296  cmp     cx, 22h ; '"'
0x14000129a  jnz     loc_140001208
0x1400012a0  movzx   ebx, r10b
0x1400012a4  jmp     short loc_140001234
0x1400012a6  mov     eax, 80070057h
0x1400012ab  jmp     short loc_1400012B2
0x1400012ad  mov     eax, 80070216h
0x1400012b2  mov     rbx, [rsp+68h+arg_8]
0x1400012b7  add     rsp, 30h
0x1400012bb  pop     r15
0x1400012bd  pop     r14
0x1400012bf  pop     r13
0x1400012c1  pop     r12
0x1400012c3  pop     rdi
0x1400012c4  pop     rsi
0x1400012c5  pop     rbp
0x1400012c6  retn
0x1400012c7  movzx   ecx, word ptr [r13+0]
0x1400012cc  mov     eax, 20h ; ' '
0x1400012d1  cmp     ax, cx
0x1400012d4  jz      loc_1400013D6
0x1400012da  cmp     r14w, cx
0x1400012de  jz      loc_1400013D6
0x1400012e4  xor     ebp, ebp
0x1400012e6  lea     r11, [r15+rbx]
0x1400012ea  xor     eax, eax
0x1400012ec  mov     r14, r15
0x1400012ef  cmp     ax, cx
0x1400012f2  mov     rdx, r12
0x1400012f5  setnz   sil
0x1400012f9  xor     ebx, ebx
0x1400012fb  nop     dword ptr [rax+rax+00h]
0x140001300  test    sil, sil
0x140001303  jz      loc_1400013F5
0x140001309  xor     ebx, ebx
0x14000130b  xor     r8d, r8d
0x14000130e  xor     dil, dil
0x140001311  movzx   eax, word ptr [r13+rdx*2+0]
0x140001317  mov     r10d, 1
0x14000131d  test    dil, dil
0x140001320  jz      loc_1400013A9
0x140001326  test    ax, ax
0x140001329  jz      loc_140001562
0x14000132f  cmp     ax, 22h ; '"'
0x140001333  jz      loc_1400015DC
0x140001339  mov     r9, r8
0x14000133c  test    r11, r11
0x14000133f  jz      short loc_140001346
0x140001341  mov     [r11+r8*2], ax
0x140001346  lea     rcx, [r8+1]
0x14000134a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140001351  cmp     rcx, r8
0x140001354  cmovnb  rax, rcx
0x140001358  cmp     rcx, r9
0x14000135b  mov     r8, rax
0x14000135e  sbb     ebx, ebx
0x140001360  and     ebx, 80070216h
0x140001366  test    ebx, ebx
0x140001368  js      loc_1400013F0
0x14000136e  lea     rax, [r10+rdx]
0x140001372  mov     rcx, rdx
0x140001375  cmp     rax, rdx
0x140001378  jnb     short loc_140001396
0x14000137a  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x140001381  cmp     rax, rcx
0x140001384  sbb     ebx, ebx
0x140001386  and     ebx, 80070216h
0x14000138c  test    ebx, ebx
0x14000138e  jns     loc_140001300
0x140001394  jmp     short loc_1400013F0
0x140001396  cmp     rax, rcx
0x140001399  mov     rdx, rax
0x14000139c  sbb     ebx, ebx
0x14000139e  and     ebx, 80070216h
0x1400013a4  jmp     loc_140001311
0x1400013a9  test    ax, ax
0x1400013ac  jz      loc_1400014BB
0x1400013b2  cmp     ax, 9
0x1400013b6  jz      loc_1400014BB
0x1400013bc  cmp     ax, 20h ; ' '
0x1400013c0  jz      loc_1400014BB
0x1400013c6  cmp     ax, 22h ; '"'
0x1400013ca  jnz     loc_140001339
0x1400013d0  movzx   edi, r10b
0x1400013d4  jmp     short loc_140001366
0x1400013d6  mov     ebx, 80070057h
0x1400013db  mov     rcx, r15; hMem
0x1400013de  call    cs:__imp_LocalFree
0x1400013e4  mov     eax, ebx
0x1400013e6  jmp     loc_1400012B2
0x1400013eb  mov     ebx, 80070216h
0x1400013f0  mov     r12, [rsp+68h+arg_0]
0x1400013f5  test    ebx, ebx
0x1400013f7  js      short loc_1400013DB
0x1400013f9  mov     rax, [rsp+68h+arg_10]
0x140001401  mov     [rax], r15
0x140001404  mov     rax, [rsp+68h+arg_18]
0x14000140c  mov     [rax], r12
0x14000140f  mov     eax, ebx
0x140001411  jmp     loc_1400012B2
0x140001416  test    r11, r11
0x140001419  jz      short loc_140001420
0x14000141b  mov     [r11+r8*2], r12w
0x140001420  lea     rax, [r8+1]
0x140001424  cmp     rax, r8
0x140001427  jb      loc_140001252
0x14000142d  test    rsi, rsi
0x140001430  jz      short loc_14000143D
0x140001432  mov     [rsi], r11
0x140001435  add     rsi, 8
0x140001439  lea     r11, [r11+rax*2]
0x14000143d  lea     rcx, [rax+rbp]
0x140001441  cmp     rcx, rbp
0x140001444  jb      loc_1400012AD
0x14000144a  inc     [rsp+68h+arg_0]
0x14000144f  mov     rbp, rcx
0x140001452  xor     r9b, r9b
0x140001455  movzx   r8d, word ptr [r13+rdx*2+0]
0x14000145b  mov     eax, r12d
0x14000145e  cmp     r14w, r8w
0x140001462  jz      short loc_140001481
0x140001464  cmp     r15w, r8w
0x140001468  jz      short loc_140001481
0x14000146a  test    eax, eax
0x14000146c  js      loc_1400012B2
0x140001472  cmp     r12w, r8w
0x140001476  jz      short loc_1400014A4
0x140001478  movzx   edi, r10b
0x14000147c  jmp     loc_140001259
0x140001481  lea     rax, [rdx+1]
0x140001485  cmp     rax, rdx
0x140001488  jb      short loc_140001493
0x14000148a  movzx   r9d, r10b
0x14000148e  mov     rdx, rax
0x140001491  jmp     short loc_140001455
0x140001493  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x14000149a  mov     eax, 80070216h
0x14000149f  jmp     loc_140001259
0x1400014a4  test    r9b, r9b
0x1400014a7  jnz     short loc_1400014B1
0x1400014a9  xor     dil, dil
0x1400014ac  jmp     loc_140001259
0x1400014b1  mov     eax, 80070057h
0x1400014b6  jmp     loc_140001259
0x1400014bb  test    r11, r11
0x1400014be  jz      short loc_1400014C7
0x1400014c0  xor     eax, eax
0x1400014c2  mov     [r11+r8*2], ax
0x1400014c7  lea     rax, [r8+1]
0x1400014cb  cmp     rax, r8
0x1400014ce  jb      loc_140001384
0x1400014d4  test    r14, r14
0x1400014d7  jz      short loc_1400014E4
0x1400014d9  mov     [r14], r11
0x1400014dc  add     r14, 8
0x1400014e0  lea     r11, [r11+rax*2]
0x1400014e4  lea     rcx, [rax+rbp]
0x1400014e8  cmp     rcx, rbp
0x1400014eb  jb      loc_1400013EB
0x1400014f1  inc     r12
0x1400014f4  xor     ebx, ebx
0x1400014f6  xor     r8b, r8b
0x1400014f9  mov     rbp, rcx
0x1400014fc  mov     r9d, 20h ; ' '
0x140001502  movzx   ecx, word ptr [r13+rdx*2+0]
0x140001508  cmp     r9w, cx
0x14000150c  jz      short loc_140001530
0x14000150e  mov     eax, 9
0x140001513  cmp     ax, cx
0x140001516  jz      short loc_140001530
0x140001518  test    ebx, ebx
0x14000151a  js      loc_1400013F0
0x140001520  xor     eax, eax
0x140001522  cmp     ax, cx
0x140001525  jz      short loc_140001555
0x140001527  movzx   esi, r10b
0x14000152b  jmp     loc_14000138C
0x140001530  lea     rax, [rdx+1]
0x140001534  cmp     rax, rdx
0x140001537  jb      short loc_140001544
0x140001539  movzx   r8d, r10b
0x14000153d  mov     rdx, rax
0x140001540  xor     ebx, ebx
0x140001542  jmp     short loc_140001502
0x140001544  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x14000154b  mov     ebx, 80070216h
0x140001550  jmp     loc_14000138C
0x140001555  test    r8b, r8b
0x140001558  jnz     short loc_140001562
0x14000155a  xor     sil, sil
0x14000155d  jmp     loc_14000138C
0x140001562  mov     ebx, 80070057h
0x140001567  jmp     loc_14000138C
0x14000156c  mov     eax, 8
0x140001571  mul     r9
0x140001574  mov     rbx, rax
0x140001577  test    rdx, rdx
0x14000157a  jnz     loc_1400012AD
0x140001580  mov     eax, 2
0x140001585  mul     rbp
0x140001588  test    rdx, rdx
0x14000158b  jnz     loc_1400012AD
0x140001591  lea     rdx, [rax+rbx]; uBytes
0x140001595  cmp     rdx, rbx
0x140001598  jb      loc_1400012AD
0x14000159e  xor     ecx, ecx; uFlags
0x1400015a0  call    cs:__imp_LocalAlloc
0x1400015a6  mov     r15, rax
0x1400015a9  test    rax, rax
0x1400015ac  jnz     loc_1400012C7
0x1400015b2  mov     eax, 8007000Eh
0x1400015b7  jmp     loc_1400012B2
0x1400015bc  mov     r9d, 22h ; '"'
0x1400015c2  cmp     r9w, [r13+rdx*2+2]
0x1400015c8  jz      short loc_1400015D1
0x1400015ca  xor     bl, bl
0x1400015cc  jmp     loc_140001234
0x1400015d1  mov     r10d, 2
0x1400015d7  jmp     loc_140001208
  ... truncated ...
```
