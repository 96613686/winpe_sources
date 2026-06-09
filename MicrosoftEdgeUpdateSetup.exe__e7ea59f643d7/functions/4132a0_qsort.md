# _qsort

- ea: `0x4132a0`
- end: `0x41378e`
- name: `_qsort`
- size: `1262`
- prototype: `void __cdecl(void *Base, size_t NumOfElements, size_t SizeOfElements, _CoreCrtNonSecureSearchSortCompareFunction CompareFunction)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x40f1e6`

## callees

- `0x405810`
- `0x408c05`
- `0x40ec26`
- `0x40ece3`
- `0x4132a0`

## pseudocode

```c
void __cdecl qsort(
        void *Base,
        size_t NumOfElements,
        size_t SizeOfElements,
        _CoreCrtNonSecureSearchSortCompareFunction CompareFunction)
{
  _CoreCrtNonSecureSearchSortCompareFunction v4; // ebx
  char *v5; // esi
  size_t v6; // edi
  char *v7; // ecx
  unsigned int v8; // eax
  char *v9; // edx
  char *v10; // eax
  char *v11; // esi
  char *v12; // edx
  int v13; // eax
  size_t v14; // ebx
  char v15; // cl
  char *v16; // edi
  int v17; // eax
  size_t v18; // esi
  bool v19; // cc
  char *v20; // eax
  size_t v21; // ebx
  char *v22; // esi
  char v23; // cl
  int v24; // eax
  char *v25; // edx
  char *v26; // esi
  size_t v27; // ebx
  char *v28; // edx
  char v29; // al
  char v30; // cl
  int v31; // eax
  char *v32; // edx
  size_t v33; // eax
  size_t v34; // ebx
  char *v35; // esi
  char *v36; // edx
  char v37; // al
  char v38; // cl
  char *v39; // ebx
  int v40; // eax
  char *v41; // ecx
  char *v42; // edx
  int v43; // esi
  size_t v44; // ebx
  char v45; // al
  char v46; // cl
  int v47; // eax
  bool v48; // zf
  char *v49; // ecx
  int v50; // eax
  int v51; // eax
  int v52; // [esp+Ch] [ebp-118h]
  char *v53; // [esp+10h] [ebp-114h]
  size_t v54; // [esp+10h] [ebp-114h]
  char *v55; // [esp+14h] [ebp-110h]
  char *v56; // [esp+18h] [ebp-10Ch]
  char *v57; // [esp+20h] [ebp-104h]
  char *v58; // [esp+28h] [ebp-FCh]
  int v59; // [esp+28h] [ebp-FCh]
  int v60; // [esp+28h] [ebp-FCh]
  char *v61; // [esp+28h] [ebp-FCh]
  char *v62; // [esp+28h] [ebp-FCh]
  char *v63; // [esp+28h] [ebp-FCh]
  char *v64; // [esp+2Ch] [ebp-F8h]
  _DWORD v65[60]; // [esp+30h] [ebp-F4h]

  v4 = CompareFunction;
  v5 = (char *)Base;
  v57 = (char *)Base;
  v6 = SizeOfElements;
  if ( (Base || !NumOfElements) && SizeOfElements && CompareFunction )
  {
    v52 = 0;
    if ( NumOfElements >= 2 )
    {
      v7 = (char *)Base + SizeOfElements * (NumOfElements - 1);
      while ( 2 )
      {
        while ( 2 )
        {
          v64 = v7;
          while ( 1 )
          {
            v8 = (v7 - v5) / v6 + 1;
            if ( v8 <= 8 )
            {
              if ( v7 > v5 )
              {
                v9 = &v5[v6];
                v55 = &v5[v6];
                do
                {
                  v10 = v5;
                  v11 = v9;
                  v58 = v10;
                  if ( v9 <= v7 )
                  {
                    do
                    {
                      if ( v4(v11, v10) <= 0 )
                      {
                        v10 = v58;
                      }
                      else
                      {
                        v10 = v11;
                        v58 = v11;
                      }
                      v7 = v64;
                      v11 += v6;
                    }
                    while ( v11 <= v64 );
                  }
                  v12 = v7;
                  if ( v10 != v7 )
                  {
                    v13 = v10 - v7;
                    v14 = v6;
                    v59 = v13;
                    do
                    {
                      v15 = (v12++)[v13];
                      v12[v59 - 1] = *(v12 - 1);
                      v13 = v59;
                      *(v12 - 1) = v15;
                      --v14;
                    }
                    while ( v14 );
                    v4 = CompareFunction;
                    v7 = v64;
                  }
                  v5 = v57;
                  v7 -= v6;
                  v9 = v55;
                  v64 = v7;
                }
                while ( v7 > v57 );
              }
              goto LABEL_77;
            }
            v60 = v6 * (v8 >> 1);
            v16 = &v5[v60];
            v53 = &v5[v60];
            v17 = v4(v5, &v5[v60]);
            v18 = SizeOfElements;
            v19 = v17 <= 0;
            v20 = v57;
            if ( !v19 && v57 != v16 )
            {
              v21 = SizeOfElements;
              v22 = v16;
              do
              {
                v23 = v22[-v60];
                v22[-v60] = *v22;
                *v22++ = v23;
                --v21;
              }
              while ( v21 );
              v16 = v53;
              v4 = CompareFunction;
              v18 = SizeOfElements;
              v20 = v57;
            }
            v24 = v4(v20, v64);
            v25 = v64;
            if ( v24 > 0 )
            {
              v54 = v18;
              v26 = v64;
              if ( v57 != v64 )
              {
                v27 = v54;
                v28 = (char *)(v57 - v64);
                do
                {
                  v29 = *v26++;
                  v30 = v26[(_DWORD)v28 - 1];
                  v26[(_DWORD)v28 - 1] = v29;
                  *(v26 - 1) = v30;
                  --v27;
                }
                while ( v27 );
                v4 = CompareFunction;
                v25 = v64;
              }
            }
            v31 = v4(v16, v25);
            v32 = v64;
            v19 = v31 <= 0;
            v33 = SizeOfElements;
            if ( !v19 )
            {
              v34 = SizeOfElements;
              v35 = v64;
              if ( v16 != v64 )
              {
                v36 = (char *)(v16 - v64);
                do
                {
                  v37 = *v35++;
                  v38 = v35[(_DWORD)v36 - 1];
                  v35[(_DWORD)v36 - 1] = v37;
                  *(v35 - 1) = v38;
                  --v34;
                }
                while ( v34 );
                v33 = SizeOfElements;
                v32 = v64;
              }
            }
            v5 = v57;
            v39 = v32;
            v61 = v32;
            while ( 1 )
            {
              if ( v16 > v5 )
              {
                while ( 1 )
                {
                  v5 += v33;
                  v56 = v5;
                  if ( v5 >= v16 )
                    break;
                  v19 = CompareFunction(v5, v16) <= 0;
                  v33 = SizeOfElements;
                  if ( !v19 )
                    goto LABEL_48;
                }
                v32 = v64;
              }
              do
              {
                v5 += v33;
                if ( v5 > v32 )
                  break;
                v40 = CompareFunction(v5, v16);
                v32 = v64;
                v19 = v40 <= 0;
                v33 = SizeOfElements;
              }
              while ( v19 );
              v39 = v61;
              v56 = v5;
LABEL_48:
              while ( 1 )
              {
                v33 = SizeOfElements;
                v41 = v39;
                v39 -= SizeOfElements;
                v62 = v41;
                if ( v39 <= v16 )
                  break;
                if ( CompareFunction(v39, v16) <= 0 )
                {
                  v33 = SizeOfElements;
                  v41 = v62;
                  break;
                }
              }
              v5 = v56;
              v61 = v39;
              if ( v39 < v56 )
                break;
              v42 = v39;
              if ( v39 != v56 )
              {
                v43 = v56 - v39;
                v44 = v33;
                do
                {
                  v45 = *v42++;
                  v46 = v42[v43 - 1];
                  v42[v43 - 1] = v45;
                  *(v42 - 1) = v46;
                  --v44;
                }
                while ( v44 );
                v5 = v56;
                v39 = v61;
                v33 = SizeOfElements;
              }
              v32 = v64;
              if ( v16 == v39 )
                v16 = v5;
            }
            if ( v16 < v41 )
            {
              v4 = CompareFunction;
              while ( 1 )
              {
                v41 -= v33;
                v63 = v41;
                if ( v41 <= v16 )
                  break;
                v47 = CompareFunction(v41, v16);
                v41 = v63;
                v48 = v47 == 0;
                v33 = SizeOfElements;
                if ( !v48 )
                  goto LABEL_67;
              }
            }
            v4 = CompareFunction;
            do
            {
              v49 = &v41[-v33];
              v63 = v49;
              if ( v49 <= v57 )
                break;
              v50 = CompareFunction(v49, v16);
              v41 = v63;
              v48 = v50 == 0;
              v33 = SizeOfElements;
            }
            while ( v48 );
            v5 = v56;
LABEL_67:
            if ( v63 - v57 < v64 - v5 )
              break;
            if ( v57 < v63 )
            {
              v65[v52 + 30] = v57;
              v65[v52++] = v63;
            }
            v7 = v64;
            v6 = SizeOfElements;
            if ( v5 >= v64 )
              goto LABEL_77;
            v57 = v5;
          }
          if ( v5 < v64 )
          {
            v65[v52 + 30] = v5;
            v65[v52++] = v64;
          }
          v5 = v57;
          if ( v57 < v63 )
          {
            v7 = v63;
            v6 = SizeOfElements;
            continue;
          }
          break;
        }
        v6 = SizeOfElements;
LABEL_77:
        v51 = --v52;
        if ( v52 >= 0 )
        {
          v5 = (char *)v65[v51 + 30];
          v7 = (char *)v65[v51];
          v57 = v5;
          continue;
        }
        break;
      }
    }
  }
  else
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
  }
}

```

## disassembly

```asm
0x4132a0  mov     edi, edi
0x4132a2  push    ebp
0x4132a3  mov     ebp, esp
0x4132a5  sub     esp, 118h
0x4132ab  mov     eax, ___security_cookie
0x4132b0  xor     eax, ebp
0x4132b2  mov     [ebp+var_4], eax
0x4132b5  mov     ecx, [ebp+NumOfElements]
0x4132b8  push    ebx
0x4132b9  mov     ebx, [ebp+CompareFunction]
0x4132bc  push    esi
0x4132bd  mov     esi, [ebp+Base]
0x4132c0  mov     [ebp+var_104], esi
0x4132c6  mov     [ebp+var_108], ebx
0x4132cc  push    edi
0x4132cd  mov     edi, [ebp+SizeOfElements]
0x4132d0  mov     [ebp+var_100], edi
0x4132d6  test    esi, esi
0x4132d8  jnz     short loc_4132FF
0x4132da  test    ecx, ecx
0x4132dc  jz      short loc_4132FF
0x4132de  call    __errno
0x4132e3  mov     dword ptr [eax], 16h
0x4132e9  call    __invalid_parameter_noinfo
0x4132ee  mov     ecx, [ebp+var_4]
0x4132f1  pop     edi
0x4132f2  pop     esi
0x4132f3  xor     ecx, ebp; StackCookie
0x4132f5  pop     ebx
0x4132f6  call    @__security_check_cookie@4
0x4132fb  mov     esp, ebp
0x4132fd  pop     ebp
0x4132fe  retn
0x4132ff  test    edi, edi
0x413301  jz      short loc_4132DE
0x413303  test    ebx, ebx
0x413305  jz      short loc_4132DE
0x413307  mov     [ebp+var_118], 0
0x413311  cmp     ecx, 2
0x413314  jb      short loc_4132EE
0x413316  dec     ecx
0x413317  imul    ecx, edi
0x41331a  add     ecx, esi
0x41331c  mov     [ebp+var_F8], ecx
0x413322  mov     eax, ecx
0x413324  xor     edx, edx
0x413326  sub     eax, esi
0x413328  div     edi
0x41332a  inc     eax
0x41332b  cmp     eax, 8
0x41332e  ja      loc_4133EA
0x413334  cmp     ecx, esi
0x413336  jbe     loc_413763
0x41333c  lea     edx, [edi+esi]
0x41333f  mov     [ebp+var_110], edx
0x413345  mov     eax, esi
0x413347  mov     esi, edx
0x413349  mov     [ebp+var_FC], eax
0x41334f  cmp     esi, ecx
0x413351  ja      short loc_413382
0x413353  push    eax
0x413354  push    esi
0x413355  mov     ecx, ebx
0x413357  call    ds:___guard_check_icall_fptr
0x41335d  call    ebx
0x41335f  add     esp, 8
0x413362  test    eax, eax
0x413364  jle     short loc_413370
0x413366  mov     eax, esi
0x413368  mov     [ebp+var_FC], eax
0x41336e  jmp     short loc_413376
0x413370  mov     eax, [ebp+var_FC]
0x413376  mov     ecx, [ebp+var_F8]
0x41337c  add     esi, edi
0x41337e  cmp     esi, ecx
0x413380  jbe     short loc_413353
0x413382  mov     [ebp+var_10C], edi
0x413388  mov     edx, ecx
0x41338a  cmp     eax, ecx
0x41338c  jz      short loc_4133C9
0x41338e  sub     eax, ecx
0x413390  mov     ebx, edi
0x413392  mov     [ebp+var_FC], eax
0x413398  jmp     short loc_4133A0
0x4133a0  mov     cl, [eax+edx]
0x4133a3  lea     edx, [edx+1]
0x4133a6  mov     esi, [ebp+var_FC]
0x4133ac  mov     al, [edx-1]
0x4133af  mov     [esi+edx-1], al
0x4133b3  mov     eax, esi
0x4133b5  mov     [edx-1], cl
0x4133b8  sub     ebx, 1
0x4133bb  jnz     short loc_4133A0
0x4133bd  mov     ebx, [ebp+var_108]
0x4133c3  mov     ecx, [ebp+var_F8]
0x4133c9  mov     esi, [ebp+var_104]
0x4133cf  sub     ecx, edi
0x4133d1  mov     edx, [ebp+var_110]
0x4133d7  mov     [ebp+var_F8], ecx
0x4133dd  cmp     ecx, esi
0x4133df  ja      loc_413345
0x4133e5  jmp     loc_413763
0x4133ea  shr     eax, 1
0x4133ec  mov     ecx, ebx
0x4133ee  imul    eax, edi
0x4133f1  mov     [ebp+var_FC], eax
0x4133f7  lea     edi, [eax+esi]
0x4133fa  push    edi
0x4133fb  push    esi
0x4133fc  mov     [ebp+var_114], edi
0x413402  call    ds:___guard_check_icall_fptr
0x413408  call    ebx
0x41340a  mov     esi, [ebp+var_100]
0x413410  add     esp, 8
0x413413  test    eax, eax
0x413415  mov     eax, [ebp+var_104]
0x41341b  jle     short loc_41346A
0x41341d  mov     [ebp+var_10C], esi
0x413423  mov     [ebp+var_110], edi
0x413429  cmp     eax, edi
0x41342b  jz      short loc_41346A
0x41342d  mov     ebx, [ebp+var_10C]
0x413433  mov     esi, edi
0x413435  mov     edi, [ebp+var_FC]
0x41343b  jmp     short loc_413440
0x413440  mov     al, [esi]
0x413442  mov     edx, esi
0x413444  sub     edx, edi
0x413446  mov     cl, [edx]
0x413448  mov     [edx], al
0x41344a  mov     [esi], cl
0x41344c  inc     esi
0x41344d  sub     ebx, 1
0x413450  jnz     short loc_413440
0x413452  mov     edi, [ebp+var_114]
0x413458  mov     ebx, [ebp+var_108]
0x41345e  mov     esi, [ebp+var_100]
0x413464  mov     eax, [ebp+var_104]
0x41346a  push    [ebp+var_F8]
0x413470  mov     ecx, ebx
0x413472  push    eax
0x413473  call    ds:___guard_check_icall_fptr
0x413479  call    ebx
0x41347b  mov     edx, [ebp+var_F8]
0x413481  add     esp, 8
0x413484  test    eax, eax
0x413486  jle     short loc_4134D1
0x413488  mov     eax, [ebp+var_104]
0x41348e  mov     [ebp+var_114], esi
0x413494  mov     esi, edx
0x413496  cmp     eax, edx
0x413498  jz      short loc_4134D1
0x41349a  mov     ebx, [ebp+var_114]
0x4134a0  sub     eax, edx
0x4134a2  mov     [ebp+var_110], eax
0x4134a8  mov     edx, eax
0x4134aa  lea     ebx, [ebx+0]
0x4134b0  mov     al, [esi]
0x4134b2  lea     esi, [esi+1]
0x4134b5  mov     cl, [edx+esi-1]
0x4134b9  mov     [edx+esi-1], al
0x4134bd  mov     [esi-1], cl
0x4134c0  sub     ebx, 1
0x4134c3  jnz     short loc_4134B0
0x4134c5  mov     ebx, [ebp+var_108]
0x4134cb  mov     edx, [ebp+var_F8]
0x4134d1  push    edx
0x4134d2  push    edi
0x4134d3  mov     ecx, ebx
0x4134d5  call    ds:___guard_check_icall_fptr
0x4134db  call    ebx
0x4134dd  mov     edx, [ebp+var_F8]
0x4134e3  add     esp, 8
0x4134e6  test    eax, eax
0x4134e8  mov     eax, [ebp+var_100]
0x4134ee  jle     short loc_413525
0x4134f0  mov     ebx, eax
0x4134f2  mov     esi, edx
0x4134f4  cmp     edi, edx
0x4134f6  jz      short loc_413525
0x4134f8  mov     eax, edi
0x4134fa  sub     eax, edx
0x4134fc  mov     [ebp+var_114], eax
0x413502  mov     edx, eax
0x413504  mov     al, [esi]
0x413506  lea     esi, [esi+1]
0x413509  mov     cl, [edx+esi-1]
0x41350d  mov     [edx+esi-1], al
0x413511  mov     [esi-1], cl
0x413514  sub     ebx, 1
0x413517  jnz     short loc_413504
0x413519  mov     eax, [ebp+var_100]
0x41351f  mov     edx, [ebp+var_F8]
0x413525  mov     esi, [ebp+var_104]
0x41352b  mov     ebx, edx
0x41352d  mov     [ebp+var_FC], edx
0x413533  cmp     edi, esi
0x413535  jbe     short loc_413575
0x413537  jmp     short loc_413540
0x413540  add     esi, eax
0x413542  mov     [ebp+var_10C], esi
0x413548  cmp     esi, edi
0x41354a  jnb     short loc_41356F
0x41354c  mov     ecx, [ebp+var_108]
0x413552  push    edi
0x413553  push    esi
0x413554  call    ds:___guard_check_icall_fptr
0x41355a  call    [ebp+var_108]
0x413560  add     esp, 8
0x413563  test    eax, eax
0x413565  mov     eax, [ebp+var_100]
0x41356b  jle     short loc_413540
0x41356d  jmp     short loc_4135B1
0x41356f  mov     edx, [ebp+var_F8]
0x413575  mov     ebx, [ebp+var_108]
0x41357b  jmp     short loc_413580
0x413580  add     esi, eax
0x413582  cmp     esi, edx
0x413584  ja      short loc_4135A5
0x413586  push    edi
0x413587  push    esi
0x413588  mov     ecx, ebx
0x41358a  call    ds:___guard_check_icall_fptr
0x413590  call    ebx
0x413592  mov     edx, [ebp+var_F8]
0x413598  add     esp, 8
0x41359b  test    eax, eax
0x41359d  mov     eax, [ebp+var_100]
0x4135a3  jle     short loc_413580
0x4135a5  mov     ebx, [ebp+var_FC]
0x4135ab  mov     [ebp+var_10C], esi
0x4135b1  mov     esi, [ebp+var_108]
0x4135b7  jmp     short loc_4135C0
0x4135c0  mov     eax, [ebp+var_100]
0x4135c6  mov     ecx, ebx
0x4135c8  sub     ebx, eax
0x4135ca  mov     [ebp+var_FC], ecx
0x4135d0  cmp     ebx, edi
0x4135d2  jbe     short loc_4135F3
0x4135d4  push    edi
0x4135d5  push    ebx
0x4135d6  mov     ecx, esi
0x4135d8  call    ds:___guard_check_icall_fptr
0x4135de  call    esi
0x4135e0  add     esp, 8
0x4135e3  test    eax, eax
0x4135e5  jg      short loc_4135C0
0x4135e7  mov     eax, [ebp+var_100]
0x4135ed  mov     ecx, [ebp+var_FC]
0x4135f3  mov     esi, [ebp+var_10C]
0x4135f9  mov     [ebp+var_FC], ebx
0x4135ff  cmp     ebx, esi
0x413601  jb      short loc_41364D
0x413603  mov     [ebp+var_110], eax
0x413609  mov     edx, ebx
0x41360b  jz      short loc_413638
0x41360d  sub     esi, ebx
0x41360f  mov     ebx, eax
0x413611  mov     al, [edx]
0x413613  lea     edx, [edx+1]
0x413616  mov     cl, [esi+edx-1]
0x41361a  mov     [esi+edx-1], al
0x41361e  mov     [edx-1], cl
0x413621  sub     ebx, 1
0x413624  jnz     short loc_413611
0x413626  mov     esi, [ebp+var_10C]
0x41362c  mov     ebx, [ebp+var_FC]
0x413632  mov     eax, [ebp+var_100]
0x413638  mov     edx, [ebp+var_F8]
0x41363e  cmp     edi, ebx
0x413640  jnz     loc_413533
0x413646  mov     edi, esi
0x413648  jmp     loc_413533
0x41364d  cmp     edi, ecx
0x41364f  jnb     short loc_41368D
0x413651  mov     ebx, [ebp+var_108]
0x413657  jmp     short loc_413660
0x413660  sub     ecx, eax
0x413662  mov     [ebp+var_FC], ecx
0x413668  cmp     ecx, edi
0x41366a  jbe     short loc_41368D
0x41366c  push    edi
0x41366d  push    ecx
0x41366e  mov     ecx, ebx
0x413670  call    ds:___guard_check_icall_fptr
0x413676  call    ebx
0x413678  mov     ecx, [ebp+var_FC]
0x41367e  add     esp, 8
0x413681  test    eax, eax
0x413683  mov     eax, [ebp+var_100]
0x413689  jz      short loc_413660
0x41368b  jmp     short loc_4136D1
0x41368d  mov     ebx, [ebp+var_108]
0x413693  mov     esi, [ebp+var_104]
0x413699  lea     esp, [esp+0]
0x4136a0  sub     ecx, eax
0x4136a2  mov     [ebp+var_FC], ecx
0x4136a8  cmp     ecx, esi
0x4136aa  jbe     short loc_4136CB
0x4136ac  push    edi
  ... truncated ...
```
