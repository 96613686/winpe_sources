# IkeFreeAcquireContext

- ea: `0x180018240`
- end: `0x180018839`
- name: `IkeFreeAcquireContext`
- size: `1529`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800172d0`
- `0x18003a2e0`
- `0x18003aa50`
- `0x18006ab0c`
- `0x18006c894`
- `0x1800c1268`
- `0x1800e1944`

## callees

- `0x1800037c4`
- `0x180014860`
- `0x180016b20`
- `0x180018240`
- `0x180025d88`
- `0x180050850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800182e1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180018326`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001844b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180018484`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800184eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180018530`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180018703`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180018748`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800182e1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180018326`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001844b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180018484`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800184eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180018530`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180018703`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180018748`
- `ntdll!EtwEventWriteTransfer` at `0x1800183f0`
- `ntdll!EtwEventWriteTransfer` at `0x180018617`
- `ntdll!EtwEventWriteTransfer` at `0x18001880e`
- `ntdll!EtwEventWriteTransfer` at `0x1800183f0`
- `ntdll!EtwEventWriteTransfer` at `0x180018617`
- `ntdll!EtwEventWriteTransfer` at `0x18001880e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018665`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018677`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018689`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018665`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018677`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018689`

## pseudocode

```c
__int64 __fastcall IkeFreeAcquireContext(__int64 a1)
{
  __int64 v2; // rbx
  LPCRITICAL_SECTION v3; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v6; // rcx
  DWORD v7; // ecx
  char *v8; // rax
  const WCHAR *v9; // rdx
  __int64 v10; // rax
  bool v11; // zf
  int v12; // eax
  _QWORD *v13; // rcx
  LPCRITICAL_SECTION v14; // rdx
  DWORD v15; // eax
  LPVOID v16; // rax
  LPVOID v17; // r8
  __int64 v18; // rsi
  DWORD v19; // eax
  __int64 *v20; // rax
  __int64 v21; // r9
  LPCRITICAL_SECTION v22; // rax
  DWORD v23; // ecx
  __int64 *v24; // rax
  __int64 v25; // rcx
  DWORD v26; // ecx
  char *v27; // rax
  const WCHAR *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  void *v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  __int64 result; // rax
  LPCRITICAL_SECTION v35; // rax
  DWORD v36; // ecx
  __int64 *v37; // rax
  __int64 v38; // rcx
  DWORD v39; // ecx
  char *v40; // rax
  const WCHAR *v41; // rdx
  int v42; // ebx
  __int64 v43; // [rsp+38h] [rbp-71h] BYREF
  _QWORD v44[2]; // [rsp+40h] [rbp-69h] BYREF
  char *v45; // [rsp+50h] [rbp-59h] BYREF
  int v46; // [rsp+58h] [rbp-51h]
  int v47; // [rsp+5Ch] [rbp-4Dh]
  char *v48; // [rsp+60h] [rbp-49h]
  int v49; // [rsp+68h] [rbp-41h]
  int v50; // [rsp+6Ch] [rbp-3Dh]
  __int64 *v51; // [rsp+70h] [rbp-39h]
  __int64 v52; // [rsp+78h] [rbp-31h]
  const WCHAR *v53; // [rsp+80h] [rbp-29h]
  int v54; // [rsp+88h] [rbp-21h]
  int v55; // [rsp+8Ch] [rbp-1Dh]
  const char *v56; // [rsp+90h] [rbp-19h]
  __int64 v57; // [rsp+98h] [rbp-11h]
  _QWORD *v58; // [rsp+A0h] [rbp-9h]
  __int64 v59; // [rsp+A8h] [rbp-1h]
  int v60; // [rsp+B0h] [rbp+7h] BYREF
  int v61; // [rsp+B4h] [rbp+Bh]
  __int64 v62; // [rsp+B8h] [rbp+Fh]
  _QWORD v63[2]; // [rsp+C0h] [rbp+17h] BYREF

  v44[0] = a1;
  v2 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v3 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v3 = gIkeExtGlobals;
LABEL_9:
    v6 = 0;
    goto LABEL_10;
  }
  v6 = *Value;
  v3 = gIkeExtGlobals;
LABEL_10:
  v43 = v6;
  v51 = &v43;
  v52 = 8;
  if ( !v3 )
    goto LABEL_18;
  v7 = (DWORD)v3[86].LockSemaphore;
  if ( v7 == -1 )
    goto LABEL_18;
  v8 = (char *)TlsGetValue(v7);
  v9 = (const WCHAR *)(v8 + 8);
  if ( !v8 )
    v9 = 0;
  if ( v9 )
  {
    v10 = -1;
    do
      v11 = v9[++v10] == 0;
    while ( !v11 );
    v12 = 2 * v10 + 2;
  }
  else
  {
LABEL_18:
    v9 = &LocaleName;
    v12 = 2;
  }
  v54 = v12;
  v45 = off_180173280;
  v53 = v9;
  v55 = 0;
  v56 = "IkeFreeAcquireContext";
  v57 = 22;
  v63[0] = 0x50B000000LL;
  v63[1] = 1;
  v46 = *(unsigned __int16 *)off_180173280;
  v48 = (char *)&dword_180166EA4;
  v47 = 2;
  v49 = 45;
  v50 = 1;
  EtwEventWriteTransfer(qword_180173298, v63, 0, 0, 5, &v45);
LABEL_20:
  if ( !a1 )
    goto LABEL_64;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v14 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v15 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v15 == -1) )
    {
      v17 = 0;
    }
    else
    {
      v16 = TlsGetValue(v15);
      v13 = WPP_GLOBAL_Control;
      v17 = v16;
      v14 = gIkeExtGlobals;
    }
    v18 = (__int64)v17 + 8;
    if ( !v17 )
      v18 = 0;
    if ( v14
      && (v19 = (DWORD)v14[86].LockSemaphore, v19 != -1)
      && (v20 = (__int64 *)TlsGetValue(v19), v13 = WPP_GLOBAL_Control, v20) )
    {
      v21 = *v20;
    }
    else
    {
      LODWORD(v21) = 0;
    }
    WPP_SF_iSq(v13[2], 34, (unsigned int)WPP_ee79efc748f53d5223c07ba2e232d700_Traceguids, v21, v18, a1);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v22 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v23 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v23 != -1 )
      {
        v24 = (__int64 *)TlsGetValue(v23);
        if ( v24 )
        {
          v25 = *v24;
          v22 = gIkeExtGlobals;
LABEL_43:
          v43 = v25;
          v51 = &v43;
          v52 = 8;
          if ( !v22 )
            goto LABEL_51;
          v26 = (DWORD)v22[86].LockSemaphore;
          if ( v26 == -1 )
            goto LABEL_51;
          v27 = (char *)TlsGetValue(v26);
          v28 = (const WCHAR *)(v27 + 8);
          if ( !v27 )
            v28 = 0;
          if ( v28 )
          {
            v29 = -1;
            do
              v11 = v28[++v29] == 0;
            while ( !v11 );
            v30 = 2 * v29 + 2;
          }
          else
          {
LABEL_51:
            v28 = &LocaleName;
            v30 = 2;
          }
          v54 = v30;
          v53 = v28;
          v56 = "IkeFreeAcquireContext: Freeing acquire";
          v55 = 0;
          v58 = v63;
          v61 = 4;
          v45 = off_180173280;
          v57 = 39;
          v63[0] = a1;
          v59 = 8;
          v60 = 184549376;
          v62 = 0;
          v46 = *(unsigned __int16 *)off_180173280;
          v48 = &byte_18015AC57;
          v47 = 2;
          v49 = 54;
          v50 = 1;
          EtwEventWriteTransfer(qword_180173298, &v60, 0, 0, 6, &v45);
          goto LABEL_53;
        }
        v22 = gIkeExtGlobals;
      }
    }
    v25 = 0;
    goto LABEL_43;
  }
LABEL_53:
  if ( *(_QWORD *)(a1 + 160) )
  {
    *(_DWORD *)(a1 + 152) = 0;
    WfpMemFree(a1 + 160);
  }
  if ( *(_QWORD *)(a1 + 344) )
  {
    *(_DWORD *)(a1 + 336) = 0;
    WfpMemFree(a1 + 344);
  }
  IkeFreeIpsecId(*(LPVOID *)(a1 + 392));
  v31 = *(void **)(a1 + 400);
  if ( v31 )
    CloseHandle(v31);
  v32 = *(void **)(a1 + 408);
  if ( v32 )
    CloseHandle(v32);
  v33 = *(void **)(a1 + 416);
  if ( v33 )
    CloseHandle(v33);
  WfpMemFree(a1 + 432);
  IkeFreeUMPolicy(*(LPVOID *)(a1 + 384));
  WfpMemFree(v44);
LABEL_64:
  result = (unsigned int)dword_180173278;
  if ( (unsigned int)dword_180173278 <= 5 )
    return result;
  result = qword_180173288;
  if ( (qword_180173288 & 1) == 0 )
    return result;
  result = qword_180173290 & 1;
  if ( result != qword_180173290 )
    return result;
  v35 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_72;
  v36 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v36 == -1 )
    goto LABEL_72;
  v37 = (__int64 *)TlsGetValue(v36);
  if ( !v37 )
  {
    v35 = gIkeExtGlobals;
LABEL_72:
    v38 = 0;
    goto LABEL_73;
  }
  v38 = *v37;
  v35 = gIkeExtGlobals;
LABEL_73:
  v44[0] = v38;
  v51 = v44;
  v52 = 8;
  if ( !v35 )
    goto LABEL_80;
  v39 = (DWORD)v35[86].LockSemaphore;
  if ( v39 == -1 )
    goto LABEL_80;
  v40 = (char *)TlsGetValue(v39);
  v41 = (const WCHAR *)(v40 + 8);
  if ( !v40 )
    v41 = 0;
  if ( v41 )
  {
    do
      v11 = v41[++v2] == 0;
    while ( !v11 );
    v42 = 2 * v2 + 2;
  }
  else
  {
LABEL_80:
    v41 = &LocaleName;
    v42 = 2;
  }
  v61 = 5;
  v45 = off_180173280;
  v53 = v41;
  v54 = v42;
  v55 = 0;
  v56 = "IkeFreeAcquireContext";
  v57 = 22;
  v60 = 184549376;
  v62 = 1;
  v46 = *(unsigned __int16 *)off_180173280;
  v48 = byte_180166E6B;
  v47 = 2;
  v49 = 45;
  v50 = 1;
  return EtwEventWriteTransfer(qword_180173298, &v60, 0, 0, 5, &v45);
}

```

## disassembly

```asm
0x180018240  mov     [rsp-8+arg_18], rbx
0x180018245  push    rbp
0x180018246  push    r12
0x180018248  push    r13
0x18001824a  push    r14
0x18001824c  push    r15
0x18001824e  lea     rbp, [rsp-37h]
0x180018253  sub     rsp, 0E0h
0x18001825a  mov     rax, cs:__security_cookie
0x180018261  xor     rax, rsp
0x180018264  mov     [rbp+57h+var_30], rax
0x180018268  mov     eax, cs:dword_180173278
0x18001826e  lea     r13, aIkefreeacquire_1; "IkeFreeAcquireContext"
0x180018275  xor     r15d, r15d
0x180018278  mov     [rsp+100h+arg_10], rdi
0x180018280  mov     [rbp+57h+var_C0], rcx
0x180018284  mov     rdi, rcx
0x180018287  lea     r14, _TraceLoggingMetadataEnd
0x18001828e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180018295  lea     r12, _TraceLoggingMetadata
0x18001829c  cmp     eax, 5
0x18001829f  jbe     loc_1800183F6
0x1800182a5  mov     rcx, cs:qword_180173290
0x1800182ac  mov     rax, cs:qword_180173288
0x1800182b3  test    al, 1
0x1800182b5  jz      loc_1800183F6
0x1800182bb  mov     rax, rcx
0x1800182be  and     eax, 1
0x1800182c1  cmp     rax, rcx
0x1800182c4  jnz     loc_1800183F6
0x1800182ca  mov     rax, cs:gIkeExtGlobals
0x1800182d1  test    rax, rax
0x1800182d4  jz      short loc_1800182FF
0x1800182d6  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800182dc  cmp     ecx, 0FFFFFFFFh
0x1800182df  jz      short loc_1800182FF
0x1800182e1  call    cs:__imp_TlsGetValue
0x1800182e7  test    rax, rax
0x1800182ea  jz      short loc_1800182F8
0x1800182ec  mov     rcx, [rax]
0x1800182ef  mov     rax, cs:gIkeExtGlobals
0x1800182f6  jmp     short loc_180018302
0x1800182f8  mov     rax, cs:gIkeExtGlobals
0x1800182ff  mov     rcx, r15
0x180018302  mov     [rbp+57h+var_C8], rcx
0x180018306  lea     rcx, [rbp+57h+var_C8]
0x18001830a  mov     [rbp+57h+var_90], rcx
0x18001830e  mov     [rbp+57h+var_88], 8
0x180018316  test    rax, rax
0x180018319  jz      short loc_180018355
0x18001831b  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180018321  cmp     ecx, 0FFFFFFFFh
0x180018324  jz      short loc_180018355
0x180018326  call    cs:__imp_TlsGetValue
0x18001832c  test    rax, rax
0x18001832f  lea     rdx, [rax+8]
0x180018333  cmovz   rdx, r15
0x180018337  test    rdx, rdx
0x18001833a  jz      short loc_180018355
0x18001833c  mov     rax, rbx
0x18001833f  nop
0x180018340  cmp     [rdx+rax*2+2], r15w
0x180018346  lea     rax, [rax+1]
0x18001834a  jnz     short loc_180018340
0x18001834c  lea     eax, ds:2[rax*2]
0x180018353  jmp     short loc_180018361
0x180018355  lea     rdx, LocaleName
0x18001835c  mov     eax, 2
0x180018361  mov     [rbp+57h+var_78], eax
0x180018364  xor     r9d, r9d
0x180018367  movzx   eax, cs:word_180166E9A
0x18001836e  xor     r8d, r8d
0x180018371  mov     dword ptr [rbp+57h+var_40+4], eax
0x180018374  mov     rax, cs:off_180173280
0x18001837b  mov     [rbp+57h+var_B0], rax
0x18001837f  mov     [rbp+57h+var_80], rdx
0x180018383  lea     rdx, [rbp+57h+var_40]
0x180018387  mov     [rbp+57h+var_74], r15d
0x18001838b  mov     [rbp+57h+var_70], r13
0x18001838f  mov     [rbp+57h+var_68], 16h
0x180018397  mov     dword ptr [rbp+57h+var_40], 0B000000h
0x18001839e  mov     [rbp+57h+var_38], 1
0x1800183a6  movzx   eax, word ptr [rax]
0x1800183a9  mov     [rbp+57h+var_A8], eax
0x1800183ac  lea     rax, dword_180166EA4
0x1800183b3  mov     [rbp+57h+var_A0], rax
0x1800183b7  mov     rax, r14
0x1800183ba  sub     eax, r12d
0x1800183bd  mov     [rbp+57h+var_A4], 2
0x1800183c4  mov     [rbp+57h+var_98], 2Dh ; '-'
0x1800183cb  mov     [rbp+57h+var_94], 1
0x1800183d2  mov     [rbp+57h+var_D0], eax
0x1800183d5  mov     eax, [rbp+57h+var_D0]
0x1800183d8  mov     rcx, cs:qword_180173298
0x1800183df  lea     rax, [rbp+57h+var_B0]
0x1800183e3  mov     [rsp+100h+var_D8], rax
0x1800183e8  mov     dword ptr [rsp+100h+var_E0], 5
0x1800183f0  call    cs:__imp_EtwEventWriteTransfer
0x1800183f6  test    rdi, rdi
0x1800183f9  jz      loc_1800186B0
0x1800183ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180018406  lea     rax, WPP_GLOBAL_Control
0x18001840d  cmp     rcx, rax
0x180018410  jz      loc_1800184C5
0x180018416  cmp     byte ptr [rcx+19h], 4
0x18001841a  jb      loc_1800184C5
0x180018420  test    byte ptr [rcx+1Ch], 10h
0x180018424  jz      loc_1800184C5
0x18001842a  mov     rdx, cs:gIkeExtGlobals
0x180018431  mov     [rsp+100h+arg_8], rsi
0x180018439  test    rdx, rdx
0x18001843c  jz      short loc_180018464
0x18001843e  mov     eax, [rdx+0D88h]
0x180018444  cmp     eax, 0FFFFFFFFh
0x180018447  jz      short loc_180018464
0x180018449  mov     ecx, eax; dwTlsIndex
0x18001844b  call    cs:__imp_TlsGetValue
0x180018451  mov     rcx, cs:WPP_GLOBAL_Control
0x180018458  mov     r8, rax
0x18001845b  mov     rdx, cs:gIkeExtGlobals
0x180018462  jmp     short loc_180018467
0x180018464  mov     r8, r15
0x180018467  test    r8, r8
0x18001846a  lea     rsi, [r8+8]
0x18001846e  cmovz   rsi, r15
0x180018472  test    rdx, rdx
0x180018475  jz      short loc_18001849B
0x180018477  mov     eax, [rdx+0D88h]
0x18001847d  cmp     eax, 0FFFFFFFFh
0x180018480  jz      short loc_18001849B
0x180018482  mov     ecx, eax; dwTlsIndex
0x180018484  call    cs:__imp_TlsGetValue
0x18001848a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018491  test    rax, rax
0x180018494  jz      short loc_18001849B
0x180018496  mov     r9, [rax]
0x180018499  jmp     short loc_18001849E
0x18001849b  mov     r9, r15
0x18001849e  mov     rcx, [rcx+10h]
0x1800184a2  lea     r8, WPP_ee79efc748f53d5223c07ba2e232d700_Traceguids
0x1800184a9  mov     edx, 22h ; '"'
0x1800184ae  mov     [rsp+100h+var_D8], rdi
0x1800184b3  mov     [rsp+100h+var_E0], rsi
0x1800184b8  call    WPP_SF_iSq
0x1800184bd  mov     rsi, [rsp+100h+arg_8]
0x1800184c5  mov     eax, cs:dword_180173278
0x1800184cb  cmp     eax, 4
0x1800184ce  jbe     loc_18001861D
0x1800184d4  mov     rax, cs:gIkeExtGlobals
0x1800184db  test    rax, rax
0x1800184de  jz      short loc_180018509
0x1800184e0  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800184e6  cmp     ecx, 0FFFFFFFFh
0x1800184e9  jz      short loc_180018509
0x1800184eb  call    cs:__imp_TlsGetValue
0x1800184f1  test    rax, rax
0x1800184f4  jz      short loc_180018502
0x1800184f6  mov     rcx, [rax]
0x1800184f9  mov     rax, cs:gIkeExtGlobals
0x180018500  jmp     short loc_18001850C
0x180018502  mov     rax, cs:gIkeExtGlobals
0x180018509  mov     rcx, r15
0x18001850c  mov     [rbp+57h+var_C8], rcx
0x180018510  lea     rcx, [rbp+57h+var_C8]
0x180018514  mov     [rbp+57h+var_90], rcx
0x180018518  mov     [rbp+57h+var_88], 8
0x180018520  test    rax, rax
0x180018523  jz      short loc_180018565
0x180018525  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18001852b  cmp     ecx, 0FFFFFFFFh
0x18001852e  jz      short loc_180018565
0x180018530  call    cs:__imp_TlsGetValue
0x180018536  test    rax, rax
0x180018539  lea     rdx, [rax+8]
0x18001853d  cmovz   rdx, r15
0x180018541  test    rdx, rdx
0x180018544  jz      short loc_180018565
0x180018546  mov     rax, rbx
0x180018549  nop     dword ptr [rax+00000000h]
0x180018550  cmp     [rdx+rax*2+2], r15w
0x180018556  lea     rax, [rax+1]
0x18001855a  jnz     short loc_180018550
0x18001855c  lea     eax, ds:2[rax*2]
0x180018563  jmp     short loc_180018571
0x180018565  lea     rdx, LocaleName
0x18001856c  mov     eax, 2
0x180018571  mov     [rbp+57h+var_78], eax
0x180018574  xor     r9d, r9d
0x180018577  mov     [rbp+57h+var_80], rdx
0x18001857b  lea     rax, aIkefreeacquire; "IkeFreeAcquireContext: Freeing acquire"
0x180018582  mov     [rbp+57h+var_70], rax
0x180018586  lea     rdx, [rbp+57h+var_50]
0x18001858a  lea     rax, [rbp+57h+var_40]
0x18001858e  mov     [rbp+57h+var_74], r15d
0x180018592  mov     [rbp+57h+var_60], rax
0x180018596  xor     r8d, r8d
0x180018599  movzx   eax, cs:word_18015AC4D
0x1800185a0  mov     [rbp+57h+var_4C], eax
0x1800185a3  mov     rax, cs:off_180173280
0x1800185aa  mov     [rbp+57h+var_B0], rax
0x1800185ae  mov     [rbp+57h+var_68], 27h ; '''
0x1800185b6  mov     [rbp+57h+var_40], rdi
0x1800185ba  mov     [rbp+57h+var_58], 8
0x1800185c2  mov     [rbp+57h+var_50], 0B000000h
0x1800185c9  mov     [rbp+57h+var_48], r15
0x1800185cd  movzx   eax, word ptr [rax]
0x1800185d0  mov     [rbp+57h+var_A8], eax
0x1800185d3  lea     rax, byte_18015AC57
0x1800185da  mov     [rbp+57h+var_A0], rax
0x1800185de  mov     rax, r14
0x1800185e1  sub     eax, r12d
0x1800185e4  mov     [rbp+57h+var_A4], 2
0x1800185eb  mov     [rbp+57h+var_98], 36h ; '6'
0x1800185f2  mov     [rbp+57h+var_94], 1
0x1800185f9  mov     [rbp+57h+var_D0], eax
0x1800185fc  mov     eax, [rbp+57h+var_D0]
0x1800185ff  mov     rcx, cs:qword_180173298
0x180018606  lea     rax, [rbp+57h+var_B0]
0x18001860a  mov     [rsp+100h+var_D8], rax
0x18001860f  mov     dword ptr [rsp+100h+var_E0], 6
0x180018617  call    cs:__imp_EtwEventWriteTransfer
0x18001861d  lea     rcx, [rdi+0A0h]
0x180018624  cmp     [rcx], r15
0x180018627  jz      short loc_180018635
0x180018629  mov     [rdi+98h], r15d
0x180018630  call    WfpMemFree
0x180018635  lea     rcx, [rdi+158h]
0x18001863c  cmp     [rcx], r15
0x18001863f  jz      short loc_18001864D
0x180018641  mov     [rdi+150h], r15d
0x180018648  call    WfpMemFree
0x18001864d  mov     rcx, [rdi+188h]; lpMem
0x180018654  call    IkeFreeIpsecId
0x180018659  mov     rcx, [rdi+190h]; hObject
0x180018660  test    rcx, rcx
0x180018663  jz      short loc_18001866B
0x180018665  call    cs:__imp_CloseHandle
0x18001866b  mov     rcx, [rdi+198h]; hObject
0x180018672  test    rcx, rcx
0x180018675  jz      short loc_18001867D
0x180018677  call    cs:__imp_CloseHandle
0x18001867d  mov     rcx, [rdi+1A0h]; hObject
0x180018684  test    rcx, rcx
0x180018687  jz      short loc_18001868F
0x180018689  call    cs:__imp_CloseHandle
0x18001868f  lea     rcx, [rdi+1B0h]
0x180018696  call    WfpMemFree
0x18001869b  mov     rcx, [rdi+180h]; lpMem
0x1800186a2  call    IkeFreeUMPolicy
0x1800186a7  lea     rcx, [rbp+57h+var_C0]
0x1800186ab  call    WfpMemFree
0x1800186b0  mov     eax, cs:dword_180173278
0x1800186b6  mov     rdi, [rsp+100h+arg_10]
0x1800186be  cmp     eax, 5
0x1800186c1  jbe     loc_180018814
0x1800186c7  mov     rcx, cs:qword_180173290
0x1800186ce  mov     rax, cs:qword_180173288
0x1800186d5  test    al, 1
0x1800186d7  jz      loc_180018814
0x1800186dd  mov     rax, rcx
0x1800186e0  and     eax, 1
0x1800186e3  cmp     rax, rcx
0x1800186e6  jnz     loc_180018814
0x1800186ec  mov     rax, cs:gIkeExtGlobals
0x1800186f3  test    rax, rax
0x1800186f6  jz      short loc_180018721
0x1800186f8  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800186fe  cmp     ecx, 0FFFFFFFFh
0x180018701  jz      short loc_180018721
0x180018703  call    cs:__imp_TlsGetValue
0x180018709  test    rax, rax
0x18001870c  jz      short loc_18001871A
0x18001870e  mov     rcx, [rax]
0x180018711  mov     rax, cs:gIkeExtGlobals
0x180018718  jmp     short loc_180018724
0x18001871a  mov     rax, cs:gIkeExtGlobals
0x180018721  mov     rcx, r15
0x180018724  mov     [rbp+57h+var_C0], rcx
0x180018728  lea     rcx, [rbp+57h+var_C0]
0x18001872c  mov     [rbp+57h+var_90], rcx
0x180018730  mov     [rbp+57h+var_88], 8
0x180018738  test    rax, rax
0x18001873b  jz      short loc_180018775
0x18001873d  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180018743  cmp     ecx, 0FFFFFFFFh
0x180018746  jz      short loc_180018775
0x180018748  call    cs:__imp_TlsGetValue
0x18001874e  test    rax, rax
0x180018751  lea     rdx, [rax+8]
0x180018755  cmovz   rdx, r15
0x180018759  test    rdx, rdx
0x18001875c  jz      short loc_180018775
0x18001875e  xchg    ax, ax
0x180018760  cmp     [rdx+rbx*2+2], r15w
0x180018766  lea     rbx, [rbx+1]
0x18001876a  jnz     short loc_180018760
0x18001876c  lea     ebx, ds:2[rbx*2]
0x180018773  jmp     short loc_180018781
0x180018775  lea     rdx, LocaleName
0x18001877c  mov     ebx, 2
  ... truncated ...
```
