# tson::output_archive::process<tson::nvp<int &>>(tson::nvp<int &> &&)

- ea: `0x180073b40`
- end: `0x180074105`
- name: `??$process@V?$nvp@AEAH@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAH@1@@Z`
- size: `1477`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180072364`
- `0x180072540`
- `0x180072764`
- `0x1800ead24`
- `0x1800eadb0`
- `0x1800f70cc`
- `0x18014dcd8`
- `0x18014dd64`

## callees

- `0x180073b40`
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

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180073db0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180073e5f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180073e88`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800740f4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180073db0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180073e5f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180073e88`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800740f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007401d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007404e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007408c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800740cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007401d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007404e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007408c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800740cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073bd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073ca8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073df6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073ed5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073bd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073ca8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073df6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073ed5`

## pseudocode

```c
void __fastcall tson::output_archive::process<tson::nvp<int &>>(__int64 a1, __int64 a2)
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
  *v48 = 15;
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
0x180073b40  push    rbx
0x180073b42  push    rbp
0x180073b43  push    rsi
0x180073b44  push    rdi
0x180073b45  push    r12
0x180073b47  push    r13
0x180073b49  push    r14
0x180073b4b  push    r15
0x180073b4d  sub     rsp, 28h
0x180073b51  mov     rax, [rdx]
0x180073b54  lea     rsi, [rcx+18h]
0x180073b58  mov     r8b, [rdx+8]
0x180073b5c  xor     r12d, r12d
0x180073b5f  mov     [rcx], rax
0x180073b62  mov     rdi, rcx
0x180073b65  mov     [rcx+8], r8b
0x180073b69  mov     r15d, 1
0x180073b6f  mov     rax, [rdx+10h]
0x180073b73  mov     r13d, [rax]
0x180073b76  mov     rax, [rsi+68h]
0x180073b7a  test    rax, rax
0x180073b7d  jz      loc_180073FCB
0x180073b83  lea     rsi, [rsi+rax*4]
0x180073b87  add     rsi, 0FFFFFFFFFFFFFFFCh
0x180073b8b  cmp     dword ptr [rsi+4], 2
0x180073b8f  jz      loc_180073FD3
0x180073b95  cmp     [rsi+4], r12d
0x180073b99  jnz     loc_180073C44
0x180073b9f  mov     [rsi+4], r15d
0x180073ba3  mov     rbx, [rcx+90h]
0x180073baa  mov     rdx, [rbx+820h]
0x180073bb1  mov     rcx, [rbx+818h]
0x180073bb8  cmp     rcx, rdx
0x180073bbb  jb      short loc_180073C3A
0x180073bbd  sub     rdx, [rbx+810h]
0x180073bc4  mov     rax, r15
0x180073bc7  cmp     rdx, r15
0x180073bca  cmova   rax, rdx
0x180073bce  lea     r15, [rax+rax]
0x180073bd2  mov     rcx, r15; cb
0x180073bd5  call    cs:__imp_CoTaskMemAlloc
0x180073bdb  mov     rbp, rax
0x180073bde  test    rax, rax
0x180073be1  jz      loc_180074032
0x180073be7  mov     r8, [rbx+810h]; Source
0x180073bee  mov     rdx, r15; DestinationSize
0x180073bf1  mov     r14, [rbx+818h]
0x180073bf8  mov     rcx, rax; Destination
0x180073bfb  sub     r14, r8
0x180073bfe  mov     r9, r14; SourceSize
0x180073c01  call    memcpy_s_1
0x180073c06  mov     r12, [rbx]
0x180073c09  test    r12, r12
0x180073c0c  jnz     loc_180074010
0x180073c12  mov     [rbx], rbp
0x180073c15  lea     rax, [r15+rbp]
0x180073c19  xor     r12d, r12d
0x180073c1c  mov     [rbx+810h], rbp
0x180073c23  lea     rcx, [r14+rbp]
0x180073c27  mov     [rbx+820h], rax
0x180073c2e  mov     [rbx+818h], rcx
0x180073c35  lea     r15d, [r12+1]
0x180073c3a  mov     [rcx], r15b
0x180073c3d  add     [rbx+818h], r15
0x180073c44  mov     [rdi+10h], r12
0x180073c48  cmp     dword ptr [rsi+4], 3
0x180073c4c  jz      loc_180073EA3
0x180073c52  test    r13d, r13d
0x180073c55  jz      loc_180073DC1
0x180073c5b  cmp     [rdi], r12
0x180073c5e  jz      loc_18007406C
0x180073c64  mov     rbx, [rdi+90h]
0x180073c6b  mov     rax, [rbx+818h]
0x180073c72  sub     rax, [rbx+810h]
0x180073c79  mov     [rdi+10h], rax
0x180073c7d  mov     rdx, [rbx+820h]
0x180073c84  mov     rcx, [rbx+818h]
0x180073c8b  cmp     rcx, rdx
0x180073c8e  jb      short loc_180073D0B
0x180073c90  sub     rdx, [rbx+810h]
0x180073c97  mov     rax, r15
0x180073c9a  cmp     rdx, r15
0x180073c9d  cmova   rax, rdx
0x180073ca1  lea     r14, [rax+rax]
0x180073ca5  mov     rcx, r14; cb
0x180073ca8  call    cs:__imp_CoTaskMemAlloc
0x180073cae  mov     rsi, rax
0x180073cb1  test    rax, rax
0x180073cb4  jz      loc_1800740A1
0x180073cba  mov     r8, [rbx+810h]; Source
0x180073cc1  mov     rdx, r14; DestinationSize
0x180073cc4  mov     rbp, [rbx+818h]
0x180073ccb  mov     rcx, rax; Destination
0x180073cce  sub     rbp, r8
0x180073cd1  mov     r9, rbp; SourceSize
0x180073cd4  call    memcpy_s_1
0x180073cd9  mov     r15, [rbx]
0x180073cdc  test    r15, r15
0x180073cdf  jnz     loc_18007407F
0x180073ce5  mov     [rbx], rsi
0x180073ce8  lea     rcx, [rsi+rbp]
0x180073cec  lea     rax, [r14+rsi]
0x180073cf0  mov     [rbx+818h], rcx
0x180073cf7  mov     [rbx+820h], rax
0x180073cfe  mov     r15d, 1
0x180073d04  mov     [rbx+810h], rsi
0x180073d0b  mov     byte ptr [rcx], 5
0x180073d0e  add     [rbx+818h], r15
0x180073d15  mov     rbx, [rdi+90h]
0x180073d1c  mov     rax, [rbx+820h]
0x180073d23  cmp     [rbx+818h], rax
0x180073d2a  jnb     loc_1800740AA
0x180073d30  mov     rcx, [rbx+818h]
0x180073d37  mov     al, [rdi+8]
0x180073d3a  mov     [rcx], al
0x180073d3c  add     [rbx+818h], r15
0x180073d43  mov     rsi, [rdi+90h]
0x180073d4a  movzx   ebx, byte ptr [rdi+8]
0x180073d4e  mov     r14, [rdi]
0x180073d51  mov     rax, [rsi+820h]
0x180073d58  sub     rax, [rsi+818h]
0x180073d5f  cmp     rax, rbx
0x180073d62  jb      loc_180073FB3
0x180073d68  test    rbx, rbx
0x180073d6b  jz      loc_180073E99
0x180073d71  mov     rcx, [rsi+818h]; void *
0x180073d78  test    rcx, rcx
0x180073d7b  jz      loc_180073E88
0x180073d81  mov     rbp, [rsi+820h]
0x180073d88  sub     rbp, rcx
0x180073d8b  test    r14, r14
0x180073d8e  jnz     loc_180073F86
0x180073d94  mov     r8, rbp; Size
0x180073d97  xor     edx, edx; Val
0x180073d99  call    memset_0
0x180073d9e  test    r14, r14
0x180073da1  jz      loc_180073E88
0x180073da7  cmp     rbp, rbx
0x180073daa  jnb     loc_180073E99
0x180073db0  call    cs:__imp__o__errno
0x180073db6  mov     dword ptr [rax], 22h ; '"'
0x180073dbc  jmp     loc_180073E94
0x180073dc1  mov     rbx, [rdi+90h]
0x180073dc8  mov     [rdi], r12
0x180073dcb  mov     rdx, [rbx+820h]
0x180073dd2  mov     rcx, [rbx+818h]
0x180073dd9  cmp     rcx, rdx
0x180073ddc  jb      short loc_180073E53
0x180073dde  sub     rdx, [rbx+810h]
0x180073de5  mov     rax, r15
0x180073de8  cmp     rdx, r15
0x180073deb  cmova   rax, rdx
0x180073def  lea     r14, [rax+rax]
0x180073df3  mov     rcx, r14; cb
0x180073df6  call    cs:__imp_CoTaskMemAlloc
0x180073dfc  mov     rdi, rax
0x180073dff  test    rax, rax
0x180073e02  jz      loc_180074063
0x180073e08  mov     r8, [rbx+810h]; Source
0x180073e0f  mov     rdx, r14; DestinationSize
0x180073e12  mov     rsi, [rbx+818h]
0x180073e19  mov     rcx, rax; Destination
0x180073e1c  sub     rsi, r8
0x180073e1f  mov     r9, rsi; SourceSize
0x180073e22  call    memcpy_s_1
0x180073e27  mov     rbp, [rbx]
0x180073e2a  test    rbp, rbp
0x180073e2d  jnz     loc_180074041
0x180073e33  mov     [rbx], rdi
0x180073e36  lea     rcx, [rsi+rdi]
0x180073e3a  lea     rax, [r14+rdi]
0x180073e3e  mov     [rbx+818h], rcx
0x180073e45  mov     [rbx+820h], rax
0x180073e4c  mov     [rbx+810h], rdi
0x180073e53  mov     byte ptr [rcx], 6
0x180073e56  add     [rbx+818h], r15
0x180073e5d  jmp     short loc_180073E77
0x180073e5f  call    cs:__imp__o__errno
0x180073e65  mov     dword ptr [rax], 16h
0x180073e6b  call    _invalid_parameter_noinfo
0x180073e70  add     [rbx+818h], rdi
0x180073e77  add     rsp, 28h
0x180073e7b  pop     r15
0x180073e7d  pop     r14
0x180073e7f  pop     r13
0x180073e81  pop     r12
0x180073e83  pop     rdi
0x180073e84  pop     rsi
0x180073e85  pop     rbp
0x180073e86  pop     rbx
0x180073e87  retn
0x180073e88  call    cs:__imp__o__errno
0x180073e8e  mov     dword ptr [rax], 16h
0x180073e94  call    _invalid_parameter_noinfo
0x180073e99  add     [rsi+818h], rbx
0x180073ea0  mov     [rdi], r12
0x180073ea3  mov     rbx, [rdi+90h]
0x180073eaa  mov     rdx, [rbx+820h]
0x180073eb1  mov     rcx, [rbx+818h]
0x180073eb8  cmp     rcx, rdx
0x180073ebb  jb      short loc_180073F32
0x180073ebd  sub     rdx, [rbx+810h]
0x180073ec4  mov     rax, r15
0x180073ec7  cmp     rdx, r15
0x180073eca  cmova   rax, rdx
0x180073ece  lea     r14, [rax+rax]
0x180073ed2  mov     rcx, r14; cb
0x180073ed5  call    cs:__imp_CoTaskMemAlloc
0x180073edb  mov     rsi, rax
0x180073ede  test    rax, rax
0x180073ee1  jz      loc_1800740E4
0x180073ee7  mov     r8, [rbx+810h]; Source
0x180073eee  mov     rdx, r14; DestinationSize
0x180073ef1  mov     rbp, [rbx+818h]
0x180073ef8  mov     rcx, rax; Destination
0x180073efb  sub     rbp, r8
0x180073efe  mov     r9, rbp; SourceSize
0x180073f01  call    memcpy_s_1
0x180073f06  mov     r15, [rbx]
0x180073f09  test    r15, r15
0x180073f0c  jnz     loc_1800740C2
0x180073f12  mov     [rbx], rsi
0x180073f15  lea     rcx, [rsi+rbp]
0x180073f19  lea     rax, [r14+rsi]
0x180073f1d  mov     [rbx+818h], rcx
0x180073f24  mov     [rbx+820h], rax
0x180073f2b  mov     [rbx+810h], rsi
0x180073f32  mov     byte ptr [rcx], 0Fh
0x180073f35  inc     qword ptr [rbx+818h]
0x180073f3c  mov     rbx, [rdi+90h]
0x180073f43  mov     edi, 4
0x180073f48  mov     rax, [rbx+820h]
0x180073f4f  sub     rax, [rbx+818h]
0x180073f56  cmp     rax, rdi
0x180073f59  jb      short loc_180073F9F
0x180073f5b  mov     rcx, [rbx+818h]; void *
0x180073f62  test    rcx, rcx
0x180073f65  jz      loc_180073E5F
0x180073f6b  mov     r8, [rbx+820h]
0x180073f72  sub     r8, rcx; Size
0x180073f75  cmp     r8, rdi
0x180073f78  jb      loc_1800740ED
0x180073f7e  mov     [rcx], r13d
0x180073f81  jmp     loc_180073E70
0x180073f86  cmp     rbp, rbx
0x180073f89  jb      loc_180073D94
0x180073f8f  mov     r8, rbx; Size
0x180073f92  mov     rdx, r14; Src
0x180073f95  call    memcpy_0
0x180073f9a  jmp     loc_180073E99
0x180073f9f  mov     rdx, rdi; unsigned __int64
0x180073fa2  mov     rcx, rbx; this
0x180073fa5  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180073faa  test    al, al
0x180073fac  jnz     short loc_180073F5B
0x180073fae  jmp     loc_180073E77
0x180073fb3  mov     rdx, rbx; unsigned __int64
0x180073fb6  mov     rcx, rsi; this
0x180073fb9  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180073fbe  test    al, al
0x180073fc0  jnz     loc_180073D68
0x180073fc6  jmp     loc_180073EA0
0x180073fcb  mov     [rsi], r15b
0x180073fce  jmp     loc_180073B8B
0x180073fd3  mov     dword ptr [rsi+4], 3
0x180073fda  lea     rdx, [rsp+68h+arg_0]
0x180073fdf  mov     rcx, [rcx+90h]
0x180073fe6  mov     [rsp+68h+arg_0], 3
0x180073feb  call    ??$push_back@W4archive_marker@details@tson@@@write_buffer@tson@@QEAA_NAEBW4archive_marker@details@1@@Z; tson::write_buffer::push_back<tson::details::archive_marker>(tson::details::archive_marker const &)
0x180073ff0  mov     rcx, [rdi+90h]; this
0x180073ff7  lea     rdx, [rdi+0Ah]; void *
0x180073ffb  mov     r8d, 2; unsigned __int64
0x180074001  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x180074006  mov     [rdi+0Ah], r12w
0x18007400b  jmp     loc_180073C44
0x180074010  lea     rcx, [rsp+68h+arg_0]; this
0x180074015  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007401a  mov     rcx, r12; pv
0x18007401d  call    cs:__imp_CoTaskMemFree
0x180074023  lea     rcx, [rsp+68h+arg_0]; this
0x180074028  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007402d  jmp     loc_180073C12
0x180074032  mov     r15d, 1
0x180074038  mov     [rbx+8], r15b
0x18007403c  jmp     loc_180073C44
0x180074041  lea     rcx, [rsp+68h+arg_0]; this
0x180074046  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007404b  mov     rcx, rbp; pv
0x18007404e  call    cs:__imp_CoTaskMemFree
0x180074054  lea     rcx, [rsp+68h+arg_0]; this
0x180074059  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007405e  jmp     loc_180073E33
0x180074063  mov     [rbx+8], r15b
0x180074067  jmp     loc_180073E77
0x18007406c  lea     rax, asc_180238410; "-"
0x180074073  mov     [rdi+8], r15b
0x180074077  mov     [rdi], rax
0x18007407a  jmp     loc_180073C64
0x18007407f  lea     rcx, [rsp+68h+arg_0]; this
0x180074084  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
  ... truncated ...
```
