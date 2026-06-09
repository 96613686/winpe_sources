# tson::output_archive::operator()<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x180071ca0`
- end: `0x18007235e`
- name: `??$?RAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@output_archive@tson@@QEAAAEAV01@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1726`
- prototype: `__int64 __fastcall(__int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180161220`

## callees

- `0x180071ca0`
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

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180071ee9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007201d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007208a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007216a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180071ee9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007201d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007208a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007216a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007222a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072253`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800722d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007222a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072253`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800722d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071d3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071e16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071f3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800720d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071d3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071e16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071f3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800720d3`

## pseudocode

```c
__int64 __fastcall tson::output_archive::operator()<std::string &>(__int64 a1, unsigned __int64 *a2)
{
  unsigned __int64 v2; // r12
  const void *v3; // r14
  __int64 v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rbx
  unsigned __int64 v8; // rdx
  char *v9; // rcx
  unsigned __int64 v10; // rdx
  __int64 v11; // rax
  char *v12; // rax
  char *v13; // r15
  const void *v14; // r8
  rsize_t v15; // r13
  rsize_t v16; // rax
  __int64 v17; // rbx
  unsigned __int64 v18; // rdx
  char *v19; // rcx
  unsigned __int64 v20; // rdx
  __int64 v21; // rax
  rsize_t v22; // r13
  char *v23; // rax
  char *v24; // rsi
  const void *v25; // r8
  rsize_t v26; // r15
  __int64 v27; // rbx
  __int64 v28; // rsi
  size_t v29; // rbx
  const void *v30; // r13
  void *v31; // rcx
  __int64 v32; // rbx
  unsigned __int64 v33; // rdx
  char *v34; // rcx
  unsigned __int64 v35; // rdx
  __int64 v36; // rax
  rsize_t v37; // r13
  char *v38; // rax
  char *v39; // rsi
  const void *v40; // r8
  rsize_t v41; // r15
  unsigned __int64 v42; // rcx
  __int64 v43; // rbx
  char v44; // si
  __int64 v45; // rbx
  void *v46; // rcx
  unsigned __int64 v48; // rsi
  __int64 v49; // rbx
  unsigned __int64 v50; // rdx
  char *v51; // rcx
  unsigned __int64 v52; // rdx
  __int64 v53; // rax
  rsize_t v54; // r15
  char *v55; // rax
  char *v56; // rsi
  const void *v57; // r8
  rsize_t v58; // r14
  void *v59; // r12
  size_t v60; // r15
  __int64 v61; // rcx
  char v62; // ah
  __int64 v63; // rcx
  rsize_t DestinationSize; // [rsp+80h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+48h] BYREF
  char v66; // [rsp+90h] [rbp+50h] BYREF

  v2 = a2[2];
  v3 = a2;
  if ( v2 )
  {
    if ( a2[3] > 0xF )
      v3 = (const void *)*a2;
  }
  else
  {
    v3 = 0;
  }
  v5 = a1 + 24;
  v6 = *(_QWORD *)(a1 + 128);
  if ( v6 )
    v5 = v5 + 4 * v6 - 4;
  else
    *(_BYTE *)v5 = 1;
  if ( *(_DWORD *)(v5 + 4) == 2 )
  {
    *(_DWORD *)(v5 + 4) = 3;
    v61 = *(_QWORD *)(a1 + 144);
    LOBYTE(DestinationSize) = 3;
    tson::write_buffer::push_back<enum tson::details::archive_marker>(v61, &DestinationSize);
    tson::write_buffer::push_back(*(tson::write_buffer **)(a1 + 144), (const void *)(a1 + 10), 2u);
    *(_WORD *)(a1 + 10) = 0;
  }
  else
  {
    if ( *(_DWORD *)(v5 + 4) )
      goto LABEL_15;
    *(_DWORD *)(v5 + 4) = 1;
    v7 = *(_QWORD *)(a1 + 144);
    v8 = *(_QWORD *)(v7 + 2080);
    v9 = *(char **)(v7 + 2072);
    if ( (unsigned __int64)v9 < v8 )
      goto LABEL_14;
    v10 = v8 - *(_QWORD *)(v7 + 2064);
    v11 = 1;
    if ( v10 > 1 )
      v11 = v10;
    DestinationSize = 2 * v11;
    v12 = (char *)CoTaskMemAlloc(2 * v11);
    v13 = v12;
    if ( v12 )
    {
      v14 = *(const void **)(v7 + 2064);
      v15 = *(_QWORD *)(v7 + 2072) - (_QWORD)v14;
      memcpy_s_1(v12, DestinationSize, v14, v15);
      pv = *(LPVOID *)v7;
      if ( pv )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v66);
        CoTaskMemFree(pv);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v66);
      }
      v16 = DestinationSize;
      v9 = &v13[v15];
      *(_QWORD *)v7 = v13;
      *(_QWORD *)(v7 + 2080) = &v13[v16];
      *(_QWORD *)(v7 + 2064) = v13;
      *(_QWORD *)(v7 + 2072) = &v13[v15];
LABEL_14:
      *v9 = 1;
      ++*(_QWORD *)(v7 + 2072);
      goto LABEL_15;
    }
    *(_BYTE *)(v7 + 8) = 1;
  }
LABEL_15:
  *(_QWORD *)(a1 + 16) = 0;
  if ( *(_DWORD *)(v5 + 4) == 3 )
    goto LABEL_36;
  if ( v3 )
  {
    if ( !*(_QWORD *)a1 )
    {
      *(_BYTE *)(a1 + 8) = 1;
      *(_QWORD *)a1 = "-";
    }
    v17 = *(_QWORD *)(a1 + 144);
    *(_QWORD *)(a1 + 16) = *(_QWORD *)(v17 + 2072) - *(_QWORD *)(v17 + 2064);
    v18 = *(_QWORD *)(v17 + 2080);
    v19 = *(char **)(v17 + 2072);
    if ( (unsigned __int64)v19 >= v18 )
    {
      v20 = v18 - *(_QWORD *)(v17 + 2064);
      v21 = 1;
      if ( v20 > 1 )
        v21 = v20;
      v22 = 2 * v21;
      v23 = (char *)CoTaskMemAlloc(2 * v21);
      v24 = v23;
      if ( !v23 )
      {
        *(_BYTE *)(v17 + 8) = 1;
        goto LABEL_27;
      }
      v25 = *(const void **)(v17 + 2064);
      v26 = *(_QWORD *)(v17 + 2072) - (_QWORD)v25;
      memcpy_s_1(v23, v22, v25, v26);
      DestinationSize = *(_QWORD *)v17;
      if ( DestinationSize )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&pv);
        CoTaskMemFree((LPVOID)DestinationSize);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&pv);
      }
      *(_QWORD *)v17 = v24;
      v19 = &v24[v26];
      *(_QWORD *)(v17 + 2072) = &v24[v26];
      *(_QWORD *)(v17 + 2080) = &v24[v22];
      *(_QWORD *)(v17 + 2064) = v24;
    }
    *v19 = 5;
    ++*(_QWORD *)(v17 + 2072);
LABEL_27:
    v27 = *(_QWORD *)(a1 + 144);
    if ( *(_QWORD *)(v27 + 2072) < *(_QWORD *)(v27 + 2080)
      || tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v27 + 2072))++ = *(_BYTE *)(a1 + 8);
    }
    v28 = *(_QWORD *)(a1 + 144);
    v29 = *(unsigned __int8 *)(a1 + 8);
    v30 = *(const void **)a1;
    if ( *(_QWORD *)(v28 + 2080) - *(_QWORD *)(v28 + 2072) < v29
      && !tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), *(unsigned __int8 *)(a1 + 8)) )
    {
      goto LABEL_35;
    }
    if ( v29 )
    {
      v31 = *(void **)(v28 + 2072);
      if ( !v31 )
        goto LABEL_32;
      v60 = *(_QWORD *)(v28 + 2080) - (_QWORD)v31;
      if ( v30 && v60 >= v29 )
      {
        memcpy_0(v31, v30, v29);
        goto LABEL_34;
      }
      memset_0(v31, 0, *(_QWORD *)(v28 + 2080) - (_QWORD)v31);
      if ( v30 )
      {
        if ( v60 >= v29 )
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
    *(_QWORD *)(v28 + 2072) += v29;
LABEL_35:
    *(_QWORD *)a1 = 0;
LABEL_36:
    v32 = *(_QWORD *)(a1 + 144);
    v33 = *(_QWORD *)(v32 + 2080);
    v34 = *(char **)(v32 + 2072);
    if ( (unsigned __int64)v34 >= v33 )
    {
      v35 = v33 - *(_QWORD *)(v32 + 2064);
      v36 = 1;
      if ( v35 > 1 )
        v36 = v35;
      v37 = 2 * v36;
      v38 = (char *)CoTaskMemAlloc(2 * v36);
      v39 = v38;
      if ( !v38 )
      {
        *(_BYTE *)(v32 + 8) = 1;
LABEL_44:
        v42 = v2 + 1;
        if ( v2 + 1 > 0x7F )
        {
          if ( v42 > 0x7FFF && *(int *)(a1 + 136) >= 0 )
            *(_DWORD *)(a1 + 136) = -2147483637;
          v62 = BYTE1(v42) | 0x80;
          LOBYTE(pv) = v2 + 1;
          v63 = *(_QWORD *)(a1 + 144);
          LOBYTE(DestinationSize) = v62;
          tson::write_buffer::push_back<unsigned char>(v63, &DestinationSize);
          tson::write_buffer::push_back<unsigned char>(*(_QWORD *)(a1 + 144), &pv);
        }
        else
        {
          v43 = *(_QWORD *)(a1 + 144);
          v44 = v3 != 0 ? v42 : 0;
          if ( *(_QWORD *)(v43 + 2072) < *(_QWORD *)(v43 + 2080)
            || tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), 1u) )
          {
            *(_BYTE *)(*(_QWORD *)(v43 + 2072))++ = v44;
          }
        }
        v45 = *(_QWORD *)(a1 + 144);
        if ( *(_QWORD *)(v45 + 2080) - *(_QWORD *)(v45 + 2072) < v2
          && !tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), v2) )
        {
          return a1;
        }
        if ( v2 )
        {
          v46 = *(void **)(v45 + 2072);
          if ( !v46 )
            goto LABEL_50;
          v48 = *(_QWORD *)(v45 + 2080) - (_QWORD)v46;
          if ( v3 && v48 >= v2 )
          {
            memcpy_0(v46, v3, v2);
            goto LABEL_52;
          }
          memset_0(v46, 0, *(_QWORD *)(v45 + 2080) - (_QWORD)v46);
          if ( v3 )
          {
            if ( v48 >= v2 )
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
        *(_QWORD *)(v45 + 2072) += v2;
        return a1;
      }
      v40 = *(const void **)(v32 + 2064);
      v41 = *(_QWORD *)(v32 + 2072) - (_QWORD)v40;
      memcpy_s_1(v38, v37, v40, v41);
      DestinationSize = *(_QWORD *)v32;
      if ( DestinationSize )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&pv);
        CoTaskMemFree((LPVOID)DestinationSize);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&pv);
      }
      *(_QWORD *)v32 = v39;
      v34 = &v39[v41];
      *(_QWORD *)(v32 + 2072) = &v39[v41];
      *(_QWORD *)(v32 + 2080) = &v39[v37];
      *(_QWORD *)(v32 + 2064) = v39;
    }
    *v34 = 23;
    ++*(_QWORD *)(v32 + 2072);
    goto LABEL_44;
  }
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
      return a1;
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
  return a1;
}

```

## disassembly

```asm
0x180071ca0  mov     [rsp-38h+arg_18], rbx
0x180071ca5  push    rbp
0x180071ca6  push    rsi
0x180071ca7  push    rdi
0x180071ca8  push    r12
0x180071caa  push    r13
0x180071cac  push    r14
0x180071cae  push    r15
0x180071cb0  mov     rbp, rsp
0x180071cb3  sub     rsp, 40h
0x180071cb7  mov     r12, [rdx+10h]
0x180071cbb  mov     r14, rdx
0x180071cbe  mov     rdi, rcx
0x180071cc1  test    r12, r12
0x180071cc4  jnz     loc_180072050
0x180071cca  xor     r14d, r14d
0x180071ccd  lea     rsi, [rcx+18h]
0x180071cd1  mov     rax, [rsi+68h]
0x180071cd5  test    rax, rax
0x180071cd8  jz      loc_1800721D9
0x180071cde  lea     rsi, [rsi+rax*4]
0x180071ce2  add     rsi, 0FFFFFFFFFFFFFFFCh
0x180071ce6  cmp     dword ptr [rsi+4], 2
0x180071cea  jz      loc_1800721E1
0x180071cf0  cmp     dword ptr [rsi+4], 0
0x180071cf4  jnz     loc_180071DAB
0x180071cfa  mov     dword ptr [rsi+4], 1
0x180071d01  mov     rbx, [rcx+90h]
0x180071d08  mov     rdx, [rbx+820h]
0x180071d0f  mov     rcx, [rbx+818h]
0x180071d16  cmp     rcx, rdx
0x180071d19  jb      loc_180071DA1
0x180071d1f  sub     rdx, [rbx+810h]
0x180071d26  mov     eax, 1
0x180071d2b  cmp     rdx, rax
0x180071d2e  cmova   rax, rdx
0x180071d32  add     rax, rax
0x180071d35  mov     rcx, rax; cb
0x180071d38  mov     [rbp+DestinationSize], rax
0x180071d3c  call    cs:__imp_CoTaskMemAlloc
0x180071d42  mov     r15, rax
0x180071d45  test    rax, rax
0x180071d48  jz      loc_18007223E
0x180071d4e  mov     r8, [rbx+810h]; Source
0x180071d55  mov     rcx, rax; Destination
0x180071d58  mov     r13, [rbx+818h]
0x180071d5f  mov     rdx, [rbp+DestinationSize]; DestinationSize
0x180071d63  sub     r13, r8
0x180071d66  mov     r9, r13; SourceSize
0x180071d69  call    memcpy_s_1
0x180071d6e  mov     rax, [rbx]
0x180071d71  mov     [rbp+pv], rax
0x180071d75  test    rax, rax
0x180071d78  jnz     loc_18007221D
0x180071d7e  mov     rax, [rbp+DestinationSize]
0x180071d82  lea     rcx, [r15+r13]
0x180071d86  mov     [rbx], r15
0x180071d89  add     rax, r15
0x180071d8c  mov     [rbx+820h], rax
0x180071d93  mov     [rbx+810h], r15
0x180071d9a  mov     [rbx+818h], rcx
0x180071da1  mov     byte ptr [rcx], 1
0x180071da4  inc     qword ptr [rbx+818h]
0x180071dab  mov     qword ptr [rdi+10h], 0
0x180071db3  cmp     dword ptr [rsi+4], 3
0x180071db7  jz      loc_180071F08
0x180071dbd  test    r14, r14
0x180071dc0  jz      loc_180072098
0x180071dc6  cmp     qword ptr [rdi], 0
0x180071dca  jz      loc_180072270
0x180071dd0  mov     rbx, [rdi+90h]
0x180071dd7  mov     rax, [rbx+818h]
0x180071dde  sub     rax, [rbx+810h]
0x180071de5  mov     [rdi+10h], rax
0x180071de9  mov     rdx, [rbx+820h]
0x180071df0  mov     rcx, [rbx+818h]
0x180071df7  cmp     rcx, rdx
0x180071dfa  jb      short loc_180071E77
0x180071dfc  sub     rdx, [rbx+810h]
0x180071e03  mov     eax, 1
0x180071e08  cmp     rdx, rax
0x180071e0b  cmova   rax, rdx
0x180071e0f  lea     r13, [rax+rax]
0x180071e13  mov     rcx, r13; cb
0x180071e16  call    cs:__imp_CoTaskMemAlloc
0x180071e1c  mov     rsi, rax
0x180071e1f  test    rax, rax
0x180071e22  jz      loc_1800722A4
0x180071e28  mov     r8, [rbx+810h]; Source
0x180071e2f  mov     rdx, r13; DestinationSize
0x180071e32  mov     r15, [rbx+818h]
0x180071e39  mov     rcx, rax; Destination
0x180071e3c  sub     r15, r8
0x180071e3f  mov     r9, r15; SourceSize
0x180071e42  call    memcpy_s_1
0x180071e47  mov     rax, [rbx]
0x180071e4a  mov     [rbp+DestinationSize], rax
0x180071e4e  test    rax, rax
0x180071e51  jnz     loc_180072283
0x180071e57  mov     [rbx], rsi
0x180071e5a  lea     rcx, [r15+rsi]
0x180071e5e  lea     rax, [rsi+r13]
0x180071e62  mov     [rbx+818h], rcx
0x180071e69  mov     [rbx+820h], rax
0x180071e70  mov     [rbx+810h], rsi
0x180071e77  mov     byte ptr [rcx], 5
0x180071e7a  inc     qword ptr [rbx+818h]
0x180071e81  mov     rbx, [rdi+90h]
0x180071e88  mov     rax, [rbx+820h]
0x180071e8f  cmp     [rbx+818h], rax
0x180071e96  jnb     loc_1800722AD
0x180071e9c  mov     rcx, [rbx+818h]
0x180071ea3  mov     al, [rdi+8]
0x180071ea6  mov     [rcx], al
0x180071ea8  inc     qword ptr [rbx+818h]
0x180071eaf  mov     rsi, [rdi+90h]
0x180071eb6  movzx   ebx, byte ptr [rdi+8]
0x180071eba  mov     r13, [rdi]
0x180071ebd  mov     rax, [rsi+820h]
0x180071ec4  sub     rax, [rsi+818h]
0x180071ecb  cmp     rax, rbx
0x180071ece  jb      loc_1800721C1
0x180071ed4  test    rbx, rbx
0x180071ed7  jz      short loc_180071EFA
0x180071ed9  mov     rcx, [rsi+818h]; void *
0x180071ee0  test    rcx, rcx
0x180071ee3  jnz     loc_18007213F
0x180071ee9  call    cs:__imp__o__errno
0x180071eef  mov     dword ptr [rax], 16h
0x180071ef5  call    _invalid_parameter_noinfo
0x180071efa  add     [rsi+818h], rbx
0x180071f01  mov     qword ptr [rdi], 0
0x180071f08  mov     rbx, [rdi+90h]
0x180071f0f  mov     rdx, [rbx+820h]
0x180071f16  mov     rcx, [rbx+818h]
0x180071f1d  cmp     rcx, rdx
0x180071f20  jb      short loc_180071F9D
0x180071f22  sub     rdx, [rbx+810h]
0x180071f29  mov     eax, 1
0x180071f2e  cmp     rdx, rax
0x180071f31  cmova   rax, rdx
0x180071f35  lea     r13, [rax+rax]
0x180071f39  mov     rcx, r13; cb
0x180071f3c  call    cs:__imp_CoTaskMemAlloc
0x180071f42  mov     rsi, rax
0x180071f45  test    rax, rax
0x180071f48  jz      loc_1800722E8
0x180071f4e  mov     r8, [rbx+810h]; Source
0x180071f55  mov     rdx, r13; DestinationSize
0x180071f58  mov     r15, [rbx+818h]
0x180071f5f  mov     rcx, rax; Destination
0x180071f62  sub     r15, r8
0x180071f65  mov     r9, r15; SourceSize
0x180071f68  call    memcpy_s_1
0x180071f6d  mov     rax, [rbx]
0x180071f70  mov     [rbp+DestinationSize], rax
0x180071f74  test    rax, rax
0x180071f77  jnz     loc_1800722C7
0x180071f7d  mov     [rbx], rsi
0x180071f80  lea     rcx, [r15+rsi]
0x180071f84  lea     rax, [rsi+r13]
0x180071f88  mov     [rbx+818h], rcx
0x180071f8f  mov     [rbx+820h], rax
0x180071f96  mov     [rbx+810h], rsi
0x180071f9d  mov     byte ptr [rcx], 17h
0x180071fa0  inc     qword ptr [rbx+818h]
0x180071fa7  lea     rcx, [r12+1]
0x180071fac  cmp     rcx, 7Fh
0x180071fb0  ja      loc_18007230B
0x180071fb6  mov     rbx, [rdi+90h]
0x180071fbd  mov     rax, r14
0x180071fc0  neg     rax
0x180071fc3  sbb     sil, sil
0x180071fc6  mov     rax, [rbx+820h]
0x180071fcd  and     sil, cl
0x180071fd0  cmp     [rbx+818h], rax
0x180071fd7  jnb     loc_1800722F1
0x180071fdd  mov     rax, [rbx+818h]
0x180071fe4  mov     [rax], sil
0x180071fe7  inc     qword ptr [rbx+818h]
0x180071fee  mov     rbx, [rdi+90h]
0x180071ff5  mov     rax, [rbx+820h]
0x180071ffc  sub     rax, [rbx+818h]
0x180072003  cmp     rax, r12
0x180072006  jb      loc_1800721A9
0x18007200c  test    r12, r12
0x18007200f  jz      short loc_18007202E
0x180072011  mov     rcx, [rbx+818h]; void *
0x180072018  test    rcx, rcx
0x18007201b  jnz     short loc_180072063
0x18007201d  call    cs:__imp__o__errno
0x180072023  mov     dword ptr [rax], 16h
0x180072029  call    _invalid_parameter_noinfo
0x18007202e  add     [rbx+818h], r12
0x180072035  mov     rbx, [rsp+40h+arg_18]
0x18007203d  mov     rax, rdi
0x180072040  add     rsp, 40h
0x180072044  pop     r15
0x180072046  pop     r14
0x180072048  pop     r13
0x18007204a  pop     r12
0x18007204c  pop     rdi
0x18007204d  pop     rsi
0x18007204e  pop     rbp
0x18007204f  retn
0x180072050  cmp     qword ptr [rdx+18h], 0Fh
0x180072055  jbe     loc_180071CCD
0x18007205b  mov     r14, [rdx]
0x18007205e  jmp     loc_180071CCD
0x180072063  mov     rsi, [rbx+820h]
0x18007206a  sub     rsi, rcx
0x18007206d  test    r14, r14
0x180072070  jnz     loc_18007217B
0x180072076  mov     r8, rsi; Size
0x180072079  xor     edx, edx; Val
0x18007207b  call    memset_0
0x180072080  test    r14, r14
0x180072083  jz      short loc_18007201D
0x180072085  cmp     rsi, r12
0x180072088  jnb     short loc_18007202E
0x18007208a  call    cs:__imp__o__errno
0x180072090  mov     dword ptr [rax], 22h ; '"'
0x180072096  jmp     short loc_180072029
0x180072098  mov     rbx, [rdi+90h]
0x18007209f  mov     qword ptr [rdi], 0
0x1800720a6  mov     rdx, [rbx+820h]
0x1800720ad  mov     rcx, [rbx+818h]
0x1800720b4  cmp     rcx, rdx
0x1800720b7  jb      short loc_180072130
0x1800720b9  sub     rdx, [rbx+810h]
0x1800720c0  mov     eax, 1
0x1800720c5  cmp     rdx, rax
0x1800720c8  cmova   rax, rdx
0x1800720cc  lea     r15, [rax+rax]
0x1800720d0  mov     rcx, r15; cb
0x1800720d3  call    cs:__imp_CoTaskMemAlloc
0x1800720d9  mov     rsi, rax
0x1800720dc  test    rax, rax
0x1800720df  jz      loc_180072267
0x1800720e5  mov     r8, [rbx+810h]; Source
0x1800720ec  mov     rdx, r15; DestinationSize
0x1800720ef  mov     r14, [rbx+818h]
0x1800720f6  mov     rcx, rax; Destination
0x1800720f9  sub     r14, r8
0x1800720fc  mov     r9, r14; SourceSize
0x1800720ff  call    memcpy_s_1
0x180072104  mov     r12, [rbx]
0x180072107  test    r12, r12
0x18007210a  jnz     loc_180072247
0x180072110  mov     [rbx], rsi
0x180072113  lea     rcx, [r14+rsi]
0x180072117  lea     rax, [r15+rsi]
0x18007211b  mov     [rbx+818h], rcx
0x180072122  mov     [rbx+820h], rax
0x180072129  mov     [rbx+810h], rsi
0x180072130  mov     byte ptr [rcx], 6
0x180072133  inc     qword ptr [rbx+818h]
0x18007213a  jmp     loc_180072035
0x18007213f  mov     r15, [rsi+820h]
0x180072146  sub     r15, rcx
0x180072149  test    r13, r13
0x18007214c  jnz     short loc_180072194
0x18007214e  mov     r8, r15; Size
0x180072151  xor     edx, edx; Val
0x180072153  call    memset_0
0x180072158  test    r13, r13
0x18007215b  jz      loc_180071EE9
0x180072161  cmp     r15, rbx
0x180072164  jnb     loc_180071EFA
0x18007216a  call    cs:__imp__o__errno
0x180072170  mov     dword ptr [rax], 22h ; '"'
0x180072176  jmp     loc_180071EF5
0x18007217b  cmp     rsi, r12
0x18007217e  jb      loc_180072076
0x180072184  mov     r8, r12; Size
0x180072187  mov     rdx, r14; Src
0x18007218a  call    memcpy_0
0x18007218f  jmp     loc_18007202E
0x180072194  cmp     r15, rbx
0x180072197  jb      short loc_18007214E
0x180072199  mov     r8, rbx; Size
0x18007219c  mov     rdx, r13; Src
0x18007219f  call    memcpy_0
0x1800721a4  jmp     loc_180071EFA
0x1800721a9  mov     rdx, r12; unsigned __int64
0x1800721ac  mov     rcx, rbx; this
0x1800721af  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800721b4  test    al, al
0x1800721b6  jnz     loc_18007200C
0x1800721bc  jmp     loc_180072035
0x1800721c1  mov     rdx, rbx; unsigned __int64
0x1800721c4  mov     rcx, rsi; this
0x1800721c7  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800721cc  test    al, al
0x1800721ce  jnz     loc_180071ED4
0x1800721d4  jmp     loc_180071F01
0x1800721d9  mov     byte ptr [rsi], 1
0x1800721dc  jmp     loc_180071CE6
0x1800721e1  mov     dword ptr [rsi+4], 3
0x1800721e8  lea     rdx, [rbp+DestinationSize]
  ... truncated ...
```
