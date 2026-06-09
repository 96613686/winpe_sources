# AUTH_PROVIDER::DoWork(ulong,IHttpContext *,IHttpEventProvider *,void *,IHttpServer *)

- ea: `0x180005f04`
- end: `0x1800066a6`
- name: `?DoWork@AUTH_PROVIDER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAXPEAVIHttpServer@@@Z`
- size: `1954`
- prototype: ``
- caller_count: `17`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002650`
- `0x1800026b0`
- `0x180002710`
- `0x180002770`
- `0x1800027d0`
- `0x180002830`
- `0x180002890`
- `0x1800028f0`
- `0x180002950`
- `0x1800029b0`
- `0x180002a10`
- `0x180002c70`
- `0x180002cd0`
- `0x180002d30`
- `0x180002d90`
- `0x180002e30`
- `0x180002f10`

## callees

- `0x180005f04`
- `0x1800066ac`
- `0x1800067e4`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall AUTH_PROVIDER::DoWork(__int64 a1, int a2, __int64 *a3, __int64 *a4, int a5, int a6)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 *v8; // rsi
  __int64 (__fastcall *v11)(__int64 *); // rax
  __int64 v13; // r15
  __int64 v14; // rcx
  int v15; // ebx
  __int64 (__fastcall **v16)(void *, __int64 *, __int64 *); // rax
  __int64 v18; // rax
  __int64 (__fastcall ***v19)(_QWORD, __int64); // rax
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
  v7 = qword_18000D800;
  v8 = (__int64 *)s_pIisCertmapAuthProvider;
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
      v19 = (__int64 (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 56LL))(v18);
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
0x180005f04  mov     [rsp-8+arg_18], rbx
0x180005f09  mov     [rsp-8+arg_0], rcx
0x180005f0e  push    rbp
0x180005f0f  push    rsi
0x180005f10  push    rdi
0x180005f11  push    r12
0x180005f13  push    r13
0x180005f15  push    r14
0x180005f17  push    r15
0x180005f19  lea     rbp, [rsp-10h]
0x180005f1e  sub     rsp, 110h
0x180005f25  mov     rax, [r8]
0x180005f28  xor     r13d, r13d
0x180005f2b  mov     rbx, cs:qword_18000D800
0x180005f32  mov     rcx, r8
0x180005f35  mov     rsi, cs:?s_pIisCertmapAuthProvider@@3PEAVIISCERTMAP_AUTH_PROVIDER@@EA; IISCERTMAP_AUTH_PROVIDER * s_pIisCertmapAuthProvider
0x180005f3c  mov     r12, r9
0x180005f3f  mov     rdi, r8
0x180005f42  mov     [rbp+40h+arg_28], r13d
0x180005f46  mov     rax, [rax+20h]
0x180005f4a  mov     r14d, edx
0x180005f4d  mov     [rsp+140h+var_E0], r13
0x180005f52  mov     [rbp+40h+var_A0], r13
0x180005f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f5b  mov     r15, rax
0x180005f5e  cmp     r14d, 20000000h
0x180005f65  jnz     loc_180006121
0x180005f6b  mov     rcx, [r12]
0x180005f6f  mov     [rbp+40h+arg_8], r13w
0x180005f74  mov     word ptr [rbp+40h+arg_0], r13w
0x180005f79  mov     rax, [rcx+8]
0x180005f7d  mov     rcx, r12
0x180005f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f85  test    eax, eax
0x180005f87  jz      loc_18000602E
0x180005f8d  mov     rax, [r15]
0x180005f90  lea     r8, [rbp+40h+arg_0]
0x180005f94  mov     [rsp+140h+var_F8], r13
0x180005f99  lea     rdx, [rbp+40h+arg_8]
0x180005f9d  mov     [rsp+140h+var_100], r13
0x180005fa2  xor     r9d, r9d
0x180005fa5  mov     [rsp+140h+var_108], r13
0x180005faa  mov     rcx, r15
0x180005fad  mov     rax, [rax+0B8h]
0x180005fb4  mov     [rsp+140h+var_110], r13
0x180005fb9  mov     [rsp+140h+var_118], r13
0x180005fbe  mov     [rsp+140h+var_120], r13
0x180005fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fc8  mov     r12d, 191h
0x180005fce  cmp     [rbp+40h+arg_8], r12w
0x180005fd3  jnz     short loc_18000604B
0x180005fd5  mov     rax, [rsi]
0x180005fd8  lea     r8, [rsp+140h+var_E0]
0x180005fdd  mov     rdx, rdi
0x180005fe0  mov     rcx, rsi
0x180005fe3  mov     rax, [rax]
0x180005fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005feb  mov     ebx, eax
0x180005fed  test    eax, eax
0x180005fef  js      loc_18000628F
0x180005ff5  mov     rax, [rsi]
0x180005ff8  lea     r8, [rsp+140h+var_D8]
0x180005ffd  mov     rdx, rdi
0x180006000  mov     dword ptr [rsp+140h+var_D8], r13d
0x180006005  mov     rcx, rsi
0x180006008  mov     rax, [rax+10h]
0x18000600c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006011  test    eax, eax
0x180006013  js      short loc_18000602E
0x180006015  cmp     dword ptr [rsp+140h+var_D8], r13d
0x18000601a  jz      short loc_18000602E
0x18000601c  mov     rax, [rsi]
0x18000601f  mov     rdx, rdi
0x180006022  mov     rcx, rsi
0x180006025  mov     rax, [rax+20h]
0x180006029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000602e  xor     eax, eax
0x180006030  mov     rbx, [rsp+140h+arg_18]
0x180006038  add     rsp, 110h
0x18000603f  pop     r15
0x180006041  pop     r14
0x180006043  pop     r13
0x180006045  pop     r12
0x180006047  pop     rdi
0x180006048  pop     rsi
0x180006049  pop     rbp
0x18000604a  retn
0x18000604b  mov     rax, [rdi]
0x18000604e  mov     rcx, rdi
0x180006051  mov     rax, [rax+0F0h]
0x180006058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000605d  mov     r8, rax
0x180006060  mov     rcx, [rax]
0x180006063  mov     rax, [rcx+38h]
0x180006067  mov     rcx, r8
0x18000606a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000606f  mov     r8, rax
0x180006072  mov     rdx, rbx
0x180006075  mov     rcx, [rax]
0x180006078  mov     rax, [rcx]
0x18000607b  mov     rcx, r8
0x18000607e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006083  mov     rbx, rax
0x180006086  test    rax, rax
0x180006089  jz      short loc_18000602E
0x18000608b  cmp     [rax+80h], r13d
0x180006092  jnz     short loc_1800060CE
0x180006094  mov     r9d, [rax+78h]
0x180006098  test    r9d, r9d
0x18000609b  jz      short loc_1800060CE
0x18000609d  mov     rcx, [r15]
0x1800060a0  lea     rdx, aWwwAuthenticat; "WWW-Authenticate"
0x1800060a7  mov     r8, [rbx+68h]
0x1800060ab  mov     dword ptr [rsp+140h+var_120], r13d
0x1800060b0  mov     rax, [rcx+28h]
0x1800060b4  mov     rcx, r15
0x1800060b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060bc  test    eax, eax
0x1800060be  js      loc_18000602E
0x1800060c4  mov     dword ptr [rbx+80h], 1
0x1800060ce  cmp     [rbx+0C4h], r13d
0x1800060d5  jz      loc_18000602E
0x1800060db  mov     rax, [rdi]
0x1800060de  mov     rcx, rdi
0x1800060e1  mov     rax, [rax+20h]
0x1800060e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ea  mov     r8, [rbx+0C8h]
0x1800060f1  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800060f5  mov     rcx, [rax]
0x1800060f8  mov     r10, [rcx+28h]
0x1800060fc  inc     r9
0x1800060ff  cmp     [r8+r9], r13b
0x180006103  jnz     short loc_1800060FC
0x180006105  mov     rcx, rax
0x180006108  mov     dword ptr [rsp+140h+var_120], r13d
0x18000610d  mov     rax, r10
0x180006110  lea     rdx, aPersistentAuth; "Persistent-Auth"
0x180006117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000611c  jmp     loc_18000602E
0x180006121  cmp     r14d, 2
0x180006125  jnz     loc_18000602E
0x18000612b  mov     rax, [rdi]
0x18000612e  mov     rcx, rdi
0x180006131  mov     rax, [rax+30h]
0x180006135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000613a  test    rax, rax
0x18000613d  jz      loc_1800061E5
0x180006143  mov     rax, [rdi]
0x180006146  mov     rcx, rdi
0x180006149  mov     rax, [rax+30h]
0x18000614d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006152  mov     rdx, rax
0x180006155  mov     rcx, [rax]
0x180006158  mov     rax, [rcx+10h]
0x18000615c  mov     rcx, rdx
0x18000615f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006164  test    rax, rax
0x180006167  jz      short loc_180006194
0x180006169  mov     rax, [rdi]
0x18000616c  mov     rcx, rdi
0x18000616f  mov     rax, [rax+30h]
0x180006173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006178  mov     rdx, rax
0x18000617b  mov     rcx, [rax]
0x18000617e  mov     rax, [rcx+10h]
0x180006182  mov     rcx, rdx
0x180006185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000618a  cmp     [rax], r13w
0x18000618e  jnz     loc_18000602E
0x180006194  mov     rax, [rdi]
0x180006197  mov     rcx, rdi
0x18000619a  mov     rax, [rax+30h]
0x18000619e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061a3  mov     rdx, rax
0x1800061a6  mov     rcx, [rax]
0x1800061a9  mov     rax, [rcx+8]
0x1800061ad  mov     rcx, rdx
0x1800061b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061b5  test    rax, rax
0x1800061b8  jz      short loc_1800061E5
0x1800061ba  mov     rax, [rdi]
0x1800061bd  mov     rcx, rdi
0x1800061c0  mov     rax, [rax+30h]
0x1800061c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061c9  mov     rdx, rax
0x1800061cc  mov     rcx, [rax]
0x1800061cf  mov     rax, [rcx+8]
0x1800061d3  mov     rcx, rdx
0x1800061d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061db  cmp     [rax], r13w
0x1800061df  jnz     loc_18000602E
0x1800061e5  mov     rax, [rdi]
0x1800061e8  mov     rcx, rdi
0x1800061eb  mov     rax, [rax+110h]
0x1800061f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061f7  mov     r8, rax
0x1800061fa  lea     rdx, [rsp+140h+var_D0]
0x1800061ff  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180006206  xorps   xmm0, xmm0
0x180006209  mov     [rsp+140h+var_D0], rax
0x18000620e  movdqu  [rsp+140h+var_C8], xmm0
0x180006214  mov     rcx, [r8]
0x180006217  mov     rax, [rcx]
0x18000621a  mov     rcx, r8
0x18000621d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006222  test    eax, eax
0x180006224  js      short loc_18000626F
0x180006226  cmp     dword ptr [rbp+40h+var_C8+8], r13d
0x18000622a  jz      short loc_18000626F
0x18000622c  cmp     dword ptr [rsp+140h+var_C8+4], 4
0x180006231  jb      short loc_18000626F
0x180006233  cmp     dword ptr [rsp+140h+var_C8], 2
0x180006238  jz      short loc_180006241
0x18000623a  test    byte ptr [rsp+140h+var_C8], 2
0x18000623f  jz      short loc_18000626F
0x180006241  mov     rax, [rsi]
0x180006244  mov     rcx, rsi
0x180006247  mov     rax, [rax+38h]
0x18000624b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006250  mov     rcx, [rdi]
0x180006253  mov     ebx, eax
0x180006255  mov     rax, [rcx+110h]
0x18000625c  mov     rcx, rdi
0x18000625f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006264  mov     r8d, ebx; unsigned int
0x180006267  mov     rcx, rax; struct IHttpTraceContext *
0x18000626a  call    ?RaiseEvent@AUTH_START@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z; IISAuthenticationEvents::AUTH_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)
0x18000626f  mov     [rbp+40h+var_A8], r13
0x180006273  mov     [rbp+40h+arg_20], r13d
0x180006277  mov     [rbp+40h+arg_10], r13d
0x18000627b  test    r12, r12
0x18000627e  jnz     loc_180006331
0x180006284  mov     ebx, 80070057h
0x180006289  mov     r12d, 191h
0x18000628f  mov     rax, [r15]
0x180006292  mov     rcx, r15
0x180006295  mov     rax, [rax+8]
0x180006299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000629e  mov     [rax+218h], r13w
0x1800062a6  mov     rcx, [rsp+140h+var_E0]
0x1800062ab  test    rcx, rcx
0x1800062ae  jz      loc_180006550
0x1800062b4  mov     rax, [rcx]
0x1800062b7  lea     r8, [rbp+40h+var_A0]
0x1800062bb  lea     rdx, IID_IAppHostConfigException
0x1800062c2  mov     rax, [rax]
0x1800062c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062ca  mov     rcx, [rbp+40h+var_A0]
0x1800062ce  lea     r8, aInternalServer; "Internal Server Error"
0x1800062d5  mov     rax, [r15]
0x1800062d8  mov     edx, 1F4h
0x1800062dd  mov     dword ptr [rsp+140h+var_110], r13d
0x1800062e2  mov     r9d, 13h
0x1800062e8  mov     [rsp+140h+var_118], rcx
0x1800062ed  mov     rcx, r15
0x1800062f0  mov     dword ptr [rsp+140h+var_120], ebx
0x1800062f4  mov     rax, [rax+18h]
0x1800062f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062fd  mov     rcx, [rbp+40h+var_A0]
0x180006301  test    rcx, rcx
0x180006304  jz      short loc_180006316
0x180006306  mov     rax, [rcx]
0x180006309  mov     rax, [rax+10h]
0x18000630d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006312  mov     [rbp+40h+var_A0], r13
0x180006316  mov     rcx, [rsp+140h+var_E0]
0x18000631b  mov     rax, [rcx]
0x18000631e  mov     rax, [rax+10h]
0x180006322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006327  mov     [rsp+140h+var_E0], r13
0x18000632c  jmp     loc_18000657D
0x180006331  mov     rax, [rsi]
0x180006334  lea     r9, [rsp+140h+var_E0]
0x180006339  lea     r8, [rbp+40h+arg_20]
0x18000633d  mov     rdx, rdi
0x180006340  mov     rcx, rsi
0x180006343  mov     rax, [rax+8]
0x180006347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000634c  mov     ebx, eax
0x18000634e  test    eax, eax
0x180006350  js      loc_180006289
0x180006356  cmp     [rbp+40h+arg_20], r13d
0x18000635a  jz      loc_1800063EA
0x180006360  mov     rax, [rdi]
0x180006363  mov     rcx, rdi
0x180006366  mov     rax, [rax+110h]
0x18000636d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006372  mov     r8, rax
0x180006375  lea     rdx, [rsp+140h+var_D0]
0x18000637a  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180006381  xorps   xmm0, xmm0
0x180006384  mov     [rsp+140h+var_D0], rax
0x180006389  movdqu  [rsp+140h+var_C8], xmm0
0x18000638f  mov     rcx, [r8]
0x180006392  mov     rax, [rcx]
0x180006395  mov     rcx, r8
0x180006398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000639d  test    eax, eax
0x18000639f  js      short loc_1800063EA
0x1800063a1  cmp     dword ptr [rbp+40h+var_C8+8], r13d
  ... truncated ...
```
