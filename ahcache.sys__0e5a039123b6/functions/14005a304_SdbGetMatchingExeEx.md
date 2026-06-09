# SdbGetMatchingExeEx

- ea: `0x14005a304`
- end: `0x14005a8cc`
- name: `SdbGetMatchingExeEx`
- size: `1480`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, void *)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002af6c`
- `0x140059d78`

## callees

- `0x1400079f0`
- `0x140007e40`
- `0x140025d84`
- `0x1400261bc`
- `0x14002e77c`
- `0x140038fd4`
- `0x140039624`
- `0x14003b694`
- `0x14003e364`
- `0x140040d5c`
- `0x140044eb8`
- `0x140045d44`
- `0x140047668`
- `0x1400520dc`
- `0x140053cb4`
- `0x140053d00`
- `0x140053e50`
- `0x1400543f4`
- `0x1400547d8`
- `0x14005498c`
- `0x14005a304`

## string_xrefs

- `0x14005a51f`: `__COMPAT_LAYER`
- `0x14005a480`: `Failed to create search DB context`
- `0x14005a3d2`: `Failed to open the database`
- `0x14005a4f1`: `Failed to allocate compat layers buffer`
- `0x14005a548`: `Failed to query __COMPAT_LAYER from environment`
- `0x14005a604`: `Layers in registry cannot exceed %d characters`

## pseudocode

```c
__int64 __fastcall SdbGetMatchingExeEx(
        _QWORD *a1,
        const wchar_t **a2,
        __int64 a3,
        WCHAR *a4,
        const WCHAR *a5,
        char a6,
        _DWORD *a7)
{
  _QWORD *inited; // rsi
  unsigned int v9; // ebx
  int v10; // r15d
  int v12; // eax
  __int64 v13; // r8
  _WORD *v14; // r15
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // ecx
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  unsigned int v22; // eax
  int v23; // ecx
  __int64 v24; // rcx
  __int64 v25; // [rsp+60h] [rbp-198h] BYREF
  unsigned int v26; // [rsp+68h] [rbp-190h] BYREF
  int v27; // [rsp+6Ch] [rbp-18Ch] BYREF
  int v28; // [rsp+70h] [rbp-188h]
  _DWORD v29[3]; // [rsp+74h] [rbp-184h] BYREF
  WCHAR *v30; // [rsp+80h] [rbp-178h] BYREF
  unsigned __int64 v31; // [rsp+90h] [rbp-168h] BYREF
  _WORD *v32; // [rsp+98h] [rbp-160h]
  _QWORD *v33; // [rsp+A0h] [rbp-158h]
  PCWSTR SourceString; // [rsp+A8h] [rbp-150h]
  void *v35; // [rsp+B0h] [rbp-148h]
  const WCHAR *v36[14]; // [rsp+C0h] [rbp-138h] BYREF
  _BYTE v37[128]; // [rsp+130h] [rbp-C8h] BYREF

  v30 = a4;
  inited = a1;
  v33 = a1;
  SourceString = a5;
  v35 = a7;
  memset(v37, 0, sizeof(v37));
  v9 = 0;
  v26 = 0;
  v10 = 0;
  v28 = 0;
  v25 = 2;
  v27 = 0;
  memset(v36, 0, 0x68u);
  v29[0] = 0;
  memset(a7, 0, 0x1C8u);
  if ( !inited )
  {
    inited = (_QWORD *)SdbInitDatabase();
    v33 = inited;
    if ( !inited )
    {
      AslLogCallPrintf(1, "SdbGetMatchingExeEx", 5074, "Failed to open the database");
      return 0;
    }
    v10 = 1;
    v28 = 1;
  }
  v12 = AslHardErrorModeDisable(v29);
  if ( v12 < 0 )
  {
    AslLogCallPrintf(1, "SdbGetMatchingExeEx", 5089, "AslHardErrorModeDisable failed [%x]", v12);
    if ( v10 )
      SdbReleaseDatabase(inited);
    return 0;
  }
  v14 = 0;
  v32 = 0;
  if ( (unsigned int)SdbpCreateSearchDBContext(v36, a2, v13, (__int64)v30, 0) )
  {
    if ( (a6 & 2) != 0 )
      LODWORD(v36[0]) |= 2u;
    SdbpCloseLocalDatabaseEx(inited, v15, 1);
    if ( (a6 & 1) == 0 && (a6 & 2) == 0 )
    {
      v14 = (_WORD *)AslAlloc(v16, 514, 1);
      v32 = v14;
      if ( !v14 )
      {
        AslLogCallPrintf(1, "SdbGetMatchingExeEx", 5135, "Failed to allocate compat layers buffer");
        goto LABEL_42;
      }
      v18 = AslEnvVarQuery(v30, (char *)L"__COMPAT_LAYER", 0xEu, v14, 0x101u, &v31);
      if ( (int)(v18 + 0x80000000) >= 0 && v18 != -1073741568 )
      {
        AslLogCallPrintf(1, "SdbGetMatchingExeEx", 5146, "Failed to query __COMPAT_LAYER from environment");
        goto LABEL_42;
      }
      if ( v18 >= 0 )
      {
        SdbParseLayerString(inited, v14, a7, &v26, (char *)&v25 + 4);
        a7[48] |= 0x20u;
        if ( (v25 & 0x200000000LL) != 0 )
          goto LABEL_42;
      }
    }
    if ( (a6 & 2) == 0 )
    {
      v31 = 514;
      if ( (unsigned int)SdbpGetPermLayerKeysWithSignature(SourceString, v14) )
      {
        SdbParseLayerString(inited, v14, a7, &v26, (char *)&v25 + 4);
        a7[48] |= 0x10u;
        if ( (v25 & 0x200000000LL) != 0 )
          goto LABEL_42;
      }
      else if ( v31 > 0x202 )
      {
        AslLogCallPrintf(1, "SdbGetMatchingExeEx", 5207, "Layers in registry cannot exceed %d characters", 256);
      }
      LODWORD(v30) = 0;
      while ( (unsigned int)SdbpOpenNthLocalDatabase((__int64)inited, v36[5], &v30, 0) )
      {
        v19 = SdbpSearchDB(inited, inited[3], v17, v36, v37, &v25);
        if ( v19 > 0x10 || v19 && (!(unsigned int)SdbpAddMatch(a7, v19, 0, 0, (__int64)&v25) || (_DWORD)v25 != 2) )
          goto LABEL_42;
        SdbpCloseLocalDatabaseEx(inited, v20, 1);
      }
    }
    v21 = inited[2];
    if ( !v21
      || (v22 = SdbpSearchDB(inited, v21, v17, v36, v37, &v25), v22 <= 0x10)
      && (!v22 || (unsigned int)SdbpAddMatch(a7, v22, 0, 0, (__int64)&v25) && (_DWORD)v25 == 2) )
    {
      v23 = SdbpSearchDB(inited, inited[1], v17, v36, v37, &v25);
      if ( (unsigned int)(v23 - 1) <= 0xF )
        SdbpAddMatch(a7, v23, 0, 0, (__int64)&v25);
    }
    goto LABEL_42;
  }
  AslLogCallPrintf(1, "SdbGetMatchingExeEx", 5115, "Failed to create search DB context");
LABEL_42:
  if ( (a6 & 2) == 0 )
    SdbpCaptureCustomSDBInformation(a7, inited);
  a7[40] |= HIDWORD(v25);
  if ( (unsigned int)SdbQueryGetExtraFlags(inited, a7, &v27) )
    a7[48] |= v27;
  if ( LODWORD(v36[10]) )
    a7[48] |= 0x20u;
  if ( HIDWORD(v36[10]) )
    a7[48] |= 0x8000u;
  if ( v26 >= 8 )
    AslLogCallPrintf(1, "SdbGetMatchingExeEx", 5389, "Hit max layer limit at %d", v26);
  SdbpReleaseSearchDBContext(v36);
  if ( v28 )
    SdbReleaseDatabase(inited);
  if ( v14 )
    AslFree(v24, v14);
  AslHardErrorModeRestore(v29[0]);
  if ( *a7 || a7[32] )
    return 1;
  return v9;
}

```

## disassembly

```asm
0x14005a304  push    rbx
0x14005a306  push    rsi
0x14005a307  push    rdi
0x14005a308  push    r12
0x14005a30a  push    r13
0x14005a30c  push    r14
0x14005a30e  push    r15
0x14005a310  sub     rsp, 1C0h
0x14005a317  mov     rax, cs:__security_cookie
0x14005a31e  xor     rax, rsp
0x14005a321  mov     [rsp+1F8h+var_48], rax
0x14005a329  mov     [rsp+1F8h+var_178], r9
0x14005a331  mov     r12, rdx
0x14005a334  mov     rsi, rcx
0x14005a337  mov     [rsp+1F8h+var_158], rcx
0x14005a33f  mov     rax, [rsp+1F8h+arg_20]
0x14005a347  mov     [rsp+1F8h+SourceString], rax
0x14005a34f  mov     rdi, [rsp+1F8h+arg_30]
0x14005a357  mov     [rsp+1F8h+var_148], rdi
0x14005a35f  xor     edx, edx; Val
0x14005a361  mov     r8d, 80h; Size
0x14005a367  lea     rcx, [rsp+1F8h+var_C8]; void *
0x14005a36f  call    memset
0x14005a374  xor     ebx, ebx
0x14005a376  mov     [rsp+1F8h+var_190], ebx
0x14005a37a  mov     r15d, ebx
0x14005a37d  mov     [rsp+1F8h+var_188], ebx
0x14005a381  mov     dword ptr [rsp+1F8h+var_198], 2
0x14005a389  mov     dword ptr [rsp+1F8h+var_198+4], ebx
0x14005a38d  mov     [rsp+1F8h+var_18C], ebx
0x14005a391  xor     edx, edx; Val
0x14005a393  lea     r8d, [rbx+68h]; Size
0x14005a397  lea     rcx, [rsp+1F8h+var_138]; void *
0x14005a39f  call    memset
0x14005a3a4  mov     [rsp+1F8h+var_184], ebx
0x14005a3a8  xor     edx, edx; Val
0x14005a3aa  mov     r8d, 1C8h; Size
0x14005a3b0  mov     rcx, rdi; void *
0x14005a3b3  call    memset
0x14005a3b8  test    rsi, rsi
0x14005a3bb  jnz     short loc_14005A405
0x14005a3bd  call    SdbInitDatabase
0x14005a3c2  mov     rsi, rax
0x14005a3c5  mov     [rsp+1F8h+var_158], rax
0x14005a3cd  test    rax, rax
0x14005a3d0  jnz     short loc_14005A3F5
0x14005a3d2  lea     r9, aFailedToOpenTh; "Failed to open the database"
0x14005a3d9  mov     r8d, 13D2h
0x14005a3df  lea     rdx, aSdbgetmatching; "SdbGetMatchingExeEx"
0x14005a3e6  lea     ecx, [rbx+1]
0x14005a3e9  call    AslLogCallPrintf
0x14005a3ee  xor     eax, eax
0x14005a3f0  jmp     loc_14005A8A8
0x14005a3f5  mov     r14d, 1
0x14005a3fb  mov     r15d, r14d
0x14005a3fe  mov     [rsp+1F8h+var_188], r14d
0x14005a403  jmp     short loc_14005A40B
0x14005a405  mov     r14d, 1
0x14005a40b  lea     rcx, [rsp+1F8h+var_184]
0x14005a410  call    AslHardErrorModeDisable
0x14005a415  test    eax, eax
0x14005a417  jns     short loc_14005A448
0x14005a419  mov     [rsp+1F8h+var_1D8], eax
0x14005a41d  lea     r9, aAslharderrormo_1; "AslHardErrorModeDisable failed [%x]"
0x14005a424  mov     r8d, 13E1h
0x14005a42a  lea     rdx, aSdbgetmatching; "SdbGetMatchingExeEx"
0x14005a431  mov     ecx, r14d
0x14005a434  call    AslLogCallPrintf
0x14005a439  test    r15d, r15d
0x14005a43c  jz      short loc_14005A3EE
0x14005a43e  mov     rcx, rsi
0x14005a441  call    SdbReleaseDatabase
0x14005a446  jmp     short loc_14005A3EE
0x14005a448  mov     r15, rbx
0x14005a44b  mov     [rsp+1F8h+var_160], rbx
0x14005a453  mov     r13d, dword ptr [rsp+1F8h+arg_28]
0x14005a45b  and     r13d, 2
0x14005a45f  mov     qword ptr [rsp+1F8h+var_1D8], rbx
0x14005a464  mov     r9, [rsp+1F8h+var_178]
0x14005a46c  mov     rdx, r12
0x14005a46f  lea     rcx, [rsp+1F8h+var_138]
0x14005a477  call    SdbpCreateSearchDBContext
0x14005a47c  test    eax, eax
0x14005a47e  jnz     short loc_14005A4A1
0x14005a480  lea     r9, aFailedToCreate_11; "Failed to create search DB context"
0x14005a487  mov     r8d, 13FBh
0x14005a48d  lea     rdx, aSdbgetmatching; "SdbGetMatchingExeEx"
0x14005a494  mov     ecx, r14d
0x14005a497  call    AslLogCallPrintf
0x14005a49c  jmp     loc_14005A7B4
0x14005a4a1  test    r13d, r13d
0x14005a4a4  jz      short loc_14005A4AE
0x14005a4a6  or      [rsp+1F8h+var_138], 2
0x14005a4ae  mov     r8d, r14d
0x14005a4b1  mov     rcx, rsi
0x14005a4b4  call    SdbpCloseLocalDatabaseEx
0x14005a4b9  test    [rsp+1F8h+arg_28], r14b
0x14005a4c1  jnz     loc_14005A58F
0x14005a4c7  test    r13d, r13d
0x14005a4ca  jnz     loc_14005A58F
0x14005a4d0  mov     r8d, r14d
0x14005a4d3  mov     r12d, 202h
0x14005a4d9  mov     edx, r12d
0x14005a4dc  call    AslAlloc
0x14005a4e1  mov     r15, rax
0x14005a4e4  mov     [rsp+1F8h+var_160], rax
0x14005a4ec  test    rax, rax
0x14005a4ef  jnz     short loc_14005A500
0x14005a4f1  lea     r9, aFailedToAlloca_21; "Failed to allocate compat layers buffer"
0x14005a4f8  mov     r8d, 140Fh
0x14005a4fe  jmp     short loc_14005A48D
0x14005a500  lea     rax, [rsp+1F8h+var_168]
0x14005a508  mov     [rsp+1F8h+var_1D0], rax
0x14005a50d  mov     qword ptr [rsp+1F8h+var_1D8], 101h
0x14005a516  mov     r9, r15
0x14005a519  mov     r8d, 0Eh
0x14005a51f  lea     rdx, aCompatLayer; "__COMPAT_LAYER"
0x14005a526  mov     rcx, [rsp+1F8h+var_178]
0x14005a52e  call    AslEnvVarQuery
0x14005a533  mov     ecx, eax
0x14005a535  mov     edx, 80000000h
0x14005a53a  add     eax, edx
0x14005a53c  test    edx, eax
0x14005a53e  jnz     short loc_14005A55A
0x14005a540  cmp     ecx, 0C0000100h
0x14005a546  jz      short loc_14005A55A
0x14005a548  lea     r9, aFailedToQueryC; "Failed to query __COMPAT_LAYER from env"...
0x14005a54f  mov     r8d, 141Ah
0x14005a555  jmp     loc_14005A48D
0x14005a55a  test    ecx, ecx
0x14005a55c  js      short loc_14005A595
0x14005a55e  lea     rax, [rsp+1F8h+var_198+4]
0x14005a563  mov     qword ptr [rsp+1F8h+var_1D8], rax
0x14005a568  lea     r9, [rsp+1F8h+var_190]
0x14005a56d  mov     r8, rdi
0x14005a570  mov     rdx, r15
0x14005a573  mov     rcx, rsi
0x14005a576  call    SdbParseLayerString
0x14005a57b  or      dword ptr [rdi+0C0h], 20h
0x14005a582  test    byte ptr [rsp+1F8h+var_198+4], 2
0x14005a587  jnz     loc_14005A7B4
0x14005a58d  jmp     short loc_14005A595
0x14005a58f  mov     r12d, 202h
0x14005a595  test    r13d, r13d
0x14005a598  jnz     loc_14005A6DC
0x14005a59e  mov     [rsp+1F8h+var_168], r12
0x14005a5a6  lea     r8, [rsp+1F8h+var_168]
0x14005a5ae  mov     rdx, r15; void *
0x14005a5b1  mov     rcx, [rsp+1F8h+SourceString]; SourceString
0x14005a5b9  call    SdbpGetPermLayerKeysWithSignature
0x14005a5be  test    eax, eax
0x14005a5c0  jz      short loc_14005A5F2
0x14005a5c2  lea     rax, [rsp+1F8h+var_198+4]
0x14005a5c7  mov     qword ptr [rsp+1F8h+var_1D8], rax
0x14005a5cc  lea     r9, [rsp+1F8h+var_190]
0x14005a5d1  mov     r8, rdi
0x14005a5d4  mov     rdx, r15
0x14005a5d7  mov     rcx, rsi
0x14005a5da  call    SdbParseLayerString
0x14005a5df  or      dword ptr [rdi+0C0h], 10h
0x14005a5e6  test    byte ptr [rsp+1F8h+var_198+4], 2
0x14005a5eb  jz      short loc_14005A620
0x14005a5ed  jmp     loc_14005A7B4
0x14005a5f2  cmp     [rsp+1F8h+var_168], r12
0x14005a5fa  jbe     short loc_14005A620
0x14005a5fc  mov     [rsp+1F8h+var_1D8], 100h
0x14005a604  lea     r9, aLayersInRegist; "Layers in registry cannot exceed %d cha"...
0x14005a60b  mov     r8d, 1457h
0x14005a611  lea     rdx, aSdbgetmatching; "SdbGetMatchingExeEx"
0x14005a618  mov     ecx, r14d
0x14005a61b  call    AslLogCallPrintf
0x14005a620  test    r13d, r13d
0x14005a623  jnz     loc_14005A6DC
0x14005a629  mov     dword ptr [rsp+1F8h+var_178], ebx
0x14005a630  xor     r9d, r9d
0x14005a633  lea     r8, [rsp+1F8h+var_178]
0x14005a63b  mov     rdx, [rsp+1F8h+var_110]
0x14005a643  mov     rcx, rsi
0x14005a646  call    SdbpOpenNthLocalDatabase
0x14005a64b  test    eax, eax
0x14005a64d  jz      loc_14005A6DC
0x14005a653  lea     rax, [rsp+1F8h+var_198]
0x14005a658  mov     [rsp+1F8h+var_1D0], rax
0x14005a65d  lea     rax, [rsp+1F8h+var_C8]
0x14005a665  mov     qword ptr [rsp+1F8h+var_1D8], rax
0x14005a66a  lea     r9, [rsp+1F8h+var_138]
0x14005a672  mov     rdx, [rsi+18h]
0x14005a676  mov     rcx, rsi
0x14005a679  call    SdbpSearchDB
0x14005a67e  cmp     eax, 10h
0x14005a681  ja      loc_14005A7B4
0x14005a687  test    eax, eax
0x14005a689  jz      short loc_14005A6CC
0x14005a68b  lea     rcx, [rsp+1F8h+var_198]
0x14005a690  mov     [rsp+1F8h+var_1C0], rcx; __int64
0x14005a695  mov     [rsp+1F8h+var_1C8], ebx; int
0x14005a699  mov     [rsp+1F8h+var_1D0], rbx; __int64
0x14005a69e  mov     [rsp+1F8h+var_1D8], eax; int
0x14005a6a2  lea     r9, [rsp+1F8h+var_C8]
0x14005a6aa  mov     r8, [rsi+18h]
0x14005a6ae  mov     rdx, rsi
0x14005a6b1  mov     rcx, rdi; void *
0x14005a6b4  call    SdbpAddMatch
0x14005a6b9  test    eax, eax
0x14005a6bb  jz      loc_14005A7B4
0x14005a6c1  cmp     dword ptr [rsp+1F8h+var_198], 2
0x14005a6c6  jnz     loc_14005A7B4
0x14005a6cc  mov     r8d, r14d
0x14005a6cf  mov     rcx, rsi
0x14005a6d2  call    SdbpCloseLocalDatabaseEx
0x14005a6d7  jmp     loc_14005A630
0x14005a6dc  mov     rdx, [rsi+10h]
0x14005a6e0  test    rdx, rdx
0x14005a6e3  jz      short loc_14005A752
0x14005a6e5  lea     rax, [rsp+1F8h+var_198]
0x14005a6ea  mov     [rsp+1F8h+var_1D0], rax
0x14005a6ef  lea     rax, [rsp+1F8h+var_C8]
0x14005a6f7  mov     qword ptr [rsp+1F8h+var_1D8], rax
0x14005a6fc  lea     r9, [rsp+1F8h+var_138]
0x14005a704  mov     rcx, rsi
0x14005a707  call    SdbpSearchDB
0x14005a70c  cmp     eax, 10h
0x14005a70f  ja      loc_14005A7B4
0x14005a715  test    eax, eax
0x14005a717  jz      short loc_14005A752
0x14005a719  lea     rcx, [rsp+1F8h+var_198]
0x14005a71e  mov     [rsp+1F8h+var_1C0], rcx; __int64
0x14005a723  mov     [rsp+1F8h+var_1C8], ebx; int
0x14005a727  mov     [rsp+1F8h+var_1D0], rbx; __int64
0x14005a72c  mov     [rsp+1F8h+var_1D8], eax; int
0x14005a730  lea     r9, [rsp+1F8h+var_C8]
0x14005a738  mov     r8, [rsi+10h]
0x14005a73c  mov     rdx, rsi
0x14005a73f  mov     rcx, rdi; void *
0x14005a742  call    SdbpAddMatch
0x14005a747  test    eax, eax
0x14005a749  jz      short loc_14005A7B4
0x14005a74b  cmp     dword ptr [rsp+1F8h+var_198], 2
0x14005a750  jnz     short loc_14005A7B4
0x14005a752  lea     rax, [rsp+1F8h+var_198]
0x14005a757  mov     [rsp+1F8h+var_1D0], rax
0x14005a75c  lea     rax, [rsp+1F8h+var_C8]
0x14005a764  mov     qword ptr [rsp+1F8h+var_1D8], rax
0x14005a769  lea     r9, [rsp+1F8h+var_138]
0x14005a771  mov     rdx, [rsi+8]
0x14005a775  mov     rcx, rsi
0x14005a778  call    SdbpSearchDB
0x14005a77d  mov     ecx, eax
0x14005a77f  dec     eax
0x14005a781  cmp     eax, 0Fh
0x14005a784  ja      short loc_14005A7B4
0x14005a786  lea     rax, [rsp+1F8h+var_198]
0x14005a78b  mov     [rsp+1F8h+var_1C0], rax; __int64
0x14005a790  mov     [rsp+1F8h+var_1C8], ebx; int
0x14005a794  mov     [rsp+1F8h+var_1D0], rbx; __int64
0x14005a799  mov     [rsp+1F8h+var_1D8], ecx; int
0x14005a79d  lea     r9, [rsp+1F8h+var_C8]
0x14005a7a5  mov     r8, [rsi+8]
0x14005a7a9  mov     rdx, rsi
0x14005a7ac  mov     rcx, rdi; void *
0x14005a7af  call    SdbpAddMatch
0x14005a7b4  test    r13d, r13d
0x14005a7b7  jnz     short loc_14005A7C4
0x14005a7b9  mov     rdx, rsi
0x14005a7bc  mov     rcx, rdi
0x14005a7bf  call    SdbpCaptureCustomSDBInformation
0x14005a7c4  mov     eax, dword ptr [rsp+1F8h+var_198+4]
0x14005a7c8  or      [rdi+0A0h], eax
0x14005a7ce  lea     r8, [rsp+1F8h+var_18C]
0x14005a7d3  mov     rdx, rdi
0x14005a7d6  mov     rcx, rsi
0x14005a7d9  call    SdbQueryGetExtraFlags
0x14005a7de  test    eax, eax
0x14005a7e0  jz      short loc_14005A7EC
0x14005a7e2  mov     eax, [rsp+1F8h+var_18C]
0x14005a7e6  or      [rdi+0C0h], eax
0x14005a7ec  cmp     [rsp+1F8h+var_E8], ebx
0x14005a7f3  jz      short loc_14005A7FC
0x14005a7f5  or      dword ptr [rdi+0C0h], 20h
0x14005a7fc  cmp     [rsp+1F8h+var_E4], ebx
0x14005a803  jz      short loc_14005A80D
0x14005a805  bts     dword ptr [rdi+0C0h], 0Fh
0x14005a80d  jmp     short loc_14005A83D
0x14005a80f  xor     edx, edx; Val
0x14005a811  mov     r8d, 1C8h; Size
0x14005a817  mov     rdi, [rsp+1F8h+var_148]
0x14005a81f  mov     rcx, rdi; void *
0x14005a822  call    memset
0x14005a827  xor     ebx, ebx
0x14005a829  lea     r14d, [rbx+1]
0x14005a82d  mov     r15, [rsp+1F8h+var_160]
0x14005a835  mov     rsi, [rsp+1F8h+var_158]
0x14005a83d  mov     eax, [rsp+1F8h+var_190]
0x14005a841  cmp     eax, 8
0x14005a844  jb      short loc_14005A866
0x14005a846  mov     [rsp+1F8h+var_1D8], eax
0x14005a84a  lea     r9, aHitMaxLayerLim; "Hit max layer limit at %d"
0x14005a851  mov     r8d, 150Dh
0x14005a857  lea     rdx, aSdbgetmatching; "SdbGetMatchingExeEx"
0x14005a85e  mov     ecx, r14d
  ... truncated ...
```
