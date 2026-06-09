# pax_attribute

- ea: `0x1800e0eec`
- end: `0x1800e1f9f`
- name: `pax_attribute`
- size: `4275`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800e05a4`

## callees

- `0x180005914`
- `0x180005c7c`
- `0x180006c00`
- `0x180007bd8`
- `0x18000e920`
- `0x18000e9a0`
- `0x18000ea00`
- `0x1800148e0`
- `0x1800aba54`
- `0x1800aba60`
- `0x1800b15a0`
- `0x1800b2140`
- `0x1800b3930`
- `0x1800df5fc`
- `0x1800e0eec`
- `0x1800e1fa8`
- `0x1800e2054`
- `0x1800e21e0`
- `0x1800e22c0`
- `0x1800e23c8`
- `0x1800e2670`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e1407`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e1407`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800e13d0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800e13d0`

## string_xrefs

- `0x1800e15c0`: `security.selinux`
- `0x1800e1b2c`: `Truncated archive detected while reading GNU sparse data`
- `0x1800e1703`: `Truncated tar archive detected while reading `symlinktype` attribute`
- `0x1800e175c`: `Unrecognized symlink type`
- `0x1800e1773`: `symlink type is very long(longest recognized value is 4 bytes, this is %llu)`
- `0x1800e17e8`: `Truncated archive detected while reading xattr information`
- `0x1800e1586`: `Ignoring unreasonably large security.selinux attribute: %llu > %llu`
- `0x1800e15b1`: `Truncated archive detected while reading selinux data`
- `0x1800e1249`: `Truncated archive detected while reading SCHILY.fflags`
- `0x1800e13b6`: `Truncated archive detected while reading SCHILY.xattr`
- `0x1800e14c4`: `Truncated archive detected while reading SUN.holesdata`
- `0x1800e1f19`: `Truncated tar archive detected while reading hdrcharset attribute`

## pseudocode

```c
__int64 __fastcall pax_attribute(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char *a4,
        unsigned __int64 a5,
        unsigned __int64 a6,
        _QWORD *a7)
{
  int v8; // ecx
  unsigned __int16 *v9; // rbx
  __int64 v11; // r14
  int v12; // edi
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  unsigned int time; // ebx
  int v20; // ecx
  unsigned __int64 v21; // rdi
  int v22; // ecx
  __int64 v23; // rcx
  __int64 result; // rax
  __int64 v25; // rcx
  int v26; // ecx
  __int64 v27; // rax
  __int64 v28; // rcx
  int v29; // ecx
  unsigned __int64 v30; // r14
  _QWORD *v31; // rbx
  __int64 v32; // rax
  const char *v33; // r8
  unsigned __int64 v34; // rdx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  unsigned __int64 v40; // r14
  _QWORD *v41; // r12
  __int64 v42; // r13
  char *v43; // rax
  char *v44; // rsi
  int v45; // ecx
  __int64 v46; // rcx
  __int64 v47; // rbx
  _QWORD *v48; // r15
  __int64 v49; // rax
  int v50; // r8d
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  unsigned __int64 v54; // rbx
  _QWORD *v55; // r14
  __int64 v56; // rax
  __int64 v57; // rcx
  unsigned __int64 v58; // r13
  __int64 v59; // rcx
  __int64 v60; // rcx
  unsigned __int16 *v61; // rax
  __int64 v62; // rdx
  int v63; // ecx
  int v64; // ecx
  __int64 v65; // r12
  __int64 v66; // rax
  unsigned __int64 v67; // rdx
  int v68; // ecx
  int v69; // ecx
  __int64 v70; // rcx
  int v71; // ecx
  __int64 v72; // r9
  bool v73; // zf
  __int64 v74; // rax
  __int64 v75; // r8
  __int64 v76; // rcx
  int v77; // eax
  __int64 v78; // rcx
  unsigned __int64 v79; // r8
  int v80; // edx
  unsigned __int64 v81; // r15
  __int64 v82; // rax
  int v83; // ecx
  int v84; // ecx
  int v85; // ecx
  __int64 v86; // rcx
  __int64 v87; // rdx
  bool v88; // sf
  int v89; // ecx
  int v90; // ecx
  int v91; // ecx
  int v92; // ecx
  int v93; // ecx
  int v94; // ecx
  int v95; // ecx
  __int64 v96; // rcx
  __int64 v97; // rdx
  int v98; // ecx
  int v99; // ecx
  __int64 v100; // rcx
  unsigned __int16 *v101; // rax
  int v102; // ecx
  _QWORD v103[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v104; // [rsp+A8h] [rbp+60h] BYREF

  v8 = *a4;
  v9 = (unsigned __int16 *)a4;
  v103[0] = 0;
  v104 = 0;
  v11 = a2;
  if ( v8 > 103 )
  {
    v90 = v8 - 104;
    if ( v90 )
    {
      v91 = v90 - 4;
      if ( v91 )
      {
        v92 = v91 - 1;
        if ( !v92 )
        {
          if ( a5 == 5 )
          {
            v99 = *(_DWORD *)a4 - 1835627629;
            if ( *(_DWORD *)a4 == 1835627629 )
              v99 = (unsigned __int8)a4[4] - 101;
            if ( !v99 )
            {
              time = pax_attribute_read_time(a1, a6, (unsigned int)v103, (unsigned int)&v104, (__int64)a7);
              if ( !time )
                archive_entry_set_mtime(a3, v103[0], v104);
              return time;
            }
          }
          goto LABEL_172;
        }
        v93 = v92 - 3;
        if ( v93 )
        {
          v94 = v93 - 3;
          if ( !v94 )
          {
            if ( a5 != 4 || *(_DWORD *)a4 != 1702521203 )
              goto LABEL_172;
            result = pax_attribute_read_number(a1, a6, v103);
            if ( !(_DWORD)result )
            {
              *(_QWORD *)(v11 + 216) = v103[0];
              *(_BYTE *)(v11 + 266) |= 1u;
              return result;
            }
            if ( v103[0] == 0x7FFFFFFFFFFFFFFFLL )
            {
              *(_QWORD *)(v11 + 152) = 0;
              v33 = "Tar size attribute overflow";
              v62 = 0xFFFFFFFFLL;
              goto LABEL_140;
            }
            return result;
          }
          if ( v94 != 2 )
            goto LABEL_172;
          if ( a5 == 3 )
          {
            v95 = *(unsigned __int16 *)a4 - 26997;
            if ( *(_WORD *)a4 == 26997 )
              v95 = (unsigned __int8)a4[2] - 100;
            if ( v95 )
              goto LABEL_172;
            result = pax_attribute_read_number(a1, a6, v103);
            if ( !(_DWORD)result )
            {
              v96 = v103[0];
              v97 = 0;
              v88 = v103[0] < 0;
              *(_DWORD *)(a3 + 16) = 0;
              if ( !v88 )
                v97 = v96;
              *(_DWORD *)(a3 + 160) |= 0x800u;
              *(_QWORD *)(a3 + 120) = v97;
            }
            return result;
          }
          if ( a5 != 5 )
            goto LABEL_172;
          v98 = *(_DWORD *)a4 - 1835101813;
          if ( *(_DWORD *)a4 == 1835101813 )
            v98 = (unsigned __int8)a4[4] - 101;
          if ( v98 )
            goto LABEL_172;
          v79 = a6;
          if ( a6 <= 0x10000 )
          {
            a2 += 48;
            return (unsigned int)read_bytes_to_string(a1, a2, v79, a7);
          }
        }
        else
        {
          if ( a5 != 4 || *(_DWORD *)a4 != 1752457584 )
            goto LABEL_172;
          v79 = a6;
          if ( a6 <= 0x100000 )
            return (unsigned int)read_bytes_to_string(a1, a2, v79, a7);
        }
      }
      else
      {
        if ( a5 != 8 || *(_QWORD *)a4 != 0x687461706B6E696CLL )
          goto LABEL_172;
        v79 = a6;
        if ( a6 <= 0x100000 )
        {
          a2 += 96;
          return (unsigned int)read_bytes_to_string(a1, a2, v79, a7);
        }
      }
      goto LABEL_208;
    }
    if ( a5 != 10 )
      goto LABEL_172;
    v100 = *(_QWORD *)a4 - 0x7372616863726468LL;
    if ( *(_QWORD *)a4 == 0x7372616863726468LL )
      v100 = *((unsigned __int16 *)a4 + 4) - 29797LL;
    if ( v100 )
      goto LABEL_172;
    v47 = a6;
    v48 = (_QWORD *)(a1 + 632);
    if ( a6 >= 0x40 )
    {
      archive_set_error(a1, 42, "hdrcharset attribute is unreasonably large (%llu bytes)", a6);
    }
    else
    {
      v101 = (unsigned __int16 *)_archive_read_filter_ahead(*v48, a6, &v104);
      if ( !v101 )
      {
        v33 = "Truncated tar archive detected while reading hdrcharset attribute";
        goto LABEL_139;
      }
      if ( v47 == 6 )
      {
        v102 = *(_DWORD *)v101 - 1095649602;
        if ( *(_DWORD *)v101 == 1095649602 )
          v102 = v101[2] - 22866;
        if ( !v102 )
        {
          *(_DWORD *)(v11 + 144) = 0;
LABEL_309:
          v12 = 0;
LABEL_109:
          v52 = *v48;
          v34 = v47;
LABEL_225:
          _archive_read_filter_consume(v52, v34);
          return (unsigned int)v12;
        }
      }
      else if ( v47 == 23 && !memcmp_0(v101, "ISO-IR 10646 2000 UTF-8", 0x17u) )
      {
        *(_DWORD *)(v11 + 144) = 1;
        goto LABEL_309;
      }
    }
    v12 = -20;
    goto LABEL_109;
  }
  if ( v8 == 103 )
  {
    if ( a5 == 3 )
    {
      v85 = *(unsigned __int16 *)a4 - 26983;
      if ( *(_WORD *)a4 == 26983 )
        v85 = (unsigned __int8)a4[2] - 100;
      if ( v85 )
        goto LABEL_172;
      result = pax_attribute_read_number(a1, a6, v103);
      if ( !(_DWORD)result )
      {
        v86 = v103[0];
        v87 = 0;
        v88 = v103[0] < 0;
        *(_DWORD *)(a3 + 16) = 0;
        if ( !v88 )
          v87 = v86;
        *(_DWORD *)(a3 + 160) |= 0x1000u;
        *(_QWORD *)(a3 + 88) = v87;
      }
      return result;
    }
    if ( a5 != 5 )
      goto LABEL_172;
    v89 = *(_DWORD *)a4 - 1835101799;
    if ( *(_DWORD *)a4 == 1835101799 )
      v89 = (unsigned __int8)a4[4] - 101;
    if ( v89 )
      goto LABEL_172;
    v79 = a6;
    if ( a6 <= 0x10000 )
    {
      a2 += 72;
      return (unsigned int)read_bytes_to_string(a1, a2, v79, a7);
    }
LABEL_208:
    v12 = -20;
    *a7 += v79;
    return (unsigned int)v12;
  }
  v12 = 0;
  v13 = v8 - 71;
  if ( !v13 )
  {
    if ( a5 <= 4 || *(_DWORD *)a4 != 777342535 )
      goto LABEL_172;
    v67 = a5 - 4;
    if ( a5 == 10 )
    {
      v68 = *((_DWORD *)a4 + 1) - 1918988403;
      if ( *((_DWORD *)a4 + 1) == 1918988403 )
        v68 = *((unsigned __int16 *)a4 + 4) - 25971;
      if ( !v68 )
        *(_BYTE *)(v11 + 264) = 1;
      goto LABEL_172;
    }
    if ( v67 <= 7 )
      goto LABEL_172;
    v69 = *((_DWORD *)a4 + 1) - 1918988403;
    if ( *((_DWORD *)a4 + 1) == 1918988403 )
    {
      v69 = *((unsigned __int16 *)a4 + 4) - 25971;
      if ( *((_WORD *)a4 + 4) == 25971 )
        v69 = (unsigned __int8)a4[10] - 46;
    }
    if ( v69 )
      goto LABEL_172;
    *(_BYTE *)(v11 + 264) = 1;
    switch ( v67 )
    {
      case 0x10uLL:
        v70 = *(_QWORD *)(a4 + 11) - 0x6B636F6C626D756ELL;
        if ( *(_QWORD *)(a4 + 11) == 0x6B636F6C626D756ELL )
          v70 = (unsigned __int8)a4[19] - 115LL;
        if ( !v70 )
        {
          *(_QWORD *)(v11 + 240) = -1;
          *(_QWORD *)(v11 + 248) = -1;
          *(_QWORD *)(v11 + 256) = 0;
        }
        goto LABEL_172;
      case 0xDuLL:
        v71 = *(_DWORD *)(a4 + 11) - 1936090735;
        if ( *(_DWORD *)(a4 + 11) == 1936090735 )
          v71 = *(unsigned __int16 *)(a4 + 15) - 29797;
        if ( v71 )
          goto LABEL_172;
        time = pax_attribute_read_number(a1, a6, v103);
        if ( time )
          return time;
        v72 = *(_QWORD *)(v11 + 248);
        *(_QWORD *)(v11 + 240) = v103[0];
        v73 = v72 == -1;
        goto LABEL_196;
      case 0xFuLL:
        v74 = *(_QWORD *)(a4 + 11);
        if ( v74 != 0x73657479626D756ELL )
        {
          if ( v74 != 0x657A69736C616572LL )
            goto LABEL_172;
          result = pax_attribute_read_number(a1, a6, v103);
          if ( !(_DWORD)result )
          {
            v76 = v103[0];
            *(_BYTE *)(v11 + 266) |= 2u;
            *(_QWORD *)(v11 + 192) = v76;
          }
          return result;
        }
        time = pax_attribute_read_number(a1, a6, v103);
        if ( time )
          return time;
        v75 = *(_QWORD *)(v11 + 240);
        *(_QWORD *)(v11 + 248) = v103[0];
        v73 = v75 == -1;
LABEL_196:
        if ( !v73 )
        {
          if ( (unsigned int)gnu_add_sparse_entry(a1, v11) )
            return 4294967266LL;
          *(_QWORD *)(v11 + 240) = -1;
          *(_QWORD *)(v11 + 248) = -1;
        }
        return time;
    }
    if ( v67 != 11 )
    {
      if ( v67 != 10 )
      {
        if ( v67 != 12 )
          goto LABEL_172;
        v83 = *(_DWORD *)(a4 + 11) - 1869242733;
        if ( *(_DWORD *)(a4 + 11) == 1869242733 )
          v83 = (unsigned __int8)a4[15] - 114;
        if ( v83 )
        {
          v84 = *(_DWORD *)(a4 + 11) - 1869506925;
          if ( *(_DWORD *)(a4 + 11) == 1869506925 )
            v84 = (unsigned __int8)a4[15] - 114;
          if ( v84 )
            goto LABEL_172;
          result = pax_attribute_read_number(a1, a6, v103);
          if ( !(_DWORD)result && v103[0] <= 0xAu )
            *(_DWORD *)(v11 + 260) = v103[0];
        }
        else
        {
          result = pax_attribute_read_number(a1, a6, v103);
          if ( !(_DWORD)result && v103[0] <= 0xAu )
            *(_DWORD *)(v11 + 256) = v103[0];
        }
        return result;
      }
      v80 = *(unsigned __int16 *)(a4 + 11) - 24941;
      if ( *(_WORD *)(a4 + 11) == 24941 )
        v80 = (unsigned __int8)a4[13] - 112;
      if ( v80 )
        goto LABEL_172;
      v81 = a6;
      v31 = (_QWORD *)(a1 + 632);
      *(_DWORD *)(v11 + 256) = 0;
      *(_DWORD *)(v11 + 260) = 1;
      if ( v81 <= 0x800000 )
      {
        v82 = _archive_read_filter_ahead(*v31, v81, &v104);
        v51 = a1;
        if ( !v82 )
        {
          v33 = "Truncated archive detected while reading GNU sparse data";
          goto LABEL_219;
        }
        if ( (unsigned int)gnu_sparse_01_parse(a1, v11, v82, v81) )
          v12 = -20;
      }
      else
      {
        archive_set_error(a1, 0xFFFFFFFFLL, "Unreasonably large sparse map: %llu > %llu", v81, 0x800000);
        v12 = -25;
      }
      v34 = v81;
LABEL_224:
      v52 = *v31;
      goto LABEL_225;
    }
    v77 = *(_DWORD *)(a4 + 11);
    if ( v77 == 1702521203 )
    {
      result = pax_attribute_read_number(a1, a6, v103);
      if ( !(_DWORD)result )
      {
        v78 = v103[0];
        *(_BYTE *)(v11 + 266) |= 4u;
        *(_QWORD *)(v11 + 200) = v78;
      }
      return result;
    }
    if ( v77 != 1701667182 )
      goto LABEL_172;
    v79 = a6;
    if ( a6 > 0x100000 )
      goto LABEL_208;
    a2 = v11 + 24;
    return (unsigned int)read_bytes_to_string(a1, a2, v79, a7);
  }
  v14 = v13 - 5;
  if ( !v14 )
  {
    if ( a5 <= 0xB )
      goto LABEL_172;
    v57 = *(_QWORD *)a4 - 0x494843524142494CLL;
    if ( *(_QWORD *)a4 == 0x494843524142494CLL )
    {
      v57 = *((unsigned __int16 *)a4 + 4) - 17750LL;
      if ( *((_WORD *)a4 + 4) == 17750 )
        v57 = (unsigned __int8)a4[10] - 46LL;
    }
    if ( v57 )
      goto LABEL_172;
    v58 = a5 - 11;
    if ( a5 == 23 )
    {
      v59 = *(_QWORD *)(a4 + 11) - 0x6E6F697461657263LL;
      if ( *(_QWORD *)(a4 + 11) == 0x6E6F697461657263LL )
        v59 = *(unsigned int *)(a4 + 19) - 1701669236LL;
      if ( !v59 )
      {
        time = pax_attribute_read_time(a1, a6, (unsigned int)v103, (unsigned int)&v104, (__int64)a7);
        if ( !time )
          archive_entry_set_birthtime(a3, v103[0], v104);
        return time;
      }
      goto LABEL_155;
    }
    if ( a5 != 22 )
    {
      if ( v58 <= 6 )
        goto LABEL_172;
      goto LABEL_155;
    }
    v60 = *(_QWORD *)(a4 + 11) - 0x746B6E696C6D7973LL;
    if ( *(_QWORD *)(a4 + 11) == 0x746B6E696C6D7973LL )
    {
      v60 = *(unsigned __int16 *)(a4 + 19) - 28793LL;
      if ( *(_WORD *)(a4 + 19) == 28793 )
        v60 = (unsigned __int8)a4[21] - 101LL;
    }
    if ( v60 )
    {
LABEL_155:
      v64 = *(_DWORD *)(a4 + 11) - 1953784184;
      if ( *(_DWORD *)(a4 + 11) == 1953784184 )
        v64 = *(unsigned __int16 *)(a4 + 15) - 11890;
      if ( v64 )
        goto LABEL_172;
      v65 = a6;
      v55 = (_QWORD *)(a1 + 632);
      if ( a6 > 0x1000000 )
        goto LABEL_163;
      v66 = _archive_read_filter_ahead(*v55, a6, &v104);
      if ( !v66 )
      {
        v33 = "Truncated archive detected while reading xattr information";
        goto LABEL_161;
      }
      if ( (unsigned int)pax_attribute_LIBARCHIVE_xattr(a3, (int)v9 + 17, (int)v58 - 6, v66, v65) )
LABEL_163:
        v12 = -20;
      v34 = v65;
LABEL_153:
      v52 = *v55;
      goto LABEL_225;
    }
    v54 = a6;
    v55 = (_QWORD *)(a1 + 632);
    if ( a6 >= 0x10 )
    {
      archive_set_error(
        a1,
        0xFFFFFFFFLL,
        "symlink type is very long(longest recognized value is 4 bytes, this is %llu)",
        a6);
    }
    else
    {
      v61 = (unsigned __int16 *)_archive_read_filter_ahead(*v55, a6, &v104);
      if ( !v61 )
      {
        v33 = "Truncated tar archive detected while reading `symlinktype` attribute";
LABEL_139:
        v62 = 42;
LABEL_140:
        v51 = a1;
LABEL_220:
        archive_set_error(v51, v62, v33);
        return 4294967266LL;
      }
      if ( v54 == 4 )
      {
        if ( *(_DWORD *)v61 == 1701603686 )
        {
          *(_DWORD *)(a3 + 1140) = 1;
LABEL_152:
          v34 = v54;
          goto LABEL_153;
        }
      }
      else if ( v54 == 3 )
      {
        v63 = *v61 - 26980;
        if ( *v61 == 26980 )
          v63 = *((unsigned __int8 *)v61 + 2) - 114;
        if ( !v63 )
        {
          *(_DWORD *)(a3 + 1140) = 2;
          goto LABEL_152;
        }
      }
      archive_set_error(a1, 0xFFFFFFFFLL, "Unrecognized symlink type");
    }
LABEL_151:
    v12 = -20;
    goto LABEL_152;
  }
  v15 = v14 - 6;
  if ( !v15 )
  {
    if ( a5 != 20 )
      goto LABEL_172;
    v53 = *(_QWORD *)a4 - 0x756365732E544852LL;
    if ( *(_QWORD *)a4 == 0x756365732E544852LL )
    {
      v53 = *((_QWORD *)a4 + 1) - 0x6C65732E79746972LL;
      if ( *((_QWORD *)a4 + 1) == 0x6C65732E79746972LL )
        v53 = *((unsigned int *)a4 + 4) - 2020961897LL;
    }
    if ( v53 )
      goto LABEL_172;
    v54 = a6;
    v55 = (_QWORD *)(a1 + 632);
    if ( a6 <= 0x1000000 )
    {
      v56 = _archive_read_filter_ahead(*v55, a6, &v104);
      if ( !v56 )
      {
        v33 = "Truncated archive detected while reading selinux data";
        goto LABEL_161;
      }
      archive_entry_xattr_add_entry(a3, "security.selinux", v56, v54);
      goto LABEL_152;
    }
    archive_set_error(
      a1,
      0xFFFFFFFFLL,
      "Ignoring unreasonably large security.selinux attribute: %llu > %llu",
      a6,
      0x1000000);
    goto LABEL_151;
  }
  v16 = v15 - 1;
  if ( v16 )
  {
    v17 = v16 - 14;
    if ( v17 )
    {
      if ( v17 == 2 && a5 == 5 )
      {
        v18 = *(_DWORD *)a4 - 1835627619;
        if ( *(_DWORD *)a4 == 1835627619 )
          v18 = (unsigned __int8)a4[4] - 101;
        if ( !v18 )
        {
          time = pax_attribute_read_time(a1, a6, (unsigned int)v103, (unsigned int)&v104, (__int64)a7);
          if ( !time )
            archive_entry_set_ctime(a3, v103[0], v104);
          return time;
        }
      }
    }
    else if ( a5 == 5 )
    {
      v20 = *(_DWORD *)a4 - 1835627617;
      if ( *(_DWORD *)a4 == 1835627617 )
        v20 = (unsigned __int8)a4[4] - 101;
      if ( !v20 )
      {
        time = pax_attribute_read_time(a1, a6, (unsigned int)v103, (unsigned int)&v104, (__int64)a7);
        if ( !time )
          archive_entry_set_atime(a3, v103[0], v104);
        return time;
      }
    }
    goto LABEL_172;
  }
  v21 = a5;
  if ( a5 <= 7 )
    goto LABEL_97;
  v22 = *(_DWORD *)a4 - 1229472595;
  if ( *(_DWORD *)a4 == 1229472595 )
  {
    v22 = *((unsigned __int16 *)a4 + 2) - 22860;
    if ( *((_WORD *)a4 + 2) == 22860 )
      v22 = (unsigned __int8)a4[6] - 46;
  }
  if ( v22 )
    goto LABEL_98;
  v21 = a5 - 7;
  v9 = (unsigned __int16 *)(a4 + 7);
  switch ( a5 )
  {
    case 0x11uLL:
      v23 = *(_QWORD *)v9 - 0x656363612E6C6361LL;
      if ( *(_QWORD *)v9 == 0x656363612E6C6361LL )
        v23 = *(unsigned __int16 *)(a4 + 15) - 29555LL;
      if ( !v23 )
        return pax_attribute_SCHILY_acl(a1, a2, a3, a6, 256);
LABEL_83:
      v39 = *(_DWORD *)v9 - 1953784184;
      if ( *(_DWORD *)v9 == 1953784184 )
        v39 = *(unsigned __int16 *)(a4 + 11) - 11890;
      if ( !v39 )
      {
        v40 = a6;
        v41 = (_QWORD *)(a1 + 632);
        if ( a6 >= 0x1000000 )
        {
          archive_set_error(a1, 0xFFFFFFFFLL, "Unreasonably large xattr: %llu > %llu", a6, 0x1000000);
          time = -20;
        }
        else
        {
          v42 = _archive_read_filter_ahead(*v41, a6, &v104);
          if ( !v42 )
          {
            v33 = "Truncated archive detected while reading SCHILY.xattr";
            goto LABEL_161;
          }
          if ( v21 - 7 > 0x7F )
          {
            v45 = 1;
          }
          else
          {
            v43 = (char *)malloc(v21 - 5);
            v44 = v43;
            if ( v43 )
            {
              memcpy_0(v43, v9 + 3, v21 - 6);
              v44[v21 - 6] = 0;
              archive_entry_xattr_add_entry(a3, v44, v42, v40);
              free(v44);
            }
            v45 = 0;
          }
          time = v45 != 0 ? 0xFFFFFFEC : 0;
        }
        _archive_read_filter_consume(*v41, v40);
        return time;
      }
LABEL_97:
      if ( v21 <= 4 )
        goto LABEL_172;
      goto LABEL_98;
    case 0x12uLL:
      v25 = *(_QWORD *)v9 - 0x616665642E6C6361LL;
      if ( *(_QWORD *)v9 == 0x616665642E6C6361LL )
      {
        v25 = *(unsigned __int16 *)(a4 + 15) - 27765LL;
        if ( *(_WORD *)(a4 + 15) == 27765 )
          v25 = (unsigned __int8)a4[17] - 116LL;
      }
      if ( !v25 )
        return pax_attribute_SCHILY_acl(a1, a2, a3, a6, 512);
      goto LABEL_83;
    case 0xEuLL:
      v26 = *(_DWORD *)v9 - 778855265;
      if ( *(_DWORD *)v9 == 778855265 )
      {
        v26 = *(unsigned __int16 *)(a4 + 11) - 25441;
        if ( *(_WORD *)(a4 + 11) == 25441 )
          v26 = (unsigned __int8)a4[13] - 101;
      }
      if ( !v26 )
        return pax_attribute_SCHILY_acl(a1, a2, a3, a6, 15360);
      goto LABEL_83;
  }
  if ( a5 != 15 )
  {
    switch ( a5 )
    {
      case 0xDuLL:
        v29 = *(_DWORD *)v9 - 1634494054;
        if ( *(_DWORD *)v9 == 1634494054 )
          v29 = *(unsigned __int16 *)(a4 + 11) - 29543;
        if ( !v29 )
        {
          v30 = a6;
          v31 = (_QWORD *)(a1 + 632);
          if ( a6 >= 0x200 )
          {
            v12 = -20;
          }
          else
          {
            v32 = _archive_read_filter_ahead(*v31, a6, &v104);
            if ( !v32 )
            {
              v33 = "Truncated archive detected while reading SCHILY.fflags";
LABEL_161:
              v62 = 22;
              goto LABEL_140;
            }
            archive_entry_copy_fflags_text_len(a3, v32, v30);
            v12 = 0;
          }
          v34 = v30;
          goto LABEL_224;
        }
        break;
      case 0xAuLL:
        v35 = *v9 - 25956;
        if ( *v9 == 25956 )
          v35 = (unsigned __int8)a4[9] - 118;
        if ( v35 )
        {
          v37 = *v9 - 28265;
          if ( *v9 == 28265 )
            v37 = (unsigned __int8)a4[9] - 111;
          if ( !v37 )
          {
            time = pax_attribute_read_number(a1, a6, v103);
            if ( !time )
              archive_entry_set_ino64(a3, v103[0]);
            return time;
          }
          goto LABEL_172;
        }
        result = pax_attribute_read_number(a1, a6, v103);
        if ( !(_DWORD)result )
        {
          v36 = v103[0];
          *(_DWORD *)(a3 + 160) |= 0x100u;
          *(_DWORD *)(a3 + 132) = v36;
          *(_DWORD *)(a3 + 16) = 0;
          *(_DWORD *)(a3 + 128) = 0;
        }
        return result;
      case 0xCuLL:
        v38 = *(_DWORD *)v9 - 1852402798;
        if ( *(_DWORD *)v9 == 1852402798 )
          v38 = (unsigned __int8)a4[11] - 107;
        if ( !v38 )
        {
          result = pax_attribute_read_number(a1, a6, v103);
          if ( !(_DWORD)result )
          {
            *(_DWORD *)(a3 + 104) = v103[0];
            *(_DWORD *)(a3 + 16) = 0;
          }
          return result;
        }
        break;
      default:
        if ( v21 <= 6 )
          goto LABEL_97;
        goto LABEL_83;
    }
LABEL_98:
    if ( *(_DWORD *)v9 == 776885587 && v21 == 13 )
    {
      v46 = *(_QWORD *)(v9 + 2) - 0x74616473656C6F68LL;
      if ( *(_QWORD *)(v9 + 2) == 0x74616473656C6F68LL )
        v46 = *((unsigned __int8 *)v9 + 12) - 97LL;
      if ( !v46 )
      {
        v47 = a6;
        v48 = (_QWORD *)(a1 + 632);
        if ( a6 >= 0x800000 )
        {
          archive_set_error(a1, 0xFFFFFFFFLL, "Unreasonably large sparse map: %llu > %llu", a6, 0x800000);
          v12 = -25;
        }
        else
        {
          v49 = _archive_read_filter_ahead(*v48, a6, &v104);
          v51 = a1;
          if ( !v49 )
          {
            v33 = "Truncated archive detected while reading SUN.holesdata";
LABEL_219:
            v62 = 22;
            goto LABEL_220;
          }
          v12 = pax_attribute_SUN_holesdata(a1, v11, v50, v49, v47);
          if ( v12 < 0 )
            archive_set_error(a1, 0xFFFFFFFFLL, "Parse error: SUN.holesdata");
        }
        goto LABEL_109;
      }
    }
LABEL_172:
    _archive_read_filter_consume(*(_QWORD *)(a1 + 632), a6);
    return 0;
  }
  v27 = *(_QWORD *)v9;
  if ( *(_QWORD *)v9 == 0x726F6A616D766564LL )
  {
    result = pax_attribute_read_number(a1, a6, v103);
    if ( (_DWORD)result )
      return result;
    *(_DWORD *)(a3 + 152) = v103[0];
    goto LABEL_48;
  }
  if ( v27 == 0x726F6E696D766564LL )
  {
    result = pax_attribute_read_number(a1, a6, v103);
    if ( (_DWORD)result )
      return result;
    *(_DWORD *)(a3 + 156) = v103[0];
LABEL_48:
    *(_DWORD *)(a3 + 160) |= 0x2000u;
    *(_QWORD *)(a3 + 144) = 1;
    *(_DWORD *)(a3 + 16) = 0;
    return result;
  }
  if ( v27 != 0x657A69736C616572LL )
    goto LABEL_83;
  result = pax_attribute_read_number(a1, a6, v103);
  if ( !(_DWORD)result )
  {
    v28 = v103[0];
    *(_BYTE *)(v11 + 266) |= 8u;
    *(_QWORD *)(v11 + 208) = v28;
  }
  return result;
}

```

## disassembly

```asm
0x1800e0eec  push    rbp
0x1800e0eee  push    rbx
0x1800e0eef  push    rsi
0x1800e0ef0  push    rdi
0x1800e0ef1  push    r12
0x1800e0ef3  push    r13
0x1800e0ef5  push    r14
0x1800e0ef7  push    r15
0x1800e0ef9  mov     rbp, rsp
0x1800e0efc  sub     rsp, 48h
0x1800e0f00  xor     r12d, r12d
0x1800e0f03  mov     rsi, rcx
0x1800e0f06  movsx   ecx, byte ptr [r9]
0x1800e0f0a  mov     rbx, r9
0x1800e0f0d  mov     [rbp+var_18], r12
0x1800e0f11  mov     r15, r8
0x1800e0f14  mov     [rbp+arg_18], r12d
0x1800e0f18  mov     r14, rdx
0x1800e0f1b  cmp     ecx, 67h ; 'g'
0x1800e0f1e  jg      loc_1800E1CB0
0x1800e0f24  jz      loc_1800E1C10
0x1800e0f2a  mov     edi, r12d
0x1800e0f2d  sub     ecx, 47h ; 'G'
0x1800e0f30  jz      loc_1800E1822
0x1800e0f36  sub     ecx, 5
0x1800e0f39  jz      loc_1800E15D7
0x1800e0f3f  sub     ecx, 6
0x1800e0f42  jz      loc_1800E1524
0x1800e0f48  sub     ecx, 1
0x1800e0f4b  jz      loc_1800E1023
0x1800e0f51  sub     ecx, 0Eh
0x1800e0f54  jz      short loc_1800E0FC1
0x1800e0f56  cmp     ecx, 2
0x1800e0f59  jnz     loc_1800E1863
0x1800e0f5f  cmp     [rbp+arg_20], 5
0x1800e0f64  jnz     loc_1800E1863
0x1800e0f6a  mov     ecx, [r9]
0x1800e0f6d  sub     ecx, 6D697463h
0x1800e0f73  jnz     short loc_1800E0F7D
0x1800e0f75  movzx   ecx, byte ptr [r9+4]
0x1800e0f7a  sub     ecx, 65h ; 'e'
0x1800e0f7d  test    ecx, ecx
0x1800e0f7f  jnz     loc_1800E1863
0x1800e0f85  mov     rax, [rbp+arg_30]
0x1800e0f89  lea     r9, [rbp+arg_18]
0x1800e0f8d  mov     rdx, [rbp+arg_28]
0x1800e0f91  lea     r8, [rbp+var_18]
0x1800e0f95  mov     rcx, rsi
0x1800e0f98  mov     [rsp+48h+var_28], rax
0x1800e0f9d  call    pax_attribute_read_time
0x1800e0fa2  mov     ebx, eax
0x1800e0fa4  test    eax, eax
0x1800e0fa6  jnz     loc_1800E197A
0x1800e0fac  mov     r8d, [rbp+arg_18]
0x1800e0fb0  mov     rcx, r15
0x1800e0fb3  mov     rdx, [rbp+var_18]
0x1800e0fb7  call    archive_entry_set_ctime
0x1800e0fbc  jmp     loc_1800E197A
0x1800e0fc1  cmp     [rbp+arg_20], 5
0x1800e0fc6  jnz     loc_1800E1863
0x1800e0fcc  mov     ecx, [r9]
0x1800e0fcf  sub     ecx, 6D697461h
0x1800e0fd5  jnz     short loc_1800E0FDF
0x1800e0fd7  movzx   ecx, byte ptr [r9+4]
0x1800e0fdc  sub     ecx, 65h ; 'e'
0x1800e0fdf  test    ecx, ecx
0x1800e0fe1  jnz     loc_1800E1863
0x1800e0fe7  mov     rax, [rbp+arg_30]
0x1800e0feb  lea     r9, [rbp+arg_18]
0x1800e0fef  mov     rdx, [rbp+arg_28]
0x1800e0ff3  lea     r8, [rbp+var_18]
0x1800e0ff7  mov     rcx, rsi
0x1800e0ffa  mov     [rsp+48h+var_28], rax
0x1800e0fff  call    pax_attribute_read_time
0x1800e1004  mov     ebx, eax
0x1800e1006  test    eax, eax
0x1800e1008  jnz     loc_1800E197A
0x1800e100e  mov     r8d, [rbp+arg_18]
0x1800e1012  mov     rcx, r15
0x1800e1015  mov     rdx, [rbp+var_18]
0x1800e1019  call    archive_entry_set_atime
0x1800e101e  jmp     loc_1800E197A
0x1800e1023  mov     rdi, [rbp+arg_20]
0x1800e1027  cmp     rdi, 7
0x1800e102b  jbe     loc_1800E144F
0x1800e1031  mov     ecx, [r9]
0x1800e1034  sub     ecx, 49484353h
0x1800e103a  jnz     short loc_1800E1052
0x1800e103c  movzx   ecx, word ptr [r9+4]
0x1800e1041  mov     eax, 594Ch
0x1800e1046  sub     ecx, eax
0x1800e1048  jnz     short loc_1800E1052
0x1800e104a  movzx   ecx, byte ptr [r9+6]
0x1800e104f  sub     ecx, 2Eh ; '.'
0x1800e1052  test    ecx, ecx
0x1800e1054  jnz     loc_1800E1459
0x1800e105a  sub     rdi, 7
0x1800e105e  add     rbx, 7
0x1800e1062  cmp     rdi, 0Ah
0x1800e1066  jnz     short loc_1800E10AB
0x1800e1068  mov     rcx, [rbx]
0x1800e106b  mov     rax, 656363612E6C6361h
0x1800e1075  sub     rcx, rax
0x1800e1078  jnz     short loc_1800E1089
0x1800e107a  movzx   ecx, word ptr [rbx+8]
0x1800e107e  mov     eax, 7373h
0x1800e1083  movzx   eax, ax
0x1800e1086  sub     rcx, rax
0x1800e1089  test    rcx, rcx
0x1800e108c  jnz     loc_1800E1368
0x1800e1092  mov     dword ptr [rsp+48h+var_28], 100h
0x1800e109a  mov     r9, [rbp+arg_28]
0x1800e109e  mov     rcx, rsi
0x1800e10a1  call    pax_attribute_SCHILY_acl
0x1800e10a6  jmp     loc_1800E1875
0x1800e10ab  cmp     rdi, 0Bh
0x1800e10af  jnz     short loc_1800E10F4
0x1800e10b1  mov     rcx, [rbx]
0x1800e10b4  mov     rax, 616665642E6C6361h
0x1800e10be  sub     rcx, rax
0x1800e10c1  jnz     short loc_1800E10E1
0x1800e10c3  movzx   ecx, word ptr [rbx+8]
0x1800e10c7  mov     eax, 6C75h
0x1800e10cc  movzx   eax, ax
0x1800e10cf  sub     rcx, rax
0x1800e10d2  jnz     short loc_1800E10E1
0x1800e10d4  movzx   ecx, byte ptr [rbx+0Ah]
0x1800e10d8  lea     eax, [rdi+69h]
0x1800e10db  movzx   eax, al
0x1800e10de  sub     rcx, rax
0x1800e10e1  test    rcx, rcx
0x1800e10e4  jnz     loc_1800E1368
0x1800e10ea  mov     dword ptr [rsp+48h+var_28], 200h
0x1800e10f2  jmp     short loc_1800E109A
0x1800e10f4  cmp     rdi, 7
0x1800e10f8  jnz     short loc_1800E112D
0x1800e10fa  mov     ecx, [rbx]
0x1800e10fc  sub     ecx, 2E6C6361h
0x1800e1102  jnz     short loc_1800E1118
0x1800e1104  movzx   ecx, word ptr [rbx+4]
0x1800e1108  mov     eax, 6361h
0x1800e110d  sub     ecx, eax
0x1800e110f  jnz     short loc_1800E1118
0x1800e1111  movzx   ecx, byte ptr [rbx+6]
0x1800e1115  sub     ecx, 65h ; 'e'
0x1800e1118  test    ecx, ecx
0x1800e111a  jnz     loc_1800E1368
0x1800e1120  mov     dword ptr [rsp+48h+var_28], 3C00h
0x1800e1128  jmp     loc_1800E109A
0x1800e112d  cmp     rdi, 8
0x1800e1131  jnz     loc_1800E11FE
0x1800e1137  mov     rax, [rbx]
0x1800e113a  mov     rcx, 726F6A616D766564h
0x1800e1144  cmp     rax, rcx
0x1800e1147  jnz     short loc_1800E1188
0x1800e1149  mov     rdx, [rbp+arg_28]
0x1800e114d  lea     r8, [rbp+var_18]
0x1800e1151  mov     rcx, rsi
0x1800e1154  call    pax_attribute_read_number
0x1800e1159  test    eax, eax
0x1800e115b  jnz     loc_1800E1875
0x1800e1161  mov     ecx, dword ptr [rbp+var_18]
0x1800e1164  mov     [r15+98h], ecx
0x1800e116b  bts     dword ptr [r15+0A0h], 0Dh
0x1800e1174  mov     qword ptr [r15+90h], 1
0x1800e117f  mov     [r15+10h], r12d
0x1800e1183  jmp     loc_1800E1875
0x1800e1188  mov     rcx, 726F6E696D766564h
0x1800e1192  cmp     rax, rcx
0x1800e1195  jnz     short loc_1800E11BB
0x1800e1197  mov     rdx, [rbp+arg_28]
0x1800e119b  lea     r8, [rbp+var_18]
0x1800e119f  mov     rcx, rsi
0x1800e11a2  call    pax_attribute_read_number
0x1800e11a7  test    eax, eax
0x1800e11a9  jnz     loc_1800E1875
0x1800e11af  mov     ecx, dword ptr [rbp+var_18]
0x1800e11b2  mov     [r15+9Ch], ecx
0x1800e11b9  jmp     short loc_1800E116B
0x1800e11bb  mov     rcx, 657A69736C616572h
0x1800e11c5  cmp     rax, rcx
0x1800e11c8  jnz     loc_1800E1368
0x1800e11ce  mov     rdx, [rbp+arg_28]
0x1800e11d2  lea     r8, [rbp+var_18]
0x1800e11d6  mov     rcx, rsi
0x1800e11d9  call    pax_attribute_read_number
0x1800e11de  test    eax, eax
0x1800e11e0  jnz     loc_1800E1875
0x1800e11e6  mov     rcx, [rbp+var_18]
0x1800e11ea  or      byte ptr [r14+10Ah], 8
0x1800e11f2  mov     [r14+0D0h], rcx
0x1800e11f9  jmp     loc_1800E1875
0x1800e11fe  cmp     rdi, 6
0x1800e1202  jnz     short loc_1800E1275
0x1800e1204  mov     ecx, [rbx]
0x1800e1206  sub     ecx, 616C6666h
0x1800e120c  jnz     short loc_1800E1219
0x1800e120e  movzx   ecx, word ptr [rbx+4]
0x1800e1212  mov     eax, 7367h
0x1800e1217  sub     ecx, eax
0x1800e1219  test    ecx, ecx
0x1800e121b  jnz     loc_1800E1459
0x1800e1221  mov     r14, [rbp+arg_28]
0x1800e1225  lea     rbx, [rsi+278h]
0x1800e122c  cmp     r14, 200h
0x1800e1233  jnb     short loc_1800E1268
0x1800e1235  mov     rcx, [rbx]
0x1800e1238  lea     r8, [rbp+arg_18]
0x1800e123c  mov     rdx, r14
0x1800e123f  call    __archive_read_filter_ahead
0x1800e1244  test    rax, rax
0x1800e1247  jnz     short loc_1800E1255
0x1800e1249  lea     r8, aTruncatedArchi_6; "Truncated archive detected while readin"...
0x1800e1250  jmp     loc_1800E17EF
0x1800e1255  mov     r8, r14
0x1800e1258  mov     rdx, rax
0x1800e125b  mov     rcx, r15
0x1800e125e  call    archive_entry_copy_fflags_text_len
0x1800e1263  mov     edi, r12d
0x1800e1266  jmp     short loc_1800E126D
0x1800e1268  mov     edi, 0FFFFFFECh
0x1800e126d  mov     rdx, r14
0x1800e1270  jmp     loc_1800E1B5C
0x1800e1275  cmp     rdi, 3
0x1800e1279  jnz     loc_1800E1317
0x1800e127f  movzx   ecx, word ptr [rbx]
0x1800e1282  mov     eax, 6564h
0x1800e1287  sub     ecx, eax
0x1800e1289  jnz     short loc_1800E1292
0x1800e128b  movzx   ecx, byte ptr [rbx+2]
0x1800e128f  sub     ecx, 76h ; 'v'
0x1800e1292  test    ecx, ecx
0x1800e1294  jnz     short loc_1800E12D1
0x1800e1296  mov     rdx, [rbp+arg_28]
0x1800e129a  lea     r8, [rbp+var_18]
0x1800e129e  mov     rcx, rsi
0x1800e12a1  call    pax_attribute_read_number
0x1800e12a6  test    eax, eax
0x1800e12a8  jnz     loc_1800E1875
0x1800e12ae  mov     ecx, dword ptr [rbp+var_18]
0x1800e12b1  bts     dword ptr [r15+0A0h], 8
0x1800e12ba  mov     [r15+84h], ecx
0x1800e12c1  mov     [r15+10h], r12d
0x1800e12c5  mov     [r15+80h], r12d
0x1800e12cc  jmp     loc_1800E1875
0x1800e12d1  movzx   ecx, word ptr [rbx]
0x1800e12d4  mov     eax, 6E69h
0x1800e12d9  sub     ecx, eax
0x1800e12db  jnz     short loc_1800E12E4
0x1800e12dd  movzx   ecx, byte ptr [rbx+2]
0x1800e12e1  sub     ecx, 6Fh ; 'o'
0x1800e12e4  test    ecx, ecx
0x1800e12e6  jnz     loc_1800E1863
0x1800e12ec  mov     rdx, [rbp+arg_28]
0x1800e12f0  lea     r8, [rbp+var_18]
0x1800e12f4  mov     rcx, rsi
0x1800e12f7  call    pax_attribute_read_number
0x1800e12fc  mov     ebx, eax
0x1800e12fe  test    eax, eax
0x1800e1300  jnz     loc_1800E197A
0x1800e1306  mov     rdx, [rbp+var_18]
0x1800e130a  mov     rcx, r15
0x1800e130d  call    archive_entry_set_ino64
0x1800e1312  jmp     loc_1800E197A
0x1800e1317  cmp     rdi, 5
0x1800e131b  jnz     short loc_1800E135E
0x1800e131d  mov     ecx, [rbx]
0x1800e131f  sub     ecx, 6E696C6Eh
0x1800e1325  jnz     short loc_1800E132E
0x1800e1327  movzx   ecx, byte ptr [rbx+4]
0x1800e132b  sub     ecx, 6Bh ; 'k'
0x1800e132e  test    ecx, ecx
0x1800e1330  jnz     loc_1800E1459
0x1800e1336  mov     rdx, [rbp+arg_28]
0x1800e133a  lea     r8, [rbp+var_18]
0x1800e133e  mov     rcx, rsi
0x1800e1341  call    pax_attribute_read_number
0x1800e1346  test    eax, eax
0x1800e1348  jnz     loc_1800E1875
0x1800e134e  mov     ecx, dword ptr [rbp+var_18]
0x1800e1351  mov     [r15+68h], ecx
0x1800e1355  mov     [r15+10h], r12d
0x1800e1359  jmp     loc_1800E1875
0x1800e135e  cmp     rdi, 6
0x1800e1362  jbe     loc_1800E144F
0x1800e1368  mov     ecx, [rbx]
0x1800e136a  sub     ecx, 74746178h
0x1800e1370  jnz     short loc_1800E137D
0x1800e1372  movzx   ecx, word ptr [rbx+4]
0x1800e1376  mov     eax, 2E72h
0x1800e137b  sub     ecx, eax
0x1800e137d  test    ecx, ecx
0x1800e137f  jnz     loc_1800E144F
0x1800e1385  mov     r14, [rbp+arg_28]
0x1800e1389  lea     r12, [rsi+278h]
0x1800e1390  mov     eax, 1000000h
0x1800e1395  cmp     r14, rax
0x1800e1398  jnb     loc_1800E141F
0x1800e139e  mov     rcx, [r12]
0x1800e13a2  lea     r8, [rbp+arg_18]
  ... truncated ...
```
