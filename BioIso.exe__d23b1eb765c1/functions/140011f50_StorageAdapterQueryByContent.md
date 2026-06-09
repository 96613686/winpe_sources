# StorageAdapterQueryByContent

- ea: `0x140011f50`
- end: `0x140012452`
- name: `StorageAdapterQueryByContent`
- size: `1282`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000a2e4`
- `0x14000a420`
- `0x14001101c`
- `0x140011b1c`
- `0x140011f50`
- `0x14001bd40`
- `0x14001cb90`
- `0x140058624`
- `0x140058734`
- `0x14005c8c8`
- `0x1400631d0`
- `0x1400633d4`
- `0x140063760`
- `0x14007dc3c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001218b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400121f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400122b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001232a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012378`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001218b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400121f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400122b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001232a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012378`

## string_xrefs

- `0x140011fa5`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140011fd6`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14001201c`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14001204a`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400120bb`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140012166`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400121ce`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14001228b`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140012305`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400123a3`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400123e6`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14001240b`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall StorageAdapterQueryByContent(__int64 a1, char a2, __int64 a3, unsigned __int64 a4)
{
  __int64 v6; // r14
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // r15
  int FileHeader; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdi
  union _LARGE_INTEGER v13; // rbx
  char v14; // r13
  __int64 v15; // rax
  __int64 v16; // r8
  _QWORD *v17; // rsi
  int RecordHeader; // eax
  unsigned int v19; // edi
  HLOCAL v20; // rcx
  __int64 v21; // rcx
  HLOCAL v22; // rcx
  char *v23; // rdx
  char v24; // r8
  char v25; // al
  unsigned __int64 i; // rcx
  union _LARGE_INTEGER v27; // r8
  struct _LOCK_BOX_RECORD_HEADER *v28; // rdx
  int v29; // eax
  HLOCAL v30; // rcx
  int v31; // [rsp+20h] [rbp-118h]
  HLOCAL hMem; // [rsp+28h] [rbp-110h] BYREF
  __int64 v33; // [rsp+30h] [rbp-108h]
  _BYTE v34[16]; // [rsp+38h] [rbp-100h] BYREF
  __int64 v35; // [rsp+48h] [rbp-F0h] BYREF
  __int64 v36; // [rsp+50h] [rbp-E8h]
  __int64 v37; // [rsp+58h] [rbp-E0h]
  _BYTE v38[8]; // [rsp+60h] [rbp-D8h] BYREF
  _BYTE v39[8]; // [rsp+68h] [rbp-D0h] BYREF
  std::_Ref_count_base *v40; // [rsp+70h] [rbp-C8h]
  _BYTE v41[64]; // [rsp+80h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+C0h] [rbp-78h]
  __int64 v43; // [rsp+C8h] [rbp-70h]
  __int64 v44; // [rsp+F0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v37 = a3;
  LOBYTE(v31) = a2;
  v35 = a1;
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54C,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80004003LL,
      v31);
    return 2147500035LL;
  }
  v6 = *(_QWORD *)(a1 + 64);
  if ( !v6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x551,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x8009800FLL,
      v31);
    return 2148106255LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x555,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80070057LL,
      v31);
    return 2147942487LL;
  }
  if ( a4 != *(_QWORD *)(v6 + 16) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55A,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80098022LL,
      v31);
    return 2148106274LL;
  }
  if ( *(_QWORD *)(v6 + 16) && !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55E,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80004003LL,
      v31);
    return 2147500035LL;
  }
  v7 = StorageAdapterClearContext();
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x562,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)(unsigned int)v7,
      v31);
    return v8;
  }
  v9 = *(_QWORD *)WinBioFramework::PipelineToPipelineObject(v39, v35);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  memset_0(v41, 0, 0x78u);
  FileHeader = CacheGetFileHeader((struct CacheBuffer *)(v9 + 1296), (struct _LOCK_BOX_FILE_HEADER *)v41);
  v11 = FileHeader;
  if ( FileHeader < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56A,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)(unsigned int)FileHeader,
      v31);
    return v11;
  }
  v12 = 4 * v42 + 152;
  v36 = v12;
  v13.QuadPart = v44 + 1144;
  v33 = v43;
  v14 = 0;
  v15 = lambda_bf25de864d02f14d70572f3f2647544a_::_lambda_bf25de864d02f14d70572f3f2647544a_(v38, &v35);
  wil::ScopeExitLog__lambda_bf25de864d02f14d70572f3f2647544a___(v34, v15);
  while ( 1 )
  {
    if ( !v16 )
    {
      if ( v14 )
      {
        v34[9] = 0;
        wil::details::ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7___::_ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7___(v34);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B0,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
          (const char *)0x8009801FLL,
          v31);
        wil::details::ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7___::_ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7___(v34);
        return 2148106271LL;
      }
    }
    wil::make_unique_hlocal<unsigned char [0]>(&hMem, v12);
    v17 = hMem;
    RecordHeader = CacheGetRecordHeader(
                     (struct CacheBuffer *)(v9 + 1296),
                     v13,
                     (struct _LOCK_BOX_RECORD_HEADER *)hMem,
                     v12);
    v19 = RecordHeader;
    if ( RecordHeader < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x586,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
        (const char *)(unsigned int)RecordHeader,
        v31);
      v20 = hMem;
      hMem = 0;
      if ( !v20 )
      {
LABEL_21:
        wil::details::ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7___::_ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7___(v34);
        return v19;
      }
LABEL_20:
      LocalFree(v20);
      goto LABEL_21;
    }
    v21 = v17[8];
    if ( v21 && v17 == (_QWORD *)-152LL )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58C,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
        (const char *)0x80004003LL,
        v31);
      v22 = hMem;
      hMem = 0;
      if ( v22 )
        goto LABEL_25;
      goto LABEL_26;
    }
    if ( (v17[2] & 1) == 0 )
      break;
LABEL_49:
    v13.QuadPart += v17[3];
    v16 = --v33;
    v30 = hMem;
    hMem = 0;
    v12 = v36;
    if ( v30 )
    {
      LocalFree(v30);
      v16 = v33;
    }
  }
  v23 = (char *)(v17 + 19);
  if ( !v21 )
    v23 = 0;
  v24 = 0;
  if ( (_BYTE)v31 != 0xFF && (v25 = *((_BYTE *)v17 + 148), v25 != -1) && (_BYTE)v31 != v25 || a4 != *(_QWORD *)(v6 + 16) )
  {
LABEL_44:
    if ( v24 )
    {
      v27.QuadPart = v13.QuadPart + v17[4];
      v28 = (struct _LOCK_BOX_RECORD_HEADER *)hMem;
      hMem = 0;
      v29 = ResAddElement((struct _RESULT_SET *)(v6 + 48), v28, v27);
      v19 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5A4,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
          (const char *)(unsigned int)v29,
          v31);
        v20 = hMem;
        hMem = 0;
        if ( !v20 )
          goto LABEL_21;
        goto LABEL_20;
      }
      v14 = 1;
    }
    goto LABEL_49;
  }
  if ( !a4 )
  {
LABEL_43:
    v24 = 1;
    goto LABEL_44;
  }
  if ( v37 && v23 )
  {
    for ( i = 0; i < a4; ++i )
    {
      if ( *(_DWORD *)(v37 + 4 * i) != *(_DWORD *)&v23[4 * i] )
        goto LABEL_44;
    }
    goto LABEL_43;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x599,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
    (const char *)0x80004003LL,
    v31);
  v22 = hMem;
  hMem = 0;
  if ( v22 )
LABEL_25:
    LocalFree(v22);
LABEL_26:
  wil::details::ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7___::_ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7___(v34);
  return 2147500035LL;
}

```

## disassembly

```asm
0x140011f50  mov     [rsp+arg_8], rbx
0x140011f55  mov     [rsp+arg_10], rsi
0x140011f5a  push    rdi
0x140011f5b  push    r12
0x140011f5d  push    r13
0x140011f5f  push    r14
0x140011f61  push    r15
0x140011f63  sub     rsp, 110h
0x140011f6a  mov     rax, cs:__security_cookie
0x140011f71  xor     rax, rsp
0x140011f74  mov     [rsp+138h+var_38], rax
0x140011f7c  mov     r12, r9
0x140011f7f  mov     rax, r8
0x140011f82  mov     [rsp+138h+var_E0], rax
0x140011f87  mov     byte ptr [rsp+138h+var_118], dl; int
0x140011f8b  mov     [rsp+138h+var_F0], rcx
0x140011f90  test    rcx, rcx
0x140011f93  jnz     short loc_140011FBD
0x140011f95  mov     rcx, [rsp+138h]; this
0x140011f9d  mov     ebx, 80004003h
0x140011fa2  mov     r9d, ebx; char *
0x140011fa5  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140011fac  mov     edx, 54Ch; void *
0x140011fb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011fb6  mov     eax, ebx
0x140011fb8  jmp     loc_140012424
0x140011fbd  mov     r14, [rcx+40h]
0x140011fc1  test    r14, r14
0x140011fc4  jnz     short loc_140011FEE
0x140011fc6  mov     rcx, [rsp+138h]; this
0x140011fce  mov     ebx, 8009800Fh
0x140011fd3  mov     r9d, ebx; char *
0x140011fd6  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140011fdd  mov     edx, 551h; void *
0x140011fe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011fe7  mov     eax, ebx
0x140011fe9  jmp     loc_140012424
0x140011fee  test    dl, dl
0x140011ff0  jz      loc_1400123FB
0x140011ff6  cmp     r12, [r14+10h]
0x140011ffa  jnz     loc_1400123D6
0x140012000  cmp     qword ptr [r14+10h], 0
0x140012005  jbe     short loc_140012034
0x140012007  test    rax, rax
0x14001200a  jnz     short loc_140012034
0x14001200c  mov     rcx, [rsp+138h]; this
0x140012014  mov     ebx, 80004003h
0x140012019  mov     r9d, ebx; char *
0x14001201c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140012023  mov     edx, 55Eh; void *
0x140012028  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001202d  mov     eax, ebx
0x14001202f  jmp     loc_140012424
0x140012034  call    StorageAdapterClearContext
0x140012039  mov     ebx, eax
0x14001203b  test    eax, eax
0x14001203d  jns     short loc_140012062
0x14001203f  mov     rcx, [rsp+138h]; this
0x140012047  mov     r9d, eax; char *
0x14001204a  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140012051  mov     edx, 562h; void *
0x140012056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001205b  mov     eax, ebx
0x14001205d  jmp     loc_140012424
0x140012062  mov     rdx, [rsp+138h+var_F0]
0x140012067  lea     rcx, [rsp+138h+var_D0]
0x14001206c  call    WinBioFramework__PipelineToPipelineObject
0x140012071  mov     r15, [rax]
0x140012074  mov     rcx, [rsp+138h+var_C8]; this
0x140012079  test    rcx, rcx
0x14001207c  jz      short loc_140012083
0x14001207e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140012083  xor     edx, edx; Val
0x140012085  lea     r8d, [rdx+78h]; Size
0x140012089  lea     rcx, [rsp+138h+var_B8]; void *
0x140012091  call    memset_0
0x140012096  lea     rdx, [rsp+138h+var_B8]; struct _LOCK_BOX_FILE_HEADER *
0x14001209e  lea     rcx, [r15+510h]; struct CacheBuffer *
0x1400120a5  call    ?CacheGetFileHeader@@YAJPEAVCacheBuffer@@PEAU_LOCK_BOX_FILE_HEADER@@@Z; CacheGetFileHeader(CacheBuffer *,_LOCK_BOX_FILE_HEADER *)
0x1400120aa  mov     ebx, eax
0x1400120ac  test    eax, eax
0x1400120ae  jns     short loc_1400120D3
0x1400120b0  mov     rcx, [rsp+138h]; this
0x1400120b8  mov     r9d, eax; char *
0x1400120bb  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400120c2  mov     edx, 56Ah; void *
0x1400120c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400120cc  mov     eax, ebx
0x1400120ce  jmp     loc_140012424
0x1400120d3  mov     rax, [rsp+138h+var_78]
0x1400120db  lea     rdi, ds:98h[rax*4]
0x1400120e3  mov     [rsp+138h+var_E8], rdi
0x1400120e8  mov     rbx, [rsp+138h+var_48]
0x1400120f0  add     rbx, 478h
0x1400120f7  mov     r8, [rsp+138h+var_70]
0x1400120ff  mov     [rsp+138h+var_108], r8
0x140012104  xor     r13b, r13b
0x140012107  lea     rdx, [rsp+138h+var_F0]
0x14001210c  lea     rcx, [rsp+138h+var_D8]
0x140012111  call    _lambda_bf25de864d02f14d70572f3f2647544a____lambda_bf25de864d02f14d70572f3f2647544a_
0x140012116  mov     rdx, rax
0x140012119  lea     rcx, [rsp+138h+var_100]
0x14001211e  call    wil__ScopeExitLog__lambda_bf25de864d02f14d70572f3f2647544a___
0x140012123  nop
0x140012124  test    r8, r8
0x140012127  jz      loc_14001238E
0x14001212d  mov     rdx, rdi
0x140012130  lea     rcx, [rsp+138h+hMem]
0x140012135  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x14001213a  nop
0x14001213b  mov     rsi, [rsp+138h+hMem]
0x140012140  mov     r9, rdi; unsigned int
0x140012143  mov     r8, rsi; struct _LOCK_BOX_RECORD_HEADER *
0x140012146  mov     rdx, rbx; union _LARGE_INTEGER
0x140012149  lea     rcx, [r15+510h]; this
0x140012150  call    ?CacheGetRecordHeader@@YAJPEAVCacheBuffer@@T_LARGE_INTEGER@@PEAU_LOCK_BOX_RECORD_HEADER@@_K@Z; CacheGetRecordHeader(CacheBuffer *,_LARGE_INTEGER,_LOCK_BOX_RECORD_HEADER *,unsigned __int64)
0x140012155  mov     edi, eax
0x140012157  test    eax, eax
0x140012159  jns     short loc_1400121A9
0x14001215b  mov     rcx, [rsp+138h]; this
0x140012163  mov     r9d, eax; char *
0x140012166  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14001216d  mov     edx, 586h; void *
0x140012172  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012177  nop
0x140012178  mov     rcx, [rsp+138h+hMem]; hMem
0x14001217d  mov     [rsp+138h+hMem], 0
0x140012186  test    rcx, rcx
0x140012189  jz      short loc_140012198
0x14001218b  call    cs:__imp_LocalFree
0x140012192  nop     dword ptr [rax+rax+00h]
0x140012197  nop
0x140012198  lea     rcx, [rsp+138h+var_100]
0x14001219d  call    wil__details__ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7______ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7___
0x1400121a2  mov     eax, edi
0x1400121a4  jmp     loc_140012424
0x1400121a9  mov     rcx, [rsi+40h]
0x1400121ad  test    rcx, rcx
0x1400121b0  jz      short loc_140012211
0x1400121b2  lea     rax, [rsi+98h]
0x1400121b9  test    rax, rax
0x1400121bc  jnz     short loc_140012211
0x1400121be  mov     rcx, [rsp+138h]; this
0x1400121c6  mov     ebx, 80004003h
0x1400121cb  mov     r9d, ebx; char *
0x1400121ce  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400121d5  mov     edx, 58Ch; void *
0x1400121da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400121df  nop
0x1400121e0  mov     rcx, [rsp+138h+hMem]; hMem
0x1400121e5  mov     [rsp+138h+hMem], 0
0x1400121ee  test    rcx, rcx
0x1400121f1  jz      short loc_140012200
0x1400121f3  call    cs:__imp_LocalFree
0x1400121fa  nop     dword ptr [rax+rax+00h]
0x1400121ff  nop
0x140012200  lea     rcx, [rsp+138h+var_100]
0x140012205  call    wil__details__ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7______ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7___
0x14001220a  mov     eax, ebx
0x14001220c  jmp     loc_140012424
0x140012211  test    byte ptr [rsi+10h], 1
0x140012215  jnz     loc_14001234B
0x14001221b  lea     rdx, [rsi+98h]
0x140012222  xor     eax, eax
0x140012224  test    rcx, rcx
0x140012227  cmovz   rdx, rax
0x14001222b  xor     r8b, r8b
0x14001222e  mov     dil, byte ptr [rsp+138h+var_118]
0x140012233  cmp     dil, 0FFh
0x140012237  jz      short loc_14001224C
0x140012239  mov     al, [rsi+94h]
0x14001223f  cmp     al, 0FFh
0x140012241  jz      short loc_14001224C
0x140012243  cmp     dil, al
0x140012246  jnz     loc_1400122D1
0x14001224c  cmp     r12, [r14+10h]
0x140012250  jnz     short loc_1400122D1
0x140012252  test    r12, r12
0x140012255  jz      short loc_1400122CE
0x140012257  mov     r9, [rsp+138h+var_E0]
0x14001225c  test    r9, r9
0x14001225f  jz      short loc_14001227B
0x140012261  test    rdx, rdx
0x140012264  jz      short loc_14001227B
0x140012266  xor     ecx, ecx
0x140012268  cmp     rcx, r12
0x14001226b  jnb     short loc_1400122CE
0x14001226d  mov     eax, [rdx+rcx*4]
0x140012270  cmp     [r9+rcx*4], eax
0x140012274  jnz     short loc_1400122D1
0x140012276  inc     rcx
0x140012279  jmp     short loc_140012268
0x14001227b  mov     rcx, [rsp+138h]; this
0x140012283  mov     ebx, 80004003h
0x140012288  mov     r9d, ebx; char *
0x14001228b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140012292  mov     edx, 599h; void *
0x140012297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001229c  nop
0x14001229d  mov     rcx, [rsp+138h+hMem]; hMem
0x1400122a2  mov     [rsp+138h+hMem], 0
0x1400122ab  test    rcx, rcx
0x1400122ae  jz      short loc_1400122BD
0x1400122b0  call    cs:__imp_LocalFree
0x1400122b7  nop     dword ptr [rax+rax+00h]
0x1400122bc  nop
0x1400122bd  lea     rcx, [rsp+138h+var_100]
0x1400122c2  call    wil__details__ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7______ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7___
0x1400122c7  mov     eax, ebx
0x1400122c9  jmp     loc_140012424
0x1400122ce  mov     r8b, 1
0x1400122d1  test    r8b, r8b
0x1400122d4  jz      short loc_14001234B
0x1400122d6  mov     r8, [rsi+20h]
0x1400122da  add     r8, rbx; union _LARGE_INTEGER
0x1400122dd  mov     rdx, [rsp+138h+hMem]; struct _LOCK_BOX_RECORD_HEADER *
0x1400122e2  mov     [rsp+138h+hMem], 0
0x1400122eb  lea     rcx, [r14+30h]; struct _RESULT_SET *
0x1400122ef  call    ?ResAddElement@@YAJPEAU_RESULT_SET@@PEAU_LOCK_BOX_RECORD_HEADER@@T_LARGE_INTEGER@@@Z; ResAddElement(_RESULT_SET *,_LOCK_BOX_RECORD_HEADER *,_LARGE_INTEGER)
0x1400122f4  mov     edi, eax
0x1400122f6  test    eax, eax
0x1400122f8  jns     short loc_140012348
0x1400122fa  mov     rcx, [rsp+138h]; this
0x140012302  mov     r9d, eax; char *
0x140012305  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14001230c  mov     edx, 5A4h; void *
0x140012311  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012316  nop
0x140012317  mov     rcx, [rsp+138h+hMem]; hMem
0x14001231c  mov     [rsp+138h+hMem], 0
0x140012325  test    rcx, rcx
0x140012328  jz      short loc_140012337
0x14001232a  call    cs:__imp_LocalFree
0x140012331  nop     dword ptr [rax+rax+00h]
0x140012336  nop
0x140012337  lea     rcx, [rsp+138h+var_100]
0x14001233c  call    wil__details__ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7______ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7___
0x140012341  mov     eax, edi
0x140012343  jmp     loc_140012424
0x140012348  mov     r13b, 1
0x14001234b  add     rbx, [rsi+18h]
0x14001234f  mov     r8, [rsp+138h+var_108]
0x140012354  dec     r8
0x140012357  mov     [rsp+138h+var_108], r8
0x14001235c  mov     rcx, [rsp+138h+hMem]; hMem
0x140012361  mov     [rsp+138h+hMem], 0
0x14001236a  test    rcx, rcx
0x14001236d  mov     rdi, [rsp+138h+var_E8]
0x140012372  jz      loc_140012124
0x140012378  call    cs:__imp_LocalFree
0x14001237f  nop     dword ptr [rax+rax+00h]
0x140012384  mov     r8, [rsp+138h+var_108]
0x140012389  jmp     loc_140012124
0x14001238e  test    r13b, r13b
0x140012391  jnz     short loc_1400123C3
0x140012393  mov     rcx, [rsp+138h]; this
0x14001239b  mov     ebx, 8009801Fh
0x1400123a0  mov     r9d, ebx; char *
0x1400123a3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400123aa  mov     edx, 5B0h; void *
0x1400123af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400123b4  nop
0x1400123b5  lea     rcx, [rsp+138h+var_100]
0x1400123ba  call    wil__details__ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7______ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7___
0x1400123bf  mov     eax, ebx
0x1400123c1  jmp     short loc_140012424
0x1400123c3  mov     [rsp+138h+var_F7], 0
0x1400123c8  lea     rcx, [rsp+138h+var_100]
0x1400123cd  call    wil__details__ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7______ScopeExitFnGuard__lambda_69f3df9b0b889b1f7e1102aee83bf1d7___
0x1400123d2  xor     eax, eax
0x1400123d4  jmp     short loc_140012424
0x1400123d6  mov     rcx, [rsp+138h]; this
0x1400123de  mov     ebx, 80098022h
0x1400123e3  mov     r9d, ebx; char *
0x1400123e6  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400123ed  mov     edx, 55Ah; void *
0x1400123f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400123f7  mov     eax, ebx
0x1400123f9  jmp     short loc_140012424
0x1400123fb  mov     rcx, [rsp+138h]; this
0x140012403  mov     ebx, 80070057h
0x140012408  mov     r9d, ebx; char *
0x14001240b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140012412  mov     edx, 555h; void *
0x140012417  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001241c  mov     eax, ebx
0x14001241e  jmp     short loc_140012424
0x140012420  mov     eax, dword ptr [rsp+138h+hMem]
0x140012424  mov     rcx, [rsp+138h+var_38]
0x14001242c  xor     rcx, rsp; StackCookie
0x14001242f  call    __security_check_cookie
0x140012434  lea     r11, [rsp+138h+var_28]
0x14001243c  mov     rbx, [r11+38h]
0x140012440  mov     rsi, [r11+40h]
0x140012444  mov     rsp, r11
0x140012447  pop     r15
0x140012449  pop     r14
0x14001244b  pop     r13
0x14001244d  pop     r12
0x14001244f  pop     rdi
  ... truncated ...
```
