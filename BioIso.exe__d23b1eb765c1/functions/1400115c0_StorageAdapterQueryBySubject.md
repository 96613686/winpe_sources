# StorageAdapterQueryBySubject

- ea: `0x1400115c0`
- end: `0x140011a32`
- name: `StorageAdapterQueryBySubject`
- size: `1138`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000fd00`
- `0x140065380`

## callees

- `0x14000a2e4`
- `0x14000a420`
- `0x14001101c`
- `0x1400115c0`
- `0x140011b1c`
- `0x14001bd40`
- `0x14001cb90`
- `0x140058624`
- `0x140058734`
- `0x14005c8c8`
- `0x1400631d0`
- `0x1400633e0`
- `0x140063760`
- `0x14007dc3c`
- `0x14007dd74`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011846`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400118ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011948`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001198c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011846`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400118ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011948`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001198c`

## string_xrefs

- `0x140011607`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140011634`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14001166a`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400116a1`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400116d3`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14001170a`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14001177b`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140011821`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400118a5`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140011923`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400119b2`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400119f5`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall StorageAdapterQueryBySubject(__int64 a1, struct _WINBIO_IDENTITY *a2, unsigned __int8 a3)
{
  WINBIO_IDENTITY_TYPE Type; // edx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // r15
  int FileHeader; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdi
  union _LARGE_INTEGER v12; // rbx
  __int64 v13; // r12
  char v14; // r13
  __int64 v15; // rax
  char *v16; // rsi
  int RecordHeader; // eax
  unsigned int v18; // edi
  HLOCAL v19; // rcx
  int matched; // eax
  union _LARGE_INTEGER v21; // r8
  struct _LOCK_BOX_RECORD_HEADER *v22; // rdx
  int v23; // eax
  HLOCAL v24; // rcx
  int v25; // [rsp+20h] [rbp-128h]
  unsigned __int8 v26; // [rsp+30h] [rbp-118h] BYREF
  unsigned __int8 v27; // [rsp+31h] [rbp-117h]
  HLOCAL hMem; // [rsp+38h] [rbp-110h] BYREF
  _BYTE v29[16]; // [rsp+40h] [rbp-108h] BYREF
  __int64 v30; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v31; // [rsp+58h] [rbp-F0h]
  __int64 v32; // [rsp+60h] [rbp-E8h]
  _BYTE v33[8]; // [rsp+68h] [rbp-E0h] BYREF
  _BYTE v34[8]; // [rsp+70h] [rbp-D8h] BYREF
  std::_Ref_count_base *v35; // [rsp+78h] [rbp-D0h]
  _BYTE v36[64]; // [rsp+80h] [rbp-C8h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-88h]
  __int64 v38; // [rsp+C8h] [rbp-80h]
  __int64 v39; // [rsp+F0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v27 = a3;
  v30 = a1;
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D4,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80004003LL,
      v25);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D7,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80004003LL,
      v25);
    return 2147500035LL;
  }
  v32 = *(_QWORD *)(a1 + 64);
  if ( !v32 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4DC,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x8009800FLL,
      v25);
    return 2148106255LL;
  }
  Type = a2->Type;
  if ( Type - 2 <= 1 )
    goto LABEL_12;
  if ( Type != 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E2,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80070057LL,
      v25);
    return 2147942487LL;
  }
  if ( a2->Value.Null == 621175426 )
  {
LABEL_12:
    if ( a3 )
    {
      v6 = StorageAdapterClearContext();
      v7 = v6;
      if ( v6 >= 0 )
      {
        v8 = *(_QWORD *)WinBioFramework::PipelineToPipelineObject(v34, v30);
        if ( v35 )
          std::_Ref_count_base::_Decref(v35);
        memset_0(v36, 0, 0x78u);
        FileHeader = CacheGetFileHeader((struct CacheBuffer *)(v8 + 1296), (struct _LOCK_BOX_FILE_HEADER *)v36);
        v10 = FileHeader;
        if ( FileHeader >= 0 )
        {
          v11 = 4 * v37 + 152;
          v31 = v11;
          v12.QuadPart = v39 + 1144;
          v13 = v38;
          v14 = 0;
          v15 = lambda_bf25de864d02f14d70572f3f2647544a_::_lambda_bf25de864d02f14d70572f3f2647544a_(v33, &v30);
          wil::ScopeExitLog__lambda_bf25de864d02f14d70572f3f2647544a___(v29, v15);
          while ( v13 )
          {
            wil::make_unique_hlocal<unsigned char [0]>(&hMem, v11);
            v16 = (char *)hMem;
            RecordHeader = CacheGetRecordHeader(
                             (struct CacheBuffer *)(v8 + 1296),
                             v12,
                             (struct _LOCK_BOX_RECORD_HEADER *)hMem,
                             v11);
            v18 = RecordHeader;
            if ( RecordHeader < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x513,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                (const char *)(unsigned int)RecordHeader,
                v25);
              v19 = hMem;
              hMem = 0;
              if ( !v19 )
                goto LABEL_32;
LABEL_31:
              LocalFree(v19);
              goto LABEL_32;
            }
            if ( (v16[16] & 1) == 0 )
            {
              v26 = 0;
              matched = MatchIdentity(a2, v27, (struct _WINBIO_IDENTITY *)(v16 + 72), v16[148], &v26);
              v18 = matched;
              if ( matched < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x51F,
                  (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                  (const char *)(unsigned int)matched,
                  v25);
                v19 = hMem;
                hMem = 0;
                if ( !v19 )
                  goto LABEL_32;
                goto LABEL_31;
              }
              if ( v26 )
              {
                v21.QuadPart = v12.QuadPart + *((_QWORD *)v16 + 4);
                v22 = (struct _LOCK_BOX_RECORD_HEADER *)hMem;
                hMem = 0;
                v23 = ResAddElement((struct _RESULT_SET *)(v32 + 48), v22, v21);
                v18 = v23;
                if ( v23 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x52A,
                    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                    (const char *)(unsigned int)v23,
                    v25);
                  v19 = hMem;
                  hMem = 0;
                  if ( v19 )
                    goto LABEL_31;
LABEL_32:
                  wil::details::ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a___::_ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a___(v29);
                  return v18;
                }
                v14 = 1;
              }
            }
            v12.QuadPart += *((_QWORD *)v16 + 3);
            --v13;
            v24 = hMem;
            hMem = 0;
            v11 = v31;
            if ( v24 )
              LocalFree(v24);
          }
          if ( v14 )
          {
            v29[9] = 0;
            wil::details::ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a___::_ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a___(v29);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x536,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
              (const char *)0x8009801FLL,
              v25);
            wil::details::ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a___::_ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a___(v29);
            return 2148106271LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4F7,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
            (const char *)(unsigned int)FileHeader,
            v25);
          return v10;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4EF,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
          (const char *)(unsigned int)v6,
          v25);
        return v7;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4EB,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
        (const char *)0x80070057LL,
        v25);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E7,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80070057LL,
      v25);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1400115c0  push    rbx
0x1400115c2  push    rsi
0x1400115c3  push    rdi
0x1400115c4  push    r12
0x1400115c6  push    r13
0x1400115c8  push    r14
0x1400115ca  push    r15
0x1400115cc  sub     rsp, 110h
0x1400115d3  mov     rax, cs:__security_cookie
0x1400115da  xor     rax, rsp
0x1400115dd  mov     [rsp+148h+var_48], rax
0x1400115e5  mov     [rsp+148h+var_117], r8b
0x1400115ea  mov     r14, rdx
0x1400115ed  mov     [rsp+148h+var_F8], rcx
0x1400115f2  test    rcx, rcx
0x1400115f5  jnz     short loc_14001161F
0x1400115f7  mov     rcx, [rsp+148h]; this
0x1400115ff  mov     ebx, 80004003h
0x140011604  mov     r9d, ebx; char *
0x140011607  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14001160e  mov     edx, 4D4h; void *
0x140011613  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011618  mov     eax, ebx
0x14001161a  jmp     loc_140011A0E
0x14001161f  test    r14, r14
0x140011622  jnz     short loc_14001164C
0x140011624  mov     rcx, [rsp+148h]; this
0x14001162c  mov     ebx, 80004003h
0x140011631  mov     r9d, ebx; char *
0x140011634  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14001163b  mov     edx, 4D7h; void *
0x140011640  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011645  mov     eax, ebx
0x140011647  jmp     loc_140011A0E
0x14001164c  mov     rax, [rcx+40h]
0x140011650  mov     [rsp+148h+var_E8], rax
0x140011655  test    rax, rax
0x140011658  jnz     short loc_140011682
0x14001165a  mov     rcx, [rsp+148h]; this
0x140011662  mov     ebx, 8009800Fh
0x140011667  mov     r9d, ebx; char *
0x14001166a  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140011671  mov     edx, 4DCh; void *
0x140011676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001167b  mov     eax, ebx
0x14001167d  jmp     loc_140011A0E
0x140011682  mov     edx, [rdx]
0x140011684  lea     eax, [rdx-2]
0x140011687  cmp     eax, 1
0x14001168a  jbe     short loc_1400116EB
0x14001168c  cmp     edx, 1
0x14001168f  jz      short loc_1400116B9
0x140011691  mov     rcx, [rsp+148h]; this
0x140011699  mov     ebx, 80070057h
0x14001169e  mov     r9d, ebx; char *
0x1400116a1  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400116a8  mov     edx, 4E2h; void *
0x1400116ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400116b2  mov     eax, ebx
0x1400116b4  jmp     loc_140011A0E
0x1400116b9  cmp     dword ptr [r14+4], 25066282h
0x1400116c1  jz      short loc_1400116EB
0x1400116c3  mov     rcx, [rsp+148h]; this
0x1400116cb  mov     ebx, 80070057h
0x1400116d0  mov     r9d, ebx; char *
0x1400116d3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400116da  mov     edx, 4E7h; void *
0x1400116df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400116e4  mov     eax, ebx
0x1400116e6  jmp     loc_140011A0E
0x1400116eb  test    r8b, r8b
0x1400116ee  jz      loc_1400119E5
0x1400116f4  call    StorageAdapterClearContext
0x1400116f9  mov     ebx, eax
0x1400116fb  test    eax, eax
0x1400116fd  jns     short loc_140011722
0x1400116ff  mov     rcx, [rsp+148h]; this
0x140011707  mov     r9d, eax; char *
0x14001170a  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140011711  mov     edx, 4EFh; void *
0x140011716  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001171b  mov     eax, ebx
0x14001171d  jmp     loc_140011A0E
0x140011722  mov     rdx, [rsp+148h+var_F8]
0x140011727  lea     rcx, [rsp+148h+var_D8]
0x14001172c  call    WinBioFramework__PipelineToPipelineObject
0x140011731  mov     r15, [rax]
0x140011734  mov     rcx, [rsp+148h+var_D0]; this
0x140011739  test    rcx, rcx
0x14001173c  jz      short loc_140011743
0x14001173e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140011743  xor     edx, edx; Val
0x140011745  lea     r8d, [rdx+78h]; Size
0x140011749  lea     rcx, [rsp+148h+var_C8]; void *
0x140011751  call    memset_0
0x140011756  lea     rdx, [rsp+148h+var_C8]; struct _LOCK_BOX_FILE_HEADER *
0x14001175e  lea     rcx, [r15+510h]; struct CacheBuffer *
0x140011765  call    ?CacheGetFileHeader@@YAJPEAVCacheBuffer@@PEAU_LOCK_BOX_FILE_HEADER@@@Z; CacheGetFileHeader(CacheBuffer *,_LOCK_BOX_FILE_HEADER *)
0x14001176a  mov     ebx, eax
0x14001176c  test    eax, eax
0x14001176e  jns     short loc_140011793
0x140011770  mov     rcx, [rsp+148h]; this
0x140011778  mov     r9d, eax; char *
0x14001177b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140011782  mov     edx, 4F7h; void *
0x140011787  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001178c  mov     eax, ebx
0x14001178e  jmp     loc_140011A0E
0x140011793  mov     rax, [rsp+148h+var_88]
0x14001179b  lea     rdi, ds:98h[rax*4]
0x1400117a3  mov     [rsp+148h+var_F0], rdi
0x1400117a8  mov     rbx, [rsp+148h+var_58]
0x1400117b0  add     rbx, 478h
0x1400117b7  mov     r12, [rsp+148h+var_80]
0x1400117bf  xor     r13b, r13b
0x1400117c2  lea     rdx, [rsp+148h+var_F8]
0x1400117c7  lea     rcx, [rsp+148h+var_E0]
0x1400117cc  call    _lambda_bf25de864d02f14d70572f3f2647544a____lambda_bf25de864d02f14d70572f3f2647544a_
0x1400117d1  mov     rdx, rax
0x1400117d4  lea     rcx, [rsp+148h+var_108]
0x1400117d9  call    wil__ScopeExitLog__lambda_bf25de864d02f14d70572f3f2647544a___
0x1400117de  nop
0x1400117df  test    r12, r12
0x1400117e2  jz      loc_14001199D
0x1400117e8  mov     rdx, rdi
0x1400117eb  lea     rcx, [rsp+148h+hMem]
0x1400117f0  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x1400117f5  nop
0x1400117f6  mov     rsi, [rsp+148h+hMem]
0x1400117fb  mov     r9, rdi; unsigned int
0x1400117fe  mov     r8, rsi; struct _LOCK_BOX_RECORD_HEADER *
0x140011801  mov     rdx, rbx; union _LARGE_INTEGER
0x140011804  lea     rcx, [r15+510h]; this
0x14001180b  call    ?CacheGetRecordHeader@@YAJPEAVCacheBuffer@@T_LARGE_INTEGER@@PEAU_LOCK_BOX_RECORD_HEADER@@_K@Z; CacheGetRecordHeader(CacheBuffer *,_LARGE_INTEGER,_LOCK_BOX_RECORD_HEADER *,unsigned __int64)
0x140011810  mov     edi, eax
0x140011812  test    eax, eax
0x140011814  jns     short loc_140011864
0x140011816  mov     rcx, [rsp+148h]; this
0x14001181e  mov     r9d, eax; char *
0x140011821  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140011828  mov     edx, 513h; void *
0x14001182d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011832  nop
0x140011833  mov     rcx, [rsp+148h+hMem]; hMem
0x140011838  mov     [rsp+148h+hMem], 0
0x140011841  test    rcx, rcx
0x140011844  jz      short loc_140011853
0x140011846  call    cs:__imp_LocalFree
0x14001184d  nop     dword ptr [rax+rax+00h]
0x140011852  nop
0x140011853  lea     rcx, [rsp+148h+var_108]
0x140011858  call    wil__details__ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a______ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a___
0x14001185d  mov     eax, edi
0x14001185f  jmp     loc_140011A0E
0x140011864  test    byte ptr [rsi+10h], 1
0x140011868  jnz     loc_140011969
0x14001186e  mov     [rsp+148h+var_118], 0
0x140011873  lea     r8, [rsi+48h]; struct _WINBIO_IDENTITY *
0x140011877  lea     rax, [rsp+148h+var_118]
0x14001187c  mov     qword ptr [rsp+148h+var_128], rax; int
0x140011881  mov     r9b, [rsi+94h]; unsigned __int8
0x140011888  mov     dl, [rsp+148h+var_117]; unsigned __int8
0x14001188c  mov     rcx, r14; struct _WINBIO_IDENTITY *
0x14001188f  call    ?MatchIdentity@@YAJPEAU_WINBIO_IDENTITY@@E0EPEAE@Z; MatchIdentity(_WINBIO_IDENTITY *,uchar,_WINBIO_IDENTITY *,uchar,uchar *)
0x140011894  mov     edi, eax
0x140011896  test    eax, eax
0x140011898  jns     short loc_1400118E8
0x14001189a  mov     rcx, [rsp+148h]; this
0x1400118a2  mov     r9d, eax; char *
0x1400118a5  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400118ac  mov     edx, 51Fh; void *
0x1400118b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400118b6  nop
0x1400118b7  mov     rcx, [rsp+148h+hMem]; hMem
0x1400118bc  mov     [rsp+148h+hMem], 0
0x1400118c5  test    rcx, rcx
0x1400118c8  jz      short loc_1400118D7
0x1400118ca  call    cs:__imp_LocalFree
0x1400118d1  nop     dword ptr [rax+rax+00h]
0x1400118d6  nop
0x1400118d7  lea     rcx, [rsp+148h+var_108]
0x1400118dc  call    wil__details__ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a______ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a___
0x1400118e1  mov     eax, edi
0x1400118e3  jmp     loc_140011A0E
0x1400118e8  cmp     [rsp+148h+var_118], 0
0x1400118ed  jz      short loc_140011969
0x1400118ef  mov     r8, [rsi+20h]
0x1400118f3  add     r8, rbx; union _LARGE_INTEGER
0x1400118f6  mov     rdx, [rsp+148h+hMem]; struct _LOCK_BOX_RECORD_HEADER *
0x1400118fb  mov     [rsp+148h+hMem], 0
0x140011904  mov     rcx, [rsp+148h+var_E8]
0x140011909  add     rcx, 30h ; '0'; struct _RESULT_SET *
0x14001190d  call    ?ResAddElement@@YAJPEAU_RESULT_SET@@PEAU_LOCK_BOX_RECORD_HEADER@@T_LARGE_INTEGER@@@Z; ResAddElement(_RESULT_SET *,_LOCK_BOX_RECORD_HEADER *,_LARGE_INTEGER)
0x140011912  mov     edi, eax
0x140011914  test    eax, eax
0x140011916  jns     short loc_140011966
0x140011918  mov     rcx, [rsp+148h]; this
0x140011920  mov     r9d, eax; char *
0x140011923  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14001192a  mov     edx, 52Ah; void *
0x14001192f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011934  nop
0x140011935  mov     rcx, [rsp+148h+hMem]; hMem
0x14001193a  mov     [rsp+148h+hMem], 0
0x140011943  test    rcx, rcx
0x140011946  jz      short loc_140011955
0x140011948  call    cs:__imp_LocalFree
0x14001194f  nop     dword ptr [rax+rax+00h]
0x140011954  nop
0x140011955  lea     rcx, [rsp+148h+var_108]
0x14001195a  call    wil__details__ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a______ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a___
0x14001195f  mov     eax, edi
0x140011961  jmp     loc_140011A0E
0x140011966  mov     r13b, 1
0x140011969  add     rbx, [rsi+18h]
0x14001196d  dec     r12
0x140011970  mov     rcx, [rsp+148h+hMem]; hMem
0x140011975  mov     [rsp+148h+hMem], 0
0x14001197e  test    rcx, rcx
0x140011981  mov     rdi, [rsp+148h+var_F0]
0x140011986  jz      loc_1400117DF
0x14001198c  call    cs:__imp_LocalFree
0x140011993  nop     dword ptr [rax+rax+00h]
0x140011998  jmp     loc_1400117DF
0x14001199d  test    r13b, r13b
0x1400119a0  jnz     short loc_1400119D2
0x1400119a2  mov     rcx, [rsp+148h]; this
0x1400119aa  mov     ebx, 8009801Fh
0x1400119af  mov     r9d, ebx; char *
0x1400119b2  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400119b9  mov     edx, 536h; void *
0x1400119be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400119c3  nop
0x1400119c4  lea     rcx, [rsp+148h+var_108]
0x1400119c9  call    wil__details__ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a______ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a___
0x1400119ce  mov     eax, ebx
0x1400119d0  jmp     short loc_140011A0E
0x1400119d2  mov     [rsp+148h+var_FF], 0
0x1400119d7  lea     rcx, [rsp+148h+var_108]
0x1400119dc  call    wil__details__ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a______ScopeExitFnGuard__lambda_bf25de864d02f14d70572f3f2647544a___
0x1400119e1  xor     eax, eax
0x1400119e3  jmp     short loc_140011A0E
0x1400119e5  mov     rcx, [rsp+148h]; this
0x1400119ed  mov     ebx, 80070057h
0x1400119f2  mov     r9d, ebx; char *
0x1400119f5  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400119fc  mov     edx, 4EBh; void *
0x140011a01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011a06  mov     eax, ebx
0x140011a08  jmp     short loc_140011A0E
0x140011a0a  mov     eax, dword ptr [rsp+148h+hMem]
0x140011a0e  mov     rcx, [rsp+148h+var_48]
0x140011a16  xor     rcx, rsp; StackCookie
0x140011a19  call    __security_check_cookie
0x140011a1e  add     rsp, 110h
0x140011a25  pop     r15
0x140011a27  pop     r14
0x140011a29  pop     r13
0x140011a2b  pop     r12
0x140011a2d  pop     rdi
0x140011a2e  pop     rsi
0x140011a2f  pop     rbx
0x140011a30  retn
```
