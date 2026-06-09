# DiscoverPeriodicityCharacteristicsForFormat(IMMDevice *,AUDIO_DIRECTION,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX const *,PacketSizeConstraints *,DPCF_OPTIONS,__int64,uint *,uint *,uint *,uint *,uint *)

- ea: `0x18003ba20`
- end: `0x18003c080`
- name: `?DiscoverPeriodicityCharacteristicsForFormat@@YAJPEAUIMMDevice@@W4AUDIO_DIRECTION@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEBUtWAVEFORMATEX@@PEAUPacketSizeConstraints@@W4DPCF_OPTIONS@@_JPEAI8888@Z`
- size: `1632`
- prototype: `__int64(__int64, unsigned int, int, struct _GUID *, ...)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003b140`
- `0x18006b398`
- `0x180145ad0`

## callees

- `0x18001280c`
- `0x18003ba20`
- `0x18003c090`
- `0x18006e898`
- `0x1800ce75c`
- `0x180160250`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003bb01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003bb01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bb98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bba8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bcf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bd1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bd45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bd55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bd7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bd8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bdb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bdc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bb98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bba8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bcf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bd1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bd45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bd55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bd7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bd8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bdb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bdc7`
- `MMDevAPI!__imp_GetClassFromEndpointId` at `0x18003badc`
- `MMDevAPI!__imp_GetClassFromEndpointId` at `0x18003badc`
- `MMDevAPI!__imp_GetSessionIdFromEndpointId` at `0x18003bb25`
- `MMDevAPI!__imp_GetSessionIdFromEndpointId` at `0x18003bb25`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
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
0x18003ba20  mov     [rsp-8+arg_18], r9
0x18003ba25  mov     [rsp-8+arg_10], r8d
0x18003ba2a  mov     [rsp-8+arg_8], edx
0x18003ba2e  push    rbp
0x18003ba2f  push    rbx
0x18003ba30  push    rsi
0x18003ba31  push    rdi
0x18003ba32  push    r12
0x18003ba34  push    r13
0x18003ba36  push    r14
0x18003ba38  push    r15
0x18003ba3a  lea     rbp, [rsp-7]
0x18003ba3f  sub     rsp, 88h
0x18003ba46  mov     r15, rcx
0x18003ba49  mov     esi, 186A0h
0x18003ba4e  mov     r12, [rbp+3Fh+arg_38]
0x18003ba55  test    r12, r12
0x18003ba58  cmovnz  rsi, r12
0x18003ba5c  mov     r14, [rbp+3Fh+Src]
0x18003ba60  xorps   xmm1, xmm1
0x18003ba63  cvtsi2sd xmm1, rsi
0x18003ba68  mov     eax, [r14+4]
0x18003ba6c  xorps   xmm0, xmm0
0x18003ba6f  cvtsi2sd xmm0, rax
0x18003ba74  mulsd   xmm1, xmm0
0x18003ba78  divsd   xmm1, cs:__real@416312d000000000
0x18003ba80  addsd   xmm1, cs:__real@3fe0000000000000
0x18003ba88  cvttsd2si rax, xmm1
0x18003ba8d  mov     rdi, [rbp+3Fh+arg_58]
0x18003ba94  mov     [rdi], eax
0x18003ba96  mov     rcx, [rbp+3Fh+arg_50]
0x18003ba9d  mov     [rcx], eax
0x18003ba9f  mov     rcx, [rbp+3Fh+arg_48]
0x18003baa6  mov     [rcx], eax
0x18003baa8  mov     r13, [rbp+3Fh+arg_40]
0x18003baaf  mov     [r13+0], eax
0x18003bab3  mov     [rbp+3Fh+pv], 0
0x18003babb  mov     rax, [r15]
0x18003babe  lea     rdx, [rbp+3Fh+pv]
0x18003bac2  mov     rcx, r15
0x18003bac5  mov     rax, [rax+28h]
0x18003bac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bace  mov     ebx, eax
0x18003bad0  test    eax, eax
0x18003bad2  js      loc_18003BBF9
0x18003bad8  mov     rcx, [rbp+3Fh+pv]
0x18003badc  call    cs:__imp_GetClassFromEndpointId
0x18003bae2  test    eax, eax
0x18003bae4  jnz     loc_18003BCFC
0x18003baea  mov     r13, [rbp+3Fh+arg_28]
0x18003baee  test    r13, r13
0x18003baf1  jnz     loc_18003BC25
0x18003baf7  movzx   edi, word ptr [r14+10h]
0x18003bafc  add     edi, 40h ; '@'
0x18003baff  mov     ecx, edi; cb
0x18003bb01  call    cs:__imp_CoTaskMemAlloc
0x18003bb07  mov     rbx, rax
0x18003bb0a  mov     [rbp+3Fh+arg_0], rax
0x18003bb0e  test    rax, rax
0x18003bb11  jz      loc_18003BBC7
0x18003bb17  movzx   ecx, word ptr [r14+10h]
0x18003bb1c  add     ecx, 40h ; '@'
0x18003bb1f  mov     [rax], ecx
0x18003bb21  mov     rcx, [rbp+3Fh+pv]
0x18003bb25  call    cs:__imp_GetSessionIdFromEndpointId
0x18003bb2b  mov     [rbx+4], eax
0x18003bb2e  mov     eax, [rbp+3Fh+arg_10]
0x18003bb31  mov     [rbx+8], eax
0x18003bb34  mov     rax, [rbp+3Fh+arg_18]
0x18003bb38  movaps  xmm0, xmmword ptr [rax]
0x18003bb3b  movups  xmmword ptr [rbx+0Ch], xmm0
0x18003bb3f  movzx   r8d, word ptr [r14+10h]
0x18003bb44  add     r8, 12h; Size
0x18003bb48  lea     rcx, [rbx+2Ch]; void *
0x18003bb4c  mov     rdx, r14; Src
0x18003bb4f  call    memcpy_0
0x18003bb54  mov     dword ptr [rbp+3Fh+arg_38], 0
0x18003bb5e  lea     rax, [rbp+3Fh+arg_38]
0x18003bb65  mov     [rsp+0C0h+var_98], rax; unsigned __int64
0x18003bb6a  mov     [rsp+0C0h+var_A0], rsi; int
0x18003bb6f  mov     r9d, edi
0x18003bb72  mov     r8, rbx
0x18003bb75  mov     edx, [rbp+3Fh+arg_8]
0x18003bb78  mov     rcx, r15
0x18003bb7b  call    ?CheckConnectorSupportForPeriodicity@@YAJPEAUIMMDevice@@W4AUDIO_DIRECTION@@PEAUAUDIO_ENDPOINT_SHARED_CREATE_PARAMS_FOR_KS_ENDPOINTS@@I_JPEAI@Z; CheckConnectorSupportForPeriodicity(IMMDevice *,AUDIO_DIRECTION,AUDIO_ENDPOINT_SHARED_CREATE_PARAMS_FOR_KS_ENDPOINTS *,uint,__int64,uint *)
0x18003bb80  mov     esi, eax
0x18003bb82  test    eax, eax
0x18003bb84  jns     loc_18003BCB5
0x18003bb8a  cmp     eax, 887C0034h
0x18003bb8f  jnz     loc_18003BD29
0x18003bb95  mov     rcx, rbx; pv
0x18003bb98  call    cs:__imp_CoTaskMemFree
0x18003bb9e  nop
0x18003bb9f  mov     rcx, [rbp+3Fh+pv]; pv
0x18003bba3  test    rcx, rcx
0x18003bba6  jz      short loc_18003BBAE
0x18003bba8  call    cs:__imp_CoTaskMemFree
0x18003bbae  mov     eax, 887C0034h
0x18003bbb3  add     rsp, 88h
0x18003bbba  pop     r15
0x18003bbbc  pop     r14
0x18003bbbe  pop     r13
0x18003bbc0  pop     r12
0x18003bbc2  pop     rdi
0x18003bbc3  pop     rsi
0x18003bbc4  pop     rbx
0x18003bbc5  pop     rbp
0x18003bbc6  retn
0x18003bbc7  mov     rcx, [rbp+47h]; this
0x18003bbcb  mov     r9d, 8007000Eh; char *
0x18003bbd1  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x18003bbd8  mov     edx, 25Ah; void *
0x18003bbdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bbe2  nop
0x18003bbe3  mov     rcx, [rbp+3Fh+pv]; pv
0x18003bbe7  test    rcx, rcx
0x18003bbea  jz      short loc_18003BBF2
0x18003bbec  call    cs:__imp_CoTaskMemFree
0x18003bbf2  mov     eax, 8007000Eh
0x18003bbf7  jmp     short loc_18003BBB3
0x18003bbf9  mov     edx, 227h; void *
0x18003bbfe  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x18003bc05  mov     r9d, ebx; char *
0x18003bc08  mov     rcx, [rbp+47h]; this
0x18003bc0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bc11  nop
0x18003bc12  mov     rcx, [rbp+3Fh+pv]; pv
0x18003bc16  test    rcx, rcx
0x18003bc19  jz      short loc_18003BC21
0x18003bc1b  call    cs:__imp_CoTaskMemFree
0x18003bc21  mov     eax, ebx
0x18003bc23  jmp     short loc_18003BBB3
0x18003bc25  test    byte ptr [rbp+3Fh+arg_30], 2
0x18003bc29  jz      loc_18003BAF7
0x18003bc2f  mov     dword ptr [rbp+3Fh+arg_58], 0
0x18003bc39  mov     dword ptr [rbp+3Fh+arg_38], 0
0x18003bc43  mov     dword ptr [rbp+3Fh+Src], 0
0x18003bc4a  mov     dword ptr [rbp+3Fh+arg_0], 0
0x18003bc51  mov     rax, [rbp+3Fh+arg_18]
0x18003bc55  movaps  xmm0, xmmword ptr [rax]
0x18003bc58  movdqa  xmmword ptr [rbp+3Fh+var_50.Data1], xmm0
0x18003bc5d  lea     rax, [rbp+3Fh+arg_0]
0x18003bc61  mov     [rsp+0C0h+var_70], rax; unsigned int *
0x18003bc66  lea     rax, [rbp+3Fh+Src]
0x18003bc6a  mov     [rsp+0C0h+var_78], rax; unsigned int *
0x18003bc6f  lea     rax, [rbp+3Fh+arg_38]
0x18003bc76  mov     [rsp+0C0h+var_80], rax; unsigned int *
0x18003bc7b  lea     rax, [rbp+3Fh+arg_58]
0x18003bc82  mov     [rsp+0C0h+var_88], rax; unsigned int *
0x18003bc87  mov     [rsp+0C0h+var_A0], rsi; unsigned __int64
0x18003bc8c  lea     r9, [rbp+3Fh+var_50]; struct _GUID
0x18003bc90  movzx   r8d, word ptr [r14+0Ch]; unsigned __int16
0x18003bc95  mov     edx, [r14+8]; unsigned int
0x18003bc99  mov     rcx, r13; struct PacketSizeConstraints *
0x18003bc9c  call    ?GetPacketSizesFromConstraints@@YAJPEBUPacketSizeConstraints@@KGU_GUID@@_K22PEAI333@Z; GetPacketSizesFromConstraints(PacketSizeConstraints const *,ulong,ushort,_GUID,unsigned __int64,unsigned __int64,unsigned __int64,uint *,uint *,uint *,uint *)
0x18003bca1  mov     ebx, eax
0x18003bca3  test    eax, eax
0x18003bca5  jns     loc_18003BDD5
0x18003bcab  mov     edx, 23Ch
0x18003bcb0  jmp     loc_18003BBFE
0x18003bcb5  mov     eax, dword ptr [rbp+3Fh+arg_38]
0x18003bcbb  mov     rcx, [rbp+3Fh+arg_58]
0x18003bcc2  mov     [rcx], eax
0x18003bcc4  mov     rsi, [rbp+3Fh+arg_50]
0x18003bccb  mov     [rsi], eax
0x18003bccd  mov     rdx, [rbp+3Fh+arg_48]
0x18003bcd4  mov     [rdx], eax
0x18003bcd6  mov     rcx, [rbp+3Fh+arg_40]
0x18003bcdd  mov     [rcx], eax
0x18003bcdf  cmp     [rbp+3Fh+arg_10], 0
0x18003bce3  jz      loc_18003BE2D
0x18003bce9  mov     r13, rcx
0x18003bcec  mov     rdi, [rbp+3Fh+arg_58]
0x18003bcf3  mov     rcx, rbx; pv
0x18003bcf6  call    cs:__imp_CoTaskMemFree
0x18003bcfc  mov     ecx, [rdi]
0x18003bcfe  mov     rax, [rbp+3Fh+arg_60]
0x18003bd05  mov     [rax], ecx
0x18003bd07  mov     eax, [r13+0]
0x18003bd0b  cmp     [rdi], eax
0x18003bd0d  ja      loc_18003C078
0x18003bd13  mov     rcx, [rbp+3Fh+pv]; pv
0x18003bd17  test    rcx, rcx
0x18003bd1a  jz      short loc_18003BD22
0x18003bd1c  call    cs:__imp_CoTaskMemFree
0x18003bd22  xor     eax, eax
0x18003bd24  jmp     loc_18003BBB3
0x18003bd29  mov     rcx, [rbp+47h]; this
0x18003bd2d  mov     r9d, esi; char *
0x18003bd30  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x18003bd37  mov     edx, 267h; void *
0x18003bd3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bd41  nop
0x18003bd42  mov     rcx, rbx; pv
0x18003bd45  call    cs:__imp_CoTaskMemFree
0x18003bd4b  nop
0x18003bd4c  mov     rcx, [rbp+3Fh+pv]; pv
0x18003bd50  test    rcx, rcx
0x18003bd53  jz      short loc_18003BD5B
0x18003bd55  call    cs:__imp_CoTaskMemFree
0x18003bd5b  mov     eax, esi
0x18003bd5d  jmp     loc_18003BBB3
0x18003bd62  mov     rcx, [rbp+47h]; this
0x18003bd66  mov     r9d, edi; char *
0x18003bd69  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x18003bd70  mov     edx, 282h; void *
0x18003bd75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bd7a  nop
0x18003bd7b  mov     rcx, rbx; pv
0x18003bd7e  call    cs:__imp_CoTaskMemFree
0x18003bd84  nop
0x18003bd85  mov     rcx, [rbp+3Fh+pv]; pv
0x18003bd89  test    rcx, rcx
0x18003bd8c  jz      short loc_18003BD94
0x18003bd8e  call    cs:__imp_CoTaskMemFree
0x18003bd94  mov     eax, edi
0x18003bd96  jmp     loc_18003BBB3
0x18003bd9b  mov     rcx, [rbp+47h]; this
0x18003bd9f  mov     r9d, r12d; char *
0x18003bda2  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x18003bda9  mov     edx, 293h; void *
0x18003bdae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bdb3  nop
0x18003bdb4  mov     rcx, rbx; pv
0x18003bdb7  call    cs:__imp_CoTaskMemFree
0x18003bdbd  nop
0x18003bdbe  mov     rcx, [rbp+3Fh+pv]; pv
0x18003bdc2  test    rcx, rcx
0x18003bdc5  jz      short loc_18003BDCD
0x18003bdc7  call    cs:__imp_CoTaskMemFree
0x18003bdcd  mov     eax, r12d
0x18003bdd0  jmp     loc_18003BBB3
0x18003bdd5  mov     eax, dword ptr [rbp+3Fh+arg_58]
0x18003bddb  mov     [rdi], eax
0x18003bddd  mov     rdx, [rbp+3Fh+arg_50]
0x18003bde4  mov     [rdx], eax
0x18003bde6  mov     r8, [rbp+3Fh+arg_48]
0x18003bded  mov     [r8], eax
0x18003bdf0  mov     rcx, [rbp+3Fh+arg_40]
0x18003bdf7  mov     [rcx], eax
0x18003bdf9  cmp     [rbp+3Fh+arg_10], 0
0x18003bdfd  jnz     short loc_18003BE25
0x18003bdff  test    r12, r12
0x18003be02  jnz     short loc_18003BE25
0x18003be04  mov     eax, dword ptr [rbp+3Fh+arg_38]
0x18003be0a  mov     [r8], eax
0x18003be0d  mov     eax, dword ptr [rbp+3Fh+Src]
0x18003be10  mov     [rdx], eax
0x18003be12  cmp     [rbp+3Fh+arg_8], 1
0x18003be16  jnz     short loc_18003BE21
0x18003be18  cmp     [r13+0], r12b
0x18003be1c  mov     eax, dword ptr [rbp+3Fh+arg_0]
0x18003be1f  jnz     short loc_18003BE23
0x18003be21  mov     eax, [rcx]
0x18003be23  mov     [rdi], eax
0x18003be25  mov     r13, rcx
0x18003be28  jmp     loc_18003BCFC
0x18003be2d  test    r12, r12
0x18003be30  jnz     loc_18003BCE9
0x18003be36  test    r13, r13
0x18003be39  jz      loc_18003BEC9
0x18003be3f  mov     dword ptr [rbp+3Fh+arg_48], r12d
0x18003be46  mov     rax, [rbp+3Fh+arg_18]
0x18003be4a  movaps  xmm0, xmmword ptr [rax]
0x18003be4d  movdqa  xmmword ptr [rbp+3Fh+var_50.Data1], xmm0
0x18003be52  lea     rax, [rbp+3Fh+arg_48]
0x18003be59  mov     [rsp+0C0h+var_70], rax; unsigned int *
0x18003be5e  mov     [rsp+0C0h+var_78], rsi; unsigned int *
0x18003be63  mov     [rsp+0C0h+var_80], rdx; unsigned int *
0x18003be68  mov     [rsp+0C0h+var_88], rcx; unsigned int *
0x18003be6d  mov     [rsp+0C0h+var_A0], 186A0h; unsigned __int64
0x18003be76  lea     r9, [rbp+3Fh+var_50]; struct _GUID
0x18003be7a  movzx   r8d, word ptr [r14+0Ch]; unsigned __int16
0x18003be7f  mov     edx, [r14+8]; unsigned int
0x18003be83  mov     rcx, r13; struct PacketSizeConstraints *
0x18003be86  call    ?GetPacketSizesFromConstraints@@YAJPEBUPacketSizeConstraints@@KGU_GUID@@_K22PEAI333@Z; GetPacketSizesFromConstraints(PacketSizeConstraints const *,ulong,ushort,_GUID,unsigned __int64,unsigned __int64,unsigned __int64,uint *,uint *,uint *,uint *)
0x18003be8b  mov     edi, eax
0x18003be8d  test    eax, eax
0x18003be8f  js      loc_18003BD62
0x18003be95  cmp     [rbp+3Fh+arg_8], 1
0x18003be99  jnz     short loc_18003BEB0
0x18003be9b  cmp     [r13+0], r12b
0x18003be9f  jz      short loc_18003BEB0
0x18003bea1  mov     eax, dword ptr [rbp+3Fh+arg_48]
0x18003bea7  mov     r13, [rbp+3Fh+arg_40]
0x18003beae  jmp     short loc_18003BEBB
0x18003beb0  mov     r13, [rbp+3Fh+arg_40]
0x18003beb7  mov     eax, [r13+0]
0x18003bebb  mov     rdi, [rbp+3Fh+arg_58]
0x18003bec2  mov     [rdi], eax
0x18003bec4  jmp     loc_18003BCF3
0x18003bec9  test    byte ptr [rbp+3Fh+arg_30], 1
0x18003becd  jz      loc_18003BCE9
0x18003bed3  mov     dword ptr [rbp+3Fh+arg_50], 0
0x18003bedd  movzx   r8d, word ptr [r14+0Ch]; unsigned int
0x18003bee2  lea     r9, [rbp+3Fh+arg_50]; unsigned int *
0x18003bee9  mov     edx, [r14+8]; unsigned int
0x18003beed  mov     ecx, 61A8h; unsigned __int64
0x18003bef2  call    ?HnsToBlocksRU@@YAJ_KKKPEAK@Z; HnsToBlocksRU(unsigned __int64,ulong,ulong,ulong *)
0x18003bef7  mov     r12d, eax
  ... truncated ...
```
