# SdbGetMatchingExeEx

- ea: `0x180017b80`
- end: `0x180018134`
- name: `SdbGetMatchingExeEx`
- size: `1460`
- prototype: `__int64 __usercall@<rax>(PVOID P@<rcx>, __int64, int, void *)`
- caller_count: `3`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016250`
- `0x180050e20`
- `0x180051234`

## callees

- `0x180002b38`
- `0x180006794`
- `0x18000c43c`
- `0x18000f114`
- `0x180015fb0`
- `0x180017b80`
- `0x180018f20`
- `0x18001aed0`
- `0x18001b068`
- `0x18002b614`
- `0x18002b65c`
- `0x18002c8dc`
- `0x180032468`
- `0x180032b6c`
- `0x1800334ac`
- `0x180033f0c`
- `0x180040f40`
- `0x18004201c`
- `0x18004ec04`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180017d54`
- `ntdll!RtlAllocateHeap` at `0x180017d54`

## string_xrefs

- `0x180017d67`: `Failed to allocate compat layers buffer`
- `0x180017d92`: `__COMPAT_LAYER`
- `0x180017c50`: `Failed to open the database`
- `0x180017cea`: `Failed to create search DB context`
- `0x180017db8`: `Failed to query __COMPAT_LAYER from environment`
- `0x180017e6c`: `Layers in registry cannot exceed %d characters`

## pseudocode

```c
__int64 __fastcall SdbGetMatchingExeEx(
        _QWORD *P,
        __int64 *a2,
        unsigned __int64 a3,
        __int64 a4,
        const WCHAR *a5,
        char a6,
        _DWORD *a7)
{
  _QWORD *inited; // rsi
  unsigned int v9; // ebx
  int v10; // r15d
  int v12; // eax
  PVOID Heap; // r15
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // ecx
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  unsigned int v20; // eax
  int v21; // ecx
  __int64 v22; // [rsp+40h] [rbp-188h] BYREF
  unsigned int v23; // [rsp+48h] [rbp-180h] BYREF
  int v24; // [rsp+4Ch] [rbp-17Ch] BYREF
  int v25; // [rsp+50h] [rbp-178h]
  unsigned int v26; // [rsp+54h] [rbp-174h] BYREF
  unsigned __int64 v27; // [rsp+58h] [rbp-170h] BYREF
  __int64 v28; // [rsp+60h] [rbp-168h] BYREF
  PVOID v29; // [rsp+68h] [rbp-160h]
  PVOID v30; // [rsp+70h] [rbp-158h]
  PCWSTR SourceString; // [rsp+78h] [rbp-150h]
  void *v32; // [rsp+80h] [rbp-148h]
  _QWORD v33[10]; // [rsp+90h] [rbp-138h] BYREF
  int v34; // [rsp+E0h] [rbp-E8h]
  int v35; // [rsp+E4h] [rbp-E4h]
  _BYTE v36[128]; // [rsp+100h] [rbp-C8h] BYREF

  v28 = a4;
  v27 = a3;
  inited = P;
  v30 = P;
  SourceString = a5;
  v32 = a7;
  memset_0(v36, 0, sizeof(v36));
  v9 = 0;
  v23 = 0;
  v10 = 0;
  v25 = 0;
  v22 = 2;
  v24 = 0;
  memset_0(v33, 0, 0x68u);
  v26 = 0;
  memset_0(a7, 0, 0x1C8u);
  if ( !inited )
  {
    inited = (_QWORD *)SdbInitDatabase(1, 0);
    v30 = inited;
    if ( !inited )
    {
      AslLogCallPrintf(1, "SdbGetMatchingExeEx", 5074, "Failed to open the database");
      return 0;
    }
    v10 = 1;
    v25 = 1;
  }
  v12 = AslHardErrorModeDisable(&v26);
  if ( v12 < 0 )
  {
    AslLogCallPrintf(1, "SdbGetMatchingExeEx", 5089, "AslHardErrorModeDisable failed [%x]", v12);
    if ( v10 )
      SdbReleaseDatabase(inited);
    return 0;
  }
  Heap = 0;
  v29 = 0;
  if ( (unsigned int)SdbpCreateSearchDBContext(v33, a2, v27, v28) )
  {
    if ( (a6 & 2) != 0 )
      LODWORD(v33[0]) |= 2u;
    SdbpCloseLocalDatabaseEx(inited, v14, 1);
    if ( (a6 & 1) == 0 && (a6 & 2) == 0 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x202u);
      v29 = Heap;
      if ( !Heap )
      {
        AslLogCallPrintf(1, "SdbGetMatchingExeEx", 5135, "Failed to allocate compat layers buffer");
        goto LABEL_42;
      }
      v16 = AslEnvVarQuery(v28, L"__COMPAT_LAYER", 14, Heap, 257, &v27);
      if ( (int)(v16 + 0x80000000) >= 0 && v16 != -1073741568 )
      {
        AslLogCallPrintf(1, "SdbGetMatchingExeEx", 5146, "Failed to query __COMPAT_LAYER from environment");
        goto LABEL_42;
      }
      if ( v16 >= 0 )
      {
        SdbParseLayerString(inited, Heap, a7, &v23, (char *)&v22 + 4);
        a7[48] |= 0x20u;
        if ( (v22 & 0x200000000LL) != 0 )
          goto LABEL_42;
      }
    }
    if ( (a6 & 2) == 0 )
    {
      v27 = 514;
      if ( (unsigned int)SdbpGetPermLayerKeysWithSignature(SourceString, Heap) )
      {
        SdbParseLayerString(inited, Heap, a7, &v23, (char *)&v22 + 4);
        a7[48] |= 0x10u;
        if ( (v22 & 0x200000000LL) != 0 )
          goto LABEL_42;
      }
      else if ( v27 > 0x202 )
      {
        AslLogCallPrintf(1, "SdbGetMatchingExeEx", 5207, "Layers in registry cannot exceed %d characters", 256);
      }
      LODWORD(v28) = 0;
      while ( (unsigned int)SdbpOpenNthLocalDatabase(inited, v33[5], &v28, 0) )
      {
        v17 = SdbpSearchDB(inited, inited[3], v15, v33, v36, &v22);
        if ( v17 > 0x10 || v17 && (!(unsigned int)SdbpAddMatch(a7, v17, 0, 0, (__int64)&v22) || (_DWORD)v22 != 2) )
          goto LABEL_42;
        SdbpCloseLocalDatabaseEx(inited, v18, 1);
      }
    }
    v19 = inited[2];
    if ( !v19
      || (v20 = SdbpSearchDB(inited, v19, v15, v33, v36, &v22), v20 <= 0x10)
      && (!v20 || (unsigned int)SdbpAddMatch(a7, v20, 0, 0, (__int64)&v22) && (_DWORD)v22 == 2) )
    {
      v21 = SdbpSearchDB(inited, inited[1], v15, v33, v36, &v22);
      if ( (unsigned int)(v21 - 1) <= 0xF )
        SdbpAddMatch(a7, v21, 0, 0, (__int64)&v22);
    }
    goto LABEL_42;
  }
  AslLogCallPrintf(1, "SdbGetMatchingExeEx", 5115, "Failed to create search DB context");
LABEL_42:
  if ( (a6 & 2) == 0 )
    SdbpCaptureCustomSDBInformation(a7, inited);
  a7[40] |= HIDWORD(v22);
  if ( (unsigned int)SdbQueryGetExtraFlags(inited, a7, &v24) )
    a7[48] |= v24;
  if ( v34 )
    a7[48] |= 0x20u;
  if ( v35 )
    a7[48] |= 0x8000u;
  if ( v23 >= 8 )
    AslLogCallPrintf(1, "SdbGetMatchingExeEx", 5389, "Hit max layer limit at %d", v23);
  SdbpReleaseSearchDBContext(v33);
  if ( v25 )
    SdbReleaseDatabase(inited);
  if ( Heap )
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  AslHardErrorModeRestore(v26);
  if ( *a7 || a7[32] )
    return 1;
  return v9;
}

```

## disassembly

```asm
0x180017b80  push    rbx
0x180017b82  push    rsi
0x180017b83  push    rdi
0x180017b84  push    r12
0x180017b86  push    r13
0x180017b88  push    r14
0x180017b8a  push    r15
0x180017b8c  sub     rsp, 190h
0x180017b93  mov     rax, cs:__security_cookie
0x180017b9a  xor     rax, rsp
0x180017b9d  mov     [rsp+1C8h+var_48], rax
0x180017ba5  mov     [rsp+1C8h+var_168], r9
0x180017baa  mov     [rsp+1C8h+var_170], r8
0x180017baf  mov     r12, rdx
0x180017bb2  mov     rsi, rcx
0x180017bb5  mov     [rsp+1C8h+var_158], rcx
0x180017bba  mov     rax, [rsp+1C8h+arg_20]
0x180017bc2  mov     [rsp+1C8h+SourceString], rax
0x180017bc7  mov     rdi, [rsp+1C8h+arg_30]
0x180017bcf  mov     [rsp+1C8h+var_148], rdi
0x180017bd7  xor     edx, edx; Val
0x180017bd9  mov     r8d, 80h; Size
0x180017bdf  lea     rcx, [rsp+1C8h+var_C8]; void *
0x180017be7  call    memset_0
0x180017bec  xor     ebx, ebx
0x180017bee  mov     [rsp+1C8h+var_180], ebx
0x180017bf2  mov     r15d, ebx
0x180017bf5  mov     [rsp+1C8h+var_178], ebx
0x180017bf9  mov     dword ptr [rsp+1C8h+var_188], 2
0x180017c01  mov     dword ptr [rsp+1C8h+var_188+4], ebx
0x180017c05  mov     [rsp+1C8h+var_17C], ebx
0x180017c09  xor     edx, edx; Val
0x180017c0b  lea     r8d, [rbx+68h]; Size
0x180017c0f  lea     rcx, [rsp+1C8h+var_138]; void *
0x180017c17  call    memset_0
0x180017c1c  mov     [rsp+1C8h+var_174], ebx
0x180017c20  xor     edx, edx; Val
0x180017c22  mov     r8d, 1C8h; Size
0x180017c28  mov     rcx, rdi; void *
0x180017c2b  call    memset_0
0x180017c30  lea     r14d, [rbx+1]
0x180017c34  test    rsi, rsi
0x180017c37  jnz     short loc_180017C7B
0x180017c39  xor     edx, edx
0x180017c3b  mov     ecx, r14d
0x180017c3e  call    SdbInitDatabase
0x180017c43  mov     rsi, rax
0x180017c46  mov     [rsp+1C8h+var_158], rax
0x180017c4b  test    rax, rax
0x180017c4e  jnz     short loc_180017C73
0x180017c50  lea     r9, aFailedToOpenTh_0; "Failed to open the database"
0x180017c57  mov     r8d, 13D2h
0x180017c5d  lea     rdx, aSdbgetmatching_0; "SdbGetMatchingExeEx"
0x180017c64  mov     ecx, r14d
0x180017c67  call    AslLogCallPrintf
0x180017c6c  xor     eax, eax
0x180017c6e  jmp     loc_180018111
0x180017c73  mov     r15d, r14d
0x180017c76  mov     [rsp+1C8h+var_178], r14d
0x180017c7b  lea     rcx, [rsp+1C8h+var_174]
0x180017c80  call    AslHardErrorModeDisable
0x180017c85  test    eax, eax
0x180017c87  jns     short loc_180017CB8
0x180017c89  mov     [rsp+1C8h+var_1A8], eax
0x180017c8d  lea     r9, aAslharderrormo_2; "AslHardErrorModeDisable failed [%x]"
0x180017c94  mov     r8d, 13E1h
0x180017c9a  lea     rdx, aSdbgetmatching_0; "SdbGetMatchingExeEx"
0x180017ca1  mov     ecx, r14d
0x180017ca4  call    AslLogCallPrintf
0x180017ca9  test    r15d, r15d
0x180017cac  jz      short loc_180017C6C
0x180017cae  mov     rcx, rsi; P
0x180017cb1  call    SdbReleaseDatabase
0x180017cb6  jmp     short loc_180017C6C
0x180017cb8  mov     r15, rbx
0x180017cbb  mov     [rsp+1C8h+var_160], rbx
0x180017cc0  mov     r13d, dword ptr [rsp+1C8h+arg_28]
0x180017cc8  and     r13d, 2
0x180017ccc  mov     r9, [rsp+1C8h+var_168]
0x180017cd1  mov     r8, [rsp+1C8h+var_170]
0x180017cd6  mov     rdx, r12
0x180017cd9  lea     rcx, [rsp+1C8h+var_138]
0x180017ce1  call    SdbpCreateSearchDBContext
0x180017ce6  test    eax, eax
0x180017ce8  jnz     short loc_180017D0B
0x180017cea  lea     r9, aFailedToCreate_18; "Failed to create search DB context"
0x180017cf1  mov     r8d, 13FBh
0x180017cf7  lea     rdx, aSdbgetmatching_0; "SdbGetMatchingExeEx"
0x180017cfe  mov     ecx, r14d
0x180017d01  call    AslLogCallPrintf
0x180017d06  jmp     loc_180018016
0x180017d0b  test    r13d, r13d
0x180017d0e  jz      short loc_180017D18
0x180017d10  or      [rsp+1C8h+var_138], 2
0x180017d18  mov     r8d, r14d
0x180017d1b  mov     rcx, rsi
0x180017d1e  call    SdbpCloseLocalDatabaseEx
0x180017d23  test    [rsp+1C8h+arg_28], r14b
0x180017d2b  jnz     loc_180017DFE
0x180017d31  test    r13d, r13d
0x180017d34  jnz     loc_180017DFE
0x180017d3a  mov     rcx, gs:60h
0x180017d43  mov     r12d, 202h
0x180017d49  mov     r8d, r12d; Size
0x180017d4c  lea     edx, [r13+8]; Flags
0x180017d50  mov     rcx, [rcx+30h]; HeapHandle
0x180017d54  call    cs:__imp_RtlAllocateHeap
0x180017d5a  mov     r15, rax
0x180017d5d  mov     [rsp+1C8h+var_160], rax
0x180017d62  test    rax, rax
0x180017d65  jnz     short loc_180017D76
0x180017d67  lea     r9, aFailedToAlloca_29; "Failed to allocate compat layers buffer"
0x180017d6e  mov     r8d, 140Fh
0x180017d74  jmp     short loc_180017CF7
0x180017d76  lea     rax, [rsp+1C8h+var_170]
0x180017d7b  mov     [rsp+1C8h+var_1A0], rax
0x180017d80  mov     qword ptr [rsp+1C8h+var_1A8], 101h
0x180017d89  mov     r9, r15
0x180017d8c  mov     r8d, 0Eh
0x180017d92  lea     rdx, aCompatLayer; "__COMPAT_LAYER"
0x180017d99  mov     rcx, [rsp+1C8h+var_168]
0x180017d9e  call    AslEnvVarQuery
0x180017da3  mov     ecx, eax
0x180017da5  mov     edx, 80000000h
0x180017daa  add     eax, edx
0x180017dac  test    edx, eax
0x180017dae  jnz     short loc_180017DCA
0x180017db0  cmp     ecx, 0C0000100h
0x180017db6  jz      short loc_180017DCA
0x180017db8  lea     r9, aFailedToQueryC; "Failed to query __COMPAT_LAYER from env"...
0x180017dbf  mov     r8d, 141Ah
0x180017dc5  jmp     loc_180017CF7
0x180017dca  test    ecx, ecx
0x180017dcc  js      short loc_180017E04
0x180017dce  lea     rax, [rsp+1C8h+var_188+4]
0x180017dd3  mov     qword ptr [rsp+1C8h+var_1A8], rax
0x180017dd8  lea     r9, [rsp+1C8h+var_180]
0x180017ddd  mov     r8, rdi
0x180017de0  mov     rdx, r15
0x180017de3  mov     rcx, rsi
0x180017de6  call    SdbParseLayerString
0x180017deb  or      dword ptr [rdi+0C0h], 20h
0x180017df2  test    byte ptr [rsp+1C8h+var_188+4], 2
0x180017df7  jz      short loc_180017E04
0x180017df9  jmp     loc_180018016
0x180017dfe  mov     r12d, 202h
0x180017e04  test    r13d, r13d
0x180017e07  jnz     loc_180017F3E
0x180017e0d  mov     [rsp+1C8h+var_170], r12
0x180017e12  lea     r9d, [r13+3]
0x180017e16  lea     r8, [rsp+1C8h+var_170]
0x180017e1b  mov     rdx, r15; void *
0x180017e1e  mov     rcx, [rsp+1C8h+SourceString]; SourceString
0x180017e23  call    SdbpGetPermLayerKeysWithSignature
0x180017e28  test    eax, eax
0x180017e2a  jz      short loc_180017E5D
0x180017e2c  lea     rax, [rsp+1C8h+var_188+4]
0x180017e31  mov     qword ptr [rsp+1C8h+var_1A8], rax
0x180017e36  lea     r9, [rsp+1C8h+var_180]
0x180017e3b  mov     r8, rdi
0x180017e3e  mov     rdx, r15
0x180017e41  mov     rcx, rsi
0x180017e44  call    SdbParseLayerString
0x180017e49  or      dword ptr [rdi+0C0h], 10h
0x180017e50  test    byte ptr [rsp+1C8h+var_188+4], 2
0x180017e55  jnz     loc_180018016
0x180017e5b  jmp     short loc_180017E88
0x180017e5d  cmp     [rsp+1C8h+var_170], r12
0x180017e62  jbe     short loc_180017E88
0x180017e64  mov     [rsp+1C8h+var_1A8], 100h
0x180017e6c  lea     r9, aLayersInRegist; "Layers in registry cannot exceed %d cha"...
0x180017e73  mov     r8d, 1457h
0x180017e79  lea     rdx, aSdbgetmatching_0; "SdbGetMatchingExeEx"
0x180017e80  mov     ecx, r14d
0x180017e83  call    AslLogCallPrintf
0x180017e88  test    r13d, r13d
0x180017e8b  jnz     loc_180017F3E
0x180017e91  mov     dword ptr [rsp+1C8h+var_168], ebx
0x180017e95  xor     r9d, r9d
0x180017e98  lea     r8, [rsp+1C8h+var_168]
0x180017e9d  mov     rdx, [rsp+1C8h+var_110]
0x180017ea5  mov     rcx, rsi
0x180017ea8  call    SdbpOpenNthLocalDatabase
0x180017ead  test    eax, eax
0x180017eaf  jz      loc_180017F3E
0x180017eb5  lea     rax, [rsp+1C8h+var_188]
0x180017eba  mov     [rsp+1C8h+var_1A0], rax
0x180017ebf  lea     rax, [rsp+1C8h+var_C8]
0x180017ec7  mov     qword ptr [rsp+1C8h+var_1A8], rax
0x180017ecc  lea     r9, [rsp+1C8h+var_138]
0x180017ed4  mov     rdx, [rsi+18h]
0x180017ed8  mov     rcx, rsi
0x180017edb  call    SdbpSearchDB
0x180017ee0  cmp     eax, 10h
0x180017ee3  ja      loc_180018016
0x180017ee9  test    eax, eax
0x180017eeb  jz      short loc_180017F2E
0x180017eed  lea     rcx, [rsp+1C8h+var_188]
0x180017ef2  mov     [rsp+1C8h+var_190], rcx; __int64
0x180017ef7  mov     [rsp+1C8h+var_198], ebx; int
0x180017efb  mov     [rsp+1C8h+var_1A0], rbx; __int64
0x180017f00  mov     [rsp+1C8h+var_1A8], eax; int
0x180017f04  lea     r9, [rsp+1C8h+var_C8]
0x180017f0c  mov     r8, [rsi+18h]
0x180017f10  mov     rdx, rsi
0x180017f13  mov     rcx, rdi; void *
0x180017f16  call    SdbpAddMatch
0x180017f1b  test    eax, eax
0x180017f1d  jz      loc_180018016
0x180017f23  cmp     dword ptr [rsp+1C8h+var_188], 2
0x180017f28  jnz     loc_180018016
0x180017f2e  mov     r8d, r14d
0x180017f31  mov     rcx, rsi
0x180017f34  call    SdbpCloseLocalDatabaseEx
0x180017f39  jmp     loc_180017E95
0x180017f3e  mov     rdx, [rsi+10h]
0x180017f42  test    rdx, rdx
0x180017f45  jz      short loc_180017FB4
0x180017f47  lea     rax, [rsp+1C8h+var_188]
0x180017f4c  mov     [rsp+1C8h+var_1A0], rax
0x180017f51  lea     rax, [rsp+1C8h+var_C8]
0x180017f59  mov     qword ptr [rsp+1C8h+var_1A8], rax
0x180017f5e  lea     r9, [rsp+1C8h+var_138]
0x180017f66  mov     rcx, rsi
0x180017f69  call    SdbpSearchDB
0x180017f6e  cmp     eax, 10h
0x180017f71  ja      loc_180018016
0x180017f77  test    eax, eax
0x180017f79  jz      short loc_180017FB4
0x180017f7b  lea     rcx, [rsp+1C8h+var_188]
0x180017f80  mov     [rsp+1C8h+var_190], rcx; __int64
0x180017f85  mov     [rsp+1C8h+var_198], ebx; int
0x180017f89  mov     [rsp+1C8h+var_1A0], rbx; __int64
0x180017f8e  mov     [rsp+1C8h+var_1A8], eax; int
0x180017f92  lea     r9, [rsp+1C8h+var_C8]
0x180017f9a  mov     r8, [rsi+10h]
0x180017f9e  mov     rdx, rsi
0x180017fa1  mov     rcx, rdi; void *
0x180017fa4  call    SdbpAddMatch
0x180017fa9  test    eax, eax
0x180017fab  jz      short loc_180018016
0x180017fad  cmp     dword ptr [rsp+1C8h+var_188], 2
0x180017fb2  jnz     short loc_180018016
0x180017fb4  lea     rax, [rsp+1C8h+var_188]
0x180017fb9  mov     [rsp+1C8h+var_1A0], rax
0x180017fbe  lea     rax, [rsp+1C8h+var_C8]
0x180017fc6  mov     qword ptr [rsp+1C8h+var_1A8], rax
0x180017fcb  lea     r9, [rsp+1C8h+var_138]
0x180017fd3  mov     rdx, [rsi+8]
0x180017fd7  mov     rcx, rsi
0x180017fda  call    SdbpSearchDB
0x180017fdf  mov     ecx, eax
0x180017fe1  dec     eax
0x180017fe3  cmp     eax, 0Fh
0x180017fe6  ja      short loc_180018016
0x180017fe8  lea     rax, [rsp+1C8h+var_188]
0x180017fed  mov     [rsp+1C8h+var_190], rax; __int64
0x180017ff2  mov     [rsp+1C8h+var_198], ebx; int
0x180017ff6  mov     [rsp+1C8h+var_1A0], rbx; __int64
0x180017ffb  mov     [rsp+1C8h+var_1A8], ecx; int
0x180017fff  lea     r9, [rsp+1C8h+var_C8]
0x180018007  mov     r8, [rsi+8]
0x18001800b  mov     rdx, rsi
0x18001800e  mov     rcx, rdi; void *
0x180018011  call    SdbpAddMatch
0x180018016  test    r13d, r13d
0x180018019  jnz     short loc_180018026
0x18001801b  mov     rdx, rsi
0x18001801e  mov     rcx, rdi
0x180018021  call    SdbpCaptureCustomSDBInformation
0x180018026  mov     eax, dword ptr [rsp+1C8h+var_188+4]
0x18001802a  or      [rdi+0A0h], eax
0x180018030  lea     r8, [rsp+1C8h+var_17C]
0x180018035  mov     rdx, rdi
0x180018038  mov     rcx, rsi
0x18001803b  call    SdbQueryGetExtraFlags
0x180018040  test    eax, eax
0x180018042  jz      short loc_18001804E
0x180018044  mov     eax, [rsp+1C8h+var_17C]
0x180018048  or      [rdi+0C0h], eax
0x18001804e  cmp     [rsp+1C8h+var_E8], ebx
0x180018055  jz      short loc_18001805E
0x180018057  or      dword ptr [rdi+0C0h], 20h
0x18001805e  cmp     [rsp+1C8h+var_E4], ebx
0x180018065  jz      short loc_18001806F
0x180018067  bts     dword ptr [rdi+0C0h], 0Fh
0x18001806f  jmp     short loc_180018099
0x180018071  xor     edx, edx; Val
0x180018073  mov     r8d, 1C8h; Size
0x180018079  mov     rdi, [rsp+1C8h+var_148]
0x180018081  mov     rcx, rdi; void *
0x180018084  call    memset_0
0x180018089  xor     ebx, ebx
0x18001808b  lea     r14d, [rbx+1]
0x18001808f  mov     r15, [rsp+1C8h+var_160]
0x180018094  mov     rsi, [rsp+1C8h+var_158]
0x180018099  mov     eax, [rsp+1C8h+var_180]
0x18001809d  cmp     eax, 8
0x1800180a0  jb      short loc_1800180C2
0x1800180a2  mov     [rsp+1C8h+var_1A8], eax
  ... truncated ...
```
