# AUTH_PROVIDER::DoWork(ulong,IHttpContext *,IHttpEventProvider *,void *,IHttpServer *)

- ea: `0x180001030`
- end: `0x1800017bf`
- name: `?DoWork@AUTH_PROVIDER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAXPEAVIHttpServer@@@Z`
- size: `1935`
- prototype: `__int64 __fastcall(__int64, int, __int64 *, __int64 *, int, int)`
- caller_count: `17`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180001010`
- `0x180003660`
- `0x1800036c0`
- `0x180003760`
- `0x1800037c0`
- `0x180003820`
- `0x180003880`
- `0x1800038e0`
- `0x180003940`
- `0x1800039a0`
- `0x180003a00`
- `0x180003c60`
- `0x180003cc0`
- `0x180003ce0`
- `0x180003d40`
- `0x180003de0`
- `0x180003ec0`

## callees

- `0x180001030`
- `0x180002840`
- `0x180005884`
- `0x180005934`
- `0x180006010`

## import_xrefs

- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x1800013f3`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x1800013f3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180001415`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180001415`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180001409`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180001409`

## pseudocode

```c
__int64 __fastcall AUTH_PROVIDER::DoWork(__int64 a1, int a2, __int64 *a3, __int64 *a4, int a5, int a6)
{
  __int64 v6; // rax
  void *v7; // rdi
  __int64 *v8; // rsi
  __int64 (__fastcall *v11)(__int64 *); // rax
  __int64 v13; // r13
  int (__fastcall ***v14)(_QWORD, GUID **); // rax
  int (__fastcall **v15)(_QWORD, GUID **); // rcx
  int v16; // edi
  __int64 v17; // rax
  unsigned int v18; // edi
  int (__fastcall ***v19)(_QWORD, GUID **); // rax
  int (__fastcall ***v21)(_QWORD, GUID **); // rax
  unsigned int v22; // edi
  struct IHttpTraceContext *v23; // rax
  const struct _GUID *v24; // rdx
  __int64 v25; // rcx
  __int64 (__fastcall **v26)(void *, __int64 *, __int64 *); // rax
  __int64 v27; // rax
  __int64 (__fastcall ***v28)(_QWORD, void *); // rax
  __int64 v29; // rax
  __int64 v30; // r14
  int (__fastcall *v31)(__int64, const char *, char *, _QWORD, _DWORD); // rsi
  unsigned __int16 CCH; // di
  char *Str; // rax
  __int64 v34; // rax
  __int64 v35; // r9
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  unsigned int v40; // edi
  struct IHttpTraceContext *v41; // rax
  const struct _GUID *v42; // rdx
  int v43; // eax
  struct IHttpTraceContext *v44; // rax
  const struct _GUID *v45; // rdx
  int v46; // [rsp+60h] [rbp-29h] BYREF
  __int64 v47; // [rsp+68h] [rbp-21h] BYREF
  __int64 v48; // [rsp+70h] [rbp-19h] BYREF
  __int64 v49; // [rsp+78h] [rbp-11h] BYREF
  GUID *v50; // [rsp+80h] [rbp-9h] BYREF
  __int128 v51; // [rsp+88h] [rbp-1h]
  __int64 v52; // [rsp+E0h] [rbp+57h] BYREF
  __int16 v53; // [rsp+E8h] [rbp+5Fh] BYREF
  int v54; // [rsp+F0h] [rbp+67h] BYREF

  v52 = a1;
  v6 = *a3;
  v7 = s_pModuleContext;
  v8 = (__int64 *)s_pAnonAuthProvider;
  v46 = 0;
  v11 = *(__int64 (__fastcall **)(__int64 *))(v6 + 32);
  v47 = 0;
  v49 = 0;
  v13 = v11(a3);
  if ( a2 == 0x20000000 )
  {
    v25 = *a4;
    v53 = 0;
    LOWORD(v52) = 0;
    if ( (*(unsigned int (__fastcall **)(__int64 *))(v25 + 8))(a4) )
    {
      (*(void (__fastcall **)(__int64, __int16 *, __int64 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v13 + 184LL))(
        v13,
        &v53,
        &v52,
        0,
        0,
        0,
        0,
        0,
        0,
        0);
      if ( v53 == 401 )
      {
        v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64 *))*v8)(v8, a3, &v47);
        if ( v16 < 0 )
          goto LABEL_55;
        v26 = (__int64 (__fastcall **)(void *, __int64 *, __int64 *))*v8;
        a6 = 0;
        if ( (int)v26[2](v8, a3, (__int64 *)&a6) >= 0 && a6 )
          (*(void (__fastcall **)(__int64 *, __int64 *))(*v8 + 32))(v8, a3);
      }
      else
      {
        v27 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 240))(a3);
        v28 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 56LL))(v27);
        v29 = (**v28)(v28, v7);
        v30 = v29;
        if ( v29 )
        {
          if ( !*(_DWORD *)(v29 + 128) && !STRA::IsEmpty((STRA *)(v29 + 72)) )
          {
            v31 = *(int (__fastcall **)(__int64, const char *, char *, _QWORD, _DWORD))(*(_QWORD *)v13 + 40LL);
            CCH = STRA::QueryCCH((STRA *)(v30 + 72));
            Str = STRA::QueryStr((STRA *)(v30 + 72));
            if ( v31(v13, "WWW-Authenticate", Str, CCH, 0) < 0 )
              return 0;
            *(_DWORD *)(v30 + 128) = 1;
          }
          if ( *(_DWORD *)(v30 + 196) )
          {
            v34 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 32))(a3);
            v35 = -1;
            do
              ++v35;
            while ( *(_BYTE *)(*(_QWORD *)(v30 + 200) + v35) );
            (*(void (__fastcall **)(__int64, const char *))(*(_QWORD *)v34 + 40LL))(v34, "Persistent-Auth");
          }
        }
      }
    }
    return 0;
  }
  if ( a2 != 2 )
    return 0;
  if ( (*(__int64 (__fastcall **)(__int64 *))(*a3 + 48))(a3) )
  {
    v36 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 48))(a3);
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36) )
    {
      v37 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 48))(a3);
      if ( *(_WORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37) )
        return 0;
    }
    v38 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 48))(a3);
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38) )
    {
      v39 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 48))(a3);
      if ( *(_WORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39) )
        return 0;
    }
  }
  v14 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(__int64 *))(*a3 + 272))(a3);
  v50 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v15 = *v14;
  v51 = 0;
  if ( (*v15)(v14, &v50) >= 0 && DWORD2(v51) && DWORD1(v51) >= 4 && ((_DWORD)v51 == 2 || (v51 & 2) != 0) )
  {
    v40 = (*(__int64 (__fastcall **)(__int64 *))(*v8 + 56))(v8);
    v41 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64 *))(*a3 + 272))(a3);
    IISAuthenticationEvents::AUTH_START::RaiseEvent(v41, v42, v40);
  }
  v48 = 0;
  a5 = 0;
  v54 = 0;
  if ( !a4 )
  {
    v16 = -2147024809;
    goto LABEL_55;
  }
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, int *, __int64 *))(*v8 + 8))(v8, a3, &a5, &v47);
  if ( v16 < 0 )
  {
LABEL_55:
    *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13) + 536) = 0;
    if ( v47 )
    {
      (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v47)(v47, &IID_IAppHostConfigException, &v49);
      (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v13 + 24LL))(
        v13,
        500,
        "Internal Server Error",
        19,
        v16,
        v49,
        0);
      if ( v49 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        v49 = 0;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      v47 = 0;
    }
    else
    {
      (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v13 + 24LL))(
        v13,
        401,
        "Unauthorized",
        1,
        v16,
        0,
        0);
    }
    v43 = 0;
    if ( a2 != 0x20000000 )
      v43 = 2;
    v18 = v43;
    goto LABEL_19;
  }
  if ( a5 )
  {
    v21 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(__int64 *))(*a3 + 272))(a3);
    v50 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v51 = 0;
    if ( (**v21)(v21, &v50) >= 0 && DWORD2(v51) && DWORD1(v51) >= 4 && ((_DWORD)v51 == 2 || (v51 & 2) != 0) )
    {
      v22 = (*(__int64 (__fastcall **)(__int64 *))(*v8 + 56))(v8);
      v23 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64 *))(*a3 + 272))(a3);
      IISAuthenticationEvents::AUTH_REQUEST_AUTH_TYPE::RaiseEvent(v23, v24, v22);
    }
  }
  v17 = *v8;
  if ( !a5 )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64 *))(v17 + 40))(v8) )
      goto LABEL_18;
    v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, int *))(*v8 + 16))(v8, a3, &v54);
    if ( v16 >= 0 )
    {
      if ( !v54 )
        goto LABEL_18;
      v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64 *))(*v8 + 48))(v8, a3, &v48);
      if ( v16 >= 0 )
      {
        if ( !v48 )
          goto LABEL_18;
        (*(void (__fastcall **)(__int64 *))(*a4 + 8))(a4);
        v18 = 0;
        goto LABEL_19;
      }
    }
    goto LABEL_55;
  }
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64 *))v17)(v8, a3, &v47);
  if ( v16 < 0 )
    goto LABEL_55;
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, int *))(*v8 + 16))(v8, a3, &v54);
  if ( v16 < 0 )
    goto LABEL_55;
  if ( !v54 )
  {
    v18 = 0;
    goto LABEL_19;
  }
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64 *, int *))(*v8 + 24))(v8, a3, &v48, &v46);
  if ( v16 < 0 )
    goto LABEL_55;
  if ( v48 )
    (*(void (__fastcall **)(__int64 *))(*a4 + 8))(a4);
  if ( (v46 & 4) != 0 )
  {
    *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13) + 536) = 0;
    (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v13 + 24LL))(
      v13,
      401,
      "Unauthorized",
      1,
      -2146893042,
      0,
      0);
    v18 = 2;
  }
  else
  {
    if ( (v46 & 2) == 0 )
    {
LABEL_18:
      v18 = 0;
      goto LABEL_19;
    }
    v18 = 2;
  }
LABEL_19:
  v19 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(__int64 *))(*a3 + 272))(a3);
  v50 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v51 = 0;
  if ( (**v19)(v19, &v50) >= 0 && DWORD2(v51) && DWORD1(v51) >= 4 && ((_DWORD)v51 == 2 || (v51 & 2) != 0) )
  {
    v44 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64 *))(*a3 + 272))(a3);
    IISAuthenticationEvents::AUTH_END::RaiseEvent(v44, v45);
  }
  return v18;
}

```

## disassembly

```asm
0x180001030  mov     [rsp-8+arg_18], rbx
0x180001035  mov     [rsp-8+arg_0], rcx
0x18000103a  push    rbp
0x18000103b  push    rsi
0x18000103c  push    rdi
0x18000103d  push    r12
0x18000103f  push    r13
0x180001041  push    r14
0x180001043  push    r15
0x180001045  lea     rbp, [rsp-17h]
0x18000104a  sub     rsp, 0A0h
0x180001051  mov     rax, [r8]
0x180001054  xor     r12d, r12d
0x180001057  mov     rdi, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x18000105e  mov     rcx, r8
0x180001061  mov     rsi, cs:?s_pAnonAuthProvider@@3PEAVANON_AUTH_PROVIDER@@EA; ANON_AUTH_PROVIDER * s_pAnonAuthProvider
0x180001068  mov     r14, r9
0x18000106b  mov     rbx, r8
0x18000106e  mov     [rbp+47h+var_70], r12d
0x180001072  mov     rax, [rax+20h]
0x180001076  mov     r15d, edx
0x180001079  mov     [rbp+47h+var_68], r12
0x18000107d  mov     [rbp+47h+var_58], r12
0x180001081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001086  mov     r13, rax
0x180001089  cmp     r15d, 20000000h
0x180001090  jz      loc_1800012D8
0x180001096  cmp     r15d, 2
0x18000109a  jnz     loc_180001393
0x1800010a0  mov     rax, [rbx]
0x1800010a3  mov     rcx, rbx
0x1800010a6  mov     rax, [rax+30h]
0x1800010aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010af  test    rax, rax
0x1800010b2  jnz     loc_1800014A2
0x1800010b8  mov     rax, [rbx]
0x1800010bb  mov     rcx, rbx
0x1800010be  mov     rax, [rax+110h]
0x1800010c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010ca  mov     r8, rax
0x1800010cd  lea     r12, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800010d4  xorps   xmm0, xmm0
0x1800010d7  mov     [rbp+47h+var_50], r12
0x1800010db  lea     rdx, [rbp+47h+var_50]
0x1800010df  mov     rcx, [rax]
0x1800010e2  movdqu  [rbp+47h+var_48], xmm0
0x1800010e7  mov     rax, [rcx]
0x1800010ea  mov     rcx, r8
0x1800010ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010f2  test    eax, eax
0x1800010f4  js      short loc_180001100
0x1800010f6  cmp     dword ptr [rbp+47h+var_48+8], 0
0x1800010fa  jnz     loc_18000154D
0x180001100  xor     eax, eax
0x180001102  mov     [rbp+47h+var_60], rax
0x180001106  mov     [rbp+47h+arg_20], eax
0x180001109  mov     [rbp+47h+arg_10], eax
0x18000110c  test    r14, r14
0x18000110f  jz      loc_18000159B
0x180001115  mov     rax, [rsi]
0x180001118  lea     r9, [rbp+47h+var_68]
0x18000111c  lea     r8, [rbp+47h+arg_20]
0x180001120  mov     rdx, rbx
0x180001123  mov     rcx, rsi
0x180001126  mov     rax, [rax+8]
0x18000112a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000112f  mov     edi, eax
0x180001131  test    eax, eax
0x180001133  js      loc_1800015A0
0x180001139  cmp     [rbp+47h+arg_20], 0
0x18000113d  jnz     loc_180001245
0x180001143  cmp     [rbp+47h+arg_20], 0
0x180001147  mov     rcx, rsi
0x18000114a  mov     rax, [rsi]
0x18000114d  jz      loc_180001653
0x180001153  mov     rax, [rax]
0x180001156  lea     r8, [rbp+47h+var_68]
0x18000115a  mov     rdx, rbx
0x18000115d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001162  mov     edi, eax
0x180001164  test    eax, eax
0x180001166  js      loc_1800015A0
0x18000116c  mov     rax, [rsi]
0x18000116f  lea     r8, [rbp+47h+arg_10]
0x180001173  mov     rdx, rbx
0x180001176  mov     rcx, rsi
0x180001179  mov     rax, [rax+10h]
0x18000117d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001182  mov     edi, eax
0x180001184  test    eax, eax
0x180001186  js      loc_1800015A0
0x18000118c  cmp     [rbp+47h+arg_10], 0
0x180001190  jz      loc_1800016D1
0x180001196  mov     rax, [rsi]
0x180001199  lea     r9, [rbp+47h+var_70]
0x18000119d  lea     r8, [rbp+47h+var_60]
0x1800011a1  mov     rdx, rbx
0x1800011a4  mov     rcx, rsi
0x1800011a7  mov     rax, [rax+18h]
0x1800011ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011b0  mov     edi, eax
0x1800011b2  test    eax, eax
0x1800011b4  js      loc_1800015A0
0x1800011ba  mov     rdx, [rbp+47h+var_60]
0x1800011be  test    rdx, rdx
0x1800011c1  jz      short loc_1800011D2
0x1800011c3  mov     rax, [r14]
0x1800011c6  mov     rcx, r14
0x1800011c9  mov     rax, [rax+8]
0x1800011cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011d2  mov     eax, [rbp+47h+var_70]
0x1800011d5  test    al, 4
0x1800011d7  jnz     loc_1800016D8
0x1800011dd  test    al, 2
0x1800011df  jnz     loc_18000172E
0x1800011e5  xor     edi, edi
0x1800011e7  mov     rax, [rbx]
0x1800011ea  mov     rcx, rbx
0x1800011ed  mov     rax, [rax+110h]
0x1800011f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011f9  mov     r8, rax
0x1800011fc  mov     [rbp+47h+var_50], r12
0x180001200  xorps   xmm0, xmm0
0x180001203  lea     rdx, [rbp+47h+var_50]
0x180001207  movdqu  [rbp+47h+var_48], xmm0
0x18000120c  mov     rcx, [rax]
0x18000120f  mov     rax, [rcx]
0x180001212  mov     rcx, r8
0x180001215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000121a  test    eax, eax
0x18000121c  js      short loc_180001228
0x18000121e  cmp     dword ptr [rbp+47h+var_48+8], 0
0x180001222  jnz     loc_180001785
0x180001228  mov     eax, edi
0x18000122a  mov     rbx, [rsp+0D0h+arg_18]
0x180001232  add     rsp, 0A0h
0x180001239  pop     r15
0x18000123b  pop     r14
0x18000123d  pop     r13
0x18000123f  pop     r12
0x180001241  pop     rdi
0x180001242  pop     rsi
0x180001243  pop     rbp
0x180001244  retn
0x180001245  mov     rax, [rbx]
0x180001248  mov     rcx, rbx
0x18000124b  mov     rax, [rax+110h]
0x180001252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001257  mov     r8, rax
0x18000125a  mov     [rbp+47h+var_50], r12
0x18000125e  xorps   xmm0, xmm0
0x180001261  lea     rdx, [rbp+47h+var_50]
0x180001265  movdqu  [rbp+47h+var_48], xmm0
0x18000126a  mov     rcx, [rax]
0x18000126d  mov     rax, [rcx]
0x180001270  mov     rcx, r8
0x180001273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001278  test    eax, eax
0x18000127a  js      loc_180001143
0x180001280  cmp     dword ptr [rbp+47h+var_48+8], 0
0x180001284  jz      loc_180001143
0x18000128a  cmp     dword ptr [rbp+47h+var_48+4], 4
0x18000128e  jb      loc_180001143
0x180001294  mov     rax, qword ptr [rbp+47h+var_48]
0x180001298  cmp     eax, 2
0x18000129b  jz      short loc_1800012A5
0x18000129d  test    al, 2
0x18000129f  jz      loc_180001143
0x1800012a5  mov     rax, [rsi]
0x1800012a8  mov     rcx, rsi
0x1800012ab  mov     rax, [rax+38h]
0x1800012af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012b4  mov     rcx, [rbx]
0x1800012b7  mov     edi, eax
0x1800012b9  mov     rax, [rcx+110h]
0x1800012c0  mov     rcx, rbx
0x1800012c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012c8  mov     r8d, edi; unsigned int
0x1800012cb  mov     rcx, rax; struct IHttpTraceContext *
0x1800012ce  call    ?RaiseEvent@AUTH_REQUEST_AUTH_TYPE@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z; IISAuthenticationEvents::AUTH_REQUEST_AUTH_TYPE::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)
0x1800012d3  jmp     loc_180001143
0x1800012d8  mov     rcx, [r14]
0x1800012db  mov     [rbp+47h+arg_8], r12w
0x1800012e0  mov     word ptr [rbp+47h+arg_0], r12w
0x1800012e5  mov     rax, [rcx+8]
0x1800012e9  mov     rcx, r14
0x1800012ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012f1  test    eax, eax
0x1800012f3  jz      loc_180001393
0x1800012f9  mov     rax, [r13+0]
0x1800012fd  lea     r8, [rbp+47h+arg_0]
0x180001301  mov     [rsp+0D0h+var_88], r12
0x180001306  lea     rdx, [rbp+47h+arg_8]
0x18000130a  mov     [rsp+0D0h+var_90], r12
0x18000130f  xor     r9d, r9d
0x180001312  mov     [rsp+0D0h+var_98], r12
0x180001317  mov     rcx, r13
0x18000131a  mov     rax, [rax+0B8h]
0x180001321  mov     [rsp+0D0h+var_A0], r12
0x180001326  mov     [rsp+0D0h+var_A8], r12
0x18000132b  mov     [rsp+0D0h+var_B0], r12
0x180001330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001335  mov     r14d, 191h
0x18000133b  cmp     [rbp+47h+arg_8], r14w
0x180001340  jnz     short loc_1800013A6
0x180001342  mov     rax, [rsi]
0x180001345  lea     r8, [rbp+47h+var_68]
0x180001349  mov     rdx, rbx
0x18000134c  mov     rcx, rsi
0x18000134f  mov     rax, [rax]
0x180001352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001357  mov     edi, eax
0x180001359  test    eax, eax
0x18000135b  js      short loc_18000139A
0x18000135d  mov     rax, [rsi]
0x180001360  lea     r8, [rbp+47h+arg_28]
0x180001364  mov     rdx, rbx
0x180001367  mov     [rbp+47h+arg_28], r12d
0x18000136b  mov     rcx, rsi
0x18000136e  mov     rax, [rax+10h]
0x180001372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001377  test    eax, eax
0x180001379  js      short loc_180001393
0x18000137b  cmp     [rbp+47h+arg_28], r12d
0x18000137f  jz      short loc_180001393
0x180001381  mov     rax, [rsi]
0x180001384  mov     rdx, rbx
0x180001387  mov     rcx, rsi
0x18000138a  mov     rax, [rax+20h]
0x18000138e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001393  xor     eax, eax
0x180001395  jmp     loc_18000122A
0x18000139a  lea     r12, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800013a1  jmp     loc_1800015A6
0x1800013a6  mov     rax, [rbx]
0x1800013a9  mov     rcx, rbx
0x1800013ac  mov     rax, [rax+0F0h]
0x1800013b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013b8  mov     r8, rax
0x1800013bb  mov     rcx, [rax]
0x1800013be  mov     rax, [rcx+38h]
0x1800013c2  mov     rcx, r8
0x1800013c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013ca  mov     r8, rax
0x1800013cd  mov     rdx, rdi
0x1800013d0  mov     rcx, [rax]
0x1800013d3  mov     rax, [rcx]
0x1800013d6  mov     rcx, r8
0x1800013d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013de  mov     r14, rax
0x1800013e1  test    rax, rax
0x1800013e4  jz      short loc_180001393
0x1800013e6  cmp     [rax+80h], r12d
0x1800013ed  jnz     short loc_18000144C
0x1800013ef  lea     rcx, [rax+48h]
0x1800013f3  call    cs:__imp_?IsEmpty@STRA@@QEBA_NXZ; STRA::IsEmpty(void)
0x1800013f9  test    al, al
0x1800013fb  jnz     short loc_18000144C
0x1800013fd  mov     rax, [r13+0]
0x180001401  lea     rcx, [r14+48h]
0x180001405  mov     rsi, [rax+28h]
0x180001409  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18000140f  lea     rcx, [r14+48h]
0x180001413  mov     edi, eax
0x180001415  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000141b  movzx   r9d, di
0x18000141f  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x180001424  mov     r8, rax
0x180001427  lea     rdx, aWwwAuthenticat; "WWW-Authenticate"
0x18000142e  mov     rax, rsi
0x180001431  mov     rcx, r13
0x180001434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001439  test    eax, eax
0x18000143b  js      loc_180001393
0x180001441  mov     dword ptr [r14+80h], 1
0x18000144c  cmp     [r14+0C4h], r12d
0x180001453  jz      loc_180001393
0x180001459  mov     rax, [rbx]
0x18000145c  mov     rcx, rbx
0x18000145f  mov     rax, [rax+20h]
0x180001463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001468  mov     r8, [r14+0C8h]
0x18000146f  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180001476  mov     rcx, [rax]
0x180001479  mov     r10, [rcx+28h]
0x18000147d  inc     r9
0x180001480  cmp     [r8+r9], r12b
0x180001484  jnz     short loc_18000147D
0x180001486  mov     rcx, rax
0x180001489  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x18000148e  mov     rax, r10
0x180001491  lea     rdx, aPersistentAuth; "Persistent-Auth"
0x180001498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000149d  jmp     loc_180001393
0x1800014a2  mov     rax, [rbx]
0x1800014a5  mov     rcx, rbx
0x1800014a8  mov     rax, [rax+30h]
0x1800014ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014b1  mov     rdx, rax
0x1800014b4  mov     rcx, [rax]
  ... truncated ...
```
