# tson::output_archive::startNode(void)

- ea: `0x1800700e0`
- end: `0x1800704aa`
- name: `?startNode@output_archive@tson@@QEAAXXZ`
- size: `970`
- prototype: `void __fastcall(tson::output_archive *__hidden this)`
- caller_count: `19`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006f2d0`
- `0x18006f4fc`
- `0x18006fab0`
- `0x180072540`
- `0x180139744`
- `0x18013c490`
- `0x18014db04`
- `0x180161220`
- `0x1801766e0`
- `0x180176780`
- `0x180176820`
- `0x1801768c0`
- `0x180176960`
- `0x180176a00`
- `0x180176a80`
- `0x180194d60`
- `0x180199f80`
- `0x1801ba46c`
- `0x1801bb040`

## callees

- `0x1800700e0`
- `0x180074110`
- `0x1800741f4`
- `0x18007b050`
- `0x1800a6f3c`
- `0x180120bea`
- `0x180120c94`
- `0x180123882`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180070311`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007038c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007039a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180070311`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007038c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007039a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007045d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007045d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070435`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070470`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070435`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007042d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070468`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007042d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070468`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070175`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070242`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070175`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070242`

## pseudocode

```c
void __fastcall tson::output_archive::startNode(tson::output_archive *this)
{
  char *v1; // rbx
  __int64 v2; // rax
  char *v4; // rbp
  int v5; // eax
  __int64 v6; // r14
  unsigned __int64 v7; // rdx
  char *v8; // rcx
  unsigned __int64 v9; // rdx
  __int64 v10; // rax
  rsize_t v11; // r13
  char *v12; // rax
  char *v13; // r15
  const void *v14; // r8
  rsize_t v15; // r12
  __int64 v16; // r14
  unsigned __int64 v17; // rdx
  char *v18; // rcx
  unsigned __int64 v19; // rdx
  __int64 v20; // rax
  rsize_t v21; // r12
  char *v22; // rax
  char *v23; // rbp
  const void *v24; // r8
  rsize_t v25; // r15
  void *v26; // r13
  __int64 v27; // rdi
  __int64 v28; // rdi
  size_t v29; // rbp
  const void *v30; // r15
  void *v31; // rcx
  unsigned __int64 v32; // rax
  size_t v33; // r14
  __int64 v34; // rcx
  DWORD LastError; // edi
  DWORD v36; // edi
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF

  v1 = (char *)this + 24;
  v2 = *((_QWORD *)this + 16);
  if ( v2 )
  {
    v4 = (char *)this + 4 * v2 + 20;
  }
  else
  {
    *v1 = 1;
    v4 = (char *)this + 24;
  }
  v5 = *((_DWORD *)v4 + 1);
  if ( v5 == 2 )
  {
    *((_DWORD *)v4 + 1) = 3;
    v34 = *((_QWORD *)this + 18);
    LOBYTE(pv) = 3;
    tson::write_buffer::push_back<enum tson::details::archive_marker>(v34, &pv);
    tson::write_buffer::push_back(*((tson::write_buffer **)this + 18), (char *)this + 10, 2u);
    *((_WORD *)this + 5) = 0;
  }
  else
  {
    if ( v5 )
      goto LABEL_13;
    *((_DWORD *)v4 + 1) = 1;
    v6 = *((_QWORD *)this + 18);
    v7 = *(_QWORD *)(v6 + 2080);
    v8 = *(char **)(v6 + 2072);
    if ( (unsigned __int64)v8 < v7 )
      goto LABEL_12;
    v9 = v7 - *(_QWORD *)(v6 + 2064);
    v10 = 1;
    if ( v9 > 1 )
      v10 = v9;
    v11 = 2 * v10;
    v12 = (char *)CoTaskMemAlloc(2 * v10);
    v13 = v12;
    if ( v12 )
    {
      v14 = *(const void **)(v6 + 2064);
      v15 = *(_QWORD *)(v6 + 2072) - (_QWORD)v14;
      memcpy_s_1(v12, v11, v14, v15);
      pv = *(LPVOID *)v6;
      if ( pv )
      {
        LastError = GetLastError();
        CoTaskMemFree(pv);
        SetLastError(LastError);
      }
      *(_QWORD *)v6 = v13;
      v8 = &v13[v15];
      *(_QWORD *)(v6 + 2072) = &v13[v15];
      *(_QWORD *)(v6 + 2080) = &v13[v11];
      *(_QWORD *)(v6 + 2064) = v13;
LABEL_12:
      *v8 = 1;
      ++*(_QWORD *)(v6 + 2072);
      goto LABEL_13;
    }
    *(_BYTE *)(v6 + 8) = 1;
  }
LABEL_13:
  *((_QWORD *)this + 2) = 0;
  if ( *((_DWORD *)v4 + 1) == 3 )
    goto LABEL_33;
  if ( !*(_QWORD *)this )
  {
    *((_BYTE *)this + 8) = 1;
    *(_QWORD *)this = "-";
  }
  v16 = *((_QWORD *)this + 18);
  *((_QWORD *)this + 2) = *(_QWORD *)(v16 + 2072) - *(_QWORD *)(v16 + 2064);
  v17 = *(_QWORD *)(v16 + 2080);
  v18 = *(char **)(v16 + 2072);
  if ( (unsigned __int64)v18 >= v17 )
  {
    v19 = v17 - *(_QWORD *)(v16 + 2064);
    v20 = 1;
    if ( v19 > 1 )
      v20 = v19;
    v21 = 2 * v20;
    v22 = (char *)CoTaskMemAlloc(2 * v20);
    v23 = v22;
    if ( !v22 )
    {
      *(_BYTE *)(v16 + 8) = 1;
      goto LABEL_24;
    }
    v24 = *(const void **)(v16 + 2064);
    v25 = *(_QWORD *)(v16 + 2072) - (_QWORD)v24;
    memcpy_s_1(v22, v21, v24, v25);
    v26 = *(void **)v16;
    if ( *(_QWORD *)v16 )
    {
      v36 = GetLastError();
      CoTaskMemFree(v26);
      SetLastError(v36);
    }
    *(_QWORD *)v16 = v23;
    v18 = &v23[v25];
    *(_QWORD *)(v16 + 2080) = &v23[v21];
    *(_QWORD *)(v16 + 2072) = &v23[v25];
    *(_QWORD *)(v16 + 2064) = v23;
  }
  *v18 = 5;
  ++*(_QWORD *)(v16 + 2072);
LABEL_24:
  v27 = *((_QWORD *)this + 18);
  if ( *(_QWORD *)(v27 + 2072) < *(_QWORD *)(v27 + 2080)
    || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
  {
    *(_BYTE *)(*(_QWORD *)(v27 + 2072))++ = *((_BYTE *)this + 8);
  }
  v28 = *((_QWORD *)this + 18);
  v29 = *((unsigned __int8 *)this + 8);
  v30 = *(const void **)this;
  if ( *(_QWORD *)(v28 + 2080) - *(_QWORD *)(v28 + 2072) < v29
    && !tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), *((unsigned __int8 *)this + 8)) )
  {
    goto LABEL_32;
  }
  if ( v29 )
  {
    v31 = *(void **)(v28 + 2072);
    if ( !v31 )
      goto LABEL_29;
    v33 = *(_QWORD *)(v28 + 2080) - (_QWORD)v31;
    if ( v30 && v33 >= v29 )
    {
      memcpy_0(v31, v30, v29);
      goto LABEL_31;
    }
    memset_0(v31, 0, *(_QWORD *)(v28 + 2080) - (_QWORD)v31);
    if ( v30 )
    {
      if ( v33 >= v29 )
        goto LABEL_31;
      *(_DWORD *)_o__errno() = 34;
    }
    else
    {
LABEL_29:
      *(_DWORD *)_o__errno() = 22;
    }
    invalid_parameter_noinfo();
  }
LABEL_31:
  *(_QWORD *)(v28 + 2072) += v29;
LABEL_32:
  *(_QWORD *)this = 0;
LABEL_33:
  v32 = *((_QWORD *)v1 + 13);
  if ( v32 >= 0x19 )
  {
    *v1 = 1;
  }
  else
  {
    *(_DWORD *)&v1[4 * v32 + 4] = 0;
    ++*((_QWORD *)v1 + 13);
  }
}

```

## disassembly

```asm
0x1800700e0  push    rbx
0x1800700e2  push    r12
0x1800700e4  sub     rsp, 38h
0x1800700e8  lea     rbx, [rcx+18h]
0x1800700ec  mov     [rsp+48h+arg_8], rbp
0x1800700f1  mov     rax, [rbx+68h]
0x1800700f5  mov     [rsp+48h+arg_10], rsi
0x1800700fa  mov     rsi, rcx
0x1800700fd  test    rax, rax
0x180070100  jz      loc_1800703D8
0x180070106  lea     rbp, [rbx-4]
0x18007010a  lea     rbp, [rbp+rax*4+0]
0x18007010f  mov     eax, [rbp+4]
0x180070112  xor     r12d, r12d
0x180070115  mov     [rsp+48h+arg_18], rdi
0x18007011a  mov     [rsp+48h+var_18], r13
0x18007011f  mov     [rsp+48h+var_20], r14
0x180070124  mov     [rsp+48h+var_28], r15
0x180070129  cmp     eax, 2
0x18007012c  jz      loc_1800703E3
0x180070132  test    eax, eax
0x180070134  jnz     loc_1800701E4
0x18007013a  mov     dword ptr [rbp+4], 1
0x180070141  mov     r14, [rcx+90h]
0x180070148  mov     rdx, [r14+820h]
0x18007014f  mov     rcx, [r14+818h]
0x180070156  cmp     rcx, rdx
0x180070159  jb      short loc_1800701DA
0x18007015b  sub     rdx, [r14+810h]
0x180070162  mov     eax, 1
0x180070167  cmp     rdx, rax
0x18007016a  cmova   rax, rdx
0x18007016e  lea     r13, [rax+rax]
0x180070172  mov     rcx, r13; cb
0x180070175  call    cs:__imp_CoTaskMemAlloc
0x18007017b  mov     r15, rax
0x18007017e  test    rax, rax
0x180070181  jz      loc_180070440
0x180070187  mov     r8, [r14+810h]; Source
0x18007018e  mov     rdx, r13; DestinationSize
0x180070191  mov     r12, [r14+818h]
0x180070198  mov     rcx, rax; Destination
0x18007019b  sub     r12, r8
0x18007019e  mov     r9, r12; SourceSize
0x1800701a1  call    memcpy_s_1
0x1800701a6  mov     rax, [r14]
0x1800701a9  mov     [rsp+48h+pv], rax
0x1800701ae  test    rax, rax
0x1800701b1  jnz     loc_180070420
0x1800701b7  mov     [r14], r15
0x1800701ba  lea     rcx, [r12+r15]
0x1800701be  lea     rax, [r15+r13]
0x1800701c2  mov     [r14+818h], rcx
0x1800701c9  mov     [r14+820h], rax
0x1800701d0  xor     r12d, r12d
0x1800701d3  mov     [r14+810h], r15
0x1800701da  mov     byte ptr [rcx], 1
0x1800701dd  inc     qword ptr [r14+818h]
0x1800701e4  mov     [rsi+10h], r12
0x1800701e8  cmp     dword ptr [rbp+4], 3
0x1800701ec  jz      loc_18007032C
0x1800701f2  cmp     qword ptr [rsi], 0
0x1800701f6  jz      loc_18007044A
0x1800701fc  mov     r14, [rsi+90h]
0x180070203  mov     rax, [r14+818h]
0x18007020a  sub     rax, [r14+810h]
0x180070211  mov     [rsi+10h], rax
0x180070215  mov     rdx, [r14+820h]
0x18007021c  mov     rcx, [r14+818h]
0x180070223  cmp     rcx, rdx
0x180070226  jb      short loc_1800702A2
0x180070228  sub     rdx, [r14+810h]
0x18007022f  mov     eax, 1
0x180070234  cmp     rdx, rax
0x180070237  cmova   rax, rdx
0x18007023b  lea     r12, [rax+rax]
0x18007023f  mov     rcx, r12; cb
0x180070242  call    cs:__imp_CoTaskMemAlloc
0x180070248  mov     rbp, rax
0x18007024b  test    rax, rax
0x18007024e  jz      loc_18007047B
0x180070254  mov     r8, [r14+810h]; Source
0x18007025b  mov     rdx, r12; DestinationSize
0x18007025e  mov     r15, [r14+818h]
0x180070265  mov     rcx, rax; Destination
0x180070268  sub     r15, r8
0x18007026b  mov     r9, r15; SourceSize
0x18007026e  call    memcpy_s_1
0x180070273  mov     r13, [r14]
0x180070276  test    r13, r13
0x180070279  jnz     loc_18007045D
0x18007027f  mov     [r14], rbp
0x180070282  lea     rax, [r12+rbp]
0x180070286  lea     rcx, [r15+rbp]
0x18007028a  mov     [r14+820h], rax
0x180070291  mov     [r14+818h], rcx
0x180070298  xor     r12d, r12d
0x18007029b  mov     [r14+810h], rbp
0x1800702a2  mov     byte ptr [rcx], 5
0x1800702a5  inc     qword ptr [r14+818h]
0x1800702ac  mov     rdi, [rsi+90h]
0x1800702b3  mov     rax, [rdi+820h]
0x1800702ba  cmp     [rdi+818h], rax
0x1800702c1  jnb     loc_180070488
0x1800702c7  mov     rcx, [rdi+818h]
0x1800702ce  movzx   eax, byte ptr [rsi+8]
0x1800702d2  mov     [rcx], al
0x1800702d4  inc     qword ptr [rdi+818h]
0x1800702db  mov     rdi, [rsi+90h]
0x1800702e2  movzx   ebp, byte ptr [rsi+8]
0x1800702e6  mov     r15, [rsi]
0x1800702e9  mov     rax, [rdi+820h]
0x1800702f0  sub     rax, [rdi+818h]
0x1800702f7  cmp     rax, rbp
0x1800702fa  jb      loc_1800703C0
0x180070300  test    rbp, rbp
0x180070303  jz      short loc_180070322
0x180070305  mov     rcx, [rdi+818h]; void *
0x18007030c  test    rcx, rcx
0x18007030f  jnz     short loc_180070369
0x180070311  call    cs:__imp__o__errno
0x180070317  mov     dword ptr [rax], 16h
0x18007031d  call    _invalid_parameter_noinfo
0x180070322  add     [rdi+818h], rbp
0x180070329  mov     [rsi], r12
0x18007032c  mov     rax, [rbx+68h]
0x180070330  mov     r15, [rsp+48h+var_28]
0x180070335  mov     r14, [rsp+48h+var_20]
0x18007033a  mov     r13, [rsp+48h+var_18]
0x18007033f  mov     rdi, [rsp+48h+arg_18]
0x180070344  mov     rsi, [rsp+48h+arg_10]
0x180070349  mov     rbp, [rsp+48h+arg_8]
0x18007034e  cmp     rax, 19h
0x180070352  jnb     loc_1800704A2
0x180070358  mov     [rbx+rax*4+4], r12d
0x18007035d  inc     qword ptr [rbx+68h]
0x180070361  add     rsp, 38h
0x180070365  pop     r12
0x180070367  pop     rbx
0x180070368  retn
0x180070369  mov     r14, [rdi+820h]
0x180070370  sub     r14, rcx
0x180070373  test    r15, r15
0x180070376  jnz     short loc_1800703AB
0x180070378  mov     r8, r14; Size
0x18007037b  xor     edx, edx; Val
0x18007037d  call    memset_0
0x180070382  test    r15, r15
0x180070385  jz      short loc_18007039A
0x180070387  cmp     r14, rbp
0x18007038a  jnb     short loc_180070322
0x18007038c  call    cs:__imp__o__errno
0x180070392  mov     dword ptr [rax], 22h ; '"'
0x180070398  jmp     short loc_18007031D
0x18007039a  call    cs:__imp__o__errno
0x1800703a0  mov     dword ptr [rax], 16h
0x1800703a6  jmp     loc_18007031D
0x1800703ab  cmp     r14, rbp
0x1800703ae  jb      short loc_180070378
0x1800703b0  mov     r8, rbp; Size
0x1800703b3  mov     rdx, r15; Src
0x1800703b6  call    memcpy_0
0x1800703bb  jmp     loc_180070322
0x1800703c0  mov     rdx, rbp; unsigned __int64
0x1800703c3  mov     rcx, rdi; this
0x1800703c6  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800703cb  test    al, al
0x1800703cd  jnz     loc_180070300
0x1800703d3  jmp     loc_180070329
0x1800703d8  mov     byte ptr [rbx], 1
0x1800703db  mov     rbp, rbx
0x1800703de  jmp     loc_18007010F
0x1800703e3  mov     dword ptr [rbp+4], 3
0x1800703ea  lea     rdx, [rsp+48h+pv]
0x1800703ef  mov     rcx, [rcx+90h]
0x1800703f6  mov     byte ptr [rsp+48h+pv], 3
0x1800703fb  call    ??$push_back@W4archive_marker@details@tson@@@write_buffer@tson@@QEAA_NAEBW4archive_marker@details@1@@Z; tson::write_buffer::push_back<tson::details::archive_marker>(tson::details::archive_marker const &)
0x180070400  mov     rcx, [rsi+90h]; this
0x180070407  lea     rdx, [rsi+0Ah]; void *
0x18007040b  mov     r8d, 2; unsigned __int64
0x180070411  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x180070416  mov     [rsi+0Ah], r12w
0x18007041b  jmp     loc_1800701E4
0x180070420  call    cs:__imp_GetLastError
0x180070426  mov     rcx, [rsp+48h+pv]; pv
0x18007042b  mov     edi, eax
0x18007042d  call    cs:__imp_CoTaskMemFree
0x180070433  mov     ecx, edi; dwErrCode
0x180070435  call    cs:__imp_SetLastError
0x18007043b  jmp     loc_1800701B7
0x180070440  mov     byte ptr [r14+8], 1
0x180070445  jmp     loc_1800701E4
0x18007044a  lea     rax, asc_180238410; "-"
0x180070451  mov     byte ptr [rsi+8], 1
0x180070455  mov     [rsi], rax
0x180070458  jmp     loc_1800701FC
0x18007045d  call    cs:__imp_GetLastError
0x180070463  mov     rcx, r13; pv
0x180070466  mov     edi, eax
0x180070468  call    cs:__imp_CoTaskMemFree
0x18007046e  mov     ecx, edi; dwErrCode
0x180070470  call    cs:__imp_SetLastError
0x180070476  jmp     loc_18007027F
0x18007047b  mov     byte ptr [r14+8], 1
0x180070480  xor     r12d, r12d
0x180070483  jmp     loc_1800702AC
0x180070488  mov     edx, 1; unsigned __int64
0x18007048d  mov     rcx, rdi; this
0x180070490  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180070495  test    al, al
0x180070497  jz      loc_1800702DB
0x18007049d  jmp     loc_1800702C7
0x1800704a2  mov     byte ptr [rbx], 1
0x1800704a5  jmp     loc_180070361
```
