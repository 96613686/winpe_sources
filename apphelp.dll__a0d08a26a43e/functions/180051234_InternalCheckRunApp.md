# InternalCheckRunApp

- ea: `0x180051234`
- end: `0x1800517c5`
- name: `InternalCheckRunApp`
- size: `1425`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `reparse_path, loader_planting`

## callers

- `0x18003aa00`
- `0x1800506a0`
- `0x180050730`

## callees

- `0x180002be0`
- `0x180009720`
- `0x18000f114`
- `0x180015a6c`
- `0x180015e8c`
- `0x180015fb0`
- `0x180017b80`
- `0x18003ab2c`
- `0x18003acf4`
- `0x18003b3e4`
- `0x18003d070`
- `0x180040ac0`
- `0x180041490`
- `0x180051044`
- `0x180051234`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800513ff`
- `ntdll!RtlFreeHeap` at `0x180051776`
- `ntdll!RtlFreeHeap` at `0x1800513ff`
- `ntdll!RtlFreeHeap` at `0x180051776`
- `ntdll!RtlAllocateHeap` at `0x1800513a3`
- `ntdll!RtlAllocateHeap` at `0x18005141f`
- `ntdll!RtlAllocateHeap` at `0x1800513a3`
- `ntdll!RtlAllocateHeap` at `0x18005141f`

## string_xrefs

- `0x1800513b1`: `Failed to allocate path`
- `0x18005147e`: `Failed to convert path '%S' to DOS on first attempt [%x]`
- `0x180051450`: `Failed to convert path '%S' to DOS on second attempt [%x]`
- `0x180051542`: `Failed to create file mapping`

## pseudocode

```c
__int64 __fastcall InternalCheckRunApp(
        const wchar_t *a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const WCHAR *a4,
        WCHAR *a5,
        __int64 a6,
        unsigned __int16 a7,
        __int64 a8,
        _QWORD *a9,
        _DWORD *a10,
        _DWORD *a11,
        _QWORD *a12,
        _DWORD *a13,
        int a14,
        unsigned __int64 a15,
        wchar_t *a16,
        __int64 a17,
        _DWORD *a18,
        _QWORD *a19,
        _DWORD *a20)
{
  _WORD *inited; // rbx
  unsigned int v22; // r15d
  const wchar_t **v23; // r14
  struct _PEB *v24; // rcx
  _DWORD *v25; // rdi
  WCHAR *Heap; // rax
  WCHAR *v27; // r13
  int v28; // eax
  WCHAR *v29; // rax
  const char *v30; // r9
  __int64 v31; // r8
  int v32; // ecx
  int v33; // r8d
  _DWORD *v34; // r15
  _QWORD *v35; // r15
  _DWORD *v36; // r15
  __int64 v37; // rdx
  int v38; // ecx
  int v39; // eax
  int v41; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v42; // [rsp+44h] [rbp-BCh]
  unsigned int v43; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t **v44; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v46; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v47; // [rsp+64h] [rbp-9Ch] BYREF
  wchar_t *v48; // [rsp+68h] [rbp-98h]
  _QWORD *v49; // [rsp+70h] [rbp-90h]
  const wchar_t *v50; // [rsp+78h] [rbp-88h]
  const wchar_t *v51; // [rsp+80h] [rbp-80h]
  const wchar_t *v52; // [rsp+88h] [rbp-78h]
  WCHAR *v53; // [rsp+90h] [rbp-70h]
  unsigned __int64 v54; // [rsp+98h] [rbp-68h]
  _DWORD *v55; // [rsp+A0h] [rbp-60h]
  _QWORD *v56; // [rsp+A8h] [rbp-58h]
  _DWORD *v57; // [rsp+B0h] [rbp-50h]
  _QWORD *v58; // [rsp+B8h] [rbp-48h]
  _DWORD *v59; // [rsp+C0h] [rbp-40h]
  __int64 v60; // [rsp+C8h] [rbp-38h]
  _BYTE v61[4]; // [rsp+D0h] [rbp-30h] BYREF
  int v62; // [rsp+D4h] [rbp-2Ch]
  _BYTE v63[464]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR v64[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  inited = 0;
  v53 = a5;
  v22 = 1;
  v42 = a7;
  v58 = a9;
  v59 = a10;
  v55 = a11;
  v56 = a12;
  v57 = a13;
  v54 = a15;
  v48 = a16;
  v50 = a3;
  v51 = a2;
  v52 = a1;
  v60 = a17;
  v49 = a19;
  memset_0(v63, 0, 0x1C8u);
  v23 = 0;
  v44 = 0;
  memset_0(v64, 0, 0x208u);
  memset_0(v61, 0, 0x50u);
  v46 = 0;
  v47 = 0;
  v45 = 0;
  v41 = 0;
  if ( a19 )
    *a19 = 0;
  if ( v48 )
    *v48 = 0;
  if ( a18 )
    memset_0(a18, 0, 0x58u);
  v24 = NtCurrentPeb();
  v25 = v63;
  v43 = 260;
  if ( a20 )
    v25 = a20;
  Heap = (WCHAR *)RtlAllocateHeap(v24->ProcessHeap, 8u, 0x208u);
  v27 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "InternalCheckRunApp", 277, "Failed to allocate path");
    goto LABEL_62;
  }
  v28 = ConvertNtPathToDosPath(a4, Heap, &v43);
  if ( v28 != -1073741789 )
  {
    if ( v28 < 0 )
    {
      v30 = "Failed to convert path '%S' to DOS on first attempt [%x]";
      v31 = 308;
      goto LABEL_17;
    }
LABEL_20:
    v32 = (v25[48] >> 10) & 8 | 0x10;
    if ( (v25[48] & 0x4000) == 0 )
      v32 = (v25[48] >> 10) & 8;
    inited = SdbInitDatabaseEx(v32, 0, v42);
    if ( v49 )
      *v49 = inited;
    if ( inited )
    {
      if ( v25[42] > 0x10u || v25[43] > 8u )
        AslLogCallPrintf(1, "SdbIsValidQueryResultLight", 6112, "Corrupt QueryResult");
      if ( (int)AslFileMappingCreate(&v44, v27, v52, v51, v50) >= 0 )
      {
        if ( (int)AslPathBuildSignature((__int64)v64, 0x104u, (__int64)v27) >= 0 )
        {
          v23 = v44;
          SdbGetMatchingExeEx(inited, v44, v54, v53, v64, 0, v25);
          v34 = v55;
          if ( v55 )
          {
            SdbQueryFlagMask((_DWORD)inited, (_DWORD)v25, 20494, (unsigned int)&v45, 0);
            *v34 = v45;
          }
          v35 = v56;
          if ( v56 )
          {
            SdbQueryFlagMask((_DWORD)inited, (_DWORD)v25, 20496, (unsigned int)&v45, 0);
            *v35 = v45;
          }
          v36 = v57;
          if ( v57 )
          {
            SdbQueryFlagMask((_DWORD)inited, (_DWORD)v25, 20497, (unsigned int)&v45, 0);
            *v36 = v45;
          }
          ParseSdbQueryResult(
            (_DWORD)inited,
            (_DWORD)v25,
            v33,
            (unsigned int)&v46,
            (__int64)&v41,
            (__int64)v61,
            (__int64)&v47);
          v37 = v46;
          if ( v46 )
          {
            v38 = v62;
            if ( v62 == 1 || v62 == 2 || v62 == 3 || v62 == 4 || v62 == 7 )
            {
              v39 = v41 & 4;
              if ( a18 )
                a18[1] = v62;
              if ( v39 )
              {
                if ( v38 == 2 )
                {
                  v22 = 0;
                  goto LABEL_61;
                }
              }
              else
              {
                v25[41] = v37;
                if ( a18 )
                {
                  v44 = 0;
                  v41 = 0;
                  if ( (unsigned int)SdbTagRefToTagID(inited, v37, &v44, &v41) )
                  {
                    if ( (unsigned int)SdbGetDatabaseGUID(inited, v44, a18 + 9) )
                      a18[8] = v41;
                  }
                }
              }
            }
            else
            {
              AslLogCallPrintf(1, "InternalCheckRunApp", 459, "Unhandled severity flag 0x%x", v62);
            }
          }
          if ( v58 && v47 )
            GetExeSxsData((__int64)inited, v47, v58, v59);
          v22 = 1;
          if ( a14 )
            GetExeNTVDMData((__int64)inited, (__int64)v25, v48, v60);
          goto LABEL_61;
        }
        AslLogCallPrintf(1, "InternalCheckRunApp", 347, "Failed to build exe signature");
      }
      else
      {
        AslLogCallPrintf(1, "InternalCheckRunApp", 341, "Failed to create file mapping");
      }
      v23 = v44;
    }
    else
    {
      AslLogCallPrintf(1, "InternalCheckRunApp", 326, "Failed to initialize the database");
    }
LABEL_61:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v27);
    goto LABEL_62;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v27);
  v29 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * v43);
  v27 = v29;
  if ( v29 )
  {
    v28 = ConvertNtPathToDosPath(a4, v29, &v43);
    if ( v28 < 0 )
    {
      v30 = "Failed to convert path '%S' to DOS on second attempt [%x]";
      v31 = 304;
LABEL_17:
      AslLogCallPrintf(1, "InternalCheckRunApp", v31, v30, a4, v28);
      goto LABEL_61;
    }
    goto LABEL_20;
  }
  AslLogCallPrintf(1, "InternalCheckRunApp", 297, "Out of memory");
LABEL_62:
  if ( !a14 && inited )
    SdbReleaseDatabase(inited);
  if ( v23 )
    AslFileMappingDelete((__int64)v23);
  return v22;
}

```

## disassembly

```asm
0x180051234  push    rbp
0x180051236  push    rbx
0x180051237  push    rsi
0x180051238  push    rdi
0x180051239  push    r12
0x18005123b  push    r13
0x18005123d  push    r14
0x18005123f  push    r15
0x180051241  lea     rbp, [rsp-418h]
0x180051249  sub     rsp, 518h
0x180051250  mov     rax, cs:__security_cookie
0x180051257  xor     rax, rsp
0x18005125a  mov     [rbp+450h+var_50], rax
0x180051261  mov     rax, [rbp+450h+arg_20]
0x180051268  xor     ebx, ebx
0x18005126a  mov     rdi, [rbp+450h+arg_90]
0x180051271  mov     r12, r9
0x180051274  mov     r13, [rbp+450h+arg_98]
0x18005127b  mov     rsi, [rbp+450h+arg_88]
0x180051282  mov     [rbp+450h+var_4C0], rax
0x180051286  lea     r15d, [rbx+1]
0x18005128a  movzx   eax, [rbp+450h+arg_30]
0x180051291  mov     [rsp+550h+var_50C], ax
0x180051296  mov     rax, [rbp+450h+arg_40]
0x18005129d  mov     [rbp+450h+var_498], rax
0x1800512a1  mov     rax, [rbp+450h+arg_48]
0x1800512a8  mov     [rbp+450h+var_490], rax
0x1800512ac  mov     rax, [rbp+450h+arg_50]
0x1800512b3  mov     [rbp+450h+var_4B0], rax
0x1800512b7  mov     rax, [rbp+450h+arg_58]
0x1800512be  mov     [rbp+450h+var_4A8], rax
0x1800512c2  mov     rax, [rbp+450h+arg_60]
0x1800512c9  mov     [rbp+450h+var_4A0], rax
0x1800512cd  mov     rax, [rbp+450h+arg_70]
0x1800512d4  mov     [rbp+450h+var_4B8], rax
0x1800512d8  mov     rax, [rbp+450h+arg_78]
0x1800512df  mov     [rsp+550h+var_4E8], rax
0x1800512e4  mov     rax, [rbp+450h+arg_80]
0x1800512eb  mov     [rsp+550h+var_4D8], r8
0x1800512f0  mov     r8d, 1C8h; Size
0x1800512f6  mov     [rbp+450h+var_4D0], rdx
0x1800512fa  xor     edx, edx; Val
0x1800512fc  mov     [rbp+450h+var_4C8], rcx
0x180051300  lea     rcx, [rbp+450h+var_430]; void *
0x180051304  mov     [rbp+450h+var_488], rax
0x180051308  mov     [rsp+550h+var_4E0], rdi
0x18005130d  call    memset_0
0x180051312  xor     r14d, r14d
0x180051315  lea     rcx, [rbp+450h+var_260]; void *
0x18005131c  xor     edx, edx; Val
0x18005131e  mov     [rsp+550h+var_500], r14
0x180051323  mov     r8d, 208h; Size
0x180051329  call    memset_0
0x18005132e  xor     edx, edx; Val
0x180051330  lea     r8d, [rbx+50h]; Size
0x180051334  lea     rcx, [rbp+450h+var_480]; void *
0x180051338  call    memset_0
0x18005133d  xor     edx, edx; Val
0x18005133f  mov     [rsp+550h+var_4F0], edx
0x180051343  mov     [rsp+550h+var_4EC], edx
0x180051347  mov     [rsp+550h+var_4F8], rdx
0x18005134c  mov     [rsp+550h+var_510], edx
0x180051350  test    rdi, rdi
0x180051353  jz      short loc_180051358
0x180051355  mov     [rdi], rdx
0x180051358  mov     rcx, [rsp+550h+var_4E8]
0x18005135d  test    rcx, rcx
0x180051360  jz      short loc_180051365
0x180051362  mov     [rcx], dx
0x180051365  test    rsi, rsi
0x180051368  jz      short loc_180051378
0x18005136a  mov     r8d, 58h ; 'X'; Size
0x180051370  mov     rcx, rsi; void *
0x180051373  call    memset_0
0x180051378  mov     rcx, gs:60h
0x180051381  lea     rdi, [rbp+450h+var_430]
0x180051385  test    r13, r13
0x180051388  mov     [rsp+550h+var_508], 104h
0x180051390  mov     edx, 8; Flags
0x180051395  mov     r8d, 208h; Size
0x18005139b  cmovnz  rdi, r13
0x18005139f  mov     rcx, [rcx+30h]; HeapHandle
0x1800513a3  call    cs:__imp_RtlAllocateHeap
0x1800513a9  mov     r13, rax
0x1800513ac  test    rax, rax
0x1800513af  jnz     short loc_1800513D2
0x1800513b1  lea     r9, aFailedToAlloca_1; "Failed to allocate path"
0x1800513b8  mov     r8d, 115h
0x1800513be  lea     rdx, aInternalcheckr; "InternalCheckRunApp"
0x1800513c5  mov     ecx, r15d
0x1800513c8  call    AslLogCallPrintf
0x1800513cd  jmp     loc_18005177C
0x1800513d2  lea     r8, [rsp+550h+var_508]
0x1800513d7  mov     rdx, r13; void *
0x1800513da  mov     rcx, r12; SourceString
0x1800513dd  call    ConvertNtPathToDosPath
0x1800513e2  cmp     eax, 0C0000023h
0x1800513e7  jnz     loc_18005147A
0x1800513ed  mov     rcx, gs:60h
0x1800513f6  mov     r8, r13; P
0x1800513f9  xor     edx, edx; Flags
0x1800513fb  mov     rcx, [rcx+30h]; HeapHandle
0x1800513ff  call    cs:__imp_RtlFreeHeap
0x180051405  mov     rcx, gs:60h
0x18005140e  mov     edx, 8; Flags
0x180051413  mov     r8d, [rsp+550h+var_508]
0x180051418  add     r8, r8; Size
0x18005141b  mov     rcx, [rcx+30h]; HeapHandle
0x18005141f  call    cs:__imp_RtlAllocateHeap
0x180051425  mov     r13, rax
0x180051428  test    rax, rax
0x18005142b  jnz     short loc_18005143C
0x18005142d  lea     r9, aOutOfMemory; "Out of memory"
0x180051434  mov     r8d, 129h
0x18005143a  jmp     short loc_1800513BE
0x18005143c  lea     r8, [rsp+550h+var_508]
0x180051441  mov     rdx, rax; void *
0x180051444  mov     rcx, r12; SourceString
0x180051447  call    ConvertNtPathToDosPath
0x18005144c  test    eax, eax
0x18005144e  jns     short loc_18005148D
0x180051450  lea     r9, aFailedToConver_19; "Failed to convert path '%S' to DOS on s"...
0x180051457  mov     r8d, 130h
0x18005145d  mov     [rsp+550h+var_528], eax
0x180051461  lea     rdx, aInternalcheckr; "InternalCheckRunApp"
0x180051468  mov     ecx, r15d
0x18005146b  mov     [rsp+550h+var_530], r12
0x180051470  call    AslLogCallPrintf
0x180051475  jmp     loc_180051764
0x18005147a  test    eax, eax
0x18005147c  jns     short loc_18005148D
0x18005147e  lea     r9, aFailedToConver_12; "Failed to convert path '%S' to DOS on f"...
0x180051485  mov     r8d, 134h
0x18005148b  jmp     short loc_18005145D
0x18005148d  mov     edx, [rdi+0C0h]
0x180051493  xor     r12d, r12d
0x180051496  movzx   r8d, [rsp+550h+var_50C]
0x18005149c  shr     edx, 0Ah
0x18005149f  and     edx, 8
0x1800514a2  mov     ecx, edx
0x1800514a4  or      ecx, 10h
0x1800514a7  test    dword ptr [rdi+0C0h], 4000h
0x1800514b1  cmovz   ecx, edx
0x1800514b4  xor     edx, edx
0x1800514b6  call    SdbInitDatabaseEx
0x1800514bb  mov     rbx, rax
0x1800514be  mov     rax, [rsp+550h+var_4E0]
0x1800514c3  test    rax, rax
0x1800514c6  jz      short loc_1800514CB
0x1800514c8  mov     [rax], rbx
0x1800514cb  test    rbx, rbx
0x1800514ce  jnz     short loc_1800514F1
0x1800514d0  lea     r9, aFailedToInitia_5; "Failed to initialize the database"
0x1800514d7  mov     r8d, 146h
0x1800514dd  lea     rdx, aInternalcheckr; "InternalCheckRunApp"
0x1800514e4  mov     ecx, r15d
0x1800514e7  call    AslLogCallPrintf
0x1800514ec  jmp     loc_180051764
0x1800514f1  cmp     dword ptr [rdi+0A8h], 10h
0x1800514f8  ja      short loc_180051503
0x1800514fa  cmp     dword ptr [rdi+0ACh], 8
0x180051501  jbe     short loc_18005151F
0x180051503  lea     r9, aCorruptQueryre; "Corrupt QueryResult"
0x18005150a  mov     r8d, 17E0h
0x180051510  lea     rdx, aSdbisvalidquer; "SdbIsValidQueryResultLight"
0x180051517  mov     ecx, r15d
0x18005151a  call    AslLogCallPrintf
0x18005151f  mov     rax, [rsp+550h+var_4D8]
0x180051524  lea     rcx, [rsp+550h+var_500]
0x180051529  mov     r9, [rbp+450h+var_4D0]
0x18005152d  mov     rdx, r13
0x180051530  mov     r8, [rbp+450h+var_4C8]
0x180051534  mov     [rsp+550h+var_530], rax
0x180051539  call    AslFileMappingCreate
0x18005153e  test    eax, eax
0x180051540  jns     short loc_180051568
0x180051542  lea     r9, aFailedToCreate_24; "Failed to create file mapping"
0x180051549  mov     r8d, 155h
0x18005154f  lea     rdx, aInternalcheckr; "InternalCheckRunApp"
0x180051556  mov     ecx, r15d
0x180051559  call    AslLogCallPrintf
0x18005155e  mov     r14, [rsp+550h+var_500]
0x180051563  jmp     loc_180051764
0x180051568  mov     r8, r13
0x18005156b  lea     rcx, [rbp+450h+var_260]
0x180051572  mov     edx, 104h
0x180051577  call    AslPathBuildSignature
0x18005157c  test    eax, eax
0x18005157e  jns     short loc_18005158F
0x180051580  lea     r9, aFailedToBuildE; "Failed to build exe signature"
0x180051587  mov     r8d, 15Bh
0x18005158d  jmp     short loc_18005154F
0x18005158f  mov     r14, [rsp+550h+var_500]
0x180051594  lea     rax, [rbp+450h+var_260]
0x18005159b  mov     r9, [rbp+450h+var_4C0]
0x18005159f  mov     rdx, r14
0x1800515a2  mov     r8, [rbp+450h+var_4B8]
0x1800515a6  mov     rcx, rbx; P
0x1800515a9  mov     [rsp+550h+var_520], rdi; void *
0x1800515ae  mov     [rsp+550h+var_528], r12d; int
0x1800515b3  mov     [rsp+550h+var_530], rax; __int64
0x1800515b8  call    SdbGetMatchingExeEx
0x1800515bd  mov     r15, [rbp+450h+var_4B0]
0x1800515c1  test    r15, r15
0x1800515c4  jz      short loc_1800515E8
0x1800515c6  mov     r8d, 500Eh
0x1800515cc  mov     [rsp+550h+var_530], r12
0x1800515d1  lea     r9, [rsp+550h+var_4F8]
0x1800515d6  mov     rdx, rdi
0x1800515d9  mov     rcx, rbx
0x1800515dc  call    SdbQueryFlagMask
0x1800515e1  mov     eax, dword ptr [rsp+550h+var_4F8]
0x1800515e5  mov     [r15], eax
0x1800515e8  mov     r15, [rbp+450h+var_4A8]
0x1800515ec  test    r15, r15
0x1800515ef  jz      short loc_180051614
0x1800515f1  mov     r8d, 5010h
0x1800515f7  mov     [rsp+550h+var_530], r12
0x1800515fc  lea     r9, [rsp+550h+var_4F8]
0x180051601  mov     rdx, rdi
0x180051604  mov     rcx, rbx
0x180051607  call    SdbQueryFlagMask
0x18005160c  mov     rax, [rsp+550h+var_4F8]
0x180051611  mov     [r15], rax
0x180051614  mov     r15, [rbp+450h+var_4A0]
0x180051618  test    r15, r15
0x18005161b  jz      short loc_18005163F
0x18005161d  mov     r8d, 5011h
0x180051623  mov     [rsp+550h+var_530], r12
0x180051628  lea     r9, [rsp+550h+var_4F8]
0x18005162d  mov     rdx, rdi
0x180051630  mov     rcx, rbx
0x180051633  call    SdbQueryFlagMask
0x180051638  mov     eax, dword ptr [rsp+550h+var_4F8]
0x18005163c  mov     [r15], eax
0x18005163f  lea     rax, [rsp+550h+var_4EC]
0x180051644  mov     rdx, rdi
0x180051647  mov     [rsp+550h+var_520], rax
0x18005164c  lea     r9, [rsp+550h+var_4F0]
0x180051651  lea     rax, [rbp+450h+var_480]
0x180051655  mov     rcx, rbx
0x180051658  mov     qword ptr [rsp+550h+var_528], rax
0x18005165d  lea     rax, [rsp+550h+var_510]
0x180051662  mov     [rsp+550h+var_530], rax
0x180051667  call    ParseSdbQueryResult
0x18005166c  mov     edx, [rsp+550h+var_4F0]
0x180051670  test    edx, edx
0x180051672  jz      loc_180051721
0x180051678  mov     ecx, [rbp+450h+var_47C]
0x18005167b  mov     eax, ecx
0x18005167d  sub     eax, 1
0x180051680  jz      short loc_1800516BA
0x180051682  sub     eax, 1
0x180051685  jz      short loc_1800516BA
0x180051687  sub     eax, 1
0x18005168a  jz      short loc_1800516BA
0x18005168c  sub     eax, 1
0x18005168f  jz      short loc_1800516BA
0x180051691  cmp     eax, 3
0x180051694  jz      short loc_1800516BA
0x180051696  mov     dword ptr [rsp+550h+var_530], ecx
0x18005169a  lea     r9, aUnhandledSever; "Unhandled severity flag 0x%x"
0x1800516a1  mov     ecx, 1
0x1800516a6  lea     rdx, aInternalcheckr; "InternalCheckRunApp"
0x1800516ad  mov     r8d, 1CBh
0x1800516b3  call    AslLogCallPrintf
0x1800516b8  jmp     short loc_180051721
0x1800516ba  mov     eax, [rsp+550h+var_510]
0x1800516be  and     eax, 4
0x1800516c1  test    rsi, rsi
0x1800516c4  jz      short loc_1800516C9
0x1800516c6  mov     [rsi+4], ecx
0x1800516c9  test    eax, eax
0x1800516cb  jz      short loc_1800516DA
0x1800516cd  cmp     ecx, 2
0x1800516d0  jnz     short loc_180051721
0x1800516d2  mov     r15d, r12d
0x1800516d5  jmp     loc_180051764
0x1800516da  mov     [rdi+0A4h], edx
0x1800516e0  test    rsi, rsi
0x1800516e3  jz      short loc_180051721
0x1800516e5  lea     r9, [rsp+550h+var_510]
0x1800516ea  mov     [rsp+550h+var_500], r12
0x1800516ef  lea     r8, [rsp+550h+var_500]
0x1800516f4  mov     [rsp+550h+var_510], r12d
0x1800516f9  mov     rcx, rbx
0x1800516fc  call    SdbTagRefToTagID
0x180051701  test    eax, eax
0x180051703  jz      short loc_180051721
0x180051705  mov     rdx, [rsp+550h+var_500]
0x18005170a  lea     r8, [rsi+24h]
0x18005170e  mov     rcx, rbx
0x180051711  call    SdbGetDatabaseGUID
0x180051716  test    eax, eax
0x180051718  jz      short loc_180051721
0x18005171a  mov     eax, [rsp+550h+var_510]
0x18005171e  mov     [rsi+20h], eax
0x180051721  mov     rax, [rbp+450h+var_498]
0x180051725  test    rax, rax
0x180051728  jz      short loc_180051741
  ... truncated ...
```
