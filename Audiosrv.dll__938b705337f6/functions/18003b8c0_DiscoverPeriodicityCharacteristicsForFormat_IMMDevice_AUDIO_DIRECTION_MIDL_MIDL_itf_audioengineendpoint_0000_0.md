# DiscoverPeriodicityCharacteristicsForFormat(IMMDevice *,AUDIO_DIRECTION,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX const *,PacketSizeConstraints *,DPCF_OPTIONS,__int64,uint *,uint *,uint *,uint *,uint *)

- ea: `0x18003b8c0`
- end: `0x18003bf20`
- name: `?DiscoverPeriodicityCharacteristicsForFormat@@YAJPEAUIMMDevice@@W4AUDIO_DIRECTION@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEBUtWAVEFORMATEX@@PEAUPacketSizeConstraints@@W4DPCF_OPTIONS@@_JPEAI8888@Z`
- size: `1632`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003afe0`
- `0x18006b828`
- `0x180144e50`

## callees

- `0x1800126bc`
- `0x18003b8c0`
- `0x18003bf30`
- `0x18006ed98`
- `0x1800d074c`
- `0x18015f540`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b9a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b9a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ba38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ba48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ba8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003babb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bb96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbe5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ba38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ba48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ba8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003babb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bb96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbe5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc67`
- `MMDevAPI!__imp_GetClassFromEndpointId` at `0x18003b97c`
- `MMDevAPI!__imp_GetClassFromEndpointId` at `0x18003b97c`
- `MMDevAPI!__imp_GetSessionIdFromEndpointId` at `0x18003b9c5`
- `MMDevAPI!__imp_GetSessionIdFromEndpointId` at `0x18003b9c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 DiscoverPeriodicityCharacteristicsForFormat(__int64 a1, unsigned int a2, int a3, struct _GUID *a4, ...)
{
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // r12
  unsigned __int16 *v7; // r14
  double v8; // xmm1_8
  unsigned int *v9; // rdi
  unsigned int *v10; // r13
  int PacketSizesFromConstraints; // ebx
  struct PacketSizeConstraints *v12; // r13
  unsigned int v13; // edi
  _DWORD *v14; // rax
  _DWORD *v15; // rbx
  int v16; // eax
  unsigned int v17; // esi
  __int64 v19; // rdx
  unsigned int v20; // eax
  unsigned int *v21; // rsi
  unsigned int *v22; // rdx
  unsigned int *v23; // rcx
  unsigned int v24; // eax
  unsigned int *v25; // rdx
  unsigned int *v26; // r8
  unsigned int *v27; // rcx
  unsigned int v28; // eax
  int v29; // eax
  unsigned int v30; // edi
  unsigned int v31; // eax
  int v32; // eax
  unsigned int v33; // r12d
  unsigned int v34; // eax
  unsigned int v35; // r12d
  bool v36; // sf
  int i; // eax
  unsigned int *v38; // rax
  unsigned int v39; // ecx
  int v40; // [rsp+20h] [rbp-61h]
  int v41; // [rsp+20h] [rbp-61h]
  int v42; // [rsp+20h] [rbp-61h]
  unsigned __int64 v43; // [rsp+28h] [rbp-59h]
  unsigned __int64 v44; // [rsp+30h] [rbp-51h]
  LPVOID pv[2]; // [rsp+60h] [rbp-21h] BYREF
  struct _GUID v46; // [rsp+70h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]
  _DWORD *v48; // [rsp+D0h] [rbp+4Fh] BYREF
  unsigned int v49; // [rsp+D8h] [rbp+57h]
  int v50; // [rsp+E0h] [rbp+5Fh]
  struct _GUID *v51; // [rsp+E8h] [rbp+67h]
  void *Src; // [rsp+F0h] [rbp+6Fh] BYREF
  va_list Srca; // [rsp+F0h] [rbp+6Fh]
  struct PacketSizeConstraints *v54; // [rsp+F8h] [rbp+77h]
  __int64 v55; // [rsp+100h] [rbp+7Fh]
  unsigned __int64 v56; // [rsp+108h] [rbp+87h] BYREF
  va_list va1; // [rsp+108h] [rbp+87h]
  unsigned int *v58; // [rsp+110h] [rbp+8Fh]
  unsigned int *v59; // [rsp+118h] [rbp+97h] BYREF
  va_list va2; // [rsp+118h] [rbp+97h]
  unsigned int *v61; // [rsp+120h] [rbp+9Fh] BYREF
  va_list va3; // [rsp+120h] [rbp+9Fh]
  unsigned int *v63; // [rsp+128h] [rbp+A7h] BYREF
  va_list va4; // [rsp+128h] [rbp+A7h]
  unsigned int *v65; // [rsp+130h] [rbp+AFh]
  va_list va5; // [rsp+138h] [rbp+B7h] BYREF

  va_start(va5, a4);
  va_start(va4, a4);
  va_start(va3, a4);
  va_start(va2, a4);
  va_start(va1, a4);
  va_start(Srca, a4);
  Src = va_arg(va1, void *);
  v54 = va_arg(va1, struct PacketSizeConstraints *);
  v55 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v56 = va_arg(va2, _QWORD);
  v58 = va_arg(va2, unsigned int *);
  va_copy(va3, va2);
  v59 = va_arg(va3, unsigned int *);
  va_copy(va4, va3);
  v61 = va_arg(va4, unsigned int *);
  va_copy(va5, va4);
  v63 = va_arg(va5, unsigned int *);
  v65 = va_arg(va5, unsigned int *);
  v51 = a4;
  v50 = a3;
  v49 = a2;
  v5 = 100000;
  v6 = v56;
  if ( v56 )
    v5 = v56;
  v7 = (unsigned __int16 *)Src;
  v8 = (double)(int)v5 * (double)*((int *)Src + 1) / 10000000.0 + 0.5;
  v9 = v63;
  *v63 = (int)v8;
  *v61 = (int)v8;
  *v59 = (int)v8;
  v10 = v58;
  *v58 = (int)v8;
  pv[0] = 0;
  PacketSizesFromConstraints = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)a1 + 40LL))(a1, pv);
  if ( PacketSizesFromConstraints < 0 )
  {
    v19 = 551;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)PacketSizesFromConstraints,
      v40);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    return (unsigned int)PacketSizesFromConstraints;
  }
  if ( (unsigned int)GetClassFromEndpointId(pv[0]) )
    goto LABEL_26;
  v12 = v54;
  if ( v54 && (v55 & 2) != 0 )
  {
    LODWORD(v63) = 0;
    LODWORD(v56) = 0;
    LODWORD(Src) = 0;
    LODWORD(v48) = 0;
    v46 = *v51;
    PacketSizesFromConstraints = GetPacketSizesFromConstraints(
                                   v54,
                                   *((_DWORD *)v7 + 2),
                                   v7[6],
                                   &v46,
                                   v5,
                                   v43,
                                   v44,
                                   (unsigned int *)va4,
                                   (unsigned int *)va1,
                                   (unsigned int *)Srca,
                                   (unsigned int *)&v48);
    if ( PacketSizesFromConstraints < 0 )
    {
      v19 = 572;
      goto LABEL_16;
    }
    v24 = (unsigned int)v63;
    *v9 = (unsigned int)v63;
    v25 = v61;
    *v61 = v24;
    v26 = v59;
    *v59 = v24;
    v27 = v58;
    *v58 = v24;
    if ( !v50 && !v6 )
    {
      *v26 = v56;
      *v25 = (unsigned int)Src;
      if ( v49 != 1 || (v28 = (unsigned int)v48, !*(_BYTE *)v12) )
        v28 = *v27;
      *v9 = v28;
    }
    v10 = v27;
    goto LABEL_26;
  }
  v13 = v7[8] + 64;
  v14 = CoTaskMemAlloc(v13);
  v15 = v14;
  v48 = v14;
  if ( !v14 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25A,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)0x8007000ELL,
      v40);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    return 2147942414LL;
  }
  *v14 = v7[8] + 64;
  v14[1] = GetSessionIdFromEndpointId(pv[0]);
  v15[2] = v50;
  *(struct _GUID *)(v15 + 3) = *v51;
  memcpy_0(v15 + 11, v7, v7[8] + 18LL);
  LODWORD(v56) = 0;
  v41 = v5;
  v16 = CheckConnectorSupportForPeriodicity(a1, v49, v15, v13);
  v17 = v16;
  if ( v16 < 0 )
  {
    if ( v16 == -2005139404 )
    {
      CoTaskMemFree(v15);
      if ( pv[0] )
        CoTaskMemFree(pv[0]);
      return 2289827892LL;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x267,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
        (const char *)(unsigned int)v16,
        v41);
      CoTaskMemFree(v15);
      if ( pv[0] )
        CoTaskMemFree(pv[0]);
      return v17;
    }
  }
  v20 = v56;
  *v63 = v56;
  v21 = v61;
  *v61 = v20;
  v22 = v59;
  *v59 = v20;
  v23 = v58;
  *v58 = v20;
  if ( v50 || v6 )
    goto LABEL_23;
  if ( !v12 )
  {
    if ( (v55 & 1) != 0 )
    {
      LODWORD(v61) = 0;
      v32 = HnsToBlocksRU(0x61A8u, *((_DWORD *)v7 + 2), v7[6], (unsigned int *)va3);
      v33 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x293,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
          (const char *)(unsigned int)v32,
          v41);
        CoTaskMemFree(v15);
        if ( pv[0] )
          CoTaskMemFree(pv[0]);
        return v33;
      }
      v34 = ((_DWORD)v61 - 1) & 0xFFFFFFE0;
      v10 = v58;
      v35 = v49;
      while ( 1 )
      {
        LODWORD(v61) = v34 + 32;
        if ( v34 + 32 >= *v10 )
          break;
        v36 = (int)CheckConnectorSupportForPeriodicity(a1, v35, v15, v13) < 0;
        v34 = (unsigned int)v61;
        if ( !v36 && (_DWORD)v61 == (_DWORD)v56 )
        {
          *v21 = v56;
          break;
        }
      }
      if ( *v21 < *v10 )
      {
        for ( i = 0; ; i = (_DWORD)v58 + 1 )
        {
          LODWORD(v58) = i;
          if ( i >= 3 )
            break;
          LODWORD(Src) = 32 * (1 << i);
          LODWORD(v61) = (_DWORD)Src * ((*v21 - 1) / (unsigned int)Src + 1);
          if ( (unsigned int)v61 < *v10
            && (int)CheckConnectorSupportForPeriodicity(a1, v35, v15, v13) >= 0
            && (_DWORD)v56 == (_DWORD)v61 )
          {
            v38 = v59;
            *v59 = (unsigned int)Src;
            goto LABEL_71;
          }
        }
        v38 = v59;
LABEL_71:
        v39 = *v10;
        v9 = v63;
        if ( *v38 == *v10 )
        {
          *v38 = v39;
          *v21 = v39;
        }
        goto LABEL_25;
      }
LABEL_24:
      v9 = v63;
LABEL_25:
      CoTaskMemFree(v15);
LABEL_26:
      *v65 = *v9;
      if ( *v9 > *v10 )
        *v9 = *v10;
      if ( pv[0] )
        CoTaskMemFree(pv[0]);
      return 0;
    }
LABEL_23:
    v10 = v23;
    goto LABEL_24;
  }
  LODWORD(v59) = 0;
  v46 = *v51;
  v29 = GetPacketSizesFromConstraints(
          v12,
          *((_DWORD *)v7 + 2),
          v7[6],
          &v46,
          0x186A0u,
          (unsigned __int64)va1,
          v44,
          v23,
          v22,
          v21,
          (unsigned int *)va2);
  v30 = v29;
  if ( v29 >= 0 )
  {
    if ( v49 == 1 && *(_BYTE *)v12 )
    {
      v31 = (unsigned int)v59;
      v10 = v58;
    }
    else
    {
      v10 = v58;
      v31 = *v58;
    }
    v9 = v63;
    *v63 = v31;
    goto LABEL_25;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x282,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
    (const char *)(unsigned int)v29,
    v42);
  CoTaskMemFree(v15);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return v30;
}

```

## disassembly

```asm
0x18003b8c0  mov     [rsp-8+arg_18], r9
0x18003b8c5  mov     [rsp-8+arg_10], r8d
0x18003b8ca  mov     [rsp-8+arg_8], edx
0x18003b8ce  push    rbp
0x18003b8cf  push    rbx
0x18003b8d0  push    rsi
0x18003b8d1  push    rdi
0x18003b8d2  push    r12
0x18003b8d4  push    r13
0x18003b8d6  push    r14
0x18003b8d8  push    r15
0x18003b8da  lea     rbp, [rsp-7]
0x18003b8df  sub     rsp, 88h
0x18003b8e6  mov     r15, rcx
0x18003b8e9  mov     esi, 186A0h
0x18003b8ee  mov     r12, [rbp+3Fh+arg_38]
0x18003b8f5  test    r12, r12
0x18003b8f8  cmovnz  rsi, r12
0x18003b8fc  mov     r14, [rbp+3Fh+Src]
0x18003b900  xorps   xmm1, xmm1
0x18003b903  cvtsi2sd xmm1, rsi
0x18003b908  mov     eax, [r14+4]
0x18003b90c  xorps   xmm0, xmm0
0x18003b90f  cvtsi2sd xmm0, rax
0x18003b914  mulsd   xmm1, xmm0
0x18003b918  divsd   xmm1, cs:__real@416312d000000000
0x18003b920  addsd   xmm1, cs:__real@3fe0000000000000
0x18003b928  cvttsd2si rax, xmm1
0x18003b92d  mov     rdi, [rbp+3Fh+arg_58]
0x18003b934  mov     [rdi], eax
0x18003b936  mov     rcx, [rbp+3Fh+arg_50]
0x18003b93d  mov     [rcx], eax
0x18003b93f  mov     rcx, [rbp+3Fh+arg_48]
0x18003b946  mov     [rcx], eax
0x18003b948  mov     r13, [rbp+3Fh+arg_40]
0x18003b94f  mov     [r13+0], eax
0x18003b953  mov     [rbp+3Fh+pv], 0
0x18003b95b  mov     rax, [r15]
0x18003b95e  lea     rdx, [rbp+3Fh+pv]
0x18003b962  mov     rcx, r15
0x18003b965  mov     rax, [rax+28h]
0x18003b969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b96e  mov     ebx, eax
0x18003b970  test    eax, eax
0x18003b972  js      loc_18003BA99
0x18003b978  mov     rcx, [rbp+3Fh+pv]
0x18003b97c  call    cs:__imp_GetClassFromEndpointId
0x18003b982  test    eax, eax
0x18003b984  jnz     loc_18003BB9C
0x18003b98a  mov     r13, [rbp+3Fh+arg_28]
0x18003b98e  test    r13, r13
0x18003b991  jnz     loc_18003BAC5
0x18003b997  movzx   edi, word ptr [r14+10h]
0x18003b99c  add     edi, 40h ; '@'
0x18003b99f  mov     ecx, edi; cb
0x18003b9a1  call    cs:__imp_CoTaskMemAlloc
0x18003b9a7  mov     rbx, rax
0x18003b9aa  mov     [rbp+3Fh+arg_0], rax
0x18003b9ae  test    rax, rax
0x18003b9b1  jz      loc_18003BA67
0x18003b9b7  movzx   ecx, word ptr [r14+10h]
0x18003b9bc  add     ecx, 40h ; '@'
0x18003b9bf  mov     [rax], ecx
0x18003b9c1  mov     rcx, [rbp+3Fh+pv]
0x18003b9c5  call    cs:__imp_GetSessionIdFromEndpointId
0x18003b9cb  mov     [rbx+4], eax
0x18003b9ce  mov     eax, [rbp+3Fh+arg_10]
0x18003b9d1  mov     [rbx+8], eax
0x18003b9d4  mov     rax, [rbp+3Fh+arg_18]
0x18003b9d8  movaps  xmm0, xmmword ptr [rax]
0x18003b9db  movups  xmmword ptr [rbx+0Ch], xmm0
0x18003b9df  movzx   r8d, word ptr [r14+10h]
0x18003b9e4  add     r8, 12h; Size
0x18003b9e8  lea     rcx, [rbx+2Ch]; void *
0x18003b9ec  mov     rdx, r14; Src
0x18003b9ef  call    memcpy_0
0x18003b9f4  mov     dword ptr [rbp+3Fh+arg_38], 0
0x18003b9fe  lea     rax, [rbp+3Fh+arg_38]
0x18003ba05  mov     [rsp+0C0h+var_98], rax; unsigned __int64
0x18003ba0a  mov     [rsp+0C0h+var_A0], rsi; int
0x18003ba0f  mov     r9d, edi
0x18003ba12  mov     r8, rbx
0x18003ba15  mov     edx, [rbp+3Fh+arg_8]
0x18003ba18  mov     rcx, r15
0x18003ba1b  call    ?CheckConnectorSupportForPeriodicity@@YAJPEAUIMMDevice@@W4AUDIO_DIRECTION@@PEAUAUDIO_ENDPOINT_SHARED_CREATE_PARAMS_FOR_KS_ENDPOINTS@@I_JPEAI@Z; CheckConnectorSupportForPeriodicity(IMMDevice *,AUDIO_DIRECTION,AUDIO_ENDPOINT_SHARED_CREATE_PARAMS_FOR_KS_ENDPOINTS *,uint,__int64,uint *)
0x18003ba20  mov     esi, eax
0x18003ba22  test    eax, eax
0x18003ba24  jns     loc_18003BB55
0x18003ba2a  cmp     eax, 887C0034h
0x18003ba2f  jnz     loc_18003BBC9
0x18003ba35  mov     rcx, rbx; pv
0x18003ba38  call    cs:__imp_CoTaskMemFree
0x18003ba3e  nop
0x18003ba3f  mov     rcx, [rbp+3Fh+pv]; pv
0x18003ba43  test    rcx, rcx
0x18003ba46  jz      short loc_18003BA4E
0x18003ba48  call    cs:__imp_CoTaskMemFree
0x18003ba4e  mov     eax, 887C0034h
0x18003ba53  add     rsp, 88h
0x18003ba5a  pop     r15
0x18003ba5c  pop     r14
0x18003ba5e  pop     r13
0x18003ba60  pop     r12
0x18003ba62  pop     rdi
0x18003ba63  pop     rsi
0x18003ba64  pop     rbx
0x18003ba65  pop     rbp
0x18003ba66  retn
0x18003ba67  mov     rcx, [rbp+47h]; this
0x18003ba6b  mov     r9d, 8007000Eh; char *
0x18003ba71  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x18003ba78  mov     edx, 25Ah; void *
0x18003ba7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ba82  nop
0x18003ba83  mov     rcx, [rbp+3Fh+pv]; pv
0x18003ba87  test    rcx, rcx
0x18003ba8a  jz      short loc_18003BA92
0x18003ba8c  call    cs:__imp_CoTaskMemFree
0x18003ba92  mov     eax, 8007000Eh
0x18003ba97  jmp     short loc_18003BA53
0x18003ba99  mov     edx, 227h; void *
0x18003ba9e  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x18003baa5  mov     r9d, ebx; char *
0x18003baa8  mov     rcx, [rbp+47h]; this
0x18003baac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bab1  nop
0x18003bab2  mov     rcx, [rbp+3Fh+pv]; pv
0x18003bab6  test    rcx, rcx
0x18003bab9  jz      short loc_18003BAC1
0x18003babb  call    cs:__imp_CoTaskMemFree
0x18003bac1  mov     eax, ebx
0x18003bac3  jmp     short loc_18003BA53
0x18003bac5  test    byte ptr [rbp+3Fh+arg_30], 2
0x18003bac9  jz      loc_18003B997
0x18003bacf  mov     dword ptr [rbp+3Fh+arg_58], 0
0x18003bad9  mov     dword ptr [rbp+3Fh+arg_38], 0
0x18003bae3  mov     dword ptr [rbp+3Fh+Src], 0
0x18003baea  mov     dword ptr [rbp+3Fh+arg_0], 0
0x18003baf1  mov     rax, [rbp+3Fh+arg_18]
0x18003baf5  movaps  xmm0, xmmword ptr [rax]
0x18003baf8  movdqa  xmmword ptr [rbp+3Fh+var_50.Data1], xmm0
0x18003bafd  lea     rax, [rbp+3Fh+arg_0]
0x18003bb01  mov     [rsp+0C0h+var_70], rax; unsigned int *
0x18003bb06  lea     rax, [rbp+3Fh+Src]
0x18003bb0a  mov     [rsp+0C0h+var_78], rax; unsigned int *
0x18003bb0f  lea     rax, [rbp+3Fh+arg_38]
0x18003bb16  mov     [rsp+0C0h+var_80], rax; unsigned int *
0x18003bb1b  lea     rax, [rbp+3Fh+arg_58]
0x18003bb22  mov     [rsp+0C0h+var_88], rax; unsigned int *
0x18003bb27  mov     [rsp+0C0h+var_A0], rsi; unsigned __int64
0x18003bb2c  lea     r9, [rbp+3Fh+var_50]; struct _GUID
0x18003bb30  movzx   r8d, word ptr [r14+0Ch]; unsigned __int16
0x18003bb35  mov     edx, [r14+8]; unsigned int
0x18003bb39  mov     rcx, r13; struct PacketSizeConstraints *
0x18003bb3c  call    ?GetPacketSizesFromConstraints@@YAJPEBUPacketSizeConstraints@@KGU_GUID@@_K22PEAI333@Z; GetPacketSizesFromConstraints(PacketSizeConstraints const *,ulong,ushort,_GUID,unsigned __int64,unsigned __int64,unsigned __int64,uint *,uint *,uint *,uint *)
0x18003bb41  mov     ebx, eax
0x18003bb43  test    eax, eax
0x18003bb45  jns     loc_18003BC75
0x18003bb4b  mov     edx, 23Ch
0x18003bb50  jmp     loc_18003BA9E
0x18003bb55  mov     eax, dword ptr [rbp+3Fh+arg_38]
0x18003bb5b  mov     rcx, [rbp+3Fh+arg_58]
0x18003bb62  mov     [rcx], eax
0x18003bb64  mov     rsi, [rbp+3Fh+arg_50]
0x18003bb6b  mov     [rsi], eax
0x18003bb6d  mov     rdx, [rbp+3Fh+arg_48]
0x18003bb74  mov     [rdx], eax
0x18003bb76  mov     rcx, [rbp+3Fh+arg_40]
0x18003bb7d  mov     [rcx], eax
0x18003bb7f  cmp     [rbp+3Fh+arg_10], 0
0x18003bb83  jz      loc_18003BCCD
0x18003bb89  mov     r13, rcx
0x18003bb8c  mov     rdi, [rbp+3Fh+arg_58]
0x18003bb93  mov     rcx, rbx; pv
0x18003bb96  call    cs:__imp_CoTaskMemFree
0x18003bb9c  mov     ecx, [rdi]
0x18003bb9e  mov     rax, [rbp+3Fh+arg_60]
0x18003bba5  mov     [rax], ecx
0x18003bba7  mov     eax, [r13+0]
0x18003bbab  cmp     [rdi], eax
0x18003bbad  ja      loc_18003BF18
0x18003bbb3  mov     rcx, [rbp+3Fh+pv]; pv
0x18003bbb7  test    rcx, rcx
0x18003bbba  jz      short loc_18003BBC2
0x18003bbbc  call    cs:__imp_CoTaskMemFree
0x18003bbc2  xor     eax, eax
0x18003bbc4  jmp     loc_18003BA53
0x18003bbc9  mov     rcx, [rbp+47h]; this
0x18003bbcd  mov     r9d, esi; char *
0x18003bbd0  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x18003bbd7  mov     edx, 267h; void *
0x18003bbdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bbe1  nop
0x18003bbe2  mov     rcx, rbx; pv
0x18003bbe5  call    cs:__imp_CoTaskMemFree
0x18003bbeb  nop
0x18003bbec  mov     rcx, [rbp+3Fh+pv]; pv
0x18003bbf0  test    rcx, rcx
0x18003bbf3  jz      short loc_18003BBFB
0x18003bbf5  call    cs:__imp_CoTaskMemFree
0x18003bbfb  mov     eax, esi
0x18003bbfd  jmp     loc_18003BA53
0x18003bc02  mov     rcx, [rbp+47h]; this
0x18003bc06  mov     r9d, edi; char *
0x18003bc09  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x18003bc10  mov     edx, 282h; void *
0x18003bc15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bc1a  nop
0x18003bc1b  mov     rcx, rbx; pv
0x18003bc1e  call    cs:__imp_CoTaskMemFree
0x18003bc24  nop
0x18003bc25  mov     rcx, [rbp+3Fh+pv]; pv
0x18003bc29  test    rcx, rcx
0x18003bc2c  jz      short loc_18003BC34
0x18003bc2e  call    cs:__imp_CoTaskMemFree
0x18003bc34  mov     eax, edi
0x18003bc36  jmp     loc_18003BA53
0x18003bc3b  mov     rcx, [rbp+47h]; this
0x18003bc3f  mov     r9d, r12d; char *
0x18003bc42  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x18003bc49  mov     edx, 293h; void *
0x18003bc4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bc53  nop
0x18003bc54  mov     rcx, rbx; pv
0x18003bc57  call    cs:__imp_CoTaskMemFree
0x18003bc5d  nop
0x18003bc5e  mov     rcx, [rbp+3Fh+pv]; pv
0x18003bc62  test    rcx, rcx
0x18003bc65  jz      short loc_18003BC6D
0x18003bc67  call    cs:__imp_CoTaskMemFree
0x18003bc6d  mov     eax, r12d
0x18003bc70  jmp     loc_18003BA53
0x18003bc75  mov     eax, dword ptr [rbp+3Fh+arg_58]
0x18003bc7b  mov     [rdi], eax
0x18003bc7d  mov     rdx, [rbp+3Fh+arg_50]
0x18003bc84  mov     [rdx], eax
0x18003bc86  mov     r8, [rbp+3Fh+arg_48]
0x18003bc8d  mov     [r8], eax
0x18003bc90  mov     rcx, [rbp+3Fh+arg_40]
0x18003bc97  mov     [rcx], eax
0x18003bc99  cmp     [rbp+3Fh+arg_10], 0
0x18003bc9d  jnz     short loc_18003BCC5
0x18003bc9f  test    r12, r12
0x18003bca2  jnz     short loc_18003BCC5
0x18003bca4  mov     eax, dword ptr [rbp+3Fh+arg_38]
0x18003bcaa  mov     [r8], eax
0x18003bcad  mov     eax, dword ptr [rbp+3Fh+Src]
0x18003bcb0  mov     [rdx], eax
0x18003bcb2  cmp     [rbp+3Fh+arg_8], 1
0x18003bcb6  jnz     short loc_18003BCC1
0x18003bcb8  cmp     [r13+0], r12b
0x18003bcbc  mov     eax, dword ptr [rbp+3Fh+arg_0]
0x18003bcbf  jnz     short loc_18003BCC3
0x18003bcc1  mov     eax, [rcx]
0x18003bcc3  mov     [rdi], eax
0x18003bcc5  mov     r13, rcx
0x18003bcc8  jmp     loc_18003BB9C
0x18003bccd  test    r12, r12
0x18003bcd0  jnz     loc_18003BB89
0x18003bcd6  test    r13, r13
0x18003bcd9  jz      loc_18003BD69
0x18003bcdf  mov     dword ptr [rbp+3Fh+arg_48], r12d
0x18003bce6  mov     rax, [rbp+3Fh+arg_18]
0x18003bcea  movaps  xmm0, xmmword ptr [rax]
0x18003bced  movdqa  xmmword ptr [rbp+3Fh+var_50.Data1], xmm0
0x18003bcf2  lea     rax, [rbp+3Fh+arg_48]
0x18003bcf9  mov     [rsp+0C0h+var_70], rax; unsigned int *
0x18003bcfe  mov     [rsp+0C0h+var_78], rsi; unsigned int *
0x18003bd03  mov     [rsp+0C0h+var_80], rdx; unsigned int *
0x18003bd08  mov     [rsp+0C0h+var_88], rcx; unsigned int *
0x18003bd0d  mov     [rsp+0C0h+var_A0], 186A0h; unsigned __int64
0x18003bd16  lea     r9, [rbp+3Fh+var_50]; struct _GUID
0x18003bd1a  movzx   r8d, word ptr [r14+0Ch]; unsigned __int16
0x18003bd1f  mov     edx, [r14+8]; unsigned int
0x18003bd23  mov     rcx, r13; struct PacketSizeConstraints *
0x18003bd26  call    ?GetPacketSizesFromConstraints@@YAJPEBUPacketSizeConstraints@@KGU_GUID@@_K22PEAI333@Z; GetPacketSizesFromConstraints(PacketSizeConstraints const *,ulong,ushort,_GUID,unsigned __int64,unsigned __int64,unsigned __int64,uint *,uint *,uint *,uint *)
0x18003bd2b  mov     edi, eax
0x18003bd2d  test    eax, eax
0x18003bd2f  js      loc_18003BC02
0x18003bd35  cmp     [rbp+3Fh+arg_8], 1
0x18003bd39  jnz     short loc_18003BD50
0x18003bd3b  cmp     [r13+0], r12b
0x18003bd3f  jz      short loc_18003BD50
0x18003bd41  mov     eax, dword ptr [rbp+3Fh+arg_48]
0x18003bd47  mov     r13, [rbp+3Fh+arg_40]
0x18003bd4e  jmp     short loc_18003BD5B
0x18003bd50  mov     r13, [rbp+3Fh+arg_40]
0x18003bd57  mov     eax, [r13+0]
0x18003bd5b  mov     rdi, [rbp+3Fh+arg_58]
0x18003bd62  mov     [rdi], eax
0x18003bd64  jmp     loc_18003BB93
0x18003bd69  test    byte ptr [rbp+3Fh+arg_30], 1
0x18003bd6d  jz      loc_18003BB89
0x18003bd73  mov     dword ptr [rbp+3Fh+arg_50], 0
0x18003bd7d  movzx   r8d, word ptr [r14+0Ch]; unsigned int
0x18003bd82  lea     r9, [rbp+3Fh+arg_50]; unsigned int *
0x18003bd89  mov     edx, [r14+8]; unsigned int
0x18003bd8d  mov     ecx, 61A8h; unsigned __int64
0x18003bd92  call    ?HnsToBlocksRU@@YAJ_KKKPEAK@Z; HnsToBlocksRU(unsigned __int64,ulong,ulong,ulong *)
0x18003bd97  mov     r12d, eax
  ... truncated ...
```
