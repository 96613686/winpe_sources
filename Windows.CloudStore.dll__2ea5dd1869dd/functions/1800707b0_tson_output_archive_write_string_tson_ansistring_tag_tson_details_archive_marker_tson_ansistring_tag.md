# tson::output_archive::write_string<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag)

- ea: `0x1800707b0`
- end: `0x180070e65`
- name: `??$write_string@Uansistring_tag@tson@@@output_archive@tson@@AEAAXW4archive_marker@details@1@Uansistring_tag@1@@Z`
- size: `1717`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006fab0`
- `0x1800e3374`
- `0x1800f75f0`

## callees

- `0x1800707b0`
- `0x180074110`
- `0x1800741f4`
- `0x180077e10`
- `0x180077e30`
- `0x18007b050`
- `0x18007d3c0`
- `0x1800a6f3c`
- `0x180120bea`
- `0x180120c94`
- `0x180123882`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180070a28`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180070adb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180070b04`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180070c72`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180070a28`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180070adb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180070b04`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180070c72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070d31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070d60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070d9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070ddd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070d31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070d60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070d9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070ddd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070842`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070920`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070a72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070b55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070842`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070920`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070a72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070b55`

## pseudocode

```c
void __fastcall tson::output_archive::write_string<tson::ansistring_tag>(__int64 a1, char a2, const void **a3)
{
  const void **v4; // r13
  const void *v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rbx
  unsigned __int64 v9; // rdx
  char *v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 v12; // rax
  rsize_t v13; // r12
  char *v14; // rax
  char *v15; // r14
  const void *v16; // r8
  rsize_t v17; // r15
  void *v18; // r13
  __int64 v19; // rbx
  unsigned __int64 v20; // rdx
  char *v21; // rcx
  unsigned __int64 v22; // rdx
  __int64 v23; // rax
  rsize_t v24; // r15
  char *v25; // rax
  char *v26; // rsi
  const void *v27; // r8
  rsize_t v28; // r14
  void *v29; // r12
  __int64 v30; // rbx
  __int64 v31; // rsi
  size_t v32; // rbx
  const void *v33; // r15
  void *v34; // rcx
  size_t v35; // r14
  __int64 v36; // rbx
  unsigned __int64 v37; // rdx
  char *v38; // rcx
  unsigned __int64 v39; // rdx
  __int64 v40; // rax
  rsize_t v41; // r14
  char *v42; // rax
  char *v43; // rdi
  const void *v44; // r8
  rsize_t v45; // rsi
  void *v46; // r15
  __int64 v47; // rbx
  unsigned __int64 v48; // rdx
  char *v49; // rcx
  unsigned __int64 v50; // rdx
  __int64 v51; // rax
  rsize_t v52; // r15
  char *v53; // rax
  char *v54; // rsi
  const void *v55; // r8
  rsize_t v56; // r14
  void *v57; // r12
  size_t v58; // rbx
  const void *v59; // r14
  unsigned __int64 v60; // rcx
  __int64 v61; // rsi
  char v62; // r15
  tson::write_buffer *v63; // rdi
  void *v64; // rcx
  size_t v65; // rsi
  __int64 v66; // rcx
  char v67; // ah
  __int64 v68; // rcx
  const void *v69; // [rsp+70h] [rbp+48h]
  char v70; // [rsp+78h] [rbp+50h] BYREF
  const void **v71; // [rsp+80h] [rbp+58h] BYREF
  char v72; // [rsp+88h] [rbp+60h] BYREF

  v71 = a3;
  v70 = a2;
  v4 = a3;
  v5 = *a3;
  v69 = *a3;
  v6 = a1 + 24;
  v7 = *(_QWORD *)(a1 + 128);
  if ( v7 )
    v6 = v6 + 4 * v7 - 4;
  else
    *(_BYTE *)v6 = 1;
  if ( *(_DWORD *)(v6 + 4) == 2 )
  {
    *(_DWORD *)(v6 + 4) = 3;
    v66 = *(_QWORD *)(a1 + 144);
    v70 = 3;
    tson::write_buffer::push_back<enum tson::details::archive_marker>(v66, &v70);
    tson::write_buffer::push_back(*(tson::write_buffer **)(a1 + 144), (const void *)(a1 + 10), 2u);
    *(_WORD *)(a1 + 10) = 0;
  }
  else
  {
    if ( *(_DWORD *)(v6 + 4) )
      goto LABEL_14;
    *(_DWORD *)(v6 + 4) = 1;
    v8 = *(_QWORD *)(a1 + 144);
    v9 = *(_QWORD *)(v8 + 2080);
    v10 = *(char **)(v8 + 2072);
    if ( (unsigned __int64)v10 >= v9 )
    {
      v11 = v9 - *(_QWORD *)(v8 + 2064);
      v12 = 1;
      if ( v11 > 1 )
        v12 = v11;
      v13 = 2 * v12;
      v14 = (char *)CoTaskMemAlloc(2 * v12);
      v15 = v14;
      if ( !v14 )
      {
        *(_BYTE *)(v8 + 8) = 1;
        goto LABEL_13;
      }
      v16 = *(const void **)(v8 + 2064);
      v17 = *(_QWORD *)(v8 + 2072) - (_QWORD)v16;
      memcpy_s_1(v14, v13, v16, v17);
      v18 = *(void **)v8;
      if ( *(_QWORD *)v8 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v72);
        CoTaskMemFree(v18);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v72);
      }
      v4 = v71;
      *(_QWORD *)v8 = v15;
      v10 = &v15[v17];
      *(_QWORD *)(v8 + 2072) = &v15[v17];
      *(_QWORD *)(v8 + 2080) = &v15[v13];
      *(_QWORD *)(v8 + 2064) = v15;
    }
    *v10 = 1;
    ++*(_QWORD *)(v8 + 2072);
  }
LABEL_13:
  v5 = v69;
LABEL_14:
  *(_QWORD *)(a1 + 16) = 0;
  if ( *(_DWORD *)(v6 + 4) == 3 )
    goto LABEL_50;
  if ( !v5 )
  {
    v36 = *(_QWORD *)(a1 + 144);
    *(_QWORD *)a1 = 0;
    v37 = *(_QWORD *)(v36 + 2080);
    v38 = *(char **)(v36 + 2072);
    if ( (unsigned __int64)v38 >= v37 )
    {
      v39 = v37 - *(_QWORD *)(v36 + 2064);
      v40 = 1;
      if ( v39 > 1 )
        v40 = v39;
      v41 = 2 * v40;
      v42 = (char *)CoTaskMemAlloc(2 * v40);
      v43 = v42;
      if ( !v42 )
      {
        *(_BYTE *)(v36 + 8) = 1;
        return;
      }
      v44 = *(const void **)(v36 + 2064);
      v45 = *(_QWORD *)(v36 + 2072) - (_QWORD)v44;
      memcpy_s_1(v42, v41, v44, v45);
      v46 = *(void **)v36;
      if ( *(_QWORD *)v36 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v71);
        CoTaskMemFree(v46);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v71);
      }
      *(_QWORD *)v36 = v43;
      v38 = &v43[v45];
      *(_QWORD *)(v36 + 2072) = &v43[v45];
      *(_QWORD *)(v36 + 2080) = &v43[v41];
      *(_QWORD *)(v36 + 2064) = v43;
    }
    *v38 = 6;
    ++*(_QWORD *)(v36 + 2072);
    return;
  }
  if ( !*(_QWORD *)a1 )
  {
    *(_BYTE *)(a1 + 8) = 1;
    *(_QWORD *)a1 = "-";
  }
  v19 = *(_QWORD *)(a1 + 144);
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(v19 + 2072) - *(_QWORD *)(v19 + 2064);
  v20 = *(_QWORD *)(v19 + 2080);
  v21 = *(char **)(v19 + 2072);
  if ( (unsigned __int64)v21 >= v20 )
  {
    v22 = v20 - *(_QWORD *)(v19 + 2064);
    v23 = 1;
    if ( v22 > 1 )
      v23 = v22;
    v24 = 2 * v23;
    v25 = (char *)CoTaskMemAlloc(2 * v23);
    v26 = v25;
    if ( !v25 )
    {
      *(_BYTE *)(v19 + 8) = 1;
      goto LABEL_26;
    }
    v27 = *(const void **)(v19 + 2064);
    v28 = *(_QWORD *)(v19 + 2072) - (_QWORD)v27;
    memcpy_s_1(v25, v24, v27, v28);
    v29 = *(void **)v19;
    if ( *(_QWORD *)v19 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v71);
      CoTaskMemFree(v29);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v71);
    }
    *(_QWORD *)v19 = v26;
    v21 = &v26[v28];
    *(_QWORD *)(v19 + 2072) = &v26[v28];
    *(_QWORD *)(v19 + 2080) = &v26[v24];
    *(_QWORD *)(v19 + 2064) = v26;
  }
  *v21 = 5;
  ++*(_QWORD *)(v19 + 2072);
LABEL_26:
  v30 = *(_QWORD *)(a1 + 144);
  if ( *(_QWORD *)(v30 + 2072) < *(_QWORD *)(v30 + 2080)
    || tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), 1u) )
  {
    *(_BYTE *)(*(_QWORD *)(v30 + 2072))++ = *(_BYTE *)(a1 + 8);
  }
  v31 = *(_QWORD *)(a1 + 144);
  v32 = *(unsigned __int8 *)(a1 + 8);
  v33 = *(const void **)a1;
  if ( *(_QWORD *)(v31 + 2080) - *(_QWORD *)(v31 + 2072) < v32
    && !tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), *(unsigned __int8 *)(a1 + 8)) )
  {
    goto LABEL_49;
  }
  if ( v32 )
  {
    v34 = *(void **)(v31 + 2072);
    if ( !v34 )
      goto LABEL_46;
    v35 = *(_QWORD *)(v31 + 2080) - (_QWORD)v34;
    if ( v33 && v35 >= v32 )
    {
      memcpy_0(v34, v33, v32);
      goto LABEL_48;
    }
    memset_0(v34, 0, *(_QWORD *)(v31 + 2080) - (_QWORD)v34);
    if ( !v33 )
    {
LABEL_46:
      *(_DWORD *)_o__errno() = 22;
      goto LABEL_47;
    }
    if ( v35 < v32 )
    {
      *(_DWORD *)_o__errno() = 34;
LABEL_47:
      invalid_parameter_noinfo();
    }
  }
LABEL_48:
  *(_QWORD *)(v31 + 2072) += v32;
LABEL_49:
  *(_QWORD *)a1 = 0;
LABEL_50:
  v47 = *(_QWORD *)(a1 + 144);
  v48 = *(_QWORD *)(v47 + 2080);
  v49 = *(char **)(v47 + 2072);
  if ( (unsigned __int64)v49 < v48 )
  {
LABEL_57:
    *v49 = 23;
    ++*(_QWORD *)(v47 + 2072);
    goto LABEL_58;
  }
  v50 = v48 - *(_QWORD *)(v47 + 2064);
  v51 = 1;
  if ( v50 > 1 )
    v51 = v50;
  v52 = 2 * v51;
  v53 = (char *)CoTaskMemAlloc(2 * v51);
  v54 = v53;
  if ( v53 )
  {
    v55 = *(const void **)(v47 + 2064);
    v56 = *(_QWORD *)(v47 + 2072) - (_QWORD)v55;
    memcpy_s_1(v53, v52, v55, v56);
    v57 = *(void **)v47;
    if ( *(_QWORD *)v47 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v71);
      CoTaskMemFree(v57);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v71);
    }
    *(_QWORD *)v47 = v54;
    v49 = &v54[v56];
    *(_QWORD *)(v47 + 2072) = &v54[v56];
    *(_QWORD *)(v47 + 2080) = &v54[v52];
    *(_QWORD *)(v47 + 2064) = v54;
    goto LABEL_57;
  }
  *(_BYTE *)(v47 + 8) = 1;
LABEL_58:
  v58 = (size_t)v4[1];
  v59 = *v4;
  v60 = v58 + 1;
  if ( v58 + 1 > 0x7F )
  {
    if ( v60 > 0x7FFF && *(int *)(a1 + 136) >= 0 )
      *(_DWORD *)(a1 + 136) = -2147483637;
    v67 = BYTE1(v60) | 0x80;
    LOBYTE(v71) = v58 + 1;
    v68 = *(_QWORD *)(a1 + 144);
    v70 = v67;
    tson::write_buffer::push_back<unsigned char>(v68, &v70);
    tson::write_buffer::push_back<unsigned char>(*(_QWORD *)(a1 + 144), &v71);
  }
  else
  {
    v61 = *(_QWORD *)(a1 + 144);
    v62 = v59 != 0 ? v60 : 0;
    if ( *(_QWORD *)(v61 + 2072) < *(_QWORD *)(v61 + 2080)
      || tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v61 + 2072))++ = v62;
    }
  }
  v63 = *(tson::write_buffer **)(a1 + 144);
  if ( *((_QWORD *)v63 + 260) - *((_QWORD *)v63 + 259) >= v58 || tson::write_buffer::reserve(v63, v58) )
  {
    if ( v58 )
    {
      v64 = (void *)*((_QWORD *)v63 + 259);
      if ( !v64 )
        goto LABEL_43;
      v65 = *((_QWORD *)v63 + 260) - (_QWORD)v64;
      if ( v59 && v65 >= v58 )
      {
        memcpy_0(v64, v59, v58);
        goto LABEL_45;
      }
      memset_0(v64, 0, *((_QWORD *)v63 + 260) - (_QWORD)v64);
      if ( v59 )
      {
        if ( v65 >= v58 )
          goto LABEL_45;
        *(_DWORD *)_o__errno() = 34;
      }
      else
      {
LABEL_43:
        *(_DWORD *)_o__errno() = 22;
      }
      invalid_parameter_noinfo();
    }
LABEL_45:
    *((_QWORD *)v63 + 259) += v58;
  }
}

```

## disassembly

```asm
0x1800707b0  mov     [rsp-40h+arg_10], r8
0x1800707b5  mov     [rsp-40h+arg_8], dl
0x1800707b9  push    rbp
0x1800707ba  push    rbx
0x1800707bb  push    rsi
0x1800707bc  push    rdi
0x1800707bd  push    r12
0x1800707bf  push    r13
0x1800707c1  push    r14
0x1800707c3  push    r15
0x1800707c5  mov     rbp, rsp
0x1800707c8  sub     rsp, 28h
0x1800707cc  mov     rdi, rcx
0x1800707cf  mov     r13, r8
0x1800707d2  mov     rcx, [r8]
0x1800707d5  mov     r12d, 1
0x1800707db  mov     [rbp+arg_0], rcx
0x1800707df  lea     rsi, [rdi+18h]
0x1800707e3  mov     rax, [rsi+68h]
0x1800707e7  test    rax, rax
0x1800707ea  jz      loc_180070CE1
0x1800707f0  lea     rsi, [rsi+rax*4]
0x1800707f4  add     rsi, 0FFFFFFFFFFFFFFFCh
0x1800707f8  cmp     dword ptr [rsi+4], 2
0x1800707fc  jz      loc_180070CE9
0x180070802  cmp     dword ptr [rsi+4], 0
0x180070806  jnz     loc_1800708B7
0x18007080c  mov     [rsi+4], r12d
0x180070810  mov     rbx, [rdi+90h]
0x180070817  mov     rdx, [rbx+820h]
0x18007081e  mov     rcx, [rbx+818h]
0x180070825  cmp     rcx, rdx
0x180070828  jb      short loc_1800708A9
0x18007082a  sub     rdx, [rbx+810h]
0x180070831  mov     rax, r12
0x180070834  cmp     rdx, r12
0x180070837  cmova   rax, rdx
0x18007083b  lea     r12, [rax+rax]
0x18007083f  mov     rcx, r12; cb
0x180070842  call    cs:__imp_CoTaskMemAlloc
0x180070848  mov     r14, rax
0x18007084b  test    rax, rax
0x18007084e  jz      loc_180070D45
0x180070854  mov     r8, [rbx+810h]; Source
0x18007085b  mov     rdx, r12; DestinationSize
0x18007085e  mov     r15, [rbx+818h]
0x180070865  mov     rcx, rax; Destination
0x180070868  sub     r15, r8
0x18007086b  mov     r9, r15; SourceSize
0x18007086e  call    memcpy_s_1
0x180070873  mov     r13, [rbx]
0x180070876  test    r13, r13
0x180070879  jnz     loc_180070D25
0x18007087f  mov     r13, [rbp+arg_10]
0x180070883  lea     rax, [r12+r14]
0x180070887  mov     [rbx], r14
0x18007088a  lea     rcx, [r15+r14]
0x18007088e  mov     [rbx+818h], rcx
0x180070895  mov     r12d, 1
0x18007089b  mov     [rbx+820h], rax
0x1800708a2  mov     [rbx+810h], r14
0x1800708a9  mov     [rcx], r12b
0x1800708ac  add     [rbx+818h], r12
0x1800708b3  mov     rcx, [rbp+arg_0]
0x1800708b7  mov     qword ptr [rdi+10h], 0
0x1800708bf  cmp     dword ptr [rsi+4], 3
0x1800708c3  jz      loc_180070B23
0x1800708c9  test    rcx, rcx
0x1800708cc  jz      loc_180070A39
0x1800708d2  cmp     qword ptr [rdi], 0
0x1800708d6  jz      loc_180070D7D
0x1800708dc  mov     rbx, [rdi+90h]
0x1800708e3  mov     rax, [rbx+818h]
0x1800708ea  sub     rax, [rbx+810h]
0x1800708f1  mov     [rdi+10h], rax
0x1800708f5  mov     rdx, [rbx+820h]
0x1800708fc  mov     rcx, [rbx+818h]
0x180070903  cmp     rcx, rdx
0x180070906  jb      short loc_180070983
0x180070908  sub     rdx, [rbx+810h]
0x18007090f  mov     rax, r12
0x180070912  cmp     rdx, r12
0x180070915  cmova   rax, rdx
0x180070919  lea     r15, [rax+rax]
0x18007091d  mov     rcx, r15; cb
0x180070920  call    cs:__imp_CoTaskMemAlloc
0x180070926  mov     rsi, rax
0x180070929  test    rax, rax
0x18007092c  jz      loc_180070DB0
0x180070932  mov     r8, [rbx+810h]; Source
0x180070939  mov     rdx, r15; DestinationSize
0x18007093c  mov     r14, [rbx+818h]
0x180070943  mov     rcx, rax; Destination
0x180070946  sub     r14, r8
0x180070949  mov     r9, r14; SourceSize
0x18007094c  call    memcpy_s_1
0x180070951  mov     r12, [rbx]
0x180070954  test    r12, r12
0x180070957  jnz     loc_180070D90
0x18007095d  mov     [rbx], rsi
0x180070960  lea     rcx, [r14+rsi]
0x180070964  lea     rax, [r15+rsi]
0x180070968  mov     [rbx+818h], rcx
0x18007096f  mov     [rbx+820h], rax
0x180070976  mov     r12d, 1
0x18007097c  mov     [rbx+810h], rsi
0x180070983  mov     byte ptr [rcx], 5
0x180070986  add     [rbx+818h], r12
0x18007098d  mov     rbx, [rdi+90h]
0x180070994  mov     rax, [rbx+820h]
0x18007099b  cmp     [rbx+818h], rax
0x1800709a2  jnb     loc_180070DB9
0x1800709a8  mov     rcx, [rbx+818h]
0x1800709af  mov     al, [rdi+8]
0x1800709b2  mov     [rcx], al
0x1800709b4  add     [rbx+818h], r12
0x1800709bb  mov     rsi, [rdi+90h]
0x1800709c2  movzx   ebx, byte ptr [rdi+8]
0x1800709c6  mov     r15, [rdi]
0x1800709c9  mov     rax, [rsi+820h]
0x1800709d0  sub     rax, [rsi+818h]
0x1800709d7  cmp     rax, rbx
0x1800709da  jb      loc_180070CC9
0x1800709e0  test    rbx, rbx
0x1800709e3  jz      loc_180070B15
0x1800709e9  mov     rcx, [rsi+818h]; void *
0x1800709f0  test    rcx, rcx
0x1800709f3  jz      loc_180070B04
0x1800709f9  mov     r14, [rsi+820h]
0x180070a00  sub     r14, rcx
0x180070a03  test    r15, r15
0x180070a06  jnz     loc_180070C98
0x180070a0c  mov     r8, r14; Size
0x180070a0f  xor     edx, edx; Val
0x180070a11  call    memset_0
0x180070a16  test    r15, r15
0x180070a19  jz      loc_180070B04
0x180070a1f  cmp     r14, rbx
0x180070a22  jnb     loc_180070B15
0x180070a28  call    cs:__imp__o__errno
0x180070a2e  mov     dword ptr [rax], 22h ; '"'
0x180070a34  jmp     loc_180070B10
0x180070a39  mov     rbx, [rdi+90h]
0x180070a40  mov     qword ptr [rdi], 0
0x180070a47  mov     rdx, [rbx+820h]
0x180070a4e  mov     rcx, [rbx+818h]
0x180070a55  cmp     rcx, rdx
0x180070a58  jb      short loc_180070ACF
0x180070a5a  sub     rdx, [rbx+810h]
0x180070a61  mov     rax, r12
0x180070a64  cmp     rdx, r12
0x180070a67  cmova   rax, rdx
0x180070a6b  lea     r14, [rax+rax]
0x180070a6f  mov     rcx, r14; cb
0x180070a72  call    cs:__imp_CoTaskMemAlloc
0x180070a78  mov     rdi, rax
0x180070a7b  test    rax, rax
0x180070a7e  jz      loc_180070D74
0x180070a84  mov     r8, [rbx+810h]; Source
0x180070a8b  mov     rdx, r14; DestinationSize
0x180070a8e  mov     rsi, [rbx+818h]
0x180070a95  mov     rcx, rax; Destination
0x180070a98  sub     rsi, r8
0x180070a9b  mov     r9, rsi; SourceSize
0x180070a9e  call    memcpy_s_1
0x180070aa3  mov     r15, [rbx]
0x180070aa6  test    r15, r15
0x180070aa9  jnz     loc_180070D54
0x180070aaf  mov     [rbx], rdi
0x180070ab2  lea     rcx, [rsi+rdi]
0x180070ab6  lea     rax, [r14+rdi]
0x180070aba  mov     [rbx+818h], rcx
0x180070ac1  mov     [rbx+820h], rax
0x180070ac8  mov     [rbx+810h], rdi
0x180070acf  mov     byte ptr [rcx], 6
0x180070ad2  add     [rbx+818h], r12
0x180070ad9  jmp     short loc_180070AF3
0x180070adb  call    cs:__imp__o__errno
0x180070ae1  mov     dword ptr [rax], 16h
0x180070ae7  call    _invalid_parameter_noinfo
0x180070aec  add     [rdi+818h], rbx
0x180070af3  add     rsp, 28h
0x180070af7  pop     r15
0x180070af9  pop     r14
0x180070afb  pop     r13
0x180070afd  pop     r12
0x180070aff  pop     rdi
0x180070b00  pop     rsi
0x180070b01  pop     rbx
0x180070b02  pop     rbp
0x180070b03  retn
0x180070b04  call    cs:__imp__o__errno
0x180070b0a  mov     dword ptr [rax], 16h
0x180070b10  call    _invalid_parameter_noinfo
0x180070b15  add     [rsi+818h], rbx
0x180070b1c  mov     qword ptr [rdi], 0
0x180070b23  mov     rbx, [rdi+90h]
0x180070b2a  mov     rdx, [rbx+820h]
0x180070b31  mov     rcx, [rbx+818h]
0x180070b38  cmp     rcx, rdx
0x180070b3b  jb      short loc_180070BB8
0x180070b3d  sub     rdx, [rbx+810h]
0x180070b44  mov     rax, r12
0x180070b47  cmp     rdx, r12
0x180070b4a  cmova   rax, rdx
0x180070b4e  lea     r15, [rax+rax]
0x180070b52  mov     rcx, r15; cb
0x180070b55  call    cs:__imp_CoTaskMemAlloc
0x180070b5b  mov     rsi, rax
0x180070b5e  test    rax, rax
0x180070b61  jz      loc_180070DF1
0x180070b67  mov     r8, [rbx+810h]; Source
0x180070b6e  mov     rdx, r15; DestinationSize
0x180070b71  mov     r14, [rbx+818h]
0x180070b78  mov     rcx, rax; Destination
0x180070b7b  sub     r14, r8
0x180070b7e  mov     r9, r14; SourceSize
0x180070b81  call    memcpy_s_1
0x180070b86  mov     r12, [rbx]
0x180070b89  test    r12, r12
0x180070b8c  jnz     loc_180070DD1
0x180070b92  mov     [rbx], rsi
0x180070b95  lea     rcx, [r14+rsi]
0x180070b99  lea     rax, [r15+rsi]
0x180070b9d  mov     [rbx+818h], rcx
0x180070ba4  mov     [rbx+820h], rax
0x180070bab  mov     r12d, 1
0x180070bb1  mov     [rbx+810h], rsi
0x180070bb8  mov     byte ptr [rcx], 17h
0x180070bbb  add     [rbx+818h], r12
0x180070bc2  mov     rbx, [r13+8]
0x180070bc6  mov     r14, [r13+0]
0x180070bca  lea     rcx, [rbx+1]
0x180070bce  cmp     rcx, 7Fh
0x180070bd2  ja      loc_180070E12
0x180070bd8  mov     rsi, [rdi+90h]
0x180070bdf  mov     rax, r14
0x180070be2  neg     rax
0x180070be5  sbb     r15b, r15b
0x180070be8  mov     rax, [rsi+820h]
0x180070bef  and     r15b, cl
0x180070bf2  cmp     [rsi+818h], rax
0x180070bf9  jnb     loc_180070DFA
0x180070bff  mov     rax, [rsi+818h]
0x180070c06  mov     [rax], r15b
0x180070c09  add     [rsi+818h], r12
0x180070c10  mov     rdi, [rdi+90h]
0x180070c17  mov     rax, [rdi+820h]
0x180070c1e  sub     rax, [rdi+818h]
0x180070c25  cmp     rax, rbx
0x180070c28  jb      loc_180070CB1
0x180070c2e  test    rbx, rbx
0x180070c31  jz      loc_180070AEC
0x180070c37  mov     rcx, [rdi+818h]; void *
0x180070c3e  test    rcx, rcx
0x180070c41  jz      loc_180070ADB
0x180070c47  mov     rsi, [rdi+820h]
0x180070c4e  sub     rsi, rcx
0x180070c51  test    r14, r14
0x180070c54  jnz     short loc_180070C83
0x180070c56  mov     r8, rsi; Size
0x180070c59  xor     edx, edx; Val
0x180070c5b  call    memset_0
0x180070c60  test    r14, r14
0x180070c63  jz      loc_180070ADB
0x180070c69  cmp     rsi, rbx
0x180070c6c  jnb     loc_180070AEC
0x180070c72  call    cs:__imp__o__errno
0x180070c78  mov     dword ptr [rax], 22h ; '"'
0x180070c7e  jmp     loc_180070AE7
0x180070c83  cmp     rsi, rbx
0x180070c86  jb      short loc_180070C56
0x180070c88  mov     r8, rbx; Size
0x180070c8b  mov     rdx, r14; Src
0x180070c8e  call    memcpy_0
0x180070c93  jmp     loc_180070AEC
0x180070c98  cmp     r14, rbx
0x180070c9b  jb      loc_180070A0C
0x180070ca1  mov     r8, rbx; Size
0x180070ca4  mov     rdx, r15; Src
0x180070ca7  call    memcpy_0
0x180070cac  jmp     loc_180070B15
0x180070cb1  mov     rdx, rbx; unsigned __int64
0x180070cb4  mov     rcx, rdi; this
0x180070cb7  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180070cbc  test    al, al
0x180070cbe  jnz     loc_180070C2E
0x180070cc4  jmp     loc_180070AF3
0x180070cc9  mov     rdx, rbx; unsigned __int64
0x180070ccc  mov     rcx, rsi; this
0x180070ccf  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180070cd4  test    al, al
0x180070cd6  jnz     loc_1800709E0
0x180070cdc  jmp     loc_180070B1C
0x180070ce1  mov     [rsi], r12b
0x180070ce4  jmp     loc_1800707F8
0x180070ce9  mov     dword ptr [rsi+4], 3
0x180070cf0  lea     rdx, [rbp+arg_8]
0x180070cf4  mov     rcx, [rdi+90h]
0x180070cfb  mov     [rbp+arg_8], 3
  ... truncated ...
```
