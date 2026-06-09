# tson::output_archive::write_value<uint>(bool,tson::details::archive_marker,uint)

- ea: `0x18007f784`
- end: `0x18007fd5d`
- name: `??$write_value@I@output_archive@tson@@AEAAX_NW4archive_marker@details@1@I@Z`
- size: `1497`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007f75c`

## callees

- `0x180074110`
- `0x1800741f4`
- `0x180077e10`
- `0x180077e30`
- `0x18007b050`
- `0x18007f784`
- `0x1800a6f3c`
- `0x180120bea`
- `0x180120c94`
- `0x180123882`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007f9fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007faae`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007fadb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007fd4c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007f9fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007faae`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007fadb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007fd4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fc75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fce4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fd27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fc75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fce4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fd27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f8f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fa45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fb2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f8f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fa45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fb2c`

## pseudocode

```c
void __fastcall tson::output_archive::write_value<unsigned int>(__int64 a1, char a2, char a3, int a4)
{
  __int64 v4; // rsi
  int v5; // r12d
  __int64 v6; // rax
  __int64 v9; // rbx
  unsigned __int64 v10; // rdx
  char *v11; // rcx
  unsigned __int64 v12; // rdx
  __int64 v13; // rax
  rsize_t v14; // r15
  char *v15; // rax
  char *v16; // rbp
  const void *v17; // r8
  rsize_t v18; // r14
  void *v19; // r12
  __int64 v20; // rbx
  unsigned __int64 v21; // rdx
  char *v22; // rcx
  unsigned __int64 v23; // rdx
  __int64 v24; // rax
  rsize_t v25; // r14
  char *v26; // rax
  char *v27; // rsi
  const void *v28; // r8
  rsize_t v29; // rbp
  void *v30; // r15
  __int64 v31; // rbx
  __int64 v32; // rsi
  size_t v33; // rbx
  const void *v34; // r14
  void *v35; // rcx
  size_t v36; // rbp
  __int64 v37; // rbx
  unsigned __int64 v38; // rdx
  char *v39; // rcx
  unsigned __int64 v40; // rdx
  __int64 v41; // rax
  rsize_t v42; // r14
  char *v43; // rax
  char *v44; // rdi
  const void *v45; // r8
  rsize_t v46; // rsi
  void *v47; // rbp
  __int64 v48; // rbx
  unsigned __int64 v49; // rdx
  char *v50; // rcx
  unsigned __int64 v51; // rdx
  __int64 v52; // rax
  rsize_t v53; // r14
  char *v54; // rax
  char *v55; // rsi
  const void *v56; // r8
  rsize_t v57; // rbp
  void *v58; // r15
  tson::write_buffer *v59; // rbx
  _DWORD *v60; // rcx
  size_t v61; // r8
  __int64 v62; // rcx
  char v63; // [rsp+60h] [rbp+8h] BYREF
  char v64; // [rsp+70h] [rbp+18h] BYREF
  int v65; // [rsp+78h] [rbp+20h]

  v65 = a4;
  v64 = a3;
  v4 = a1 + 24;
  v5 = a4;
  v6 = *(_QWORD *)(a1 + 128);
  if ( v6 )
    v4 = v4 + 4 * v6 - 4;
  else
    *(_BYTE *)v4 = 1;
  if ( *(_DWORD *)(v4 + 4) == 2 )
  {
    *(_DWORD *)(v4 + 4) = 3;
    v62 = *(_QWORD *)(a1 + 144);
    v64 = 3;
    tson::write_buffer::push_back<enum tson::details::archive_marker>(v62, &v64);
    tson::write_buffer::push_back(*(tson::write_buffer **)(a1 + 144), (const void *)(a1 + 10), 2u);
    *(_WORD *)(a1 + 10) = 0;
  }
  else
  {
    if ( *(_DWORD *)(v4 + 4) )
      goto LABEL_13;
    *(_DWORD *)(v4 + 4) = 1;
    v9 = *(_QWORD *)(a1 + 144);
    v10 = *(_QWORD *)(v9 + 2080);
    v11 = *(char **)(v9 + 2072);
    if ( (unsigned __int64)v11 < v10 )
      goto LABEL_12;
    v12 = v10 - *(_QWORD *)(v9 + 2064);
    v13 = 1;
    if ( v12 > 1 )
      v13 = v12;
    v14 = 2 * v13;
    v15 = (char *)CoTaskMemAlloc(2 * v13);
    v16 = v15;
    if ( v15 )
    {
      v17 = *(const void **)(v9 + 2064);
      v18 = *(_QWORD *)(v9 + 2072) - (_QWORD)v17;
      memcpy_s_1(v15, v14, v17, v18);
      v19 = *(void **)v9;
      if ( *(_QWORD *)v9 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v63);
        CoTaskMemFree(v19);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v63);
      }
      v5 = v65;
      *(_QWORD *)v9 = v16;
      v11 = &v16[v18];
      *(_QWORD *)(v9 + 2072) = &v16[v18];
      *(_QWORD *)(v9 + 2080) = &v16[v14];
      *(_QWORD *)(v9 + 2064) = v16;
LABEL_12:
      *v11 = 1;
      ++*(_QWORD *)(v9 + 2072);
      goto LABEL_13;
    }
    *(_BYTE *)(v9 + 8) = 1;
  }
LABEL_13:
  *(_QWORD *)(a1 + 16) = 0;
  if ( *(_DWORD *)(v4 + 4) == 3 )
    goto LABEL_49;
  if ( a2 )
  {
    v37 = *(_QWORD *)(a1 + 144);
    *(_QWORD *)a1 = 0;
    v38 = *(_QWORD *)(v37 + 2080);
    v39 = *(char **)(v37 + 2072);
    if ( (unsigned __int64)v39 >= v38 )
    {
      v40 = v38 - *(_QWORD *)(v37 + 2064);
      v41 = 1;
      if ( v40 > 1 )
        v41 = v40;
      v42 = 2 * v41;
      v43 = (char *)CoTaskMemAlloc(2 * v41);
      v44 = v43;
      if ( !v43 )
      {
        *(_BYTE *)(v37 + 8) = 1;
        return;
      }
      v45 = *(const void **)(v37 + 2064);
      v46 = *(_QWORD *)(v37 + 2072) - (_QWORD)v45;
      memcpy_s_1(v43, v42, v45, v46);
      v47 = *(void **)v37;
      if ( *(_QWORD *)v37 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v63);
        CoTaskMemFree(v47);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v63);
      }
      *(_QWORD *)v37 = v44;
      v39 = &v44[v46];
      *(_QWORD *)(v37 + 2072) = &v44[v46];
      *(_QWORD *)(v37 + 2080) = &v44[v42];
      *(_QWORD *)(v37 + 2064) = v44;
    }
    *v39 = 6;
    ++*(_QWORD *)(v37 + 2072);
    return;
  }
  if ( !*(_QWORD *)a1 )
  {
    *(_BYTE *)(a1 + 8) = 1;
    *(_QWORD *)a1 = "-";
  }
  v20 = *(_QWORD *)(a1 + 144);
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(v20 + 2072) - *(_QWORD *)(v20 + 2064);
  v21 = *(_QWORD *)(v20 + 2080);
  v22 = *(char **)(v20 + 2072);
  if ( (unsigned __int64)v22 >= v21 )
  {
    v23 = v21 - *(_QWORD *)(v20 + 2064);
    v24 = 1;
    if ( v23 > 1 )
      v24 = v23;
    v25 = 2 * v24;
    v26 = (char *)CoTaskMemAlloc(2 * v24);
    v27 = v26;
    if ( !v26 )
    {
      *(_BYTE *)(v20 + 8) = 1;
      goto LABEL_25;
    }
    v28 = *(const void **)(v20 + 2064);
    v29 = *(_QWORD *)(v20 + 2072) - (_QWORD)v28;
    memcpy_s_1(v26, v25, v28, v29);
    v30 = *(void **)v20;
    if ( *(_QWORD *)v20 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v63);
      CoTaskMemFree(v30);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v63);
    }
    *(_QWORD *)v20 = v27;
    v22 = &v27[v29];
    *(_QWORD *)(v20 + 2072) = &v27[v29];
    *(_QWORD *)(v20 + 2080) = &v27[v25];
    *(_QWORD *)(v20 + 2064) = v27;
  }
  *v22 = 5;
  ++*(_QWORD *)(v20 + 2072);
LABEL_25:
  v31 = *(_QWORD *)(a1 + 144);
  if ( *(_QWORD *)(v31 + 2072) < *(_QWORD *)(v31 + 2080)
    || tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), 1u) )
  {
    *(_BYTE *)(*(_QWORD *)(v31 + 2072))++ = *(_BYTE *)(a1 + 8);
  }
  v32 = *(_QWORD *)(a1 + 144);
  v33 = *(unsigned __int8 *)(a1 + 8);
  v34 = *(const void **)a1;
  if ( *(_QWORD *)(v32 + 2080) - *(_QWORD *)(v32 + 2072) < v33
    && !tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), *(unsigned __int8 *)(a1 + 8)) )
  {
    goto LABEL_48;
  }
  if ( v33 )
  {
    v35 = *(void **)(v32 + 2072);
    if ( !v35 )
      goto LABEL_45;
    v36 = *(_QWORD *)(v32 + 2080) - (_QWORD)v35;
    if ( v34 && v36 >= v33 )
    {
      memcpy_0(v35, v34, v33);
      goto LABEL_47;
    }
    memset_0(v35, 0, *(_QWORD *)(v32 + 2080) - (_QWORD)v35);
    if ( !v34 )
    {
LABEL_45:
      *(_DWORD *)_o__errno() = 22;
      goto LABEL_46;
    }
    if ( v36 < v33 )
    {
      *(_DWORD *)_o__errno() = 34;
LABEL_46:
      invalid_parameter_noinfo();
    }
  }
LABEL_47:
  *(_QWORD *)(v32 + 2072) += v33;
LABEL_48:
  *(_QWORD *)a1 = 0;
LABEL_49:
  v48 = *(_QWORD *)(a1 + 144);
  v49 = *(_QWORD *)(v48 + 2080);
  v50 = *(char **)(v48 + 2072);
  if ( (unsigned __int64)v50 >= v49 )
  {
    v51 = v49 - *(_QWORD *)(v48 + 2064);
    v52 = 1;
    if ( v51 > 1 )
      v52 = v51;
    v53 = 2 * v52;
    v54 = (char *)CoTaskMemAlloc(2 * v52);
    v55 = v54;
    if ( !v54 )
    {
      *(_BYTE *)(v48 + 8) = 1;
      goto LABEL_57;
    }
    v56 = *(const void **)(v48 + 2064);
    v57 = *(_QWORD *)(v48 + 2072) - (_QWORD)v56;
    memcpy_s_1(v54, v53, v56, v57);
    v58 = *(void **)v48;
    if ( *(_QWORD *)v48 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v63);
      CoTaskMemFree(v58);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v63);
    }
    *(_QWORD *)v48 = v55;
    v50 = &v55[v57];
    *(_QWORD *)(v48 + 2072) = &v55[v57];
    *(_QWORD *)(v48 + 2080) = &v55[v53];
    *(_QWORD *)(v48 + 2064) = v55;
  }
  *v50 = 16;
  ++*(_QWORD *)(v48 + 2072);
LABEL_57:
  v59 = *(tson::write_buffer **)(a1 + 144);
  if ( *((_QWORD *)v59 + 260) - *((_QWORD *)v59 + 259) >= 4u || tson::write_buffer::reserve(v59, 4u) )
  {
    v60 = (_DWORD *)*((_QWORD *)v59 + 259);
    if ( v60 )
    {
      v61 = *((_QWORD *)v59 + 260) - (_QWORD)v60;
      if ( v61 >= 4 )
      {
        *v60 = v5;
        goto LABEL_44;
      }
      memset_0(v60, 0, v61);
      *(_DWORD *)_o__errno() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
    }
    invalid_parameter_noinfo();
LABEL_44:
    *((_QWORD *)v59 + 259) += 4LL;
  }
}

```

## disassembly

```asm
0x18007f784  mov     [rsp+arg_8], rbx
0x18007f789  mov     [rsp+arg_18], r9d
0x18007f78e  mov     [rsp+arg_10], r8b
0x18007f793  push    rbp
0x18007f794  push    rsi
0x18007f795  push    rdi
0x18007f796  push    r12
0x18007f798  push    r13
0x18007f79a  push    r14
0x18007f79c  push    r15
0x18007f79e  sub     rsp, 20h
0x18007f7a2  lea     rsi, [rcx+18h]
0x18007f7a6  mov     r12d, r9d
0x18007f7a9  mov     rax, [rsi+68h]
0x18007f7ad  mov     r13b, dl
0x18007f7b0  mov     rdi, rcx
0x18007f7b3  mov     r15d, 1
0x18007f7b9  test    rax, rax
0x18007f7bc  jz      loc_18007FC22
0x18007f7c2  lea     rsi, [rsi+rax*4]
0x18007f7c6  add     rsi, 0FFFFFFFFFFFFFFFCh
0x18007f7ca  cmp     dword ptr [rsi+4], 2
0x18007f7ce  jz      loc_18007FC2A
0x18007f7d4  cmp     dword ptr [rsi+4], 0
0x18007f7d8  jnz     loc_18007F88A
0x18007f7de  mov     [rsi+4], r15d
0x18007f7e2  mov     rbx, [rcx+90h]
0x18007f7e9  mov     rdx, [rbx+820h]
0x18007f7f0  mov     rcx, [rbx+818h]
0x18007f7f7  cmp     rcx, rdx
0x18007f7fa  jb      loc_18007F880
0x18007f800  sub     rdx, [rbx+810h]
0x18007f807  mov     rax, r15
0x18007f80a  cmp     rdx, r15
0x18007f80d  cmova   rax, rdx
0x18007f811  lea     r15, [rax+rax]
0x18007f815  mov     rcx, r15; cb
0x18007f818  call    cs:__imp_CoTaskMemAlloc
0x18007f81e  mov     rbp, rax
0x18007f821  test    rax, rax
0x18007f824  jz      loc_18007FC8A
0x18007f82a  mov     r8, [rbx+810h]; Source
0x18007f831  mov     rdx, r15; DestinationSize
0x18007f834  mov     r14, [rbx+818h]
0x18007f83b  mov     rcx, rax; Destination
0x18007f83e  sub     r14, r8
0x18007f841  mov     r9, r14; SourceSize
0x18007f844  call    memcpy_s_1
0x18007f849  mov     r12, [rbx]
0x18007f84c  test    r12, r12
0x18007f84f  jnz     loc_18007FC68
0x18007f855  mov     r12d, [rsp+58h+arg_18]
0x18007f85a  lea     rax, [r15+rbp]
0x18007f85e  mov     [rbx], rbp
0x18007f861  lea     rcx, [r14+rbp]
0x18007f865  mov     [rbx+818h], rcx
0x18007f86c  mov     r15d, 1
0x18007f872  mov     [rbx+820h], rax
0x18007f879  mov     [rbx+810h], rbp
0x18007f880  mov     [rcx], r15b
0x18007f883  add     [rbx+818h], r15
0x18007f88a  mov     qword ptr [rdi+10h], 0
0x18007f892  cmp     dword ptr [rsi+4], 3
0x18007f896  jz      loc_18007FAFA
0x18007f89c  test    r13b, r13b
0x18007f89f  jnz     loc_18007FA0C
0x18007f8a5  cmp     qword ptr [rdi], 0
0x18007f8a9  jz      loc_18007FCC4
0x18007f8af  mov     rbx, [rdi+90h]
0x18007f8b6  mov     rax, [rbx+818h]
0x18007f8bd  sub     rax, [rbx+810h]
0x18007f8c4  mov     [rdi+10h], rax
0x18007f8c8  mov     rdx, [rbx+820h]
0x18007f8cf  mov     rcx, [rbx+818h]
0x18007f8d6  cmp     rcx, rdx
0x18007f8d9  jb      short loc_18007F956
0x18007f8db  sub     rdx, [rbx+810h]
0x18007f8e2  mov     rax, r15
0x18007f8e5  cmp     rdx, r15
0x18007f8e8  cmova   rax, rdx
0x18007f8ec  lea     r14, [rax+rax]
0x18007f8f0  mov     rcx, r14; cb
0x18007f8f3  call    cs:__imp_CoTaskMemAlloc
0x18007f8f9  mov     rsi, rax
0x18007f8fc  test    rax, rax
0x18007f8ff  jz      loc_18007FCF9
0x18007f905  mov     r8, [rbx+810h]; Source
0x18007f90c  mov     rdx, r14; DestinationSize
0x18007f90f  mov     rbp, [rbx+818h]
0x18007f916  mov     rcx, rax; Destination
0x18007f919  sub     rbp, r8
0x18007f91c  mov     r9, rbp; SourceSize
0x18007f91f  call    memcpy_s_1
0x18007f924  mov     r15, [rbx]
0x18007f927  test    r15, r15
0x18007f92a  jnz     loc_18007FCD7
0x18007f930  mov     [rbx], rsi
0x18007f933  lea     rcx, [rsi+rbp]
0x18007f937  lea     rax, [r14+rsi]
0x18007f93b  mov     [rbx+818h], rcx
0x18007f942  mov     [rbx+820h], rax
0x18007f949  mov     r15d, 1
0x18007f94f  mov     [rbx+810h], rsi
0x18007f956  mov     byte ptr [rcx], 5
0x18007f959  add     [rbx+818h], r15
0x18007f960  mov     rbx, [rdi+90h]
0x18007f967  mov     rax, [rbx+820h]
0x18007f96e  cmp     [rbx+818h], rax
0x18007f975  jnb     loc_18007FD02
0x18007f97b  mov     rcx, [rbx+818h]
0x18007f982  mov     al, [rdi+8]
0x18007f985  mov     [rcx], al
0x18007f987  add     [rbx+818h], r15
0x18007f98e  mov     rsi, [rdi+90h]
0x18007f995  movzx   ebx, byte ptr [rdi+8]
0x18007f999  mov     r14, [rdi]
0x18007f99c  mov     rax, [rsi+820h]
0x18007f9a3  sub     rax, [rsi+818h]
0x18007f9aa  cmp     rax, rbx
0x18007f9ad  jb      loc_18007FC0A
0x18007f9b3  test    rbx, rbx
0x18007f9b6  jz      loc_18007FAEC
0x18007f9bc  mov     rcx, [rsi+818h]; void *
0x18007f9c3  test    rcx, rcx
0x18007f9c6  jz      loc_18007FADB
0x18007f9cc  mov     rbp, [rsi+820h]
0x18007f9d3  sub     rbp, rcx
0x18007f9d6  test    r14, r14
0x18007f9d9  jnz     loc_18007FBDD
0x18007f9df  mov     r8, rbp; Size
0x18007f9e2  xor     edx, edx; Val
0x18007f9e4  call    memset_0
0x18007f9e9  test    r14, r14
0x18007f9ec  jz      loc_18007FADB
0x18007f9f2  cmp     rbp, rbx
0x18007f9f5  jnb     loc_18007FAEC
0x18007f9fb  call    cs:__imp__o__errno
0x18007fa01  mov     dword ptr [rax], 22h ; '"'
0x18007fa07  jmp     loc_18007FAE7
0x18007fa0c  mov     rbx, [rdi+90h]
0x18007fa13  mov     qword ptr [rdi], 0
0x18007fa1a  mov     rdx, [rbx+820h]
0x18007fa21  mov     rcx, [rbx+818h]
0x18007fa28  cmp     rcx, rdx
0x18007fa2b  jb      short loc_18007FAA2
0x18007fa2d  sub     rdx, [rbx+810h]
0x18007fa34  mov     rax, r15
0x18007fa37  cmp     rdx, r15
0x18007fa3a  cmova   rax, rdx
0x18007fa3e  lea     r14, [rax+rax]
0x18007fa42  mov     rcx, r14; cb
0x18007fa45  call    cs:__imp_CoTaskMemAlloc
0x18007fa4b  mov     rdi, rax
0x18007fa4e  test    rax, rax
0x18007fa51  jz      loc_18007FCBB
0x18007fa57  mov     r8, [rbx+810h]; Source
0x18007fa5e  mov     rdx, r14; DestinationSize
0x18007fa61  mov     rsi, [rbx+818h]
0x18007fa68  mov     rcx, rax; Destination
0x18007fa6b  sub     rsi, r8
0x18007fa6e  mov     r9, rsi; SourceSize
0x18007fa71  call    memcpy_s_1
0x18007fa76  mov     rbp, [rbx]
0x18007fa79  test    rbp, rbp
0x18007fa7c  jnz     loc_18007FC99
0x18007fa82  mov     [rbx], rdi
0x18007fa85  lea     rcx, [rdi+rsi]
0x18007fa89  lea     rax, [r14+rdi]
0x18007fa8d  mov     [rbx+818h], rcx
0x18007fa94  mov     [rbx+820h], rax
0x18007fa9b  mov     [rbx+810h], rdi
0x18007faa2  mov     byte ptr [rcx], 6
0x18007faa5  add     [rbx+818h], r15
0x18007faac  jmp     short loc_18007FAC6
0x18007faae  call    cs:__imp__o__errno
0x18007fab4  mov     dword ptr [rax], 16h
0x18007faba  call    _invalid_parameter_noinfo
0x18007fabf  add     [rbx+818h], rdi
0x18007fac6  mov     rbx, [rsp+58h+arg_8]
0x18007facb  add     rsp, 20h
0x18007facf  pop     r15
0x18007fad1  pop     r14
0x18007fad3  pop     r13
0x18007fad5  pop     r12
0x18007fad7  pop     rdi
0x18007fad8  pop     rsi
0x18007fad9  pop     rbp
0x18007fada  retn
0x18007fadb  call    cs:__imp__o__errno
0x18007fae1  mov     dword ptr [rax], 16h
0x18007fae7  call    _invalid_parameter_noinfo
0x18007faec  add     [rsi+818h], rbx
0x18007faf3  mov     qword ptr [rdi], 0
0x18007fafa  mov     rbx, [rdi+90h]
0x18007fb01  mov     rdx, [rbx+820h]
0x18007fb08  mov     rcx, [rbx+818h]
0x18007fb0f  cmp     rcx, rdx
0x18007fb12  jb      short loc_18007FB89
0x18007fb14  sub     rdx, [rbx+810h]
0x18007fb1b  mov     rax, r15
0x18007fb1e  cmp     rdx, r15
0x18007fb21  cmova   rax, rdx
0x18007fb25  lea     r14, [rax+rax]
0x18007fb29  mov     rcx, r14; cb
0x18007fb2c  call    cs:__imp_CoTaskMemAlloc
0x18007fb32  mov     rsi, rax
0x18007fb35  test    rax, rax
0x18007fb38  jz      loc_18007FD3C
0x18007fb3e  mov     r8, [rbx+810h]; Source
0x18007fb45  mov     rdx, r14; DestinationSize
0x18007fb48  mov     rbp, [rbx+818h]
0x18007fb4f  mov     rcx, rax; Destination
0x18007fb52  sub     rbp, r8
0x18007fb55  mov     r9, rbp; SourceSize
0x18007fb58  call    memcpy_s_1
0x18007fb5d  mov     r15, [rbx]
0x18007fb60  test    r15, r15
0x18007fb63  jnz     loc_18007FD1A
0x18007fb69  mov     [rbx], rsi
0x18007fb6c  lea     rcx, [rsi+rbp]
0x18007fb70  lea     rax, [r14+rsi]
0x18007fb74  mov     [rbx+818h], rcx
0x18007fb7b  mov     [rbx+820h], rax
0x18007fb82  mov     [rbx+810h], rsi
0x18007fb89  mov     byte ptr [rcx], 10h
0x18007fb8c  inc     qword ptr [rbx+818h]
0x18007fb93  mov     rbx, [rdi+90h]
0x18007fb9a  mov     edi, 4
0x18007fb9f  mov     rax, [rbx+820h]
0x18007fba6  sub     rax, [rbx+818h]
0x18007fbad  cmp     rax, rdi
0x18007fbb0  jb      short loc_18007FBF6
0x18007fbb2  mov     rcx, [rbx+818h]; void *
0x18007fbb9  test    rcx, rcx
0x18007fbbc  jz      loc_18007FAAE
0x18007fbc2  mov     r8, [rbx+820h]
0x18007fbc9  sub     r8, rcx; Size
0x18007fbcc  cmp     r8, rdi
0x18007fbcf  jb      loc_18007FD45
0x18007fbd5  mov     [rcx], r12d
0x18007fbd8  jmp     loc_18007FABF
0x18007fbdd  cmp     rbp, rbx
0x18007fbe0  jb      loc_18007F9DF
0x18007fbe6  mov     r8, rbx; Size
0x18007fbe9  mov     rdx, r14; Src
0x18007fbec  call    memcpy_0
0x18007fbf1  jmp     loc_18007FAEC
0x18007fbf6  mov     rdx, rdi; unsigned __int64
0x18007fbf9  mov     rcx, rbx; this
0x18007fbfc  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18007fc01  test    al, al
0x18007fc03  jnz     short loc_18007FBB2
0x18007fc05  jmp     loc_18007FAC6
0x18007fc0a  mov     rdx, rbx; unsigned __int64
0x18007fc0d  mov     rcx, rsi; this
0x18007fc10  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18007fc15  test    al, al
0x18007fc17  jnz     loc_18007F9B3
0x18007fc1d  jmp     loc_18007FAF3
0x18007fc22  mov     [rsi], r15b
0x18007fc25  jmp     loc_18007F7CA
0x18007fc2a  mov     dword ptr [rsi+4], 3
0x18007fc31  lea     rdx, [rsp+58h+arg_10]
0x18007fc36  mov     rcx, [rcx+90h]
0x18007fc3d  mov     [rsp+58h+arg_10], 3
0x18007fc42  call    ??$push_back@W4archive_marker@details@tson@@@write_buffer@tson@@QEAA_NAEBW4archive_marker@details@1@@Z; tson::write_buffer::push_back<tson::details::archive_marker>(tson::details::archive_marker const &)
0x18007fc47  mov     rcx, [rdi+90h]; this
0x18007fc4e  lea     rdx, [rdi+0Ah]; void *
0x18007fc52  mov     r8d, 2; unsigned __int64
0x18007fc58  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x18007fc5d  xor     eax, eax
0x18007fc5f  mov     [rdi+0Ah], ax
0x18007fc63  jmp     loc_18007F88A
0x18007fc68  lea     rcx, [rsp+58h+arg_0]; this
0x18007fc6d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007fc72  mov     rcx, r12; pv
0x18007fc75  call    cs:__imp_CoTaskMemFree
0x18007fc7b  lea     rcx, [rsp+58h+arg_0]; this
0x18007fc80  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007fc85  jmp     loc_18007F855
0x18007fc8a  mov     r15d, 1
0x18007fc90  mov     [rbx+8], r15b
0x18007fc94  jmp     loc_18007F88A
0x18007fc99  lea     rcx, [rsp+58h+arg_0]; this
0x18007fc9e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007fca3  mov     rcx, rbp; pv
0x18007fca6  call    cs:__imp_CoTaskMemFree
0x18007fcac  lea     rcx, [rsp+58h+arg_0]; this
0x18007fcb1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007fcb6  jmp     loc_18007FA82
0x18007fcbb  mov     [rbx+8], r15b
0x18007fcbf  jmp     loc_18007FAC6
0x18007fcc4  lea     rax, asc_180238410; "-"
0x18007fccb  mov     [rdi+8], r15b
0x18007fccf  mov     [rdi], rax
0x18007fcd2  jmp     loc_18007F8AF
0x18007fcd7  lea     rcx, [rsp+58h+arg_0]; this
0x18007fcdc  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007fce1  mov     rcx, r15; pv
0x18007fce4  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
