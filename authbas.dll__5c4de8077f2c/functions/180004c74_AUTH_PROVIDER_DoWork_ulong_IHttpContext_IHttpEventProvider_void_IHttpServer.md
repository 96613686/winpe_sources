# AUTH_PROVIDER::DoWork(ulong,IHttpContext *,IHttpEventProvider *,void *,IHttpServer *)

- ea: `0x180004c74`
- end: `0x180005416`
- name: `?DoWork@AUTH_PROVIDER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAXPEAVIHttpServer@@@Z`
- size: `1954`
- prototype: ``
- caller_count: `16`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002be0`
- `0x180002ca0`
- `0x180002d00`
- `0x180002d60`
- `0x180002dc0`
- `0x180002e20`
- `0x180002e80`
- `0x180002ee0`
- `0x180002f40`
- `0x180002fa0`
- `0x180003200`
- `0x180003260`
- `0x1800032c0`
- `0x180003320`
- `0x1800033c0`
- `0x1800036ec`

## callees

- `0x180004c74`
- `0x18000541c`
- `0x180005554`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall AUTH_PROVIDER::DoWork(__int64 a1, int a2, __int64 *a3, __int64 *a4, int a5, int a6)
{
  __int64 v6; // rax
  void *v7; // rbx
  __int64 *v8; // rsi
  __int64 (__fastcall *v11)(__int64 *); // rax
  __int64 v13; // r15
  __int64 v14; // rcx
  int v15; // ebx
  __int64 (__fastcall **v16)(void *, __int64 *, __int64 *); // rax
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
  __int64 v44; // [rsp+68h] [rbp-98h] BYREF
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
  v8 = (__int64 *)s_pBasicAuthProvider;
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
        v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64 *))*v8)(v8, a3, &v43);
        if ( v15 >= 0 )
        {
          v16 = (__int64 (__fastcall **)(void *, __int64 *, __int64 *))*v8;
          LODWORD(v44) = 0;
          if ( (int)v16[2](v8, a3, &v44) >= 0 )
          {
            if ( (_DWORD)v44 )
              (*(void (__fastcall **)(__int64 *, __int64 *))(*v8 + 32))(v8, a3);
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
    v29 = (*(__int64 (__fastcall **)(__int64 *))(*v8 + 56))(v8);
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
  v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, int *, __int64 *))(*v8 + 8))(v8, a3, &a5, &v43);
  if ( v15 < 0 )
    goto LABEL_32;
  if ( a5 )
  {
    v32 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(__int64 *))(*a3 + 272))(a3);
    v45 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v46 = 0;
    if ( (**v32)(v32, &v45) >= 0 && DWORD2(v46) && DWORD1(v46) >= 4 && ((_DWORD)v46 == 2 || (v46 & 2) != 0) )
    {
      v33 = (*(__int64 (__fastcall **)(__int64 *))(*v8 + 56))(v8);
      v34 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64 *))(*a3 + 272))(a3);
      IISAuthenticationEvents::AUTH_REQUEST_AUTH_TYPE::RaiseEvent(v34, v35, v33);
    }
  }
  v36 = *v8;
  if ( !a5 )
  {
    if ( (*(unsigned int (__fastcall **)(__int64 *))(v36 + 40))(v8) )
    {
      v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, int *))(*v8 + 16))(v8, a3, &v61);
      if ( v15 < 0 )
        goto LABEL_32;
      if ( v61 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64 *))(*v8 + 48))(v8, a3, &v49);
        if ( v15 < 0 )
          goto LABEL_32;
        if ( v49 )
          (*(void (__fastcall **)(__int64 *))(*a4 + 8))(a4);
      }
    }
    goto LABEL_48;
  }
  v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64 *))v36)(v8, a3, &v43);
  if ( v15 < 0 )
    goto LABEL_32;
  v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, int *))(*v8 + 16))(v8, a3, &v61);
  if ( v15 < 0 )
    goto LABEL_32;
  if ( !v61 )
    goto LABEL_48;
  v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64 *, int *))(*v8 + 24))(v8, a3, &v49, &a6);
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
0x180004c74  mov     [rsp-8+arg_18], rbx
0x180004c79  mov     [rsp-8+arg_0], rcx
0x180004c7e  push    rbp
0x180004c7f  push    rsi
0x180004c80  push    rdi
0x180004c81  push    r12
0x180004c83  push    r13
0x180004c85  push    r14
0x180004c87  push    r15
0x180004c89  lea     rbp, [rsp-10h]
0x180004c8e  sub     rsp, 110h
0x180004c95  mov     rax, [r8]
0x180004c98  xor     r13d, r13d
0x180004c9b  mov     rbx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180004ca2  mov     rcx, r8
0x180004ca5  mov     rsi, cs:?s_pBasicAuthProvider@@3PEAVBASIC_AUTH_PROVIDER@@EA; BASIC_AUTH_PROVIDER * s_pBasicAuthProvider
0x180004cac  mov     r12, r9
0x180004caf  mov     rdi, r8
0x180004cb2  mov     [rbp+40h+arg_28], r13d
0x180004cb6  mov     rax, [rax+20h]
0x180004cba  mov     r14d, edx
0x180004cbd  mov     [rsp+140h+var_E0], r13
0x180004cc2  mov     [rbp+40h+var_A0], r13
0x180004cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ccb  mov     r15, rax
0x180004cce  cmp     r14d, 20000000h
0x180004cd5  jnz     loc_180004E91
0x180004cdb  mov     rcx, [r12]
0x180004cdf  mov     [rbp+40h+arg_8], r13w
0x180004ce4  mov     word ptr [rbp+40h+arg_0], r13w
0x180004ce9  mov     rax, [rcx+8]
0x180004ced  mov     rcx, r12
0x180004cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cf5  test    eax, eax
0x180004cf7  jz      loc_180004D9E
0x180004cfd  mov     rax, [r15]
0x180004d00  lea     r8, [rbp+40h+arg_0]
0x180004d04  mov     [rsp+140h+var_F8], r13
0x180004d09  lea     rdx, [rbp+40h+arg_8]
0x180004d0d  mov     [rsp+140h+var_100], r13
0x180004d12  xor     r9d, r9d
0x180004d15  mov     [rsp+140h+var_108], r13
0x180004d1a  mov     rcx, r15
0x180004d1d  mov     rax, [rax+0B8h]
0x180004d24  mov     [rsp+140h+var_110], r13
0x180004d29  mov     [rsp+140h+var_118], r13
0x180004d2e  mov     [rsp+140h+var_120], r13
0x180004d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d38  mov     r12d, 191h
0x180004d3e  cmp     [rbp+40h+arg_8], r12w
0x180004d43  jnz     short loc_180004DBB
0x180004d45  mov     rax, [rsi]
0x180004d48  lea     r8, [rsp+140h+var_E0]
0x180004d4d  mov     rdx, rdi
0x180004d50  mov     rcx, rsi
0x180004d53  mov     rax, [rax]
0x180004d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d5b  mov     ebx, eax
0x180004d5d  test    eax, eax
0x180004d5f  js      loc_180004FFF
0x180004d65  mov     rax, [rsi]
0x180004d68  lea     r8, [rsp+140h+var_D8]
0x180004d6d  mov     rdx, rdi
0x180004d70  mov     dword ptr [rsp+140h+var_D8], r13d
0x180004d75  mov     rcx, rsi
0x180004d78  mov     rax, [rax+10h]
0x180004d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d81  test    eax, eax
0x180004d83  js      short loc_180004D9E
0x180004d85  cmp     dword ptr [rsp+140h+var_D8], r13d
0x180004d8a  jz      short loc_180004D9E
0x180004d8c  mov     rax, [rsi]
0x180004d8f  mov     rdx, rdi
0x180004d92  mov     rcx, rsi
0x180004d95  mov     rax, [rax+20h]
0x180004d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d9e  xor     eax, eax
0x180004da0  mov     rbx, [rsp+140h+arg_18]
0x180004da8  add     rsp, 110h
0x180004daf  pop     r15
0x180004db1  pop     r14
0x180004db3  pop     r13
0x180004db5  pop     r12
0x180004db7  pop     rdi
0x180004db8  pop     rsi
0x180004db9  pop     rbp
0x180004dba  retn
0x180004dbb  mov     rax, [rdi]
0x180004dbe  mov     rcx, rdi
0x180004dc1  mov     rax, [rax+0F0h]
0x180004dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dcd  mov     r8, rax
0x180004dd0  mov     rcx, [rax]
0x180004dd3  mov     rax, [rcx+38h]
0x180004dd7  mov     rcx, r8
0x180004dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ddf  mov     r8, rax
0x180004de2  mov     rdx, rbx
0x180004de5  mov     rcx, [rax]
0x180004de8  mov     rax, [rcx]
0x180004deb  mov     rcx, r8
0x180004dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004df3  mov     rbx, rax
0x180004df6  test    rax, rax
0x180004df9  jz      short loc_180004D9E
0x180004dfb  cmp     [rax+80h], r13d
0x180004e02  jnz     short loc_180004E3E
0x180004e04  mov     r9d, [rax+78h]
0x180004e08  test    r9d, r9d
0x180004e0b  jz      short loc_180004E3E
0x180004e0d  mov     rcx, [r15]
0x180004e10  lea     rdx, aWwwAuthenticat; "WWW-Authenticate"
0x180004e17  mov     r8, [rbx+68h]
0x180004e1b  mov     dword ptr [rsp+140h+var_120], r13d
0x180004e20  mov     rax, [rcx+28h]
0x180004e24  mov     rcx, r15
0x180004e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e2c  test    eax, eax
0x180004e2e  js      loc_180004D9E
0x180004e34  mov     dword ptr [rbx+80h], 1
0x180004e3e  cmp     [rbx+0C4h], r13d
0x180004e45  jz      loc_180004D9E
0x180004e4b  mov     rax, [rdi]
0x180004e4e  mov     rcx, rdi
0x180004e51  mov     rax, [rax+20h]
0x180004e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e5a  mov     r8, [rbx+0C8h]
0x180004e61  or      r9, 0FFFFFFFFFFFFFFFFh
0x180004e65  mov     rcx, [rax]
0x180004e68  mov     r10, [rcx+28h]
0x180004e6c  inc     r9
0x180004e6f  cmp     [r8+r9], r13b
0x180004e73  jnz     short loc_180004E6C
0x180004e75  mov     rcx, rax
0x180004e78  mov     dword ptr [rsp+140h+var_120], r13d
0x180004e7d  mov     rax, r10
0x180004e80  lea     rdx, aPersistentAuth; "Persistent-Auth"
0x180004e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e8c  jmp     loc_180004D9E
0x180004e91  cmp     r14d, 2
0x180004e95  jnz     loc_180004D9E
0x180004e9b  mov     rax, [rdi]
0x180004e9e  mov     rcx, rdi
0x180004ea1  mov     rax, [rax+30h]
0x180004ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eaa  test    rax, rax
0x180004ead  jz      loc_180004F55
0x180004eb3  mov     rax, [rdi]
0x180004eb6  mov     rcx, rdi
0x180004eb9  mov     rax, [rax+30h]
0x180004ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ec2  mov     rdx, rax
0x180004ec5  mov     rcx, [rax]
0x180004ec8  mov     rax, [rcx+10h]
0x180004ecc  mov     rcx, rdx
0x180004ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ed4  test    rax, rax
0x180004ed7  jz      short loc_180004F04
0x180004ed9  mov     rax, [rdi]
0x180004edc  mov     rcx, rdi
0x180004edf  mov     rax, [rax+30h]
0x180004ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ee8  mov     rdx, rax
0x180004eeb  mov     rcx, [rax]
0x180004eee  mov     rax, [rcx+10h]
0x180004ef2  mov     rcx, rdx
0x180004ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004efa  cmp     [rax], r13w
0x180004efe  jnz     loc_180004D9E
0x180004f04  mov     rax, [rdi]
0x180004f07  mov     rcx, rdi
0x180004f0a  mov     rax, [rax+30h]
0x180004f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f13  mov     rdx, rax
0x180004f16  mov     rcx, [rax]
0x180004f19  mov     rax, [rcx+8]
0x180004f1d  mov     rcx, rdx
0x180004f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f25  test    rax, rax
0x180004f28  jz      short loc_180004F55
0x180004f2a  mov     rax, [rdi]
0x180004f2d  mov     rcx, rdi
0x180004f30  mov     rax, [rax+30h]
0x180004f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f39  mov     rdx, rax
0x180004f3c  mov     rcx, [rax]
0x180004f3f  mov     rax, [rcx+8]
0x180004f43  mov     rcx, rdx
0x180004f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f4b  cmp     [rax], r13w
0x180004f4f  jnz     loc_180004D9E
0x180004f55  mov     rax, [rdi]
0x180004f58  mov     rcx, rdi
0x180004f5b  mov     rax, [rax+110h]
0x180004f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f67  mov     r8, rax
0x180004f6a  lea     rdx, [rsp+140h+var_D0]
0x180004f6f  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180004f76  xorps   xmm0, xmm0
0x180004f79  mov     [rsp+140h+var_D0], rax
0x180004f7e  movdqu  [rsp+140h+var_C8], xmm0
0x180004f84  mov     rcx, [r8]
0x180004f87  mov     rax, [rcx]
0x180004f8a  mov     rcx, r8
0x180004f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f92  test    eax, eax
0x180004f94  js      short loc_180004FDF
0x180004f96  cmp     dword ptr [rbp+40h+var_C8+8], r13d
0x180004f9a  jz      short loc_180004FDF
0x180004f9c  cmp     dword ptr [rsp+140h+var_C8+4], 4
0x180004fa1  jb      short loc_180004FDF
0x180004fa3  cmp     dword ptr [rsp+140h+var_C8], 2
0x180004fa8  jz      short loc_180004FB1
0x180004faa  test    byte ptr [rsp+140h+var_C8], 2
0x180004faf  jz      short loc_180004FDF
0x180004fb1  mov     rax, [rsi]
0x180004fb4  mov     rcx, rsi
0x180004fb7  mov     rax, [rax+38h]
0x180004fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fc0  mov     rcx, [rdi]
0x180004fc3  mov     ebx, eax
0x180004fc5  mov     rax, [rcx+110h]
0x180004fcc  mov     rcx, rdi
0x180004fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd4  mov     r8d, ebx; unsigned int
0x180004fd7  mov     rcx, rax; struct IHttpTraceContext *
0x180004fda  call    ?RaiseEvent@AUTH_START@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z; IISAuthenticationEvents::AUTH_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)
0x180004fdf  mov     [rbp+40h+var_A8], r13
0x180004fe3  mov     [rbp+40h+arg_20], r13d
0x180004fe7  mov     [rbp+40h+arg_10], r13d
0x180004feb  test    r12, r12
0x180004fee  jnz     loc_1800050A1
0x180004ff4  mov     ebx, 80070057h
0x180004ff9  mov     r12d, 191h
0x180004fff  mov     rax, [r15]
0x180005002  mov     rcx, r15
0x180005005  mov     rax, [rax+8]
0x180005009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000500e  mov     [rax+218h], r13w
0x180005016  mov     rcx, [rsp+140h+var_E0]
0x18000501b  test    rcx, rcx
0x18000501e  jz      loc_1800052C0
0x180005024  mov     rax, [rcx]
0x180005027  lea     r8, [rbp+40h+var_A0]
0x18000502b  lea     rdx, IID_IAppHostConfigException
0x180005032  mov     rax, [rax]
0x180005035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000503a  mov     rcx, [rbp+40h+var_A0]
0x18000503e  lea     r8, aInternalServer; "Internal Server Error"
0x180005045  mov     rax, [r15]
0x180005048  mov     edx, 1F4h
0x18000504d  mov     dword ptr [rsp+140h+var_110], r13d
0x180005052  mov     r9d, 13h
0x180005058  mov     [rsp+140h+var_118], rcx
0x18000505d  mov     rcx, r15
0x180005060  mov     dword ptr [rsp+140h+var_120], ebx
0x180005064  mov     rax, [rax+18h]
0x180005068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000506d  mov     rcx, [rbp+40h+var_A0]
0x180005071  test    rcx, rcx
0x180005074  jz      short loc_180005086
0x180005076  mov     rax, [rcx]
0x180005079  mov     rax, [rax+10h]
0x18000507d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005082  mov     [rbp+40h+var_A0], r13
0x180005086  mov     rcx, [rsp+140h+var_E0]
0x18000508b  mov     rax, [rcx]
0x18000508e  mov     rax, [rax+10h]
0x180005092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005097  mov     [rsp+140h+var_E0], r13
0x18000509c  jmp     loc_1800052ED
0x1800050a1  mov     rax, [rsi]
0x1800050a4  lea     r9, [rsp+140h+var_E0]
0x1800050a9  lea     r8, [rbp+40h+arg_20]
0x1800050ad  mov     rdx, rdi
0x1800050b0  mov     rcx, rsi
0x1800050b3  mov     rax, [rax+8]
0x1800050b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050bc  mov     ebx, eax
0x1800050be  test    eax, eax
0x1800050c0  js      loc_180004FF9
0x1800050c6  cmp     [rbp+40h+arg_20], r13d
0x1800050ca  jz      loc_18000515A
0x1800050d0  mov     rax, [rdi]
0x1800050d3  mov     rcx, rdi
0x1800050d6  mov     rax, [rax+110h]
0x1800050dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050e2  mov     r8, rax
0x1800050e5  lea     rdx, [rsp+140h+var_D0]
0x1800050ea  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800050f1  xorps   xmm0, xmm0
0x1800050f4  mov     [rsp+140h+var_D0], rax
0x1800050f9  movdqu  [rsp+140h+var_C8], xmm0
0x1800050ff  mov     rcx, [r8]
0x180005102  mov     rax, [rcx]
0x180005105  mov     rcx, r8
0x180005108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000510d  test    eax, eax
0x18000510f  js      short loc_18000515A
0x180005111  cmp     dword ptr [rbp+40h+var_C8+8], r13d
  ... truncated ...
```
