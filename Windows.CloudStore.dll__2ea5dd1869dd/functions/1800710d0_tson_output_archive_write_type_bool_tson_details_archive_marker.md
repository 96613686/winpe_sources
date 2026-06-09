# tson::output_archive::write_type(bool,tson::details::archive_marker)

- ea: `0x1800710d0`
- end: `0x180071627`
- name: `?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z`
- size: `1367`
- prototype: ``
- caller_count: `12`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006f4fc`
- `0x18006fab0`
- `0x180071630`
- `0x1800719b0`
- `0x1800e33ac`
- `0x1800e3404`
- `0x1800e345c`
- `0x1800eae08`
- `0x1801390b4`
- `0x180139140`
- `0x18013952c`
- `0x18013c444`

## callees

- `0x1800710d0`
- `0x180074110`
- `0x1800741f4`
- `0x18007b050`
- `0x1800a6f3c`
- `0x180120bea`
- `0x180120c94`
- `0x180123882`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180071350`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180071400`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800714ca`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180071350`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180071400`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800714ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800715bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800715bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071600`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071566`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071595`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800715d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071613`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071566`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071595`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800715d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071613`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007155e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007158d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800715c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007160b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007155e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007158d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800715c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007160b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007116b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071245`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071449`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007116b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071245`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071449`

## pseudocode

```c
char __fastcall tson::output_archive::write_type(__int64 a1, char a2, char a3)
{
  __int64 v3; // rbx
  char v4; // r13
  __int64 v5; // rax
  int v8; // eax
  __int64 v9; // r15
  __int64 v10; // r14
  unsigned __int64 v11; // rdx
  char *v12; // rcx
  unsigned __int64 v13; // rdx
  __int64 v14; // rax
  rsize_t v15; // rdi
  char *v16; // rax
  char *v17; // r12
  const void *v18; // r8
  rsize_t v19; // r13
  __int64 v20; // rdi
  unsigned __int64 v21; // rdx
  char *v22; // rcx
  unsigned __int64 v23; // rdx
  __int64 v24; // rax
  rsize_t v25; // r12
  char *v26; // rax
  char *v27; // r14
  const void *v28; // r8
  rsize_t v29; // rbp
  __int64 v30; // rbx
  __int64 v31; // rbx
  size_t v32; // rdi
  const void *v33; // r14
  void *v34; // rcx
  size_t v35; // rbp
  __int64 v36; // rdi
  unsigned __int64 v37; // rax
  char *v38; // rcx
  unsigned __int64 v39; // rax
  __int64 v40; // r15
  char *v41; // rax
  char *v42; // rsi
  const void *v43; // r8
  rsize_t v44; // rbp
  void *v45; // r14
  __int64 v47; // rdi
  unsigned __int64 v48; // rax
  char *v49; // rcx
  unsigned __int64 v50; // rax
  __int64 v51; // r15
  char *v52; // rax
  char *v53; // rsi
  const void *v54; // r8
  rsize_t v55; // rbp
  void *v56; // r14
  __int64 v57; // rcx
  DWORD LastError; // edi
  DWORD v59; // ebx
  DWORD v60; // ebx
  DWORD v61; // ebx
  LPVOID pv; // [rsp+60h] [rbp+8h] BYREF
  char v63; // [rsp+70h] [rbp+18h]
  __int64 v64; // [rsp+78h] [rbp+20h]

  v63 = a3;
  v3 = a1 + 24;
  v4 = a3;
  v5 = *(_QWORD *)(a1 + 128);
  if ( v5 )
    v3 = v3 + 4 * v5 - 4;
  else
    *(_BYTE *)v3 = 1;
  v8 = *(_DWORD *)(v3 + 4);
  v9 = 1;
  if ( v8 == 2 )
  {
    *(_DWORD *)(v3 + 4) = 3;
    v57 = *(_QWORD *)(a1 + 144);
    LOBYTE(pv) = 3;
    tson::write_buffer::push_back<enum tson::details::archive_marker>(v57, &pv);
    tson::write_buffer::push_back(*(tson::write_buffer **)(a1 + 144), (const void *)(a1 + 10), 2u);
    *(_WORD *)(a1 + 10) = 0;
  }
  else
  {
    if ( v8 )
      goto LABEL_13;
    *(_DWORD *)(v3 + 4) = 1;
    v10 = *(_QWORD *)(a1 + 144);
    v11 = *(_QWORD *)(v10 + 2080);
    v12 = *(char **)(v10 + 2072);
    if ( (unsigned __int64)v12 < v11 )
      goto LABEL_12;
    v13 = v11 - *(_QWORD *)(v10 + 2064);
    v14 = 1;
    if ( v13 > 1 )
      v14 = v13;
    v15 = 2 * v14;
    v64 = 2 * v14;
    v16 = (char *)CoTaskMemAlloc(2 * v14);
    v17 = v16;
    if ( v16 )
    {
      v18 = *(const void **)(v10 + 2064);
      v19 = *(_QWORD *)(v10 + 2072) - (_QWORD)v18;
      memcpy_s_1(v16, v15, v18, v19);
      pv = *(LPVOID *)v10;
      if ( pv )
      {
        LastError = GetLastError();
        CoTaskMemFree(pv);
        SetLastError(LastError);
        v15 = v64;
      }
      *(_QWORD *)v10 = v17;
      v12 = &v17[v19];
      v4 = v63;
      *(_QWORD *)(v10 + 2064) = v17;
      *(_QWORD *)(v10 + 2072) = v12;
      *(_QWORD *)(v10 + 2080) = &v17[v15];
LABEL_12:
      *v12 = 1;
      ++*(_QWORD *)(v10 + 2072);
      goto LABEL_13;
    }
    *(_BYTE *)(v10 + 8) = 1;
  }
LABEL_13:
  *(_QWORD *)(a1 + 16) = 0;
  if ( *(_DWORD *)(v3 + 4) == 3 )
    goto LABEL_47;
  if ( a2 )
  {
    v36 = *(_QWORD *)(a1 + 144);
    *(_QWORD *)a1 = 0;
    v37 = *(_QWORD *)(v36 + 2080);
    v38 = *(char **)(v36 + 2072);
    if ( (unsigned __int64)v38 >= v37 )
    {
      v39 = v37 - *(_QWORD *)(v36 + 2064);
      if ( v39 > 1 )
        v9 = v39;
      v40 = 2 * v9;
      v41 = (char *)CoTaskMemAlloc(v40);
      v42 = v41;
      if ( !v41 )
      {
        *(_BYTE *)(v36 + 8) = 1;
        return 0;
      }
      v43 = *(const void **)(v36 + 2064);
      v44 = *(_QWORD *)(v36 + 2072) - (_QWORD)v43;
      memcpy_s_1(v41, v40, v43, v44);
      v45 = *(void **)v36;
      if ( *(_QWORD *)v36 )
      {
        v59 = GetLastError();
        CoTaskMemFree(v45);
        SetLastError(v59);
      }
      *(_QWORD *)v36 = v42;
      v38 = &v42[v44];
      *(_QWORD *)(v36 + 2072) = &v42[v44];
      *(_QWORD *)(v36 + 2080) = &v42[v40];
      *(_QWORD *)(v36 + 2064) = v42;
    }
    *v38 = 6;
    ++*(_QWORD *)(v36 + 2072);
    return 0;
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
    pv = *(LPVOID *)v20;
    if ( pv )
    {
      v60 = GetLastError();
      CoTaskMemFree(pv);
      SetLastError(v60);
    }
    *(_QWORD *)v20 = v27;
    v22 = &v27[v29];
    *(_QWORD *)(v20 + 2080) = &v27[v25];
    *(_QWORD *)(v20 + 2072) = &v27[v29];
    *(_QWORD *)(v20 + 2064) = v27;
  }
  *v22 = 5;
  ++*(_QWORD *)(v20 + 2072);
LABEL_25:
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
    goto LABEL_46;
  }
  if ( v32 )
  {
    v34 = *(void **)(v31 + 2072);
    if ( !v34 )
      goto LABEL_43;
    v35 = *(_QWORD *)(v31 + 2080) - (_QWORD)v34;
    if ( v33 && v35 >= v32 )
    {
      memcpy_0(v34, v33, v32);
      goto LABEL_45;
    }
    memset_0(v34, 0, *(_QWORD *)(v31 + 2080) - (_QWORD)v34);
    if ( !v33 )
    {
LABEL_43:
      *(_DWORD *)_o__errno() = 22;
      goto LABEL_44;
    }
    if ( v35 < v32 )
    {
      *(_DWORD *)_o__errno() = 34;
LABEL_44:
      invalid_parameter_noinfo();
    }
  }
LABEL_45:
  *(_QWORD *)(v31 + 2072) += v32;
LABEL_46:
  *(_QWORD *)a1 = 0;
LABEL_47:
  v47 = *(_QWORD *)(a1 + 144);
  v48 = *(_QWORD *)(v47 + 2080);
  v49 = *(char **)(v47 + 2072);
  if ( (unsigned __int64)v49 >= v48 )
  {
    v50 = v48 - *(_QWORD *)(v47 + 2064);
    if ( v50 > 1 )
      v9 = v50;
    v51 = 2 * v9;
    v52 = (char *)CoTaskMemAlloc(v51);
    v53 = v52;
    if ( !v52 )
    {
      *(_BYTE *)(v47 + 8) = 1;
      return 1;
    }
    v54 = *(const void **)(v47 + 2064);
    v55 = *(_QWORD *)(v47 + 2072) - (_QWORD)v54;
    memcpy_s_1(v52, v51, v54, v55);
    v56 = *(void **)v47;
    if ( *(_QWORD *)v47 )
    {
      v61 = GetLastError();
      CoTaskMemFree(v56);
      SetLastError(v61);
    }
    *(_QWORD *)v47 = v53;
    v49 = &v53[v55];
    *(_QWORD *)(v47 + 2072) = &v53[v55];
    *(_QWORD *)(v47 + 2080) = &v53[v51];
    *(_QWORD *)(v47 + 2064) = v53;
  }
  *v49 = v4;
  ++*(_QWORD *)(v47 + 2072);
  return 1;
}

```

## disassembly

```asm
0x1800710d0  mov     [rsp+arg_10], r8b
0x1800710d5  push    rbx
0x1800710d6  push    rbp
0x1800710d7  push    rsi
0x1800710d8  push    r12
0x1800710da  push    r13
0x1800710dc  push    r15
0x1800710de  sub     rsp, 28h
0x1800710e2  lea     rbx, [rcx+18h]
0x1800710e6  movzx   r13d, r8b
0x1800710ea  mov     rax, [rbx+68h]
0x1800710ee  movzx   ebp, dl
0x1800710f1  mov     rsi, rcx
0x1800710f4  test    rax, rax
0x1800710f7  jz      loc_18007150C
0x1800710fd  lea     rbx, [rbx+rax*4]
0x180071101  add     rbx, 0FFFFFFFFFFFFFFFCh
0x180071105  mov     eax, [rbx+4]
0x180071108  xor     r12d, r12d
0x18007110b  mov     [rsp+58h+arg_8], rdi
0x180071110  mov     r15d, 1
0x180071116  mov     [rsp+58h+var_38], r14
0x18007111b  cmp     eax, 2
0x18007111e  jz      loc_180071514
0x180071124  test    eax, eax
0x180071126  jnz     loc_1800711E0
0x18007112c  mov     [rbx+4], r15d
0x180071130  mov     r14, [rcx+90h]
0x180071137  mov     rdx, [r14+820h]
0x18007113e  mov     rcx, [r14+818h]
0x180071145  cmp     rcx, rdx
0x180071148  jb      loc_1800711D6
0x18007114e  sub     rdx, [r14+810h]
0x180071155  mov     eax, r15d
0x180071158  cmp     rdx, rax
0x18007115b  cmova   rax, rdx
0x18007115f  lea     rdi, [rax+rax]
0x180071163  mov     rcx, rdi; cb
0x180071166  mov     [rsp+58h+arg_18], rdi
0x18007116b  call    cs:__imp_CoTaskMemAlloc
0x180071171  mov     r12, rax
0x180071174  test    rax, rax
0x180071177  jz      loc_180071576
0x18007117d  mov     r8, [r14+810h]; Source
0x180071184  mov     rdx, rdi; DestinationSize
0x180071187  mov     r13, [r14+818h]
0x18007118e  mov     rcx, rax; Destination
0x180071191  sub     r13, r8
0x180071194  mov     r9, r13; SourceSize
0x180071197  call    memcpy_s_1
0x18007119c  mov     rax, [r14]
0x18007119f  mov     [rsp+58h+pv], rax
0x1800711a4  test    rax, rax
0x1800711a7  jnz     loc_180071551
0x1800711ad  mov     [r14], r12
0x1800711b0  lea     rcx, [r12+r13]
0x1800711b4  movzx   r13d, [rsp+58h+arg_10]
0x1800711ba  lea     rax, [rdi+r12]
0x1800711be  mov     [r14+810h], r12
0x1800711c5  xor     r12d, r12d
0x1800711c8  mov     [r14+818h], rcx
0x1800711cf  mov     [r14+820h], rax
0x1800711d6  mov     [rcx], r15b
0x1800711d9  inc     qword ptr [r14+818h]
0x1800711e0  mov     [rsi+10h], r12
0x1800711e4  cmp     dword ptr [rbx+4], 3
0x1800711e8  jz      loc_18007141B
0x1800711ee  test    bpl, bpl
0x1800711f1  jnz     loc_180071361
0x1800711f7  cmp     qword ptr [rsi], 0
0x1800711fb  jz      loc_1800715A9
0x180071201  mov     rdi, [rsi+90h]
0x180071208  mov     rax, [rdi+818h]
0x18007120f  sub     rax, [rdi+810h]
0x180071216  mov     [rsi+10h], rax
0x18007121a  mov     rdx, [rdi+820h]
0x180071221  mov     rcx, [rdi+818h]
0x180071228  cmp     rcx, rdx
0x18007122b  jb      short loc_1800712AA
0x18007122d  sub     rdx, [rdi+810h]
0x180071234  mov     rax, r15
0x180071237  cmp     rdx, rax
0x18007123a  cmova   rax, rdx
0x18007123e  lea     r12, [rax+rax]
0x180071242  mov     rcx, r12; cb
0x180071245  call    cs:__imp_CoTaskMemAlloc
0x18007124b  mov     r14, rax
0x18007124e  test    rax, rax
0x180071251  jz      loc_1800715DC
0x180071257  mov     r8, [rdi+810h]; Source
0x18007125e  mov     rdx, r12; DestinationSize
0x180071261  mov     rbp, [rdi+818h]
0x180071268  mov     rcx, rax; Destination
0x18007126b  sub     rbp, r8
0x18007126e  mov     r9, rbp; SourceSize
0x180071271  call    memcpy_s_1
0x180071276  mov     rax, [rdi]
0x180071279  mov     [rsp+58h+pv], rax
0x18007127e  test    rax, rax
0x180071281  jnz     loc_1800715BC
0x180071287  mov     [rdi], r14
0x18007128a  lea     rax, [r12+r14]
0x18007128e  lea     rcx, [r14+rbp]
0x180071292  mov     [rdi+820h], rax
0x180071299  mov     [rdi+818h], rcx
0x1800712a0  xor     r12d, r12d
0x1800712a3  mov     [rdi+810h], r14
0x1800712aa  mov     byte ptr [rcx], 5
0x1800712ad  inc     qword ptr [rdi+818h]
0x1800712b4  mov     rbx, [rsi+90h]
0x1800712bb  mov     rax, [rbx+820h]
0x1800712c2  cmp     [rbx+818h], rax
0x1800712c9  jnb     loc_1800715E8
0x1800712cf  mov     rcx, [rbx+818h]
0x1800712d6  movzx   eax, byte ptr [rsi+8]
0x1800712da  mov     [rcx], al
0x1800712dc  inc     qword ptr [rbx+818h]
0x1800712e3  mov     rbx, [rsi+90h]
0x1800712ea  movzx   edi, byte ptr [rsi+8]
0x1800712ee  mov     r14, [rsi]
0x1800712f1  mov     rax, [rbx+820h]
0x1800712f8  sub     rax, [rbx+818h]
0x1800712ff  cmp     rax, rdi
0x180071302  jb      loc_1800714F4
0x180071308  test    rdi, rdi
0x18007130b  jz      loc_180071411
0x180071311  mov     rcx, [rbx+818h]; void *
0x180071318  test    rcx, rcx
0x18007131b  jz      loc_180071400
0x180071321  mov     rbp, [rbx+820h]
0x180071328  sub     rbp, rcx
0x18007132b  test    r14, r14
0x18007132e  jnz     loc_1800714DB
0x180071334  mov     r8, rbp; Size
0x180071337  xor     edx, edx; Val
0x180071339  call    memset_0
0x18007133e  test    r14, r14
0x180071341  jz      loc_1800714CA
0x180071347  cmp     rbp, rdi
0x18007134a  jnb     loc_180071411
0x180071350  call    cs:__imp__o__errno
0x180071356  mov     dword ptr [rax], 22h ; '"'
0x18007135c  jmp     loc_18007140C
0x180071361  mov     rdi, [rsi+90h]
0x180071368  mov     [rsi], r12
0x18007136b  mov     rax, [rdi+820h]
0x180071372  mov     rcx, [rdi+818h]
0x180071379  cmp     rcx, rax
0x18007137c  jb      short loc_1800713EF
0x18007137e  sub     rax, [rdi+810h]
0x180071385  cmp     rax, r15
0x180071388  cmova   r15, rax
0x18007138c  add     r15, r15
0x18007138f  mov     rcx, r15; cb
0x180071392  call    cs:__imp_CoTaskMemAlloc
0x180071398  mov     rsi, rax
0x18007139b  test    rax, rax
0x18007139e  jz      loc_1800715A0
0x1800713a4  mov     r8, [rdi+810h]; Source
0x1800713ab  mov     rdx, r15; DestinationSize
0x1800713ae  mov     rbp, [rdi+818h]
0x1800713b5  mov     rcx, rax; Destination
0x1800713b8  sub     rbp, r8
0x1800713bb  mov     r9, rbp; SourceSize
0x1800713be  call    memcpy_s_1
0x1800713c3  mov     r14, [rdi]
0x1800713c6  test    r14, r14
0x1800713c9  jnz     loc_180071582
0x1800713cf  mov     [rdi], rsi
0x1800713d2  lea     rcx, [rsi+rbp]
0x1800713d6  lea     rax, [r15+rsi]
0x1800713da  mov     [rdi+818h], rcx
0x1800713e1  mov     [rdi+820h], rax
0x1800713e8  mov     [rdi+810h], rsi
0x1800713ef  mov     byte ptr [rcx], 6
0x1800713f2  inc     qword ptr [rdi+818h]
0x1800713f9  xor     al, al
0x1800713fb  jmp     loc_1800714B2
0x180071400  call    cs:__imp__o__errno
0x180071406  mov     dword ptr [rax], 16h
0x18007140c  call    _invalid_parameter_noinfo
0x180071411  add     [rbx+818h], rdi
0x180071418  mov     [rsi], r12
0x18007141b  mov     rdi, [rsi+90h]
0x180071422  mov     rax, [rdi+820h]
0x180071429  mov     rcx, [rdi+818h]
0x180071430  cmp     rcx, rax
0x180071433  jb      short loc_1800714A6
0x180071435  sub     rax, [rdi+810h]
0x18007143c  cmp     rax, r15
0x18007143f  cmova   r15, rax
0x180071443  add     r15, r15
0x180071446  mov     rcx, r15; cb
0x180071449  call    cs:__imp_CoTaskMemAlloc
0x18007144f  mov     rsi, rax
0x180071452  test    rax, rax
0x180071455  jz      loc_18007161E
0x18007145b  mov     r8, [rdi+810h]; Source
0x180071462  mov     rdx, r15; DestinationSize
0x180071465  mov     rbp, [rdi+818h]
0x18007146c  mov     rcx, rax; Destination
0x18007146f  sub     rbp, r8
0x180071472  mov     r9, rbp; SourceSize
0x180071475  call    memcpy_s_1
0x18007147a  mov     r14, [rdi]
0x18007147d  test    r14, r14
0x180071480  jnz     loc_180071600
0x180071486  mov     [rdi], rsi
0x180071489  lea     rcx, [rsi+rbp]
0x18007148d  lea     rax, [r15+rsi]
0x180071491  mov     [rdi+818h], rcx
0x180071498  mov     [rdi+820h], rax
0x18007149f  mov     [rdi+810h], rsi
0x1800714a6  mov     [rcx], r13b
0x1800714a9  inc     qword ptr [rdi+818h]
0x1800714b0  mov     al, 1
0x1800714b2  mov     r14, [rsp+58h+var_38]
0x1800714b7  mov     rdi, [rsp+58h+arg_8]
0x1800714bc  add     rsp, 28h
0x1800714c0  pop     r15
0x1800714c2  pop     r13
0x1800714c4  pop     r12
0x1800714c6  pop     rsi
0x1800714c7  pop     rbp
0x1800714c8  pop     rbx
0x1800714c9  retn
0x1800714ca  call    cs:__imp__o__errno
0x1800714d0  mov     dword ptr [rax], 16h
0x1800714d6  jmp     loc_18007140C
0x1800714db  cmp     rbp, rdi
0x1800714de  jb      loc_180071334
0x1800714e4  mov     r8, rdi; Size
0x1800714e7  mov     rdx, r14; Src
0x1800714ea  call    memcpy_0
0x1800714ef  jmp     loc_180071411
0x1800714f4  mov     rdx, rdi; unsigned __int64
0x1800714f7  mov     rcx, rbx; this
0x1800714fa  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800714ff  test    al, al
0x180071501  jnz     loc_180071308
0x180071507  jmp     loc_180071418
0x18007150c  mov     byte ptr [rbx], 1
0x18007150f  jmp     loc_180071105
0x180071514  mov     dword ptr [rbx+4], 3
0x18007151b  lea     rdx, [rsp+58h+pv]
0x180071520  mov     rcx, [rcx+90h]
0x180071527  mov     byte ptr [rsp+58h+pv], 3
0x18007152c  call    ??$push_back@W4archive_marker@details@tson@@@write_buffer@tson@@QEAA_NAEBW4archive_marker@details@1@@Z; tson::write_buffer::push_back<tson::details::archive_marker>(tson::details::archive_marker const &)
0x180071531  mov     rcx, [rsi+90h]; this
0x180071538  lea     rdx, [rsi+0Ah]; void *
0x18007153c  mov     r8d, 2; unsigned __int64
0x180071542  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x180071547  mov     [rsi+0Ah], r12w
0x18007154c  jmp     loc_1800711E0
0x180071551  call    cs:__imp_GetLastError
0x180071557  mov     rcx, [rsp+58h+pv]; pv
0x18007155c  mov     edi, eax
0x18007155e  call    cs:__imp_CoTaskMemFree
0x180071564  mov     ecx, edi; dwErrCode
0x180071566  call    cs:__imp_SetLastError
0x18007156c  mov     rdi, [rsp+58h+arg_18]
0x180071571  jmp     loc_1800711AD
0x180071576  mov     [r14+8], r15b
0x18007157a  xor     r12d, r12d
0x18007157d  jmp     loc_1800711E0
0x180071582  call    cs:__imp_GetLastError
0x180071588  mov     rcx, r14; pv
0x18007158b  mov     ebx, eax
0x18007158d  call    cs:__imp_CoTaskMemFree
0x180071593  mov     ecx, ebx; dwErrCode
0x180071595  call    cs:__imp_SetLastError
0x18007159b  jmp     loc_1800713CF
0x1800715a0  mov     byte ptr [rdi+8], 1
0x1800715a4  jmp     loc_1800713F9
0x1800715a9  lea     rax, asc_180238410; "-"
0x1800715b0  mov     [rsi+8], r15b
0x1800715b4  mov     [rsi], rax
0x1800715b7  jmp     loc_180071201
0x1800715bc  call    cs:__imp_GetLastError
0x1800715c2  mov     rcx, [rsp+58h+pv]; pv
0x1800715c7  mov     ebx, eax
0x1800715c9  call    cs:__imp_CoTaskMemFree
0x1800715cf  mov     ecx, ebx; dwErrCode
0x1800715d1  call    cs:__imp_SetLastError
0x1800715d7  jmp     loc_180071287
0x1800715dc  mov     [rdi+8], r15b
0x1800715e0  xor     r12d, r12d
0x1800715e3  jmp     loc_1800712B4
0x1800715e8  mov     rdx, r15; unsigned __int64
0x1800715eb  mov     rcx, rbx; this
0x1800715ee  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800715f3  test    al, al
0x1800715f5  jz      loc_1800712E3
0x1800715fb  jmp     loc_1800712CF
0x180071600  call    cs:__imp_GetLastError
0x180071606  mov     rcx, r14; pv
0x180071609  mov     ebx, eax
0x18007160b  call    cs:__imp_CoTaskMemFree
0x180071611  mov     ecx, ebx; dwErrCode
0x180071613  call    cs:__imp_SetLastError
  ... truncated ...
```
