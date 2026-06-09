# sndQueryRegistry(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong &,HKEY__ *)

- ea: `0x180017740`
- end: `0x180017e5b`
- name: `?sndQueryRegistry@@YAHPEBG00PEAGKAEAKPEAUHKEY__@@@Z`
- size: `1819`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *, HKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016da4`

## callees

- `0x180017740`
- `0x180087e80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017b9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017d82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017b9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017d82`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180017b4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180017d32`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180017b4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180017d32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017b8e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017be2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017d75`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017b8e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017be2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017d75`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180017dca`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180017dca`

## pseudocode

```c
__int64 __fastcall sndQueryRegistry(
        const unsigned __int16 *a1,
        WCHAR *a2,
        WCHAR *a3,
        unsigned __int16 *a4,
        DWORD a5,
        unsigned int *a6)
{
  WCHAR *v6; // rbx
  __int64 v7; // r13
  __int64 v8; // rdi
  WCHAR *v11; // rax
  WCHAR *v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r10
  WCHAR *v17; // rcx
  __int64 v18; // r11
  __int64 result; // rax
  WCHAR *v20; // r9
  unsigned __int64 v21; // r14
  __int64 v22; // rax
  unsigned __int16 near **v23; // rcx
  unsigned __int64 v24; // r10
  WCHAR *v25; // r11
  WCHAR *v26; // rdx
  WCHAR *v27; // rcx
  int v28; // ebx
  unsigned __int64 v29; // r14
  __int64 v30; // rax
  unsigned __int64 v31; // r9
  __int64 v32; // rbx
  WCHAR *v33; // r10
  __int64 v34; // rdx
  WCHAR *v35; // rcx
  int v36; // ebx
  unsigned __int64 v37; // rsi
  unsigned __int16 near **v38; // r14
  __int64 v39; // rcx
  unsigned __int16 near **v40; // rdx
  unsigned __int64 v41; // r9
  __int64 v42; // r11
  WCHAR *v43; // rbx
  __int64 v44; // rdx
  WCHAR *v45; // rcx
  int v46; // r11d
  unsigned __int64 v47; // rsi
  __int64 v48; // rcx
  unsigned __int64 v49; // r9
  __int64 v50; // r10
  WCHAR *v51; // r11
  __int64 v52; // rdx
  WCHAR *v53; // rcx
  int v54; // r10d
  unsigned __int64 v55; // rsi
  __int64 v56; // rcx
  unsigned __int16 near **v57; // rdx
  unsigned __int64 v58; // r10
  __int64 v59; // rbx
  WCHAR *v60; // r9
  __int64 v61; // rdx
  WCHAR *v62; // rcx
  int v63; // ebx
  __int64 v64; // rsi
  unsigned __int64 v65; // r8
  __int64 v66; // rax
  unsigned __int16 near **v67; // rdx
  WCHAR *v68; // rcx
  HKEY v69; // rcx
  LSTATUS ValueW; // ebx
  __int64 v71; // rdx
  WCHAR *v72; // rax
  __int64 v73; // rcx
  _WORD *v74; // r8
  _WORD *v75; // rcx
  WCHAR *v76; // rax
  _WORD *v77; // rdx
  unsigned __int16 near **v78; // rcx
  _WORD *v79; // rcx
  WCHAR *v80; // r11
  unsigned __int64 v81; // r8
  WCHAR *v82; // r10
  unsigned __int64 v83; // r8
  LSTATUS v84; // ebx
  unsigned __int64 v85; // r8
  WCHAR *v86; // r11
  unsigned __int64 v87; // r8
  WCHAR *v88; // r9
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  int v90; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v92; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-98h] BYREF
  unsigned int *v94; // [rsp+70h] [rbp-90h]
  WCHAR SubKey[302]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v96[4]; // [rsp+2DCh] [rbp+1DCh] BYREF

  v6 = 0;
  v7 = 2147483646;
  v94 = a6;
  v8 = 302;
  v90 = 0;
  v11 = SubKey;
  v13 = gszSchemesRootKey;
  v14 = 2147483646;
  v15 = 302;
  v16 = 0;
  do
  {
    if ( !v14 )
      break;
    if ( !*v13 )
      break;
    *v11++ = *v13++;
    --v14;
    ++v16;
    --v15;
  }
  while ( v15 );
  v17 = v11 - 1;
  v18 = v16 - 1;
  if ( v15 )
  {
    v17 = v11;
    v18 = v16;
  }
  result = 0;
  *v17 = 0;
  if ( v15 )
  {
    v20 = &SubKey[v18];
    v21 = (unsigned __int64)(2 * (302 - v18)) >> 1;
    if ( v21 - 1 > 0x7FFFFFFE )
    {
      if ( v21 )
        *v20 = 0;
      goto LABEL_93;
    }
    v22 = 2147483646;
    v23 = &gszSchemeAppsKey;
    v24 = (unsigned __int64)(2 * (302 - v18)) >> 1;
    v25 = &SubKey[v18];
    do
    {
      if ( !v22 )
        break;
      if ( !*(_WORD *)v23 )
        break;
      *v20 = *(_WORD *)v23;
      v23 = (unsigned __int16 near **)((char *)v23 + 2);
      ++v20;
      --v22;
      v6 = (WCHAR *)((char *)v6 + 1);
      --v24;
    }
    while ( v24 );
    v26 = (WCHAR *)((char *)v6 - 1);
    v27 = v20 - 1;
    if ( v24 )
      v26 = v6;
    v28 = -2147024774;
    if ( v24 )
    {
      v27 = v20;
      v28 = 0;
    }
    *v27 = 0;
    v80 = &v25[(_QWORD)v26];
    v81 = 2 * (v21 - (_QWORD)v26);
    if ( !v28 )
    {
      v29 = v81 >> 1;
      if ( (v81 >> 1) - 1 > 0x7FFFFFFE )
      {
        if ( v29 )
        {
          *v80 = 0;
          LODWORD(v6) = 0;
          goto LABEL_93;
        }
        goto LABEL_101;
      }
      v30 = 2147483646;
      v31 = v81 >> 1;
      v32 = 0;
      v33 = v80;
      do
      {
        if ( !v30 )
          break;
        if ( !*a2 )
          break;
        *v80++ = *a2++;
        --v30;
        ++v32;
        --v31;
      }
      while ( v31 );
      v34 = v32 - 1;
      v35 = v80 - 1;
      if ( v31 )
        v34 = v32;
      v36 = -2147024774;
      if ( v31 )
      {
        v35 = v80;
        v36 = 0;
      }
      *v35 = 0;
      v82 = &v33[v34];
      v83 = 2 * (v29 - v34);
      if ( !v36 )
      {
        v37 = v83 >> 1;
        if ( (v83 >> 1) - 1 > 0x7FFFFFFE )
        {
          if ( v37 )
          {
            *v82 = 0;
            LODWORD(v6) = 0;
            goto LABEL_93;
          }
          goto LABEL_101;
        }
        v38 = &gszSlash;
        v39 = 2147483646;
        v40 = &gszSlash;
        v41 = v83 >> 1;
        v42 = 0;
        v43 = v82;
        do
        {
          if ( !v39 )
            break;
          if ( !*(_WORD *)v40 )
            break;
          *v82 = *(_WORD *)v40;
          v40 = (unsigned __int16 near **)((char *)v40 + 2);
          ++v82;
          --v39;
          ++v42;
          --v41;
        }
        while ( v41 );
        v44 = v42 - 1;
        v45 = v82 - 1;
        if ( v41 )
          v44 = v42;
        v46 = -2147024774;
        if ( v41 )
        {
          v45 = v82;
          v46 = 0;
        }
        *v45 = 0;
        v6 = &v43[v44];
        v85 = 2 * (v37 - v44);
        if ( !v46 )
        {
          v47 = v85 >> 1;
          if ( (v85 >> 1) - 1 > 0x7FFFFFFE )
          {
            if ( v47 )
            {
              *v6 = 0;
              LODWORD(v6) = 0;
              goto LABEL_93;
            }
            goto LABEL_101;
          }
          v48 = 2147483646;
          v49 = v85 >> 1;
          v50 = 0;
          v51 = v6;
          do
          {
            if ( !v48 )
              break;
            if ( !*a3 )
              break;
            *v6++ = *a3++;
            --v48;
            ++v50;
            --v49;
          }
          while ( v49 );
          v52 = v50 - 1;
          v53 = v6 - 1;
          if ( v49 )
            v52 = v50;
          v54 = -2147024774;
          if ( v49 )
          {
            v53 = v6;
            v54 = 0;
          }
          *v53 = 0;
          v86 = &v51[v52];
          v87 = (v85 & 1) + 2 * (v47 - v52);
          if ( !v54 )
          {
            v55 = v87 >> 1;
            if ( (v87 >> 1) - 1 > 0x7FFFFFFE )
            {
              if ( !v55 )
                goto LABEL_101;
              *v86 = 0;
            }
            else
            {
              v56 = 2147483646;
              v57 = &gszSlash;
              v58 = v87 >> 1;
              v59 = 0;
              v60 = v86;
              do
              {
                if ( !v56 )
                  break;
                if ( !*(_WORD *)v57 )
                  break;
                *v86 = *(_WORD *)v57;
                v57 = (unsigned __int16 near **)((char *)v57 + 2);
                ++v86;
                --v56;
                ++v59;
                --v58;
              }
              while ( v58 );
              v61 = v59 - 1;
              v62 = v86 - 1;
              if ( v58 )
              {
                v61 = v59;
                v62 = v86;
              }
              v63 = -2147024774;
              if ( v58 )
                v63 = 0;
              v64 = v55 - v61;
              *v62 = 0;
              v88 = &v60[v61];
              if ( v63 )
                goto LABEL_101;
              v65 = (unsigned __int64)(2 * v64) >> 1;
              if ( v65 - 1 <= 0x7FFFFFFE )
              {
                v66 = 2147483646;
                v67 = &aszCurrent;
                do
                {
                  if ( !v66 )
                    break;
                  if ( !*(_WORD *)v67 )
                    break;
                  *v88 = *(_WORD *)v67;
                  v67 = (unsigned __int16 near **)((char *)v67 + 2);
                  ++v88;
                  --v66;
                  --v65;
                }
                while ( v65 );
                v68 = v88 - 1;
                if ( v65 )
                  v68 = v88;
                *v68 = 0;
                if ( v65 )
                {
                  phkResult = 0;
                  *a4 = 0;
                  if ( !RegOpenCurrentUser(1u, &phkResult) )
                  {
                    v69 = phkResult;
                    pcbData = a5;
                    *a4 = 0;
                    ValueW = RegGetValueW(v69, SubKey, 0, 2u, 0, a4, &pcbData);
                    RegCloseKey(phkResult);
                    if ( !ValueW )
                    {
                      v92 = 4;
                      if ( !RegGetValueW(HKEY_CURRENT_USER, SubKey, gszDefaultFlags, 0x10u, 0, &v90, &v92) )
                        v90 &= 0x380002u;
                      v71 = 302;
                      v72 = SubKey;
                      while ( *v72 )
                      {
                        ++v72;
                        if ( !--v71 )
                          goto LABEL_92;
                      }
                      v73 = 2147483646;
                      v74 = &v96[-2 * v71];
                      do
                      {
                        if ( !v73 )
                          break;
                        if ( !*(_WORD *)v38 )
                          break;
                        *v74 = *(_WORD *)v38;
                        v38 = (unsigned __int16 near **)((char *)v38 + 2);
                        ++v74;
                        --v73;
                        --v71;
                      }
                      while ( v71 );
                      v75 = v74 - 1;
                      if ( v71 )
                        v75 = v74;
                      *v75 = 0;
                      if ( !v71 )
                        goto LABEL_92;
                      v76 = SubKey;
                      while ( *v76 )
                      {
                        ++v76;
                        if ( !--v8 )
                          goto LABEL_92;
                      }
                      v77 = &v96[-2 * v8];
                      v78 = &aszActiveKey;
                      do
                      {
                        if ( !v7 )
                          break;
                        if ( !*(_WORD *)v78 )
                          break;
                        *v77 = *(_WORD *)v78;
                        v78 = (unsigned __int16 near **)((char *)v78 + 2);
                        ++v77;
                        --v7;
                        --v8;
                      }
                      while ( v8 );
                      v79 = v77 - 1;
                      if ( v8 )
                        v79 = v77;
                      *v79 = 0;
                      if ( !v8 )
                        goto LABEL_92;
                      pcbData = 0;
                      hkey = 0;
                      if ( RegOpenCurrentUser(1u, &hkey)
                        || (LODWORD(phkResult) = 4,
                            LOWORD(pcbData) = 0,
                            v84 = RegGetValueW(hkey, SubKey, 0, 2u, 0, &pcbData, (LPDWORD)&phkResult),
                            RegCloseKey(hkey),
                            v84)
                        || !lstrcmpW((LPCWSTR)&pcbData, aszBoolOne) )
                      {
                        LODWORD(v6) = 1;
                        goto LABEL_93;
                      }
                    }
                  }
                }
                goto LABEL_101;
              }
              if ( !v65 )
                goto LABEL_101;
              *v88 = 0;
            }
LABEL_92:
            LODWORD(v6) = 0;
LABEL_93:
            if ( v90 )
              *v94 |= v90;
            return (unsigned int)v6;
          }
        }
      }
    }
LABEL_101:
    LODWORD(v6) = 0;
    goto LABEL_93;
  }
  return result;
}

```

## disassembly

```asm
0x180017740  mov     [rsp-8+arg_8], rbx
0x180017745  mov     [rsp-8+arg_10], rsi
0x18001774a  push    rbp
0x18001774b  push    rdi
0x18001774c  push    r12
0x18001774e  push    r13
0x180017750  push    r15
0x180017752  lea     rbp, [rsp-1F0h]
0x18001775a  sub     rsp, 2F0h
0x180017761  mov     rax, cs:__security_cookie
0x180017768  xor     rax, rsp
0x18001776b  mov     [rbp+210h+var_30], rax
0x180017772  mov     rax, [rbp+210h+arg_28]
0x180017779  xor     ebx, ebx
0x18001777b  mov     r13d, 7FFFFFFEh
0x180017781  mov     [rsp+310h+var_2A0], rax
0x180017786  mov     edi, 12Eh
0x18001778b  mov     [rsp+310h+var_2C0], 0
0x180017793  mov     r12, r9
0x180017796  mov     [rsp+310h+var_2D0], ebx
0x18001779a  mov     rsi, rdx
0x18001779d  lea     rax, [rbp+210h+SubKey]
0x1800177a1  mov     r15, r8
0x1800177a4  lea     r9, ?gszSchemesRootKey@@3PAGA; "AppEvents\\Schemes\\"
0x1800177ab  mov     ecx, r13d
0x1800177ae  mov     edx, edi
0x1800177b0  xor     r10d, r10d
0x1800177b3  test    rcx, rcx
0x1800177b6  jz      short loc_1800177DA
0x1800177b8  movzx   r8d, word ptr [r9]
0x1800177bc  test    r8w, r8w
0x1800177c0  jz      short loc_1800177DA
0x1800177c2  mov     [rax], r8w
0x1800177c6  add     r9, 2
0x1800177ca  add     rax, 2
0x1800177ce  dec     rcx
0x1800177d1  inc     r10
0x1800177d4  sub     rdx, 1
0x1800177d8  jnz     short loc_1800177B3
0x1800177da  test    rdx, rdx
0x1800177dd  lea     rcx, [rax-2]
0x1800177e1  lea     r11, [r10-1]
0x1800177e5  cmovnz  rcx, rax
0x1800177e9  cmovnz  r11, r10
0x1800177ed  xor     eax, eax
0x1800177ef  mov     [rcx], ax
0x1800177f2  test    rdx, rdx
0x1800177f5  jz      loc_180017CDB
0x1800177fb  mov     [rsp+310h+arg_0], r14
0x180017803  lea     r9, [rbp+210h+SubKey]
0x180017807  mov     r8, rdi
0x18001780a  lea     r9, [r9+r11*2]
0x18001780e  sub     r8, r11
0x180017811  add     r8, r8
0x180017814  mov     r14, r8
0x180017817  shr     r14, 1
0x18001781a  lea     rax, [r14-1]
0x18001781e  cmp     rax, r13
0x180017821  ja      loc_180017E3B
0x180017827  mov     rax, r13
0x18001782a  lea     rcx, ?gszSchemeAppsKey@@3PAGA; "Apps\\"
0x180017831  mov     r10, r14
0x180017834  mov     r11, r9
0x180017837  test    rax, rax
0x18001783a  jz      short loc_18001785C
0x18001783c  movzx   edx, word ptr [rcx]
0x18001783f  test    dx, dx
0x180017842  jz      short loc_18001785C
0x180017844  mov     [r9], dx
0x180017848  add     rcx, 2
0x18001784c  add     r9, 2
0x180017850  dec     rax
0x180017853  inc     rbx
0x180017856  sub     r10, 1
0x18001785a  jnz     short loc_180017837
0x18001785c  test    r10, r10
0x18001785f  lea     rdx, [rbx-1]
0x180017863  lea     rcx, [r9-2]
0x180017867  cmovnz  rdx, rbx
0x18001786b  xor     eax, eax
0x18001786d  test    r10, r10
0x180017870  mov     ebx, 8007007Ah
0x180017875  cmovnz  rcx, r9
0x180017879  cmovnz  ebx, eax
0x18001787c  sub     r14, rdx
0x18001787f  mov     [rcx], ax
0x180017882  lea     rax, [r11+rdx*2]
0x180017886  test    ebx, ebx
0x180017888  jns     loc_180017D06
0x18001788e  cmp     ebx, 8007007Ah
0x180017894  jz      loc_180017D06
0x18001789a  test    ebx, ebx
0x18001789c  jnz     loc_180017DD4
0x1800178a2  mov     r14, r8
0x1800178a5  shr     r14, 1
0x1800178a8  lea     rax, [r14-1]
0x1800178ac  cmp     rax, r13
0x1800178af  ja      loc_180017E29
0x1800178b5  mov     rax, r13
0x1800178b8  mov     r9, r14
0x1800178bb  xor     ebx, ebx
0x1800178bd  mov     r10, r11
0x1800178c0  test    rax, rax
0x1800178c3  jz      short loc_1800178E5
0x1800178c5  movzx   ecx, word ptr [rsi]
0x1800178c8  test    cx, cx
0x1800178cb  jz      short loc_1800178E5
0x1800178cd  mov     [r11], cx
0x1800178d1  add     rsi, 2
0x1800178d5  add     r11, 2
0x1800178d9  dec     rax
0x1800178dc  inc     rbx
0x1800178df  sub     r9, 1
0x1800178e3  jnz     short loc_1800178C0
0x1800178e5  test    r9, r9
0x1800178e8  lea     rdx, [rbx-1]
0x1800178ec  lea     rcx, [r11-2]
0x1800178f0  cmovnz  rdx, rbx
0x1800178f4  xor     eax, eax
0x1800178f6  test    r9, r9
0x1800178f9  mov     ebx, 8007007Ah
0x1800178fe  cmovnz  rcx, r11
0x180017902  cmovnz  ebx, eax
0x180017905  sub     r14, rdx
0x180017908  mov     [rcx], ax
0x18001790b  lea     rax, [r10+rdx*2]
0x18001790f  test    ebx, ebx
0x180017911  jns     loc_180017D12
0x180017917  cmp     ebx, 8007007Ah
0x18001791d  jz      loc_180017D12
0x180017923  test    ebx, ebx
0x180017925  jnz     loc_180017DD4
0x18001792b  mov     rsi, r8
0x18001792e  shr     rsi, 1
0x180017931  lea     rax, [rsi-1]
0x180017935  cmp     rax, r13
0x180017938  ja      loc_180017E17
0x18001793e  lea     r14, ?gszSlash@@3PAGA; "\\"
0x180017945  mov     rcx, r13
0x180017948  mov     rdx, r14
0x18001794b  mov     r9, rsi
0x18001794e  xor     r11d, r11d
0x180017951  mov     rbx, r10
0x180017954  test    rcx, rcx
0x180017957  jz      short loc_180017979
0x180017959  movzx   eax, word ptr [rdx]
0x18001795c  test    ax, ax
0x18001795f  jz      short loc_180017979
0x180017961  mov     [r10], ax
0x180017965  add     rdx, 2
0x180017969  add     r10, 2
0x18001796d  dec     rcx
0x180017970  inc     r11
0x180017973  sub     r9, 1
0x180017977  jnz     short loc_180017954
0x180017979  test    r9, r9
0x18001797c  lea     rdx, [r11-1]
0x180017980  lea     rcx, [r10-2]
0x180017984  cmovnz  rdx, r11
0x180017988  xor     eax, eax
0x18001798a  test    r9, r9
0x18001798d  mov     r11d, 8007007Ah
0x180017993  cmovnz  rcx, r10
0x180017997  cmovnz  r11d, eax
0x18001799b  sub     rsi, rdx
0x18001799e  mov     [rcx], ax
0x1800179a1  lea     rax, [rbx+rdx*2]
0x1800179a5  test    r11d, r11d
0x1800179a8  jns     loc_180017D96
0x1800179ae  cmp     r11d, 8007007Ah
0x1800179b5  jz      loc_180017D96
0x1800179bb  test    r11d, r11d
0x1800179be  jnz     loc_180017DD4
0x1800179c4  mov     rsi, r8
0x1800179c7  shr     rsi, 1
0x1800179ca  lea     rax, [rsi-1]
0x1800179ce  cmp     rax, r13
0x1800179d1  ja      loc_180017E06
0x1800179d7  mov     rcx, r13
0x1800179da  mov     r9, rsi
0x1800179dd  xor     r10d, r10d
0x1800179e0  mov     r11, rbx
0x1800179e3  test    rcx, rcx
0x1800179e6  jz      short loc_180017A08
0x1800179e8  movzx   eax, word ptr [r15]
0x1800179ec  test    ax, ax
0x1800179ef  jz      short loc_180017A08
0x1800179f1  mov     [rbx], ax
0x1800179f4  add     r15, 2
0x1800179f8  add     rbx, 2
0x1800179fc  dec     rcx
0x1800179ff  inc     r10
0x180017a02  sub     r9, 1
0x180017a06  jnz     short loc_1800179E3
0x180017a08  test    r9, r9
0x180017a0b  lea     rdx, [r10-1]
0x180017a0f  lea     rcx, [rbx-2]
0x180017a13  cmovnz  rdx, r10
0x180017a17  xor     r15d, r15d
0x180017a1a  test    r9, r9
0x180017a1d  mov     r10d, 8007007Ah
0x180017a23  cmovnz  rcx, rbx
0x180017a27  cmovnz  r10d, r15d
0x180017a2b  sub     rsi, rdx
0x180017a2e  lea     rax, [r11+rdx*2]
0x180017a32  mov     [rcx], r15w
0x180017a36  test    r10d, r10d
0x180017a39  jns     loc_180017DA2
0x180017a3f  cmp     r10d, 8007007Ah
0x180017a46  jz      loc_180017DA2
0x180017a4c  test    r10d, r10d
0x180017a4f  jnz     loc_180017DD4
0x180017a55  mov     rsi, r8
0x180017a58  shr     rsi, 1
0x180017a5b  lea     rax, [rsi-1]
0x180017a5f  cmp     rax, r13
0x180017a62  ja      loc_180017DF8
0x180017a68  mov     rcx, r13
0x180017a6b  mov     rdx, r14
0x180017a6e  mov     r10, rsi
0x180017a71  mov     rbx, r15
0x180017a74  mov     r9, r11
0x180017a77  test    rcx, rcx
0x180017a7a  jz      short loc_180017A9C
0x180017a7c  movzx   eax, word ptr [rdx]
0x180017a7f  test    ax, ax
0x180017a82  jz      short loc_180017A9C
0x180017a84  mov     [r11], ax
0x180017a88  add     rdx, 2
0x180017a8c  add     r11, 2
0x180017a90  dec     rcx
0x180017a93  inc     rbx
0x180017a96  sub     r10, 1
0x180017a9a  jnz     short loc_180017A77
0x180017a9c  test    r10, r10
0x180017a9f  lea     rdx, [rbx-1]
0x180017aa3  lea     rcx, [r11-2]
0x180017aa7  cmovnz  rdx, rbx
0x180017aab  cmovnz  rcx, r11
0x180017aaf  mov     ebx, 8007007Ah
0x180017ab4  cmovnz  ebx, r15d
0x180017ab8  sub     rsi, rdx
0x180017abb  mov     [rcx], r15w
0x180017abf  lea     rax, [r9+rdx*2]
0x180017ac3  test    ebx, ebx
0x180017ac5  jns     loc_180017DB2
0x180017acb  cmp     ebx, 8007007Ah
0x180017ad1  jz      loc_180017DB2
0x180017ad7  test    ebx, ebx
0x180017ad9  jnz     loc_180017DD4
0x180017adf  shr     r8, 1
0x180017ae2  lea     rax, [r8-1]
0x180017ae6  cmp     rax, r13
0x180017ae9  ja      loc_180017DEA
0x180017aef  mov     rax, r13
0x180017af2  lea     rdx, ?aszCurrent@@3PAGA; ".Current"
0x180017af9  nop     dword ptr [rax+00000000h]
0x180017b00  test    rax, rax
0x180017b03  jz      short loc_180017B22
0x180017b05  movzx   ecx, word ptr [rdx]
0x180017b08  test    cx, cx
0x180017b0b  jz      short loc_180017B22
0x180017b0d  mov     [r9], cx
0x180017b11  add     rdx, 2
0x180017b15  add     r9, 2
0x180017b19  dec     rax
0x180017b1c  sub     r8, 1
0x180017b20  jnz     short loc_180017B00
0x180017b22  test    r8, r8
0x180017b25  lea     rcx, [r9-2]
0x180017b29  cmovnz  rcx, r9
0x180017b2d  mov     [rcx], r15w
0x180017b31  jz      loc_180017DD4
0x180017b37  lea     rdx, [rsp+310h+phkResult]; phkResult
0x180017b3c  mov     [rsp+310h+phkResult], r15
0x180017b41  mov     ecx, 1; samDesired
0x180017b46  mov     [r12], r15w
0x180017b4b  call    cs:__imp_RegOpenCurrentUser
0x180017b51  test    eax, eax
0x180017b53  jnz     loc_180017DD4
0x180017b59  mov     eax, [rbp+210h+arg_20]
0x180017b5f  lea     rdx, [rbp+210h+SubKey]; lpSubKey
0x180017b63  mov     rcx, [rsp+310h+phkResult]; hkey
0x180017b68  mov     r9d, 2; dwFlags
0x180017b6e  mov     [rsp+310h+var_2C8], eax
0x180017b72  xor     r8d, r8d; lpValue
0x180017b75  lea     rax, [rsp+310h+var_2C8]
0x180017b7a  mov     [r12], r15w
0x180017b7f  mov     [rsp+310h+pcbData], rax; pcbData
0x180017b84  mov     [rsp+310h+pvData], r12; pvData
0x180017b89  mov     [rsp+310h+pdwType], r15; pdwType
0x180017b8e  call    cs:__imp_RegGetValueW
0x180017b94  mov     rcx, [rsp+310h+phkResult]; hKey
0x180017b99  mov     ebx, eax
0x180017b9b  call    cs:__imp_RegCloseKey
0x180017ba1  test    ebx, ebx
0x180017ba3  jnz     loc_180017DD4
0x180017ba9  lea     rax, [rsp+310h+var_2B0]
0x180017bae  mov     [rsp+310h+var_2B0], 4
0x180017bb6  mov     [rsp+310h+pcbData], rax; pcbData
  ... truncated ...
```
