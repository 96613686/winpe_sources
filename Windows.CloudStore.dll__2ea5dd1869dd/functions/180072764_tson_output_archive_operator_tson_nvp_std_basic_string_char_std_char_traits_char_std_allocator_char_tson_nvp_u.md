# tson::output_archive::operator()<tson::nvp<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &>,tson::nvp<uint &>,tson::nvp<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &>,tson::nvp<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &>,tson::nvp<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &>,tson::nvp<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &>,tson::nvp<uint &>,tson::nvp<int &>>(tson::nvp<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &> &&,tson::nvp<uint &> &&,tson::nvp<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &> &&,tson::nvp<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &> &&,tson::nvp<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &> &&,tson::nvp<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &> &&,tson::nvp<uint &> &&,tson::nvp<int &> &&)

- ea: `0x180072764`
- end: `0x180072e9e`
- name: `??$?RV?$nvp@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@tson@@V?$nvp@AEAI@1@V01@V01@V01@V01@V21@V?$nvp@AEAH@1@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@$$QEAV?$nvp@AEAI@1@00001$$QEAV?$nvp@AEAH@1@@Z`
- size: `1850`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180161db0`
- `0x18016245c`

## callees

- `0x180072764`
- `0x180072ea4`
- `0x180073574`
- `0x180073b40`
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

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800729f5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180072abd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180072b43`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180072caa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800729f5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180072abd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180072b43`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180072caa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072d6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072d93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072e14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072d6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072d93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072e14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180072815`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800728ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180072a54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180072b96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180072815`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800728ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180072a54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180072b96`

## pseudocode

```c
__int64 __fastcall tson::output_archive::operator()<tson::nvp<std::string &>,tson::nvp<unsigned int &>,tson::nvp<std::string &>,tson::nvp<std::string &>,tson::nvp<std::string &>,tson::nvp<std::string &>,tson::nvp<unsigned int &>,tson::nvp<int &>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  char v9; // r10
  _QWORD *v11; // r15
  unsigned __int64 v12; // r12
  __int64 v13; // rsi
  __int64 v14; // rax
  __int64 v15; // rbx
  unsigned __int64 v16; // rdx
  char *v17; // rcx
  unsigned __int64 v18; // rdx
  __int64 v19; // rax
  char *v20; // rax
  char *v21; // r14
  const void *v22; // r8
  rsize_t v23; // r13
  rsize_t v24; // rax
  __int64 v25; // rbx
  unsigned __int64 v26; // rdx
  char *v27; // rcx
  unsigned __int64 v28; // rdx
  __int64 v29; // rax
  rsize_t v30; // r13
  char *v31; // rax
  char *v32; // rsi
  const void *v33; // r8
  rsize_t v34; // r14
  __int64 v35; // rbx
  __int64 v36; // rsi
  size_t v37; // rbx
  const void *v38; // r13
  void *v39; // rcx
  size_t v40; // r14
  __int64 v41; // rbx
  unsigned __int64 v42; // rdx
  char *v43; // rcx
  unsigned __int64 v44; // rdx
  __int64 v45; // rax
  rsize_t v46; // r15
  char *v47; // rax
  char *v48; // rsi
  const void *v49; // r8
  rsize_t v50; // r14
  void *v51; // r12
  __int64 v53; // rbx
  unsigned __int64 v54; // rdx
  char *v55; // rcx
  unsigned __int64 v56; // rdx
  __int64 v57; // rax
  rsize_t v58; // r13
  char *v59; // rax
  char *v60; // rsi
  const void *v61; // r8
  rsize_t v62; // r14
  unsigned __int64 v63; // rcx
  __int64 v64; // rbx
  char v65; // si
  __int64 v66; // rbx
  void *v67; // rcx
  unsigned __int64 v68; // rsi
  __int64 v69; // rcx
  char v70; // ah
  __int64 v71; // rcx
  _BYTE v72[40]; // [rsp+20h] [rbp-28h] BYREF
  rsize_t DestinationSize; // [rsp+90h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+50h] BYREF
  __int64 v75; // [rsp+A0h] [rbp+58h]
  __int64 v76; // [rsp+A8h] [rbp+60h]

  v76 = a4;
  v75 = a3;
  v9 = *(_BYTE *)(a2 + 8);
  *(_QWORD *)a1 = *(_QWORD *)a2;
  *(_BYTE *)(a1 + 8) = v9;
  v11 = *(_QWORD **)(a2 + 16);
  v12 = v11[2];
  if ( v12 )
  {
    if ( v11[3] > 0xFu )
      v11 = (_QWORD *)*v11;
  }
  else
  {
    v11 = 0;
  }
  v13 = a1 + 24;
  v14 = *(_QWORD *)(a1 + 128);
  if ( v14 )
    v13 = v13 + 4 * v14 - 4;
  else
    *(_BYTE *)v13 = 1;
  if ( *(_DWORD *)(v13 + 4) == 2 )
  {
    *(_DWORD *)(v13 + 4) = 3;
    v69 = *(_QWORD *)(a1 + 144);
    LOBYTE(DestinationSize) = 3;
    tson::write_buffer::push_back<enum tson::details::archive_marker>(v69, &DestinationSize);
    tson::write_buffer::push_back(*(tson::write_buffer **)(a1 + 144), (const void *)(a1 + 10), 2u);
    *(_WORD *)(a1 + 10) = 0;
  }
  else
  {
    if ( *(_DWORD *)(v13 + 4) )
      goto LABEL_15;
    *(_DWORD *)(v13 + 4) = 1;
    v15 = *(_QWORD *)(a1 + 144);
    v16 = *(_QWORD *)(v15 + 2080);
    v17 = *(char **)(v15 + 2072);
    if ( (unsigned __int64)v17 < v16 )
      goto LABEL_14;
    v18 = v16 - *(_QWORD *)(v15 + 2064);
    v19 = 1;
    if ( v18 > 1 )
      v19 = v18;
    DestinationSize = 2 * v19;
    v20 = (char *)CoTaskMemAlloc(2 * v19);
    v21 = v20;
    if ( v20 )
    {
      v22 = *(const void **)(v15 + 2064);
      v23 = *(_QWORD *)(v15 + 2072) - (_QWORD)v22;
      memcpy_s_1(v20, DestinationSize, v22, v23);
      pv = *(LPVOID *)v15;
      if ( pv )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v72);
        CoTaskMemFree(pv);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v72);
      }
      v24 = DestinationSize;
      v17 = &v21[v23];
      *(_QWORD *)v15 = v21;
      *(_QWORD *)(v15 + 2080) = &v21[v24];
      *(_QWORD *)(v15 + 2064) = v21;
      *(_QWORD *)(v15 + 2072) = &v21[v23];
LABEL_14:
      *v17 = 1;
      ++*(_QWORD *)(v15 + 2072);
      goto LABEL_15;
    }
    *(_BYTE *)(v15 + 8) = 1;
  }
LABEL_15:
  *(_QWORD *)(a1 + 16) = 0;
  if ( *(_DWORD *)(v13 + 4) == 3 )
    goto LABEL_54;
  if ( v11 )
  {
    if ( !*(_QWORD *)a1 )
    {
      *(_BYTE *)(a1 + 8) = 1;
      *(_QWORD *)a1 = "-";
    }
    v25 = *(_QWORD *)(a1 + 144);
    *(_QWORD *)(a1 + 16) = *(_QWORD *)(v25 + 2072) - *(_QWORD *)(v25 + 2064);
    v26 = *(_QWORD *)(v25 + 2080);
    v27 = *(char **)(v25 + 2072);
    if ( (unsigned __int64)v27 >= v26 )
    {
      v28 = v26 - *(_QWORD *)(v25 + 2064);
      v29 = 1;
      if ( v28 > 1 )
        v29 = v28;
      v30 = 2 * v29;
      v31 = (char *)CoTaskMemAlloc(2 * v29);
      v32 = v31;
      if ( !v31 )
      {
        *(_BYTE *)(v25 + 8) = 1;
        goto LABEL_27;
      }
      v33 = *(const void **)(v25 + 2064);
      v34 = *(_QWORD *)(v25 + 2072) - (_QWORD)v33;
      memcpy_s_1(v31, v30, v33, v34);
      DestinationSize = *(_QWORD *)v25;
      if ( DestinationSize )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&pv);
        CoTaskMemFree((LPVOID)DestinationSize);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&pv);
      }
      *(_QWORD *)v25 = v32;
      v27 = &v32[v34];
      *(_QWORD *)(v25 + 2072) = &v32[v34];
      *(_QWORD *)(v25 + 2080) = &v32[v30];
      *(_QWORD *)(v25 + 2064) = v32;
    }
    *v27 = 5;
    ++*(_QWORD *)(v25 + 2072);
LABEL_27:
    v35 = *(_QWORD *)(a1 + 144);
    if ( *(_QWORD *)(v35 + 2072) < *(_QWORD *)(v35 + 2080)
      || tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v35 + 2072))++ = *(_BYTE *)(a1 + 8);
    }
    v36 = *(_QWORD *)(a1 + 144);
    v37 = *(unsigned __int8 *)(a1 + 8);
    v38 = *(const void **)a1;
    if ( *(_QWORD *)(v36 + 2080) - *(_QWORD *)(v36 + 2072) < v37
      && !tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), *(unsigned __int8 *)(a1 + 8)) )
    {
      goto LABEL_53;
    }
    if ( v37 )
    {
      v39 = *(void **)(v36 + 2072);
      if ( !v39 )
        goto LABEL_50;
      v40 = *(_QWORD *)(v36 + 2080) - (_QWORD)v39;
      if ( v38 && v40 >= v37 )
      {
        memcpy_0(v39, v38, v37);
        goto LABEL_52;
      }
      memset_0(v39, 0, *(_QWORD *)(v36 + 2080) - (_QWORD)v39);
      if ( !v38 )
      {
LABEL_50:
        *(_DWORD *)_o__errno() = 22;
        goto LABEL_51;
      }
      if ( v40 < v37 )
      {
        *(_DWORD *)_o__errno() = 34;
LABEL_51:
        invalid_parameter_noinfo();
      }
    }
LABEL_52:
    *(_QWORD *)(v36 + 2072) += v37;
LABEL_53:
    *(_QWORD *)a1 = 0;
LABEL_54:
    v53 = *(_QWORD *)(a1 + 144);
    v54 = *(_QWORD *)(v53 + 2080);
    v55 = *(char **)(v53 + 2072);
    if ( (unsigned __int64)v55 >= v54 )
    {
      v56 = v54 - *(_QWORD *)(v53 + 2064);
      v57 = 1;
      if ( v56 > 1 )
        v57 = v56;
      v58 = 2 * v57;
      v59 = (char *)CoTaskMemAlloc(2 * v57);
      v60 = v59;
      if ( !v59 )
      {
        *(_BYTE *)(v53 + 8) = 1;
LABEL_62:
        v63 = v12 + 1;
        if ( v12 + 1 > 0x7F )
        {
          if ( v63 > 0x7FFF && *(int *)(a1 + 136) >= 0 )
            *(_DWORD *)(a1 + 136) = -2147483637;
          v70 = BYTE1(v63) | 0x80;
          LOBYTE(pv) = v12 + 1;
          v71 = *(_QWORD *)(a1 + 144);
          LOBYTE(DestinationSize) = v70;
          tson::write_buffer::push_back<unsigned char>(v71, &DestinationSize);
          tson::write_buffer::push_back<unsigned char>(*(_QWORD *)(a1 + 144), &pv);
        }
        else
        {
          v64 = *(_QWORD *)(a1 + 144);
          v65 = v11 != 0 ? v63 : 0;
          if ( *(_QWORD *)(v64 + 2072) < *(_QWORD *)(v64 + 2080)
            || tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), 1u) )
          {
            *(_BYTE *)(*(_QWORD *)(v64 + 2072))++ = v65;
          }
        }
        v66 = *(_QWORD *)(a1 + 144);
        if ( *(_QWORD *)(v66 + 2080) - *(_QWORD *)(v66 + 2072) < v12
          && !tson::write_buffer::reserve(*(tson::write_buffer **)(a1 + 144), v12) )
        {
          goto LABEL_49;
        }
        if ( v12 )
        {
          v67 = *(void **)(v66 + 2072);
          if ( !v67 )
            goto LABEL_46;
          v68 = *(_QWORD *)(v66 + 2080) - (_QWORD)v67;
          if ( v11 && v68 >= v12 )
          {
            memcpy_0(v67, v11, v12);
            goto LABEL_48;
          }
          memset_0(v67, 0, *(_QWORD *)(v66 + 2080) - (_QWORD)v67);
          if ( v11 )
          {
            if ( v68 >= v12 )
              goto LABEL_48;
            *(_DWORD *)_o__errno() = 34;
          }
          else
          {
LABEL_46:
            *(_DWORD *)_o__errno() = 22;
          }
          invalid_parameter_noinfo();
        }
LABEL_48:
        *(_QWORD *)(v66 + 2072) += v12;
        goto LABEL_49;
      }
      v61 = *(const void **)(v53 + 2064);
      v62 = *(_QWORD *)(v53 + 2072) - (_QWORD)v61;
      memcpy_s_1(v59, v58, v61, v62);
      DestinationSize = *(_QWORD *)v53;
      if ( DestinationSize )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&pv);
        CoTaskMemFree((LPVOID)DestinationSize);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&pv);
      }
      *(_QWORD *)v53 = v60;
      v55 = &v60[v62];
      *(_QWORD *)(v53 + 2072) = &v60[v62];
      *(_QWORD *)(v53 + 2080) = &v60[v58];
      *(_QWORD *)(v53 + 2064) = v60;
    }
    *v55 = 23;
    ++*(_QWORD *)(v53 + 2072);
    goto LABEL_62;
  }
  v41 = *(_QWORD *)(a1 + 144);
  *(_QWORD *)a1 = 0;
  v42 = *(_QWORD *)(v41 + 2080);
  v43 = *(char **)(v41 + 2072);
  if ( (unsigned __int64)v43 >= v42 )
  {
    v44 = v42 - *(_QWORD *)(v41 + 2064);
    v45 = 1;
    if ( v44 > 1 )
      v45 = v44;
    v46 = 2 * v45;
    v47 = (char *)CoTaskMemAlloc(2 * v45);
    v48 = v47;
    if ( !v47 )
    {
      *(_BYTE *)(v41 + 8) = 1;
      goto LABEL_49;
    }
    v49 = *(const void **)(v41 + 2064);
    v50 = *(_QWORD *)(v41 + 2072) - (_QWORD)v49;
    memcpy_s_1(v47, v46, v49, v50);
    v51 = *(void **)v41;
    if ( *(_QWORD *)v41 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&DestinationSize);
      CoTaskMemFree(v51);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&DestinationSize);
    }
    *(_QWORD *)v41 = v48;
    v43 = &v48[v50];
    *(_QWORD *)(v41 + 2072) = &v48[v50];
    *(_QWORD *)(v41 + 2080) = &v48[v46];
    *(_QWORD *)(v41 + 2064) = v48;
  }
  *v43 = 6;
  ++*(_QWORD *)(v41 + 2072);
LABEL_49:
  tson::save_nothrow<unsigned int &>(a1, v75);
  tson::output_archive::process<tson::nvp<std::string &>>(a1, v76);
  tson::output_archive::process<tson::nvp<std::string &>>(a1, a5);
  tson::output_archive::process<tson::nvp<std::string &>>(a1, a6);
  tson::output_archive::process<tson::nvp<std::string &>>(a1, a7);
  tson::save_nothrow<unsigned int &>(a1, a8);
  tson::output_archive::process<tson::nvp<int &>>(a1, a9);
  return a1;
}

```

## disassembly

```asm
0x180072764  mov     [rsp-40h+arg_18], r9
0x180072769  mov     [rsp-40h+arg_10], r8
0x18007276e  push    rbp
0x18007276f  push    rbx
0x180072770  push    rsi
0x180072771  push    rdi
0x180072772  push    r12
0x180072774  push    r13
0x180072776  push    r14
0x180072778  push    r15
0x18007277a  mov     rbp, rsp
0x18007277d  sub     rsp, 48h
0x180072781  mov     r10b, [rdx+8]
0x180072785  mov     rdi, rcx
0x180072788  mov     rax, [rdx]
0x18007278b  mov     [rcx], rax
0x18007278e  mov     [rcx+8], r10b
0x180072792  mov     r15, [rdx+10h]
0x180072796  mov     r12, [r15+10h]
0x18007279a  test    r12, r12
0x18007279d  jnz     loc_180072A06
0x1800727a3  xor     r15d, r15d
0x1800727a6  lea     rsi, [rcx+18h]
0x1800727aa  mov     rax, [rsi+68h]
0x1800727ae  test    rax, rax
0x1800727b1  jz      loc_180072D19
0x1800727b7  lea     rsi, [rsi+rax*4]
0x1800727bb  add     rsi, 0FFFFFFFFFFFFFFFCh
0x1800727bf  cmp     dword ptr [rsi+4], 2
0x1800727c3  jz      loc_180072D21
0x1800727c9  cmp     dword ptr [rsi+4], 0
0x1800727cd  jnz     loc_180072884
0x1800727d3  mov     dword ptr [rsi+4], 1
0x1800727da  mov     rbx, [rcx+90h]
0x1800727e1  mov     rdx, [rbx+820h]
0x1800727e8  mov     rcx, [rbx+818h]
0x1800727ef  cmp     rcx, rdx
0x1800727f2  jb      loc_18007287A
0x1800727f8  sub     rdx, [rbx+810h]
0x1800727ff  mov     eax, 1
0x180072804  cmp     rdx, rax
0x180072807  cmova   rax, rdx
0x18007280b  add     rax, rax
0x18007280e  mov     rcx, rax; cb
0x180072811  mov     [rbp+DestinationSize], rax
0x180072815  call    cs:__imp_CoTaskMemAlloc
0x18007281b  mov     r14, rax
0x18007281e  test    rax, rax
0x180072821  jz      loc_180072D7E
0x180072827  mov     r8, [rbx+810h]; Source
0x18007282e  mov     rcx, rax; Destination
0x180072831  mov     r13, [rbx+818h]
0x180072838  mov     rdx, [rbp+DestinationSize]; DestinationSize
0x18007283c  sub     r13, r8
0x18007283f  mov     r9, r13; SourceSize
0x180072842  call    memcpy_s_1
0x180072847  mov     rax, [rbx]
0x18007284a  mov     [rbp+pv], rax
0x18007284e  test    rax, rax
0x180072851  jnz     loc_180072D5D
0x180072857  mov     rax, [rbp+DestinationSize]
0x18007285b  lea     rcx, [r14+r13]
0x18007285f  mov     [rbx], r14
0x180072862  add     rax, r14
0x180072865  mov     [rbx+820h], rax
0x18007286c  mov     [rbx+810h], r14
0x180072873  mov     [rbx+818h], rcx
0x18007287a  mov     byte ptr [rcx], 1
0x18007287d  inc     qword ptr [rbx+818h]
0x180072884  mov     qword ptr [rdi+10h], 0
0x18007288c  cmp     dword ptr [rsi+4], 3
0x180072890  jz      loc_180072B62
0x180072896  test    r15, r15
0x180072899  jz      loc_180072A19
0x18007289f  cmp     qword ptr [rdi], 0
0x1800728a3  jz      loc_180072DB0
0x1800728a9  mov     rbx, [rdi+90h]
0x1800728b0  mov     rax, [rbx+818h]
0x1800728b7  sub     rax, [rbx+810h]
0x1800728be  mov     [rdi+10h], rax
0x1800728c2  mov     rdx, [rbx+820h]
0x1800728c9  mov     rcx, [rbx+818h]
0x1800728d0  cmp     rcx, rdx
0x1800728d3  jb      short loc_180072950
0x1800728d5  sub     rdx, [rbx+810h]
0x1800728dc  mov     eax, 1
0x1800728e1  cmp     rdx, rax
0x1800728e4  cmova   rax, rdx
0x1800728e8  lea     r13, [rax+rax]
0x1800728ec  mov     rcx, r13; cb
0x1800728ef  call    cs:__imp_CoTaskMemAlloc
0x1800728f5  mov     rsi, rax
0x1800728f8  test    rax, rax
0x1800728fb  jz      loc_180072DE4
0x180072901  mov     r8, [rbx+810h]; Source
0x180072908  mov     rdx, r13; DestinationSize
0x18007290b  mov     r14, [rbx+818h]
0x180072912  mov     rcx, rax; Destination
0x180072915  sub     r14, r8
0x180072918  mov     r9, r14; SourceSize
0x18007291b  call    memcpy_s_1
0x180072920  mov     rax, [rbx]
0x180072923  mov     [rbp+DestinationSize], rax
0x180072927  test    rax, rax
0x18007292a  jnz     loc_180072DC3
0x180072930  mov     [rbx], rsi
0x180072933  lea     rcx, [r14+rsi]
0x180072937  lea     rax, [rsi+r13]
0x18007293b  mov     [rbx+818h], rcx
0x180072942  mov     [rbx+820h], rax
0x180072949  mov     [rbx+810h], rsi
0x180072950  mov     byte ptr [rcx], 5
0x180072953  inc     qword ptr [rbx+818h]
0x18007295a  mov     rbx, [rdi+90h]
0x180072961  mov     rax, [rbx+820h]
0x180072968  cmp     [rbx+818h], rax
0x18007296f  jnb     loc_180072DED
0x180072975  mov     rcx, [rbx+818h]
0x18007297c  mov     al, [rdi+8]
0x18007297f  mov     [rcx], al
0x180072981  inc     qword ptr [rbx+818h]
0x180072988  mov     rsi, [rdi+90h]
0x18007298f  movzx   ebx, byte ptr [rdi+8]
0x180072993  mov     r13, [rdi]
0x180072996  mov     rax, [rsi+820h]
0x18007299d  sub     rax, [rsi+818h]
0x1800729a4  cmp     rax, rbx
0x1800729a7  jb      loc_180072D01
0x1800729ad  test    rbx, rbx
0x1800729b0  jz      loc_180072B54
0x1800729b6  mov     rcx, [rsi+818h]; void *
0x1800729bd  test    rcx, rcx
0x1800729c0  jz      loc_180072B43
0x1800729c6  mov     r14, [rsi+820h]
0x1800729cd  sub     r14, rcx
0x1800729d0  test    r13, r13
0x1800729d3  jnz     loc_180072CD0
0x1800729d9  mov     r8, r14; Size
0x1800729dc  xor     edx, edx; Val
0x1800729de  call    memset_0
0x1800729e3  test    r13, r13
0x1800729e6  jz      loc_180072B43
0x1800729ec  cmp     r14, rbx
0x1800729ef  jnb     loc_180072B54
0x1800729f5  call    cs:__imp__o__errno
0x1800729fb  mov     dword ptr [rax], 22h ; '"'
0x180072a01  jmp     loc_180072B4F
0x180072a06  cmp     qword ptr [r15+18h], 0Fh
0x180072a0b  jbe     loc_1800727A6
0x180072a11  mov     r15, [r15]
0x180072a14  jmp     loc_1800727A6
0x180072a19  mov     rbx, [rdi+90h]
0x180072a20  mov     qword ptr [rdi], 0
0x180072a27  mov     rdx, [rbx+820h]
0x180072a2e  mov     rcx, [rbx+818h]
0x180072a35  cmp     rcx, rdx
0x180072a38  jb      short loc_180072AB1
0x180072a3a  sub     rdx, [rbx+810h]
0x180072a41  mov     eax, 1
0x180072a46  cmp     rdx, rax
0x180072a49  cmova   rax, rdx
0x180072a4d  lea     r15, [rax+rax]
0x180072a51  mov     rcx, r15; cb
0x180072a54  call    cs:__imp_CoTaskMemAlloc
0x180072a5a  mov     rsi, rax
0x180072a5d  test    rax, rax
0x180072a60  jz      loc_180072DA7
0x180072a66  mov     r8, [rbx+810h]; Source
0x180072a6d  mov     rdx, r15; DestinationSize
0x180072a70  mov     r14, [rbx+818h]
0x180072a77  mov     rcx, rax; Destination
0x180072a7a  sub     r14, r8
0x180072a7d  mov     r9, r14; SourceSize
0x180072a80  call    memcpy_s_1
0x180072a85  mov     r12, [rbx]
0x180072a88  test    r12, r12
0x180072a8b  jnz     loc_180072D87
0x180072a91  mov     [rbx], rsi
0x180072a94  lea     rcx, [r14+rsi]
0x180072a98  lea     rax, [rsi+r15]
0x180072a9c  mov     [rbx+818h], rcx
0x180072aa3  mov     [rbx+820h], rax
0x180072aaa  mov     [rbx+810h], rsi
0x180072ab1  mov     byte ptr [rcx], 6
0x180072ab4  inc     qword ptr [rbx+818h]
0x180072abb  jmp     short loc_180072AD5
0x180072abd  call    cs:__imp__o__errno
0x180072ac3  mov     dword ptr [rax], 16h
0x180072ac9  call    _invalid_parameter_noinfo
0x180072ace  add     [rbx+818h], r12
0x180072ad5  mov     rdx, [rbp+arg_10]
0x180072ad9  mov     rcx, rdi
0x180072adc  call    ??$save_nothrow@AEAI@tson@@YAXAEAVoutput_archive@0@AEAV?$nvp@AEAI@0@@Z; tson::save_nothrow<uint &>(tson::output_archive &,tson::nvp<uint &> &)
0x180072ae1  mov     rdx, [rbp+arg_18]
0x180072ae5  mov     rcx, rdi
0x180072ae8  call    ??$process@V?$nvp@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::string &>>(tson::nvp<std::string &> &&)
0x180072aed  mov     rdx, [rbp+arg_20]
0x180072af1  mov     rcx, rdi
0x180072af4  call    ??$process@V?$nvp@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::string &>>(tson::nvp<std::string &> &&)
0x180072af9  mov     rdx, [rbp+arg_28]
0x180072afd  mov     rcx, rdi
0x180072b00  call    ??$process@V?$nvp@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::string &>>(tson::nvp<std::string &> &&)
0x180072b05  mov     rdx, [rbp+arg_30]
0x180072b09  mov     rcx, rdi
0x180072b0c  call    ??$process@V?$nvp@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; tson::output_archive::process<tson::nvp<std::string &>>(tson::nvp<std::string &> &&)
0x180072b11  mov     rdx, [rbp+arg_38]
0x180072b18  mov     rcx, rdi
0x180072b1b  call    ??$save_nothrow@AEAI@tson@@YAXAEAVoutput_archive@0@AEAV?$nvp@AEAI@0@@Z; tson::save_nothrow<uint &>(tson::output_archive &,tson::nvp<uint &> &)
0x180072b20  mov     rdx, [rbp+arg_40]
0x180072b27  mov     rcx, rdi
0x180072b2a  call    ??$process@V?$nvp@AEAH@tson@@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAH@1@@Z; tson::output_archive::process<tson::nvp<int &>>(tson::nvp<int &> &&)
0x180072b2f  mov     rax, rdi
0x180072b32  add     rsp, 48h
0x180072b36  pop     r15
0x180072b38  pop     r14
0x180072b3a  pop     r13
0x180072b3c  pop     r12
0x180072b3e  pop     rdi
0x180072b3f  pop     rsi
0x180072b40  pop     rbx
0x180072b41  pop     rbp
0x180072b42  retn
0x180072b43  call    cs:__imp__o__errno
0x180072b49  mov     dword ptr [rax], 16h
0x180072b4f  call    _invalid_parameter_noinfo
0x180072b54  add     [rsi+818h], rbx
0x180072b5b  mov     qword ptr [rdi], 0
0x180072b62  mov     rbx, [rdi+90h]
0x180072b69  mov     rdx, [rbx+820h]
0x180072b70  mov     rcx, [rbx+818h]
0x180072b77  cmp     rcx, rdx
0x180072b7a  jb      short loc_180072BF7
0x180072b7c  sub     rdx, [rbx+810h]
0x180072b83  mov     eax, 1
0x180072b88  cmp     rdx, rax
0x180072b8b  cmova   rax, rdx
0x180072b8f  lea     r13, [rax+rax]
0x180072b93  mov     rcx, r13; cb
0x180072b96  call    cs:__imp_CoTaskMemAlloc
0x180072b9c  mov     rsi, rax
0x180072b9f  test    rax, rax
0x180072ba2  jz      loc_180072E28
0x180072ba8  mov     r8, [rbx+810h]; Source
0x180072baf  mov     rdx, r13; DestinationSize
0x180072bb2  mov     r14, [rbx+818h]
0x180072bb9  mov     rcx, rax; Destination
0x180072bbc  sub     r14, r8
0x180072bbf  mov     r9, r14; SourceSize
0x180072bc2  call    memcpy_s_1
0x180072bc7  mov     rax, [rbx]
0x180072bca  mov     [rbp+DestinationSize], rax
0x180072bce  test    rax, rax
0x180072bd1  jnz     loc_180072E07
0x180072bd7  mov     [rbx], rsi
0x180072bda  lea     rcx, [r14+rsi]
0x180072bde  lea     rax, [rsi+r13]
0x180072be2  mov     [rbx+818h], rcx
0x180072be9  mov     [rbx+820h], rax
0x180072bf0  mov     [rbx+810h], rsi
0x180072bf7  mov     byte ptr [rcx], 17h
0x180072bfa  inc     qword ptr [rbx+818h]
0x180072c01  lea     rcx, [r12+1]
0x180072c06  cmp     rcx, 7Fh
0x180072c0a  ja      loc_180072E4B
0x180072c10  mov     rbx, [rdi+90h]
0x180072c17  mov     rax, r15
0x180072c1a  neg     rax
0x180072c1d  sbb     sil, sil
0x180072c20  mov     rax, [rbx+820h]
0x180072c27  and     sil, cl
0x180072c2a  cmp     [rbx+818h], rax
0x180072c31  jnb     loc_180072E31
0x180072c37  mov     rax, [rbx+818h]
0x180072c3e  mov     [rax], sil
0x180072c41  inc     qword ptr [rbx+818h]
0x180072c48  mov     rbx, [rdi+90h]
0x180072c4f  mov     rax, [rbx+820h]
0x180072c56  sub     rax, [rbx+818h]
0x180072c5d  cmp     rax, r12
0x180072c60  jb      loc_180072CE9
0x180072c66  test    r12, r12
0x180072c69  jz      loc_180072ACE
0x180072c6f  mov     rcx, [rbx+818h]; void *
0x180072c76  test    rcx, rcx
0x180072c79  jz      loc_180072ABD
0x180072c7f  mov     rsi, [rbx+820h]
0x180072c86  sub     rsi, rcx
0x180072c89  test    r15, r15
0x180072c8c  jnz     short loc_180072CBB
0x180072c8e  mov     r8, rsi; Size
0x180072c91  xor     edx, edx; Val
0x180072c93  call    memset_0
0x180072c98  test    r15, r15
0x180072c9b  jz      loc_180072ABD
0x180072ca1  cmp     rsi, r12
0x180072ca4  jnb     loc_180072ACE
0x180072caa  call    cs:__imp__o__errno
0x180072cb0  mov     dword ptr [rax], 22h ; '"'
0x180072cb6  jmp     loc_180072AC9
0x180072cbb  cmp     rsi, r12
  ... truncated ...
```
