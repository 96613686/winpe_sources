# IkeFinishPacket

- ea: `0x180031640`
- end: `0x180031dc1`
- name: `IkeFinishPacket`
- size: `1921`
- prototype: ``
- caller_count: `19`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x18003fa20`
- `0x1800416f0`
- `0x18004b818`
- `0x1800c6c54`
- `0x1800d44f0`
- `0x1800d49d0`
- `0x1800d4b7c`
- `0x1800d4d8c`
- `0x1800dcad8`
- `0x1800dceb4`
- `0x1800dd194`
- `0x1800dd38c`
- `0x1800dd564`
- `0x1800dd994`
- `0x1800ddbe8`
- `0x180108c04`
- `0x180108f38`
- `0x18010935c`
- `0x180109764`

## callees

- `0x180008388`
- `0x180025fcc`
- `0x180031640`
- `0x180031dd0`
- `0x18004c1ac`
- `0x18004d08c`
- `0x180050850`
- `0x1800b0cd8`
- `0x1800b0e54`
- `0x1800b5cfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800316d2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180031717`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800318ac`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180031989`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800319ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180031b2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180031b6f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180031cb5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800316d2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180031717`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800318ac`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180031989`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800319ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180031b2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180031b6f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180031cb5`
- `ntdll!EtwEventWriteTransfer` at `0x1800317ec`
- `ntdll!EtwEventWriteTransfer` at `0x180031aa6`
- `ntdll!EtwEventWriteTransfer` at `0x180031c4d`
- `ntdll!EtwEventWriteTransfer` at `0x180031d85`
- `ntdll!EtwEventWriteTransfer` at `0x1800317ec`
- `ntdll!EtwEventWriteTransfer` at `0x180031aa6`
- `ntdll!EtwEventWriteTransfer` at `0x180031c4d`
- `ntdll!EtwEventWriteTransfer` at `0x180031d85`
- `WS2_32!__imp_htonl` at `0x180031ab5`
- `WS2_32!__imp_htonl` at `0x180031ac1`
- `WS2_32!__imp_htonl` at `0x180031ab5`
- `WS2_32!__imp_htonl` at `0x180031ac1`

## pseudocode

```c
__int64 __fastcall IkeFinishPacket(__int64 *a1, _BYTE *a2, __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // rsi
  LPCRITICAL_SECTION v8; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v11; // rcx
  DWORD v12; // ecx
  char *v13; // rax
  const WCHAR *v14; // rdx
  __int64 v15; // rax
  bool v16; // zf
  int v17; // eax
  char v18; // r8
  __int64 v19; // rax
  LPCRITICAL_SECTION v20; // rax
  DWORD v21; // ecx
  __int64 *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 updated; // r14
  LPCRITICAL_SECTION v26; // rax
  DWORD v27; // ecx
  __int64 *v28; // rax
  __int64 v29; // rcx
  DWORD v30; // ecx
  char *v31; // rax
  const WCHAR *v32; // rdx
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rbx
  u_long v36; // ecx
  u_long v37; // eax
  u_long v38; // ecx
  u_long v39; // eax
  LPCRITICAL_SECTION v40; // rax
  DWORD v41; // ecx
  __int64 *v42; // rax
  __int64 v43; // rcx
  DWORD v44; // ecx
  char *v45; // rax
  const WCHAR *v46; // rdx
  __int64 v47; // rax
  int v48; // eax
  DWORD v49; // ecx
  char *v50; // rax
  const WCHAR *v51; // rdx
  int v52; // esi
  __int64 v54; // [rsp+38h] [rbp-51h] BYREF
  int v55; // [rsp+40h] [rbp-49h] BYREF
  int v56; // [rsp+44h] [rbp-45h]
  __int64 v57; // [rsp+48h] [rbp-41h]
  char *v58; // [rsp+50h] [rbp-39h] BYREF
  int v59; // [rsp+58h] [rbp-31h]
  int v60; // [rsp+5Ch] [rbp-2Dh]
  int *v61; // [rsp+60h] [rbp-29h]
  int v62; // [rsp+68h] [rbp-21h]
  int v63; // [rsp+6Ch] [rbp-1Dh]
  __int64 *v64; // [rsp+70h] [rbp-19h]
  __int64 v65; // [rsp+78h] [rbp-11h]
  const WCHAR *v66; // [rsp+80h] [rbp-9h]
  int v67; // [rsp+88h] [rbp-1h]
  int v68; // [rsp+8Ch] [rbp+3h]
  const char *v69; // [rsp+90h] [rbp+7h]
  __int64 v70; // [rsp+98h] [rbp+Fh]

  v6 = 0;
  v7 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v8 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v8 = gIkeExtGlobals;
LABEL_9:
    v11 = 0;
    goto LABEL_10;
  }
  v11 = *Value;
  v8 = gIkeExtGlobals;
LABEL_10:
  v54 = v11;
  v64 = &v54;
  v65 = 8;
  if ( !v8 )
    goto LABEL_18;
  v12 = (DWORD)v8[86].LockSemaphore;
  if ( v12 == -1 )
    goto LABEL_18;
  v13 = (char *)TlsGetValue(v12);
  v14 = (const WCHAR *)(v13 + 8);
  if ( !v13 )
    v14 = 0;
  if ( v14 )
  {
    v15 = -1;
    do
      v16 = v14[++v15] == 0;
    while ( !v16 );
    v17 = 2 * v15 + 2;
  }
  else
  {
LABEL_18:
    v14 = &LocaleName;
    v17 = 2;
  }
  v67 = v17;
  v66 = v14;
  v69 = "IkeFinishPacket";
  v56 = 5;
  v58 = off_180173280;
  v68 = 0;
  v70 = 16;
  v55 = 184549376;
  v57 = 1;
  v59 = *(unsigned __int16 *)off_180173280;
  v61 = &dword_180166EA4;
  v60 = 2;
  v62 = 45;
  v63 = 1;
  EtwEventWriteTransfer(qword_180173298, &v55, 0, 0, 5, &v58);
LABEL_20:
  if ( !*a1 )
    goto LABEL_28;
  IkeDumpPacket(a1, "Outgoing packet");
  if ( (*a2 & 1) == 0 )
  {
    updated = 0;
    if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
      goto LABEL_61;
    v26 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v27 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v27 != -1 )
      {
        v28 = (__int64 *)TlsGetValue(v27);
        if ( v28 )
        {
          v29 = *v28;
          v26 = gIkeExtGlobals;
LABEL_51:
          v54 = v29;
          v64 = &v54;
          v65 = 8;
          if ( !v26 )
            goto LABEL_59;
          v30 = (DWORD)v26[86].LockSemaphore;
          if ( v30 == -1 )
            goto LABEL_59;
          v31 = (char *)TlsGetValue(v30);
          v32 = (const WCHAR *)(v31 + 8);
          if ( !v31 )
            v32 = 0;
          if ( v32 )
          {
            v33 = -1;
            do
              v16 = v32[++v33] == 0;
            while ( !v16 );
            v34 = 2 * v33 + 2;
          }
          else
          {
LABEL_59:
            v32 = &LocaleName;
            v34 = 2;
          }
          v67 = v34;
          v56 = 5;
          v58 = off_180173280;
          v66 = v32;
          v68 = 0;
          v69 = "IkeFixupHeader";
          v70 = 15;
          v55 = 184549376;
          v57 = 1;
          v59 = *(unsigned __int16 *)off_180173280;
          v61 = &dword_180166EA4;
          v60 = 2;
          v62 = 45;
          v63 = 1;
          EtwEventWriteTransfer(qword_180173298, &v55, 0, 0, 5, &v58);
LABEL_61:
          v35 = *a1;
          v36 = *((_DWORD *)a1 + 2);
          *(_DWORD *)(*a1 + 24) = v36;
          v37 = htonl(v36);
          v38 = *(_DWORD *)(v35 + 20);
          *(_DWORD *)(v35 + 24) = v37;
          v39 = htonl(v38);
          v16 = *(_BYTE *)(v35 + 18) == 0xF3;
          *(_DWORD *)(v35 + 20) = v39;
          if ( v16 )
            updated = IkeUpdateCumulativeHash(a1, a2);
          if ( (unsigned int)dword_180173278 <= 5
            || (qword_180173288 & 1) == 0
            || (qword_180173290 & 1) != qword_180173290 )
          {
            v6 = IkeReturnError(updated, "IkeFixupHeader");
            goto LABEL_28;
          }
          v40 = gIkeExtGlobals;
          if ( gIkeExtGlobals )
          {
            v41 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
            if ( v41 != -1 )
            {
              v42 = (__int64 *)TlsGetValue(v41);
              if ( v42 )
              {
                v43 = *v42;
                v40 = gIkeExtGlobals;
LABEL_72:
                v54 = v43;
                v64 = &v54;
                v65 = 8;
                if ( !v40 )
                  goto LABEL_80;
                v44 = (DWORD)v40[86].LockSemaphore;
                if ( v44 == -1 )
                  goto LABEL_80;
                v45 = (char *)TlsGetValue(v44);
                v46 = (const WCHAR *)(v45 + 8);
                if ( !v45 )
                  v46 = 0;
                if ( v46 )
                {
                  v47 = -1;
                  do
                    v16 = v46[++v47] == 0;
                  while ( !v16 );
                  v48 = 2 * v47 + 2;
                }
                else
                {
LABEL_80:
                  v46 = &LocaleName;
                  v48 = 2;
                }
                v67 = v48;
                v56 = 5;
                v58 = off_180173280;
                v66 = v46;
                v68 = 0;
                v69 = "IkeFixupHeader";
                v70 = 15;
                v55 = 184549376;
                v57 = 1;
                v59 = *(unsigned __int16 *)off_180173280;
                v60 = 2;
                v61 = (int *)byte_180166E6B;
                v62 = 45;
                v63 = 1;
                EtwEventWriteTransfer(qword_180173298, &v55, 0, 0, 5, &v58);
                v6 = IkeReturnError(updated, "IkeFixupHeader");
LABEL_28:
                if ( (unsigned int)dword_180173278 <= 5
                  || (qword_180173288 & 1) == 0
                  || (qword_180173290 & 1) != qword_180173290 )
                {
LABEL_94:
                  v24 = v6;
                  return IkeReturnError(v24, "IkeFinishPacket");
                }
                v20 = gIkeExtGlobals;
                if ( gIkeExtGlobals )
                {
                  v21 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
                  if ( v21 != -1 )
                  {
                    v22 = (__int64 *)TlsGetValue(v21);
                    if ( v22 )
                    {
                      v23 = *v22;
                      v20 = gIkeExtGlobals;
LABEL_85:
                      v54 = v23;
                      v64 = &v54;
                      v65 = 8;
                      if ( !v20 )
                        goto LABEL_92;
                      v49 = (DWORD)v20[86].LockSemaphore;
                      if ( v49 == -1 )
                        goto LABEL_92;
                      v50 = (char *)TlsGetValue(v49);
                      v51 = (const WCHAR *)(v50 + 8);
                      if ( !v50 )
                        v51 = 0;
                      if ( v51 )
                      {
                        do
                          v16 = v51[++v7] == 0;
                        while ( !v16 );
                        v52 = 2 * v7 + 2;
                      }
                      else
                      {
LABEL_92:
                        v51 = &LocaleName;
                        v52 = 2;
                      }
                      v66 = v51;
                      v69 = "IkeFinishPacket";
                      v56 = 5;
                      v58 = off_180173280;
                      v67 = v52;
                      v68 = 0;
                      v70 = 16;
                      v55 = 184549376;
                      v57 = 1;
                      v59 = *(unsigned __int16 *)off_180173280;
                      v60 = 2;
                      v61 = (int *)byte_180166E6B;
                      v62 = 45;
                      v63 = 1;
                      EtwEventWriteTransfer(qword_180173298, &v55, 0, 0, 5, &v58);
                      goto LABEL_94;
                    }
                    v20 = gIkeExtGlobals;
                  }
                }
                v23 = 0;
                goto LABEL_85;
              }
              v40 = gIkeExtGlobals;
            }
          }
          v43 = 0;
          goto LABEL_72;
        }
        v26 = gIkeExtGlobals;
      }
    }
    v29 = 0;
    goto LABEL_51;
  }
  v18 = *(_BYTE *)(*a1 + 18);
  switch ( v18 )
  {
    case 2:
      v19 = IkeEncryptOakPacket(a1, a2);
      goto LABEL_27;
    case 32:
      __fastfail(5u);
    case 5:
      v19 = IkeEncryptOakNDPacket(a1, a2, a3);
      goto LABEL_27;
  }
  if ( (unsigned __int8)(v18 + 13) <= 3u )
  {
    v19 = IkeSignAndEncryptPacketAuthip(a1, a2);
LABEL_27:
    v6 = v19;
    goto LABEL_28;
  }
  if ( !(unsigned int)Ikev2IsFragmentationNeeded(a3, a1) )
  {
    v6 = IkeSignAndEncryptPacketIkeV2(a1, (__int64)a2, a3 + 584, 0);
    if ( !v6 )
      *((_DWORD *)a1 + 7) |= 4u;
    goto LABEL_28;
  }
  v24 = 0;
  return IkeReturnError(v24, "IkeFinishPacket");
}

```

## disassembly

```asm
0x180031640  mov     [rsp-8+arg_18], rbx
0x180031645  push    rbp
0x180031646  push    rsi
0x180031647  push    rdi
0x180031648  push    r12
0x18003164a  push    r13
0x18003164c  push    r14
0x18003164e  push    r15
0x180031650  lea     rbp, [rsp-27h]
0x180031655  sub     rsp, 0B0h
0x18003165c  mov     rax, cs:__security_cookie
0x180031663  xor     rax, rsp
0x180031666  mov     [rbp+57h+var_40], rax
0x18003166a  mov     eax, cs:dword_180173278
0x180031670  lea     r12, _TraceLoggingMetadataEnd
0x180031677  xor     r13d, r13d
0x18003167a  mov     r14, r8
0x18003167d  mov     r15, rdx
0x180031680  mov     rdi, rcx
0x180031683  mov     ebx, r13d
0x180031686  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18003168d  cmp     eax, 5
0x180031690  jbe     loc_1800317F2
0x180031696  mov     rcx, cs:qword_180173290
0x18003169d  mov     rax, cs:qword_180173288
0x1800316a4  test    al, 1
0x1800316a6  jz      loc_1800317F2
0x1800316ac  mov     rax, rcx
0x1800316af  and     eax, 1
0x1800316b2  cmp     rax, rcx
0x1800316b5  jnz     loc_1800317F2
0x1800316bb  mov     rax, cs:gIkeExtGlobals
0x1800316c2  test    rax, rax
0x1800316c5  jz      short loc_1800316F0
0x1800316c7  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800316cd  cmp     ecx, 0FFFFFFFFh
0x1800316d0  jz      short loc_1800316F0
0x1800316d2  call    cs:__imp_TlsGetValue
0x1800316d8  test    rax, rax
0x1800316db  jz      short loc_1800316E9
0x1800316dd  mov     rcx, [rax]
0x1800316e0  mov     rax, cs:gIkeExtGlobals
0x1800316e7  jmp     short loc_1800316F3
0x1800316e9  mov     rax, cs:gIkeExtGlobals
0x1800316f0  mov     rcx, r13
0x1800316f3  mov     [rbp+57h+var_A8], rcx
0x1800316f7  lea     rcx, [rbp+57h+var_A8]
0x1800316fb  mov     [rbp+57h+var_70], rcx
0x1800316ff  mov     [rbp+57h+var_68], 8
0x180031707  test    rax, rax
0x18003170a  jz      short loc_180031744
0x18003170c  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180031712  cmp     ecx, 0FFFFFFFFh
0x180031715  jz      short loc_180031744
0x180031717  call    cs:__imp_TlsGetValue
0x18003171d  test    rax, rax
0x180031720  lea     rdx, [rax+8]
0x180031724  cmovz   rdx, r13
0x180031728  test    rdx, rdx
0x18003172b  jz      short loc_180031744
0x18003172d  mov     rax, rsi
0x180031730  cmp     [rdx+rax*2+2], bx
0x180031735  lea     rax, [rax+1]
0x180031739  jnz     short loc_180031730
0x18003173b  lea     eax, ds:2[rax*2]
0x180031742  jmp     short loc_180031750
0x180031744  lea     rdx, LocaleName
0x18003174b  mov     eax, 2
0x180031750  mov     [rbp+57h+var_58], eax
0x180031753  lea     rcx, _TraceLoggingMetadata
0x18003175a  mov     [rbp+57h+var_60], rdx
0x18003175e  lea     rax, aIkefinishpacke; "IkeFinishPacket"
0x180031765  mov     [rbp+57h+var_50], rax
0x180031769  lea     rdx, [rbp+57h+var_A0]
0x18003176d  movzx   eax, cs:word_180166E9A
0x180031774  xor     r9d, r9d
0x180031777  mov     [rbp+57h+var_9C], eax
0x18003177a  xor     r8d, r8d
0x18003177d  mov     rax, cs:off_180173280
0x180031784  mov     [rbp+57h+var_90], rax
0x180031788  mov     [rbp+57h+var_54], r13d
0x18003178c  mov     [rbp+57h+var_48], 10h
0x180031794  mov     [rbp+57h+var_A0], 0B000000h
0x18003179b  mov     [rbp+57h+var_98], 1
0x1800317a3  movzx   eax, word ptr [rax]
0x1800317a6  mov     [rbp+57h+var_88], eax
0x1800317a9  lea     rax, dword_180166EA4
0x1800317b0  mov     [rbp+57h+var_80], rax
0x1800317b4  mov     rax, r12
0x1800317b7  sub     eax, ecx
0x1800317b9  mov     [rbp+57h+var_84], 2
0x1800317c0  mov     [rbp+57h+var_78], 2Dh ; '-'
0x1800317c7  mov     [rbp+57h+var_74], 1
0x1800317ce  mov     [rbp+57h+var_B0], eax
0x1800317d1  mov     eax, [rbp+57h+var_B0]
0x1800317d4  mov     rcx, cs:qword_180173298
0x1800317db  lea     rax, [rbp+57h+var_90]
0x1800317df  mov     [rsp+0E0h+var_B8], rax
0x1800317e4  mov     [rsp+0E0h+var_C0], 5
0x1800317ec  call    cs:__imp_EtwEventWriteTransfer
0x1800317f2  cmp     [rdi], rbx
0x1800317f5  jz      short loc_180031852
0x1800317f7  lea     rdx, aOutgoingPacket; "Outgoing packet"
0x1800317fe  mov     rcx, rdi
0x180031801  call    IkeDumpPacket
0x180031806  test    byte ptr [r15], 1
0x18003180a  jz      loc_180031934
0x180031810  mov     rax, [rdi]
0x180031813  movzx   r8d, byte ptr [rax+12h]
0x180031818  cmp     r8b, 2
0x18003181c  jz      loc_180031924
0x180031822  cmp     r8b, 20h ; ' '
0x180031826  jz      loc_18003191D
0x18003182c  cmp     r8b, 5
0x180031830  jz      loc_18003190A
0x180031836  add     r8b, 0Dh
0x18003183a  cmp     r8b, 3
0x18003183e  ja      loc_1800318CA
0x180031844  mov     rdx, r15
0x180031847  mov     rcx, rdi
0x18003184a  call    IkeSignAndEncryptPacketAuthip
0x18003184f  mov     rbx, rax
0x180031852  lea     rdi, byte_180166E6B
0x180031859  mov     eax, cs:dword_180173278
0x18003185f  cmp     eax, 5
0x180031862  jbe     loc_180031D8B
0x180031868  mov     rcx, cs:qword_180173290
0x18003186f  mov     rax, cs:qword_180173288
0x180031876  test    al, 1
0x180031878  jz      loc_180031D8B
0x18003187e  mov     rax, rcx
0x180031881  and     eax, 1
0x180031884  cmp     rax, rcx
0x180031887  jnz     loc_180031D8B
0x18003188d  mov     rax, cs:gIkeExtGlobals
0x180031894  test    rax, rax
0x180031897  jz      loc_180031C8E
0x18003189d  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800318a3  cmp     ecx, 0FFFFFFFFh
0x1800318a6  jz      loc_180031C8E
0x1800318ac  call    cs:__imp_TlsGetValue
0x1800318b2  test    rax, rax
0x1800318b5  jz      loc_180031C87
0x1800318bb  mov     rcx, [rax]
0x1800318be  mov     rax, cs:gIkeExtGlobals
0x1800318c5  jmp     loc_180031C91
0x1800318ca  mov     rdx, rdi
0x1800318cd  mov     rcx, r14
0x1800318d0  call    Ikev2IsFragmentationNeeded
0x1800318d5  test    eax, eax
0x1800318d7  jz      short loc_1800318E0
0x1800318d9  xor     ecx, ecx
0x1800318db  jmp     loc_180031D8E
0x1800318e0  lea     r8, [r14+248h]
0x1800318e7  xor     r9d, r9d
0x1800318ea  mov     rdx, r15
0x1800318ed  mov     rcx, rdi
0x1800318f0  call    IkeSignAndEncryptPacketIkeV2
0x1800318f5  mov     rbx, rax
0x1800318f8  test    rax, rax
0x1800318fb  jnz     loc_180031852
0x180031901  or      dword ptr [rdi+1Ch], 4
0x180031905  jmp     loc_180031852
0x18003190a  mov     r8, r14
0x18003190d  mov     rdx, r15
0x180031910  mov     rcx, rdi
0x180031913  call    IkeEncryptOakNDPacket
0x180031918  jmp     loc_18003184F
0x18003191d  mov     ecx, 5
0x180031922  int     29h; Win8: RtlFailFast(ecx)
0x180031924  mov     rdx, r15
0x180031927  mov     rcx, rdi
0x18003192a  call    IkeEncryptOakPacket
0x18003192f  jmp     loc_18003184F
0x180031934  mov     eax, cs:dword_180173278
0x18003193a  lea     rbx, aIkefixupheader; "IkeFixupHeader"
0x180031941  mov     r14, r13
0x180031944  cmp     eax, 5
0x180031947  jbe     loc_180031AAC
0x18003194d  mov     rcx, cs:qword_180173290
0x180031954  mov     rax, cs:qword_180173288
0x18003195b  test    al, 1
0x18003195d  jz      loc_180031AAC
0x180031963  mov     rax, rcx
0x180031966  and     eax, 1
0x180031969  cmp     rax, rcx
0x18003196c  jnz     loc_180031AAC
0x180031972  mov     rax, cs:gIkeExtGlobals
0x180031979  test    rax, rax
0x18003197c  jz      short loc_1800319A7
0x18003197e  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180031984  cmp     ecx, 0FFFFFFFFh
0x180031987  jz      short loc_1800319A7
0x180031989  call    cs:__imp_TlsGetValue
0x18003198f  test    rax, rax
0x180031992  jz      short loc_1800319A0
0x180031994  mov     rcx, [rax]
0x180031997  mov     rax, cs:gIkeExtGlobals
0x18003199e  jmp     short loc_1800319AA
0x1800319a0  mov     rax, cs:gIkeExtGlobals
0x1800319a7  mov     rcx, r13
0x1800319aa  mov     [rbp+57h+var_A8], rcx
0x1800319ae  lea     rcx, [rbp+57h+var_A8]
0x1800319b2  mov     [rbp+57h+var_70], rcx
0x1800319b6  mov     [rbp+57h+var_68], 8
0x1800319be  test    rax, rax
0x1800319c1  jz      short loc_180031A05
0x1800319c3  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800319c9  cmp     ecx, 0FFFFFFFFh
0x1800319cc  jz      short loc_180031A05
0x1800319ce  call    cs:__imp_TlsGetValue
0x1800319d4  test    rax, rax
0x1800319d7  lea     rdx, [rax+8]
0x1800319db  cmovz   rdx, r13
0x1800319df  test    rdx, rdx
0x1800319e2  jz      short loc_180031A05
0x1800319e4  mov     rax, rsi
0x1800319e7  nop     word ptr [rax+rax+00000000h]
0x1800319f0  cmp     [rdx+rax*2+2], r13w
0x1800319f6  lea     rax, [rax+1]
0x1800319fa  jnz     short loc_1800319F0
0x1800319fc  lea     eax, ds:2[rax*2]
0x180031a03  jmp     short loc_180031A11
0x180031a05  lea     rdx, LocaleName
0x180031a0c  mov     eax, 2
0x180031a11  mov     [rbp+57h+var_58], eax
0x180031a14  lea     rcx, _TraceLoggingMetadata
0x180031a1b  movzx   eax, cs:word_180166E9A
0x180031a22  xor     r9d, r9d
0x180031a25  mov     [rbp+57h+var_9C], eax
0x180031a28  xor     r8d, r8d
0x180031a2b  mov     rax, cs:off_180173280
0x180031a32  mov     [rbp+57h+var_90], rax
0x180031a36  mov     [rbp+57h+var_60], rdx
0x180031a3a  lea     rdx, [rbp+57h+var_A0]
0x180031a3e  mov     [rbp+57h+var_54], r13d
0x180031a42  mov     [rbp+57h+var_50], rbx
0x180031a46  mov     [rbp+57h+var_48], 0Fh
0x180031a4e  mov     [rbp+57h+var_A0], 0B000000h
0x180031a55  mov     [rbp+57h+var_98], 1
0x180031a5d  movzx   eax, word ptr [rax]
0x180031a60  mov     [rbp+57h+var_88], eax
0x180031a63  lea     rax, dword_180166EA4
0x180031a6a  mov     [rbp+57h+var_80], rax
0x180031a6e  mov     rax, r12
0x180031a71  sub     eax, ecx
0x180031a73  mov     [rbp+57h+var_84], 2
0x180031a7a  mov     [rbp+57h+var_78], 2Dh ; '-'
0x180031a81  mov     [rbp+57h+var_74], 1
0x180031a88  mov     [rbp+57h+var_B0], eax
0x180031a8b  mov     eax, [rbp+57h+var_B0]
0x180031a8e  mov     rcx, cs:qword_180173298
0x180031a95  lea     rax, [rbp+57h+var_90]
0x180031a99  mov     [rsp+0E0h+var_B8], rax
0x180031a9e  mov     [rsp+0E0h+var_C0], 5
0x180031aa6  call    cs:__imp_EtwEventWriteTransfer
0x180031aac  mov     rbx, [rdi]
0x180031aaf  mov     ecx, [rdi+8]; hostlong
0x180031ab2  mov     [rbx+18h], ecx
0x180031ab5  call    cs:__imp_htonl
0x180031abb  mov     ecx, [rbx+14h]; hostlong
0x180031abe  mov     [rbx+18h], eax
0x180031ac1  call    cs:__imp_htonl
0x180031ac7  cmp     byte ptr [rbx+12h], 0F3h
0x180031acb  mov     [rbx+14h], eax
0x180031ace  jnz     short loc_180031ADE
0x180031ad0  mov     rdx, r15
0x180031ad3  mov     rcx, rdi
0x180031ad6  call    IkeUpdateCumulativeHash
0x180031adb  mov     r14, rax
0x180031ade  mov     ecx, cs:dword_180173278
0x180031ae4  cmp     ecx, 5
0x180031ae7  jbe     loc_180031C66
0x180031aed  mov     rdx, cs:qword_180173290
0x180031af4  mov     rcx, cs:qword_180173288
0x180031afb  test    cl, 1
0x180031afe  jz      loc_180031C66
0x180031b04  mov     rcx, rdx
0x180031b07  and     ecx, 1
0x180031b0a  cmp     rcx, rdx
0x180031b0d  jnz     loc_180031C66
0x180031b13  mov     rax, cs:gIkeExtGlobals
0x180031b1a  test    rax, rax
0x180031b1d  jz      short loc_180031B48
0x180031b1f  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180031b25  cmp     ecx, 0FFFFFFFFh
0x180031b28  jz      short loc_180031B48
0x180031b2a  call    cs:__imp_TlsGetValue
0x180031b30  test    rax, rax
0x180031b33  jz      short loc_180031B41
0x180031b35  mov     rcx, [rax]
0x180031b38  mov     rax, cs:gIkeExtGlobals
0x180031b3f  jmp     short loc_180031B4B
0x180031b41  mov     rax, cs:gIkeExtGlobals
0x180031b48  mov     rcx, r13
0x180031b4b  mov     [rbp+57h+var_A8], rcx
0x180031b4f  lea     rcx, [rbp+57h+var_A8]
0x180031b53  mov     [rbp+57h+var_70], rcx
0x180031b57  mov     [rbp+57h+var_68], 8
0x180031b5f  test    rax, rax
  ... truncated ...
```
