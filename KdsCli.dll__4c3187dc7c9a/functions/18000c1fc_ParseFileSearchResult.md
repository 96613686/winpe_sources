# ParseFileSearchResult

- ea: `0x18000c1fc`
- end: `0x18000c5f8`
- name: `ParseFileSearchResult`
- size: `1020`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, _QWORD *, unsigned int, unsigned int, unsigned int, int, int, __int64, _DWORD *, void **, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000aef0`

## callees

- `0x18000bfd8`
- `0x18000c1fc`
- `0x180010270`
- `0x180010920`
- `0x180010950`
- `0x180010a94`
- `0x18001a450`
- `0x18001a6ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c396`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c34b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c34b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4c7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000c341`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000c341`
- `CRYPT32!CryptUnprotectData` at `0x18000c4bd`
- `CRYPT32!CryptUnprotectData` at `0x18000c4bd`

## string_xrefs

- `0x18000c280`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000c2b4`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`

## pseudocode

```c
__int64 __fastcall ParseFileSearchResult(
        const WCHAR *a1,
        __int64 a2,
        _QWORD *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        int a8,
        __int64 a9,
        _DWORD *a10,
        void **a11,
        _DWORD *a12)
{
  int v12; // r12d
  _DWORD *v13; // rsi
  unsigned int v15; // ebx
  int v16; // r14d
  signed int IntervalStartTime; // eax
  signed int LastError; // edi
  int v19; // r15d
  signed int v20; // eax
  DWORD v21; // eax
  _BYTE *v22; // rcx
  __int64 v23; // rax
  unsigned int v25; // r12d
  signed int v26; // eax
  unsigned int v28; // r9d
  __int64 v29; // r13
  char *v30; // rax
  char *v31; // r12
  void *v32; // rcx
  __int64 v33; // rdx
  _BYTE *v34; // rax
  int v35; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v36; // [rsp+44h] [rbp-3Ch] BYREF
  void *Src; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int64 v38[2]; // [rsp+50h] [rbp-30h] BYREF
  HLOCAL hMem[2]; // [rsp+60h] [rbp-20h] BYREF
  DATA_BLOB pDataIn; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v42; // [rsp+CCh] [rbp+4Ch]
  int v44; // [rsp+108h] [rbp+88h]

  v42 = HIDWORD(a2);
  v12 = (int)a1;
  v13 = 0;
  Src = 0;
  v15 = a2;
  v36 = 0;
  v38[0] = 0;
  v16 = 0;
  v35 = 0;
  pDataIn = 0;
  *(_OWORD *)hMem = 0;
  IntervalStartTime = GetIntervalStartTime(0x53D1AC1000uLL, a4, a5, a6, v38);
  LastError = IntervalStartTime;
  if ( IntervalStartTime < 0 )
  {
    SidKeyDebugTraceError(
      IntervalStartTime,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      0x41Fu);
    *a10 = 0;
    goto LABEL_10;
  }
  v19 = 0;
  v38[1] = __PAIR64__(v42, v15);
  if ( __PAIR64__(v42, v15) < v38[0] )
  {
LABEL_7:
    *a10 = v16;
    if ( !v19 )
      goto LABEL_10;
    goto LABEL_8;
  }
  v20 = IsSIDKeyFound(v12, a5, a6, a8, a9, (__int64)&v35, (__int64)&Src, (__int64)&v36);
  LastError = v20;
  if ( v20 < 0 )
  {
    SidKeyDebugTraceError(v20, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx", 0x434u);
    v16 = v35;
    LOBYTE(v19) = LastError == -2146893821;
LABEL_6:
    v13 = Src;
    goto LABEL_7;
  }
  v16 = v35;
  if ( !v35 )
    goto LABEL_6;
  v13 = Src;
  v25 = v36;
  v26 = ValidateSIDKey((const struct _SID_KEY_HEADER *)Src, v36, 0);
  LastError = v26;
  if ( v26 < 0 )
  {
    SidKeyDebugTraceError(v26, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx", 0x44Au);
    LOBYTE(v19) = LastError == -2146893821;
    goto LABEL_7;
  }
  if ( v13[3] != a4 || a3 && (*((_QWORD *)v13 + 3) != *a3 || *((_QWORD *)v13 + 4) != a3[1]) || a7 != (v13[2] & 1) )
  {
    v28 = 1112;
    goto LABEL_32;
  }
  pDataIn.cbData = v25 - v13[19] - v13[18] - v13[13] - v13[12] - v13[11] - v13[10] - 80;
  pDataIn.pbData = (BYTE *)v13
                 + v13[11]
                 + v13[12]
                 + v13[13]
                 + (unsigned int)v13[18]
                 + (unsigned __int64)(unsigned int)v13[19]
                 + (unsigned int)v13[10]
                 + 80;
  if ( !CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 0, (DATA_BLOB *)hMem) )
  {
    LastError = GetLastError();
    SidKeyDebugTraceError(
      LastError,
      "dwReturn",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      0x479u);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_29;
  }
  if ( LODWORD(hMem[0]) != v13[16] + v13[17] )
  {
    v28 = 1153;
LABEL_32:
    LastError = -2146893821;
    SidKeyDebugTraceError(
      0x80090003,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      v28);
    *a10 = v16;
LABEL_8:
    if ( !DeleteFileW(a1) )
    {
      v21 = GetLastError();
      SidKeyDebugTraceError(
        v21,
        "dwReturn",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
        0x4AFu);
    }
    goto LABEL_10;
  }
  v29 = (unsigned int)(v13[11] + v13[12] + v13[13] + v13[18] + v13[19] + v13[10] + 80);
  v44 = LODWORD(hMem[0]) + v29;
  v30 = (char *)SIDKeyProvAlloc((unsigned int)(LODWORD(hMem[0]) + v29));
  v31 = v30;
  if ( !v30 )
  {
    LastError = -2147024882;
    SidKeyDebugTraceError(
      0x8007000E,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      0x493u);
LABEL_29:
    *a10 = v16;
    goto LABEL_10;
  }
  memcpy_0(v30, v13, (unsigned int)v29);
  memcpy_0(&v31[v29], hMem[1], LODWORD(hMem[0]));
  v32 = *a11;
  if ( *a11 )
  {
    v33 = (unsigned int)*a12;
    v34 = *a11;
    if ( *a12 )
    {
      do
      {
        *v34++ = 0;
        --v33;
      }
      while ( v33 );
    }
    SIDKeyProvFree(v32);
  }
  *a12 = v44;
  *a11 = v31;
  *a10 = 1;
LABEL_10:
  if ( v13 )
    SIDKeyProvFree(v13);
  v22 = hMem[1];
  if ( hMem[1] )
  {
    v23 = LODWORD(hMem[0]);
    if ( LODWORD(hMem[0]) )
    {
      do
      {
        *v22++ = 0;
        --v23;
      }
      while ( v23 );
      v22 = hMem[1];
    }
    LocalFree(v22);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000c1fc  mov     rax, rsp
0x18000c1ff  mov     [rax+18h], rbx
0x18000c203  mov     [rax+20h], r9d
0x18000c207  mov     [rax+10h], rdx
0x18000c20b  mov     [rax+8], rcx
0x18000c20f  push    rbp
0x18000c210  push    rsi
0x18000c211  push    rdi
0x18000c212  push    r12
0x18000c214  push    r13
0x18000c216  push    r14
0x18000c218  push    r15
0x18000c21a  mov     rbp, rsp
0x18000c21d  sub     rsp, 80h
0x18000c224  mov     r12, rcx
0x18000c227  mov     eax, r9d
0x18000c22a  mov     r9d, [rbp+arg_28]; unsigned int
0x18000c22e  lea     rcx, [rbp+var_30]
0x18000c232  xor     esi, esi
0x18000c234  mov     [rsp+80h+pPromptStruct], rcx; unsigned __int64 *
0x18000c239  mov     r13, r8
0x18000c23c  mov     [rbp+Src], rsi
0x18000c240  mov     r8d, [rbp+arg_20]; unsigned int
0x18000c244  mov     rbx, rdx
0x18000c247  xorps   xmm0, xmm0
0x18000c24a  mov     [rbp+var_3C], esi
0x18000c24d  xorps   xmm1, xmm1
0x18000c250  mov     [rbp+var_30], rsi
0x18000c254  xor     r14d, r14d
0x18000c257  mov     rcx, 53D1AC1000h; unsigned __int64
0x18000c261  mov     edx, eax; unsigned int
0x18000c263  mov     [rbp+var_40], r14d
0x18000c267  movups  xmmword ptr [rbp+pDataIn.cbData], xmm0
0x18000c26b  movups  xmmword ptr [rbp+hMem], xmm1
0x18000c26f  call    ?GetIntervalStartTime@@YAJ_KKKKPEA_K@Z; GetIntervalStartTime(unsigned __int64,ulong,ulong,ulong,unsigned __int64 *)
0x18000c274  mov     edi, eax
0x18000c276  test    eax, eax
0x18000c278  jns     short loc_18000C2A4
0x18000c27a  mov     r9d, 41Fh; unsigned int
0x18000c280  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000c287  lea     rdx, aHr; "hr"
0x18000c28e  mov     ecx, eax; unsigned int
0x18000c290  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000c295  mov     rcx, [rbp+arg_48]
0x18000c29c  mov     [rcx], r14d
0x18000c29f  jmp     loc_18000C368
0x18000c2a4  mov     eax, [rbp+arg_C]
0x18000c2a7  xor     r15d, r15d
0x18000c2aa  mov     dword ptr [rbp+var_28+4], eax
0x18000c2ad  mov     rax, [rbp+var_30]
0x18000c2b1  mov     dword ptr [rbp+var_28], ebx
0x18000c2b4  lea     rbx, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000c2bb  cmp     [rbp+var_28], rax
0x18000c2bf  jb      short loc_18000C32E
0x18000c2c1  mov     r9d, [rbp+arg_38]
0x18000c2c5  lea     rax, [rbp+var_3C]
0x18000c2c9  mov     r8d, [rbp+arg_28]
0x18000c2cd  mov     rcx, r12
0x18000c2d0  mov     edx, [rbp+arg_20]
0x18000c2d3  mov     [rsp+80h+var_48], rax
0x18000c2d8  lea     rax, [rbp+Src]
0x18000c2dc  mov     [rsp+80h+pDataOut], rax
0x18000c2e1  lea     rax, [rbp+var_40]
0x18000c2e5  mov     qword ptr [rsp+80h+dwFlags], rax
0x18000c2ea  mov     rax, [rbp+arg_40]
0x18000c2f1  mov     [rsp+80h+pPromptStruct], rax
0x18000c2f6  call    IsSIDKeyFound
0x18000c2fb  mov     edi, eax
0x18000c2fd  test    eax, eax
0x18000c2ff  jns     loc_18000C3B9
0x18000c305  mov     r9d, 434h; unsigned int
0x18000c30b  lea     rdx, aHr; "hr"
0x18000c312  mov     r8, rbx; char *
0x18000c315  mov     ecx, eax; unsigned int
0x18000c317  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000c31c  mov     r14d, [rbp+var_40]
0x18000c320  cmp     edi, 80090003h
0x18000c326  setz    r15b
0x18000c32a  mov     rsi, [rbp+Src]
0x18000c32e  mov     rax, [rbp+arg_48]
0x18000c335  mov     [rax], r14d
0x18000c338  test    r15d, r15d
0x18000c33b  jz      short loc_18000C368
0x18000c33d  mov     rcx, [rbp+lpFileName]; lpFileName
0x18000c341  call    cs:__imp_DeleteFileW
0x18000c347  test    eax, eax
0x18000c349  jnz     short loc_18000C368
0x18000c34b  call    cs:__imp_GetLastError
0x18000c351  mov     r9d, 4AFh; unsigned int
0x18000c357  lea     rdx, aDwreturn; "dwReturn"
0x18000c35e  mov     ecx, eax; unsigned int
0x18000c360  mov     r8, rbx; char *
0x18000c363  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000c368  test    rsi, rsi
0x18000c36b  jz      short loc_18000C375
0x18000c36d  mov     rcx, rsi; lpMem
0x18000c370  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000c375  mov     rcx, [rbp+hMem+8]
0x18000c379  test    rcx, rcx
0x18000c37c  jz      short loc_18000C39C
0x18000c37e  mov     eax, dword ptr [rbp+hMem]
0x18000c381  test    rax, rax
0x18000c384  jz      short loc_18000C396
0x18000c386  mov     byte ptr [rcx], 0
0x18000c389  inc     rcx
0x18000c38c  sub     rax, 1
0x18000c390  jnz     short loc_18000C386
0x18000c392  mov     rcx, [rbp+hMem+8]; hMem
0x18000c396  call    cs:__imp_LocalFree
0x18000c39c  mov     rbx, [rsp+80h+arg_10]
0x18000c3a4  mov     eax, edi
0x18000c3a6  add     rsp, 80h
0x18000c3ad  pop     r15
0x18000c3af  pop     r14
0x18000c3b1  pop     r13
0x18000c3b3  pop     r12
0x18000c3b5  pop     rdi
0x18000c3b6  pop     rsi
0x18000c3b7  pop     rbp
0x18000c3b8  retn
0x18000c3b9  mov     r14d, [rbp+var_40]
0x18000c3bd  test    r14d, r14d
0x18000c3c0  jz      loc_18000C32A
0x18000c3c6  mov     rsi, [rbp+Src]
0x18000c3ca  xor     r8d, r8d; int
0x18000c3cd  mov     r12d, [rbp+var_3C]
0x18000c3d1  mov     rcx, rsi; struct _SID_KEY_HEADER *
0x18000c3d4  mov     edx, r12d; unsigned int
0x18000c3d7  call    ?ValidateSIDKey@@YAJPEBU_SID_KEY_HEADER@@KH@Z; ValidateSIDKey(_SID_KEY_HEADER const *,ulong,int)
0x18000c3dc  mov     edi, eax
0x18000c3de  test    eax, eax
0x18000c3e0  jns     short loc_18000C408
0x18000c3e2  mov     r9d, 44Ah; unsigned int
0x18000c3e8  lea     rdx, aHr; "hr"
0x18000c3ef  mov     r8, rbx; char *
0x18000c3f2  mov     ecx, eax; unsigned int
0x18000c3f4  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000c3f9  cmp     edi, 80090003h
0x18000c3ff  setz    r15b
0x18000c403  jmp     loc_18000C32E
0x18000c408  mov     eax, [rbp+arg_18]
0x18000c40b  mov     r15, [rbp+arg_48]
0x18000c412  cmp     [rsi+0Ch], eax
0x18000c415  jnz     loc_18000C5ED
0x18000c41b  test    r13, r13
0x18000c41e  jz      short loc_18000C43C
0x18000c420  mov     rax, [rsi+18h]
0x18000c424  cmp     rax, [r13+0]
0x18000c428  jnz     loc_18000C5ED
0x18000c42e  mov     rax, [rsi+20h]
0x18000c432  cmp     rax, [r13+8]
0x18000c436  jnz     loc_18000C5ED
0x18000c43c  mov     eax, [rsi+8]
0x18000c43f  and     eax, 1
0x18000c442  cmp     [rbp+arg_30], eax
0x18000c445  jnz     loc_18000C5ED
0x18000c44b  sub     r12d, [rsi+4Ch]
0x18000c44f  xor     r9d, r9d; pvReserved
0x18000c452  sub     r12d, [rsi+48h]
0x18000c456  xor     r8d, r8d; pOptionalEntropy
0x18000c459  sub     r12d, [rsi+34h]
0x18000c45d  sub     r12d, [rsi+30h]
0x18000c461  sub     r12d, [rsi+2Ch]
0x18000c465  sub     r12d, [rsi+28h]
0x18000c469  sub     r12d, 50h ; 'P'
0x18000c46d  mov     [rbp+pDataIn.cbData], r12d
0x18000c471  mov     eax, [rsi+48h]
0x18000c474  mov     edx, [rsi+4Ch]
0x18000c477  mov     ecx, [rsi+2Ch]
0x18000c47a  add     rdx, rax
0x18000c47d  mov     eax, [rsi+34h]
0x18000c480  add     rcx, rsi
0x18000c483  add     rdx, rax
0x18000c486  mov     eax, [rsi+30h]
0x18000c489  add     rdx, rax
0x18000c48c  mov     eax, [rsi+28h]
0x18000c48f  add     rcx, rdx
0x18000c492  add     rax, 50h ; 'P'
0x18000c496  add     rax, rcx
0x18000c499  xor     edx, edx; ppszDataDescr
0x18000c49b  mov     [rbp+pDataIn.pbData], rax
0x18000c49f  lea     rcx, [rbp+pDataIn]; pDataIn
0x18000c4a3  lea     rax, [rbp+hMem]
0x18000c4a7  mov     [rsp+80h+pDataOut], rax; pDataOut
0x18000c4ac  mov     [rsp+80h+dwFlags], 0; dwFlags
0x18000c4b4  mov     [rsp+80h+pPromptStruct], 0; pPromptStruct
0x18000c4bd  call    cs:__imp_CryptUnprotectData
0x18000c4c3  test    eax, eax
0x18000c4c5  jnz     short loc_18000C4FB
0x18000c4c7  call    cs:__imp_GetLastError
0x18000c4cd  mov     r9d, 479h; unsigned int
0x18000c4d3  lea     rdx, aDwreturn; "dwReturn"
0x18000c4da  mov     ecx, eax; unsigned int
0x18000c4dc  mov     r8, rbx; char *
0x18000c4df  mov     edi, eax
0x18000c4e1  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000c4e6  test    edi, edi
0x18000c4e8  jle     short loc_18000C4F3
0x18000c4ea  movzx   edi, di
0x18000c4ed  or      edi, 80070000h
0x18000c4f3  mov     [r15], r14d
0x18000c4f6  jmp     loc_18000C368
0x18000c4fb  mov     eax, [rsi+44h]
0x18000c4fe  add     eax, [rsi+40h]
0x18000c501  mov     edx, dword ptr [rbp+hMem]
0x18000c504  cmp     edx, eax
0x18000c506  jz      short loc_18000C52F
0x18000c508  mov     r9d, 481h; unsigned int
0x18000c50e  mov     r8, rbx; char *
0x18000c511  lea     rdx, aHr; "hr"
0x18000c518  mov     ecx, 80090003h; unsigned int
0x18000c51d  mov     edi, 80090003h
0x18000c522  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000c527  mov     [r15], r14d
0x18000c52a  jmp     loc_18000C33D
0x18000c52f  mov     ecx, [rsi+4Ch]
0x18000c532  add     ecx, [rsi+48h]
0x18000c535  add     ecx, [rsi+34h]
0x18000c538  add     ecx, [rsi+30h]
0x18000c53b  add     ecx, [rsi+2Ch]
0x18000c53e  mov     r13d, [rsi+28h]
0x18000c542  add     r13d, 50h ; 'P'
0x18000c546  add     r13d, ecx
0x18000c549  lea     eax, [rdx+r13]
0x18000c54d  mov     ecx, eax; unsigned __int64
0x18000c54f  mov     dword ptr [rbp+arg_48], eax
0x18000c555  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000c55a  mov     r12, rax
0x18000c55d  test    rax, rax
0x18000c560  jnz     short loc_18000C586
0x18000c562  mov     r9d, 493h; unsigned int
0x18000c568  lea     rdx, aHr; "hr"
0x18000c56f  mov     r8, rbx; char *
0x18000c572  mov     ecx, 8007000Eh; unsigned int
0x18000c577  mov     edi, 8007000Eh
0x18000c57c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000c581  jmp     loc_18000C4F3
0x18000c586  mov     r8d, r13d; Size
0x18000c589  mov     rdx, rsi; Src
0x18000c58c  mov     rcx, r12; void *
0x18000c58f  call    memcpy_0
0x18000c594  mov     r8d, dword ptr [rbp+hMem]; Size
0x18000c598  lea     rcx, [r12+r13]; void *
0x18000c59c  mov     rdx, [rbp+hMem+8]; Src
0x18000c5a0  call    memcpy_0
0x18000c5a5  mov     r14, [rbp+arg_50]
0x18000c5ac  mov     rbx, [rbp+arg_58]
0x18000c5b3  mov     rcx, [r14]; lpMem
0x18000c5b6  test    rcx, rcx
0x18000c5b9  jz      short loc_18000C5D6
0x18000c5bb  mov     edx, [rbx]
0x18000c5bd  mov     rax, rcx
0x18000c5c0  test    rdx, rdx
0x18000c5c3  jz      short loc_18000C5D1
0x18000c5c5  mov     byte ptr [rax], 0
0x18000c5c8  inc     rax
0x18000c5cb  sub     rdx, 1
0x18000c5cf  jnz     short loc_18000C5C5
0x18000c5d1  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000c5d6  mov     eax, dword ptr [rbp+arg_48]
0x18000c5dc  mov     [rbx], eax
0x18000c5de  mov     [r14], r12
0x18000c5e1  mov     dword ptr [r15], 1
0x18000c5e8  jmp     loc_18000C368
0x18000c5ed  mov     r9d, 458h
0x18000c5f3  jmp     loc_18000C50E
```
