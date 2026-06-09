# AUTH_PROVIDER::DoWork(ulong,IHttpContext *,IHttpEventProvider *,void *,IHttpServer *)

- ea: `0x180003048`
- end: `0x1800037ea`
- name: `?DoWork@AUTH_PROVIDER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAXPEAVIHttpServer@@@Z`
- size: `1954`
- prototype: `__int64 __fastcall(__int64, int, __int64 *, __int64 *, int, int)`
- caller_count: `17`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002320`
- `0x180002380`
- `0x1800023e0`
- `0x180002440`
- `0x1800024a0`
- `0x180002500`
- `0x180002560`
- `0x1800025c0`
- `0x180002620`
- `0x180002680`
- `0x1800026e0`
- `0x180002940`
- `0x1800029a0`
- `0x180002a00`
- `0x180002a60`
- `0x180002b00`
- `0x180002be0`

## callees

- `0x180003048`
- `0x1800037f0`
- `0x180003928`
- `0x180005010`

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
  v8 = (__int64 *)s_pCertmapAuthProvider;
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
0x180003048  mov     [rsp-8+arg_18], rbx
0x18000304d  mov     [rsp-8+arg_0], rcx
0x180003052  push    rbp
0x180003053  push    rsi
0x180003054  push    rdi
0x180003055  push    r12
0x180003057  push    r13
0x180003059  push    r14
0x18000305b  push    r15
0x18000305d  lea     rbp, [rsp-10h]
0x180003062  sub     rsp, 110h
0x180003069  mov     rax, [r8]
0x18000306c  xor     r13d, r13d
0x18000306f  mov     rbx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180003076  mov     rcx, r8
0x180003079  mov     rsi, cs:?s_pCertmapAuthProvider@@3PEAVCERTMAP_AUTH_PROVIDER@@EA; CERTMAP_AUTH_PROVIDER * s_pCertmapAuthProvider
0x180003080  mov     r12, r9
0x180003083  mov     rdi, r8
0x180003086  mov     [rbp+40h+arg_28], r13d
0x18000308a  mov     rax, [rax+20h]
0x18000308e  mov     r14d, edx
0x180003091  mov     [rsp+140h+var_E0], r13
0x180003096  mov     [rbp+40h+var_A0], r13
0x18000309a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000309f  mov     r15, rax
0x1800030a2  cmp     r14d, 20000000h
0x1800030a9  jnz     loc_180003265
0x1800030af  mov     rcx, [r12]
0x1800030b3  mov     [rbp+40h+arg_8], r13w
0x1800030b8  mov     word ptr [rbp+40h+arg_0], r13w
0x1800030bd  mov     rax, [rcx+8]
0x1800030c1  mov     rcx, r12
0x1800030c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c9  test    eax, eax
0x1800030cb  jz      loc_180003172
0x1800030d1  mov     rax, [r15]
0x1800030d4  lea     r8, [rbp+40h+arg_0]
0x1800030d8  mov     [rsp+140h+var_F8], r13
0x1800030dd  lea     rdx, [rbp+40h+arg_8]
0x1800030e1  mov     [rsp+140h+var_100], r13
0x1800030e6  xor     r9d, r9d
0x1800030e9  mov     [rsp+140h+var_108], r13
0x1800030ee  mov     rcx, r15
0x1800030f1  mov     rax, [rax+0B8h]
0x1800030f8  mov     [rsp+140h+var_110], r13
0x1800030fd  mov     [rsp+140h+var_118], r13
0x180003102  mov     [rsp+140h+var_120], r13
0x180003107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000310c  mov     r12d, 191h
0x180003112  cmp     [rbp+40h+arg_8], r12w
0x180003117  jnz     short loc_18000318F
0x180003119  mov     rax, [rsi]
0x18000311c  lea     r8, [rsp+140h+var_E0]
0x180003121  mov     rdx, rdi
0x180003124  mov     rcx, rsi
0x180003127  mov     rax, [rax]
0x18000312a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000312f  mov     ebx, eax
0x180003131  test    eax, eax
0x180003133  js      loc_1800033D3
0x180003139  mov     rax, [rsi]
0x18000313c  lea     r8, [rsp+140h+var_D8]
0x180003141  mov     rdx, rdi
0x180003144  mov     dword ptr [rsp+140h+var_D8], r13d
0x180003149  mov     rcx, rsi
0x18000314c  mov     rax, [rax+10h]
0x180003150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003155  test    eax, eax
0x180003157  js      short loc_180003172
0x180003159  cmp     dword ptr [rsp+140h+var_D8], r13d
0x18000315e  jz      short loc_180003172
0x180003160  mov     rax, [rsi]
0x180003163  mov     rdx, rdi
0x180003166  mov     rcx, rsi
0x180003169  mov     rax, [rax+20h]
0x18000316d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003172  xor     eax, eax
0x180003174  mov     rbx, [rsp+140h+arg_18]
0x18000317c  add     rsp, 110h
0x180003183  pop     r15
0x180003185  pop     r14
0x180003187  pop     r13
0x180003189  pop     r12
0x18000318b  pop     rdi
0x18000318c  pop     rsi
0x18000318d  pop     rbp
0x18000318e  retn
0x18000318f  mov     rax, [rdi]
0x180003192  mov     rcx, rdi
0x180003195  mov     rax, [rax+0F0h]
0x18000319c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a1  mov     r8, rax
0x1800031a4  mov     rcx, [rax]
0x1800031a7  mov     rax, [rcx+38h]
0x1800031ab  mov     rcx, r8
0x1800031ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b3  mov     r8, rax
0x1800031b6  mov     rdx, rbx
0x1800031b9  mov     rcx, [rax]
0x1800031bc  mov     rax, [rcx]
0x1800031bf  mov     rcx, r8
0x1800031c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c7  mov     rbx, rax
0x1800031ca  test    rax, rax
0x1800031cd  jz      short loc_180003172
0x1800031cf  cmp     [rax+80h], r13d
0x1800031d6  jnz     short loc_180003212
0x1800031d8  mov     r9d, [rax+78h]
0x1800031dc  test    r9d, r9d
0x1800031df  jz      short loc_180003212
0x1800031e1  mov     rcx, [r15]
0x1800031e4  lea     rdx, aWwwAuthenticat; "WWW-Authenticate"
0x1800031eb  mov     r8, [rbx+68h]
0x1800031ef  mov     dword ptr [rsp+140h+var_120], r13d
0x1800031f4  mov     rax, [rcx+28h]
0x1800031f8  mov     rcx, r15
0x1800031fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003200  test    eax, eax
0x180003202  js      loc_180003172
0x180003208  mov     dword ptr [rbx+80h], 1
0x180003212  cmp     [rbx+0C4h], r13d
0x180003219  jz      loc_180003172
0x18000321f  mov     rax, [rdi]
0x180003222  mov     rcx, rdi
0x180003225  mov     rax, [rax+20h]
0x180003229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000322e  mov     r8, [rbx+0C8h]
0x180003235  or      r9, 0FFFFFFFFFFFFFFFFh
0x180003239  mov     rcx, [rax]
0x18000323c  mov     r10, [rcx+28h]
0x180003240  inc     r9
0x180003243  cmp     [r8+r9], r13b
0x180003247  jnz     short loc_180003240
0x180003249  mov     rcx, rax
0x18000324c  mov     dword ptr [rsp+140h+var_120], r13d
0x180003251  mov     rax, r10
0x180003254  lea     rdx, aPersistentAuth; "Persistent-Auth"
0x18000325b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003260  jmp     loc_180003172
0x180003265  cmp     r14d, 2
0x180003269  jnz     loc_180003172
0x18000326f  mov     rax, [rdi]
0x180003272  mov     rcx, rdi
0x180003275  mov     rax, [rax+30h]
0x180003279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000327e  test    rax, rax
0x180003281  jz      loc_180003329
0x180003287  mov     rax, [rdi]
0x18000328a  mov     rcx, rdi
0x18000328d  mov     rax, [rax+30h]
0x180003291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003296  mov     rdx, rax
0x180003299  mov     rcx, [rax]
0x18000329c  mov     rax, [rcx+10h]
0x1800032a0  mov     rcx, rdx
0x1800032a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a8  test    rax, rax
0x1800032ab  jz      short loc_1800032D8
0x1800032ad  mov     rax, [rdi]
0x1800032b0  mov     rcx, rdi
0x1800032b3  mov     rax, [rax+30h]
0x1800032b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032bc  mov     rdx, rax
0x1800032bf  mov     rcx, [rax]
0x1800032c2  mov     rax, [rcx+10h]
0x1800032c6  mov     rcx, rdx
0x1800032c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032ce  cmp     [rax], r13w
0x1800032d2  jnz     loc_180003172
0x1800032d8  mov     rax, [rdi]
0x1800032db  mov     rcx, rdi
0x1800032de  mov     rax, [rax+30h]
0x1800032e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032e7  mov     rdx, rax
0x1800032ea  mov     rcx, [rax]
0x1800032ed  mov     rax, [rcx+8]
0x1800032f1  mov     rcx, rdx
0x1800032f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032f9  test    rax, rax
0x1800032fc  jz      short loc_180003329
0x1800032fe  mov     rax, [rdi]
0x180003301  mov     rcx, rdi
0x180003304  mov     rax, [rax+30h]
0x180003308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000330d  mov     rdx, rax
0x180003310  mov     rcx, [rax]
0x180003313  mov     rax, [rcx+8]
0x180003317  mov     rcx, rdx
0x18000331a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000331f  cmp     [rax], r13w
0x180003323  jnz     loc_180003172
0x180003329  mov     rax, [rdi]
0x18000332c  mov     rcx, rdi
0x18000332f  mov     rax, [rax+110h]
0x180003336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000333b  mov     r8, rax
0x18000333e  lea     rdx, [rsp+140h+var_D0]
0x180003343  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000334a  xorps   xmm0, xmm0
0x18000334d  mov     [rsp+140h+var_D0], rax
0x180003352  movdqu  [rsp+140h+var_C8], xmm0
0x180003358  mov     rcx, [r8]
0x18000335b  mov     rax, [rcx]
0x18000335e  mov     rcx, r8
0x180003361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003366  test    eax, eax
0x180003368  js      short loc_1800033B3
0x18000336a  cmp     dword ptr [rbp+40h+var_C8+8], r13d
0x18000336e  jz      short loc_1800033B3
0x180003370  cmp     dword ptr [rsp+140h+var_C8+4], 4
0x180003375  jb      short loc_1800033B3
0x180003377  cmp     dword ptr [rsp+140h+var_C8], 2
0x18000337c  jz      short loc_180003385
0x18000337e  test    byte ptr [rsp+140h+var_C8], 2
0x180003383  jz      short loc_1800033B3
0x180003385  mov     rax, [rsi]
0x180003388  mov     rcx, rsi
0x18000338b  mov     rax, [rax+38h]
0x18000338f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003394  mov     rcx, [rdi]
0x180003397  mov     ebx, eax
0x180003399  mov     rax, [rcx+110h]
0x1800033a0  mov     rcx, rdi
0x1800033a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033a8  mov     r8d, ebx; unsigned int
0x1800033ab  mov     rcx, rax; struct IHttpTraceContext *
0x1800033ae  call    ?RaiseEvent@AUTH_START@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z; IISAuthenticationEvents::AUTH_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)
0x1800033b3  mov     [rbp+40h+var_A8], r13
0x1800033b7  mov     [rbp+40h+arg_20], r13d
0x1800033bb  mov     [rbp+40h+arg_10], r13d
0x1800033bf  test    r12, r12
0x1800033c2  jnz     loc_180003475
0x1800033c8  mov     ebx, 80070057h
0x1800033cd  mov     r12d, 191h
0x1800033d3  mov     rax, [r15]
0x1800033d6  mov     rcx, r15
0x1800033d9  mov     rax, [rax+8]
0x1800033dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e2  mov     [rax+218h], r13w
0x1800033ea  mov     rcx, [rsp+140h+var_E0]
0x1800033ef  test    rcx, rcx
0x1800033f2  jz      loc_180003694
0x1800033f8  mov     rax, [rcx]
0x1800033fb  lea     r8, [rbp+40h+var_A0]
0x1800033ff  lea     rdx, IID_IAppHostConfigException
0x180003406  mov     rax, [rax]
0x180003409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000340e  mov     rcx, [rbp+40h+var_A0]
0x180003412  lea     r8, aInternalServer; "Internal Server Error"
0x180003419  mov     rax, [r15]
0x18000341c  mov     edx, 1F4h
0x180003421  mov     dword ptr [rsp+140h+var_110], r13d
0x180003426  mov     r9d, 13h
0x18000342c  mov     [rsp+140h+var_118], rcx
0x180003431  mov     rcx, r15
0x180003434  mov     dword ptr [rsp+140h+var_120], ebx
0x180003438  mov     rax, [rax+18h]
0x18000343c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003441  mov     rcx, [rbp+40h+var_A0]
0x180003445  test    rcx, rcx
0x180003448  jz      short loc_18000345A
0x18000344a  mov     rax, [rcx]
0x18000344d  mov     rax, [rax+10h]
0x180003451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003456  mov     [rbp+40h+var_A0], r13
0x18000345a  mov     rcx, [rsp+140h+var_E0]
0x18000345f  mov     rax, [rcx]
0x180003462  mov     rax, [rax+10h]
0x180003466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000346b  mov     [rsp+140h+var_E0], r13
0x180003470  jmp     loc_1800036C1
0x180003475  mov     rax, [rsi]
0x180003478  lea     r9, [rsp+140h+var_E0]
0x18000347d  lea     r8, [rbp+40h+arg_20]
0x180003481  mov     rdx, rdi
0x180003484  mov     rcx, rsi
0x180003487  mov     rax, [rax+8]
0x18000348b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003490  mov     ebx, eax
0x180003492  test    eax, eax
0x180003494  js      loc_1800033CD
0x18000349a  cmp     [rbp+40h+arg_20], r13d
0x18000349e  jz      loc_18000352E
0x1800034a4  mov     rax, [rdi]
0x1800034a7  mov     rcx, rdi
0x1800034aa  mov     rax, [rax+110h]
0x1800034b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034b6  mov     r8, rax
0x1800034b9  lea     rdx, [rsp+140h+var_D0]
0x1800034be  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800034c5  xorps   xmm0, xmm0
0x1800034c8  mov     [rsp+140h+var_D0], rax
0x1800034cd  movdqu  [rsp+140h+var_C8], xmm0
0x1800034d3  mov     rcx, [r8]
0x1800034d6  mov     rax, [rcx]
0x1800034d9  mov     rcx, r8
0x1800034dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034e1  test    eax, eax
0x1800034e3  js      short loc_18000352E
0x1800034e5  cmp     dword ptr [rbp+40h+var_C8+8], r13d
  ... truncated ...
```
