# I_ReaderListReadRootCertsFromCard

- ea: `0x180019d6c`
- end: `0x18001a258`
- name: `I_ReaderListReadRootCertsFromCard`
- size: `1260`
- prototype: `__int64 __fastcall(int *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180016d74`

## callees

- `0x180001178`
- `0x1800011e4`
- `0x180007178`
- `0x1800071d4`
- `0x180013910`
- `0x180013ca8`
- `0x180019d6c`
- `0x18001cc6c`
- `0x18001e020`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019e06`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019e16`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001a1e8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019e06`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019e16`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001a1e8`

## pseudocode

```c
__int64 __fastcall I_ReaderListReadRootCertsFromCard(int *a1, __int64 a2)
{
  unsigned int v3; // edi
  __int64 v5; // rcx
  __int64 v6; // rcx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int64 *v10; // rdx
  __int64 *v11; // r9
  int v12; // eax
  __int64 *v13; // rdx
  __int64 *v14; // r9
  __int64 *v15; // rdx
  __int64 *v16; // r9
  __int64 *v17; // rdx
  __int64 *v18; // r9
  __int64 *v19; // rdx
  __int64 *v20; // r9
  __int64 *v21; // rdx
  __int64 *v22; // r9
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  __int64 v26; // rcx
  int v28; // [rsp+30h] [rbp-D0h] BYREF
  int v29; // [rsp+34h] [rbp-CCh] BYREF
  int v30; // [rsp+38h] [rbp-C8h] BYREF
  int v31; // [rsp+3Ch] [rbp-C4h] BYREF
  int v32; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+44h] [rbp-BCh] BYREF
  int v34; // [rsp+48h] [rbp-B8h] BYREF
  int v35; // [rsp+4Ch] [rbp-B4h] BYREF
  int v36; // [rsp+50h] [rbp-B0h] BYREF
  int v37; // [rsp+54h] [rbp-ACh] BYREF
  int v38; // [rsp+58h] [rbp-A8h] BYREF
  int v39; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v40; // [rsp+60h] [rbp-A0h] BYREF
  GUID ActivityId; // [rsp+68h] [rbp-98h] BYREF
  GUID v42; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v43; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v44[16]; // [rsp+B0h] [rbp-50h] BYREF
  int *v45; // [rsp+C0h] [rbp-40h]
  __int64 v46; // [rsp+C8h] [rbp-38h]
  _BYTE v47[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v48[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v49[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v50[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v51[16]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v52[16]; // [rsp+120h] [rbp+20h] BYREF
  int *v53; // [rsp+130h] [rbp+30h]
  __int64 v54; // [rsp+138h] [rbp+38h]
  int *v55; // [rsp+140h] [rbp+40h]
  __int64 v56; // [rsp+148h] [rbp+48h]
  int *v57; // [rsp+150h] [rbp+50h]
  __int64 v58; // [rsp+158h] [rbp+58h]
  int *v59; // [rsp+160h] [rbp+60h]
  __int64 v60; // [rsp+168h] [rbp+68h]
  int *v61; // [rsp+170h] [rbp+70h]
  __int64 v62; // [rsp+178h] [rbp+78h]
  int *v63; // [rsp+180h] [rbp+80h]
  __int64 v64; // [rsp+188h] [rbp+88h]
  int *v65; // [rsp+190h] [rbp+90h]
  __int64 v66; // [rsp+198h] [rbp+98h]
  int *v67; // [rsp+1A0h] [rbp+A0h]
  __int64 v68; // [rsp+1A8h] [rbp+A8h]
  int *v69; // [rsp+1B0h] [rbp+B0h]
  __int64 v70; // [rsp+1B8h] [rbp+B8h]
  int *v71; // [rsp+1C0h] [rbp+C0h]
  __int64 v72; // [rsp+1C8h] [rbp+C8h]
  int *v73; // [rsp+1D0h] [rbp+D0h]
  __int64 v74; // [rsp+1D8h] [rbp+D8h]
  int *v75; // [rsp+1E0h] [rbp+E0h]
  __int64 v76; // [rsp+1E8h] [rbp+E8h]
  struct _EVENT_DATA_DESCRIPTOR v77; // [rsp+1F0h] [rbp+F0h] BYREF

  v28 = 0;
  v3 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  ActivityId = 0;
  v42 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v42);
  if ( (unsigned int)dword_18002B008 > 5 )
    tlgWriteTransfer_EventWriteTransfer(v5, (unsigned __int8 *)&byte_180025127, &v42, &ActivityId, 2u, &v77);
  v6 = (unsigned int)(a1[6] - 1);
  if ( a1[6] != 1 )
  {
    if ( a1[6] != 2 )
      goto LABEL_28;
    if ( *(_QWORD *)(a2 + 88) )
    {
      v9 = I_CollectRootCertsUsingCng(a2, &v28);
LABEL_23:
      v3 = v9;
      *(GUID *)(a2 + 200) = ActivityId;
      *(_DWORD *)(a2 + 156) = 0;
      if ( v9 )
      {
        WppTraceIndent(0, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            178,
            (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent,
            v3);
        }
      }
      goto LABEL_28;
    }
    if ( !*(_QWORD *)(a2 + 80) )
    {
      WppTraceIndent(v6, 2);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v8 = 177;
LABEL_15:
        WPP_SF_s(v7[2], v8, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
        goto LABEL_28;
      }
      goto LABEL_28;
    }
LABEL_22:
    v9 = I_CollectRootCertsUsingCapi(a2, &v28);
    goto LABEL_23;
  }
  if ( *(_QWORD *)(a2 + 80) )
    goto LABEL_22;
  WppTraceIndent(v6, 2);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v8 = 176;
    goto LABEL_15;
  }
LABEL_28:
  if ( (unsigned int)dword_18002B008 > 5 )
  {
    if ( a2 )
      v10 = *(__int64 **)a2;
    else
      v10 = &qword_180024730;
    tlgCreate1Sz_wchar_t((__int64)v44, v10);
    if ( a2 )
      v12 = *(_DWORD *)(a2 + 8);
    else
      v12 = 0;
    v28 = v12;
    v45 = &v28;
    v46 = 4;
    if ( a2 )
      v13 = *(__int64 **)(a2 + 16);
    else
      v13 = v11;
    tlgCreate1Sz_wchar_t((__int64)v47, v13);
    if ( a2 )
      v15 = *(__int64 **)(a2 + 80);
    else
      v15 = v14;
    tlgCreate1Sz_wchar_t((__int64)v48, v15);
    if ( a2 )
      v17 = *(__int64 **)(a2 + 88);
    else
      v17 = v16;
    tlgCreate1Sz_wchar_t((__int64)v49, v17);
    if ( a2 )
      v19 = *(__int64 **)(a2 + 96);
    else
      v19 = v18;
    tlgCreate1Sz_wchar_t((__int64)v50, v19);
    if ( a2 )
      v21 = *(__int64 **)(a2 + 104);
    else
      v21 = v20;
    tlgCreate1Sz_wchar_t((__int64)v51, v21);
    if ( a2 )
      v22 = *(__int64 **)(a2 + 112);
    tlgCreate1Sz_wchar_t((__int64)v52, v22);
    if ( a2 )
      v24 = *(_DWORD *)(a2 + 120);
    else
      v24 = 0;
    v29 = v24;
    v53 = &v29;
    v54 = 4;
    if ( a2 )
      v25 = *(_DWORD *)(a2 + 160);
    else
      v25 = 0;
    v30 = v25;
    v56 = 4;
    v55 = &v30;
    v31 = a1[64];
    v57 = &v31;
    v32 = *a1;
    v59 = &v32;
    v33 = a1[1];
    v61 = &v33;
    v34 = a1[2];
    v63 = &v34;
    v35 = a1[3];
    v65 = &v35;
    v36 = a1[4];
    v67 = &v36;
    v37 = a1[5];
    v69 = &v37;
    v38 = a1[10];
    v71 = &v38;
    v39 = a1[6];
    v73 = &v39;
    v75 = (int *)&v40;
    v58 = 4;
    v60 = 4;
    v62 = 4;
    v64 = 4;
    v66 = 4;
    v68 = 4;
    v70 = 4;
    v72 = 4;
    v74 = 4;
    v40 = v3;
    v76 = 4;
    tlgWriteTransfer_EventWriteTransfer(v23, (unsigned __int8 *)byte_1800257CF, &v42, &ActivityId, 0x16u, &v43);
  }
  EventActivityIdControl(2u, &ActivityId);
  WppTraceIndent(v26, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      179,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180019d6c  push    rbp
0x180019d6e  push    rbx
0x180019d6f  push    rsi
0x180019d70  push    rdi
0x180019d71  push    r14
0x180019d73  push    r15
0x180019d75  lea     rbp, [rsp-128h]
0x180019d7d  sub     rsp, 228h
0x180019d84  mov     rax, cs:__security_cookie
0x180019d8b  xor     rax, rsp
0x180019d8e  mov     [rbp+150h+var_40], rax
0x180019d95  xor     r14d, r14d
0x180019d98  mov     rbx, rdx
0x180019d9b  xor     edx, edx
0x180019d9d  mov     [rsp+250h+var_220], r14d
0x180019da2  mov     edi, r14d
0x180019da5  mov     rsi, rcx
0x180019da8  call    WppTraceIndent
0x180019dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180019db4  lea     rax, WPP_GLOBAL_Control
0x180019dbb  lea     r15d, [r14+2]
0x180019dbf  cmp     rcx, rax
0x180019dc2  jz      short loc_180019DEC
0x180019dc4  test    [rcx+1Ch], r15b
0x180019dc8  jz      short loc_180019DEC
0x180019dca  cmp     byte ptr [rcx+19h], 5
0x180019dce  jb      short loc_180019DEC
0x180019dd0  mov     r9, cs:WPP_pszIndent
0x180019dd7  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180019dde  mov     rcx, [rcx+10h]
0x180019de2  mov     edx, 0AFh
0x180019de7  call    WPP_SF_s
0x180019dec  xorps   xmm0, xmm0
0x180019def  lea     rdx, [rsp+250h+ActivityId]; ActivityId
0x180019df4  xorps   xmm1, xmm1
0x180019df7  mov     ecx, 5; ControlCode
0x180019dfc  movups  xmmword ptr [rsp+250h+ActivityId.Data1], xmm0
0x180019e01  movups  xmmword ptr [rsp+250h+var_1D8.Data1], xmm1
0x180019e06  call    cs:__imp_EventActivityIdControl
0x180019e0c  lea     rdx, [rsp+250h+var_1D8]; ActivityId
0x180019e11  mov     ecx, 1; ControlCode
0x180019e16  call    cs:__imp_EventActivityIdControl
0x180019e1c  mov     eax, cs:dword_18002B008
0x180019e22  cmp     eax, 5
0x180019e25  jbe     short loc_180019E4E
0x180019e27  lea     rax, [rbp+150h+var_60]
0x180019e2e  mov     [rsp+250h+var_228], rax
0x180019e33  lea     r9, [rsp+250h+ActivityId]
0x180019e38  lea     r8, [rsp+250h+var_1D8]
0x180019e3d  mov     [rsp+250h+var_230], r15d
0x180019e42  lea     rdx, byte_180025127
0x180019e49  call    _tlgWriteTransfer_EventWriteTransfer
0x180019e4e  mov     ecx, [rsi+18h]
0x180019e51  sub     ecx, 1
0x180019e54  jz      short loc_180019ED2
0x180019e56  cmp     ecx, 1
0x180019e59  jnz     loc_180019F83
0x180019e5f  cmp     [rbx+58h], r14
0x180019e63  jnz     short loc_180019EC3
0x180019e65  cmp     [rbx+50h], r14
0x180019e69  jnz     loc_180019F0E
0x180019e6f  mov     edx, r15d
0x180019e72  call    WppTraceIndent
0x180019e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e7e  lea     rax, WPP_GLOBAL_Control
0x180019e85  cmp     rcx, rax
0x180019e88  jz      loc_180019F83
0x180019e8e  test    byte ptr [rcx+1Ch], 1
0x180019e92  jz      loc_180019F83
0x180019e98  cmp     byte ptr [rcx+19h], 3
0x180019e9c  jb      loc_180019F83
0x180019ea2  mov     edx, 0B1h
0x180019ea7  mov     r9, cs:WPP_pszIndent
0x180019eae  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180019eb5  mov     rcx, [rcx+10h]
0x180019eb9  call    WPP_SF_s
0x180019ebe  jmp     loc_180019F83
0x180019ec3  lea     rdx, [rsp+250h+var_220]
0x180019ec8  mov     rcx, rbx
0x180019ecb  call    I_CollectRootCertsUsingCng
0x180019ed0  jmp     short loc_180019F1B
0x180019ed2  cmp     [rbx+50h], r14
0x180019ed6  jnz     short loc_180019F0E
0x180019ed8  mov     edx, r15d
0x180019edb  call    WppTraceIndent
0x180019ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ee7  lea     rax, WPP_GLOBAL_Control
0x180019eee  cmp     rcx, rax
0x180019ef1  jz      loc_180019F83
0x180019ef7  test    byte ptr [rcx+1Ch], 1
0x180019efb  jz      loc_180019F83
0x180019f01  cmp     byte ptr [rcx+19h], 3
0x180019f05  jb      short loc_180019F83
0x180019f07  mov     edx, 0B0h
0x180019f0c  jmp     short loc_180019EA7
0x180019f0e  lea     rdx, [rsp+250h+var_220]
0x180019f13  mov     rcx, rbx
0x180019f16  call    I_CollectRootCertsUsingCapi
0x180019f1b  movups  xmm0, xmmword ptr [rsp+250h+ActivityId.Data1]
0x180019f20  mov     edi, eax
0x180019f22  mov     ecx, r14d
0x180019f25  mov     eax, 9Ch
0x180019f2a  mov     rdx, rbx
0x180019f2d  movdqu  xmmword ptr [rbx+0C8h], xmm0
0x180019f35  mov     [rbx+rax], ecx
0x180019f38  test    edi, edi
0x180019f3a  jz      short loc_180019F83
0x180019f3c  mov     edx, r15d
0x180019f3f  call    WppTraceIndent
0x180019f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f4b  lea     rax, WPP_GLOBAL_Control
0x180019f52  cmp     rcx, rax
0x180019f55  jz      short loc_180019F83
0x180019f57  test    byte ptr [rcx+1Ch], 1
0x180019f5b  jz      short loc_180019F83
0x180019f5d  cmp     byte ptr [rcx+19h], 3
0x180019f61  jb      short loc_180019F83
0x180019f63  mov     r9, cs:WPP_pszIndent
0x180019f6a  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180019f71  mov     rcx, [rcx+10h]
0x180019f75  mov     edx, 0B2h
0x180019f7a  mov     [rsp+250h+var_230], edi
0x180019f7e  call    WPP_SF_sd
0x180019f83  mov     eax, cs:dword_18002B008
0x180019f89  cmp     eax, 5
0x180019f8c  jbe     loc_18001A1E0
0x180019f92  lea     r9, qword_180024730
0x180019f99  test    rbx, rbx
0x180019f9c  jz      short loc_180019FA3
0x180019f9e  mov     rdx, [rbx]
0x180019fa1  jmp     short loc_180019FA6
0x180019fa3  mov     rdx, r9
0x180019fa6  lea     rcx, [rbp+150h+var_1A0]
0x180019faa  call    _tlgCreate1Sz_wchar_t
0x180019faf  test    rbx, rbx
0x180019fb2  jz      short loc_180019FB9
0x180019fb4  mov     eax, [rbx+8]
0x180019fb7  jmp     short loc_180019FBC
0x180019fb9  mov     eax, r14d
0x180019fbc  mov     [rsp+250h+var_220], eax
0x180019fc0  lea     rax, [rsp+250h+var_220]
0x180019fc5  mov     [rbp+150h+var_190], rax
0x180019fc9  mov     [rbp+150h+var_188], 4
0x180019fd1  test    rbx, rbx
0x180019fd4  jz      short loc_180019FDC
0x180019fd6  mov     rdx, [rbx+10h]
0x180019fda  jmp     short loc_180019FDF
0x180019fdc  mov     rdx, r9
0x180019fdf  lea     rcx, [rbp+150h+var_180]
0x180019fe3  call    _tlgCreate1Sz_wchar_t
0x180019fe8  test    rbx, rbx
0x180019feb  jz      short loc_180019FF3
0x180019fed  mov     rdx, [rbx+50h]
0x180019ff1  jmp     short loc_180019FF6
0x180019ff3  mov     rdx, r9
0x180019ff6  lea     rcx, [rbp+150h+var_170]
0x180019ffa  call    _tlgCreate1Sz_wchar_t
0x180019fff  test    rbx, rbx
0x18001a002  jz      short loc_18001A00A
0x18001a004  mov     rdx, [rbx+58h]
0x18001a008  jmp     short loc_18001A00D
0x18001a00a  mov     rdx, r9
0x18001a00d  lea     rcx, [rbp+150h+var_160]
0x18001a011  call    _tlgCreate1Sz_wchar_t
0x18001a016  test    rbx, rbx
0x18001a019  jz      short loc_18001A021
0x18001a01b  mov     rdx, [rbx+60h]
0x18001a01f  jmp     short loc_18001A024
0x18001a021  mov     rdx, r9
0x18001a024  lea     rcx, [rbp+150h+var_150]
0x18001a028  call    _tlgCreate1Sz_wchar_t
0x18001a02d  test    rbx, rbx
0x18001a030  jz      short loc_18001A038
0x18001a032  mov     rdx, [rbx+68h]
0x18001a036  jmp     short loc_18001A03B
0x18001a038  mov     rdx, r9
0x18001a03b  lea     rcx, [rbp+150h+var_140]
0x18001a03f  call    _tlgCreate1Sz_wchar_t
0x18001a044  test    rbx, rbx
0x18001a047  jz      short loc_18001A04D
0x18001a049  mov     r9, [rbx+70h]
0x18001a04d  mov     rdx, r9
0x18001a050  lea     rcx, [rbp+150h+var_130]
0x18001a054  call    _tlgCreate1Sz_wchar_t
0x18001a059  test    rbx, rbx
0x18001a05c  jz      short loc_18001A063
0x18001a05e  mov     eax, [rbx+78h]
0x18001a061  jmp     short loc_18001A066
0x18001a063  mov     eax, r14d
0x18001a066  mov     [rsp+250h+var_21C], eax
0x18001a06a  lea     rax, [rsp+250h+var_21C]
0x18001a06f  mov     [rbp+150h+var_120], rax
0x18001a073  mov     [rbp+150h+var_118], 4
0x18001a07b  test    rbx, rbx
0x18001a07e  jz      short loc_18001A088
0x18001a080  mov     eax, [rbx+0A0h]
0x18001a086  jmp     short loc_18001A08B
0x18001a088  mov     eax, r14d
0x18001a08b  mov     [rsp+250h+var_218], eax
0x18001a08f  lea     r9, [rsp+250h+ActivityId]
0x18001a094  lea     rax, [rsp+250h+var_218]
0x18001a099  mov     [rbp+150h+var_108], 4
0x18001a0a1  mov     [rbp+150h+var_110], rax
0x18001a0a5  lea     r8, [rsp+250h+var_1D8]
0x18001a0aa  mov     eax, [rsi+100h]
0x18001a0b0  lea     rdx, byte_1800257CF
0x18001a0b7  mov     [rsp+250h+var_214], eax
0x18001a0bb  lea     rax, [rsp+250h+var_214]
0x18001a0c0  mov     [rbp+150h+var_100], rax
0x18001a0c4  mov     eax, [rsi]
0x18001a0c6  mov     [rsp+250h+var_210], eax
0x18001a0ca  lea     rax, [rsp+250h+var_210]
0x18001a0cf  mov     [rbp+150h+var_F0], rax
0x18001a0d3  mov     eax, [rsi+4]
0x18001a0d6  mov     [rsp+250h+var_20C], eax
0x18001a0da  lea     rax, [rsp+250h+var_20C]
0x18001a0df  mov     [rbp+150h+var_E0], rax
0x18001a0e3  mov     eax, [rsi+8]
0x18001a0e6  mov     [rsp+250h+var_208], eax
0x18001a0ea  lea     rax, [rsp+250h+var_208]
0x18001a0ef  mov     [rbp+150h+var_D0], rax
0x18001a0f6  mov     eax, [rsi+0Ch]
0x18001a0f9  mov     [rsp+250h+var_204], eax
0x18001a0fd  lea     rax, [rsp+250h+var_204]
0x18001a102  mov     [rbp+150h+var_C0], rax
0x18001a109  mov     eax, [rsi+10h]
0x18001a10c  mov     [rsp+250h+var_200], eax
0x18001a110  lea     rax, [rsp+250h+var_200]
0x18001a115  mov     [rbp+150h+var_B0], rax
0x18001a11c  mov     eax, [rsi+14h]
0x18001a11f  mov     [rsp+250h+var_1FC], eax
0x18001a123  lea     rax, [rsp+250h+var_1FC]
0x18001a128  mov     [rbp+150h+var_A0], rax
0x18001a12f  mov     eax, [rsi+28h]
0x18001a132  mov     [rsp+250h+var_1F8], eax
0x18001a136  lea     rax, [rsp+250h+var_1F8]
0x18001a13b  mov     [rbp+150h+var_90], rax
0x18001a142  mov     eax, [rsi+18h]
0x18001a145  mov     [rsp+250h+var_1F4], eax
0x18001a149  lea     rax, [rsp+250h+var_1F4]
0x18001a14e  mov     [rbp+150h+var_80], rax
0x18001a155  lea     rax, [rsp+250h+var_1F0]
0x18001a15a  mov     [rbp+150h+var_70], rax
0x18001a161  lea     rax, [rbp+150h+var_1C0]
0x18001a165  mov     [rsp+250h+var_228], rax
0x18001a16a  mov     [rsp+250h+var_230], 16h
0x18001a172  mov     [rbp+150h+var_F8], 4
0x18001a17a  mov     [rbp+150h+var_E8], 4
0x18001a182  mov     [rbp+150h+var_D8], 4
0x18001a18a  mov     [rbp+150h+var_C8], 4
0x18001a195  mov     [rbp+150h+var_B8], 4
0x18001a1a0  mov     [rbp+150h+var_A8], 4
0x18001a1ab  mov     [rbp+150h+var_98], 4
0x18001a1b6  mov     [rbp+150h+var_88], 4
0x18001a1c1  mov     [rbp+150h+var_78], 4
0x18001a1cc  mov     [rsp+250h+var_1F0], edi
0x18001a1d0  mov     [rbp+150h+var_68], 4
0x18001a1db  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a1e0  lea     rdx, [rsp+250h+ActivityId]; ActivityId
0x18001a1e5  mov     ecx, r15d; ControlCode
0x18001a1e8  call    cs:__imp_EventActivityIdControl
0x18001a1ee  mov     edx, 1
0x18001a1f3  call    WppTraceIndent
0x18001a1f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1ff  lea     rax, WPP_GLOBAL_Control
0x18001a206  cmp     rcx, rax
0x18001a209  jz      short loc_18001A237
0x18001a20b  test    [rcx+1Ch], r15b
0x18001a20f  jz      short loc_18001A237
0x18001a211  cmp     byte ptr [rcx+19h], 5
0x18001a215  jb      short loc_18001A237
0x18001a217  mov     r9, cs:WPP_pszIndent
0x18001a21e  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001a225  mov     rcx, [rcx+10h]
0x18001a229  mov     edx, 0B3h
0x18001a22e  mov     [rsp+250h+var_230], edi
0x18001a232  call    WPP_SF_sd
0x18001a237  mov     eax, edi
0x18001a239  mov     rcx, [rbp+150h+var_40]
0x18001a240  xor     rcx, rsp; StackCookie
0x18001a243  call    __security_check_cookie
0x18001a248  add     rsp, 228h
0x18001a24f  pop     r15
0x18001a251  pop     r14
0x18001a253  pop     rdi
0x18001a254  pop     rsi
0x18001a255  pop     rbx
0x18001a256  pop     rbp
0x18001a257  retn
```
