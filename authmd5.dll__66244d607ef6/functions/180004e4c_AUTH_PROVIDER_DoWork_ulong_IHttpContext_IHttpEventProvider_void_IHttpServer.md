# AUTH_PROVIDER::DoWork(ulong,IHttpContext *,IHttpEventProvider *,void *,IHttpServer *)

- ea: `0x180004e4c`
- end: `0x1800055ee`
- name: `?DoWork@AUTH_PROVIDER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAXPEAVIHttpServer@@@Z`
- size: `1954`
- prototype: ``
- caller_count: `17`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003850`
- `0x1800038b0`
- `0x180003910`
- `0x180003970`
- `0x1800039d0`
- `0x180003a30`
- `0x180003a90`
- `0x180003af0`
- `0x180003b50`
- `0x180003bb0`
- `0x180003c10`
- `0x180003e70`
- `0x180003ed0`
- `0x180003f30`
- `0x180003f90`
- `0x180004030`
- `0x180004110`

## callees

- `0x180004e4c`
- `0x1800055f4`
- `0x18000572c`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall AUTH_PROVIDER::DoWork(__int64 a1, int a2, __int64 *a3, __int64 *a4, int a5, int a6)
{
  __int64 v6; // rax
  void *v7; // rbx
  DIGEST_AUTH_PROVIDER *v8; // rsi
  __int64 (__fastcall *v11)(__int64 *); // rax
  __int64 v13; // r15
  __int64 v14; // rcx
  int v15; // ebx
  __int64 (__fastcall **v16)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v18; // rax
  __int64 (__fastcall ***v19)(_QWORD, void *); // rax
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  int (__fastcall ***v28)(_QWORD, GUID **); // rax
  unsigned int v29; // ebx
  struct IHttpTraceContext *v30; // rax
  const struct _GUID *v31; // rdx
  int (__fastcall ***v32)(_QWORD, GUID **); // rax
  unsigned int v33; // ebx
  struct IHttpTraceContext *v34; // rax
  const struct _GUID *v35; // rdx
  __int64 v36; // rax
  unsigned int v37; // ebx
  int (__fastcall ***v38)(_QWORD, GUID **); // rax
  int (__fastcall **v39)(_QWORD, GUID **); // rcx
  __int64 *v40; // r8
  __int64 v41; // rcx
  void (__fastcall *v42)(__int64 *, _QWORD *); // rax
  __int64 v43; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+68h] [rbp-98h] BYREF
  GUID *v45; // [rsp+70h] [rbp-90h] BYREF
  __int128 v46; // [rsp+78h] [rbp-88h]
  int v47; // [rsp+88h] [rbp-78h]
  __int64 v48; // [rsp+90h] [rbp-70h]
  __int64 v49; // [rsp+98h] [rbp-68h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v51[5]; // [rsp+B0h] [rbp-50h] BYREF
  int v52; // [rsp+D8h] [rbp-28h]
  int v53; // [rsp+DCh] [rbp-24h]
  __int128 v54; // [rsp+E0h] [rbp-20h]
  int v55; // [rsp+F0h] [rbp-10h]
  int v56; // [rsp+F4h] [rbp-Ch]
  __int64 v57; // [rsp+F8h] [rbp-8h]
  GUID **v58; // [rsp+100h] [rbp+0h]
  __int64 v59; // [rsp+150h] [rbp+50h] BYREF
  __int16 v60; // [rsp+158h] [rbp+58h] BYREF
  int v61; // [rsp+160h] [rbp+60h] BYREF

  v59 = a1;
  v6 = *a3;
  v7 = s_pModuleContext;
  v8 = s_pDigestAuthProvider;
  a6 = 0;
  v11 = *(__int64 (__fastcall **)(__int64 *))(v6 + 32);
  v43 = 0;
  v50 = 0;
  v13 = v11(a3);
  if ( a2 == 0x20000000 )
  {
    v14 = *a4;
    v60 = 0;
    LOWORD(v59) = 0;
    if ( (*(unsigned int (__fastcall **)(__int64 *))(v14 + 8))(a4) )
    {
      (*(void (__fastcall **)(__int64, __int16 *, __int64 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v13 + 184LL))(
        v13,
        &v60,
        &v59,
        0,
        0,
        0,
        0,
        0,
        0,
        0);
      if ( v60 == 401 )
      {
        v15 = (**(__int64 (__fastcall ***)(DIGEST_AUTH_PROVIDER *, __int64 *, __int64 *))v8)(v8, a3, &v43);
        if ( v15 >= 0 )
        {
          v16 = *(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v8;
          v44 = 0;
          if ( (int)((__int64 (__fastcall **)(DIGEST_AUTH_PROVIDER *, __int64 *, int *))v16)[2](v8, a3, &v44) >= 0 )
          {
            if ( v44 )
              (*(void (__fastcall **)(DIGEST_AUTH_PROVIDER *, __int64 *))(*(_QWORD *)v8 + 32LL))(v8, a3);
          }
          return 0;
        }
        goto LABEL_32;
      }
      v18 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 240))(a3);
      v19 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 56LL))(v18);
      v20 = (**v19)(v19, v7);
      v21 = v20;
      if ( v20 )
      {
        if ( *(_DWORD *)(v20 + 128) || !*(_DWORD *)(v20 + 120) )
        {
LABEL_14:
          if ( *(_DWORD *)(v21 + 196) )
          {
            v22 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 32))(a3);
            v23 = -1;
            do
              ++v23;
            while ( *(_BYTE *)(*(_QWORD *)(v21 + 200) + v23) );
            (*(void (__fastcall **)(__int64, const char *))(*(_QWORD *)v22 + 40LL))(v22, "Persistent-Auth");
          }
          return 0;
        }
        if ( (*(int (__fastcall **)(__int64, const char *, _QWORD))(*(_QWORD *)v13 + 40LL))(
               v13,
               "WWW-Authenticate",
               *(_QWORD *)(v20 + 104)) >= 0 )
        {
          *(_DWORD *)(v21 + 128) = 1;
          goto LABEL_14;
        }
      }
    }
    return 0;
  }
  if ( a2 != 2 )
    return 0;
  if ( (*(__int64 (__fastcall **)(__int64 *))(*a3 + 48))(a3) )
  {
    v24 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 48))(a3);
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24) )
    {
      v25 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 48))(a3);
      if ( *(_WORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25) )
        return 0;
    }
    v26 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 48))(a3);
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26) )
    {
      v27 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 48))(a3);
      if ( *(_WORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27) )
        return 0;
    }
  }
  v28 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(__int64 *))(*a3 + 272))(a3);
  v45 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v46 = 0;
  if ( (**v28)(v28, &v45) >= 0 && DWORD2(v46) && DWORD1(v46) >= 4 && ((_DWORD)v46 == 2 || (v46 & 2) != 0) )
  {
    v29 = (*(__int64 (__fastcall **)(DIGEST_AUTH_PROVIDER *))(*(_QWORD *)v8 + 56LL))(v8);
    v30 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64 *))(*a3 + 272))(a3);
    IISAuthenticationEvents::AUTH_START::RaiseEvent(v30, v31, v29);
  }
  v49 = 0;
  a5 = 0;
  v61 = 0;
  if ( !a4 )
  {
    v15 = -2147024809;
LABEL_32:
    *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13) + 536) = 0;
    if ( v43 )
    {
      (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v43)(v43, &IID_IAppHostConfigException, &v50);
      (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v13 + 24LL))(
        v13,
        500,
        "Internal Server Error",
        19,
        v15,
        v50,
        0);
      if ( v50 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        v50 = 0;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      v43 = 0;
    }
    else
    {
      (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v13 + 24LL))(
        v13,
        401,
        "Unauthorized",
        1,
        v15,
        0,
        0);
    }
    v37 = a2 != 0x20000000 ? 2 : 0;
    goto LABEL_65;
  }
  v15 = (*(__int64 (__fastcall **)(DIGEST_AUTH_PROVIDER *, __int64 *, int *, __int64 *))(*(_QWORD *)v8 + 8LL))(
          v8,
          a3,
          &a5,
          &v43);
  if ( v15 < 0 )
    goto LABEL_32;
  if ( a5 )
  {
    v32 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(__int64 *))(*a3 + 272))(a3);
    v45 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v46 = 0;
    if ( (**v32)(v32, &v45) >= 0 && DWORD2(v46) && DWORD1(v46) >= 4 && ((_DWORD)v46 == 2 || (v46 & 2) != 0) )
    {
      v33 = (*(__int64 (__fastcall **)(DIGEST_AUTH_PROVIDER *))(*(_QWORD *)v8 + 56LL))(v8);
      v34 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64 *))(*a3 + 272))(a3);
      IISAuthenticationEvents::AUTH_REQUEST_AUTH_TYPE::RaiseEvent(v34, v35, v33);
    }
  }
  v36 = *(_QWORD *)v8;
  if ( !a5 )
  {
    if ( (*(unsigned int (__fastcall **)(DIGEST_AUTH_PROVIDER *))(v36 + 40))(v8) )
    {
      v15 = (*(__int64 (__fastcall **)(DIGEST_AUTH_PROVIDER *, __int64 *, int *))(*(_QWORD *)v8 + 16LL))(v8, a3, &v61);
      if ( v15 < 0 )
        goto LABEL_32;
      if ( v61 )
      {
        v15 = (*(__int64 (__fastcall **)(DIGEST_AUTH_PROVIDER *, __int64 *, __int64 *))(*(_QWORD *)v8 + 48LL))(
                v8,
                a3,
                &v49);
        if ( v15 < 0 )
          goto LABEL_32;
        if ( v49 )
          (*(void (__fastcall **)(__int64 *))(*a4 + 8))(a4);
      }
    }
    goto LABEL_48;
  }
  v15 = (*(__int64 (__fastcall **)(DIGEST_AUTH_PROVIDER *, __int64 *, __int64 *))v36)(v8, a3, &v43);
  if ( v15 < 0 )
    goto LABEL_32;
  v15 = (*(__int64 (__fastcall **)(DIGEST_AUTH_PROVIDER *, __int64 *, int *))(*(_QWORD *)v8 + 16LL))(v8, a3, &v61);
  if ( v15 < 0 )
    goto LABEL_32;
  if ( !v61 )
    goto LABEL_48;
  v15 = (*(__int64 (__fastcall **)(DIGEST_AUTH_PROVIDER *, __int64 *, __int64 *, int *))(*(_QWORD *)v8 + 24LL))(
          v8,
          a3,
          &v49,
          &a6);
  if ( v15 < 0 )
    goto LABEL_32;
  if ( v49 )
    (*(void (__fastcall **)(__int64 *))(*a4 + 8))(a4);
  if ( (a6 & 4) == 0 )
  {
    if ( (a6 & 2) != 0 )
      goto LABEL_60;
LABEL_48:
    v37 = 0;
    goto LABEL_65;
  }
  *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13) + 536) = 0;
  (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v13 + 24LL))(
    v13,
    401,
    "Unauthorized",
    1,
    -2146893042,
    0,
    0);
LABEL_60:
  v37 = 2;
LABEL_65:
  v38 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(__int64 *))(*a3 + 272))(a3);
  v45 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v39 = *v38;
  v46 = 0;
  if ( (*v39)(v38, &v45) >= 0 && DWORD2(v46) && DWORD1(v46) >= 4 && ((_DWORD)v46 == 2 || (v46 & 2) != 0) )
  {
    v40 = (__int64 *)(*(__int64 (__fastcall **)(__int64 *))(*a3 + 272))(a3);
    v51[1] = 2;
    v51[3] = 28;
    v51[2] = &`IISAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
    v57 = 1;
    v41 = *v40;
    v51[4] = L"AUTH_END";
    v45 = (GUID *)L"ContextId";
    v58 = &v45;
    v42 = *(void (__fastcall **)(__int64 *, _QWORD *))(v41 + 16);
    v51[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v52 = 1;
    v53 = 4;
    v54 = 0;
    v55 = 0;
    v56 = 1;
    LODWORD(v46) = 72;
    *((_QWORD *)&v46 + 1) = 0;
    v47 = 16;
    v48 = 0;
    v42(v40, v51);
  }
  return v37;
}

```

## disassembly

```asm
0x180004e4c  mov     [rsp-8+arg_18], rbx
0x180004e51  mov     [rsp-8+arg_0], rcx
0x180004e56  push    rbp
0x180004e57  push    rsi
0x180004e58  push    rdi
0x180004e59  push    r12
0x180004e5b  push    r13
0x180004e5d  push    r14
0x180004e5f  push    r15
0x180004e61  lea     rbp, [rsp-10h]
0x180004e66  sub     rsp, 110h
0x180004e6d  mov     rax, [r8]
0x180004e70  xor     r13d, r13d
0x180004e73  mov     rbx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180004e7a  mov     rcx, r8
0x180004e7d  mov     rsi, cs:?s_pDigestAuthProvider@@3PEAVDIGEST_AUTH_PROVIDER@@EA; DIGEST_AUTH_PROVIDER * s_pDigestAuthProvider
0x180004e84  mov     r12, r9
0x180004e87  mov     rdi, r8
0x180004e8a  mov     [rbp+40h+arg_28], r13d
0x180004e8e  mov     rax, [rax+20h]
0x180004e92  mov     r14d, edx
0x180004e95  mov     [rsp+140h+var_E0], r13
0x180004e9a  mov     [rbp+40h+var_A0], r13
0x180004e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ea3  mov     r15, rax
0x180004ea6  cmp     r14d, 20000000h
0x180004ead  jnz     loc_180005069
0x180004eb3  mov     rcx, [r12]
0x180004eb7  mov     [rbp+40h+arg_8], r13w
0x180004ebc  mov     word ptr [rbp+40h+arg_0], r13w
0x180004ec1  mov     rax, [rcx+8]
0x180004ec5  mov     rcx, r12
0x180004ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ecd  test    eax, eax
0x180004ecf  jz      loc_180004F76
0x180004ed5  mov     rax, [r15]
0x180004ed8  lea     r8, [rbp+40h+arg_0]
0x180004edc  mov     [rsp+140h+var_F8], r13
0x180004ee1  lea     rdx, [rbp+40h+arg_8]
0x180004ee5  mov     [rsp+140h+var_100], r13
0x180004eea  xor     r9d, r9d
0x180004eed  mov     [rsp+140h+var_108], r13
0x180004ef2  mov     rcx, r15
0x180004ef5  mov     rax, [rax+0B8h]
0x180004efc  mov     [rsp+140h+var_110], r13
0x180004f01  mov     [rsp+140h+var_118], r13
0x180004f06  mov     [rsp+140h+var_120], r13
0x180004f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f10  mov     r12d, 191h
0x180004f16  cmp     [rbp+40h+arg_8], r12w
0x180004f1b  jnz     short loc_180004F93
0x180004f1d  mov     rax, [rsi]
0x180004f20  lea     r8, [rsp+140h+var_E0]
0x180004f25  mov     rdx, rdi
0x180004f28  mov     rcx, rsi
0x180004f2b  mov     rax, [rax]
0x180004f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f33  mov     ebx, eax
0x180004f35  test    eax, eax
0x180004f37  js      loc_1800051D7
0x180004f3d  mov     rax, [rsi]
0x180004f40  lea     r8, [rsp+140h+var_D8]
0x180004f45  mov     rdx, rdi
0x180004f48  mov     [rsp+140h+var_D8], r13d
0x180004f4d  mov     rcx, rsi
0x180004f50  mov     rax, [rax+10h]
0x180004f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f59  test    eax, eax
0x180004f5b  js      short loc_180004F76
0x180004f5d  cmp     [rsp+140h+var_D8], r13d
0x180004f62  jz      short loc_180004F76
0x180004f64  mov     rax, [rsi]
0x180004f67  mov     rdx, rdi
0x180004f6a  mov     rcx, rsi
0x180004f6d  mov     rax, [rax+20h]
0x180004f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f76  xor     eax, eax
0x180004f78  mov     rbx, [rsp+140h+arg_18]
0x180004f80  add     rsp, 110h
0x180004f87  pop     r15
0x180004f89  pop     r14
0x180004f8b  pop     r13
0x180004f8d  pop     r12
0x180004f8f  pop     rdi
0x180004f90  pop     rsi
0x180004f91  pop     rbp
0x180004f92  retn
0x180004f93  mov     rax, [rdi]
0x180004f96  mov     rcx, rdi
0x180004f99  mov     rax, [rax+0F0h]
0x180004fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa5  mov     r8, rax
0x180004fa8  mov     rcx, [rax]
0x180004fab  mov     rax, [rcx+38h]
0x180004faf  mov     rcx, r8
0x180004fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb7  mov     r8, rax
0x180004fba  mov     rdx, rbx
0x180004fbd  mov     rcx, [rax]
0x180004fc0  mov     rax, [rcx]
0x180004fc3  mov     rcx, r8
0x180004fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fcb  mov     rbx, rax
0x180004fce  test    rax, rax
0x180004fd1  jz      short loc_180004F76
0x180004fd3  cmp     [rax+80h], r13d
0x180004fda  jnz     short loc_180005016
0x180004fdc  mov     r9d, [rax+78h]
0x180004fe0  test    r9d, r9d
0x180004fe3  jz      short loc_180005016
0x180004fe5  mov     rcx, [r15]
0x180004fe8  lea     rdx, aWwwAuthenticat; "WWW-Authenticate"
0x180004fef  mov     r8, [rbx+68h]
0x180004ff3  mov     dword ptr [rsp+140h+var_120], r13d
0x180004ff8  mov     rax, [rcx+28h]
0x180004ffc  mov     rcx, r15
0x180004fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005004  test    eax, eax
0x180005006  js      loc_180004F76
0x18000500c  mov     dword ptr [rbx+80h], 1
0x180005016  cmp     [rbx+0C4h], r13d
0x18000501d  jz      loc_180004F76
0x180005023  mov     rax, [rdi]
0x180005026  mov     rcx, rdi
0x180005029  mov     rax, [rax+20h]
0x18000502d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005032  mov     r8, [rbx+0C8h]
0x180005039  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000503d  mov     rcx, [rax]
0x180005040  mov     r10, [rcx+28h]
0x180005044  inc     r9
0x180005047  cmp     [r8+r9], r13b
0x18000504b  jnz     short loc_180005044
0x18000504d  mov     rcx, rax
0x180005050  mov     dword ptr [rsp+140h+var_120], r13d
0x180005055  mov     rax, r10
0x180005058  lea     rdx, aPersistentAuth; "Persistent-Auth"
0x18000505f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005064  jmp     loc_180004F76
0x180005069  cmp     r14d, 2
0x18000506d  jnz     loc_180004F76
0x180005073  mov     rax, [rdi]
0x180005076  mov     rcx, rdi
0x180005079  mov     rax, [rax+30h]
0x18000507d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005082  test    rax, rax
0x180005085  jz      loc_18000512D
0x18000508b  mov     rax, [rdi]
0x18000508e  mov     rcx, rdi
0x180005091  mov     rax, [rax+30h]
0x180005095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000509a  mov     rdx, rax
0x18000509d  mov     rcx, [rax]
0x1800050a0  mov     rax, [rcx+10h]
0x1800050a4  mov     rcx, rdx
0x1800050a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050ac  test    rax, rax
0x1800050af  jz      short loc_1800050DC
0x1800050b1  mov     rax, [rdi]
0x1800050b4  mov     rcx, rdi
0x1800050b7  mov     rax, [rax+30h]
0x1800050bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050c0  mov     rdx, rax
0x1800050c3  mov     rcx, [rax]
0x1800050c6  mov     rax, [rcx+10h]
0x1800050ca  mov     rcx, rdx
0x1800050cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d2  cmp     [rax], r13w
0x1800050d6  jnz     loc_180004F76
0x1800050dc  mov     rax, [rdi]
0x1800050df  mov     rcx, rdi
0x1800050e2  mov     rax, [rax+30h]
0x1800050e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050eb  mov     rdx, rax
0x1800050ee  mov     rcx, [rax]
0x1800050f1  mov     rax, [rcx+8]
0x1800050f5  mov     rcx, rdx
0x1800050f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050fd  test    rax, rax
0x180005100  jz      short loc_18000512D
0x180005102  mov     rax, [rdi]
0x180005105  mov     rcx, rdi
0x180005108  mov     rax, [rax+30h]
0x18000510c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005111  mov     rdx, rax
0x180005114  mov     rcx, [rax]
0x180005117  mov     rax, [rcx+8]
0x18000511b  mov     rcx, rdx
0x18000511e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005123  cmp     [rax], r13w
0x180005127  jnz     loc_180004F76
0x18000512d  mov     rax, [rdi]
0x180005130  mov     rcx, rdi
0x180005133  mov     rax, [rax+110h]
0x18000513a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000513f  mov     r8, rax
0x180005142  lea     rdx, [rsp+140h+var_D0]
0x180005147  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000514e  xorps   xmm0, xmm0
0x180005151  mov     [rsp+140h+var_D0], rax
0x180005156  movdqu  [rsp+140h+var_C8], xmm0
0x18000515c  mov     rcx, [r8]
0x18000515f  mov     rax, [rcx]
0x180005162  mov     rcx, r8
0x180005165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000516a  test    eax, eax
0x18000516c  js      short loc_1800051B7
0x18000516e  cmp     dword ptr [rbp+40h+var_C8+8], r13d
0x180005172  jz      short loc_1800051B7
0x180005174  cmp     dword ptr [rsp+140h+var_C8+4], 4
0x180005179  jb      short loc_1800051B7
0x18000517b  cmp     dword ptr [rsp+140h+var_C8], 2
0x180005180  jz      short loc_180005189
0x180005182  test    byte ptr [rsp+140h+var_C8], 2
0x180005187  jz      short loc_1800051B7
0x180005189  mov     rax, [rsi]
0x18000518c  mov     rcx, rsi
0x18000518f  mov     rax, [rax+38h]
0x180005193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005198  mov     rcx, [rdi]
0x18000519b  mov     ebx, eax
0x18000519d  mov     rax, [rcx+110h]
0x1800051a4  mov     rcx, rdi
0x1800051a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051ac  mov     r8d, ebx; unsigned int
0x1800051af  mov     rcx, rax; struct IHttpTraceContext *
0x1800051b2  call    ?RaiseEvent@AUTH_START@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z; IISAuthenticationEvents::AUTH_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)
0x1800051b7  mov     [rbp+40h+var_A8], r13
0x1800051bb  mov     [rbp+40h+arg_20], r13d
0x1800051bf  mov     [rbp+40h+arg_10], r13d
0x1800051c3  test    r12, r12
0x1800051c6  jnz     loc_180005279
0x1800051cc  mov     ebx, 80070057h
0x1800051d1  mov     r12d, 191h
0x1800051d7  mov     rax, [r15]
0x1800051da  mov     rcx, r15
0x1800051dd  mov     rax, [rax+8]
0x1800051e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051e6  mov     [rax+218h], r13w
0x1800051ee  mov     rcx, [rsp+140h+var_E0]
0x1800051f3  test    rcx, rcx
0x1800051f6  jz      loc_180005498
0x1800051fc  mov     rax, [rcx]
0x1800051ff  lea     r8, [rbp+40h+var_A0]
0x180005203  lea     rdx, IID_IAppHostConfigException
0x18000520a  mov     rax, [rax]
0x18000520d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005212  mov     rcx, [rbp+40h+var_A0]
0x180005216  lea     r8, aInternalServer; "Internal Server Error"
0x18000521d  mov     rax, [r15]
0x180005220  mov     edx, 1F4h
0x180005225  mov     dword ptr [rsp+140h+var_110], r13d
0x18000522a  mov     r9d, 13h
0x180005230  mov     [rsp+140h+var_118], rcx
0x180005235  mov     rcx, r15
0x180005238  mov     dword ptr [rsp+140h+var_120], ebx
0x18000523c  mov     rax, [rax+18h]
0x180005240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005245  mov     rcx, [rbp+40h+var_A0]
0x180005249  test    rcx, rcx
0x18000524c  jz      short loc_18000525E
0x18000524e  mov     rax, [rcx]
0x180005251  mov     rax, [rax+10h]
0x180005255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000525a  mov     [rbp+40h+var_A0], r13
0x18000525e  mov     rcx, [rsp+140h+var_E0]
0x180005263  mov     rax, [rcx]
0x180005266  mov     rax, [rax+10h]
0x18000526a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000526f  mov     [rsp+140h+var_E0], r13
0x180005274  jmp     loc_1800054C5
0x180005279  mov     rax, [rsi]
0x18000527c  lea     r9, [rsp+140h+var_E0]
0x180005281  lea     r8, [rbp+40h+arg_20]
0x180005285  mov     rdx, rdi
0x180005288  mov     rcx, rsi
0x18000528b  mov     rax, [rax+8]
0x18000528f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005294  mov     ebx, eax
0x180005296  test    eax, eax
0x180005298  js      loc_1800051D1
0x18000529e  cmp     [rbp+40h+arg_20], r13d
0x1800052a2  jz      loc_180005332
0x1800052a8  mov     rax, [rdi]
0x1800052ab  mov     rcx, rdi
0x1800052ae  mov     rax, [rax+110h]
0x1800052b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052ba  mov     r8, rax
0x1800052bd  lea     rdx, [rsp+140h+var_D0]
0x1800052c2  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800052c9  xorps   xmm0, xmm0
0x1800052cc  mov     [rsp+140h+var_D0], rax
0x1800052d1  movdqu  [rsp+140h+var_C8], xmm0
0x1800052d7  mov     rcx, [r8]
0x1800052da  mov     rax, [rcx]
0x1800052dd  mov     rcx, r8
0x1800052e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052e5  test    eax, eax
0x1800052e7  js      short loc_180005332
0x1800052e9  cmp     dword ptr [rbp+40h+var_C8+8], r13d
  ... truncated ...
```
