# AUTH_PROVIDER::DoWork(ulong,IHttpContext *,IHttpEventProvider *,void *,IHttpServer *)

- ea: `0x180007120`
- end: `0x1800078c2`
- name: `?DoWork@AUTH_PROVIDER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAXPEAVIHttpServer@@@Z`
- size: `1954`
- prototype: `__int64 __fastcall(__int64, int, __int64 *, __int64 *, int, int)`
- caller_count: `17`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004fc0`
- `0x180005020`
- `0x180005080`
- `0x1800050e0`
- `0x180005140`
- `0x1800051a0`
- `0x180005200`
- `0x180005260`
- `0x1800052c0`
- `0x180005320`
- `0x180005380`
- `0x1800055e0`
- `0x180005640`
- `0x1800056a0`
- `0x180005700`
- `0x1800057a0`
- `0x180005880`

## callees

- `0x180007120`
- `0x1800078c8`
- `0x180007a00`
- `0x180009010`

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
  v7 = s_ModuleId;
  v8 = (__int64 *)s_pSSPIAuthProvider;
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
0x180007120  mov     [rsp-8+arg_18], rbx
0x180007125  mov     [rsp-8+arg_0], rcx
0x18000712a  push    rbp
0x18000712b  push    rsi
0x18000712c  push    rdi
0x18000712d  push    r12
0x18000712f  push    r13
0x180007131  push    r14
0x180007133  push    r15
0x180007135  lea     rbp, [rsp-10h]
0x18000713a  sub     rsp, 110h
0x180007141  mov     rax, [r8]
0x180007144  xor     r13d, r13d
0x180007147  mov     rbx, cs:?s_ModuleId@@3PEAXEA; void * s_ModuleId
0x18000714e  mov     rcx, r8
0x180007151  mov     rsi, cs:?s_pSSPIAuthProvider@@3PEAVSSPI_AUTH_PROVIDER@@EA; SSPI_AUTH_PROVIDER * s_pSSPIAuthProvider
0x180007158  mov     r12, r9
0x18000715b  mov     rdi, r8
0x18000715e  mov     [rbp+40h+arg_28], r13d
0x180007162  mov     rax, [rax+20h]
0x180007166  mov     r14d, edx
0x180007169  mov     [rsp+140h+var_E0], r13
0x18000716e  mov     [rbp+40h+var_A0], r13
0x180007172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007177  mov     r15, rax
0x18000717a  cmp     r14d, 20000000h
0x180007181  jnz     loc_18000733D
0x180007187  mov     rcx, [r12]
0x18000718b  mov     [rbp+40h+arg_8], r13w
0x180007190  mov     word ptr [rbp+40h+arg_0], r13w
0x180007195  mov     rax, [rcx+8]
0x180007199  mov     rcx, r12
0x18000719c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071a1  test    eax, eax
0x1800071a3  jz      loc_18000724A
0x1800071a9  mov     rax, [r15]
0x1800071ac  lea     r8, [rbp+40h+arg_0]
0x1800071b0  mov     [rsp+140h+var_F8], r13
0x1800071b5  lea     rdx, [rbp+40h+arg_8]
0x1800071b9  mov     [rsp+140h+var_100], r13
0x1800071be  xor     r9d, r9d
0x1800071c1  mov     [rsp+140h+var_108], r13
0x1800071c6  mov     rcx, r15
0x1800071c9  mov     rax, [rax+0B8h]
0x1800071d0  mov     [rsp+140h+var_110], r13
0x1800071d5  mov     [rsp+140h+var_118], r13
0x1800071da  mov     [rsp+140h+var_120], r13
0x1800071df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071e4  mov     r12d, 191h
0x1800071ea  cmp     [rbp+40h+arg_8], r12w
0x1800071ef  jnz     short loc_180007267
0x1800071f1  mov     rax, [rsi]
0x1800071f4  lea     r8, [rsp+140h+var_E0]
0x1800071f9  mov     rdx, rdi
0x1800071fc  mov     rcx, rsi
0x1800071ff  mov     rax, [rax]
0x180007202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007207  mov     ebx, eax
0x180007209  test    eax, eax
0x18000720b  js      loc_1800074AB
0x180007211  mov     rax, [rsi]
0x180007214  lea     r8, [rsp+140h+var_D8]
0x180007219  mov     rdx, rdi
0x18000721c  mov     dword ptr [rsp+140h+var_D8], r13d
0x180007221  mov     rcx, rsi
0x180007224  mov     rax, [rax+10h]
0x180007228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000722d  test    eax, eax
0x18000722f  js      short loc_18000724A
0x180007231  cmp     dword ptr [rsp+140h+var_D8], r13d
0x180007236  jz      short loc_18000724A
0x180007238  mov     rax, [rsi]
0x18000723b  mov     rdx, rdi
0x18000723e  mov     rcx, rsi
0x180007241  mov     rax, [rax+20h]
0x180007245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000724a  xor     eax, eax
0x18000724c  mov     rbx, [rsp+140h+arg_18]
0x180007254  add     rsp, 110h
0x18000725b  pop     r15
0x18000725d  pop     r14
0x18000725f  pop     r13
0x180007261  pop     r12
0x180007263  pop     rdi
0x180007264  pop     rsi
0x180007265  pop     rbp
0x180007266  retn
0x180007267  mov     rax, [rdi]
0x18000726a  mov     rcx, rdi
0x18000726d  mov     rax, [rax+0F0h]
0x180007274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007279  mov     r8, rax
0x18000727c  mov     rcx, [rax]
0x18000727f  mov     rax, [rcx+38h]
0x180007283  mov     rcx, r8
0x180007286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000728b  mov     r8, rax
0x18000728e  mov     rdx, rbx
0x180007291  mov     rcx, [rax]
0x180007294  mov     rax, [rcx]
0x180007297  mov     rcx, r8
0x18000729a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000729f  mov     rbx, rax
0x1800072a2  test    rax, rax
0x1800072a5  jz      short loc_18000724A
0x1800072a7  cmp     [rax+80h], r13d
0x1800072ae  jnz     short loc_1800072EA
0x1800072b0  mov     r9d, [rax+78h]
0x1800072b4  test    r9d, r9d
0x1800072b7  jz      short loc_1800072EA
0x1800072b9  mov     rcx, [r15]
0x1800072bc  lea     rdx, aWwwAuthenticat; "WWW-Authenticate"
0x1800072c3  mov     r8, [rbx+68h]
0x1800072c7  mov     dword ptr [rsp+140h+var_120], r13d
0x1800072cc  mov     rax, [rcx+28h]
0x1800072d0  mov     rcx, r15
0x1800072d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072d8  test    eax, eax
0x1800072da  js      loc_18000724A
0x1800072e0  mov     dword ptr [rbx+80h], 1
0x1800072ea  cmp     [rbx+0C4h], r13d
0x1800072f1  jz      loc_18000724A
0x1800072f7  mov     rax, [rdi]
0x1800072fa  mov     rcx, rdi
0x1800072fd  mov     rax, [rax+20h]
0x180007301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007306  mov     r8, [rbx+0C8h]
0x18000730d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180007311  mov     rcx, [rax]
0x180007314  mov     r10, [rcx+28h]
0x180007318  inc     r9
0x18000731b  cmp     [r8+r9], r13b
0x18000731f  jnz     short loc_180007318
0x180007321  mov     rcx, rax
0x180007324  mov     dword ptr [rsp+140h+var_120], r13d
0x180007329  mov     rax, r10
0x18000732c  lea     rdx, aPersistentAuth; "Persistent-Auth"
0x180007333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007338  jmp     loc_18000724A
0x18000733d  cmp     r14d, 2
0x180007341  jnz     loc_18000724A
0x180007347  mov     rax, [rdi]
0x18000734a  mov     rcx, rdi
0x18000734d  mov     rax, [rax+30h]
0x180007351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007356  test    rax, rax
0x180007359  jz      loc_180007401
0x18000735f  mov     rax, [rdi]
0x180007362  mov     rcx, rdi
0x180007365  mov     rax, [rax+30h]
0x180007369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000736e  mov     rdx, rax
0x180007371  mov     rcx, [rax]
0x180007374  mov     rax, [rcx+10h]
0x180007378  mov     rcx, rdx
0x18000737b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007380  test    rax, rax
0x180007383  jz      short loc_1800073B0
0x180007385  mov     rax, [rdi]
0x180007388  mov     rcx, rdi
0x18000738b  mov     rax, [rax+30h]
0x18000738f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007394  mov     rdx, rax
0x180007397  mov     rcx, [rax]
0x18000739a  mov     rax, [rcx+10h]
0x18000739e  mov     rcx, rdx
0x1800073a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073a6  cmp     [rax], r13w
0x1800073aa  jnz     loc_18000724A
0x1800073b0  mov     rax, [rdi]
0x1800073b3  mov     rcx, rdi
0x1800073b6  mov     rax, [rax+30h]
0x1800073ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073bf  mov     rdx, rax
0x1800073c2  mov     rcx, [rax]
0x1800073c5  mov     rax, [rcx+8]
0x1800073c9  mov     rcx, rdx
0x1800073cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073d1  test    rax, rax
0x1800073d4  jz      short loc_180007401
0x1800073d6  mov     rax, [rdi]
0x1800073d9  mov     rcx, rdi
0x1800073dc  mov     rax, [rax+30h]
0x1800073e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073e5  mov     rdx, rax
0x1800073e8  mov     rcx, [rax]
0x1800073eb  mov     rax, [rcx+8]
0x1800073ef  mov     rcx, rdx
0x1800073f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073f7  cmp     [rax], r13w
0x1800073fb  jnz     loc_18000724A
0x180007401  mov     rax, [rdi]
0x180007404  mov     rcx, rdi
0x180007407  mov     rax, [rax+110h]
0x18000740e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007413  mov     r8, rax
0x180007416  lea     rdx, [rsp+140h+var_D0]
0x18000741b  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180007422  xorps   xmm0, xmm0
0x180007425  mov     [rsp+140h+var_D0], rax
0x18000742a  movdqu  [rsp+140h+var_C8], xmm0
0x180007430  mov     rcx, [r8]
0x180007433  mov     rax, [rcx]
0x180007436  mov     rcx, r8
0x180007439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000743e  test    eax, eax
0x180007440  js      short loc_18000748B
0x180007442  cmp     dword ptr [rbp+40h+var_C8+8], r13d
0x180007446  jz      short loc_18000748B
0x180007448  cmp     dword ptr [rsp+140h+var_C8+4], 4
0x18000744d  jb      short loc_18000748B
0x18000744f  cmp     dword ptr [rsp+140h+var_C8], 2
0x180007454  jz      short loc_18000745D
0x180007456  test    byte ptr [rsp+140h+var_C8], 2
0x18000745b  jz      short loc_18000748B
0x18000745d  mov     rax, [rsi]
0x180007460  mov     rcx, rsi
0x180007463  mov     rax, [rax+38h]
0x180007467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000746c  mov     rcx, [rdi]
0x18000746f  mov     ebx, eax
0x180007471  mov     rax, [rcx+110h]
0x180007478  mov     rcx, rdi
0x18000747b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007480  mov     r8d, ebx; unsigned int
0x180007483  mov     rcx, rax; struct IHttpTraceContext *
0x180007486  call    ?RaiseEvent@AUTH_START@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z; IISAuthenticationEvents::AUTH_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)
0x18000748b  mov     [rbp+40h+var_A8], r13
0x18000748f  mov     [rbp+40h+arg_20], r13d
0x180007493  mov     [rbp+40h+arg_10], r13d
0x180007497  test    r12, r12
0x18000749a  jnz     loc_18000754D
0x1800074a0  mov     ebx, 80070057h
0x1800074a5  mov     r12d, 191h
0x1800074ab  mov     rax, [r15]
0x1800074ae  mov     rcx, r15
0x1800074b1  mov     rax, [rax+8]
0x1800074b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074ba  mov     [rax+218h], r13w
0x1800074c2  mov     rcx, [rsp+140h+var_E0]
0x1800074c7  test    rcx, rcx
0x1800074ca  jz      loc_18000776C
0x1800074d0  mov     rax, [rcx]
0x1800074d3  lea     r8, [rbp+40h+var_A0]
0x1800074d7  lea     rdx, IID_IAppHostConfigException
0x1800074de  mov     rax, [rax]
0x1800074e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074e6  mov     rcx, [rbp+40h+var_A0]
0x1800074ea  lea     r8, aInternalServer; "Internal Server Error"
0x1800074f1  mov     rax, [r15]
0x1800074f4  mov     edx, 1F4h
0x1800074f9  mov     dword ptr [rsp+140h+var_110], r13d
0x1800074fe  mov     r9d, 13h
0x180007504  mov     [rsp+140h+var_118], rcx
0x180007509  mov     rcx, r15
0x18000750c  mov     dword ptr [rsp+140h+var_120], ebx
0x180007510  mov     rax, [rax+18h]
0x180007514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007519  mov     rcx, [rbp+40h+var_A0]
0x18000751d  test    rcx, rcx
0x180007520  jz      short loc_180007532
0x180007522  mov     rax, [rcx]
0x180007525  mov     rax, [rax+10h]
0x180007529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000752e  mov     [rbp+40h+var_A0], r13
0x180007532  mov     rcx, [rsp+140h+var_E0]
0x180007537  mov     rax, [rcx]
0x18000753a  mov     rax, [rax+10h]
0x18000753e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007543  mov     [rsp+140h+var_E0], r13
0x180007548  jmp     loc_180007799
0x18000754d  mov     rax, [rsi]
0x180007550  lea     r9, [rsp+140h+var_E0]
0x180007555  lea     r8, [rbp+40h+arg_20]
0x180007559  mov     rdx, rdi
0x18000755c  mov     rcx, rsi
0x18000755f  mov     rax, [rax+8]
0x180007563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007568  mov     ebx, eax
0x18000756a  test    eax, eax
0x18000756c  js      loc_1800074A5
0x180007572  cmp     [rbp+40h+arg_20], r13d
0x180007576  jz      loc_180007606
0x18000757c  mov     rax, [rdi]
0x18000757f  mov     rcx, rdi
0x180007582  mov     rax, [rax+110h]
0x180007589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000758e  mov     r8, rax
0x180007591  lea     rdx, [rsp+140h+var_D0]
0x180007596  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000759d  xorps   xmm0, xmm0
0x1800075a0  mov     [rsp+140h+var_D0], rax
0x1800075a5  movdqu  [rsp+140h+var_C8], xmm0
0x1800075ab  mov     rcx, [r8]
0x1800075ae  mov     rax, [rcx]
0x1800075b1  mov     rcx, r8
0x1800075b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075b9  test    eax, eax
0x1800075bb  js      short loc_180007606
0x1800075bd  cmp     dword ptr [rbp+40h+var_C8+8], r13d
  ... truncated ...
```
