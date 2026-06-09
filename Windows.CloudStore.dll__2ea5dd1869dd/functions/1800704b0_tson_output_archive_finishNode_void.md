# tson::output_archive::finishNode(void)

- ea: `0x1800704b0`
- end: `0x1800707a8`
- name: `?finishNode@output_archive@tson@@QEAAXXZ`
- size: `760`
- prototype: `void __fastcall(tson::output_archive *__hidden this)`
- caller_count: `19`
- callee_count: `6`
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

- `0x1800704b0`
- `0x180074110`
- `0x18007b050`
- `0x180087dcc`
- `0x1800a6f3c`
- `0x180124678`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007070b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007070b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070738`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007071e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007074b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007071e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007074b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070716`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070743`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070716`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070743`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007056c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007064c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007056c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007064c`

## pseudocode

```c
void __fastcall tson::output_archive::finishNode(tson::output_archive *this)
{
  char *v1; // rbx
  __int64 v3; // rax
  char *v4; // rcx
  int v5; // ecx
  wil::details::in1diag3 *v6; // rcx
  _QWORD *v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rsi
  unsigned __int64 v10; // rax
  char *v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  rsize_t v14; // r15
  char *v15; // rax
  char *v16; // rbp
  const void *v17; // r8
  rsize_t v18; // r14
  void *v19; // r12
  __int64 v20; // rax
  int v21; // ecx
  unsigned __int64 v22; // rax
  char *v23; // rcx
  unsigned __int64 v24; // rax
  __int64 v25; // rcx
  rsize_t v26; // r15
  char *v27; // rax
  char *v28; // rbp
  const void *v29; // r8
  rsize_t v30; // r14
  void *v31; // r12
  unsigned __int64 v32; // rdx
  tson::write_buffer *v33; // rcx
  DWORD v34; // edi
  DWORD LastError; // edi
  tson::write_buffer *v36; // rcx
  char v37; // [rsp+50h] [rbp+8h] BYREF

  v1 = (char *)this + 24;
  v3 = *((_QWORD *)this + 16);
  if ( v3 )
  {
    v4 = (char *)this + 4 * v3 + 20;
  }
  else
  {
    *v1 = 1;
    v4 = (char *)this + 24;
  }
  v5 = *((_DWORD *)v4 + 1);
  if ( v5 == 2 )
  {
    v6 = (wil::details::in1diag3 *)*((_QWORD *)this + 2);
    v7 = (_QWORD *)*((_QWORD *)this + 18);
    if ( v6 )
    {
      v8 = v7[258];
      if ( (unsigned __int64)v6 >= v7[260] - v8 )
        wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
      v7[259] = (char *)v6 + v8;
      v9 = *((_QWORD *)this + 18);
      *((_QWORD *)this + 2) = 0;
      v10 = *(_QWORD *)(v9 + 2080);
      v11 = *(char **)(v9 + 2072);
      if ( (unsigned __int64)v11 < v10 )
        goto LABEL_13;
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
          LastError = GetLastError();
          CoTaskMemFree(v19);
          SetLastError(LastError);
        }
        *(_QWORD *)v9 = v16;
        v11 = &v16[v18];
        *(_QWORD *)(v9 + 2072) = &v16[v18];
        *(_QWORD *)(v9 + 2080) = &v16[v14];
        *(_QWORD *)(v9 + 2064) = v16;
LABEL_13:
        *v11 = 7;
        ++*(_QWORD *)(v9 + 2072);
        goto LABEL_14;
      }
      goto LABEL_32;
    }
    v37 = 3;
    tson::write_buffer::push_back<enum tson::details::archive_marker>(v7, &v37);
    v36 = (tson::write_buffer *)*((_QWORD *)this + 18);
    *((_WORD *)this + 5) = 0;
    tson::write_buffer::push_back(v36, (char *)this + 10, 2u);
    goto LABEL_35;
  }
  if ( v5 )
  {
    v21 = v5 - 1;
    if ( v21 )
    {
      if ( v21 != 2 )
        goto LABEL_14;
LABEL_35:
      v37 = 4;
      goto LABEL_36;
    }
LABEL_18:
    v9 = *((_QWORD *)this + 18);
    v22 = *(_QWORD *)(v9 + 2080);
    v23 = *(char **)(v9 + 2072);
    if ( (unsigned __int64)v23 >= v22 )
    {
      v24 = v22 - *(_QWORD *)(v9 + 2064);
      v25 = 1;
      if ( v24 > 1 )
        v25 = v24;
      v26 = 2 * v25;
      v27 = (char *)CoTaskMemAlloc(2 * v25);
      v28 = v27;
      if ( !v27 )
      {
LABEL_32:
        *(_BYTE *)(v9 + 8) = 1;
        goto LABEL_14;
      }
      v29 = *(const void **)(v9 + 2064);
      v30 = *(_QWORD *)(v9 + 2072) - (_QWORD)v29;
      memcpy_s_1(v27, v26, v29, v30);
      v31 = *(void **)v9;
      if ( *(_QWORD *)v9 )
      {
        v34 = GetLastError();
        CoTaskMemFree(v31);
        SetLastError(v34);
      }
      *(_QWORD *)v9 = v28;
      v23 = &v28[v30];
      *(_QWORD *)(v9 + 2072) = &v28[v30];
      *(_QWORD *)(v9 + 2080) = &v28[v26];
      *(_QWORD *)(v9 + 2064) = v28;
    }
    *v23 = 2;
    ++*(_QWORD *)(v9 + 2072);
    goto LABEL_14;
  }
  v32 = *((_QWORD *)this + 2);
  v33 = (tson::write_buffer *)*((_QWORD *)this + 18);
  if ( !v32 )
  {
    v37 = 1;
    tson::write_buffer::push_back<enum tson::details::archive_marker>(v33, &v37);
    goto LABEL_18;
  }
  tson::write_buffer::set_position(v33, v32);
  v37 = 8;
  *((_QWORD *)this + 2) = 0;
LABEL_36:
  tson::write_buffer::push_back<enum tson::details::archive_marker>(*((_QWORD *)this + 18), &v37);
LABEL_14:
  v20 = *((_QWORD *)v1 + 13);
  if ( v20 )
    *((_QWORD *)v1 + 13) = v20 - 1;
  else
    *v1 = 1;
}

```

## disassembly

```asm
0x1800704b0  push    rbx
0x1800704b2  push    rdi
0x1800704b3  sub     rsp, 38h
0x1800704b7  lea     rbx, [rcx+18h]
0x1800704bb  mov     rdi, rcx
0x1800704be  mov     rax, [rbx+68h]
0x1800704c2  test    rax, rax
0x1800704c5  jz      loc_1800706C6
0x1800704cb  lea     rcx, [rbx-4]
0x1800704cf  lea     rcx, [rcx+rax*4]
0x1800704d3  mov     ecx, [rcx+4]
0x1800704d6  mov     [rsp+48h+arg_8], rbp
0x1800704db  mov     [rsp+48h+arg_10], rsi
0x1800704e0  mov     [rsp+48h+var_18], r12
0x1800704e5  mov     [rsp+48h+var_20], r14
0x1800704ea  mov     [rsp+48h+var_28], r15
0x1800704ef  cmp     ecx, 2
0x1800704f2  jnz     loc_180070607
0x1800704f8  mov     rcx, [rdi+10h]; this
0x1800704fc  mov     r8, [rdi+90h]
0x180070503  test    rcx, rcx
0x180070506  jz      loc_180070756
0x18007050c  mov     rdx, [r8+810h]
0x180070513  mov     rax, [r8+820h]
0x18007051a  sub     rax, rdx
0x18007051d  cmp     rcx, rax
0x180070520  jnb     loc_180070732
0x180070526  lea     rax, [rdx+rcx]
0x18007052a  xor     r9d, r9d
0x18007052d  mov     [r8+818h], rax
0x180070534  mov     rsi, [rdi+90h]
0x18007053b  mov     [rdi+10h], r9
0x18007053f  mov     rax, [rsi+820h]
0x180070546  mov     rcx, [rsi+818h]
0x18007054d  cmp     rcx, rax
0x180070550  jb      short loc_1800705C9
0x180070552  sub     rax, [rsi+810h]
0x180070559  mov     ecx, 1
0x18007055e  cmp     rax, rcx
0x180070561  cmova   rcx, rax
0x180070565  lea     r15, [rcx+rcx]
0x180070569  mov     rcx, r15; cb
0x18007056c  call    cs:__imp_CoTaskMemAlloc
0x180070572  mov     rbp, rax
0x180070575  test    rax, rax
0x180070578  jz      loc_180070729
0x18007057e  mov     r8, [rsi+810h]; Source
0x180070585  mov     rdx, r15; DestinationSize
0x180070588  mov     r14, [rsi+818h]
0x18007058f  mov     rcx, rax; Destination
0x180070592  sub     r14, r8
0x180070595  mov     r9, r14; SourceSize
0x180070598  call    memcpy_s_1
0x18007059d  mov     r12, [rsi]
0x1800705a0  test    r12, r12
0x1800705a3  jnz     loc_180070738
0x1800705a9  mov     [rsi], rbp
0x1800705ac  lea     rcx, [r14+rbp]
0x1800705b0  lea     rax, [r15+rbp]
0x1800705b4  mov     [rsi+818h], rcx
0x1800705bb  mov     [rsi+820h], rax
0x1800705c2  mov     [rsi+810h], rbp
0x1800705c9  mov     byte ptr [rcx], 7
0x1800705cc  inc     qword ptr [rsi+818h]
0x1800705d3  mov     rax, [rbx+68h]
0x1800705d7  test    rax, rax
0x1800705da  jz      loc_1800707A0
0x1800705e0  dec     rax
0x1800705e3  mov     [rbx+68h], rax
0x1800705e7  mov     r15, [rsp+48h+var_28]
0x1800705ec  mov     r14, [rsp+48h+var_20]
0x1800705f1  mov     r12, [rsp+48h+var_18]
0x1800705f6  mov     rsi, [rsp+48h+arg_10]
0x1800705fb  mov     rbp, [rsp+48h+arg_8]
0x180070600  add     rsp, 38h
0x180070604  pop     rdi
0x180070605  pop     rbx
0x180070606  retn
0x180070607  test    ecx, ecx
0x180070609  jz      loc_1800706D1
0x18007060f  sub     ecx, 1
0x180070612  jnz     loc_1800706B8
0x180070618  mov     rsi, [rdi+90h]
0x18007061f  mov     rax, [rsi+820h]
0x180070626  mov     rcx, [rsi+818h]
0x18007062d  cmp     rcx, rax
0x180070630  jb      short loc_1800706A9
0x180070632  sub     rax, [rsi+810h]
0x180070639  mov     ecx, 1
0x18007063e  cmp     rax, rcx
0x180070641  cmova   rcx, rax
0x180070645  lea     r15, [rcx+rcx]
0x180070649  mov     rcx, r15; cb
0x18007064c  call    cs:__imp_CoTaskMemAlloc
0x180070652  mov     rbp, rax
0x180070655  test    rax, rax
0x180070658  jz      loc_180070729
0x18007065e  mov     r8, [rsi+810h]; Source
0x180070665  mov     rdx, r15; DestinationSize
0x180070668  mov     r14, [rsi+818h]
0x18007066f  mov     rcx, rax; Destination
0x180070672  sub     r14, r8
0x180070675  mov     r9, r14; SourceSize
0x180070678  call    memcpy_s_1
0x18007067d  mov     r12, [rsi]
0x180070680  test    r12, r12
0x180070683  jnz     loc_18007070B
0x180070689  mov     [rsi], rbp
0x18007068c  lea     rcx, [r14+rbp]
0x180070690  lea     rax, [r15+rbp]
0x180070694  mov     [rsi+818h], rcx
0x18007069b  mov     [rsi+820h], rax
0x1800706a2  mov     [rsi+810h], rbp
0x1800706a9  mov     byte ptr [rcx], 2
0x1800706ac  inc     qword ptr [rsi+818h]
0x1800706b3  jmp     loc_1800705D3
0x1800706b8  cmp     ecx, 2
0x1800706bb  jnz     loc_1800705D3
0x1800706c1  jmp     loc_180070785
0x1800706c6  mov     byte ptr [rbx], 1
0x1800706c9  mov     rcx, rbx
0x1800706cc  jmp     loc_1800704D3
0x1800706d1  mov     rdx, [rdi+10h]; unsigned __int64
0x1800706d5  mov     rcx, [rdi+90h]; this
0x1800706dc  test    rdx, rdx
0x1800706df  jz      short loc_1800706F7
0x1800706e1  call    ?set_position@write_buffer@tson@@QEAAX_K@Z; tson::write_buffer::set_position(unsigned __int64)
0x1800706e6  xor     r9d, r9d
0x1800706e9  mov     [rsp+48h+arg_0], 8
0x1800706ee  mov     [rdi+10h], r9
0x1800706f2  jmp     loc_18007078A
0x1800706f7  lea     rdx, [rsp+48h+arg_0]
0x1800706fc  mov     [rsp+48h+arg_0], 1
0x180070701  call    ??$push_back@W4archive_marker@details@tson@@@write_buffer@tson@@QEAA_NAEBW4archive_marker@details@1@@Z; tson::write_buffer::push_back<tson::details::archive_marker>(tson::details::archive_marker const &)
0x180070706  jmp     loc_180070618
0x18007070b  call    cs:__imp_GetLastError
0x180070711  mov     rcx, r12; pv
0x180070714  mov     edi, eax
0x180070716  call    cs:__imp_CoTaskMemFree
0x18007071c  mov     ecx, edi; dwErrCode
0x18007071e  call    cs:__imp_SetLastError
0x180070724  jmp     loc_180070689
0x180070729  mov     byte ptr [rsi+8], 1
0x18007072d  jmp     loc_1800705D3
0x180070732  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180070738  call    cs:__imp_GetLastError
0x18007073e  mov     rcx, r12; pv
0x180070741  mov     edi, eax
0x180070743  call    cs:__imp_CoTaskMemFree
0x180070749  mov     ecx, edi; dwErrCode
0x18007074b  call    cs:__imp_SetLastError
0x180070751  jmp     loc_1800705A9
0x180070756  lea     rdx, [rsp+48h+arg_0]
0x18007075b  mov     [rsp+48h+arg_0], 3
0x180070760  mov     rcx, r8
0x180070763  call    ??$push_back@W4archive_marker@details@tson@@@write_buffer@tson@@QEAA_NAEBW4archive_marker@details@1@@Z; tson::write_buffer::push_back<tson::details::archive_marker>(tson::details::archive_marker const &)
0x180070768  mov     rcx, [rdi+90h]; this
0x18007076f  lea     rdx, [rdi+0Ah]; void *
0x180070773  xor     r9d, r9d
0x180070776  mov     r8d, 2; unsigned __int64
0x18007077c  mov     [rdx], r9w
0x180070780  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x180070785  mov     [rsp+48h+arg_0], 4
0x18007078a  mov     rcx, [rdi+90h]
0x180070791  lea     rdx, [rsp+48h+arg_0]
0x180070796  call    ??$push_back@W4archive_marker@details@tson@@@write_buffer@tson@@QEAA_NAEBW4archive_marker@details@1@@Z; tson::write_buffer::push_back<tson::details::archive_marker>(tson::details::archive_marker const &)
0x18007079b  jmp     loc_1800705D3
0x1800707a0  mov     byte ptr [rbx], 1
0x1800707a3  jmp     loc_1800705E7
```
