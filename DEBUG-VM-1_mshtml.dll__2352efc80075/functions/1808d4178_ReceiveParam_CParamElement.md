# ReceiveParam_CParamElement_

- ea: `0x1808d4178`
- end: `0x1808d48b9`
- name: `ReceiveParam_CParamElement_`
- size: `1857`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, CParamElement *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1808d4fe4`

## callees

- `0x1808d4178`
- `0x180e4b360`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1808d4232`
- `KERNEL32!CompareStringW` at `0x1808d4315`
- `KERNEL32!CompareStringW` at `0x1808d43be`
- `KERNEL32!CompareStringW` at `0x1808d449d`
- `KERNEL32!CompareStringW` at `0x1808d4543`
- `KERNEL32!CompareStringW` at `0x1808d45e9`
- `KERNEL32!CompareStringW` at `0x1808d4682`
- `KERNEL32!CompareStringW` at `0x1808d471b`
- `KERNEL32!CompareStringW` at `0x1808d47b4`
- `KERNEL32!CompareStringW` at `0x1808d484c`
- `KERNEL32!CompareStringW` at `0x1808d4232`
- `KERNEL32!CompareStringW` at `0x1808d4315`
- `KERNEL32!CompareStringW` at `0x1808d43be`
- `KERNEL32!CompareStringW` at `0x1808d449d`
- `KERNEL32!CompareStringW` at `0x1808d4543`
- `KERNEL32!CompareStringW` at `0x1808d45e9`
- `KERNEL32!CompareStringW` at `0x1808d4682`
- `KERNEL32!CompareStringW` at `0x1808d471b`
- `KERNEL32!CompareStringW` at `0x1808d47b4`
- `KERNEL32!CompareStringW` at `0x1808d484c`
- `OLEAUT32!__imp_SysFreeString` at `0x1808d48a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1808d48a2`
- `OLEAUT32!__imp_SysStringLen` at `0x1808d427d`
- `OLEAUT32!__imp_SysStringLen` at `0x1808d4409`
- `OLEAUT32!__imp_SysStringLen` at `0x1808d488b`
- `OLEAUT32!__imp_SysStringLen` at `0x1808d427d`
- `OLEAUT32!__imp_SysStringLen` at `0x1808d4409`
- `OLEAUT32!__imp_SysStringLen` at `0x1808d488b`

## string_xrefs

- `0x1808d4340`: `allowscriptaccess`

## pseudocode

```c
void __fastcall ReceiveParam_CParamElement_(PCNZWCH lpString1, CParamElement *this, __int64 a3)
{
  const WCHAR *lpString2; // r9
  PCNZWCH v6; // rbx
  PCNZWCH i; // r8
  WCHAR v8; // dx
  WCHAR v9; // cx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  OLECHAR *v13; // rbx
  const WCHAR *v14; // r8
  const WCHAR *v15; // r9
  WCHAR v16; // dx
  WCHAR v17; // cx
  int v18; // eax
  int v19; // eax
  const WCHAR *v20; // r8
  const WCHAR *j; // r9
  WCHAR v22; // dx
  WCHAR v23; // cx
  int v24; // eax
  int v25; // eax
  int value; // eax
  const WCHAR *v27; // r8
  const WCHAR *v28; // r9
  WCHAR v29; // dx
  WCHAR v30; // cx
  int v31; // eax
  int v32; // eax
  const WCHAR *v33; // r8
  const WCHAR *v34; // r9
  WCHAR v35; // dx
  WCHAR v36; // cx
  int v37; // eax
  int v38; // eax
  const WCHAR *v39; // r8
  const WCHAR *v40; // r9
  WCHAR v41; // dx
  WCHAR v42; // cx
  int v43; // eax
  int v44; // eax
  const WCHAR *v45; // r8
  const WCHAR *v46; // r9
  WCHAR v47; // dx
  WCHAR v48; // cx
  int v49; // eax
  int v50; // eax
  const WCHAR *v51; // r8
  const WCHAR *v52; // r9
  WCHAR v53; // dx
  WCHAR v54; // cx
  int v55; // eax
  int v56; // eax
  const WCHAR *v57; // r8
  const WCHAR *v58; // r9
  WCHAR v59; // dx
  WCHAR v60; // cx
  int v61; // eax
  int v62; // eax
  const WCHAR *v63; // r8
  WCHAR v64; // dx
  WCHAR v65; // cx
  int v66; // eax
  int v67; // eax
  int v68; // eax
  OLECHAR *v69; // rax
  BSTR pbstr; // [rsp+80h] [rbp+8h] BYREF

  if ( !lpString1 )
    return;
  lpString2 = L"allowfullscreen";
  v6 = lpString1;
  for ( i = lpString1; ; ++i )
  {
    v8 = *i;
    v9 = *lpString2;
    if ( !*i )
      break;
    if ( v8 == v9 )
      goto LABEL_11;
    if ( (unsigned __int16)(v8 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v9 - 65) > 0x19u )
        goto LABEL_12;
    }
    else
    {
      v8 += 32;
      if ( (unsigned __int16)(v9 - 65) > 0x19u )
        goto LABEL_10;
    }
    v9 += 32;
LABEL_10:
    if ( v8 != v9 )
    {
LABEL_12:
      if ( ((v8 | v9) & 0xFF80) != 0 )
      {
        v10 = CompareStringW(0, 0x31001u, i, -1, lpString2, -1);
        if ( v10 > 0 )
        {
          v11 = v10 - 2;
          goto LABEL_16;
        }
      }
      goto LABEL_36;
    }
LABEL_11:
    ++lpString2;
  }
  v11 = -(v9 != 0);
LABEL_16:
  if ( v11 )
  {
LABEL_36:
    v20 = v6;
    for ( j = L"allowscriptaccess"; ; ++j )
    {
      v22 = *v20;
      v23 = *j;
      if ( !*v20 )
      {
        v25 = -(v23 != 0);
LABEL_50:
        if ( !v25 )
        {
          pbstr = 0;
          value = CParamElement::get_value(this, &pbstr);
          v13 = pbstr;
          if ( value < 0 || !SysStringLen(pbstr) )
            goto LABEL_164;
          v27 = v13;
          if ( !v13 )
            goto LABEL_69;
          v28 = L"always";
          while ( 2 )
          {
            v29 = *v27;
            v30 = *v28;
            if ( !*v27 )
            {
              v32 = -(v30 != 0);
              goto LABEL_68;
            }
            if ( v29 != v30 )
            {
              if ( (unsigned __int16)(v29 - 65) > 0x19u )
              {
                if ( (unsigned __int16)(v30 - 65) > 0x19u )
                  goto LABEL_64;
LABEL_61:
                v30 += 32;
              }
              else
              {
                v29 += 32;
                if ( (unsigned __int16)(v30 - 65) <= 0x19u )
                  goto LABEL_61;
              }
              if ( v29 != v30 )
              {
LABEL_64:
                if ( ((v29 | v30) & 0xFF80) != 0 )
                {
                  v31 = CompareStringW(0, 0x31001u, v27, -1, v28, -1);
                  if ( v31 > 0 )
                  {
                    v32 = v31 - 2;
LABEL_68:
                    if ( !v32 )
                      goto LABEL_85;
                  }
                }
LABEL_69:
                v33 = v13;
                if ( !v13 )
                  goto LABEL_164;
                v34 = L"samedomain";
                while ( 2 )
                {
                  v35 = *v33;
                  v36 = *v34;
                  if ( !*v33 )
                  {
                    v38 = -(v36 != 0);
                    goto LABEL_84;
                  }
                  if ( v35 != v36 )
                  {
                    if ( (unsigned __int16)(v35 - 65) > 0x19u )
                    {
                      if ( (unsigned __int16)(v36 - 65) > 0x19u )
                        goto LABEL_80;
LABEL_77:
                      v36 += 32;
                    }
                    else
                    {
                      v35 += 32;
                      if ( (unsigned __int16)(v36 - 65) <= 0x19u )
                        goto LABEL_77;
                    }
                    if ( v35 != v36 )
                    {
LABEL_80:
                      if ( ((v35 | v36) & 0xFF80) == 0 )
                        goto LABEL_164;
                      v37 = CompareStringW(0, 0x31001u, v33, -1, v34, -1);
                      if ( v37 <= 0 )
                        goto LABEL_164;
                      v38 = v37 - 2;
LABEL_84:
                      if ( v38 )
                        goto LABEL_164;
LABEL_85:
                      *(_BYTE *)(a3 + 1) = 1;
                      goto LABEL_164;
                    }
                  }
                  ++v33;
                  ++v34;
                  continue;
                }
              }
            }
            ++v27;
            ++v28;
            continue;
          }
        }
LABEL_86:
        v39 = v6;
        v40 = L"movie";
        while ( 2 )
        {
          v41 = *v39;
          v42 = *v40;
          if ( !*v39 )
          {
            v44 = -(v42 != 0);
            goto LABEL_100;
          }
          if ( v41 != v42 )
          {
            if ( (unsigned __int16)(v41 - 65) > 0x19u )
            {
              if ( (unsigned __int16)(v42 - 65) > 0x19u )
                goto LABEL_96;
LABEL_93:
              v42 += 32;
            }
            else
            {
              v41 += 32;
              if ( (unsigned __int16)(v42 - 65) <= 0x19u )
                goto LABEL_93;
            }
            if ( v41 != v42 )
            {
LABEL_96:
              if ( ((v41 | v42) & 0xFF80) != 0 )
              {
                v43 = CompareStringW(0, 0x31001u, v39, -1, v40, -1);
                if ( v43 > 0 )
                {
                  v44 = v43 - 2;
LABEL_100:
                  if ( !v44 )
                    goto LABEL_161;
                }
              }
              v45 = v6;
              v46 = L"src";
              while ( 2 )
              {
                v47 = *v45;
                v48 = *v46;
                if ( !*v45 )
                {
                  v50 = -(v48 != 0);
                  goto LABEL_115;
                }
                if ( v47 != v48 )
                {
                  if ( (unsigned __int16)(v47 - 65) > 0x19u )
                  {
                    if ( (unsigned __int16)(v48 - 65) > 0x19u )
                      goto LABEL_111;
LABEL_108:
                    v48 += 32;
                  }
                  else
                  {
                    v47 += 32;
                    if ( (unsigned __int16)(v48 - 65) <= 0x19u )
                      goto LABEL_108;
                  }
                  if ( v47 != v48 )
                  {
LABEL_111:
                    if ( ((v47 | v48) & 0xFF80) != 0 )
                    {
                      v49 = CompareStringW(0, 0x31001u, v45, -1, v46, -1);
                      if ( v49 > 0 )
                      {
                        v50 = v49 - 2;
LABEL_115:
                        if ( !v50 )
                          goto LABEL_161;
                      }
                    }
                    v51 = v6;
                    v52 = L"filename";
                    while ( 2 )
                    {
                      v53 = *v51;
                      v54 = *v52;
                      if ( !*v51 )
                      {
                        v56 = -(v54 != 0);
                        goto LABEL_130;
                      }
                      if ( v53 != v54 )
                      {
                        if ( (unsigned __int16)(v53 - 65) > 0x19u )
                        {
                          if ( (unsigned __int16)(v54 - 65) > 0x19u )
                            goto LABEL_126;
LABEL_123:
                          v54 += 32;
                        }
                        else
                        {
                          v53 += 32;
                          if ( (unsigned __int16)(v54 - 65) <= 0x19u )
                            goto LABEL_123;
                        }
                        if ( v53 != v54 )
                        {
LABEL_126:
                          if ( ((v53 | v54) & 0xFF80) != 0 )
                          {
                            v55 = CompareStringW(0, 0x31001u, v51, -1, v52, -1);
                            if ( v55 > 0 )
                            {
                              v56 = v55 - 2;
LABEL_130:
                              if ( !v56 )
                                goto LABEL_161;
                            }
                          }
                          v57 = v6;
                          v58 = L"url";
                          while ( 2 )
                          {
                            v59 = *v57;
                            v60 = *v58;
                            if ( !*v57 )
                            {
                              v62 = -(v60 != 0);
                              goto LABEL_145;
                            }
                            if ( v59 != v60 )
                            {
                              if ( (unsigned __int16)(v59 - 65) > 0x19u )
                              {
                                if ( (unsigned __int16)(v60 - 65) > 0x19u )
                                  goto LABEL_141;
LABEL_138:
                                v60 += 32;
                              }
                              else
                              {
                                v59 += 32;
                                if ( (unsigned __int16)(v60 - 65) <= 0x19u )
                                  goto LABEL_138;
                              }
                              if ( v59 != v60 )
                              {
LABEL_141:
                                if ( ((v59 | v60) & 0xFF80) != 0 )
                                {
                                  v61 = CompareStringW(0, 0x31001u, v57, -1, v58, -1);
                                  if ( v61 > 0 )
                                  {
                                    v62 = v61 - 2;
LABEL_145:
                                    if ( !v62 )
                                      goto LABEL_161;
                                  }
                                }
                                v63 = L"source";
                                while ( 2 )
                                {
                                  v64 = *v6;
                                  v65 = *v63;
                                  if ( !*v6 )
                                  {
                                    v67 = -(v65 != 0);
                                    goto LABEL_160;
                                  }
                                  if ( v64 != v65 )
                                  {
                                    if ( (unsigned __int16)(v64 - 65) > 0x19u )
                                    {
                                      if ( (unsigned __int16)(v65 - 65) > 0x19u )
                                        goto LABEL_156;
LABEL_153:
                                      v65 += 32;
                                    }
                                    else
                                    {
                                      v64 += 32;
                                      if ( (unsigned __int16)(v65 - 65) <= 0x19u )
                                        goto LABEL_153;
                                    }
                                    if ( v64 != v65 )
                                    {
LABEL_156:
                                      if ( ((v64 | v65) & 0xFF80) == 0 )
                                        return;
                                      v66 = CompareStringW(0, 0x31001u, v6, -1, v63, -1);
                                      if ( v66 <= 0 )
                                        return;
                                      v67 = v66 - 2;
LABEL_160:
                                      if ( v67 )
                                        return;
LABEL_161:
                                      pbstr = 0;
                                      v68 = CParamElement::get_value(this, &pbstr);
                                      v13 = pbstr;
                                      if ( v68 >= 0 && SysStringLen(pbstr) )
                                      {
                                        v69 = v13;
                                        v13 = 0;
                                        *(_QWORD *)(a3 + 8) = v69;
                                      }
                                      goto LABEL_164;
                                    }
                                  }
                                  ++v6;
                                  ++v63;
                                  continue;
                                }
                              }
                            }
                            ++v57;
                            ++v58;
                            continue;
                          }
                        }
                      }
                      ++v51;
                      ++v52;
                      continue;
                    }
                  }
                }
                ++v45;
                ++v46;
                continue;
              }
            }
          }
          ++v39;
          ++v40;
          continue;
        }
      }
      if ( v22 != v23 )
        break;
LABEL_45:
      ++v20;
    }
    if ( (unsigned __int16)(v22 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v23 - 65) > 0x19u )
        goto LABEL_46;
    }
    else
    {
      v22 += 32;
      if ( (unsigned __int16)(v23 - 65) > 0x19u )
        goto LABEL_44;
    }
    v23 += 32;
LABEL_44:
    if ( v22 != v23 )
    {
LABEL_46:
      if ( ((v22 | v23) & 0xFF80) != 0 )
      {
        v24 = CompareStringW(0, 0x31001u, v20, -1, j, -1);
        if ( v24 > 0 )
        {
          v25 = v24 - 2;
          goto LABEL_50;
        }
      }
      goto LABEL_86;
    }
    goto LABEL_45;
  }
  pbstr = 0;
  v12 = CParamElement::get_value(this, &pbstr);
  v13 = pbstr;
  if ( v12 < 0 )
    goto LABEL_164;
  if ( !SysStringLen(pbstr) )
    goto LABEL_164;
  v14 = v13;
  if ( !v13 )
    goto LABEL_164;
  v15 = L"true";
  while ( 2 )
  {
    v16 = *v14;
    v17 = *v15;
    if ( !*v14 )
    {
      v19 = -(v17 != 0);
LABEL_34:
      if ( !v19 )
        *(_BYTE *)a3 = 1;
      goto LABEL_164;
    }
    if ( v16 == v17 )
      goto LABEL_29;
    if ( (unsigned __int16)(v16 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v17 - 65) > 0x19u )
        break;
LABEL_27:
      v17 += 32;
    }
    else
    {
      v16 += 32;
      if ( (unsigned __int16)(v17 - 65) <= 0x19u )
        goto LABEL_27;
    }
    if ( v16 == v17 )
    {
LABEL_29:
      ++v14;
      ++v15;
      continue;
    }
    break;
  }
  if ( ((v16 | v17) & 0xFF80) != 0 )
  {
    v18 = CompareStringW(0, 0x31001u, v14, -1, v15, -1);
    if ( v18 > 0 )
    {
      v19 = v18 - 2;
      goto LABEL_34;
    }
  }
LABEL_164:
  SysFreeString(v13);
}

```

## disassembly

```asm
0x1808d4178  test    rcx, rcx
0x1808d417b  jz      locret_1808D48B8
0x1808d4181  push    rbx
0x1808d4182  push    rbp
0x1808d4183  push    rsi
0x1808d4184  push    rdi
0x1808d4185  push    r12
0x1808d4187  push    r13
0x1808d4189  push    r14
0x1808d418b  push    r15
0x1808d418d  sub     rsp, 38h
0x1808d4191  xor     ebp, ebp
0x1808d4193  lea     r9, aAllowfullscree_0; "allowfullscreen"
0x1808d419a  mov     rsi, r8
0x1808d419d  mov     rdi, rdx
0x1808d41a0  mov     rbx, rcx
0x1808d41a3  mov     r8, rcx; lpString1
0x1808d41a6  mov     r15w, 41h ; 'A'
0x1808d41ab  mov     r12w, 19h
0x1808d41b0  lea     r13d, [rbp+2]
0x1808d41b4  mov     r14w, 20h ; ' '
0x1808d41b9  movzx   edx, word ptr [r8]
0x1808d41bd  or      r10d, 0FFFFFFFFh
0x1808d41c1  movzx   ecx, word ptr [r9]
0x1808d41c5  test    dx, dx
0x1808d41c8  jz      short loc_1808D4245
0x1808d41ca  cmp     dx, cx
0x1808d41cd  jz      short loc_1808D4202
0x1808d41cf  movzx   eax, dx
0x1808d41d2  sub     ax, r15w
0x1808d41d6  cmp     ax, r12w
0x1808d41da  movzx   eax, cx
0x1808d41dd  ja      short loc_1808D41EF
0x1808d41df  add     dx, r14w
0x1808d41e3  sub     ax, r15w
0x1808d41e7  cmp     ax, r12w
0x1808d41eb  ja      short loc_1808D41FD
0x1808d41ed  jmp     short loc_1808D41F9
0x1808d41ef  sub     ax, r15w
0x1808d41f3  cmp     ax, r12w
0x1808d41f7  ja      short loc_1808D420A
0x1808d41f9  add     cx, r14w
0x1808d41fd  cmp     dx, cx
0x1808d4200  jnz     short loc_1808D420A
0x1808d4202  add     r8, r13
0x1808d4205  add     r9, r13
0x1808d4208  jmp     short loc_1808D41B9
0x1808d420a  movzx   ecx, cx
0x1808d420d  movzx   eax, dx
0x1808d4210  or      ecx, eax
0x1808d4212  test    ecx, 0FFFFFF80h
0x1808d4218  jz      loc_1808D433D
0x1808d421e  mov     [rsp+78h+cchCount2], r10d; cchCount2
0x1808d4223  mov     edx, 31001h; dwCmpFlags
0x1808d4228  mov     [rsp+78h+lpString2], r9; lpString2
0x1808d422d  xor     ecx, ecx; Locale
0x1808d422f  mov     r9d, r10d; cchCount1
0x1808d4232  call    cs:__imp_CompareStringW
0x1808d4238  test    eax, eax
0x1808d423a  jle     loc_1808D433D
0x1808d4240  add     eax, 0FFFFFFFEh
0x1808d4243  jmp     short loc_1808D424A
0x1808d4245  neg     cx
0x1808d4248  sbb     eax, eax
0x1808d424a  test    eax, eax
0x1808d424c  jnz     loc_1808D433D
0x1808d4252  lea     rdx, [rsp+78h+pbstr]; unsigned __int16 **
0x1808d425a  mov     [rsp+78h+pbstr], rbp
0x1808d4262  mov     rcx, rdi; this
0x1808d4265  call    ?get_value@CParamElement@@QEAAJPEAPEAG@Z; CParamElement::get_value(ushort * *)
0x1808d426a  mov     rbx, [rsp+78h+pbstr]
0x1808d4272  test    eax, eax
0x1808d4274  js      loc_1808D489F
0x1808d427a  mov     rcx, rbx; pbstr
0x1808d427d  call    cs:__imp_SysStringLen
0x1808d4283  test    eax, eax
0x1808d4285  jz      loc_1808D489F
0x1808d428b  mov     r8, rbx; lpString1
0x1808d428e  test    rbx, rbx
0x1808d4291  jz      loc_1808D489F
0x1808d4297  lea     r9, pszStr2; "true"
0x1808d429e  movzx   edx, word ptr [r8]
0x1808d42a2  movzx   ecx, word ptr [r9]
0x1808d42a6  test    dx, dx
0x1808d42a9  jz      short loc_1808D4328
0x1808d42ab  cmp     dx, cx
0x1808d42ae  jz      short loc_1808D42E3
0x1808d42b0  movzx   eax, dx
0x1808d42b3  sub     ax, r15w
0x1808d42b7  cmp     ax, r12w
0x1808d42bb  movzx   eax, cx
0x1808d42be  ja      short loc_1808D42D0
0x1808d42c0  add     dx, r14w
0x1808d42c4  sub     ax, r15w
0x1808d42c8  cmp     ax, r12w
0x1808d42cc  ja      short loc_1808D42DE
0x1808d42ce  jmp     short loc_1808D42DA
0x1808d42d0  sub     ax, r15w
0x1808d42d4  cmp     ax, r12w
0x1808d42d8  ja      short loc_1808D42EB
0x1808d42da  add     cx, r14w
0x1808d42de  cmp     dx, cx
0x1808d42e1  jnz     short loc_1808D42EB
0x1808d42e3  add     r8, r13
0x1808d42e6  add     r9, r13
0x1808d42e9  jmp     short loc_1808D429E
0x1808d42eb  movzx   ecx, cx
0x1808d42ee  movzx   eax, dx
0x1808d42f1  or      ecx, eax
0x1808d42f3  test    ecx, 0FFFFFF80h
0x1808d42f9  jz      loc_1808D489F
0x1808d42ff  or      eax, 0FFFFFFFFh
0x1808d4302  mov     edx, 31001h; dwCmpFlags
0x1808d4307  mov     [rsp+78h+cchCount2], eax; cchCount2
0x1808d430b  xor     ecx, ecx; Locale
0x1808d430d  mov     [rsp+78h+lpString2], r9; lpString2
0x1808d4312  mov     r9d, eax; cchCount1
0x1808d4315  call    cs:__imp_CompareStringW
0x1808d431b  test    eax, eax
0x1808d431d  jle     loc_1808D489F
0x1808d4323  add     eax, 0FFFFFFFEh
0x1808d4326  jmp     short loc_1808D432D
0x1808d4328  neg     cx
0x1808d432b  sbb     eax, eax
0x1808d432d  test    eax, eax
0x1808d432f  jnz     loc_1808D489F
0x1808d4335  mov     byte ptr [rsi], 1
0x1808d4338  jmp     loc_1808D489F
0x1808d433d  mov     r8, rbx; lpString1
0x1808d4340  lea     r9, aAllowscriptacc; "allowscriptaccess"
0x1808d4347  movzx   edx, word ptr [r8]
0x1808d434b  movzx   ecx, word ptr [r9]
0x1808d434f  test    dx, dx
0x1808d4352  jz      short loc_1808D43D1
0x1808d4354  cmp     dx, cx
0x1808d4357  jz      short loc_1808D438C
0x1808d4359  movzx   eax, dx
0x1808d435c  sub     ax, r15w
0x1808d4360  cmp     ax, r12w
0x1808d4364  movzx   eax, cx
0x1808d4367  ja      short loc_1808D4379
0x1808d4369  add     dx, r14w
0x1808d436d  sub     ax, r15w
0x1808d4371  cmp     ax, r12w
0x1808d4375  ja      short loc_1808D4387
0x1808d4377  jmp     short loc_1808D4383
0x1808d4379  sub     ax, r15w
0x1808d437d  cmp     ax, r12w
0x1808d4381  ja      short loc_1808D4394
0x1808d4383  add     cx, r14w
0x1808d4387  cmp     dx, cx
0x1808d438a  jnz     short loc_1808D4394
0x1808d438c  add     r8, r13
0x1808d438f  add     r9, r13
0x1808d4392  jmp     short loc_1808D4347
0x1808d4394  movzx   ecx, cx
0x1808d4397  movzx   eax, dx
0x1808d439a  or      ecx, eax
0x1808d439c  test    ecx, 0FFFFFF80h
0x1808d43a2  jz      loc_1808D456C
0x1808d43a8  or      eax, 0FFFFFFFFh
0x1808d43ab  mov     edx, 31001h; dwCmpFlags
0x1808d43b0  mov     [rsp+78h+cchCount2], eax; cchCount2
0x1808d43b4  xor     ecx, ecx; Locale
0x1808d43b6  mov     [rsp+78h+lpString2], r9; lpString2
0x1808d43bb  mov     r9d, eax; cchCount1
0x1808d43be  call    cs:__imp_CompareStringW
0x1808d43c4  test    eax, eax
0x1808d43c6  jle     loc_1808D456C
0x1808d43cc  add     eax, 0FFFFFFFEh
0x1808d43cf  jmp     short loc_1808D43D6
0x1808d43d1  neg     cx
0x1808d43d4  sbb     eax, eax
0x1808d43d6  test    eax, eax
0x1808d43d8  jnz     loc_1808D456C
0x1808d43de  lea     rdx, [rsp+78h+pbstr]; unsigned __int16 **
0x1808d43e6  mov     [rsp+78h+pbstr], rbp
0x1808d43ee  mov     rcx, rdi; this
0x1808d43f1  call    ?get_value@CParamElement@@QEAAJPEAPEAG@Z; CParamElement::get_value(ushort * *)
0x1808d43f6  mov     rbx, [rsp+78h+pbstr]
0x1808d43fe  test    eax, eax
0x1808d4400  js      loc_1808D489F
0x1808d4406  mov     rcx, rbx; pbstr
0x1808d4409  call    cs:__imp_SysStringLen
0x1808d440f  test    eax, eax
0x1808d4411  jz      loc_1808D489F
0x1808d4417  mov     r8, rbx; lpString1
0x1808d441a  test    rbx, rbx
0x1808d441d  jz      loc_1808D44B9
0x1808d4423  lea     r9, aAlways; "always"
0x1808d442a  movzx   edx, word ptr [r8]
0x1808d442e  movzx   ecx, word ptr [r9]
0x1808d4432  test    dx, dx
0x1808d4435  jz      short loc_1808D44AC
0x1808d4437  cmp     dx, cx
0x1808d443a  jz      short loc_1808D446F
0x1808d443c  movzx   eax, dx
0x1808d443f  sub     ax, r15w
0x1808d4443  cmp     ax, r12w
0x1808d4447  movzx   eax, cx
0x1808d444a  ja      short loc_1808D445C
0x1808d444c  add     dx, r14w
0x1808d4450  sub     ax, r15w
0x1808d4454  cmp     ax, r12w
0x1808d4458  ja      short loc_1808D446A
0x1808d445a  jmp     short loc_1808D4466
0x1808d445c  sub     ax, r15w
0x1808d4460  cmp     ax, r12w
0x1808d4464  ja      short loc_1808D4477
0x1808d4466  add     cx, r14w
0x1808d446a  cmp     dx, cx
0x1808d446d  jnz     short loc_1808D4477
0x1808d446f  add     r8, r13
0x1808d4472  add     r9, r13
0x1808d4475  jmp     short loc_1808D442A
0x1808d4477  movzx   ecx, cx
0x1808d447a  movzx   eax, dx
0x1808d447d  or      ecx, eax
0x1808d447f  test    ecx, 0FFFFFF80h
0x1808d4485  jz      short loc_1808D44B9
0x1808d4487  or      eax, 0FFFFFFFFh
0x1808d448a  mov     edx, 31001h; dwCmpFlags
0x1808d448f  mov     [rsp+78h+cchCount2], eax; cchCount2
0x1808d4493  xor     ecx, ecx; Locale
0x1808d4495  mov     [rsp+78h+lpString2], r9; lpString2
0x1808d449a  mov     r9d, eax; cchCount1
0x1808d449d  call    cs:__imp_CompareStringW
0x1808d44a3  test    eax, eax
0x1808d44a5  jle     short loc_1808D44B9
0x1808d44a7  add     eax, 0FFFFFFFEh
0x1808d44aa  jmp     short loc_1808D44B1
0x1808d44ac  neg     cx
0x1808d44af  sbb     eax, eax
0x1808d44b1  test    eax, eax
0x1808d44b3  jz      loc_1808D4563
0x1808d44b9  mov     r8, rbx; lpString1
0x1808d44bc  test    rbx, rbx
0x1808d44bf  jz      loc_1808D489F
0x1808d44c5  lea     r9, aSamedomain; "samedomain"
0x1808d44cc  movzx   edx, word ptr [r8]
0x1808d44d0  movzx   ecx, word ptr [r9]
0x1808d44d4  test    dx, dx
0x1808d44d7  jz      short loc_1808D4556
0x1808d44d9  cmp     dx, cx
0x1808d44dc  jz      short loc_1808D4511
0x1808d44de  movzx   eax, dx
0x1808d44e1  sub     ax, r15w
0x1808d44e5  cmp     ax, r12w
0x1808d44e9  movzx   eax, cx
0x1808d44ec  ja      short loc_1808D44FE
0x1808d44ee  add     dx, r14w
0x1808d44f2  sub     ax, r15w
0x1808d44f6  cmp     ax, r12w
0x1808d44fa  ja      short loc_1808D450C
0x1808d44fc  jmp     short loc_1808D4508
0x1808d44fe  sub     ax, r15w
0x1808d4502  cmp     ax, r12w
0x1808d4506  ja      short loc_1808D4519
0x1808d4508  add     cx, r14w
0x1808d450c  cmp     dx, cx
0x1808d450f  jnz     short loc_1808D4519
0x1808d4511  add     r8, r13
0x1808d4514  add     r9, r13
0x1808d4517  jmp     short loc_1808D44CC
0x1808d4519  movzx   ecx, cx
0x1808d451c  movzx   eax, dx
0x1808d451f  or      ecx, eax
0x1808d4521  test    ecx, 0FFFFFF80h
0x1808d4527  jz      loc_1808D489F
0x1808d452d  or      eax, 0FFFFFFFFh
0x1808d4530  mov     edx, 31001h; dwCmpFlags
0x1808d4535  mov     [rsp+78h+cchCount2], eax; cchCount2
0x1808d4539  xor     ecx, ecx; Locale
0x1808d453b  mov     [rsp+78h+lpString2], r9; lpString2
0x1808d4540  mov     r9d, eax; cchCount1
0x1808d4543  call    cs:__imp_CompareStringW
0x1808d4549  test    eax, eax
0x1808d454b  jle     loc_1808D489F
0x1808d4551  add     eax, 0FFFFFFFEh
0x1808d4554  jmp     short loc_1808D455B
0x1808d4556  neg     cx
0x1808d4559  sbb     eax, eax
0x1808d455b  test    eax, eax
0x1808d455d  jnz     loc_1808D489F
0x1808d4563  mov     byte ptr [rsi+1], 1
0x1808d4567  jmp     loc_1808D489F
0x1808d456c  mov     r8, rbx; lpString1
0x1808d456f  lea     r9, aMovie; "movie"
0x1808d4576  movzx   edx, word ptr [r8]
0x1808d457a  movzx   ecx, word ptr [r9]
0x1808d457e  test    dx, dx
0x1808d4581  jz      short loc_1808D45F8
0x1808d4583  cmp     dx, cx
0x1808d4586  jz      short loc_1808D45BB
0x1808d4588  movzx   eax, dx
0x1808d458b  sub     ax, r15w
0x1808d458f  cmp     ax, r12w
0x1808d4593  movzx   eax, cx
0x1808d4596  ja      short loc_1808D45A8
0x1808d4598  add     dx, r14w
  ... truncated ...
```
