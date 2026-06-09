# tson::output_archive::process<tson::nvp<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &>>(tson::nvp<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &> &&)

- ea: `0x180072ea4`
- end: `0x18007356e`
- name: `??$process@V?$nvp@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z`
- size: `1738`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180072364`
- `0x180072540`
- `0x180072764`
- `0x1800ead24`
- `0x1800f70cc`
- `0x180139744`
- `0x18014db04`
- `0x18014dcd8`
- `0x18014dd64`
- `0x180161220`
- `0x180176a80`
- `0x18018799c`
- `0x180198584`
- `0x1801ba46c`

## callees

- `0x180072ea4`
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

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800730fc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180073230`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007329a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007337a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800730fc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180073230`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007329a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007337a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007343a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073463`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800734a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800734e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007343a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073463`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800734a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800734e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180072f4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073029`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007314f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800732e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180072f4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073029`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007314f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800732e3`

## pseudocode

```c
void __fastcall tson::output_archive::process<tson::nvp<std::string &>>(__int64 a1, __int64 a2)
{
  char v2; // r8
  _QWORD *v4; // r14
  size_t v5; // r12
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rbx
  unsigned __int64 v9; // rdx
  char *v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 v12; // rax
  char *v13; // rax
  char *v14; // r15
  const void *v15; // r8
  rsize_t v16; // r13
  rsize_t v17; // rax
  __int64 v18; // rbx
  unsigned __int64 v19; // rdx
  char *v20; // rcx
  unsigned __int64 v21; // rdx
  __int64 v22; // rax
  rsize_t v23; // r13
  char *v24; // rax
  char *v25; // rsi
  const void *v26; // r8
  rsize_t v27; // r15
  __int64 v28; // rbx
  __int64 v29; // rsi
  size_t v30; // rbx
  const void *v31; // r13
  void *v32; // rcx
  __int64 v33; // rbx
  unsigned __int64 v34; // rdx
  char *v35; // rcx
  unsigned __int64 v36; // rdx
  __int64 v37; // rax
  rsize_t v38; // r13
  char *v39; // rax
  char *v40; // rsi
  const void *v41; // r8
  rsize_t v42; // r15
  unsigned __int64 v43; // rcx
  __int64 v44; // rbx
  char v45; // si
  __int64 v46; // rbx
  void *v47; // rcx
  size_t v48; // rdi
  __int64 v49; // rbx
  unsigned __int64 v50; // rdx
  char *v51; // rcx
  unsigned __int64 v52; // rdx
  __int64 v53; // rax
  rsize_t v54; // r14
  char *v55; // rax
  char *v56; // rdi
  const void *v57; // r8
  rsize_t v58; // rsi
  void *v59; // r15
  size_t v60; // r15
  __int64 v61; // rcx
  char v62; // ah
  __int64 v63; // rcx
  rsize_t DestinationSize; // [rsp+80h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+48h] BYREF
  char v66; // [rsp+90h] [rbp+50h] BYREF

  v2 = *(_BYTE *)(a2 + 8);
  *(_QWORD *)a1 = *(_QWORD *)a2;
  *(_BYTE *)(a1 + 8) = v2;
  v4 = *(_QWORD **)(a2 + 16);
  v5 = v4[2];
  if ( v5 )
  {
    if ( v4[3] > 0xFu )
      v4 = (_QWORD *)*v4;
  }
  else
  {
    v4 = 0;
  }
  v6 = a1 + 24;
  v7 = *(_QWORD *)(a1 + 128);
  if ( v7 )
    v6 = v6 + 4 * v7 - 4;
  else
    *(_BYTE *)v6 = 1;
  if ( *(_DWORD *)(v6 + 4) == 2 )
  {
    *(_DWORD *)(v6 + 4) = 3;
    v61 = *(_QWORD *)(a1 + 144);
    LOBYTE(DestinationSize) = 3;
    tson::write_buffer::push_back<enum tson::details::archive_marker>(v61, &DestinationSize);
    tson::write_buffer::push_back(*(tson::write_buffer **)(a1 + 144), (const void *)(a1 + 10), 2u);
    *(_WORD *)(a1 + 10) = 0;
  }
  else
  {
    if ( *(_DWORD *)(v6 + 4) )
      goto LABEL_15;
    *(_DWORD *)(v6 + 4) = 1;
    v8 = *(_QWORD *)(a1 + 144);
    v9 = *(_QWORD *)(v8 + 2080);
    v10 = *(char **)(v8 + 2072);
    if ( (unsigned __int64)v10 < v9 )
      goto LABEL_14;
    v11 = v9 - *(_QWORD *)(v8 + 2064);
    v12 = 1;
    if ( v11 > 1 )
      v12 = v11;
    DestinationSize = 2 * v12;
    v13 = (char *)CoTaskMemAlloc(2 * v12);
    v14 = v13;
    if ( v13 )
    {
      v15 = *(const void **)(v8 + 2064);
      v16 = *(_QWORD *)(v8 + 2072) - (_QWORD)v15;
      memcpy_s_1(v13, DestinationSize, v15, v16);
      pv = *(LPVOID *)v8;
      if ( pv )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v66);
        CoTaskMemFree(pv);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v66);
      }
      v17 = DestinationSize;
      v10 = &v14[v16];
      *(_QWORD *)v8 = v14;
      *(_QWORD *)(v8 + 2080) = &v14[v17];
      *(_QWORD *)(v8 + 2064) = v14;
      *(_QWORD *)(v8 + 2072) = &v14[v16];
LABEL_14:
      *v10 = 1;
      ++*(_QWORD *)(v8 + 2072);
      goto LABEL_15;
    }
    *(_BYTE *)(v8 + 8) = 1;
  }
LABEL_15:
  *(_QWORD *)(a1 + 16) = 0;
  if ( *(_DWORD *)(v6 + 4) == 3 )
    goto LABEL_36;
  if ( !v4 )
  {
    v49 = *(_QWORD *)(a1 + 144);
    *(_QWORD *)a1 = 0;
    v50 = *(_QWORD *)(v49 + 2080);
    v51 = *(char **)(v49 + 2072);
    if ( (unsigned __int64)v51 >= v50 )
    {
      v52 = v50 - *(_QWORD *)(v49 + 2064);
      v53 = 1;
      if ( v52 > 1 )
        v53 = v52;
      v54 = 2 * v53;
      v55 = (char *)CoTaskMemAlloc(2 * v53);
      v56 = v55;
      if ( !v55 )
      {
        *(_BYTE *)(v49 + 8) = 1;
        return;
      }
      v57 = *(const void **)(v49 + 2064);
      v58 = *(_QWORD *)(v49 + 2072) - (_QWORD)v57;
      memcpy_s_1(v55, v54, v57, v58);
      v59 = *(void **)v49;
      if ( *(_QWORD *)v49 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&DestinationSize);
        CoTaskMemFree(v59);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&DestinationSize);
      }
      *(_QWORD *)v49 = v56;
      v51 = &v56[v58];
      *(_QWORD *)(v49 + 2072) = &v56[v58];
      *(_QWORD *)(v49 + 2080) = &v56[v54];
      *(_QWORD *)(v49 + 2064) = v56;
    }
    *v51 = 6;
    ++*(_QWORD *)(v49 + 2072);
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
      goto LABEL_27;
    }
    v26 = *(const void **)(v18 + 2064);
    v27 = *(_QWORD *)(v18 + 2072) - (_QWORD)v26;
    memcpy_s_1(v24, v23, v26, v27);
    DestinationSize = *(_QWORD *)v18;
    if ( DestinationSize )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&pv);
      CoTaskMemFree((LPVOID)DestinationSize);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&pv);
    }
    *(_QWORD *)v18 = v25;
    v20 = &v25[v27];
    *(_QWORD *)(v18 + 2072) = &v25[v27];
    *(_QWORD *)(v18 + 2080) = &v25[v23];
    *(_QWORD *)(v18 + 2064) = v25;
  }
  *v20 = 5;
  ++*(_QWORD *)(v18 + 2072);
LABEL_27:
  v28 = *(_QWORD *)(a1 + 144);
  if ( *(_QWORD *)(v28 + 2072) < *(_QWORD *)(v28 + 2080)
    || tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), 1u) )
  {
    *(_BYTE *)(*(_QWORD *)(v28 + 2072))++ = *(_BYTE *)(a1 + 8);
  }
  v29 = *(_QWORD *)(a1 + 144);
  v30 = *(unsigned __int8 *)(a1 + 8);
  v31 = *(const void **)a1;
  if ( *(_QWORD *)(v29 + 2080) - *(_QWORD *)(v29 + 2072) < v30
    && !tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), *(unsigned __int8 *)(a1 + 8)) )
  {
    goto LABEL_35;
  }
  if ( v30 )
  {
    v32 = *(void **)(v29 + 2072);
    if ( !v32 )
      goto LABEL_32;
    v60 = *(_QWORD *)(v29 + 2080) - (_QWORD)v32;
    if ( v31 && v60 >= v30 )
    {
      memcpy_0(v32, v31, v30);
      goto LABEL_34;
    }
    memset_0(v32, 0, *(_QWORD *)(v29 + 2080) - (_QWORD)v32);
    if ( v31 )
    {
      if ( v60 >= v30 )
        goto LABEL_34;
      *(_DWORD *)_o__errno() = 34;
    }
    else
    {
LABEL_32:
      *(_DWORD *)_o__errno() = 22;
    }
    invalid_parameter_noinfo();
  }
LABEL_34:
  *(_QWORD *)(v29 + 2072) += v30;
LABEL_35:
  *(_QWORD *)a1 = 0;
LABEL_36:
  v33 = *(_QWORD *)(a1 + 144);
  v34 = *(_QWORD *)(v33 + 2080);
  v35 = *(char **)(v33 + 2072);
  if ( (unsigned __int64)v35 < v34 )
  {
LABEL_43:
    *v35 = 23;
    ++*(_QWORD *)(v33 + 2072);
    goto LABEL_44;
  }
  v36 = v34 - *(_QWORD *)(v33 + 2064);
  v37 = 1;
  if ( v36 > 1 )
    v37 = v36;
  v38 = 2 * v37;
  v39 = (char *)CoTaskMemAlloc(2 * v37);
  v40 = v39;
  if ( v39 )
  {
    v41 = *(const void **)(v33 + 2064);
    v42 = *(_QWORD *)(v33 + 2072) - (_QWORD)v41;
    memcpy_s_1(v39, v38, v41, v42);
    DestinationSize = *(_QWORD *)v33;
    if ( DestinationSize )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&pv);
      CoTaskMemFree((LPVOID)DestinationSize);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&pv);
    }
    *(_QWORD *)v33 = v40;
    v35 = &v40[v42];
    *(_QWORD *)(v33 + 2072) = &v40[v42];
    *(_QWORD *)(v33 + 2080) = &v40[v38];
    *(_QWORD *)(v33 + 2064) = v40;
    goto LABEL_43;
  }
  *(_BYTE *)(v33 + 8) = 1;
LABEL_44:
  v43 = v5 + 1;
  if ( v5 + 1 > 0x7F )
  {
    if ( v43 > 0x7FFF && *(int *)(a1 + 136) >= 0 )
      *(_DWORD *)(a1 + 136) = -2147483637;
    v62 = BYTE1(v43) | 0x80;
    LOBYTE(pv) = v5 + 1;
    v63 = *(_QWORD *)(a1 + 144);
    LOBYTE(DestinationSize) = v62;
    tson::write_buffer::push_back<unsigned char>(v63, &DestinationSize);
    tson::write_buffer::push_back<unsigned char>(*(_QWORD *)(a1 + 144), &pv);
  }
  else
  {
    v44 = *(_QWORD *)(a1 + 144);
    v45 = v4 != 0 ? v43 : 0;
    if ( *(_QWORD *)(v44 + 2072) < *(_QWORD *)(v44 + 2080)
      || tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v44 + 2072))++ = v45;
    }
  }
  v46 = *(_QWORD *)(a1 + 144);
  if ( *(_QWORD *)(v46 + 2080) - *(_QWORD *)(v46 + 2072) >= v5
    || tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), v5) )
  {
    if ( v5 )
    {
      v47 = *(void **)(v46 + 2072);
      if ( !v47 )
        goto LABEL_50;
      v48 = *(_QWORD *)(v46 + 2080) - (_QWORD)v47;
      if ( v4 && v48 >= v5 )
      {
        memcpy_0(v47, v4, v5);
        goto LABEL_52;
      }
      memset_0(v47, 0, *(_QWORD *)(v46 + 2080) - (_QWORD)v47);
      if ( v4 )
      {
        if ( v48 >= v5 )
          goto LABEL_52;
        *(_DWORD *)_o__errno() = 34;
      }
      else
      {
LABEL_50:
        *(_DWORD *)_o__errno() = 22;
      }
      invalid_parameter_noinfo();
    }
LABEL_52:
    *(_QWORD *)(v46 + 2072) += v5;
  }
}

```

## disassembly

```asm
0x180072ea4  mov     [rsp-38h+arg_18], rbx
0x180072ea9  push    rbp
0x180072eaa  push    rsi
0x180072eab  push    rdi
0x180072eac  push    r12
0x180072eae  push    r13
0x180072eb0  push    r14
0x180072eb2  push    r15
0x180072eb4  mov     rbp, rsp
0x180072eb7  sub     rsp, 40h
0x180072ebb  mov     r8b, [rdx+8]
0x180072ebf  mov     rdi, rcx
0x180072ec2  mov     rax, [rdx]
0x180072ec5  mov     [rcx], rax
0x180072ec8  mov     [rcx+8], r8b
0x180072ecc  mov     r14, [rdx+10h]
0x180072ed0  mov     r12, [r14+10h]
0x180072ed4  test    r12, r12
0x180072ed7  jnz     loc_180073260
0x180072edd  xor     r14d, r14d
0x180072ee0  lea     rsi, [rcx+18h]
0x180072ee4  mov     rax, [rsi+68h]
0x180072ee8  test    rax, rax
0x180072eeb  jz      loc_1800733E9
0x180072ef1  lea     rsi, [rsi+rax*4]
0x180072ef5  add     rsi, 0FFFFFFFFFFFFFFFCh
0x180072ef9  cmp     dword ptr [rsi+4], 2
0x180072efd  jz      loc_1800733F1
0x180072f03  cmp     dword ptr [rsi+4], 0
0x180072f07  jnz     loc_180072FBE
0x180072f0d  mov     dword ptr [rsi+4], 1
0x180072f14  mov     rbx, [rcx+90h]
0x180072f1b  mov     rdx, [rbx+820h]
0x180072f22  mov     rcx, [rbx+818h]
0x180072f29  cmp     rcx, rdx
0x180072f2c  jb      loc_180072FB4
0x180072f32  sub     rdx, [rbx+810h]
0x180072f39  mov     eax, 1
0x180072f3e  cmp     rdx, rax
0x180072f41  cmova   rax, rdx
0x180072f45  add     rax, rax
0x180072f48  mov     rcx, rax; cb
0x180072f4b  mov     [rbp+DestinationSize], rax
0x180072f4f  call    cs:__imp_CoTaskMemAlloc
0x180072f55  mov     r15, rax
0x180072f58  test    rax, rax
0x180072f5b  jz      loc_18007344E
0x180072f61  mov     r8, [rbx+810h]; Source
0x180072f68  mov     rcx, rax; Destination
0x180072f6b  mov     r13, [rbx+818h]
0x180072f72  mov     rdx, [rbp+DestinationSize]; DestinationSize
0x180072f76  sub     r13, r8
0x180072f79  mov     r9, r13; SourceSize
0x180072f7c  call    memcpy_s_1
0x180072f81  mov     rax, [rbx]
0x180072f84  mov     [rbp+pv], rax
0x180072f88  test    rax, rax
0x180072f8b  jnz     loc_18007342D
0x180072f91  mov     rax, [rbp+DestinationSize]
0x180072f95  lea     rcx, [r15+r13]
0x180072f99  mov     [rbx], r15
0x180072f9c  add     rax, r15
0x180072f9f  mov     [rbx+820h], rax
0x180072fa6  mov     [rbx+810h], r15
0x180072fad  mov     [rbx+818h], rcx
0x180072fb4  mov     byte ptr [rcx], 1
0x180072fb7  inc     qword ptr [rbx+818h]
0x180072fbe  mov     qword ptr [rdi+10h], 0
0x180072fc6  cmp     dword ptr [rsi+4], 3
0x180072fca  jz      loc_18007311B
0x180072fd0  test    r14, r14
0x180072fd3  jz      loc_1800732A8
0x180072fd9  cmp     qword ptr [rdi], 0
0x180072fdd  jz      loc_180073480
0x180072fe3  mov     rbx, [rdi+90h]
0x180072fea  mov     rax, [rbx+818h]
0x180072ff1  sub     rax, [rbx+810h]
0x180072ff8  mov     [rdi+10h], rax
0x180072ffc  mov     rdx, [rbx+820h]
0x180073003  mov     rcx, [rbx+818h]
0x18007300a  cmp     rcx, rdx
0x18007300d  jb      short loc_18007308A
0x18007300f  sub     rdx, [rbx+810h]
0x180073016  mov     eax, 1
0x18007301b  cmp     rdx, rax
0x18007301e  cmova   rax, rdx
0x180073022  lea     r13, [rax+rax]
0x180073026  mov     rcx, r13; cb
0x180073029  call    cs:__imp_CoTaskMemAlloc
0x18007302f  mov     rsi, rax
0x180073032  test    rax, rax
0x180073035  jz      loc_1800734B4
0x18007303b  mov     r8, [rbx+810h]; Source
0x180073042  mov     rdx, r13; DestinationSize
0x180073045  mov     r15, [rbx+818h]
0x18007304c  mov     rcx, rax; Destination
0x18007304f  sub     r15, r8
0x180073052  mov     r9, r15; SourceSize
0x180073055  call    memcpy_s_1
0x18007305a  mov     rax, [rbx]
0x18007305d  mov     [rbp+DestinationSize], rax
0x180073061  test    rax, rax
0x180073064  jnz     loc_180073493
0x18007306a  mov     [rbx], rsi
0x18007306d  lea     rcx, [r15+rsi]
0x180073071  lea     rax, [rsi+r13]
0x180073075  mov     [rbx+818h], rcx
0x18007307c  mov     [rbx+820h], rax
0x180073083  mov     [rbx+810h], rsi
0x18007308a  mov     byte ptr [rcx], 5
0x18007308d  inc     qword ptr [rbx+818h]
0x180073094  mov     rbx, [rdi+90h]
0x18007309b  mov     rax, [rbx+820h]
0x1800730a2  cmp     [rbx+818h], rax
0x1800730a9  jnb     loc_1800734BD
0x1800730af  mov     rcx, [rbx+818h]
0x1800730b6  mov     al, [rdi+8]
0x1800730b9  mov     [rcx], al
0x1800730bb  inc     qword ptr [rbx+818h]
0x1800730c2  mov     rsi, [rdi+90h]
0x1800730c9  movzx   ebx, byte ptr [rdi+8]
0x1800730cd  mov     r13, [rdi]
0x1800730d0  mov     rax, [rsi+820h]
0x1800730d7  sub     rax, [rsi+818h]
0x1800730de  cmp     rax, rbx
0x1800730e1  jb      loc_1800733D1
0x1800730e7  test    rbx, rbx
0x1800730ea  jz      short loc_18007310D
0x1800730ec  mov     rcx, [rsi+818h]; void *
0x1800730f3  test    rcx, rcx
0x1800730f6  jnz     loc_18007334F
0x1800730fc  call    cs:__imp__o__errno
0x180073102  mov     dword ptr [rax], 16h
0x180073108  call    _invalid_parameter_noinfo
0x18007310d  add     [rsi+818h], rbx
0x180073114  mov     qword ptr [rdi], 0
0x18007311b  mov     rbx, [rdi+90h]
0x180073122  mov     rdx, [rbx+820h]
0x180073129  mov     rcx, [rbx+818h]
0x180073130  cmp     rcx, rdx
0x180073133  jb      short loc_1800731B0
0x180073135  sub     rdx, [rbx+810h]
0x18007313c  mov     eax, 1
0x180073141  cmp     rdx, rax
0x180073144  cmova   rax, rdx
0x180073148  lea     r13, [rax+rax]
0x18007314c  mov     rcx, r13; cb
0x18007314f  call    cs:__imp_CoTaskMemAlloc
0x180073155  mov     rsi, rax
0x180073158  test    rax, rax
0x18007315b  jz      loc_1800734F8
0x180073161  mov     r8, [rbx+810h]; Source
0x180073168  mov     rdx, r13; DestinationSize
0x18007316b  mov     r15, [rbx+818h]
0x180073172  mov     rcx, rax; Destination
0x180073175  sub     r15, r8
0x180073178  mov     r9, r15; SourceSize
0x18007317b  call    memcpy_s_1
0x180073180  mov     rax, [rbx]
0x180073183  mov     [rbp+DestinationSize], rax
0x180073187  test    rax, rax
0x18007318a  jnz     loc_1800734D7
0x180073190  mov     [rbx], rsi
0x180073193  lea     rcx, [r15+rsi]
0x180073197  lea     rax, [rsi+r13]
0x18007319b  mov     [rbx+818h], rcx
0x1800731a2  mov     [rbx+820h], rax
0x1800731a9  mov     [rbx+810h], rsi
0x1800731b0  mov     byte ptr [rcx], 17h
0x1800731b3  inc     qword ptr [rbx+818h]
0x1800731ba  lea     rcx, [r12+1]
0x1800731bf  cmp     rcx, 7Fh
0x1800731c3  ja      loc_18007351B
0x1800731c9  mov     rbx, [rdi+90h]
0x1800731d0  mov     rax, r14
0x1800731d3  neg     rax
0x1800731d6  sbb     sil, sil
0x1800731d9  mov     rax, [rbx+820h]
0x1800731e0  and     sil, cl
0x1800731e3  cmp     [rbx+818h], rax
0x1800731ea  jnb     loc_180073501
0x1800731f0  mov     rax, [rbx+818h]
0x1800731f7  mov     [rax], sil
0x1800731fa  inc     qword ptr [rbx+818h]
0x180073201  mov     rbx, [rdi+90h]
0x180073208  mov     rax, [rbx+820h]
0x18007320f  sub     rax, [rbx+818h]
0x180073216  cmp     rax, r12
0x180073219  jb      loc_1800733B9
0x18007321f  test    r12, r12
0x180073222  jz      short loc_180073241
0x180073224  mov     rcx, [rbx+818h]; void *
0x18007322b  test    rcx, rcx
0x18007322e  jnz     short loc_180073273
0x180073230  call    cs:__imp__o__errno
0x180073236  mov     dword ptr [rax], 16h
0x18007323c  call    _invalid_parameter_noinfo
0x180073241  add     [rbx+818h], r12
0x180073248  mov     rbx, [rsp+40h+arg_18]
0x180073250  add     rsp, 40h
0x180073254  pop     r15
0x180073256  pop     r14
0x180073258  pop     r13
0x18007325a  pop     r12
0x18007325c  pop     rdi
0x18007325d  pop     rsi
0x18007325e  pop     rbp
0x18007325f  retn
0x180073260  cmp     qword ptr [r14+18h], 0Fh
0x180073265  jbe     loc_180072EE0
0x18007326b  mov     r14, [r14]
0x18007326e  jmp     loc_180072EE0
0x180073273  mov     rdi, [rbx+820h]
0x18007327a  sub     rdi, rcx
0x18007327d  test    r14, r14
0x180073280  jnz     loc_18007338B
0x180073286  mov     r8, rdi; Size
0x180073289  xor     edx, edx; Val
0x18007328b  call    memset_0
0x180073290  test    r14, r14
0x180073293  jz      short loc_180073230
0x180073295  cmp     rdi, r12
0x180073298  jnb     short loc_180073241
0x18007329a  call    cs:__imp__o__errno
0x1800732a0  mov     dword ptr [rax], 22h ; '"'
0x1800732a6  jmp     short loc_18007323C
0x1800732a8  mov     rbx, [rdi+90h]
0x1800732af  mov     qword ptr [rdi], 0
0x1800732b6  mov     rdx, [rbx+820h]
0x1800732bd  mov     rcx, [rbx+818h]
0x1800732c4  cmp     rcx, rdx
0x1800732c7  jb      short loc_180073340
0x1800732c9  sub     rdx, [rbx+810h]
0x1800732d0  mov     eax, 1
0x1800732d5  cmp     rdx, rax
0x1800732d8  cmova   rax, rdx
0x1800732dc  lea     r14, [rax+rax]
0x1800732e0  mov     rcx, r14; cb
0x1800732e3  call    cs:__imp_CoTaskMemAlloc
0x1800732e9  mov     rdi, rax
0x1800732ec  test    rax, rax
0x1800732ef  jz      loc_180073477
0x1800732f5  mov     r8, [rbx+810h]; Source
0x1800732fc  mov     rdx, r14; DestinationSize
0x1800732ff  mov     rsi, [rbx+818h]
0x180073306  mov     rcx, rax; Destination
0x180073309  sub     rsi, r8
0x18007330c  mov     r9, rsi; SourceSize
0x18007330f  call    memcpy_s_1
0x180073314  mov     r15, [rbx]
0x180073317  test    r15, r15
0x18007331a  jnz     loc_180073457
0x180073320  mov     [rbx], rdi
0x180073323  lea     rcx, [rsi+rdi]
0x180073327  lea     rax, [r14+rdi]
0x18007332b  mov     [rbx+818h], rcx
0x180073332  mov     [rbx+820h], rax
0x180073339  mov     [rbx+810h], rdi
0x180073340  mov     byte ptr [rcx], 6
0x180073343  inc     qword ptr [rbx+818h]
0x18007334a  jmp     loc_180073248
0x18007334f  mov     r15, [rsi+820h]
0x180073356  sub     r15, rcx
0x180073359  test    r13, r13
0x18007335c  jnz     short loc_1800733A4
0x18007335e  mov     r8, r15; Size
0x180073361  xor     edx, edx; Val
0x180073363  call    memset_0
0x180073368  test    r13, r13
0x18007336b  jz      loc_1800730FC
0x180073371  cmp     r15, rbx
0x180073374  jnb     loc_18007310D
0x18007337a  call    cs:__imp__o__errno
0x180073380  mov     dword ptr [rax], 22h ; '"'
0x180073386  jmp     loc_180073108
0x18007338b  cmp     rdi, r12
0x18007338e  jb      loc_180073286
0x180073394  mov     r8, r12; Size
0x180073397  mov     rdx, r14; Src
0x18007339a  call    memcpy_0
0x18007339f  jmp     loc_180073241
0x1800733a4  cmp     r15, rbx
0x1800733a7  jb      short loc_18007335E
0x1800733a9  mov     r8, rbx; Size
0x1800733ac  mov     rdx, r13; Src
0x1800733af  call    memcpy_0
0x1800733b4  jmp     loc_18007310D
0x1800733b9  mov     rdx, r12; unsigned __int64
0x1800733bc  mov     rcx, rbx; this
0x1800733bf  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800733c4  test    al, al
0x1800733c6  jnz     loc_18007321F
0x1800733cc  jmp     loc_180073248
0x1800733d1  mov     rdx, rbx; unsigned __int64
0x1800733d4  mov     rcx, rsi; this
0x1800733d7  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800733dc  test    al, al
0x1800733de  jnz     loc_1800730E7
0x1800733e4  jmp     loc_180073114
0x1800733e9  mov     byte ptr [rsi], 1
  ... truncated ...
```
