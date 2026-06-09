# IkeSendEmptyInformationalReqIkeV2

- ea: `0x18003fa20`
- end: `0x180040091`
- name: `IkeSendEmptyInformationalReqIkeV2`
- size: `1649`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18003bf34`

## callees

- `0x1800037c4`
- `0x180008388`
- `0x1800149d0`
- `0x180031484`
- `0x180031640`
- `0x180038230`
- `0x18003c468`
- `0x18003cfa0`
- `0x18003fa20`
- `0x18004890c`
- `0x180050850`
- `0x18005bc40`
- `0x1800cf350`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fac7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fb0e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fc9e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fd01`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fd48`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ff49`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ff90`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fac7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fb0e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fc9e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fd01`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fd48`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ff49`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ff90`
- `ntdll!EtwEventWriteTransfer` at `0x18003fbe2`
- `ntdll!EtwEventWriteTransfer` at `0x18003fe1c`
- `ntdll!EtwEventWriteTransfer` at `0x180040060`
- `ntdll!EtwEventWriteTransfer` at `0x18003fbe2`
- `ntdll!EtwEventWriteTransfer` at `0x18003fe1c`
- `ntdll!EtwEventWriteTransfer` at `0x180040060`

## pseudocode

```c
__int64 __fastcall IkeSendEmptyInformationalReqIkeV2(__int64 a1)
{
  __int64 v1; // r14
  __int64 v3; // rdi
  LPCRITICAL_SECTION v4; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v7; // rcx
  DWORD v8; // ecx
  char *v9; // rax
  const WCHAR *v10; // rdx
  __int64 v11; // rax
  bool v12; // zf
  int v13; // eax
  __int64 LockSemaphore_low; // rcx
  __int64 inited; // rbx
  __int64 v16; // r13
  _QWORD *v17; // rbx
  __int64 *v18; // rax
  __int64 v19; // rbx
  __int64 TlsPeerAddr; // rax
  LPCRITICAL_SECTION v21; // rax
  DWORD v22; // ecx
  __int64 *v23; // rax
  __int64 v24; // rcx
  DWORD v25; // ecx
  char *v26; // rax
  const WCHAR *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  LPCRITICAL_SECTION v30; // rax
  DWORD v31; // ecx
  __int64 *v32; // rax
  __int64 v33; // rcx
  DWORD v34; // ecx
  char *v35; // rax
  const WCHAR *v36; // rdx
  int v37; // edi
  __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v40; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v41; // [rsp+70h] [rbp-90h]
  __int64 v42; // [rsp+80h] [rbp-80h] BYREF
  int v43; // [rsp+88h] [rbp-78h] BYREF
  int v44; // [rsp+8Ch] [rbp-74h]
  __int64 v45; // [rsp+90h] [rbp-70h]
  char *v46; // [rsp+A0h] [rbp-60h] BYREF
  int v47; // [rsp+A8h] [rbp-58h]
  int v48; // [rsp+ACh] [rbp-54h]
  __int16 *v49; // [rsp+B0h] [rbp-50h]
  int v50; // [rsp+B8h] [rbp-48h]
  int v51; // [rsp+BCh] [rbp-44h]
  __int64 *v52; // [rsp+C0h] [rbp-40h]
  __int64 v53; // [rsp+C8h] [rbp-38h]
  const WCHAR *v54; // [rsp+D0h] [rbp-30h]
  int v55; // [rsp+D8h] [rbp-28h]
  int v56; // [rsp+DCh] [rbp-24h]
  const char *v57; // [rsp+E0h] [rbp-20h]
  __int64 v58; // [rsp+E8h] [rbp-18h]

  v42 = 0;
  LODWORD(v1) = 0;
  v3 = -1;
  v40 = 0;
  v41 = 0;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v4 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v4 = gIkeExtGlobals;
LABEL_9:
    v7 = 0;
    goto LABEL_10;
  }
  v7 = *Value;
  v4 = gIkeExtGlobals;
LABEL_10:
  v39 = v7;
  v52 = &v39;
  v53 = 8;
  if ( !v4 )
    goto LABEL_18;
  v8 = (DWORD)v4[86].LockSemaphore;
  if ( v8 == -1 )
    goto LABEL_18;
  v9 = (char *)TlsGetValue(v8);
  v10 = (const WCHAR *)(v9 + 8);
  if ( !v9 )
    v10 = 0;
  if ( v10 )
  {
    v11 = -1;
    do
      v12 = v10[++v11] == 0;
    while ( !v12 );
    v13 = 2 * v11 + 2;
  }
  else
  {
LABEL_18:
    v10 = &LocaleName;
    v13 = 2;
  }
  v55 = v13;
  v44 = 5;
  v46 = off_180173280;
  v54 = v10;
  v56 = 0;
  v57 = "IkeSendEmptyInformationalReqIkeV2";
  v58 = 34;
  v43 = 184549376;
  v45 = 1;
  v47 = *(unsigned __int16 *)off_180173280;
  v49 = (__int16 *)&dword_180166EA4;
  v48 = 2;
  v50 = 45;
  v51 = 1;
  EtwEventWriteTransfer(qword_180173298, &v43, 0, 0, 5, &v46);
LABEL_20:
  inited = IkeConstructHdr(
             (int)a1 + 584,
             (unsigned int)&v40,
             (int)a1 + 680,
             (int)a1 + 688,
             37,
             *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 452LL),
             (*(_DWORD *)(a1 + 592) >> 14) & 8);
  if ( inited )
    goto LABEL_54;
  v16 = *(_QWORD *)(a1 + 1104);
  if ( (*(_BYTE *)(a1 + 752) & 1) != 0 )
  {
    inited = IkeConstructEncryptIkeV2(&v40, a1 + 752);
    if ( inited )
      goto LABEL_54;
    goto LABEL_49;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    if ( gIkeExtGlobals )
    {
      LockSemaphore_low = LODWORD(gIkeExtGlobals[86].LockSemaphore);
      if ( (_DWORD)LockSemaphore_low != -1 )
      {
        v18 = (__int64 *)TlsGetValue(LockSemaphore_low);
        v17 = WPP_GLOBAL_Control;
        if ( v18 )
          v1 = *v18;
      }
    }
    v19 = v17[2];
    TlsPeerAddr = IkeGetTlsPeerAddr(LockSemaphore_low);
    WPP_SF_iS(v19, 16, (unsigned int)WPP_5159582079a530f532f4b431d2895ff1_Traceguids, v1, TlsPeerAddr);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v21 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v22 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v22 != -1 )
      {
        v23 = (__int64 *)TlsGetValue(v22);
        if ( v23 )
        {
          v24 = *v23;
          v21 = gIkeExtGlobals;
LABEL_39:
          v39 = v24;
          v52 = &v39;
          v53 = 8;
          if ( !v21 )
            goto LABEL_47;
          v25 = (DWORD)v21[86].LockSemaphore;
          if ( v25 == -1 )
            goto LABEL_47;
          v26 = (char *)TlsGetValue(v25);
          v27 = (const WCHAR *)(v26 + 8);
          if ( !v26 )
            v27 = 0;
          if ( v27 )
          {
            v28 = -1;
            do
              v12 = v27[++v28] == 0;
            while ( !v12 );
            v29 = 2 * v28 + 2;
          }
          else
          {
LABEL_47:
            v27 = &LocaleName;
            v29 = 2;
          }
          v55 = v29;
          v54 = v27;
          v57 = "Sending cleartext empty Informational request";
          v44 = 4;
          v46 = off_180173280;
          v56 = 0;
          v58 = 46;
          v43 = 184549376;
          v45 = 0;
          v47 = *(unsigned __int16 *)off_180173280;
          v49 = &word_180160D26;
          v48 = 2;
          v50 = 63;
          v51 = 1;
          EtwEventWriteTransfer(qword_180173298, &v43, 0, 0, 5, &v46);
          goto LABEL_49;
        }
        v21 = gIkeExtGlobals;
      }
    }
    v24 = 0;
    goto LABEL_39;
  }
LABEL_49:
  inited = IkeFinishPacket((__int64 *)&v40, (_BYTE *)(a1 + 752), a1);
  if ( !inited )
  {
    inited = IkeSendPacket(&v40, a1 + 376, a1 + 280, a1);
    if ( !inited )
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 400LL) = 4;
      if ( *(_QWORD *)(v16 + 592) )
        IkeDestroyTimerContext(v16 + 592);
      inited = IkeAllocAndInitTimerContext(0, (unsigned int)&v40, a1, 0, 0, 0, 0, 0, v16 + 592);
    }
  }
LABEL_54:
  if ( (BYTE12(v41) & 2) != 0 && v42 )
  {
    Ikev2ClearFragmentListEntryList();
    WfpMemFree(&v42);
  }
  WfpMemFree(&v40);
  v42 = 0;
  v40 = 0;
  v41 = 0;
  if ( (unsigned int)dword_180173278 > 5 && (qword_180173288 & 1) != 0 && (qword_180173290 & 1) == qword_180173290 )
  {
    v30 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v31 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v31 != -1 )
      {
        v32 = (__int64 *)TlsGetValue(v31);
        if ( v32 )
        {
          v33 = *v32;
          v30 = gIkeExtGlobals;
LABEL_66:
          v39 = v33;
          v52 = &v39;
          v53 = 8;
          if ( !v30 )
            goto LABEL_73;
          v34 = (DWORD)v30[86].LockSemaphore;
          if ( v34 == -1 )
            goto LABEL_73;
          v35 = (char *)TlsGetValue(v34);
          v36 = (const WCHAR *)(v35 + 8);
          if ( !v35 )
            v36 = 0;
          if ( v36 )
          {
            do
              v12 = v36[++v3] == 0;
            while ( !v12 );
            v37 = 2 * v3 + 2;
          }
          else
          {
LABEL_73:
            v36 = &LocaleName;
            v37 = 2;
          }
          v44 = 5;
          v46 = off_180173280;
          v54 = v36;
          v55 = v37;
          v56 = 0;
          v57 = "IkeSendEmptyInformationalReqIkeV2";
          v58 = 34;
          v43 = 184549376;
          v45 = 1;
          v47 = *(unsigned __int16 *)off_180173280;
          v49 = (__int16 *)byte_180166E6B;
          v48 = 2;
          v50 = 45;
          v51 = 1;
          EtwEventWriteTransfer(qword_180173298, &v43, 0, 0, 5, &v46);
          return IkeReturnError(inited, "IkeSendEmptyInformationalReqIkeV2");
        }
        v30 = gIkeExtGlobals;
      }
    }
    v33 = 0;
    goto LABEL_66;
  }
  return IkeReturnError(inited, "IkeSendEmptyInformationalReqIkeV2");
}

```

## disassembly

```asm
0x18003fa20  push    rbp
0x18003fa22  push    rbx
0x18003fa23  push    rsi
0x18003fa24  push    rdi
0x18003fa25  push    r12
0x18003fa27  push    r13
0x18003fa29  push    r14
0x18003fa2b  push    r15
0x18003fa2d  lea     rbp, [rsp-8]
0x18003fa32  sub     rsp, 108h
0x18003fa39  mov     rax, cs:__security_cookie
0x18003fa40  xor     rax, rsp
0x18003fa43  mov     [rbp+40h+var_50], rax
0x18003fa47  xor     eax, eax
0x18003fa49  lea     r15, aIkesendemptyin; "IkeSendEmptyInformationalReqIkeV2"
0x18003fa50  xorps   xmm0, xmm0
0x18003fa53  mov     [rbp+40h+var_C0], rax
0x18003fa57  mov     eax, cs:dword_180173278
0x18003fa5d  lea     r12, _TraceLoggingMetadataEnd
0x18003fa64  xor     r14d, r14d
0x18003fa67  lea     r13, _TraceLoggingMetadata
0x18003fa6e  mov     rsi, rcx
0x18003fa71  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18003fa78  movups  [rsp+140h+var_E0], xmm0
0x18003fa7d  movups  [rsp+140h+var_D0], xmm0
0x18003fa82  cmp     eax, 5
0x18003fa85  jbe     loc_18003FBE8
0x18003fa8b  mov     rcx, cs:qword_180173290
0x18003fa92  mov     rax, cs:qword_180173288
0x18003fa99  test    al, 1
0x18003fa9b  jz      loc_18003FBE8
0x18003faa1  mov     rax, rcx
0x18003faa4  and     eax, 1
0x18003faa7  cmp     rax, rcx
0x18003faaa  jnz     loc_18003FBE8
0x18003fab0  mov     rax, cs:gIkeExtGlobals
0x18003fab7  test    rax, rax
0x18003faba  jz      short loc_18003FAE5
0x18003fabc  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003fac2  cmp     ecx, 0FFFFFFFFh
0x18003fac5  jz      short loc_18003FAE5
0x18003fac7  call    cs:__imp_TlsGetValue
0x18003facd  test    rax, rax
0x18003fad0  jz      short loc_18003FADE
0x18003fad2  mov     rcx, [rax]
0x18003fad5  mov     rax, cs:gIkeExtGlobals
0x18003fadc  jmp     short loc_18003FAE8
0x18003fade  mov     rax, cs:gIkeExtGlobals
0x18003fae5  mov     rcx, r14
0x18003fae8  mov     [rsp+140h+var_E8], rcx
0x18003faed  lea     rcx, [rsp+140h+var_E8]
0x18003faf2  mov     [rbp+40h+var_80], rcx
0x18003faf6  mov     [rbp+40h+var_78], 8
0x18003fafe  test    rax, rax
0x18003fb01  jz      short loc_18003FB45
0x18003fb03  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003fb09  cmp     ecx, 0FFFFFFFFh
0x18003fb0c  jz      short loc_18003FB45
0x18003fb0e  call    cs:__imp_TlsGetValue
0x18003fb14  test    rax, rax
0x18003fb17  lea     rdx, [rax+8]
0x18003fb1b  cmovz   rdx, r14
0x18003fb1f  test    rdx, rdx
0x18003fb22  jz      short loc_18003FB45
0x18003fb24  mov     rax, rdi
0x18003fb27  nop     word ptr [rax+rax+00000000h]
0x18003fb30  cmp     [rdx+rax*2+2], r14w
0x18003fb36  lea     rax, [rax+1]
0x18003fb3a  jnz     short loc_18003FB30
0x18003fb3c  lea     eax, ds:2[rax*2]
0x18003fb43  jmp     short loc_18003FB51
0x18003fb45  lea     rdx, LocaleName
0x18003fb4c  mov     eax, 2
0x18003fb51  mov     [rbp+40h+var_68], eax
0x18003fb54  xor     r9d, r9d
0x18003fb57  movzx   eax, cs:word_180166E9A
0x18003fb5e  xor     r8d, r8d
0x18003fb61  mov     [rbp+40h+var_B4], eax
0x18003fb64  mov     rax, cs:off_180173280
0x18003fb6b  mov     [rbp+40h+var_A0], rax
0x18003fb6f  mov     [rbp+40h+var_70], rdx
0x18003fb73  lea     rdx, [rbp+40h+var_B8]
0x18003fb77  mov     [rbp+40h+var_64], r14d
0x18003fb7b  mov     [rbp+40h+var_60], r15
0x18003fb7f  mov     [rbp+40h+var_58], 22h ; '"'
0x18003fb87  mov     [rbp+40h+var_B8], 0B000000h
0x18003fb8e  mov     [rbp+40h+var_B0], 1
0x18003fb96  movzx   eax, word ptr [rax]
0x18003fb99  mov     [rbp+40h+var_98], eax
0x18003fb9c  lea     rax, dword_180166EA4
0x18003fba3  mov     [rbp+40h+var_90], rax
0x18003fba7  mov     rax, r12
0x18003fbaa  sub     eax, r13d
0x18003fbad  mov     [rbp+40h+var_94], 2
0x18003fbb4  mov     [rbp+40h+var_88], 2Dh ; '-'
0x18003fbbb  mov     [rbp+40h+var_84], 1
0x18003fbc2  mov     [rsp+140h+var_F0], eax
0x18003fbc6  mov     eax, [rsp+140h+var_F0]
0x18003fbca  mov     rcx, cs:qword_180173298
0x18003fbd1  lea     rax, [rbp+40h+var_A0]
0x18003fbd5  mov     [rsp+140h+var_118], rax
0x18003fbda  mov     dword ptr [rsp+140h+var_120], 5
0x18003fbe2  call    cs:__imp_EtwEventWriteTransfer
0x18003fbe8  mov     rax, [rsi+450h]
0x18003fbef  lea     rcx, [rsi+248h]
0x18003fbf6  mov     edx, [rcx+8]
0x18003fbf9  lea     r9, [rsi+2B0h]
0x18003fc00  shr     edx, 0Eh
0x18003fc03  lea     r8, [rsi+2A8h]
0x18003fc0a  and     dl, 8
0x18003fc0d  mov     eax, [rax+1C4h]
0x18003fc13  mov     byte ptr [rsp+140h+var_110], dl
0x18003fc17  lea     rdx, [rsp+140h+var_E0]
0x18003fc1c  mov     dword ptr [rsp+140h+var_118], eax
0x18003fc20  mov     byte ptr [rsp+140h+var_120], 25h ; '%'
0x18003fc25  call    IkeConstructHdr
0x18003fc2a  mov     rbx, rax
0x18003fc2d  test    rax, rax
0x18003fc30  jnz     loc_18003FEC3
0x18003fc36  test    byte ptr [rsi+2F0h], 1
0x18003fc3d  mov     r13, [rsi+450h]
0x18003fc44  jz      short loc_18003FC68
0x18003fc46  lea     rdx, [rsi+2F0h]
0x18003fc4d  lea     rcx, [rsp+140h+var_E0]
0x18003fc52  call    IkeConstructEncryptIkeV2
0x18003fc57  mov     rbx, rax
0x18003fc5a  test    rax, rax
0x18003fc5d  jnz     loc_18003FEB5
0x18003fc63  jmp     loc_18003FE22
0x18003fc68  mov     rbx, cs:WPP_GLOBAL_Control
0x18003fc6f  lea     rax, WPP_GLOBAL_Control
0x18003fc76  cmp     rbx, rax
0x18003fc79  jz      short loc_18003FCDB
0x18003fc7b  cmp     byte ptr [rbx+19h], 4
0x18003fc7f  jb      short loc_18003FCDB
0x18003fc81  test    byte ptr [rbx+1Ch], 10h
0x18003fc85  jz      short loc_18003FCDB
0x18003fc87  mov     rax, cs:gIkeExtGlobals
0x18003fc8e  test    rax, rax
0x18003fc91  jz      short loc_18003FCB3
0x18003fc93  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003fc99  cmp     ecx, 0FFFFFFFFh
0x18003fc9c  jz      short loc_18003FCB3
0x18003fc9e  call    cs:__imp_TlsGetValue
0x18003fca4  mov     rbx, cs:WPP_GLOBAL_Control
0x18003fcab  test    rax, rax
0x18003fcae  jz      short loc_18003FCB3
0x18003fcb0  mov     r14, [rax]
0x18003fcb3  mov     rbx, [rbx+10h]
0x18003fcb7  call    IkeGetTlsPeerAddr
0x18003fcbc  mov     edx, 10h
0x18003fcc1  mov     [rsp+140h+var_120], rax
0x18003fcc6  mov     r9, r14
0x18003fcc9  lea     r8, WPP_5159582079a530f532f4b431d2895ff1_Traceguids
0x18003fcd0  mov     rcx, rbx
0x18003fcd3  call    WPP_SF_iS
0x18003fcd8  xor     r14d, r14d
0x18003fcdb  mov     eax, cs:dword_180173278
0x18003fce1  cmp     eax, 4
0x18003fce4  jbe     loc_18003FE22
0x18003fcea  mov     rax, cs:gIkeExtGlobals
0x18003fcf1  test    rax, rax
0x18003fcf4  jz      short loc_18003FD1F
0x18003fcf6  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003fcfc  cmp     ecx, 0FFFFFFFFh
0x18003fcff  jz      short loc_18003FD1F
0x18003fd01  call    cs:__imp_TlsGetValue
0x18003fd07  test    rax, rax
0x18003fd0a  jz      short loc_18003FD18
0x18003fd0c  mov     rcx, [rax]
0x18003fd0f  mov     rax, cs:gIkeExtGlobals
0x18003fd16  jmp     short loc_18003FD22
0x18003fd18  mov     rax, cs:gIkeExtGlobals
0x18003fd1f  mov     rcx, r14
0x18003fd22  mov     [rsp+140h+var_E8], rcx
0x18003fd27  lea     rcx, [rsp+140h+var_E8]
0x18003fd2c  mov     [rbp+40h+var_80], rcx
0x18003fd30  mov     [rbp+40h+var_78], 8
0x18003fd38  test    rax, rax
0x18003fd3b  jz      short loc_18003FD76
0x18003fd3d  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003fd43  cmp     ecx, 0FFFFFFFFh
0x18003fd46  jz      short loc_18003FD76
0x18003fd48  call    cs:__imp_TlsGetValue
0x18003fd4e  test    rax, rax
0x18003fd51  lea     rdx, [rax+8]
0x18003fd55  cmovz   rdx, r14
0x18003fd59  test    rdx, rdx
0x18003fd5c  jz      short loc_18003FD76
0x18003fd5e  mov     rax, rdi
0x18003fd61  cmp     word ptr [rdx+rax*2+2], 0
0x18003fd67  lea     rax, [rax+1]
0x18003fd6b  jnz     short loc_18003FD61
0x18003fd6d  lea     eax, ds:2[rax*2]
0x18003fd74  jmp     short loc_18003FD82
0x18003fd76  lea     rdx, LocaleName
0x18003fd7d  mov     eax, 2
0x18003fd82  mov     [rbp+40h+var_68], eax
0x18003fd85  lea     rcx, _TraceLoggingMetadata
0x18003fd8c  mov     [rbp+40h+var_70], rdx
0x18003fd90  lea     rax, aSendingClearte_0; "Sending cleartext empty Informational r"...
0x18003fd97  mov     [rbp+40h+var_60], rax
0x18003fd9b  lea     rdx, [rbp+40h+var_B8]
0x18003fd9f  movzx   eax, cs:word_180160D1C
0x18003fda6  xor     r9d, r9d
0x18003fda9  mov     [rbp+40h+var_B4], eax
0x18003fdac  xor     r8d, r8d
0x18003fdaf  mov     rax, cs:off_180173280
0x18003fdb6  mov     [rbp+40h+var_A0], rax
0x18003fdba  mov     [rbp+40h+var_64], r14d
0x18003fdbe  mov     [rbp+40h+var_58], 2Eh ; '.'
0x18003fdc6  mov     [rbp+40h+var_B8], 0B000000h
0x18003fdcd  mov     [rbp+40h+var_B0], r14
0x18003fdd1  movzx   eax, word ptr [rax]
0x18003fdd4  mov     [rbp+40h+var_98], eax
0x18003fdd7  lea     rax, word_180160D26
0x18003fdde  mov     [rbp+40h+var_90], rax
0x18003fde2  mov     rax, r12
0x18003fde5  sub     eax, ecx
0x18003fde7  mov     [rbp+40h+var_94], 2
0x18003fdee  mov     [rbp+40h+var_88], 3Fh ; '?'
0x18003fdf5  mov     [rbp+40h+var_84], 1
0x18003fdfc  mov     [rsp+140h+var_F0], eax
0x18003fe00  mov     eax, [rsp+140h+var_F0]
0x18003fe04  mov     rcx, cs:qword_180173298
0x18003fe0b  lea     rax, [rbp+40h+var_A0]
0x18003fe0f  mov     [rsp+140h+var_118], rax
0x18003fe14  mov     dword ptr [rsp+140h+var_120], 5
0x18003fe1c  call    cs:__imp_EtwEventWriteTransfer
0x18003fe22  mov     r8, rsi
0x18003fe25  lea     rdx, [rsi+2F0h]
0x18003fe2c  lea     rcx, [rsp+140h+var_E0]
0x18003fe31  call    IkeFinishPacket
0x18003fe36  mov     rbx, rax
0x18003fe39  test    rax, rax
0x18003fe3c  jnz     short loc_18003FEB5
0x18003fe3e  lea     r8, [rsi+118h]
0x18003fe45  mov     r9, rsi
0x18003fe48  lea     rdx, [rsi+178h]
0x18003fe4f  lea     rcx, [rsp+140h+var_E0]
0x18003fe54  call    IkeSendPacket
0x18003fe59  mov     rbx, rax
0x18003fe5c  test    rax, rax
0x18003fe5f  jnz     short loc_18003FEB5
0x18003fe61  mov     rax, [rsi+450h]
0x18003fe68  lea     rbx, [r13+250h]
0x18003fe6f  mov     dword ptr [rax+190h], 4
0x18003fe79  cmp     qword ptr [rbx], 0
0x18003fe7d  jz      short loc_18003FE87
0x18003fe7f  mov     rcx, rbx
0x18003fe82  call    IkeDestroyTimerContext
0x18003fe87  mov     [rsp+140h+var_100], rbx
0x18003fe8c  lea     rdx, [rsp+140h+var_E0]
0x18003fe91  mov     [rsp+140h+var_108], r14
0x18003fe96  xor     r9d, r9d
0x18003fe99  mov     [rsp+140h+var_110], r14d
0x18003fe9e  mov     r8, rsi
0x18003fea1  mov     dword ptr [rsp+140h+var_118], r14d
0x18003fea6  xor     ecx, ecx
0x18003fea8  mov     dword ptr [rsp+140h+var_120], r14d
0x18003fead  call    IkeAllocAndInitTimerContext
0x18003feb2  mov     rbx, rax
0x18003feb5  lea     r13, _TraceLoggingMetadata
0x18003febc  lea     r15, aIkesendemptyin; "IkeSendEmptyInformationalReqIkeV2"
0x18003fec3  test    byte ptr [rsp+140h+var_D0+0Ch], 2
0x18003fec8  jz      short loc_18003FEE1
0x18003feca  mov     rcx, [rbp+40h+var_C0]
0x18003fece  test    rcx, rcx
0x18003fed1  jz      short loc_18003FEE1
0x18003fed3  call    Ikev2ClearFragmentListEntryList
0x18003fed8  lea     rcx, [rbp+40h+var_C0]
0x18003fedc  call    WfpMemFree
0x18003fee1  lea     rcx, [rsp+140h+var_E0]
0x18003fee6  call    WfpMemFree
0x18003feeb  xor     eax, eax
0x18003feed  xorps   xmm0, xmm0
0x18003fef0  mov     [rbp+40h+var_C0], rax
0x18003fef4  mov     eax, cs:dword_180173278
0x18003fefa  movups  [rsp+140h+var_E0], xmm0
0x18003feff  movups  [rsp+140h+var_D0], xmm0
0x18003ff04  cmp     eax, 5
0x18003ff07  jbe     loc_180040066
0x18003ff0d  mov     rcx, cs:qword_180173290
0x18003ff14  mov     rax, cs:qword_180173288
0x18003ff1b  test    al, 1
0x18003ff1d  jz      loc_180040066
0x18003ff23  mov     rax, rcx
0x18003ff26  and     eax, 1
0x18003ff29  cmp     rax, rcx
0x18003ff2c  jnz     loc_180040066
0x18003ff32  mov     rax, cs:gIkeExtGlobals
0x18003ff39  test    rax, rax
0x18003ff3c  jz      short loc_18003FF67
0x18003ff3e  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003ff44  cmp     ecx, 0FFFFFFFFh
0x18003ff47  jz      short loc_18003FF67
0x18003ff49  call    cs:__imp_TlsGetValue
0x18003ff4f  test    rax, rax
0x18003ff52  jz      short loc_18003FF60
0x18003ff54  mov     rcx, [rax]
  ... truncated ...
```
