# StorageAdapterDeleteRecord

- ea: `0x140063840`
- end: `0x140063c0d`
- name: `StorageAdapterDeleteRecord`
- size: `973`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x14000a2e4`
- `0x14000a420`
- `0x14001101c`
- `0x140011b1c`
- `0x14001bd40`
- `0x14001cb90`
- `0x140058734`
- `0x140058810`
- `0x14005885c`
- `0x14006328c`
- `0x140063840`
- `0x14007dd74`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140063a28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140063aa6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140063b0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140063b4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140063a28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140063aa6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140063b0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140063b4e`

## string_xrefs

- `0x140063885`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400638b2`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400638ea`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14006391c`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14006398e`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140063a03`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140063a81`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140063aea`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140063b74`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140063ba7`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140063bd0`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall StorageAdapterDeleteRecord(__int64 a1, struct _WINBIO_IDENTITY *a2, unsigned __int8 a3)
{
  struct CacheBuffer *v5; // rsi
  int FileHeader; // eax
  unsigned int v7; // ebx
  union _LARGE_INTEGER v8; // rbx
  __int64 v9; // r15
  char v10; // r13
  __int64 v11; // r12
  int RecordHeader; // eax
  unsigned int v13; // edi
  HLOCAL v14; // rcx
  _QWORD *v15; // rcx
  int matched; // eax
  unsigned int v17; // edi
  HLOCAL v18; // rcx
  int v19; // eax
  unsigned int v20; // edi
  HLOCAL v21; // rcx
  int v22; // eax
  unsigned int v23; // ebx
  int v24; // [rsp+20h] [rbp-F8h]
  unsigned __int8 v25; // [rsp+30h] [rbp-E8h] BYREF
  unsigned __int8 v26; // [rsp+31h] [rbp-E7h]
  HLOCAL hMem; // [rsp+38h] [rbp-E0h] BYREF
  _BYTE v28[8]; // [rsp+40h] [rbp-D8h] BYREF
  std::_Ref_count_base *v29; // [rsp+48h] [rbp-D0h]
  _BYTE v30[72]; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v31; // [rsp+98h] [rbp-80h]
  __int64 v32; // [rsp+A0h] [rbp-78h]
  __int64 v33; // [rsp+C0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v26 = a3;
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x472,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80004003LL,
      v24);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x475,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80004003LL,
      v24);
    return 2147500035LL;
  }
  if ( a2->Type - 2 > 1 )
  {
    if ( a2->Type != 1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47B,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
        (const char *)0x80070057LL,
        v24);
      return 2147942487LL;
    }
    if ( a2->Value.Null != 621175426 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x480,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
        (const char *)0x80070057LL,
        v24);
      return 2147942487LL;
    }
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x484,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80070057LL,
      v24);
    return 2147942487LL;
  }
  v5 = (struct CacheBuffer *)(*(_QWORD *)WinBioFramework::PipelineToPipelineObject(v28, a1) + 1296LL);
  if ( v29 )
    std::_Ref_count_base::_Decref(v29);
  memset_0(v30, 0, 0x78u);
  FileHeader = CacheGetFileHeader(v5, (struct _LOCK_BOX_FILE_HEADER *)v30);
  v7 = FileHeader;
  if ( FileHeader < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48C,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)(unsigned int)FileHeader,
      v24);
    return v7;
  }
  v8.QuadPart = v33 + 1144;
  v9 = v31;
  v10 = 0;
  v11 = v32;
  while ( 1 )
  {
    if ( !v9 )
    {
      if ( v10 )
      {
        v22 = CacheReplaceFileHeader(v5, (struct _LOCK_BOX_FILE_HEADER *)v30);
        v23 = v22;
        if ( v22 >= 0 )
        {
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4C1,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
            (const char *)(unsigned int)v22,
            v24);
          return v23;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4BC,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
          (const char *)0x8009801BLL,
          v24);
        return 2148106267LL;
      }
    }
    wil::make_unique_hlocal<_LOCK_BOX_RECORD_HEADER,>(&hMem);
    RecordHeader = CacheGetRecordHeader(v5, v8, (struct _LOCK_BOX_RECORD_HEADER *)hMem, 0x98u);
    v13 = RecordHeader;
    if ( RecordHeader < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49B,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
        (const char *)(unsigned int)RecordHeader,
        v24);
      v14 = hMem;
      hMem = 0;
      if ( v14 )
        LocalFree(v14);
      return v13;
    }
    v15 = hMem;
    if ( (*((_BYTE *)hMem + 16) & 1) == 0 )
      break;
LABEL_33:
    v8.QuadPart += v15[3];
    --v9;
    hMem = 0;
    if ( v15 )
      LocalFree(v15);
  }
  v25 = 0;
  matched = MatchIdentity(a2, v26, (struct _WINBIO_IDENTITY *)((char *)hMem + 72), *((_BYTE *)hMem + 148), &v25);
  v17 = matched;
  if ( matched < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A7,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)(unsigned int)matched,
      v24);
    v18 = hMem;
    hMem = 0;
    if ( v18 )
      LocalFree(v18);
    return v17;
  }
  if ( !v25 )
  {
LABEL_32:
    v15 = hMem;
    goto LABEL_33;
  }
  *((_DWORD *)hMem + 4) |= 1u;
  v19 = CacheReplaceRecordHeader(v5, v8, (struct _LOCK_BOX_RECORD_HEADER *)hMem);
  v20 = v19;
  if ( v19 >= 0 )
  {
    v32 = ++v11;
    v10 = 1;
    goto LABEL_32;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4AF,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
    (const char *)(unsigned int)v19,
    v24);
  v21 = hMem;
  hMem = 0;
  if ( v21 )
    LocalFree(v21);
  return v20;
}

```

## disassembly

```asm
0x140063840  push    rbx
0x140063842  push    rsi
0x140063843  push    rdi
0x140063844  push    r12
0x140063846  push    r13
0x140063848  push    r14
0x14006384a  push    r15
0x14006384c  sub     rsp, 0E0h
0x140063853  mov     rax, cs:__security_cookie
0x14006385a  xor     rax, rsp
0x14006385d  mov     [rsp+118h+var_48], rax
0x140063865  mov     [rsp+118h+var_E7], r8b
0x14006386a  mov     r14, rdx
0x14006386d  mov     rdx, rcx
0x140063870  test    rcx, rcx
0x140063873  jnz     short loc_14006389D
0x140063875  mov     rcx, [rsp+118h]; this
0x14006387d  mov     ebx, 80004003h
0x140063882  mov     r9d, ebx; char *
0x140063885  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14006388c  mov     edx, 472h; void *
0x140063891  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140063896  mov     eax, ebx
0x140063898  jmp     loc_140063BE9
0x14006389d  test    r14, r14
0x1400638a0  jnz     short loc_1400638CA
0x1400638a2  mov     rcx, [rsp+118h]; this
0x1400638aa  mov     ebx, 80004003h
0x1400638af  mov     r9d, ebx; char *
0x1400638b2  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400638b9  mov     edx, 475h; void *
0x1400638be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400638c3  mov     eax, ebx
0x1400638c5  jmp     loc_140063BE9
0x1400638ca  mov     ecx, [r14]
0x1400638cd  lea     eax, [rcx-2]
0x1400638d0  cmp     eax, 1
0x1400638d3  jbe     short loc_140063934
0x1400638d5  cmp     ecx, 1
0x1400638d8  jz      short loc_140063902
0x1400638da  mov     rcx, [rsp+118h]; this
0x1400638e2  mov     ebx, 80070057h
0x1400638e7  mov     r9d, ebx; char *
0x1400638ea  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400638f1  mov     edx, 47Bh; void *
0x1400638f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400638fb  mov     eax, ebx
0x1400638fd  jmp     loc_140063BE9
0x140063902  cmp     dword ptr [r14+4], 25066282h
0x14006390a  jz      short loc_140063934
0x14006390c  mov     rcx, [rsp+118h]; this
0x140063914  mov     ebx, 80070057h
0x140063919  mov     r9d, ebx; char *
0x14006391c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140063923  mov     edx, 480h; void *
0x140063928  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006392d  mov     eax, ebx
0x14006392f  jmp     loc_140063BE9
0x140063934  test    r8b, r8b
0x140063937  jz      loc_140063BC0
0x14006393d  lea     rcx, [rsp+118h+var_D8]
0x140063942  call    WinBioFramework__PipelineToPipelineObject
0x140063947  mov     rsi, [rax]
0x14006394a  add     rsi, 510h
0x140063951  mov     rcx, [rsp+118h+var_D0]; this
0x140063956  test    rcx, rcx
0x140063959  jz      short loc_140063960
0x14006395b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140063960  xor     edx, edx; Val
0x140063962  lea     r8d, [rdx+78h]; Size
0x140063966  lea     rcx, [rsp+118h+var_C8]; void *
0x14006396b  call    memset_0
0x140063970  lea     rdx, [rsp+118h+var_C8]; struct _LOCK_BOX_FILE_HEADER *
0x140063975  mov     rcx, rsi; struct CacheBuffer *
0x140063978  call    ?CacheGetFileHeader@@YAJPEAVCacheBuffer@@PEAU_LOCK_BOX_FILE_HEADER@@@Z; CacheGetFileHeader(CacheBuffer *,_LOCK_BOX_FILE_HEADER *)
0x14006397d  mov     ebx, eax
0x14006397f  test    eax, eax
0x140063981  jns     short loc_1400639A6
0x140063983  mov     rcx, [rsp+118h]; this
0x14006398b  mov     r9d, eax; char *
0x14006398e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140063995  mov     edx, 48Ch; void *
0x14006399a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006399f  mov     eax, ebx
0x1400639a1  jmp     loc_140063BE9
0x1400639a6  mov     rbx, [rsp+118h+var_58]
0x1400639ae  add     rbx, 478h
0x1400639b5  mov     r15, [rsp+118h+var_80]
0x1400639bd  xor     r13b, r13b
0x1400639c0  mov     r12, [rsp+118h+var_78]
0x1400639c8  test    r15, r15
0x1400639cb  jz      loc_140063B5F
0x1400639d1  lea     rcx, [rsp+118h+hMem]
0x1400639d6  call    ??$make_unique_hlocal@U_LOCK_BOX_RECORD_HEADER@@$$V@wil@@YA?AV?$unique_ptr@U_LOCK_BOX_RECORD_HEADER@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@XZ; wil::make_unique_hlocal<_LOCK_BOX_RECORD_HEADER,>(void)
0x1400639db  nop
0x1400639dc  mov     r9d, 98h; unsigned int
0x1400639e2  mov     r8, [rsp+118h+hMem]; struct _LOCK_BOX_RECORD_HEADER *
0x1400639e7  mov     rdx, rbx; union _LARGE_INTEGER
0x1400639ea  mov     rcx, rsi; this
0x1400639ed  call    ?CacheGetRecordHeader@@YAJPEAVCacheBuffer@@T_LARGE_INTEGER@@PEAU_LOCK_BOX_RECORD_HEADER@@_K@Z; CacheGetRecordHeader(CacheBuffer *,_LARGE_INTEGER,_LOCK_BOX_RECORD_HEADER *,unsigned __int64)
0x1400639f2  mov     edi, eax
0x1400639f4  test    eax, eax
0x1400639f6  jns     short loc_140063A3B
0x1400639f8  mov     rcx, [rsp+118h]; this
0x140063a00  mov     r9d, eax; char *
0x140063a03  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140063a0a  mov     edx, 49Bh; void *
0x140063a0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140063a14  nop
0x140063a15  mov     rcx, [rsp+118h+hMem]; hMem
0x140063a1a  mov     [rsp+118h+hMem], 0
0x140063a23  test    rcx, rcx
0x140063a26  jz      short loc_140063A34
0x140063a28  call    cs:__imp_LocalFree
0x140063a2f  nop     dword ptr [rax+rax+00h]
0x140063a34  mov     eax, edi
0x140063a36  jmp     loc_140063BE9
0x140063a3b  mov     rcx, [rsp+118h+hMem]
0x140063a40  test    byte ptr [rcx+10h], 1
0x140063a44  jnz     loc_140063B35
0x140063a4a  mov     [rsp+118h+var_E8], 0
0x140063a4f  lea     r8, [rcx+48h]; struct _WINBIO_IDENTITY *
0x140063a53  lea     rax, [rsp+118h+var_E8]
0x140063a58  mov     qword ptr [rsp+118h+var_F8], rax; int
0x140063a5d  mov     r9b, [rcx+94h]; unsigned __int8
0x140063a64  mov     dl, [rsp+118h+var_E7]; unsigned __int8
0x140063a68  mov     rcx, r14; struct _WINBIO_IDENTITY *
0x140063a6b  call    ?MatchIdentity@@YAJPEAU_WINBIO_IDENTITY@@E0EPEAE@Z; MatchIdentity(_WINBIO_IDENTITY *,uchar,_WINBIO_IDENTITY *,uchar,uchar *)
0x140063a70  mov     edi, eax
0x140063a72  test    eax, eax
0x140063a74  jns     short loc_140063AB9
0x140063a76  mov     rcx, [rsp+118h]; this
0x140063a7e  mov     r9d, eax; char *
0x140063a81  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140063a88  mov     edx, 4A7h; void *
0x140063a8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140063a92  nop
0x140063a93  mov     rcx, [rsp+118h+hMem]; hMem
0x140063a98  mov     [rsp+118h+hMem], 0
0x140063aa1  test    rcx, rcx
0x140063aa4  jz      short loc_140063AB2
0x140063aa6  call    cs:__imp_LocalFree
0x140063aad  nop     dword ptr [rax+rax+00h]
0x140063ab2  mov     eax, edi
0x140063ab4  jmp     loc_140063BE9
0x140063ab9  cmp     [rsp+118h+var_E8], 0
0x140063abe  jz      short loc_140063B30
0x140063ac0  mov     rax, [rsp+118h+hMem]
0x140063ac5  or      dword ptr [rax+10h], 1
0x140063ac9  mov     r8, [rsp+118h+hMem]; struct _LOCK_BOX_RECORD_HEADER *
0x140063ace  mov     rdx, rbx; union _LARGE_INTEGER
0x140063ad1  mov     rcx, rsi; struct CacheBuffer *
0x140063ad4  call    ?CacheReplaceRecordHeader@@YAJPEAVCacheBuffer@@T_LARGE_INTEGER@@PEAU_LOCK_BOX_RECORD_HEADER@@@Z; CacheReplaceRecordHeader(CacheBuffer *,_LARGE_INTEGER,_LOCK_BOX_RECORD_HEADER *)
0x140063ad9  mov     edi, eax
0x140063adb  test    eax, eax
0x140063add  jns     short loc_140063B22
0x140063adf  mov     rcx, [rsp+118h]; this
0x140063ae7  mov     r9d, eax; char *
0x140063aea  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140063af1  mov     edx, 4AFh; void *
0x140063af6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140063afb  nop
0x140063afc  mov     rcx, [rsp+118h+hMem]; hMem
0x140063b01  mov     [rsp+118h+hMem], 0
0x140063b0a  test    rcx, rcx
0x140063b0d  jz      short loc_140063B1B
0x140063b0f  call    cs:__imp_LocalFree
0x140063b16  nop     dword ptr [rax+rax+00h]
0x140063b1b  mov     eax, edi
0x140063b1d  jmp     loc_140063BE9
0x140063b22  inc     r12
0x140063b25  mov     [rsp+118h+var_78], r12
0x140063b2d  mov     r13b, 1
0x140063b30  mov     rcx, [rsp+118h+hMem]; hMem
0x140063b35  add     rbx, [rcx+18h]
0x140063b39  dec     r15
0x140063b3c  mov     [rsp+118h+hMem], 0
0x140063b45  test    rcx, rcx
0x140063b48  jz      loc_1400639C8
0x140063b4e  call    cs:__imp_LocalFree
0x140063b55  nop     dword ptr [rax+rax+00h]
0x140063b5a  jmp     loc_1400639C8
0x140063b5f  test    r13b, r13b
0x140063b62  jnz     short loc_140063B89
0x140063b64  mov     rcx, [rsp+118h]; this
0x140063b6c  mov     ebx, 8009801Bh
0x140063b71  mov     r9d, ebx; char *
0x140063b74  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140063b7b  mov     edx, 4BCh; void *
0x140063b80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140063b85  mov     eax, ebx
0x140063b87  jmp     short loc_140063BE9
0x140063b89  lea     rdx, [rsp+118h+var_C8]; struct _LOCK_BOX_FILE_HEADER *
0x140063b8e  mov     rcx, rsi; struct CacheBuffer *
0x140063b91  call    ?CacheReplaceFileHeader@@YAJPEAVCacheBuffer@@PEAU_LOCK_BOX_FILE_HEADER@@@Z; CacheReplaceFileHeader(CacheBuffer *,_LOCK_BOX_FILE_HEADER *)
0x140063b96  mov     ebx, eax
0x140063b98  test    eax, eax
0x140063b9a  jns     short loc_140063BBC
0x140063b9c  mov     rcx, [rsp+118h]; this
0x140063ba4  mov     r9d, eax; char *
0x140063ba7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140063bae  mov     edx, 4C1h; void *
0x140063bb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140063bb8  mov     eax, ebx
0x140063bba  jmp     short loc_140063BE9
0x140063bbc  xor     eax, eax
0x140063bbe  jmp     short loc_140063BE9
0x140063bc0  mov     rcx, [rsp+118h]; this
0x140063bc8  mov     ebx, 80070057h
0x140063bcd  mov     r9d, ebx; char *
0x140063bd0  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140063bd7  mov     edx, 484h; void *
0x140063bdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140063be1  mov     eax, ebx
0x140063be3  jmp     short loc_140063BE9
0x140063be5  mov     eax, dword ptr [rsp+118h+hMem]
0x140063be9  mov     rcx, [rsp+118h+var_48]
0x140063bf1  xor     rcx, rsp; StackCookie
0x140063bf4  call    __security_check_cookie
0x140063bf9  add     rsp, 0E0h
0x140063c00  pop     r15
0x140063c02  pop     r14
0x140063c04  pop     r13
0x140063c06  pop     r12
0x140063c08  pop     rdi
0x140063c09  pop     rsi
0x140063c0a  pop     rbx
0x140063c0b  retn
```
