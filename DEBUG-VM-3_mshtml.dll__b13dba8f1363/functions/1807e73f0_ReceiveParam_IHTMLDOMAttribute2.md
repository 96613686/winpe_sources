# ReceiveParam_IHTMLDOMAttribute2_

- ea: `0x1807e73f0`
- end: `0x1807e7b42`
- name: `ReceiveParam_IHTMLDOMAttribute2_`
- size: `1874`
- prototype: `__int64 __fastcall(PCNZWCH lpString1)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1808d4fe4`

## callees

- `0x1807e73f0`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1807e74ac`
- `KERNEL32!CompareStringW` at `0x1807e7586`
- `KERNEL32!CompareStringW` at `0x1807e763f`
- `KERNEL32!CompareStringW` at `0x1807e7719`
- `KERNEL32!CompareStringW` at `0x1807e77c2`
- `KERNEL32!CompareStringW` at `0x1807e786a`
- `KERNEL32!CompareStringW` at `0x1807e7905`
- `KERNEL32!CompareStringW` at `0x1807e79a0`
- `KERNEL32!CompareStringW` at `0x1807e7a3b`
- `KERNEL32!CompareStringW` at `0x1807e7add`
- `KERNEL32!CompareStringW` at `0x1807e74ac`
- `KERNEL32!CompareStringW` at `0x1807e7586`
- `KERNEL32!CompareStringW` at `0x1807e763f`
- `KERNEL32!CompareStringW` at `0x1807e7719`
- `KERNEL32!CompareStringW` at `0x1807e77c2`
- `KERNEL32!CompareStringW` at `0x1807e786a`
- `KERNEL32!CompareStringW` at `0x1807e7905`
- `KERNEL32!CompareStringW` at `0x1807e79a0`
- `KERNEL32!CompareStringW` at `0x1807e7a3b`
- `KERNEL32!CompareStringW` at `0x1807e7add`
- `OLEAUT32!__imp_SysFreeString` at `0x1807e75a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1807e75a5`
- `OLEAUT32!__imp_SysStringLen` at `0x1807e74ef`
- `OLEAUT32!__imp_SysStringLen` at `0x1807e7682`
- `OLEAUT32!__imp_SysStringLen` at `0x1807e7b20`
- `OLEAUT32!__imp_SysStringLen` at `0x1807e74ef`
- `OLEAUT32!__imp_SysStringLen` at `0x1807e7682`
- `OLEAUT32!__imp_SysStringLen` at `0x1807e7b20`

## string_xrefs

- `0x1807e75bf`: `allowscriptaccess`

## pseudocode

```c
void __fastcall ReceiveParam_IHTMLDOMAttribute2_(PCNZWCH lpString1, __int64 *a2, __int64 a3)
{
  const WCHAR *lpString2; // r9
  PCNZWCH v5; // r8
  PCNZWCH v7; // rbx
  WCHAR v8; // dx
  WCHAR v9; // cx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax
  BSTR v13; // r8
  const WCHAR *v14; // r9
  WCHAR v15; // dx
  WCHAR v16; // cx
  int v17; // eax
  int v18; // eax
  OLECHAR *v19; // rcx
  const WCHAR *v20; // r8
  const WCHAR *v21; // r9
  WCHAR v22; // dx
  WCHAR v23; // cx
  int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  BSTR v27; // r8
  const WCHAR *v28; // r9
  WCHAR v29; // dx
  WCHAR v30; // cx
  int v31; // eax
  int v32; // eax
  BSTR v33; // r8
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
  __int64 v68; // rax
  BSTR v69; // rax
  BSTR pbstr; // [rsp+80h] [rbp+48h] BYREF

  if ( !lpString1 )
    return;
  lpString2 = L"allowfullscreen";
  v5 = lpString1;
  v7 = lpString1;
  while ( 1 )
  {
    v8 = *v5;
    v9 = *lpString2;
    if ( !*v5 )
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
        v10 = CompareStringW(0, 0x31001u, v5, -1, lpString2, -1);
        if ( v10 > 0 )
        {
          v11 = v10 - 2;
          goto LABEL_16;
        }
      }
      goto LABEL_39;
    }
LABEL_11:
    ++v5;
    ++lpString2;
  }
  v11 = -(v9 != 0);
LABEL_16:
  if ( !v11 )
  {
    v12 = *a2;
    pbstr = 0;
    if ( (*(int (__fastcall **)(__int64 *, BSTR *))(v12 + 72))(a2, &pbstr) < 0 )
      goto LABEL_36;
    if ( !SysStringLen(pbstr) )
      goto LABEL_36;
    v13 = pbstr;
    if ( !pbstr )
      goto LABEL_36;
    v14 = L"true";
    while ( 2 )
    {
      v15 = *v13;
      v16 = *v14;
      if ( !*v13 )
      {
        v18 = -(v16 != 0);
LABEL_34:
        if ( !v18 )
          *(_BYTE *)a3 = 1;
        goto LABEL_36;
      }
      if ( v15 != v16 )
      {
        if ( (unsigned __int16)(v15 - 65) > 0x19u )
        {
          if ( (unsigned __int16)(v16 - 65) > 0x19u )
            goto LABEL_30;
LABEL_27:
          v16 += 32;
        }
        else
        {
          v15 += 32;
          if ( (unsigned __int16)(v16 - 65) <= 0x19u )
            goto LABEL_27;
        }
        if ( v15 != v16 )
        {
LABEL_30:
          if ( ((v15 | v16) & 0xFF80) != 0 )
          {
            v17 = CompareStringW(0, 0x31001u, v13, -1, v14, -1);
            if ( v17 > 0 )
            {
              v18 = v17 - 2;
              goto LABEL_34;
            }
          }
LABEL_36:
          v19 = pbstr;
          goto LABEL_37;
        }
      }
      ++v13;
      ++v14;
      continue;
    }
  }
LABEL_39:
  v20 = v7;
  v21 = L"allowscriptaccess";
  while ( 2 )
  {
    v22 = *v20;
    v23 = *v21;
    if ( *v20 )
    {
      if ( v22 != v23 )
      {
        if ( (unsigned __int16)(v22 - 65) > 0x19u )
        {
          if ( (unsigned __int16)(v23 - 65) > 0x19u )
            goto LABEL_49;
LABEL_46:
          v23 += 32;
        }
        else
        {
          v22 += 32;
          if ( (unsigned __int16)(v23 - 65) <= 0x19u )
            goto LABEL_46;
        }
        if ( v22 != v23 )
        {
LABEL_49:
          if ( ((v22 | v23) & 0xFF80) != 0 )
          {
            v24 = CompareStringW(0, 0x31001u, v20, -1, v21, -1);
            if ( v24 > 0 )
            {
              v25 = v24 - 2;
              goto LABEL_53;
            }
          }
          goto LABEL_89;
        }
      }
      ++v20;
      ++v21;
      continue;
    }
    break;
  }
  v25 = -(v23 != 0);
LABEL_53:
  if ( !v25 )
  {
    v26 = *a2;
    pbstr = 0;
    if ( (*(int (__fastcall **)(__int64 *, BSTR *))(v26 + 72))(a2, &pbstr) < 0 || !SysStringLen(pbstr) )
      goto LABEL_36;
    v27 = pbstr;
    if ( !pbstr )
      goto LABEL_72;
    v28 = L"always";
    while ( 2 )
    {
      v29 = *v27;
      v30 = *v28;
      if ( !*v27 )
      {
        v32 = -(v30 != 0);
        goto LABEL_71;
      }
      if ( v29 != v30 )
      {
        if ( (unsigned __int16)(v29 - 65) > 0x19u )
        {
          if ( (unsigned __int16)(v30 - 65) > 0x19u )
            goto LABEL_67;
LABEL_64:
          v30 += 32;
        }
        else
        {
          v29 += 32;
          if ( (unsigned __int16)(v30 - 65) <= 0x19u )
            goto LABEL_64;
        }
        if ( v29 != v30 )
        {
LABEL_67:
          if ( ((v29 | v30) & 0xFF80) != 0 )
          {
            v31 = CompareStringW(0, 0x31001u, v27, -1, v28, -1);
            if ( v31 > 0 )
            {
              v32 = v31 - 2;
LABEL_71:
              if ( !v32 )
                goto LABEL_88;
            }
          }
LABEL_72:
          v33 = pbstr;
          if ( !pbstr )
            goto LABEL_36;
          v34 = L"samedomain";
          while ( 2 )
          {
            v35 = *v33;
            v36 = *v34;
            if ( !*v33 )
            {
              v38 = -(v36 != 0);
              goto LABEL_87;
            }
            if ( v35 != v36 )
            {
              if ( (unsigned __int16)(v35 - 65) > 0x19u )
              {
                if ( (unsigned __int16)(v36 - 65) > 0x19u )
                  goto LABEL_83;
LABEL_80:
                v36 += 32;
              }
              else
              {
                v35 += 32;
                if ( (unsigned __int16)(v36 - 65) <= 0x19u )
                  goto LABEL_80;
              }
              if ( v35 != v36 )
              {
LABEL_83:
                if ( ((v35 | v36) & 0xFF80) == 0 )
                  goto LABEL_36;
                v37 = CompareStringW(0, 0x31001u, v33, -1, v34, -1);
                if ( v37 <= 0 )
                  goto LABEL_36;
                v38 = v37 - 2;
LABEL_87:
                if ( v38 )
                  goto LABEL_36;
LABEL_88:
                *(_BYTE *)(a3 + 1) = 1;
                goto LABEL_36;
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
LABEL_89:
  v39 = v7;
  v40 = L"movie";
  while ( 2 )
  {
    v41 = *v39;
    v42 = *v40;
    if ( !*v39 )
    {
      v44 = -(v42 != 0);
      goto LABEL_103;
    }
    if ( v41 == v42 )
      goto LABEL_98;
    if ( (unsigned __int16)(v41 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v42 - 65) > 0x19u )
        break;
LABEL_96:
      v42 += 32;
    }
    else
    {
      v41 += 32;
      if ( (unsigned __int16)(v42 - 65) <= 0x19u )
        goto LABEL_96;
    }
    if ( v41 == v42 )
    {
LABEL_98:
      ++v39;
      ++v40;
      continue;
    }
    break;
  }
  if ( ((v41 | v42) & 0xFF80) == 0 )
    goto LABEL_104;
  v43 = CompareStringW(0, 0x31001u, v39, -1, v40, -1);
  if ( v43 <= 0 )
    goto LABEL_104;
  v44 = v43 - 2;
LABEL_103:
  if ( !v44 )
    goto LABEL_164;
LABEL_104:
  v45 = v7;
  v46 = L"src";
  while ( 2 )
  {
    v47 = *v45;
    v48 = *v46;
    if ( !*v45 )
    {
      v50 = -(v48 != 0);
      goto LABEL_118;
    }
    if ( v47 == v48 )
      goto LABEL_113;
    if ( (unsigned __int16)(v47 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v48 - 65) > 0x19u )
        break;
LABEL_111:
      v48 += 32;
    }
    else
    {
      v47 += 32;
      if ( (unsigned __int16)(v48 - 65) <= 0x19u )
        goto LABEL_111;
    }
    if ( v47 == v48 )
    {
LABEL_113:
      ++v45;
      ++v46;
      continue;
    }
    break;
  }
  if ( ((v47 | v48) & 0xFF80) == 0 )
    goto LABEL_119;
  v49 = CompareStringW(0, 0x31001u, v45, -1, v46, -1);
  if ( v49 <= 0 )
    goto LABEL_119;
  v50 = v49 - 2;
LABEL_118:
  if ( !v50 )
    goto LABEL_164;
LABEL_119:
  v51 = v7;
  v52 = L"filename";
  while ( 2 )
  {
    v53 = *v51;
    v54 = *v52;
    if ( !*v51 )
    {
      v56 = -(v54 != 0);
      goto LABEL_133;
    }
    if ( v53 == v54 )
      goto LABEL_128;
    if ( (unsigned __int16)(v53 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v54 - 65) > 0x19u )
        break;
LABEL_126:
      v54 += 32;
    }
    else
    {
      v53 += 32;
      if ( (unsigned __int16)(v54 - 65) <= 0x19u )
        goto LABEL_126;
    }
    if ( v53 == v54 )
    {
LABEL_128:
      ++v51;
      ++v52;
      continue;
    }
    break;
  }
  if ( ((v53 | v54) & 0xFF80) == 0 )
    goto LABEL_134;
  v55 = CompareStringW(0, 0x31001u, v51, -1, v52, -1);
  if ( v55 <= 0 )
    goto LABEL_134;
  v56 = v55 - 2;
LABEL_133:
  if ( !v56 )
    goto LABEL_164;
LABEL_134:
  v57 = v7;
  v58 = L"url";
  while ( 2 )
  {
    v59 = *v57;
    v60 = *v58;
    if ( !*v57 )
    {
      v62 = -(v60 != 0);
      goto LABEL_148;
    }
    if ( v59 == v60 )
      goto LABEL_143;
    if ( (unsigned __int16)(v59 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v60 - 65) > 0x19u )
        break;
LABEL_141:
      v60 += 32;
    }
    else
    {
      v59 += 32;
      if ( (unsigned __int16)(v60 - 65) <= 0x19u )
        goto LABEL_141;
    }
    if ( v59 == v60 )
    {
LABEL_143:
      ++v57;
      ++v58;
      continue;
    }
    break;
  }
  if ( ((v59 | v60) & 0xFF80) == 0 )
    goto LABEL_149;
  v61 = CompareStringW(0, 0x31001u, v57, -1, v58, -1);
  if ( v61 <= 0 )
    goto LABEL_149;
  v62 = v61 - 2;
LABEL_148:
  if ( !v62 )
    goto LABEL_164;
LABEL_149:
  v63 = L"source";
  while ( 2 )
  {
    v64 = *v7;
    v65 = *v63;
    if ( !*v7 )
    {
      v67 = -(v65 != 0);
      goto LABEL_163;
    }
    if ( v64 == v65 )
      goto LABEL_158;
    if ( (unsigned __int16)(v64 - 65) > 0x19u )
    {
      if ( (unsigned __int16)(v65 - 65) > 0x19u )
        break;
LABEL_156:
      v65 += 32;
    }
    else
    {
      v64 += 32;
      if ( (unsigned __int16)(v65 - 65) <= 0x19u )
        goto LABEL_156;
    }
    if ( v64 == v65 )
    {
LABEL_158:
      ++v7;
      ++v63;
      continue;
    }
    break;
  }
  if ( ((v64 | v65) & 0xFF80) == 0 )
    return;
  v66 = CompareStringW(0, 0x31001u, v7, -1, v63, -1);
  if ( v66 <= 0 )
    return;
  v67 = v66 - 2;
LABEL_163:
  if ( v67 )
    return;
LABEL_164:
  v68 = *a2;
  pbstr = 0;
  if ( (*(int (__fastcall **)(__int64 *, BSTR *))(v68 + 72))(a2, &pbstr) < 0 || !SysStringLen(pbstr) )
    goto LABEL_36;
  v69 = pbstr;
  v19 = 0;
  pbstr = 0;
  *(_QWORD *)(a3 + 8) = v69;
LABEL_37:
  SysFreeString(v19);
}

```

## disassembly

```asm
0x1807e73f0  test    rcx, rcx
0x1807e73f3  jz      locret_1807E75BB
0x1807e73f9  push    rbp
0x1807e73fa  push    rbx
0x1807e73fb  push    rsi
0x1807e73fc  push    rdi
0x1807e73fd  push    r12
0x1807e73ff  push    r13
0x1807e7401  push    r14
0x1807e7403  push    r15
0x1807e7405  mov     rbp, rsp
0x1807e7408  sub     rsp, 38h
0x1807e740c  mov     rsi, r8
0x1807e740f  lea     r9, aAllowfullscree_0; "allowfullscreen"
0x1807e7416  mov     r8, rcx; lpString1
0x1807e7419  mov     rdi, rdx
0x1807e741c  mov     rbx, rcx
0x1807e741f  xor     r14d, r14d
0x1807e7422  mov     r12w, 41h ; 'A'
0x1807e7427  mov     r13w, 19h
0x1807e742c  mov     r15w, 20h ; ' '
0x1807e7431  movzx   edx, word ptr [r8]
0x1807e7435  or      r10d, 0FFFFFFFFh
0x1807e7439  movzx   ecx, word ptr [r9]
0x1807e743d  test    dx, dx
0x1807e7440  jz      short loc_1807E74BF
0x1807e7442  cmp     dx, cx
0x1807e7445  jz      short loc_1807E747A
0x1807e7447  movzx   eax, dx
0x1807e744a  sub     ax, r12w
0x1807e744e  cmp     ax, r13w
0x1807e7452  movzx   eax, cx
0x1807e7455  ja      short loc_1807E7467
0x1807e7457  add     dx, r15w
0x1807e745b  sub     ax, r12w
0x1807e745f  cmp     ax, r13w
0x1807e7463  ja      short loc_1807E7475
0x1807e7465  jmp     short loc_1807E7471
0x1807e7467  sub     ax, r12w
0x1807e746b  cmp     ax, r13w
0x1807e746f  ja      short loc_1807E7484
0x1807e7471  add     cx, r15w
0x1807e7475  cmp     dx, cx
0x1807e7478  jnz     short loc_1807E7484
0x1807e747a  add     r8, 2
0x1807e747e  add     r9, 2
0x1807e7482  jmp     short loc_1807E7431
0x1807e7484  movzx   ecx, cx
0x1807e7487  movzx   eax, dx
0x1807e748a  or      ecx, eax
0x1807e748c  test    ecx, 0FFFFFF80h
0x1807e7492  jz      loc_1807E75BC
0x1807e7498  mov     [rsp+38h+cchCount2], r10d; cchCount2
0x1807e749d  mov     edx, 31001h; dwCmpFlags
0x1807e74a2  mov     [rsp+38h+lpString2], r9; lpString2
0x1807e74a7  xor     ecx, ecx; Locale
0x1807e74a9  mov     r9d, r10d; cchCount1
0x1807e74ac  call    cs:__imp_CompareStringW
0x1807e74b2  test    eax, eax
0x1807e74b4  jle     loc_1807E75BC
0x1807e74ba  add     eax, 0FFFFFFFEh
0x1807e74bd  jmp     short loc_1807E74C4
0x1807e74bf  neg     cx
0x1807e74c2  sbb     eax, eax
0x1807e74c4  test    eax, eax
0x1807e74c6  jnz     loc_1807E75BC
0x1807e74cc  mov     rax, [rdi]
0x1807e74cf  lea     rdx, [rbp+pbstr]
0x1807e74d3  mov     rcx, rdi
0x1807e74d6  mov     [rbp+pbstr], r14
0x1807e74da  mov     rax, [rax+48h]
0x1807e74de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807e74e3  test    eax, eax
0x1807e74e5  js      loc_1807E75A1
0x1807e74eb  mov     rcx, [rbp+pbstr]; pbstr
0x1807e74ef  call    cs:__imp_SysStringLen
0x1807e74f5  test    eax, eax
0x1807e74f7  jz      loc_1807E75A1
0x1807e74fd  mov     r8, [rbp+pbstr]; lpString1
0x1807e7501  test    r8, r8
0x1807e7504  jz      loc_1807E75A1
0x1807e750a  lea     r9, pszStr2; "true"
0x1807e7511  movzx   edx, word ptr [r8]
0x1807e7515  movzx   ecx, word ptr [r9]
0x1807e7519  test    dx, dx
0x1807e751c  jz      short loc_1807E7595
0x1807e751e  cmp     dx, cx
0x1807e7521  jz      short loc_1807E7556
0x1807e7523  movzx   eax, dx
0x1807e7526  sub     ax, r12w
0x1807e752a  cmp     ax, r13w
0x1807e752e  movzx   eax, cx
0x1807e7531  ja      short loc_1807E7543
0x1807e7533  add     dx, r15w
0x1807e7537  sub     ax, r12w
0x1807e753b  cmp     ax, r13w
0x1807e753f  ja      short loc_1807E7551
0x1807e7541  jmp     short loc_1807E754D
0x1807e7543  sub     ax, r12w
0x1807e7547  cmp     ax, r13w
0x1807e754b  ja      short loc_1807E7560
0x1807e754d  add     cx, r15w
0x1807e7551  cmp     dx, cx
0x1807e7554  jnz     short loc_1807E7560
0x1807e7556  add     r8, 2
0x1807e755a  add     r9, 2
0x1807e755e  jmp     short loc_1807E7511
0x1807e7560  movzx   ecx, cx
0x1807e7563  movzx   eax, dx
0x1807e7566  or      ecx, eax
0x1807e7568  test    ecx, 0FFFFFF80h
0x1807e756e  jz      short loc_1807E75A1
0x1807e7570  or      eax, 0FFFFFFFFh
0x1807e7573  mov     edx, 31001h; dwCmpFlags
0x1807e7578  mov     [rsp+38h+cchCount2], eax; cchCount2
0x1807e757c  xor     ecx, ecx; Locale
0x1807e757e  mov     [rsp+38h+lpString2], r9; lpString2
0x1807e7583  mov     r9d, eax; cchCount1
0x1807e7586  call    cs:__imp_CompareStringW
0x1807e758c  test    eax, eax
0x1807e758e  jle     short loc_1807E75A1
0x1807e7590  add     eax, 0FFFFFFFEh
0x1807e7593  jmp     short loc_1807E759A
0x1807e7595  neg     cx
0x1807e7598  sbb     eax, eax
0x1807e759a  test    eax, eax
0x1807e759c  jnz     short loc_1807E75A1
0x1807e759e  mov     byte ptr [rsi], 1
0x1807e75a1  mov     rcx, [rbp+pbstr]; bstrString
0x1807e75a5  call    cs:__imp_SysFreeString
0x1807e75ab  add     rsp, 38h
0x1807e75af  pop     r15
0x1807e75b1  pop     r14
0x1807e75b3  pop     r13
0x1807e75b5  pop     r12
0x1807e75b7  pop     rdi
0x1807e75b8  pop     rsi
0x1807e75b9  pop     rbx
0x1807e75ba  pop     rbp
0x1807e75bb  retn
0x1807e75bc  mov     r8, rbx; lpString1
0x1807e75bf  lea     r9, aAllowscriptacc; "allowscriptaccess"
0x1807e75c6  movzx   edx, word ptr [r8]
0x1807e75ca  movzx   ecx, word ptr [r9]
0x1807e75ce  test    dx, dx
0x1807e75d1  jz      short loc_1807E7652
0x1807e75d3  cmp     dx, cx
0x1807e75d6  jz      short loc_1807E760B
0x1807e75d8  movzx   eax, dx
0x1807e75db  sub     ax, r12w
0x1807e75df  cmp     ax, r13w
0x1807e75e3  movzx   eax, cx
0x1807e75e6  ja      short loc_1807E75F8
0x1807e75e8  add     dx, r15w
0x1807e75ec  sub     ax, r12w
0x1807e75f0  cmp     ax, r13w
0x1807e75f4  ja      short loc_1807E7606
0x1807e75f6  jmp     short loc_1807E7602
0x1807e75f8  sub     ax, r12w
0x1807e75fc  cmp     ax, r13w
0x1807e7600  ja      short loc_1807E7615
0x1807e7602  add     cx, r15w
0x1807e7606  cmp     dx, cx
0x1807e7609  jnz     short loc_1807E7615
0x1807e760b  add     r8, 2
0x1807e760f  add     r9, 2
0x1807e7613  jmp     short loc_1807E75C6
0x1807e7615  movzx   ecx, cx
0x1807e7618  movzx   eax, dx
0x1807e761b  or      ecx, eax
0x1807e761d  test    ecx, 0FFFFFF80h
0x1807e7623  jz      loc_1807E77EB
0x1807e7629  or      eax, 0FFFFFFFFh
0x1807e762c  mov     edx, 31001h; dwCmpFlags
0x1807e7631  mov     [rsp+38h+cchCount2], eax; cchCount2
0x1807e7635  xor     ecx, ecx; Locale
0x1807e7637  mov     [rsp+38h+lpString2], r9; lpString2
0x1807e763c  mov     r9d, eax; cchCount1
0x1807e763f  call    cs:__imp_CompareStringW
0x1807e7645  test    eax, eax
0x1807e7647  jle     loc_1807E77EB
0x1807e764d  add     eax, 0FFFFFFFEh
0x1807e7650  jmp     short loc_1807E7657
0x1807e7652  neg     cx
0x1807e7655  sbb     eax, eax
0x1807e7657  test    eax, eax
0x1807e7659  jnz     loc_1807E77EB
0x1807e765f  mov     rax, [rdi]
0x1807e7662  lea     rdx, [rbp+pbstr]
0x1807e7666  mov     rcx, rdi
0x1807e7669  mov     [rbp+pbstr], r14
0x1807e766d  mov     rax, [rax+48h]
0x1807e7671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807e7676  test    eax, eax
0x1807e7678  js      loc_1807E75A1
0x1807e767e  mov     rcx, [rbp+pbstr]; pbstr
0x1807e7682  call    cs:__imp_SysStringLen
0x1807e7688  test    eax, eax
0x1807e768a  jz      loc_1807E75A1
0x1807e7690  mov     r8, [rbp+pbstr]; lpString1
0x1807e7694  test    r8, r8
0x1807e7697  jz      loc_1807E7735
0x1807e769d  lea     r9, aAlways; "always"
0x1807e76a4  movzx   edx, word ptr [r8]
0x1807e76a8  movzx   ecx, word ptr [r9]
0x1807e76ac  test    dx, dx
0x1807e76af  jz      short loc_1807E7728
0x1807e76b1  cmp     dx, cx
0x1807e76b4  jz      short loc_1807E76E9
0x1807e76b6  movzx   eax, dx
0x1807e76b9  sub     ax, r12w
0x1807e76bd  cmp     ax, r13w
0x1807e76c1  movzx   eax, cx
0x1807e76c4  ja      short loc_1807E76D6
0x1807e76c6  add     dx, r15w
0x1807e76ca  sub     ax, r12w
0x1807e76ce  cmp     ax, r13w
0x1807e76d2  ja      short loc_1807E76E4
0x1807e76d4  jmp     short loc_1807E76E0
0x1807e76d6  sub     ax, r12w
0x1807e76da  cmp     ax, r13w
0x1807e76de  ja      short loc_1807E76F3
0x1807e76e0  add     cx, r15w
0x1807e76e4  cmp     dx, cx
0x1807e76e7  jnz     short loc_1807E76F3
0x1807e76e9  add     r8, 2
0x1807e76ed  add     r9, 2
0x1807e76f1  jmp     short loc_1807E76A4
0x1807e76f3  movzx   ecx, cx
0x1807e76f6  movzx   eax, dx
0x1807e76f9  or      ecx, eax
0x1807e76fb  test    ecx, 0FFFFFF80h
0x1807e7701  jz      short loc_1807E7735
0x1807e7703  or      eax, 0FFFFFFFFh
0x1807e7706  mov     edx, 31001h; dwCmpFlags
0x1807e770b  mov     [rsp+38h+cchCount2], eax; cchCount2
0x1807e770f  xor     ecx, ecx; Locale
0x1807e7711  mov     [rsp+38h+lpString2], r9; lpString2
0x1807e7716  mov     r9d, eax; cchCount1
0x1807e7719  call    cs:__imp_CompareStringW
0x1807e771f  test    eax, eax
0x1807e7721  jle     short loc_1807E7735
0x1807e7723  add     eax, 0FFFFFFFEh
0x1807e7726  jmp     short loc_1807E772D
0x1807e7728  neg     cx
0x1807e772b  sbb     eax, eax
0x1807e772d  test    eax, eax
0x1807e772f  jz      loc_1807E77E2
0x1807e7735  mov     r8, [rbp+pbstr]; lpString1
0x1807e7739  test    r8, r8
0x1807e773c  jz      loc_1807E75A1
0x1807e7742  lea     r9, aSamedomain; "samedomain"
0x1807e7749  movzx   edx, word ptr [r8]
0x1807e774d  movzx   ecx, word ptr [r9]
0x1807e7751  test    dx, dx
0x1807e7754  jz      short loc_1807E77D5
0x1807e7756  cmp     dx, cx
0x1807e7759  jz      short loc_1807E778E
0x1807e775b  movzx   eax, dx
0x1807e775e  sub     ax, r12w
0x1807e7762  cmp     ax, r13w
0x1807e7766  movzx   eax, cx
0x1807e7769  ja      short loc_1807E777B
0x1807e776b  add     dx, r15w
0x1807e776f  sub     ax, r12w
0x1807e7773  cmp     ax, r13w
0x1807e7777  ja      short loc_1807E7789
0x1807e7779  jmp     short loc_1807E7785
0x1807e777b  sub     ax, r12w
0x1807e777f  cmp     ax, r13w
0x1807e7783  ja      short loc_1807E7798
0x1807e7785  add     cx, r15w
0x1807e7789  cmp     dx, cx
0x1807e778c  jnz     short loc_1807E7798
0x1807e778e  add     r8, 2
0x1807e7792  add     r9, 2
0x1807e7796  jmp     short loc_1807E7749
0x1807e7798  movzx   ecx, cx
0x1807e779b  movzx   eax, dx
0x1807e779e  or      ecx, eax
0x1807e77a0  test    ecx, 0FFFFFF80h
0x1807e77a6  jz      loc_1807E75A1
0x1807e77ac  or      eax, 0FFFFFFFFh
0x1807e77af  mov     edx, 31001h; dwCmpFlags
0x1807e77b4  mov     [rsp+38h+cchCount2], eax; cchCount2
0x1807e77b8  xor     ecx, ecx; Locale
0x1807e77ba  mov     [rsp+38h+lpString2], r9; lpString2
0x1807e77bf  mov     r9d, eax; cchCount1
0x1807e77c2  call    cs:__imp_CompareStringW
0x1807e77c8  test    eax, eax
0x1807e77ca  jle     loc_1807E75A1
0x1807e77d0  add     eax, 0FFFFFFFEh
0x1807e77d3  jmp     short loc_1807E77DA
0x1807e77d5  neg     cx
0x1807e77d8  sbb     eax, eax
0x1807e77da  test    eax, eax
0x1807e77dc  jnz     loc_1807E75A1
0x1807e77e2  mov     byte ptr [rsi+1], 1
0x1807e77e6  jmp     loc_1807E75A1
0x1807e77eb  mov     r8, rbx; lpString1
  ... truncated ...
```
