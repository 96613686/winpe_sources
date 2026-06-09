# _qsort

- ea: `0x417eb0`
- end: `0x41839e`
- name: `_qsort`
- size: `1262`
- prototype: `void __cdecl(void *Base, size_t NumOfElements, size_t SizeOfElements, _CoreCrtNonSecureSearchSortCompareFunction CompareFunction)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x414174`

## callees

- `0x402330`
- `0x40d08d`
- `0x410369`
- `0x410443`
- `0x417eb0`

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
0x417eb0  mov     edi, edi
0x417eb2  push    ebp
0x417eb3  mov     ebp, esp
0x417eb5  sub     esp, 118h
0x417ebb  mov     eax, ___security_cookie
0x417ec0  xor     eax, ebp
0x417ec2  mov     [ebp+var_4], eax
0x417ec5  mov     ecx, [ebp+NumOfElements]
0x417ec8  push    ebx
0x417ec9  mov     ebx, [ebp+CompareFunction]
0x417ecc  push    esi
0x417ecd  mov     esi, [ebp+Base]
0x417ed0  mov     [ebp+var_104], esi
0x417ed6  mov     [ebp+var_108], ebx
0x417edc  push    edi
0x417edd  mov     edi, [ebp+SizeOfElements]
0x417ee0  mov     [ebp+var_100], edi
0x417ee6  test    esi, esi
0x417ee8  jnz     short loc_417F0F
0x417eea  test    ecx, ecx
0x417eec  jz      short loc_417F0F
0x417eee  call    __errno
0x417ef3  mov     dword ptr [eax], 16h
0x417ef9  call    __invalid_parameter_noinfo
0x417efe  mov     ecx, [ebp+var_4]
0x417f01  pop     edi
0x417f02  pop     esi
0x417f03  xor     ecx, ebp; StackCookie
0x417f05  pop     ebx
0x417f06  call    @__security_check_cookie@4
0x417f0b  mov     esp, ebp
0x417f0d  pop     ebp
0x417f0e  retn
0x417f0f  test    edi, edi
0x417f11  jz      short loc_417EEE
0x417f13  test    ebx, ebx
0x417f15  jz      short loc_417EEE
0x417f17  mov     [ebp+var_118], 0
0x417f21  cmp     ecx, 2
0x417f24  jb      short loc_417EFE
0x417f26  dec     ecx
0x417f27  imul    ecx, edi
0x417f2a  add     ecx, esi
0x417f2c  mov     [ebp+var_F8], ecx
0x417f32  mov     eax, ecx
0x417f34  xor     edx, edx
0x417f36  sub     eax, esi
0x417f38  div     edi
0x417f3a  inc     eax
0x417f3b  cmp     eax, 8
0x417f3e  ja      loc_417FFA
0x417f44  cmp     ecx, esi
0x417f46  jbe     loc_418373
0x417f4c  lea     edx, [edi+esi]
0x417f4f  mov     [ebp+var_110], edx
0x417f55  mov     eax, esi
0x417f57  mov     esi, edx
0x417f59  mov     [ebp+var_FC], eax
0x417f5f  cmp     esi, ecx
0x417f61  ja      short loc_417F92
0x417f63  push    eax
0x417f64  push    esi
0x417f65  mov     ecx, ebx
0x417f67  call    ds:___guard_check_icall_fptr
0x417f6d  call    ebx
0x417f6f  add     esp, 8
0x417f72  test    eax, eax
0x417f74  jle     short loc_417F80
0x417f76  mov     eax, esi
0x417f78  mov     [ebp+var_FC], eax
0x417f7e  jmp     short loc_417F86
0x417f80  mov     eax, [ebp+var_FC]
0x417f86  mov     ecx, [ebp+var_F8]
0x417f8c  add     esi, edi
0x417f8e  cmp     esi, ecx
0x417f90  jbe     short loc_417F63
0x417f92  mov     [ebp+var_10C], edi
0x417f98  mov     edx, ecx
0x417f9a  cmp     eax, ecx
0x417f9c  jz      short loc_417FD9
0x417f9e  sub     eax, ecx
0x417fa0  mov     ebx, edi
0x417fa2  mov     [ebp+var_FC], eax
0x417fa8  jmp     short loc_417FB0
0x417fb0  mov     cl, [eax+edx]
0x417fb3  lea     edx, [edx+1]
0x417fb6  mov     esi, [ebp+var_FC]
0x417fbc  mov     al, [edx-1]
0x417fbf  mov     [esi+edx-1], al
0x417fc3  mov     eax, esi
0x417fc5  mov     [edx-1], cl
0x417fc8  sub     ebx, 1
0x417fcb  jnz     short loc_417FB0
0x417fcd  mov     ebx, [ebp+var_108]
0x417fd3  mov     ecx, [ebp+var_F8]
0x417fd9  mov     esi, [ebp+var_104]
0x417fdf  sub     ecx, edi
0x417fe1  mov     edx, [ebp+var_110]
0x417fe7  mov     [ebp+var_F8], ecx
0x417fed  cmp     ecx, esi
0x417fef  ja      loc_417F55
0x417ff5  jmp     loc_418373
0x417ffa  shr     eax, 1
0x417ffc  mov     ecx, ebx
0x417ffe  imul    eax, edi
0x418001  mov     [ebp+var_FC], eax
0x418007  lea     edi, [eax+esi]
0x41800a  push    edi
0x41800b  push    esi
0x41800c  mov     [ebp+var_114], edi
0x418012  call    ds:___guard_check_icall_fptr
0x418018  call    ebx
0x41801a  mov     esi, [ebp+var_100]
0x418020  add     esp, 8
0x418023  test    eax, eax
0x418025  mov     eax, [ebp+var_104]
0x41802b  jle     short loc_41807A
0x41802d  mov     [ebp+var_10C], esi
0x418033  mov     [ebp+var_110], edi
0x418039  cmp     eax, edi
0x41803b  jz      short loc_41807A
0x41803d  mov     ebx, [ebp+var_10C]
0x418043  mov     esi, edi
0x418045  mov     edi, [ebp+var_FC]
0x41804b  jmp     short loc_418050
0x418050  mov     al, [esi]
0x418052  mov     edx, esi
0x418054  sub     edx, edi
0x418056  mov     cl, [edx]
0x418058  mov     [edx], al
0x41805a  mov     [esi], cl
0x41805c  inc     esi
0x41805d  sub     ebx, 1
0x418060  jnz     short loc_418050
0x418062  mov     edi, [ebp+var_114]
0x418068  mov     ebx, [ebp+var_108]
0x41806e  mov     esi, [ebp+var_100]
0x418074  mov     eax, [ebp+var_104]
0x41807a  push    [ebp+var_F8]
0x418080  mov     ecx, ebx
0x418082  push    eax
0x418083  call    ds:___guard_check_icall_fptr
0x418089  call    ebx
0x41808b  mov     edx, [ebp+var_F8]
0x418091  add     esp, 8
0x418094  test    eax, eax
0x418096  jle     short loc_4180E1
0x418098  mov     eax, [ebp+var_104]
0x41809e  mov     [ebp+var_114], esi
0x4180a4  mov     esi, edx
0x4180a6  cmp     eax, edx
0x4180a8  jz      short loc_4180E1
0x4180aa  mov     ebx, [ebp+var_114]
0x4180b0  sub     eax, edx
0x4180b2  mov     [ebp+var_110], eax
0x4180b8  mov     edx, eax
0x4180ba  lea     ebx, [ebx+0]
0x4180c0  mov     al, [esi]
0x4180c2  lea     esi, [esi+1]
0x4180c5  mov     cl, [edx+esi-1]
0x4180c9  mov     [edx+esi-1], al
0x4180cd  mov     [esi-1], cl
0x4180d0  sub     ebx, 1
0x4180d3  jnz     short loc_4180C0
0x4180d5  mov     ebx, [ebp+var_108]
0x4180db  mov     edx, [ebp+var_F8]
0x4180e1  push    edx
0x4180e2  push    edi
0x4180e3  mov     ecx, ebx
0x4180e5  call    ds:___guard_check_icall_fptr
0x4180eb  call    ebx
0x4180ed  mov     edx, [ebp+var_F8]
0x4180f3  add     esp, 8
0x4180f6  test    eax, eax
0x4180f8  mov     eax, [ebp+var_100]
0x4180fe  jle     short loc_418135
0x418100  mov     ebx, eax
0x418102  mov     esi, edx
0x418104  cmp     edi, edx
0x418106  jz      short loc_418135
0x418108  mov     eax, edi
0x41810a  sub     eax, edx
0x41810c  mov     [ebp+var_114], eax
0x418112  mov     edx, eax
0x418114  mov     al, [esi]
0x418116  lea     esi, [esi+1]
0x418119  mov     cl, [edx+esi-1]
0x41811d  mov     [edx+esi-1], al
0x418121  mov     [esi-1], cl
0x418124  sub     ebx, 1
0x418127  jnz     short loc_418114
0x418129  mov     eax, [ebp+var_100]
0x41812f  mov     edx, [ebp+var_F8]
0x418135  mov     esi, [ebp+var_104]
0x41813b  mov     ebx, edx
0x41813d  mov     [ebp+var_FC], edx
0x418143  cmp     edi, esi
0x418145  jbe     short loc_418185
0x418147  jmp     short loc_418150
0x418150  add     esi, eax
0x418152  mov     [ebp+var_10C], esi
0x418158  cmp     esi, edi
0x41815a  jnb     short loc_41817F
0x41815c  mov     ecx, [ebp+var_108]
0x418162  push    edi
0x418163  push    esi
0x418164  call    ds:___guard_check_icall_fptr
0x41816a  call    [ebp+var_108]
0x418170  add     esp, 8
0x418173  test    eax, eax
0x418175  mov     eax, [ebp+var_100]
0x41817b  jle     short loc_418150
0x41817d  jmp     short loc_4181C1
0x41817f  mov     edx, [ebp+var_F8]
0x418185  mov     ebx, [ebp+var_108]
0x41818b  jmp     short loc_418190
0x418190  add     esi, eax
0x418192  cmp     esi, edx
0x418194  ja      short loc_4181B5
0x418196  push    edi
0x418197  push    esi
0x418198  mov     ecx, ebx
0x41819a  call    ds:___guard_check_icall_fptr
0x4181a0  call    ebx
0x4181a2  mov     edx, [ebp+var_F8]
0x4181a8  add     esp, 8
0x4181ab  test    eax, eax
0x4181ad  mov     eax, [ebp+var_100]
0x4181b3  jle     short loc_418190
0x4181b5  mov     ebx, [ebp+var_FC]
0x4181bb  mov     [ebp+var_10C], esi
0x4181c1  mov     esi, [ebp+var_108]
0x4181c7  jmp     short loc_4181D0
0x4181d0  mov     eax, [ebp+var_100]
0x4181d6  mov     ecx, ebx
0x4181d8  sub     ebx, eax
0x4181da  mov     [ebp+var_FC], ecx
0x4181e0  cmp     ebx, edi
0x4181e2  jbe     short loc_418203
0x4181e4  push    edi
0x4181e5  push    ebx
0x4181e6  mov     ecx, esi
0x4181e8  call    ds:___guard_check_icall_fptr
0x4181ee  call    esi
0x4181f0  add     esp, 8
0x4181f3  test    eax, eax
0x4181f5  jg      short loc_4181D0
0x4181f7  mov     eax, [ebp+var_100]
0x4181fd  mov     ecx, [ebp+var_FC]
0x418203  mov     esi, [ebp+var_10C]
0x418209  mov     [ebp+var_FC], ebx
0x41820f  cmp     ebx, esi
0x418211  jb      short loc_41825D
0x418213  mov     [ebp+var_110], eax
0x418219  mov     edx, ebx
0x41821b  jz      short loc_418248
0x41821d  sub     esi, ebx
0x41821f  mov     ebx, eax
0x418221  mov     al, [edx]
0x418223  lea     edx, [edx+1]
0x418226  mov     cl, [esi+edx-1]
0x41822a  mov     [esi+edx-1], al
0x41822e  mov     [edx-1], cl
0x418231  sub     ebx, 1
0x418234  jnz     short loc_418221
0x418236  mov     esi, [ebp+var_10C]
0x41823c  mov     ebx, [ebp+var_FC]
0x418242  mov     eax, [ebp+var_100]
0x418248  mov     edx, [ebp+var_F8]
0x41824e  cmp     edi, ebx
0x418250  jnz     loc_418143
0x418256  mov     edi, esi
0x418258  jmp     loc_418143
0x41825d  cmp     edi, ecx
0x41825f  jnb     short loc_41829D
0x418261  mov     ebx, [ebp+var_108]
0x418267  jmp     short loc_418270
0x418270  sub     ecx, eax
0x418272  mov     [ebp+var_FC], ecx
0x418278  cmp     ecx, edi
0x41827a  jbe     short loc_41829D
0x41827c  push    edi
0x41827d  push    ecx
0x41827e  mov     ecx, ebx
0x418280  call    ds:___guard_check_icall_fptr
0x418286  call    ebx
0x418288  mov     ecx, [ebp+var_FC]
0x41828e  add     esp, 8
0x418291  test    eax, eax
0x418293  mov     eax, [ebp+var_100]
0x418299  jz      short loc_418270
0x41829b  jmp     short loc_4182E1
0x41829d  mov     ebx, [ebp+var_108]
0x4182a3  mov     esi, [ebp+var_104]
0x4182a9  lea     esp, [esp+0]
0x4182b0  sub     ecx, eax
0x4182b2  mov     [ebp+var_FC], ecx
0x4182b8  cmp     ecx, esi
0x4182ba  jbe     short loc_4182DB
0x4182bc  push    edi
  ... truncated ...
```
