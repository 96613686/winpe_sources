# TiffSeekToPage

- ea: `0x1800091a0`
- end: `0x1800097db`
- name: `TiffSeekToPage`
- size: `1595`
- prototype: `__int64 __fastcall(__int64, unsigned int, int)`
- caller_count: `7`
- callee_count: `8`
- tags: ``

## callers

- `0x1800044f0`
- `0x180005d80`
- `0x180006530`
- `0x1800087a0`
- `0x18000ac38`
- `0x18000b604`
- `0x18000e16c`

## callees

- `0x180005104`
- `0x1800091a0`
- `0x180009a7c`
- `0x180009bd0`
- `0x18000ea18`
- `0x18000eac0`
- `0x180017bc2`
- `0x180017bce`

## import_xrefs

- `KERNEL32!VirtualAlloc` at `0x180009648`
- `KERNEL32!VirtualAlloc` at `0x180009648`
- `KERNEL32!VirtualFree` at `0x18000962e`
- `KERNEL32!VirtualFree` at `0x18000962e`

## pseudocode

```c
__int64 __fastcall TiffSeekToPage(__int64 a1, unsigned int a2, int a3)
{
  __int64 v5; // rcx
  _QWORD *v6; // r12
  __int64 v7; // r9
  int v8; // r8d
  __int64 v9; // r10
  __int64 v10; // r11
  _DWORD *v11; // r14
  unsigned int v12; // r15d
  __int64 v13; // r13
  __int64 v14; // r10
  unsigned __int16 v15; // dx
  __int64 v16; // r8
  unsigned __int16 *v17; // rdi
  unsigned int v18; // eax
  __int64 v19; // r9
  unsigned int v20; // esi
  unsigned int *v21; // rbp
  unsigned int v22; // ecx
  unsigned int v23; // esi
  __int64 v24; // rbp
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  unsigned int v29; // ecx
  unsigned int v30; // edi
  unsigned int v31; // edx
  void *v32; // rcx
  LPVOID v33; // rax
  char *v35; // rdi
  unsigned int v36; // ebp
  unsigned int v37; // r9d
  char *v38; // rdx
  char *v39; // r8
  __int64 j; // r8
  unsigned int i; // [rsp+30h] [rbp-58h]
  __int64 v42; // [rsp+38h] [rbp-50h]
  unsigned __int16 v43; // [rsp+90h] [rbp+8h]
  int v46; // [rsp+A8h] [rbp+20h] BYREF

  v46 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
  }
  if ( a2 > *(_DWORD *)(a1 + 836) )
    return 0;
  if ( a2 == *(_DWORD *)(a1 + 1528) + 1 )
  {
    v5 = *(unsigned int *)(a1 + 844);
    v6 = (_QWORD *)(a1 + 16);
    LOWORD(v7) = *(_WORD *)(v5 + *(_QWORD *)(a1 + 16));
  }
  else
  {
    LODWORD(v5) = *(_DWORD *)(a1 + 568);
    if ( !(_DWORD)v5 )
      return 0;
    v8 = 0;
    v9 = *(_QWORD *)(a1 + 16);
    do
    {
      ++v8;
      v6 = (_QWORD *)(a1 + 16);
      v7 = *(unsigned __int16 *)((unsigned int)v5 + v9);
      if ( v8 == a2 )
        break;
      LODWORD(v5) = *(_DWORD *)((unsigned int)v5 + 12 * v7 + v9 + 2);
    }
    while ( (_DWORD)v5 );
  }
  if ( !(_DWORD)v5 )
    return 0;
  v10 = a1 + 1628;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = (unsigned int)v5 + *v6 + 2LL;
  v42 = v14;
  v15 = 0;
  v16 = a1 + 1624;
  *(_DWORD *)(a1 + 844) = *(_DWORD *)((unsigned int)v5 + 12LL * (unsigned __int16)v7 + *v6 + 2);
  *(_DWORD *)(a1 + 1628) = 1;
  *(_DWORD *)(a1 + 1624) = 0;
  for ( i = (unsigned __int16)v7; (unsigned int)v13 < i; v13 = (unsigned int)(v13 + 1) )
  {
    v17 = (unsigned __int16 *)(v14 + 12 * v13);
    v18 = *v17;
    v43 = v18;
    if ( (unsigned __int16)v18 < v15 )
      goto LABEL_74;
    if ( v18 > 0x111 )
    {
      if ( v18 == 278 )
      {
        *(_QWORD *)(a1 + 1640) = v17;
        v19 = a1 + 1556;
        goto LABEL_64;
      }
      if ( v18 != 279 )
      {
        if ( v18 == 282 )
        {
          v19 = a1 + 1688;
        }
        else
        {
          if ( v18 != 283 )
          {
            if ( v18 == 292 )
            {
              if ( !(unsigned int)GetTagData(a1, 0, v14 + 12 * v13, &v46) )
                goto LABEL_74;
              v16 = a1 + 1624;
              v14 = v42;
              v10 = a1 + 1628;
              if ( (v46 & 1) != 0 )
              {
                if ( *(_DWORD *)(a1 + 852) != 4 )
                  *(_DWORD *)(a1 + 852) = 3;
              }
              else if ( (v46 & 2) != 0 )
              {
                *(_DWORD *)(a1 + 852) = 1;
              }
            }
            goto LABEL_66;
          }
          v19 = a1 + 1684;
        }
        goto LABEL_64;
      }
      if ( !v11 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
        }
        return 0;
      }
      if ( v12 != *((_DWORD *)v17 + 1) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids,
            v12,
            *((_DWORD *)v17 + 1));
        }
        goto LABEL_75;
      }
      v23 = 0;
      *(_QWORD *)(a1 + 1648) = v17;
      if ( *((_DWORD *)v17 + 1) )
      {
        while ( 1 )
        {
          v24 = 4LL * v23;
          if ( !(unsigned int)GetTagData(a1, v23, v17, &v11[v24 + 1]) )
            goto LABEL_75;
          v25 = (unsigned int)v11[v24 + 1];
          v26 = *(unsigned int *)(a1 + 1664);
          v27 = v25 + (unsigned int)v11[4 * v23];
          if ( v27 > v26 )
          {
            v28 = v27 - v26;
            if ( v28 >= v25 )
              goto LABEL_75;
            v11[v24 + 1] = v25 - v28;
          }
          if ( ++v23 >= *((_DWORD *)v17 + 1) )
            goto LABEL_65;
        }
      }
    }
    else
    {
      switch ( v18 )
      {
        case 0x111u:
          v12 = *((_DWORD *)v17 + 1);
          if ( v12 > 0x2FAF08 )
            goto LABEL_74;
          v11 = (_DWORD *)pMemAlloc(16LL * v12);
          if ( !v11 )
            return 0;
          v20 = 0;
          if ( *((_DWORD *)v17 + 1) )
          {
            while ( 1 )
            {
              v21 = &v11[4 * v20];
              if ( !(unsigned int)GetTagData(a1, v20, v17, v21) )
                goto LABEL_75;
              v22 = *v21;
              *((_QWORD *)v21 + 1) = *v6 + *v21;
              ++v20;
              *(_DWORD *)(a1 + 1560) = v22;
              if ( v20 >= *((_DWORD *)v17 + 1) )
                goto LABEL_65;
            }
          }
          goto LABEL_65;
        case 0x100u:
          if ( !(unsigned int)GetTagData(a1, 0, v14 + 12 * v13, a1 + 1564) )
            goto LABEL_74;
          *(_DWORD *)(a1 + 1692) = (*(_DWORD *)(a1 + 1564) >> 3) + ((*(_DWORD *)(a1 + 1564) & 7) != 0);
          goto LABEL_65;
        case 0x101u:
          *(_QWORD *)(a1 + 1632) = v17;
          v19 = a1 + 1568;
          goto LABEL_64;
        case 0x103u:
          if ( !(unsigned int)GetTagData(a1, 0, v14 + 12 * v13, &v46) )
            goto LABEL_74;
          switch ( v46 )
          {
            case 1:
              *(_DWORD *)(a1 + 852) = 1;
              break;
            case 2:
            case 3:
              *(_DWORD *)(a1 + 852) = 2;
              break;
            case 4:
              *(_DWORD *)(a1 + 852) = 4;
              break;
            default:
              goto LABEL_74;
          }
LABEL_65:
          v14 = v42;
          v10 = a1 + 1628;
          v16 = a1 + 1624;
          break;
        case 0x106u:
          v19 = v16;
LABEL_64:
          if ( !(unsigned int)GetTagData(a1, 0, v14 + 12 * v13, v19) )
            goto LABEL_74;
          goto LABEL_65;
        case 0x10Au:
          *(_QWORD *)(a1 + 1656) = v17;
          v19 = v10;
          goto LABEL_64;
      }
    }
LABEL_66:
    v15 = v43;
  }
  v29 = 0;
  v30 = 0;
  if ( v12 )
  {
    while ( 1 )
    {
      v31 = v30 + v11[4 * v29 + 1];
      if ( v31 < v30 )
        break;
      ++v29;
      v30 = v31;
      if ( v29 >= v12 )
        goto LABEL_70;
    }
LABEL_74:
    if ( v11 )
LABEL_75:
      pMemFree(v11);
    return 0;
  }
LABEL_70:
  v32 = *(void **)(a1 + 1536);
  if ( v30 < *(_DWORD *)(a1 + 1552) )
  {
    if ( v32 )
      memset_0(v32, 0, *(unsigned int *)(a1 + 1552));
  }
  else
  {
    if ( v32 )
      VirtualFree(v32, 0, 0x8000u);
    *(_DWORD *)(a1 + 1552) = v30;
    v33 = VirtualAlloc(0, v30, 0x1000u, 4u);
    *(_QWORD *)(a1 + 1536) = v33;
    if ( !v33 )
      goto LABEL_74;
  }
  v35 = *(char **)(a1 + 1536);
  v36 = 0;
  if ( v12 )
  {
    do
    {
      v37 = v11[4 * v36 + 1];
      if ( v37 )
      {
        v38 = *(char **)&v11[4 * v36 + 2];
        v39 = &v38[v37 - 1];
        if ( v39 < v38 || (unsigned __int64)v39 < *v6 || (unsigned __int64)&v39[-*v6] > *(unsigned int *)(a1 + 1664) )
          goto LABEL_74;
        memcpy_0(v35, v38, v37);
        v35 += (unsigned int)v11[4 * v36 + 1];
      }
      ++v36;
    }
    while ( v36 < v12 );
    v35 = *(char **)(a1 + 1536);
  }
  if ( *(_DWORD *)(a1 + 1628) != a3 )
  {
    for ( j = 0; (unsigned int)j < *(_DWORD *)(a1 + 1552); j = (unsigned int)(j + 1) )
      v35[j] = *((_BYTE *)qword_18001B7D0 + (unsigned __int8)v35[j]);
  }
  *(_QWORD *)(a1 + 1544) = *(_QWORD *)(a1 + 1536);
  *(_DWORD *)(a1 + 1528) = a2;
  pMemFree(v11);
  return 1;
}

```

## disassembly

```asm
0x1800091a0  mov     rax, rsp
0x1800091a3  mov     [rax+18h], r8d
0x1800091a7  mov     [rax+10h], edx
0x1800091aa  push    rbx
0x1800091ab  push    rbp
0x1800091ac  push    rsi
0x1800091ad  push    rdi
0x1800091ae  push    r12
0x1800091b0  push    r13
0x1800091b2  push    r14
0x1800091b4  push    r15
0x1800091b6  sub     rsp, 48h
0x1800091ba  mov     edi, edx
0x1800091bc  mov     dword ptr [rax+20h], 0
0x1800091c3  mov     rbx, rcx
0x1800091c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091cd  lea     rsi, WPP_GLOBAL_Control
0x1800091d4  cmp     rcx, rsi
0x1800091d7  jz      short loc_1800091FA
0x1800091d9  test    byte ptr [rcx+1Ch], 2
0x1800091dd  jz      short loc_1800091FA
0x1800091df  cmp     byte ptr [rcx+19h], 5
0x1800091e3  jb      short loc_1800091FA
0x1800091e5  mov     rcx, [rcx+10h]
0x1800091e9  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x1800091f0  mov     edx, 12h
0x1800091f5  call    WPP_SF_
0x1800091fa  cmp     edi, [rbx+344h]
0x180009200  ja      loc_18000966B
0x180009206  mov     eax, [rbx+5F8h]
0x18000920c  mov     ebp, 1
0x180009211  add     eax, ebp
0x180009213  cmp     edi, eax
0x180009215  jnz     short loc_18000922C
0x180009217  mov     ecx, [rbx+34Ch]
0x18000921d  lea     r12, [rbx+10h]
0x180009221  mov     rax, [r12]
0x180009225  movzx   r9d, word ptr [rcx+rax]
0x18000922a  jmp     short loc_180009268
0x18000922c  mov     ecx, [rbx+238h]
0x180009232  test    ecx, ecx
0x180009234  jz      loc_18000966B
0x18000923a  lea     rdx, [rbx+10h]
0x18000923e  xor     r8d, r8d
0x180009241  mov     r10, [rdx]
0x180009244  mov     r11d, ecx
0x180009247  add     r8d, ebp
0x18000924a  mov     r12, rdx
0x18000924d  movzx   r9d, word ptr [r11+r10]
0x180009252  cmp     r8d, edi
0x180009255  jz      short loc_180009268
0x180009257  lea     rcx, [r9+r9*2]
0x18000925b  lea     rax, [r11+rcx*4]
0x18000925f  mov     ecx, [rax+r10+2]
0x180009264  test    ecx, ecx
0x180009266  jnz     short loc_180009244
0x180009268  test    ecx, ecx
0x18000926a  jz      loc_18000966B
0x180009270  mov     r8, [r12]
0x180009274  lea     r11, [rbx+65Ch]
0x18000927b  mov     edx, ecx
0x18000927d  xor     r14d, r14d
0x180009280  movzx   eax, r9w
0x180009284  xor     r15d, r15d
0x180009287  xor     r13d, r13d
0x18000928a  lea     r10, [r8+2]
0x18000928e  add     r10, rdx
0x180009291  lea     rcx, [rax+rax*2]
0x180009295  mov     [rsp+88h+var_50], r10
0x18000929a  lea     rax, [rdx+rcx*4]
0x18000929e  xor     edx, edx
0x1800092a0  mov     ecx, [rax+r8+2]
0x1800092a5  lea     r8, [rbx+658h]
0x1800092ac  movzx   eax, r9w
0x1800092b0  mov     [rbx+34Ch], ecx
0x1800092b6  mov     [r11], ebp
0x1800092b9  mov     [r8], r14d
0x1800092bc  mov     [rsp+88h+var_58], eax
0x1800092c0  test    eax, eax
0x1800092c2  jz      loc_1800095EA
0x1800092c8  lea     rcx, ds:0[r13*2]
0x1800092d0  add     rcx, r13
0x1800092d3  lea     rdi, [r10+rcx*4]
0x1800092d7  movzx   eax, word ptr [rdi]
0x1800092da  mov     [rsp+88h+arg_0], ax
0x1800092e2  cmp     ax, dx
0x1800092e5  jb      loc_18000965E
0x1800092eb  mov     ecx, eax
0x1800092ed  cmp     eax, 111h
0x1800092f2  ja      loc_18000946A
0x1800092f8  jz      loc_1800093F1
0x1800092fe  sub     ecx, 100h
0x180009304  jz      loc_1800093B5
0x18000930a  sub     ecx, 1
0x18000930d  jz      loc_1800093A2
0x180009313  sub     ecx, 2
0x180009316  jz      short loc_18000933D
0x180009318  sub     ecx, 3
0x18000931b  jz      short loc_180009335
0x18000931d  cmp     ecx, 4
0x180009320  jnz     loc_1800095D4
0x180009326  mov     [rbx+678h], rdi
0x18000932d  mov     r9, r11
0x180009330  jmp     loc_1800095AC
0x180009335  mov     r9, r8
0x180009338  jmp     loc_1800095AC
0x18000933d  lea     r9, [rsp+88h+arg_18]
0x180009345  mov     r8, rdi
0x180009348  xor     edx, edx
0x18000934a  mov     rcx, rbx
0x18000934d  call    GetTagData
0x180009352  test    eax, eax
0x180009354  jz      loc_18000965E
0x18000935a  mov     eax, [rsp+88h+arg_18]
0x180009361  sub     eax, 1
0x180009364  jz      short loc_180009397
0x180009366  sub     eax, 1
0x180009369  jz      short loc_180009388
0x18000936b  sub     eax, 1
0x18000936e  jz      short loc_180009388
0x180009370  cmp     eax, 1
0x180009373  jnz     loc_18000965E
0x180009379  mov     dword ptr [rbx+354h], 4
0x180009383  jmp     loc_1800095C1
0x180009388  mov     dword ptr [rbx+354h], 2
0x180009392  jmp     loc_1800095C1
0x180009397  mov     [rbx+354h], ebp
0x18000939d  jmp     loc_1800095C1
0x1800093a2  mov     [rbx+660h], rdi
0x1800093a9  lea     r9, [rbx+620h]
0x1800093b0  jmp     loc_1800095AC
0x1800093b5  lea     rsi, [rbx+61Ch]
0x1800093bc  mov     r8, rdi
0x1800093bf  mov     r9, rsi
0x1800093c2  xor     edx, edx
0x1800093c4  mov     rcx, rbx
0x1800093c7  call    GetTagData
0x1800093cc  test    eax, eax
0x1800093ce  jz      loc_18000965E
0x1800093d4  mov     ecx, [rsi]
0x1800093d6  mov     eax, 0
0x1800093db  test    cl, 7
0x1800093de  setnz   al
0x1800093e1  shr     ecx, 3
0x1800093e4  add     eax, ecx
0x1800093e6  mov     [rbx+69Ch], eax
0x1800093ec  jmp     loc_1800095C1
0x1800093f1  mov     r15d, [rdi+4]
0x1800093f5  cmp     r15d, 2FAF08h
0x1800093fc  ja      loc_18000965E
0x180009402  mov     ecx, r15d
0x180009405  shl     rcx, 4; dwBytes
0x180009409  call    pMemAlloc
0x18000940e  mov     r14, rax
0x180009411  test    rax, rax
0x180009414  jz      loc_18000966B
0x18000941a  xor     esi, esi
0x18000941c  cmp     [rdi+4], esi
0x18000941f  jbe     loc_1800095C1
0x180009425  mov     ebp, esi
0x180009427  mov     r8, rdi
0x18000942a  shl     rbp, 4
0x18000942e  mov     edx, esi
0x180009430  add     rbp, r14
0x180009433  mov     rcx, rbx
0x180009436  mov     r9, rbp
0x180009439  call    GetTagData
0x18000943e  test    eax, eax
0x180009440  jz      loc_180009663
0x180009446  mov     ecx, [rbp+0]
0x180009449  mov     eax, ecx
0x18000944b  add     rax, [r12]
0x18000944f  mov     [rbp+8], rax
0x180009453  mov     ebp, 1
0x180009458  add     esi, ebp
0x18000945a  mov     [rbx+618h], ecx
0x180009460  cmp     esi, [rdi+4]
0x180009463  jb      short loc_180009425
0x180009465  jmp     loc_1800095C1
0x18000946a  sub     ecx, 116h
0x180009470  jz      loc_18000959E
0x180009476  sub     ecx, 1
0x180009479  jz      loc_18000951D
0x18000947f  sub     ecx, 3
0x180009482  jz      loc_180009511
0x180009488  sub     ecx, 1
0x18000948b  jz      short loc_180009505
0x18000948d  cmp     ecx, 9
0x180009490  jnz     loc_1800095D4
0x180009496  lea     r9, [rsp+88h+arg_18]
0x18000949e  mov     r8, rdi
0x1800094a1  xor     edx, edx
0x1800094a3  mov     rcx, rbx
0x1800094a6  call    GetTagData
0x1800094ab  test    eax, eax
0x1800094ad  jz      loc_18000965E
0x1800094b3  lea     r8, [rbx+658h]
0x1800094ba  mov     r10, [rsp+88h+var_50]
0x1800094bf  lea     r11, [rbx+65Ch]
0x1800094c6  test    byte ptr [rsp+88h+arg_18], bpl
0x1800094ce  jz      short loc_1800094EC
0x1800094d0  cmp     dword ptr [rbx+354h], 4
0x1800094d7  jz      loc_1800095D4
0x1800094dd  mov     dword ptr [rbx+354h], 3
0x1800094e7  jmp     loc_1800095D4
0x1800094ec  test    byte ptr [rsp+88h+arg_18], 2
0x1800094f4  jz      loc_1800095D4
0x1800094fa  mov     [rbx+354h], ebp
0x180009500  jmp     loc_1800095D4
0x180009505  lea     r9, [rbx+694h]
0x18000950c  jmp     loc_1800095AC
0x180009511  lea     r9, [rbx+698h]
0x180009518  jmp     loc_1800095AC
0x18000951d  test    r14, r14
0x180009520  jz      loc_1800096BB
0x180009526  mov     eax, [rdi+4]
0x180009529  cmp     r15d, eax
0x18000952c  jnz     loc_18000967E
0x180009532  xor     esi, esi
0x180009534  mov     [rbx+670h], rdi
0x18000953b  cmp     [rdi+4], esi
0x18000953e  jbe     loc_1800095D4
0x180009544  mov     ebp, esi
0x180009546  mov     r8, rdi
0x180009549  shl     rbp, 4
0x18000954d  mov     edx, esi
0x18000954f  mov     rcx, rbx
0x180009552  lea     r9, [rbp+4]
0x180009556  add     r9, r14
0x180009559  call    GetTagData
0x18000955e  test    eax, eax
0x180009560  jz      loc_180009663
0x180009566  mov     ecx, [r14+rbp+4]
0x18000956b  mov     edx, [r14+rbp]
0x18000956f  mov     eax, [rbx+680h]
0x180009575  add     rdx, rcx
0x180009578  cmp     rdx, rax
0x18000957b  jbe     short loc_180009590
0x18000957d  sub     rdx, rax
0x180009580  cmp     rdx, rcx
0x180009583  jnb     loc_180009663
0x180009589  sub     ecx, edx
0x18000958b  mov     [r14+rbp+4], ecx
0x180009590  mov     ebp, 1
0x180009595  add     esi, ebp
0x180009597  cmp     esi, [rdi+4]
0x18000959a  jb      short loc_180009544
0x18000959c  jmp     short loc_1800095C1
0x18000959e  mov     [rbx+668h], rdi
0x1800095a5  lea     r9, [rbx+614h]
0x1800095ac  mov     r8, rdi
0x1800095af  xor     edx, edx
0x1800095b1  mov     rcx, rbx
0x1800095b4  call    GetTagData
0x1800095b9  test    eax, eax
0x1800095bb  jz      loc_18000965E
0x1800095c1  mov     r10, [rsp+88h+var_50]
0x1800095c6  lea     r11, [rbx+65Ch]
0x1800095cd  lea     r8, [rbx+658h]
0x1800095d4  movzx   edx, [rsp+88h+arg_0]
0x1800095dc  add     r13d, ebp
0x1800095df  cmp     r13d, [rsp+88h+var_58]
0x1800095e4  jb      loc_1800092C8
0x1800095ea  xor     ecx, ecx
0x1800095ec  xor     edi, edi
0x1800095ee  test    r15d, r15d
0x1800095f1  jz      short loc_18000960C
0x1800095f3  mov     eax, ecx
0x1800095f5  add     rax, rax
0x1800095f8  mov     edx, [r14+rax*8+4]
0x1800095fd  add     edx, edi
0x1800095ff  cmp     edx, edi
0x180009601  jb      short loc_18000965E
0x180009603  add     ecx, ebp
0x180009605  mov     edi, edx
0x180009607  cmp     ecx, r15d
0x18000960a  jb      short loc_1800095F3
0x18000960c  mov     eax, [rbx+610h]
0x180009612  mov     rcx, [rbx+600h]; void *
0x180009619  cmp     edi, eax
0x18000961b  jb      loc_1800096F4
0x180009621  test    rcx, rcx
0x180009624  jz      short loc_180009634
0x180009626  xor     edx, edx; dwSize
0x180009628  mov     r8d, 8000h; dwFreeType
0x18000962e  call    cs:__imp_VirtualFree
0x180009634  xor     ecx, ecx; lpAddress
0x180009636  mov     edx, edi; dwSize
0x180009638  mov     r8d, 1000h; flAllocationType
0x18000963e  mov     [rbx+610h], edi
0x180009644  lea     r9d, [rcx+4]; flProtect
0x180009648  call    cs:__imp_VirtualAlloc
0x18000964e  mov     [rbx+600h], rax
0x180009655  test    rax, rax
0x180009658  jnz     loc_180009703
0x18000965e  test    r14, r14
0x180009661  jz      short loc_18000966B
0x180009663  mov     rcx, r14; lpMem
0x180009666  call    pMemFree
0x18000966b  xor     eax, eax
  ... truncated ...
```
