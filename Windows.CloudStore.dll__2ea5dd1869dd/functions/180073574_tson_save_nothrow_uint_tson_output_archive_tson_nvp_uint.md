# tson::save_nothrow<uint &>(tson::output_archive &,tson::nvp<uint &> &)

- ea: `0x180073574`
- end: `0x180073b39`
- name: `??$save_nothrow@AEAI@tson@@YAXAEAVoutput_archive@0@AEAV?$nvp@AEAI@0@@Z`
- size: `1477`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180072364`
- `0x180072540`
- `0x180072764`

## callees

- `0x180073574`
- `0x180074110`
- `0x1800741f4`
- `0x180077e10`
- `0x180077e30`
- `0x18007b050`
- `0x1800a6f3c`
- `0x180120bea`
- `0x180120c94`
- `0x180123882`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800737e4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180073893`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800738bc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180073b28`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800737e4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180073893`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800738bc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180073b28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073a51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073a82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073ac0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073b03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073a51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073a82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073ac0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073b03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800736dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007382a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800736dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007382a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073909`

## pseudocode

```c
void __fastcall tson::save_nothrow<unsigned int &>(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  char v3; // r8
  int v5; // r13d
  __int64 v6; // rax
  __int64 v7; // rbx
  unsigned __int64 v8; // rdx
  char *v9; // rcx
  unsigned __int64 v10; // rdx
  __int64 v11; // rax
  rsize_t v12; // r15
  char *v13; // rax
  char *v14; // rbp
  const void *v15; // r8
  rsize_t v16; // r14
  void *v17; // r12
  __int64 v18; // rbx
  unsigned __int64 v19; // rdx
  char *v20; // rcx
  unsigned __int64 v21; // rdx
  __int64 v22; // rax
  rsize_t v23; // r14
  char *v24; // rax
  char *v25; // rsi
  const void *v26; // r8
  rsize_t v27; // rbp
  void *v28; // r15
  __int64 v29; // rbx
  __int64 v30; // rsi
  size_t v31; // rbx
  const void *v32; // r14
  void *v33; // rcx
  size_t v34; // rbp
  __int64 v35; // rbx
  unsigned __int64 v36; // rdx
  char *v37; // rcx
  unsigned __int64 v38; // rdx
  __int64 v39; // rax
  rsize_t v40; // r14
  char *v41; // rax
  char *v42; // rdi
  const void *v43; // r8
  rsize_t v44; // rsi
  void *v45; // rbp
  __int64 v46; // rbx
  unsigned __int64 v47; // rdx
  char *v48; // rcx
  unsigned __int64 v49; // rdx
  __int64 v50; // rax
  rsize_t v51; // r14
  char *v52; // rax
  char *v53; // rsi
  const void *v54; // r8
  rsize_t v55; // rbp
  void *v56; // r15
  tson::write_buffer *v57; // rbx
  _DWORD *v58; // rcx
  size_t v59; // r8
  __int64 v60; // rcx
  char v61; // [rsp+70h] [rbp+8h] BYREF

  v2 = a1 + 24;
  v3 = *(_BYTE *)(a2 + 8);
  *(_QWORD *)a1 = *(_QWORD *)a2;
  *(_BYTE *)(a1 + 8) = v3;
  v5 = **(_DWORD **)(a2 + 16);
  v6 = *(_QWORD *)(a1 + 128);
  if ( v6 )
    v2 = v2 + 4 * v6 - 4;
  else
    *(_BYTE *)v2 = 1;
  if ( *(_DWORD *)(v2 + 4) == 2 )
  {
    *(_DWORD *)(v2 + 4) = 3;
    v60 = *(_QWORD *)(a1 + 144);
    v61 = 3;
    tson::write_buffer::push_back<enum tson::details::archive_marker>(v60, &v61);
    tson::write_buffer::push_back(*(tson::write_buffer **)(a1 + 144), (const void *)(a1 + 10), 2u);
    *(_WORD *)(a1 + 10) = 0;
  }
  else
  {
    if ( *(_DWORD *)(v2 + 4) )
      goto LABEL_13;
    *(_DWORD *)(v2 + 4) = 1;
    v7 = *(_QWORD *)(a1 + 144);
    v8 = *(_QWORD *)(v7 + 2080);
    v9 = *(char **)(v7 + 2072);
    if ( (unsigned __int64)v9 < v8 )
      goto LABEL_12;
    v10 = v8 - *(_QWORD *)(v7 + 2064);
    v11 = 1;
    if ( v10 > 1 )
      v11 = v10;
    v12 = 2 * v11;
    v13 = (char *)CoTaskMemAlloc(2 * v11);
    v14 = v13;
    if ( v13 )
    {
      v15 = *(const void **)(v7 + 2064);
      v16 = *(_QWORD *)(v7 + 2072) - (_QWORD)v15;
      memcpy_s_1(v13, v12, v15, v16);
      v17 = *(void **)v7;
      if ( *(_QWORD *)v7 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v61);
        CoTaskMemFree(v17);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v61);
      }
      *(_QWORD *)v7 = v14;
      *(_QWORD *)(v7 + 2064) = v14;
      v9 = &v14[v16];
      *(_QWORD *)(v7 + 2080) = &v14[v12];
      *(_QWORD *)(v7 + 2072) = &v14[v16];
LABEL_12:
      *v9 = 1;
      ++*(_QWORD *)(v7 + 2072);
      goto LABEL_13;
    }
    *(_BYTE *)(v7 + 8) = 1;
  }
LABEL_13:
  *(_QWORD *)(a1 + 16) = 0;
  if ( *(_DWORD *)(v2 + 4) == 3 )
    goto LABEL_49;
  if ( !v5 )
  {
    v35 = *(_QWORD *)(a1 + 144);
    *(_QWORD *)a1 = 0;
    v36 = *(_QWORD *)(v35 + 2080);
    v37 = *(char **)(v35 + 2072);
    if ( (unsigned __int64)v37 >= v36 )
    {
      v38 = v36 - *(_QWORD *)(v35 + 2064);
      v39 = 1;
      if ( v38 > 1 )
        v39 = v38;
      v40 = 2 * v39;
      v41 = (char *)CoTaskMemAlloc(2 * v39);
      v42 = v41;
      if ( !v41 )
      {
        *(_BYTE *)(v35 + 8) = 1;
        return;
      }
      v43 = *(const void **)(v35 + 2064);
      v44 = *(_QWORD *)(v35 + 2072) - (_QWORD)v43;
      memcpy_s_1(v41, v40, v43, v44);
      v45 = *(void **)v35;
      if ( *(_QWORD *)v35 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v61);
        CoTaskMemFree(v45);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v61);
      }
      *(_QWORD *)v35 = v42;
      v37 = &v42[v44];
      *(_QWORD *)(v35 + 2072) = &v42[v44];
      *(_QWORD *)(v35 + 2080) = &v42[v40];
      *(_QWORD *)(v35 + 2064) = v42;
    }
    *v37 = 6;
    ++*(_QWORD *)(v35 + 2072);
    return;
  }
  if ( !*(_QWORD *)a1 )
  {
    *(_BYTE *)(a1 + 8) = 1;
    *(_QWORD *)a1 = "-";
  }
  v18 = *(_QWORD *)(a1 + 144);
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(v18 + 2072) - *(_QWORD *)(v18 + 2064);
  v19 = *(_QWORD *)(v18 + 2080);
  v20 = *(char **)(v18 + 2072);
  if ( (unsigned __int64)v20 >= v19 )
  {
    v21 = v19 - *(_QWORD *)(v18 + 2064);
    v22 = 1;
    if ( v21 > 1 )
      v22 = v21;
    v23 = 2 * v22;
    v24 = (char *)CoTaskMemAlloc(2 * v22);
    v25 = v24;
    if ( !v24 )
    {
      *(_BYTE *)(v18 + 8) = 1;
      goto LABEL_25;
    }
    v26 = *(const void **)(v18 + 2064);
    v27 = *(_QWORD *)(v18 + 2072) - (_QWORD)v26;
    memcpy_s_1(v24, v23, v26, v27);
    v28 = *(void **)v18;
    if ( *(_QWORD *)v18 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v61);
      CoTaskMemFree(v28);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v61);
    }
    *(_QWORD *)v18 = v25;
    v20 = &v25[v27];
    *(_QWORD *)(v18 + 2072) = &v25[v27];
    *(_QWORD *)(v18 + 2080) = &v25[v23];
    *(_QWORD *)(v18 + 2064) = v25;
  }
  *v20 = 5;
  ++*(_QWORD *)(v18 + 2072);
LABEL_25:
  v29 = *(_QWORD *)(a1 + 144);
  if ( *(_QWORD *)(v29 + 2072) < *(_QWORD *)(v29 + 2080)
    || tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), 1u) )
  {
    *(_BYTE *)(*(_QWORD *)(v29 + 2072))++ = *(_BYTE *)(a1 + 8);
  }
  v30 = *(_QWORD *)(a1 + 144);
  v31 = *(unsigned __int8 *)(a1 + 8);
  v32 = *(const void **)a1;
  if ( *(_QWORD *)(v30 + 2080) - *(_QWORD *)(v30 + 2072) < v31
    && !tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), *(unsigned __int8 *)(a1 + 8)) )
  {
    goto LABEL_48;
  }
  if ( v31 )
  {
    v33 = *(void **)(v30 + 2072);
    if ( !v33 )
      goto LABEL_45;
    v34 = *(_QWORD *)(v30 + 2080) - (_QWORD)v33;
    if ( v32 && v34 >= v31 )
    {
      memcpy_0(v33, v32, v31);
      goto LABEL_47;
    }
    memset_0(v33, 0, *(_QWORD *)(v30 + 2080) - (_QWORD)v33);
    if ( !v32 )
    {
LABEL_45:
      *(_DWORD *)_o__errno() = 22;
      goto LABEL_46;
    }
    if ( v34 < v31 )
    {
      *(_DWORD *)_o__errno() = 34;
LABEL_46:
      invalid_parameter_noinfo();
    }
  }
LABEL_47:
  *(_QWORD *)(v30 + 2072) += v31;
LABEL_48:
  *(_QWORD *)a1 = 0;
LABEL_49:
  v46 = *(_QWORD *)(a1 + 144);
  v47 = *(_QWORD *)(v46 + 2080);
  v48 = *(char **)(v46 + 2072);
  if ( (unsigned __int64)v48 >= v47 )
  {
    v49 = v47 - *(_QWORD *)(v46 + 2064);
    v50 = 1;
    if ( v49 > 1 )
      v50 = v49;
    v51 = 2 * v50;
    v52 = (char *)CoTaskMemAlloc(2 * v50);
    v53 = v52;
    if ( !v52 )
    {
      *(_BYTE *)(v46 + 8) = 1;
      goto LABEL_57;
    }
    v54 = *(const void **)(v46 + 2064);
    v55 = *(_QWORD *)(v46 + 2072) - (_QWORD)v54;
    memcpy_s_1(v52, v51, v54, v55);
    v56 = *(void **)v46;
    if ( *(_QWORD *)v46 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v61);
      CoTaskMemFree(v56);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v61);
    }
    *(_QWORD *)v46 = v53;
    v48 = &v53[v55];
    *(_QWORD *)(v46 + 2072) = &v53[v55];
    *(_QWORD *)(v46 + 2080) = &v53[v51];
    *(_QWORD *)(v46 + 2064) = v53;
  }
  *v48 = 16;
  ++*(_QWORD *)(v46 + 2072);
LABEL_57:
  v57 = *(tson::write_buffer **)(a1 + 144);
  if ( *((_QWORD *)v57 + 260) - *((_QWORD *)v57 + 259) >= 4u || tson::write_buffer::reserve(v57, 4u) )
  {
    v58 = (_DWORD *)*((_QWORD *)v57 + 259);
    if ( v58 )
    {
      v59 = *((_QWORD *)v57 + 260) - (_QWORD)v58;
      if ( v59 >= 4 )
      {
        *v58 = v5;
        goto LABEL_44;
      }
      memset_0(v58, 0, v59);
      *(_DWORD *)_o__errno() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
    }
    invalid_parameter_noinfo();
LABEL_44:
    *((_QWORD *)v57 + 259) += 4LL;
  }
}

```

## disassembly

```asm
0x180073574  push    rbx
0x180073576  push    rbp
0x180073577  push    rsi
0x180073578  push    rdi
0x180073579  push    r12
0x18007357b  push    r13
0x18007357d  push    r14
0x18007357f  push    r15
0x180073581  sub     rsp, 28h
0x180073585  mov     rax, [rdx]
0x180073588  lea     rsi, [rcx+18h]
0x18007358c  mov     r8b, [rdx+8]
0x180073590  xor     r12d, r12d
0x180073593  mov     [rcx], rax
0x180073596  mov     rdi, rcx
0x180073599  mov     [rcx+8], r8b
0x18007359d  mov     r15d, 1
0x1800735a3  mov     rax, [rdx+10h]
0x1800735a7  mov     r13d, [rax]
0x1800735aa  mov     rax, [rsi+68h]
0x1800735ae  test    rax, rax
0x1800735b1  jz      loc_1800739FF
0x1800735b7  lea     rsi, [rsi+rax*4]
0x1800735bb  add     rsi, 0FFFFFFFFFFFFFFFCh
0x1800735bf  cmp     dword ptr [rsi+4], 2
0x1800735c3  jz      loc_180073A07
0x1800735c9  cmp     [rsi+4], r12d
0x1800735cd  jnz     loc_180073678
0x1800735d3  mov     [rsi+4], r15d
0x1800735d7  mov     rbx, [rcx+90h]
0x1800735de  mov     rdx, [rbx+820h]
0x1800735e5  mov     rcx, [rbx+818h]
0x1800735ec  cmp     rcx, rdx
0x1800735ef  jb      short loc_18007366E
0x1800735f1  sub     rdx, [rbx+810h]
0x1800735f8  mov     rax, r15
0x1800735fb  cmp     rdx, r15
0x1800735fe  cmova   rax, rdx
0x180073602  lea     r15, [rax+rax]
0x180073606  mov     rcx, r15; cb
0x180073609  call    cs:__imp_CoTaskMemAlloc
0x18007360f  mov     rbp, rax
0x180073612  test    rax, rax
0x180073615  jz      loc_180073A66
0x18007361b  mov     r8, [rbx+810h]; Source
0x180073622  mov     rdx, r15; DestinationSize
0x180073625  mov     r14, [rbx+818h]
0x18007362c  mov     rcx, rax; Destination
0x18007362f  sub     r14, r8
0x180073632  mov     r9, r14; SourceSize
0x180073635  call    memcpy_s_1
0x18007363a  mov     r12, [rbx]
0x18007363d  test    r12, r12
0x180073640  jnz     loc_180073A44
0x180073646  mov     [rbx], rbp
0x180073649  lea     rax, [r15+rbp]
0x18007364d  xor     r12d, r12d
0x180073650  mov     [rbx+810h], rbp
0x180073657  lea     rcx, [r14+rbp]
0x18007365b  mov     [rbx+820h], rax
0x180073662  mov     [rbx+818h], rcx
0x180073669  lea     r15d, [r12+1]
0x18007366e  mov     [rcx], r15b
0x180073671  add     [rbx+818h], r15
0x180073678  mov     [rdi+10h], r12
0x18007367c  cmp     dword ptr [rsi+4], 3
0x180073680  jz      loc_1800738D7
0x180073686  test    r13d, r13d
0x180073689  jz      loc_1800737F5
0x18007368f  cmp     [rdi], r12
0x180073692  jz      loc_180073AA0
0x180073698  mov     rbx, [rdi+90h]
0x18007369f  mov     rax, [rbx+818h]
0x1800736a6  sub     rax, [rbx+810h]
0x1800736ad  mov     [rdi+10h], rax
0x1800736b1  mov     rdx, [rbx+820h]
0x1800736b8  mov     rcx, [rbx+818h]
0x1800736bf  cmp     rcx, rdx
0x1800736c2  jb      short loc_18007373F
0x1800736c4  sub     rdx, [rbx+810h]
0x1800736cb  mov     rax, r15
0x1800736ce  cmp     rdx, r15
0x1800736d1  cmova   rax, rdx
0x1800736d5  lea     r14, [rax+rax]
0x1800736d9  mov     rcx, r14; cb
0x1800736dc  call    cs:__imp_CoTaskMemAlloc
0x1800736e2  mov     rsi, rax
0x1800736e5  test    rax, rax
0x1800736e8  jz      loc_180073AD5
0x1800736ee  mov     r8, [rbx+810h]; Source
0x1800736f5  mov     rdx, r14; DestinationSize
0x1800736f8  mov     rbp, [rbx+818h]
0x1800736ff  mov     rcx, rax; Destination
0x180073702  sub     rbp, r8
0x180073705  mov     r9, rbp; SourceSize
0x180073708  call    memcpy_s_1
0x18007370d  mov     r15, [rbx]
0x180073710  test    r15, r15
0x180073713  jnz     loc_180073AB3
0x180073719  mov     [rbx], rsi
0x18007371c  lea     rcx, [rsi+rbp]
0x180073720  lea     rax, [r14+rsi]
0x180073724  mov     [rbx+818h], rcx
0x18007372b  mov     [rbx+820h], rax
0x180073732  mov     r15d, 1
0x180073738  mov     [rbx+810h], rsi
0x18007373f  mov     byte ptr [rcx], 5
0x180073742  add     [rbx+818h], r15
0x180073749  mov     rbx, [rdi+90h]
0x180073750  mov     rax, [rbx+820h]
0x180073757  cmp     [rbx+818h], rax
0x18007375e  jnb     loc_180073ADE
0x180073764  mov     rcx, [rbx+818h]
0x18007376b  mov     al, [rdi+8]
0x18007376e  mov     [rcx], al
0x180073770  add     [rbx+818h], r15
0x180073777  mov     rsi, [rdi+90h]
0x18007377e  movzx   ebx, byte ptr [rdi+8]
0x180073782  mov     r14, [rdi]
0x180073785  mov     rax, [rsi+820h]
0x18007378c  sub     rax, [rsi+818h]
0x180073793  cmp     rax, rbx
0x180073796  jb      loc_1800739E7
0x18007379c  test    rbx, rbx
0x18007379f  jz      loc_1800738CD
0x1800737a5  mov     rcx, [rsi+818h]; void *
0x1800737ac  test    rcx, rcx
0x1800737af  jz      loc_1800738BC
0x1800737b5  mov     rbp, [rsi+820h]
0x1800737bc  sub     rbp, rcx
0x1800737bf  test    r14, r14
0x1800737c2  jnz     loc_1800739BA
0x1800737c8  mov     r8, rbp; Size
0x1800737cb  xor     edx, edx; Val
0x1800737cd  call    memset_0
0x1800737d2  test    r14, r14
0x1800737d5  jz      loc_1800738BC
0x1800737db  cmp     rbp, rbx
0x1800737de  jnb     loc_1800738CD
0x1800737e4  call    cs:__imp__o__errno
0x1800737ea  mov     dword ptr [rax], 22h ; '"'
0x1800737f0  jmp     loc_1800738C8
0x1800737f5  mov     rbx, [rdi+90h]
0x1800737fc  mov     [rdi], r12
0x1800737ff  mov     rdx, [rbx+820h]
0x180073806  mov     rcx, [rbx+818h]
0x18007380d  cmp     rcx, rdx
0x180073810  jb      short loc_180073887
0x180073812  sub     rdx, [rbx+810h]
0x180073819  mov     rax, r15
0x18007381c  cmp     rdx, r15
0x18007381f  cmova   rax, rdx
0x180073823  lea     r14, [rax+rax]
0x180073827  mov     rcx, r14; cb
0x18007382a  call    cs:__imp_CoTaskMemAlloc
0x180073830  mov     rdi, rax
0x180073833  test    rax, rax
0x180073836  jz      loc_180073A97
0x18007383c  mov     r8, [rbx+810h]; Source
0x180073843  mov     rdx, r14; DestinationSize
0x180073846  mov     rsi, [rbx+818h]
0x18007384d  mov     rcx, rax; Destination
0x180073850  sub     rsi, r8
0x180073853  mov     r9, rsi; SourceSize
0x180073856  call    memcpy_s_1
0x18007385b  mov     rbp, [rbx]
0x18007385e  test    rbp, rbp
0x180073861  jnz     loc_180073A75
0x180073867  mov     [rbx], rdi
0x18007386a  lea     rcx, [rsi+rdi]
0x18007386e  lea     rax, [r14+rdi]
0x180073872  mov     [rbx+818h], rcx
0x180073879  mov     [rbx+820h], rax
0x180073880  mov     [rbx+810h], rdi
0x180073887  mov     byte ptr [rcx], 6
0x18007388a  add     [rbx+818h], r15
0x180073891  jmp     short loc_1800738AB
0x180073893  call    cs:__imp__o__errno
0x180073899  mov     dword ptr [rax], 16h
0x18007389f  call    _invalid_parameter_noinfo
0x1800738a4  add     [rbx+818h], rdi
0x1800738ab  add     rsp, 28h
0x1800738af  pop     r15
0x1800738b1  pop     r14
0x1800738b3  pop     r13
0x1800738b5  pop     r12
0x1800738b7  pop     rdi
0x1800738b8  pop     rsi
0x1800738b9  pop     rbp
0x1800738ba  pop     rbx
0x1800738bb  retn
0x1800738bc  call    cs:__imp__o__errno
0x1800738c2  mov     dword ptr [rax], 16h
0x1800738c8  call    _invalid_parameter_noinfo
0x1800738cd  add     [rsi+818h], rbx
0x1800738d4  mov     [rdi], r12
0x1800738d7  mov     rbx, [rdi+90h]
0x1800738de  mov     rdx, [rbx+820h]
0x1800738e5  mov     rcx, [rbx+818h]
0x1800738ec  cmp     rcx, rdx
0x1800738ef  jb      short loc_180073966
0x1800738f1  sub     rdx, [rbx+810h]
0x1800738f8  mov     rax, r15
0x1800738fb  cmp     rdx, r15
0x1800738fe  cmova   rax, rdx
0x180073902  lea     r14, [rax+rax]
0x180073906  mov     rcx, r14; cb
0x180073909  call    cs:__imp_CoTaskMemAlloc
0x18007390f  mov     rsi, rax
0x180073912  test    rax, rax
0x180073915  jz      loc_180073B18
0x18007391b  mov     r8, [rbx+810h]; Source
0x180073922  mov     rdx, r14; DestinationSize
0x180073925  mov     rbp, [rbx+818h]
0x18007392c  mov     rcx, rax; Destination
0x18007392f  sub     rbp, r8
0x180073932  mov     r9, rbp; SourceSize
0x180073935  call    memcpy_s_1
0x18007393a  mov     r15, [rbx]
0x18007393d  test    r15, r15
0x180073940  jnz     loc_180073AF6
0x180073946  mov     [rbx], rsi
0x180073949  lea     rcx, [rsi+rbp]
0x18007394d  lea     rax, [r14+rsi]
0x180073951  mov     [rbx+818h], rcx
0x180073958  mov     [rbx+820h], rax
0x18007395f  mov     [rbx+810h], rsi
0x180073966  mov     byte ptr [rcx], 10h
0x180073969  inc     qword ptr [rbx+818h]
0x180073970  mov     rbx, [rdi+90h]
0x180073977  mov     edi, 4
0x18007397c  mov     rax, [rbx+820h]
0x180073983  sub     rax, [rbx+818h]
0x18007398a  cmp     rax, rdi
0x18007398d  jb      short loc_1800739D3
0x18007398f  mov     rcx, [rbx+818h]; void *
0x180073996  test    rcx, rcx
0x180073999  jz      loc_180073893
0x18007399f  mov     r8, [rbx+820h]
0x1800739a6  sub     r8, rcx; Size
0x1800739a9  cmp     r8, rdi
0x1800739ac  jb      loc_180073B21
0x1800739b2  mov     [rcx], r13d
0x1800739b5  jmp     loc_1800738A4
0x1800739ba  cmp     rbp, rbx
0x1800739bd  jb      loc_1800737C8
0x1800739c3  mov     r8, rbx; Size
0x1800739c6  mov     rdx, r14; Src
0x1800739c9  call    memcpy_0
0x1800739ce  jmp     loc_1800738CD
0x1800739d3  mov     rdx, rdi; unsigned __int64
0x1800739d6  mov     rcx, rbx; this
0x1800739d9  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800739de  test    al, al
0x1800739e0  jnz     short loc_18007398F
0x1800739e2  jmp     loc_1800738AB
0x1800739e7  mov     rdx, rbx; unsigned __int64
0x1800739ea  mov     rcx, rsi; this
0x1800739ed  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800739f2  test    al, al
0x1800739f4  jnz     loc_18007379C
0x1800739fa  jmp     loc_1800738D4
0x1800739ff  mov     [rsi], r15b
0x180073a02  jmp     loc_1800735BF
0x180073a07  mov     dword ptr [rsi+4], 3
0x180073a0e  lea     rdx, [rsp+68h+arg_0]
0x180073a13  mov     rcx, [rcx+90h]
0x180073a1a  mov     [rsp+68h+arg_0], 3
0x180073a1f  call    ??$push_back@W4archive_marker@details@tson@@@write_buffer@tson@@QEAA_NAEBW4archive_marker@details@1@@Z; tson::write_buffer::push_back<tson::details::archive_marker>(tson::details::archive_marker const &)
0x180073a24  mov     rcx, [rdi+90h]; this
0x180073a2b  lea     rdx, [rdi+0Ah]; void *
0x180073a2f  mov     r8d, 2; unsigned __int64
0x180073a35  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x180073a3a  mov     [rdi+0Ah], r12w
0x180073a3f  jmp     loc_180073678
0x180073a44  lea     rcx, [rsp+68h+arg_0]; this
0x180073a49  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180073a4e  mov     rcx, r12; pv
0x180073a51  call    cs:__imp_CoTaskMemFree
0x180073a57  lea     rcx, [rsp+68h+arg_0]; this
0x180073a5c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180073a61  jmp     loc_180073646
0x180073a66  mov     r15d, 1
0x180073a6c  mov     [rbx+8], r15b
0x180073a70  jmp     loc_180073678
0x180073a75  lea     rcx, [rsp+68h+arg_0]; this
0x180073a7a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180073a7f  mov     rcx, rbp; pv
0x180073a82  call    cs:__imp_CoTaskMemFree
0x180073a88  lea     rcx, [rsp+68h+arg_0]; this
0x180073a8d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180073a92  jmp     loc_180073867
0x180073a97  mov     [rbx+8], r15b
0x180073a9b  jmp     loc_1800738AB
0x180073aa0  lea     rax, asc_180238410; "-"
0x180073aa7  mov     [rdi+8], r15b
0x180073aab  mov     [rdi], rax
0x180073aae  jmp     loc_180073698
0x180073ab3  lea     rcx, [rsp+68h+arg_0]; this
0x180073ab8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
  ... truncated ...
```
