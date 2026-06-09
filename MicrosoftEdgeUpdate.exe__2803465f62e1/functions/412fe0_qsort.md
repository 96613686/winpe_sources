# _qsort

- ea: `0x412fe0`
- end: `0x4134ce`
- name: `_qsort`
- size: `1262`
- prototype: `void __cdecl(void *Base, size_t NumOfElements, size_t SizeOfElements, _CoreCrtNonSecureSearchSortCompareFunction CompareFunction)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x410354`

## callees

- `0x407eb0`
- `0x40b3e3`
- `0x40de54`
- `0x40ffa9`
- `0x412fe0`

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
0x412fe0  mov     edi, edi
0x412fe2  push    ebp
0x412fe3  mov     ebp, esp
0x412fe5  sub     esp, 118h
0x412feb  mov     eax, ___security_cookie
0x412ff0  xor     eax, ebp
0x412ff2  mov     [ebp+var_4], eax
0x412ff5  mov     ecx, [ebp+NumOfElements]
0x412ff8  push    ebx
0x412ff9  mov     ebx, [ebp+CompareFunction]
0x412ffc  push    esi
0x412ffd  mov     esi, [ebp+Base]
0x413000  mov     [ebp+var_104], esi
0x413006  mov     [ebp+var_108], ebx
0x41300c  push    edi
0x41300d  mov     edi, [ebp+SizeOfElements]
0x413010  mov     [ebp+var_100], edi
0x413016  test    esi, esi
0x413018  jnz     short loc_41303F
0x41301a  test    ecx, ecx
0x41301c  jz      short loc_41303F
0x41301e  call    __errno
0x413023  mov     dword ptr [eax], 16h
0x413029  call    __invalid_parameter_noinfo
0x41302e  mov     ecx, [ebp+var_4]
0x413031  pop     edi
0x413032  pop     esi
0x413033  xor     ecx, ebp; StackCookie
0x413035  pop     ebx
0x413036  call    @__security_check_cookie@4
0x41303b  mov     esp, ebp
0x41303d  pop     ebp
0x41303e  retn
0x41303f  test    edi, edi
0x413041  jz      short loc_41301E
0x413043  test    ebx, ebx
0x413045  jz      short loc_41301E
0x413047  mov     [ebp+var_118], 0
0x413051  cmp     ecx, 2
0x413054  jb      short loc_41302E
0x413056  dec     ecx
0x413057  imul    ecx, edi
0x41305a  add     ecx, esi
0x41305c  mov     [ebp+var_F8], ecx
0x413062  mov     eax, ecx
0x413064  xor     edx, edx
0x413066  sub     eax, esi
0x413068  div     edi
0x41306a  inc     eax
0x41306b  cmp     eax, 8
0x41306e  ja      loc_41312A
0x413074  cmp     ecx, esi
0x413076  jbe     loc_4134A3
0x41307c  lea     edx, [edi+esi]
0x41307f  mov     [ebp+var_110], edx
0x413085  mov     eax, esi
0x413087  mov     esi, edx
0x413089  mov     [ebp+var_FC], eax
0x41308f  cmp     esi, ecx
0x413091  ja      short loc_4130C2
0x413093  push    eax
0x413094  push    esi
0x413095  mov     ecx, ebx
0x413097  call    ds:___guard_check_icall_fptr
0x41309d  call    ebx
0x41309f  add     esp, 8
0x4130a2  test    eax, eax
0x4130a4  jle     short loc_4130B0
0x4130a6  mov     eax, esi
0x4130a8  mov     [ebp+var_FC], eax
0x4130ae  jmp     short loc_4130B6
0x4130b0  mov     eax, [ebp+var_FC]
0x4130b6  mov     ecx, [ebp+var_F8]
0x4130bc  add     esi, edi
0x4130be  cmp     esi, ecx
0x4130c0  jbe     short loc_413093
0x4130c2  mov     [ebp+var_10C], edi
0x4130c8  mov     edx, ecx
0x4130ca  cmp     eax, ecx
0x4130cc  jz      short loc_413109
0x4130ce  sub     eax, ecx
0x4130d0  mov     ebx, edi
0x4130d2  mov     [ebp+var_FC], eax
0x4130d8  jmp     short loc_4130E0
0x4130e0  mov     cl, [eax+edx]
0x4130e3  lea     edx, [edx+1]
0x4130e6  mov     esi, [ebp+var_FC]
0x4130ec  mov     al, [edx-1]
0x4130ef  mov     [esi+edx-1], al
0x4130f3  mov     eax, esi
0x4130f5  mov     [edx-1], cl
0x4130f8  sub     ebx, 1
0x4130fb  jnz     short loc_4130E0
0x4130fd  mov     ebx, [ebp+var_108]
0x413103  mov     ecx, [ebp+var_F8]
0x413109  mov     esi, [ebp+var_104]
0x41310f  sub     ecx, edi
0x413111  mov     edx, [ebp+var_110]
0x413117  mov     [ebp+var_F8], ecx
0x41311d  cmp     ecx, esi
0x41311f  ja      loc_413085
0x413125  jmp     loc_4134A3
0x41312a  shr     eax, 1
0x41312c  mov     ecx, ebx
0x41312e  imul    eax, edi
0x413131  mov     [ebp+var_FC], eax
0x413137  lea     edi, [eax+esi]
0x41313a  push    edi
0x41313b  push    esi
0x41313c  mov     [ebp+var_114], edi
0x413142  call    ds:___guard_check_icall_fptr
0x413148  call    ebx
0x41314a  mov     esi, [ebp+var_100]
0x413150  add     esp, 8
0x413153  test    eax, eax
0x413155  mov     eax, [ebp+var_104]
0x41315b  jle     short loc_4131AA
0x41315d  mov     [ebp+var_10C], esi
0x413163  mov     [ebp+var_110], edi
0x413169  cmp     eax, edi
0x41316b  jz      short loc_4131AA
0x41316d  mov     ebx, [ebp+var_10C]
0x413173  mov     esi, edi
0x413175  mov     edi, [ebp+var_FC]
0x41317b  jmp     short loc_413180
0x413180  mov     al, [esi]
0x413182  mov     edx, esi
0x413184  sub     edx, edi
0x413186  mov     cl, [edx]
0x413188  mov     [edx], al
0x41318a  mov     [esi], cl
0x41318c  inc     esi
0x41318d  sub     ebx, 1
0x413190  jnz     short loc_413180
0x413192  mov     edi, [ebp+var_114]
0x413198  mov     ebx, [ebp+var_108]
0x41319e  mov     esi, [ebp+var_100]
0x4131a4  mov     eax, [ebp+var_104]
0x4131aa  push    [ebp+var_F8]
0x4131b0  mov     ecx, ebx
0x4131b2  push    eax
0x4131b3  call    ds:___guard_check_icall_fptr
0x4131b9  call    ebx
0x4131bb  mov     edx, [ebp+var_F8]
0x4131c1  add     esp, 8
0x4131c4  test    eax, eax
0x4131c6  jle     short loc_413211
0x4131c8  mov     eax, [ebp+var_104]
0x4131ce  mov     [ebp+var_114], esi
0x4131d4  mov     esi, edx
0x4131d6  cmp     eax, edx
0x4131d8  jz      short loc_413211
0x4131da  mov     ebx, [ebp+var_114]
0x4131e0  sub     eax, edx
0x4131e2  mov     [ebp+var_110], eax
0x4131e8  mov     edx, eax
0x4131ea  lea     ebx, [ebx+0]
0x4131f0  mov     al, [esi]
0x4131f2  lea     esi, [esi+1]
0x4131f5  mov     cl, [edx+esi-1]
0x4131f9  mov     [edx+esi-1], al
0x4131fd  mov     [esi-1], cl
0x413200  sub     ebx, 1
0x413203  jnz     short loc_4131F0
0x413205  mov     ebx, [ebp+var_108]
0x41320b  mov     edx, [ebp+var_F8]
0x413211  push    edx
0x413212  push    edi
0x413213  mov     ecx, ebx
0x413215  call    ds:___guard_check_icall_fptr
0x41321b  call    ebx
0x41321d  mov     edx, [ebp+var_F8]
0x413223  add     esp, 8
0x413226  test    eax, eax
0x413228  mov     eax, [ebp+var_100]
0x41322e  jle     short loc_413265
0x413230  mov     ebx, eax
0x413232  mov     esi, edx
0x413234  cmp     edi, edx
0x413236  jz      short loc_413265
0x413238  mov     eax, edi
0x41323a  sub     eax, edx
0x41323c  mov     [ebp+var_114], eax
0x413242  mov     edx, eax
0x413244  mov     al, [esi]
0x413246  lea     esi, [esi+1]
0x413249  mov     cl, [edx+esi-1]
0x41324d  mov     [edx+esi-1], al
0x413251  mov     [esi-1], cl
0x413254  sub     ebx, 1
0x413257  jnz     short loc_413244
0x413259  mov     eax, [ebp+var_100]
0x41325f  mov     edx, [ebp+var_F8]
0x413265  mov     esi, [ebp+var_104]
0x41326b  mov     ebx, edx
0x41326d  mov     [ebp+var_FC], edx
0x413273  cmp     edi, esi
0x413275  jbe     short loc_4132B5
0x413277  jmp     short loc_413280
0x413280  add     esi, eax
0x413282  mov     [ebp+var_10C], esi
0x413288  cmp     esi, edi
0x41328a  jnb     short loc_4132AF
0x41328c  mov     ecx, [ebp+var_108]
0x413292  push    edi
0x413293  push    esi
0x413294  call    ds:___guard_check_icall_fptr
0x41329a  call    [ebp+var_108]
0x4132a0  add     esp, 8
0x4132a3  test    eax, eax
0x4132a5  mov     eax, [ebp+var_100]
0x4132ab  jle     short loc_413280
0x4132ad  jmp     short loc_4132F1
0x4132af  mov     edx, [ebp+var_F8]
0x4132b5  mov     ebx, [ebp+var_108]
0x4132bb  jmp     short loc_4132C0
0x4132c0  add     esi, eax
0x4132c2  cmp     esi, edx
0x4132c4  ja      short loc_4132E5
0x4132c6  push    edi
0x4132c7  push    esi
0x4132c8  mov     ecx, ebx
0x4132ca  call    ds:___guard_check_icall_fptr
0x4132d0  call    ebx
0x4132d2  mov     edx, [ebp+var_F8]
0x4132d8  add     esp, 8
0x4132db  test    eax, eax
0x4132dd  mov     eax, [ebp+var_100]
0x4132e3  jle     short loc_4132C0
0x4132e5  mov     ebx, [ebp+var_FC]
0x4132eb  mov     [ebp+var_10C], esi
0x4132f1  mov     esi, [ebp+var_108]
0x4132f7  jmp     short loc_413300
0x413300  mov     eax, [ebp+var_100]
0x413306  mov     ecx, ebx
0x413308  sub     ebx, eax
0x41330a  mov     [ebp+var_FC], ecx
0x413310  cmp     ebx, edi
0x413312  jbe     short loc_413333
0x413314  push    edi
0x413315  push    ebx
0x413316  mov     ecx, esi
0x413318  call    ds:___guard_check_icall_fptr
0x41331e  call    esi
0x413320  add     esp, 8
0x413323  test    eax, eax
0x413325  jg      short loc_413300
0x413327  mov     eax, [ebp+var_100]
0x41332d  mov     ecx, [ebp+var_FC]
0x413333  mov     esi, [ebp+var_10C]
0x413339  mov     [ebp+var_FC], ebx
0x41333f  cmp     ebx, esi
0x413341  jb      short loc_41338D
0x413343  mov     [ebp+var_110], eax
0x413349  mov     edx, ebx
0x41334b  jz      short loc_413378
0x41334d  sub     esi, ebx
0x41334f  mov     ebx, eax
0x413351  mov     al, [edx]
0x413353  lea     edx, [edx+1]
0x413356  mov     cl, [esi+edx-1]
0x41335a  mov     [esi+edx-1], al
0x41335e  mov     [edx-1], cl
0x413361  sub     ebx, 1
0x413364  jnz     short loc_413351
0x413366  mov     esi, [ebp+var_10C]
0x41336c  mov     ebx, [ebp+var_FC]
0x413372  mov     eax, [ebp+var_100]
0x413378  mov     edx, [ebp+var_F8]
0x41337e  cmp     edi, ebx
0x413380  jnz     loc_413273
0x413386  mov     edi, esi
0x413388  jmp     loc_413273
0x41338d  cmp     edi, ecx
0x41338f  jnb     short loc_4133CD
0x413391  mov     ebx, [ebp+var_108]
0x413397  jmp     short loc_4133A0
0x4133a0  sub     ecx, eax
0x4133a2  mov     [ebp+var_FC], ecx
0x4133a8  cmp     ecx, edi
0x4133aa  jbe     short loc_4133CD
0x4133ac  push    edi
0x4133ad  push    ecx
0x4133ae  mov     ecx, ebx
0x4133b0  call    ds:___guard_check_icall_fptr
0x4133b6  call    ebx
0x4133b8  mov     ecx, [ebp+var_FC]
0x4133be  add     esp, 8
0x4133c1  test    eax, eax
0x4133c3  mov     eax, [ebp+var_100]
0x4133c9  jz      short loc_4133A0
0x4133cb  jmp     short loc_413411
0x4133cd  mov     ebx, [ebp+var_108]
0x4133d3  mov     esi, [ebp+var_104]
0x4133d9  lea     esp, [esp+0]
0x4133e0  sub     ecx, eax
0x4133e2  mov     [ebp+var_FC], ecx
0x4133e8  cmp     ecx, esi
0x4133ea  jbe     short loc_41340B
0x4133ec  push    edi
  ... truncated ...
```
