# tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x18006fab0`
- end: `0x1800700cd`
- name: `?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `1565`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ebb8`
- `0x1800460d4`
- `0x18006f008`

## callees

- `0x18006fab0`
- `0x1800700e0`
- `0x1800704b0`
- `0x1800707b0`
- `0x180070e6c`
- `0x1800710d0`
- `0x180071630`
- `0x1800741f4`
- `0x1800a6f3c`
- `0x1800f75f0`
- `0x1801201a0`
- `0x180124678`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ffeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ffeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ffff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ffff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fff7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fff7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006fb6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006fb6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::details::shared_data<0,0,0>::serialize_data(__int64 *a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // r15d
  char v6; // r13
  unsigned __int64 v7; // rdx
  char *v8; // rcx
  unsigned __int64 v9; // rdx
  __int64 v10; // rax
  rsize_t v11; // r12
  char *v12; // rax
  char *v13; // r14
  const void *v14; // r8
  rsize_t v15; // r15
  tson::write_buffer *v16; // rbx
  char v17; // r14
  tson::write_buffer *v18; // rbx
  __int64 v19; // rcx
  wil::details::in1diag3 *v20; // rcx
  tson::write_buffer *v21; // rax
  _DWORD *v22; // r8
  unsigned __int64 v23; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rax
  unsigned __int64 v28; // rcx
  _DWORD *v29; // rdx
  __int64 *v30; // rbx
  __int64 *i; // r14
  unsigned __int64 v32; // rcx
  _DWORD *v33; // rdx
  struct tson::output_archive *v34; // rbx
  struct tson::output_archive *j; // r14
  struct wil::StoredFailureInfo *v36; // r8
  unsigned __int64 v37; // rcx
  _DWORD *v38; // rdx
  struct tson::output_archive *v39; // r14
  struct tson::output_archive *k; // rbx
  struct tip2::test_flag *v41; // r8
  DWORD LastError; // ebx
  int v43; // eax
  int v44; // eax
  int v45; // eax
  __int128 v47; // [rsp+40h] [rbp-C0h]
  __int128 v48; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v49; // [rsp+70h] [rbp-90h]
  LPVOID pv; // [rsp+80h] [rbp-80h]
  const char *v51; // [rsp+90h] [rbp-70h] BYREF
  char v52; // [rsp+98h] [rbp-68h]
  __int16 v53; // [rsp+9Ah] [rbp-66h]
  __int64 v54; // [rsp+A0h] [rbp-60h]
  _BYTE v55[4]; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD v56[6]; // [rsp+ACh] [rbp-54h] BYREF
  int v57; // [rsp+10Ch] [rbp+Ch]
  unsigned __int64 v58; // [rsp+110h] [rbp+10h]
  int v59; // [rsp+118h] [rbp+18h]
  tson::write_buffer *v60; // [rsp+120h] [rbp+20h]

  v3 = a3;
  if ( !a3 )
    return 0;
  v6 = *((_BYTE *)a1 + 33);
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55[0] = 0;
  memset(v56, 0, sizeof(v56));
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = (tson::write_buffer *)a2;
  v7 = *(_QWORD *)(a2 + 2080);
  v8 = *(char **)(a2 + 2072);
  if ( (unsigned __int64)v8 >= v7 )
  {
    v9 = v7 - *(_QWORD *)(a2 + 2064);
    v10 = 1;
    if ( v9 > 1 )
      v10 = v9;
    v11 = 2 * v10;
    v12 = (char *)CoTaskMemAlloc(2 * v10);
    v13 = v12;
    if ( !v12 )
    {
      *(_BYTE *)(a2 + 8) = 1;
      goto LABEL_10;
    }
    v14 = *(const void **)(a2 + 2064);
    v15 = *(_QWORD *)(a2 + 2072) - (_QWORD)v14;
    memcpy_s_1(v12, v11, v14, v15);
    pv = *(LPVOID *)a2;
    if ( pv )
    {
      LastError = GetLastError();
      CoTaskMemFree(pv);
      SetLastError(LastError);
    }
    *(_QWORD *)a2 = v13;
    *(_QWORD *)(a2 + 2064) = v13;
    v8 = &v13[v15];
    *(_QWORD *)(a2 + 2072) = &v13[v15];
    *(_QWORD *)(a2 + 2080) = &v13[v11];
    v3 = a3;
  }
  *v8 = 0x80;
  ++*(_QWORD *)(a2 + 2072);
LABEL_10:
  v16 = v60;
  if ( *((_QWORD *)v60 + 259) < *((_QWORD *)v60 + 260) || tson::write_buffer::reserve(v60, 1u) )
  {
    **((_BYTE **)v60 + 259) = v6;
    ++*((_QWORD *)v16 + 259);
  }
  if ( v58 >= 0x19 )
    v55[0] = 1;
  else
    *((_DWORD *)v56 + v58++) = 1;
  if ( (v3 & 4) != 0 )
  {
    v17 = *((_BYTE *)a1 + 33);
    if ( v17 )
    {
      v51 = "version";
      v52 = 7;
      if ( tson::output_archive::write_type((__int64)&v51, 0, 12) )
      {
        v18 = v60;
        if ( *((_QWORD *)v60 + 259) < *((_QWORD *)v60 + 260) || tson::write_buffer::reserve(v60, 1u) )
          *(_BYTE *)(*((_QWORD *)v18 + 259))++ = v17;
      }
    }
  }
  if ( (v3 & 1) != 0 )
  {
    if ( (*((_DWORD *)a1 + 5) & 0x40000) == 0 )
    {
LABEL_35:
      v51 = "log";
      v52 = 3;
      tson::output_archive::startNode((tson::output_archive *)&v51);
      v28 = a1[14];
      if ( v58 )
      {
        v29 = &v55[4 * v58];
      }
      else
      {
        v55[0] = 1;
        v29 = v56;
      }
      *v29 = 2;
      if ( v28 > 0xFFFF )
      {
        v43 = v59;
        if ( v59 >= 0 )
          v43 = -2147483637;
        v59 = v43;
      }
      v53 = v28;
      v30 = (__int64 *)a1[12];
      for ( i = &v30[a1[14]]; v30 != i; ++v30 )
        tson::output_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(
          (__int64)&v51,
          v30);
      tson::output_archive::finishNode((tson::output_archive *)&v51);
      v51 = "errors";
      v52 = 6;
      tson::output_archive::startNode((tson::output_archive *)&v51);
      v32 = a1[11];
      if ( v58 )
      {
        v33 = &v55[4 * v58];
      }
      else
      {
        v55[0] = 1;
        v33 = v56;
      }
      *v33 = 2;
      if ( v32 > 0xFFFF )
      {
        v44 = v59;
        if ( v59 >= 0 )
          v44 = -2147483637;
        v59 = v44;
      }
      v53 = v32;
      v34 = (struct tson::output_archive *)a1[9];
      for ( j = (struct tson::output_archive *)((char *)v34 + 168 * a1[11]);
            v34 != j;
            v34 = (struct tson::output_archive *)((char *)v34 + 168) )
      {
        tson::output_archive::startNode((tson::output_archive *)&v51);
        tson::save_nothrow((tson *)&v51, v34, v36);
        tson::output_archive::finishNode((tson::output_archive *)&v51);
      }
      tson::output_archive::finishNode((tson::output_archive *)&v51);
      v51 = "flags";
      v52 = 5;
      tson::output_archive::startNode((tson::output_archive *)&v51);
      v37 = a1[17];
      if ( v58 )
      {
        v38 = &v55[4 * v58];
      }
      else
      {
        v55[0] = 1;
        v38 = v56;
      }
      *v38 = 2;
      if ( v37 > 0xFFFF )
      {
        v45 = v59;
        if ( v59 >= 0 )
          v45 = -2147483637;
        v59 = v45;
      }
      v53 = v37;
      v39 = (struct tson::output_archive *)a1[15];
      for ( k = (struct tson::output_archive *)((char *)v39 + 104 * a1[17]);
            v39 != k;
            v39 = (struct tson::output_archive *)((char *)v39 + 104) )
      {
        tson::output_archive::startNode((tson::output_archive *)&v51);
        tson::save_nothrow((tson *)&v51, v39, v41);
        tson::output_archive::finishNode((tson::output_archive *)&v51);
      }
      tson::output_archive::finishNode((tson::output_archive *)&v51);
      goto LABEL_20;
    }
    v25 = a1[1];
    if ( v25 )
    {
      v26 = a1[1];
    }
    else
    {
      v25 = a1[3];
      v26 = v25;
      if ( !v25 )
      {
        v27 = 0;
LABEL_34:
        v51 = "name";
        v52 = 4;
        *(_QWORD *)&v47 = v26;
        *((_QWORD *)&v47 + 1) = v27;
        v48 = v47;
        v49 = 0;
        tson::output_archive::write_string<tson::ansistring_tag>((__int64)&v51, v26, (const void **)&v48);
        goto LABEL_35;
      }
    }
    v27 = -1;
    do
      ++v27;
    while ( *(_BYTE *)(v25 + v27) );
    goto LABEL_34;
  }
LABEL_20:
  v19 = *a1;
  if ( tip2::details::g_test_interface_exception_guard )
  {
    if ( !(unsigned __int8)((__int64 (__fastcall *)(__int64, const char **, _QWORD, _QWORD, _QWORD))tip2::details::g_test_interface_exception_guard)(
                             v19,
                             &v51,
                             v3,
                             0,
                             0) )
    {
      *((_BYTE *)a1 + 160) = 3;
      *((_WORD *)a1 + 81) = 16396;
      a1[21] = 0;
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64, const char **, _QWORD))(*(_QWORD *)v19 + 8LL))(v19, &v51, v3);
  }
  if ( v55[0] || v59 < 0 )
    goto LABEL_51;
  v21 = v60;
  if ( *((_BYTE *)v60 + 8) )
  {
    *((_QWORD *)v60 + 258) = 0;
    *((_QWORD *)v21 + 259) = 0;
    *((_QWORD *)v21 + 260) = 0;
LABEL_51:
    *((_DWORD *)a1 + 16) |= 0x100000u;
    return 0;
  }
  v22 = (_DWORD *)*((_QWORD *)v60 + 258);
  v23 = (unsigned int)*((_QWORD *)v60 + 259) - (unsigned int)v22;
  if ( v23 > 0xFFFFFF )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
  *v22 = v23 & 0x3F | (16 * v23) & 0x3F0000 | (4 * (_WORD)v23) & 0x3F00 | ((_DWORD)v23 << 6) & 0x3F000000 | 0x80408040;
  return *(_QWORD *)(a2 + 2064);
}

```

## disassembly

```asm
0x18006fab0  mov     [rsp-8+arg_8], rbx
0x18006fab5  push    rbp
0x18006fab6  push    rsi
0x18006fab7  push    rdi
0x18006fab8  push    r12
0x18006faba  push    r13
0x18006fabc  push    r14
0x18006fabe  push    r15
0x18006fac0  lea     rbp, [rsp-40h]
0x18006fac5  sub     rsp, 140h
0x18006facc  mov     rax, cs:__security_cookie
0x18006fad3  xor     rax, rsp
0x18006fad6  mov     [rbp+70h+var_40], rax
0x18006fada  mov     r15d, r8d
0x18006fadd  mov     [rsp+170h+var_140], r8d
0x18006fae2  mov     rsi, rdx
0x18006fae5  mov     rdi, rcx
0x18006fae8  test    r8d, r8d
0x18006faeb  jz      loc_18006FF95
0x18006faf1  movzx   r13d, byte ptr [rcx+21h]
0x18006faf6  xor     r12d, r12d
0x18006faf9  mov     [rbp+70h+var_E0], r12
0x18006fafd  mov     [rbp+70h+var_D8], r12b
0x18006fb01  mov     [rbp+70h+var_D6], r12w
0x18006fb06  mov     [rbp+70h+var_D0], r12
0x18006fb0a  mov     [rbp+70h+var_C8], r12b
0x18006fb0e  xorps   xmm0, xmm0
0x18006fb11  xor     eax, eax
0x18006fb13  movups  [rbp+70h+var_C4], xmm0
0x18006fb17  movups  [rbp+70h+var_B4], xmm0
0x18006fb1b  movups  [rbp+70h+var_A4], xmm0
0x18006fb1f  movups  [rbp+70h+var_94], xmm0
0x18006fb23  movups  [rbp+70h+var_84], xmm0
0x18006fb27  movups  [rbp+70h+var_74], xmm0
0x18006fb2b  mov     [rbp+70h+var_64], eax
0x18006fb2e  mov     [rbp+70h+var_60], r12
0x18006fb32  mov     [rbp+70h+var_58], r12d
0x18006fb36  mov     [rbp+70h+var_50], rdx
0x18006fb3a  mov     rdx, [rdx+820h]
0x18006fb41  mov     rcx, [rsi+818h]
0x18006fb48  cmp     rcx, rdx
0x18006fb4b  jb      loc_18006FBD4
0x18006fb51  sub     rdx, [rsi+810h]
0x18006fb58  mov     eax, 1
0x18006fb5d  cmp     rdx, rax
0x18006fb60  cmova   rax, rdx
0x18006fb64  lea     r12, [rax+rax]
0x18006fb68  mov     rcx, r12; cb
0x18006fb6b  call    cs:__imp_CoTaskMemAlloc
0x18006fb71  mov     r14, rax
0x18006fb74  test    rax, rax
0x18006fb77  jz      loc_18007000A
0x18006fb7d  mov     r8, [rsi+810h]; Source
0x18006fb84  mov     r15, [rsi+818h]
0x18006fb8b  sub     r15, r8
0x18006fb8e  mov     r9, r15; SourceSize
0x18006fb91  mov     rdx, r12; DestinationSize
0x18006fb94  mov     rcx, rax; Destination
0x18006fb97  call    memcpy_s_1
0x18006fb9c  mov     rax, [rsi]
0x18006fb9f  mov     [rbp+70h+pv], rax
0x18006fba3  test    rax, rax
0x18006fba6  jnz     loc_18006FFEB
0x18006fbac  mov     [rsi], r14
0x18006fbaf  mov     [rsi+810h], r14
0x18006fbb6  lea     rcx, [r15+r14]
0x18006fbba  mov     [rsi+818h], rcx
0x18006fbc1  lea     rax, [r12+r14]
0x18006fbc5  mov     [rsi+820h], rax
0x18006fbcc  mov     r15d, [rsp+170h+var_140]
0x18006fbd1  xor     r12d, r12d
0x18006fbd4  mov     byte ptr [rcx], 80h
0x18006fbd7  inc     qword ptr [rsi+818h]
0x18006fbde  mov     rbx, [rbp+70h+var_50]
0x18006fbe2  mov     rax, [rbx+820h]
0x18006fbe9  cmp     [rbx+818h], rax
0x18006fbf0  jnb     loc_180070016
0x18006fbf6  mov     rax, [rbx+818h]
0x18006fbfd  mov     [rax], r13b
0x18006fc00  inc     qword ptr [rbx+818h]
0x18006fc07  mov     rax, [rbp+70h+var_60]
0x18006fc0b  cmp     rax, 19h
0x18006fc0f  jnb     loc_180070030
0x18006fc15  mov     dword ptr [rbp+rax*4+70h+var_C4], 1
0x18006fc1d  inc     [rbp+70h+var_60]
0x18006fc21  test    r15b, 4
0x18006fc25  jz      short loc_18006FC7B
0x18006fc27  movzx   r14d, byte ptr [rdi+21h]
0x18006fc2c  test    r14b, r14b
0x18006fc2f  jz      short loc_18006FC7B
0x18006fc31  lea     rax, aVersion_1; "version"
0x18006fc38  mov     [rbp+70h+var_E0], rax
0x18006fc3c  mov     [rbp+70h+var_D8], 7
0x18006fc40  mov     r8b, 0Ch
0x18006fc43  xor     edx, edx
0x18006fc45  lea     rcx, [rbp+70h+var_E0]
0x18006fc49  call    ?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z; tson::output_archive::write_type(bool,tson::details::archive_marker)
0x18006fc4e  test    al, al
0x18006fc50  jz      short loc_18006FC7B
0x18006fc52  mov     rbx, [rbp+70h+var_50]
0x18006fc56  mov     rax, [rbx+820h]
0x18006fc5d  cmp     [rbx+818h], rax
0x18006fc64  jnb     loc_180070039
0x18006fc6a  mov     rax, [rbx+818h]
0x18006fc71  mov     [rax], r14b
0x18006fc74  inc     qword ptr [rbx+818h]
0x18006fc7b  test    r15b, 1
0x18006fc7f  jnz     loc_18006FD7E
0x18006fc85  mov     rcx, [rdi]
0x18006fc88  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18006fc8f  mov     r8d, r15d
0x18006fc92  lea     rdx, [rbp+70h+var_E0]
0x18006fc96  test    rax, rax
0x18006fc99  jz      loc_18006FD6D
0x18006fc9f  mov     [rsp+170h+var_150], r12
0x18006fca4  xor     r9d, r9d
0x18006fca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fcac  test    al, al
0x18006fcae  jnz     short loc_18006FCC7
0x18006fcb0  mov     byte ptr [rdi+0A0h], 3
0x18006fcb7  mov     word ptr [rdi+0A2h], 400Ch
0x18006fcc0  mov     [rdi+0A8h], r12
0x18006fcc7  cmp     [rbp+70h+var_C8], 0
0x18006fccb  jnz     loc_18006FF8E
0x18006fcd1  cmp     [rbp+70h+var_58], 0
0x18006fcd5  jl      loc_18006FF8E
0x18006fcdb  mov     rax, [rbp+70h+var_50]
0x18006fcdf  cmp     byte ptr [rax+8], 0
0x18006fce3  jnz     loc_1800700B3
0x18006fce9  mov     r8, [rax+810h]
0x18006fcf0  mov     rdx, [rax+818h]
0x18006fcf7  sub     rdx, r8
0x18006fcfa  mov     edx, edx
0x18006fcfc  cmp     rdx, 0FFFFFFh
0x18006fd03  ja      loc_1800700AD
0x18006fd09  mov     ecx, edx
0x18006fd0b  shl     rcx, 6
0x18006fd0f  and     ecx, 3F000000h
0x18006fd15  lea     rax, ds:0[rdx*4]
0x18006fd1d  and     eax, 3F00h
0x18006fd22  or      ecx, eax
0x18006fd24  mov     eax, edx
0x18006fd26  shl     rax, 4
0x18006fd2a  and     eax, 3F0000h
0x18006fd2f  or      ecx, eax
0x18006fd31  and     edx, 3Fh
0x18006fd34  or      ecx, edx
0x18006fd36  or      ecx, 80408040h
0x18006fd3c  mov     [r8], ecx
0x18006fd3f  mov     rax, [rsi+810h]
0x18006fd46  mov     rcx, [rbp+70h+var_40]
0x18006fd4a  xor     rcx, rsp; StackCookie
0x18006fd4d  call    __security_check_cookie
0x18006fd52  mov     rbx, [rsp+170h+arg_8]
0x18006fd5a  add     rsp, 140h
0x18006fd61  pop     r15
0x18006fd63  pop     r14
0x18006fd65  pop     r13
0x18006fd67  pop     r12
0x18006fd69  pop     rdi
0x18006fd6a  pop     rsi
0x18006fd6b  pop     rbp
0x18006fd6c  retn
0x18006fd6d  mov     rax, [rcx]
0x18006fd70  mov     rax, [rax+8]
0x18006fd74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd79  jmp     loc_18006FCC7
0x18006fd7e  test    dword ptr [rdi+14h], 40000h
0x18006fd85  jz      loc_18006FE0E
0x18006fd8b  mov     rcx, [rdi+8]
0x18006fd8f  test    rcx, rcx
0x18006fd92  jz      loc_18006FF76
0x18006fd98  mov     rdx, rcx
0x18006fd9b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18006fda2  inc     rax
0x18006fda5  cmp     byte ptr [rcx+rax], 0
0x18006fda9  jnz     short loc_18006FDA2
0x18006fdab  xor     ecx, ecx
0x18006fdad  mov     [rsp+170h+var_FF], ecx
0x18006fdb1  mov     [rsp+170h+var_FB], cx
0x18006fdb6  mov     [rsp+170h+var_F9], cl
0x18006fdba  lea     r8, aName; "name"
0x18006fdc1  mov     [rbp+70h+var_E0], r8
0x18006fdc5  mov     [rbp+70h+var_D8], 4
0x18006fdc9  mov     qword ptr [rsp+170h+var_130], rdx
0x18006fdce  mov     qword ptr [rsp+170h+var_130+8], rax
0x18006fdd3  mov     word ptr [rsp+170h+var_120], cx
0x18006fdd8  mov     eax, [rsp+170h+var_FF+1]
0x18006fddc  mov     dword ptr [rsp+170h+var_120+2], eax
0x18006fde0  movzx   eax, [rsp+170h+var_FB+1]
0x18006fde5  mov     word ptr [rsp+170h+var_120+6], ax
0x18006fdea  movaps  xmm0, [rsp+170h+var_130]
0x18006fdef  movaps  [rsp+170h+var_110], xmm0
0x18006fdf4  movsd   xmm1, [rsp+170h+var_120]
0x18006fdfa  movsd   qword ptr [rsp+70h], xmm1
0x18006fe00  lea     r8, [rsp+170h+var_110]
0x18006fe05  lea     rcx, [rbp+70h+var_E0]
0x18006fe09  call    ??$write_string@Uansistring_tag@tson@@@output_archive@tson@@AEAAXW4archive_marker@details@1@Uansistring_tag@1@@Z; tson::output_archive::write_string<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag)
0x18006fe0e  lea     rax, aLog_0; "log"
0x18006fe15  mov     [rbp+70h+var_E0], rax
0x18006fe19  mov     [rbp+70h+var_D8], 3
0x18006fe1d  lea     rcx, [rbp+70h+var_E0]; this
0x18006fe21  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18006fe26  mov     rcx, [rdi+70h]
0x18006fe2a  mov     rax, [rbp+70h+var_60]
0x18006fe2e  test    rax, rax
0x18006fe31  jz      loc_180070053
0x18006fe37  lea     rdx, [rbp+70h+var_C8]
0x18006fe3b  lea     rdx, [rdx+rax*4]
0x18006fe3f  mov     dword ptr [rdx], 2
0x18006fe45  mov     r13d, 8000000Bh
0x18006fe4b  cmp     rcx, 0FFFFh
0x18006fe52  ja      loc_180070060
0x18006fe58  mov     [rbp+70h+var_D6], cx
0x18006fe5c  mov     rbx, [rdi+60h]
0x18006fe60  mov     rax, [rdi+70h]
0x18006fe64  lea     r14, [rbx+rax*8]
0x18006fe68  cmp     rbx, r14
0x18006fe6b  jnz     loc_18006FFD0
0x18006fe71  lea     rcx, [rbp+70h+var_E0]; this
0x18006fe75  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18006fe7a  lea     rax, aErrors; "errors"
0x18006fe81  mov     [rbp+70h+var_E0], rax
0x18006fe85  mov     [rbp+70h+var_D8], 6
0x18006fe89  lea     rcx, [rbp+70h+var_E0]; this
0x18006fe8d  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18006fe92  mov     rcx, [rdi+58h]
0x18006fe96  mov     rax, [rbp+70h+var_60]
0x18006fe9a  test    rax, rax
0x18006fe9d  jz      loc_180070071
0x18006fea3  lea     rdx, [rbp+70h+var_C8]
0x18006fea7  lea     rdx, [rdx+rax*4]
0x18006feab  mov     dword ptr [rdx], 2
0x18006feb1  cmp     rcx, 0FFFFh
0x18006feb8  ja      loc_18007007E
0x18006febe  mov     [rbp+70h+var_D6], cx
0x18006fec2  mov     rbx, [rdi+48h]
0x18006fec6  imul    r14, [rdi+58h], 0A8h
0x18006fece  add     r14, rbx
0x18006fed1  cmp     rbx, r14
0x18006fed4  jz      short loc_18006FF00
0x18006fed6  lea     rcx, [rbp+70h+var_E0]; this
0x18006feda  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18006fedf  mov     rdx, rbx; struct tson::output_archive *
0x18006fee2  lea     rcx, [rbp+70h+var_E0]; this
0x18006fee6  call    ?save_nothrow@tson@@YAXAEAVoutput_archive@1@AEAVStoredFailureInfo@wil@@@Z; tson::save_nothrow(tson::output_archive &,wil::StoredFailureInfo &)
0x18006feeb  lea     rcx, [rbp+70h+var_E0]; this
0x18006feef  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18006fef4  add     rbx, 0A8h
0x18006fefb  cmp     rbx, r14
0x18006fefe  jnz     short loc_18006FED6
0x18006ff00  lea     rcx, [rbp+70h+var_E0]; this
0x18006ff04  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18006ff09  lea     rax, aFlags; "flags"
0x18006ff10  mov     [rbp+70h+var_E0], rax
0x18006ff14  mov     [rbp+70h+var_D8], 5
0x18006ff18  lea     rcx, [rbp+70h+var_E0]; this
0x18006ff1c  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18006ff21  mov     rcx, [rdi+88h]
0x18006ff28  mov     rax, [rbp+70h+var_60]
0x18006ff2c  test    rax, rax
0x18006ff2f  jz      loc_18007008F
0x18006ff35  lea     rdx, [rbp+70h+var_C8]
0x18006ff39  lea     rdx, [rdx+rax*4]
0x18006ff3d  mov     dword ptr [rdx], 2
0x18006ff43  cmp     rcx, 0FFFFh
0x18006ff4a  ja      loc_18007009C
0x18006ff50  mov     [rbp+70h+var_D6], cx
0x18006ff54  mov     r14, [rdi+78h]
0x18006ff58  imul    rbx, [rdi+88h], 68h ; 'h'
0x18006ff60  add     rbx, r14
0x18006ff63  cmp     r14, rbx
0x18006ff66  jnz     short loc_18006FFA0
0x18006ff68  lea     rcx, [rbp+70h+var_E0]; this
0x18006ff6c  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18006ff71  jmp     loc_18006FC85
0x18006ff76  mov     rcx, [rdi+18h]
0x18006ff7a  mov     rdx, rcx
0x18006ff7d  test    rcx, rcx
0x18006ff80  jnz     loc_18006FD9B
0x18006ff86  mov     rax, r12
0x18006ff89  jmp     loc_18006FDAB
0x18006ff8e  or      dword ptr [rdi+40h], 100000h
0x18006ff95  xor     eax, eax
0x18006ff97  jmp     loc_18006FD46
0x18006ffa0  lea     rcx, [rbp+70h+var_E0]; this
0x18006ffa4  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18006ffa9  mov     rdx, r14; struct tson::output_archive *
0x18006ffac  lea     rcx, [rbp+70h+var_E0]; this
0x18006ffb0  call    ?save_nothrow@tson@@YAXAEAVoutput_archive@1@AEAUtest_flag@tip2@@@Z; tson::save_nothrow(tson::output_archive &,tip2::test_flag &)
0x18006ffb5  lea     rcx, [rbp+70h+var_E0]; this
0x18006ffb9  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18006ffbe  add     r14, 68h ; 'h'
0x18006ffc2  cmp     r14, rbx
0x18006ffc5  jz      short loc_18006FF68
0x18006ffc7  jmp     short loc_18006FFA0
0x18006ffd0  mov     rdx, rbx
0x18006ffd3  lea     rcx, [rbp+70h+var_E0]
0x18006ffd7  call    ??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@output_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::output_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x18006ffdc  add     rbx, 8
  ... truncated ...
```
