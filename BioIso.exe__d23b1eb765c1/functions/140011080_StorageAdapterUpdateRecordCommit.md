# StorageAdapterUpdateRecordCommit

- ea: `0x140011080`
- end: `0x1400115b0`
- name: `StorageAdapterUpdateRecordCommit`
- size: `1328`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x14000a2e4`
- `0x14000a420`
- `0x14001019c`
- `0x14001101c`
- `0x140011080`
- `0x140011b1c`
- `0x14001bd40`
- `0x14001cb78`
- `0x14001cb90`
- `0x140058558`
- `0x140058624`
- `0x140058810`
- `0x14005885c`
- `0x14007dcf8`
- `0x14007dd74`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400113af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011411`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400114e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011510`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400113af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011411`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400114e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011510`

## string_xrefs

- `0x1400110e5`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140011113`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140011168`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400111c5`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14001138e`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400113f0`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140011457`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400114c3`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14001153a`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140011569`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall StorageAdapterUpdateRecordCommit(__int64 a1, _OWORD **a2)
{
  __int64 v4; // rcx
  int Current; // eax
  unsigned int v7; // edi
  struct _LOCK_BOX_RECORD_HEADER *v8; // rdi
  int matched; // eax
  unsigned int v10; // esi
  _OWORD *v11; // rcx
  unsigned __int64 v12; // r14
  char *v13; // r13
  struct _WINBIO_IDENTITY *v14; // rax
  _OWORD *v15; // r8
  size_t v16; // r8
  CacheBuffer *v17; // rsi
  LONGLONG v18; // rbx
  unsigned __int64 v19; // rax
  int FileHeader; // eax
  unsigned int v21; // r15d
  HLOCAL v22; // rcx
  int v23; // eax
  unsigned int v24; // ebx
  HLOCAL v25; // rcx
  int v26; // eax
  unsigned int v27; // ebx
  HLOCAL v28; // rcx
  int v29; // eax
  unsigned int v30; // ebx
  HLOCAL v31; // rcx
  HLOCAL v32; // rcx
  int v33; // [rsp+20h] [rbp-108h]
  int v34; // [rsp+20h] [rbp-108h]
  unsigned __int8 v35[8]; // [rsp+30h] [rbp-F8h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-F0h] BYREF
  __int64 v37; // [rsp+40h] [rbp-E8h] BYREF
  union _LARGE_INTEGER v38; // [rsp+48h] [rbp-E0h] BYREF
  struct _LOCK_BOX_RECORD_HEADER *v39; // [rsp+50h] [rbp-D8h] BYREF
  std::_Ref_count_base *v40; // [rsp+58h] [rbp-D0h]
  __int64 *v41; // [rsp+60h] [rbp-C8h]
  char v42; // [rsp+68h] [rbp-C0h]
  _BYTE v43[72]; // [rsp+70h] [rbp-B8h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-70h]
  __int64 v45; // [rsp+C0h] [rbp-68h]
  __int64 v46; // [rsp+D0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  if ( !a1 || !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F6,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80004003LL,
      v33);
    return 2147500035LL;
  }
  v4 = *(_QWORD *)(a1 + 64);
  v37 = v4;
  if ( !v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6FB,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x8009800FLL,
      v33);
    return 2148106255LL;
  }
  if ( !*(_BYTE *)(v4 + 80) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6FF,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x8009800FLL,
      v33);
    return 2148106255LL;
  }
  v41 = &v37;
  v42 = 1;
  v39 = 0;
  v38.QuadPart = 0;
  Current = ResGetCurrent((struct _RESULT_SET *)(v4 + 48), &v39, &v38);
  v7 = Current;
  if ( Current < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70B,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)(unsigned int)Current,
      v33);
    *(_BYTE *)(v37 + 80) = 0;
    return v7;
  }
  v35[0] = 0;
  v8 = v39;
  matched = MatchIdentity(
              (struct _WINBIO_IDENTITY *)*a2,
              *((_BYTE *)a2 + 8),
              (struct _WINBIO_IDENTITY *)((char *)v39 + 72),
              *((_BYTE *)v39 + 148),
              v35);
  v10 = matched;
  if ( matched < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x715,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)(unsigned int)matched,
      v34);
    *(_BYTE *)(v37 + 80) = 0;
    return v10;
  }
  if ( !v35[0] || (v11 = a2[3], *((_OWORD **)v8 + 8) != v11) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71A,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x8009801BLL,
      v34);
    *(_BYTE *)(v37 + 80) = 0;
    return 2148106267LL;
  }
  v12 = (unsigned __int64)a2[5] + 4 * ((_QWORD)v11 + 38) + (_QWORD)a2[7];
  wil::make_unique_hlocal<unsigned char [0]>(&hMem, v12);
  v13 = (char *)hMem;
  *(_OWORD *)hMem = xmmword_14008EBE8;
  *((_QWORD *)v13 + 3) = (unsigned int)v12;
  *((_QWORD *)v13 + 4) = 4LL * (_QWORD)a2[3] + 152;
  *((_QWORD *)v13 + 8) = a2[3];
  *((_QWORD *)v13 + 5) = a2[5];
  *((_QWORD *)v13 + 7) = a2[7];
  v14 = (struct _WINBIO_IDENTITY *)*a2;
  *(_OWORD *)(v13 + 72) = **a2;
  *(_OWORD *)(v13 + 88) = *(_OWORD *)&v14->Value.AccountSid.Data[8];
  *(_OWORD *)(v13 + 104) = *(_OWORD *)&v14->Value.AccountSid.Data[24];
  *(_OWORD *)(v13 + 120) = *(_OWORD *)&v14->Value.AccountSid.Data[40];
  *(_OWORD *)(v13 + 132) = *(_OWORD *)&v14->Value.AccountSid.Data[52];
  v13[148] = *((_BYTE *)a2 + 8);
  v15 = a2[3];
  if ( v15 )
    memcpy_0((char *)hMem + 152, a2[2], 4LL * (_QWORD)v15);
  memcpy_0((char *)hMem + 4 * (_QWORD)a2[3] + 152, a2[4], (size_t)a2[5]);
  v16 = (size_t)a2[7];
  if ( v16 )
    memcpy_0((char *)a2[5] + 4 * (_QWORD)a2[3] + (_QWORD)hMem + 152, a2[6], v16);
  v17 = (CacheBuffer *)(*(_QWORD *)WinBioFramework::PipelineToPipelineObject(&v39, a1) + 1296LL);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  v18 = v38.QuadPart - *((_QWORD *)v8 + 4);
  v19 = *((_QWORD *)v8 + 3);
  if ( v12 <= v19 )
  {
    *((_QWORD *)v13 + 3) = v19;
    CacheBuffer::Replace(v17, v18, (unsigned __int8 *)hMem, v12);
LABEL_37:
    v32 = hMem;
    hMem = 0;
    if ( v32 )
      LocalFree(v32);
    *(_BYTE *)(v37 + 80) = 0;
    return 0;
  }
  memset_0(v43, 0, 0x78u);
  FileHeader = CacheGetFileHeader(v17, (struct _LOCK_BOX_FILE_HEADER *)v43);
  v21 = FileHeader;
  if ( FileHeader >= 0 )
  {
    *((_DWORD *)v8 + 4) |= 1u;
    v23 = CacheReplaceRecordHeader(v17, (union _LARGE_INTEGER)v18, v8);
    v24 = v23;
    if ( v23 >= 0 )
    {
      ++v45;
      v26 = CacheAddRecord(v17, (unsigned __int8 *)hMem, v12);
      v27 = v26;
      if ( v26 >= 0 )
      {
        ++v44;
        v46 += v12;
        v29 = CacheReplaceFileHeader(v17, (struct _LOCK_BOX_FILE_HEADER *)v43);
        v30 = v29;
        if ( v29 >= 0 )
          goto LABEL_37;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x784,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
          (const char *)(unsigned int)v29,
          v34);
        v31 = hMem;
        hMem = 0;
        if ( v31 )
          LocalFree(v31);
        *(_BYTE *)(v37 + 80) = 0;
        return v30;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x77D,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
          (const char *)(unsigned int)v26,
          v34);
        v28 = hMem;
        hMem = 0;
        if ( v28 )
          LocalFree(v28);
        *(_BYTE *)(v37 + 80) = 0;
        return v27;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x775,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
        (const char *)(unsigned int)v23,
        v34);
      v25 = hMem;
      hMem = 0;
      if ( v25 )
        LocalFree(v25);
      *(_BYTE *)(v37 + 80) = 0;
      return v24;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76D,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)(unsigned int)FileHeader,
      v34);
    v22 = hMem;
    hMem = 0;
    if ( v22 )
      LocalFree(v22);
    *(_BYTE *)(v37 + 80) = 0;
    return v21;
  }
}

```

## disassembly

```asm
0x140011080  mov     [rsp+arg_10], rbx
0x140011085  mov     [rsp+arg_18], rsi
0x14001108a  push    rdi
0x14001108b  push    r12
0x14001108d  push    r13
0x14001108f  push    r14
0x140011091  push    r15
0x140011093  sub     rsp, 100h
0x14001109a  mov     rax, cs:__security_cookie
0x1400110a1  xor     rax, rsp
0x1400110a4  mov     [rsp+128h+var_38], rax
0x1400110ac  mov     rbx, rdx
0x1400110af  mov     r15, rcx
0x1400110b2  xor     r14d, r14d
0x1400110b5  test    rcx, rcx
0x1400110b8  jz      loc_140011559
0x1400110be  test    rdx, rdx
0x1400110c1  jz      loc_140011559
0x1400110c7  mov     rcx, [rcx+40h]
0x1400110cb  mov     [rsp+128h+var_E8], rcx
0x1400110d0  test    rcx, rcx
0x1400110d3  jnz     short loc_1400110FD
0x1400110d5  mov     rcx, [rsp+128h]; this
0x1400110dd  mov     ebx, 8009800Fh
0x1400110e2  mov     r9d, ebx; char *
0x1400110e5  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400110ec  mov     edx, 6FBh; void *
0x1400110f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400110f6  mov     eax, ebx
0x1400110f8  jmp     loc_140011582
0x1400110fd  cmp     [rcx+50h], r14b
0x140011101  jnz     short loc_14001112B
0x140011103  mov     rcx, [rsp+128h]; this
0x14001110b  mov     ebx, 8009800Fh
0x140011110  mov     r9d, ebx; char *
0x140011113  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14001111a  mov     edx, 6FFh; void *
0x14001111f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011124  mov     eax, ebx
0x140011126  jmp     loc_140011582
0x14001112b  lea     rax, [rsp+128h+var_E8]
0x140011130  mov     [rsp+128h+var_C8], rax
0x140011135  mov     [rsp+128h+var_C0], 1
0x14001113a  mov     [rsp+128h+var_D8], r14
0x14001113f  mov     qword ptr [rsp+128h+var_E0], r14
0x140011144  add     rcx, 30h ; '0'; struct _RESULT_SET *
0x140011148  lea     r8, [rsp+128h+var_E0]; union _LARGE_INTEGER *
0x14001114d  lea     rdx, [rsp+128h+var_D8]; struct _LOCK_BOX_RECORD_HEADER **
0x140011152  call    ?ResGetCurrent@@YAJPEAU_RESULT_SET@@PEAPEAU_LOCK_BOX_RECORD_HEADER@@PEAT_LARGE_INTEGER@@@Z; ResGetCurrent(_RESULT_SET *,_LOCK_BOX_RECORD_HEADER * *,_LARGE_INTEGER *)
0x140011157  mov     edi, eax
0x140011159  test    eax, eax
0x14001115b  jns     short loc_14001118A
0x14001115d  mov     rcx, [rsp+128h]; this
0x140011165  mov     r9d, eax; char *
0x140011168  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14001116f  mov     edx, 70Bh; void *
0x140011174  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011179  nop
0x14001117a  mov     rcx, [rsp+128h+var_E8]
0x14001117f  mov     [rcx+50h], r14b
0x140011183  mov     eax, edi
0x140011185  jmp     loc_140011582
0x14001118a  mov     [rsp+128h+var_F8], r14b
0x14001118f  mov     rdi, [rsp+128h+var_D8]
0x140011194  lea     r8, [rdi+48h]; struct _WINBIO_IDENTITY *
0x140011198  lea     rax, [rsp+128h+var_F8]
0x14001119d  mov     qword ptr [rsp+128h+var_108], rax; int
0x1400111a2  mov     r9b, [rdi+94h]; unsigned __int8
0x1400111a9  mov     dl, [rbx+8]; unsigned __int8
0x1400111ac  mov     rcx, [rbx]; struct _WINBIO_IDENTITY *
0x1400111af  call    ?MatchIdentity@@YAJPEAU_WINBIO_IDENTITY@@E0EPEAE@Z; MatchIdentity(_WINBIO_IDENTITY *,uchar,_WINBIO_IDENTITY *,uchar,uchar *)
0x1400111b4  mov     esi, eax
0x1400111b6  test    eax, eax
0x1400111b8  jns     short loc_1400111E7
0x1400111ba  mov     rcx, [rsp+128h]; this
0x1400111c2  mov     r9d, eax; char *
0x1400111c5  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400111cc  mov     edx, 715h; void *
0x1400111d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400111d6  nop
0x1400111d7  mov     rcx, [rsp+128h+var_E8]
0x1400111dc  mov     [rcx+50h], r14b
0x1400111e0  mov     eax, esi
0x1400111e2  jmp     loc_140011582
0x1400111e7  cmp     [rsp+128h+var_F8], r14b
0x1400111ec  jz      loc_14001152A
0x1400111f2  mov     rcx, [rbx+18h]
0x1400111f6  cmp     [rdi+40h], rcx
0x1400111fa  jnz     loc_14001152A
0x140011200  mov     rax, [rbx+28h]
0x140011204  add     rcx, 26h ; '&'
0x140011208  lea     r14, [rax+rcx*4]
0x14001120c  add     r14, [rbx+38h]
0x140011210  mov     rdx, r14
0x140011213  lea     rcx, [rsp+128h+hMem]
0x140011218  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x14001121d  nop
0x14001121e  mov     r13, [rsp+128h+hMem]
0x140011223  movups  xmm0, cs:xmmword_14008EBE8
0x14001122a  movdqu  xmmword ptr [r13+0], xmm0
0x140011230  mov     r12d, r14d
0x140011233  mov     [r13+18h], r12
0x140011237  mov     rax, [rbx+18h]
0x14001123b  lea     rax, ds:98h[rax*4]
0x140011243  mov     [r13+20h], rax
0x140011247  mov     rax, [rbx+18h]
0x14001124b  mov     [r13+40h], rax
0x14001124f  mov     rax, [rbx+28h]
0x140011253  mov     [r13+28h], rax
0x140011257  mov     rax, [rbx+38h]
0x14001125b  mov     [r13+38h], rax
0x14001125f  mov     rax, [rbx]
0x140011262  movups  xmm0, xmmword ptr [rax]
0x140011265  movups  xmmword ptr [r13+48h], xmm0
0x14001126a  movups  xmm1, xmmword ptr [rax+10h]
0x14001126e  movups  xmmword ptr [r13+58h], xmm1
0x140011273  movups  xmm0, xmmword ptr [rax+20h]
0x140011277  movups  xmmword ptr [r13+68h], xmm0
0x14001127c  movups  xmm1, xmmword ptr [rax+30h]
0x140011280  movups  xmmword ptr [r13+78h], xmm1
0x140011285  movups  xmm0, xmmword ptr [rax+3Ch]
0x140011289  movups  xmmword ptr [r13+84h], xmm0
0x140011291  mov     al, [rbx+8]
0x140011294  mov     [r13+94h], al
0x14001129b  mov     r8, [rbx+18h]
0x14001129f  test    r8, r8
0x1400112a2  jz      short loc_1400112BD
0x1400112a4  shl     r8, 2; Size
0x1400112a8  mov     rcx, [rsp+128h+hMem]
0x1400112ad  add     rcx, 98h; void *
0x1400112b4  mov     rdx, [rbx+10h]; Src
0x1400112b8  call    memcpy_0
0x1400112bd  mov     rcx, [rbx+18h]
0x1400112c1  mov     rax, [rsp+128h+hMem]
0x1400112c6  add     rax, 98h
0x1400112cc  lea     rcx, [rax+rcx*4]; void *
0x1400112d0  mov     r8, [rbx+28h]; Size
0x1400112d4  mov     rdx, [rbx+20h]; Src
0x1400112d8  call    memcpy_0
0x1400112dd  mov     r8, [rbx+38h]; Size
0x1400112e1  test    r8, r8
0x1400112e4  jz      short loc_140011306
0x1400112e6  mov     rcx, [rbx+18h]
0x1400112ea  mov     rax, [rbx+28h]
0x1400112ee  add     rax, 98h
0x1400112f4  lea     rcx, [rax+rcx*4]
0x1400112f8  add     rcx, [rsp+128h+hMem]; void *
0x1400112fd  mov     rdx, [rbx+30h]; Src
0x140011301  call    memcpy_0
0x140011306  mov     rdx, r15
0x140011309  lea     rcx, [rsp+128h+var_D8]
0x14001130e  call    WinBioFramework__PipelineToPipelineObject
0x140011313  mov     rsi, [rax]
0x140011316  add     rsi, 510h
0x14001131d  mov     rcx, [rsp+128h+var_D0]; this
0x140011322  test    rcx, rcx
0x140011325  jz      short loc_14001132C
0x140011327  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001132c  mov     rbx, qword ptr [rsp+128h+var_E0]
0x140011331  sub     rbx, [rdi+20h]
0x140011335  mov     rax, [rdi+18h]
0x140011339  cmp     r14, rax
0x14001133c  ja      short loc_14001135C
0x14001133e  mov     [r13+18h], rax
0x140011342  mov     r9d, r12d; unsigned int
0x140011345  mov     r8, [rsp+128h+hMem]; unsigned __int8 *
0x14001134a  mov     edx, ebx; unsigned int
0x14001134c  mov     rcx, rsi; this
0x14001134f  call    ?Replace@CacheBuffer@@QEAAJKPEAEK@Z; CacheBuffer::Replace(ulong,uchar *,ulong)
0x140011354  xor     r12d, r12d
0x140011357  jmp     loc_140011501
0x14001135c  xor     edx, edx; Val
0x14001135e  lea     r8d, [rdx+78h]; Size
0x140011362  lea     rcx, [rsp+128h+var_B8]; void *
0x140011367  call    memset_0
0x14001136c  lea     rdx, [rsp+128h+var_B8]; struct _LOCK_BOX_FILE_HEADER *
0x140011371  mov     rcx, rsi; struct CacheBuffer *
0x140011374  call    ?CacheGetFileHeader@@YAJPEAVCacheBuffer@@PEAU_LOCK_BOX_FILE_HEADER@@@Z; CacheGetFileHeader(CacheBuffer *,_LOCK_BOX_FILE_HEADER *)
0x140011379  mov     r15d, eax
0x14001137c  xor     r12d, r12d
0x14001137f  test    eax, eax
0x140011381  jns     short loc_1400113CD
0x140011383  mov     rcx, [rsp+128h]; this
0x14001138b  mov     r9d, eax; char *
0x14001138e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140011395  mov     edx, 76Dh; void *
0x14001139a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001139f  nop
0x1400113a0  mov     rcx, [rsp+128h+hMem]; hMem
0x1400113a5  mov     [rsp+128h+hMem], r12
0x1400113aa  test    rcx, rcx
0x1400113ad  jz      short loc_1400113BC
0x1400113af  call    cs:__imp_LocalFree
0x1400113b6  nop     dword ptr [rax+rax+00h]
0x1400113bb  nop
0x1400113bc  mov     rax, [rsp+128h+var_E8]
0x1400113c1  mov     [rax+50h], r12b
0x1400113c5  mov     eax, r15d
0x1400113c8  jmp     loc_140011582
0x1400113cd  or      dword ptr [rdi+10h], 1
0x1400113d1  mov     r8, rdi; struct _LOCK_BOX_RECORD_HEADER *
0x1400113d4  mov     rdx, rbx; union _LARGE_INTEGER
0x1400113d7  mov     rcx, rsi; struct CacheBuffer *
0x1400113da  call    ?CacheReplaceRecordHeader@@YAJPEAVCacheBuffer@@T_LARGE_INTEGER@@PEAU_LOCK_BOX_RECORD_HEADER@@@Z; CacheReplaceRecordHeader(CacheBuffer *,_LARGE_INTEGER,_LOCK_BOX_RECORD_HEADER *)
0x1400113df  mov     ebx, eax
0x1400113e1  test    eax, eax
0x1400113e3  jns     short loc_14001142E
0x1400113e5  mov     rcx, [rsp+128h]; this
0x1400113ed  mov     r9d, eax; char *
0x1400113f0  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400113f7  mov     edx, 775h; void *
0x1400113fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011401  nop
0x140011402  mov     rcx, [rsp+128h+hMem]; hMem
0x140011407  mov     [rsp+128h+hMem], r12
0x14001140c  test    rcx, rcx
0x14001140f  jz      short loc_14001141E
0x140011411  call    cs:__imp_LocalFree
0x140011418  nop     dword ptr [rax+rax+00h]
0x14001141d  nop
0x14001141e  mov     rax, [rsp+128h+var_E8]
0x140011423  mov     [rax+50h], r12b
0x140011427  mov     eax, ebx
0x140011429  jmp     loc_140011582
0x14001142e  inc     [rsp+128h+var_68]
0x140011436  mov     r8, r14; unsigned __int64
0x140011439  mov     rdx, [rsp+128h+hMem]; unsigned __int8 *
0x14001143e  mov     rcx, rsi; struct CacheBuffer *
0x140011441  call    ?CacheAddRecord@@YAJPEAVCacheBuffer@@PEAE_K@Z; CacheAddRecord(CacheBuffer *,uchar *,unsigned __int64)
0x140011446  mov     ebx, eax
0x140011448  test    eax, eax
0x14001144a  jns     short loc_140011495
0x14001144c  mov     rcx, [rsp+128h]; this
0x140011454  mov     r9d, eax; char *
0x140011457  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14001145e  mov     edx, 77Dh; void *
0x140011463  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011468  nop
0x140011469  mov     rcx, [rsp+128h+hMem]; hMem
0x14001146e  mov     [rsp+128h+hMem], r12
0x140011473  test    rcx, rcx
0x140011476  jz      short loc_140011485
0x140011478  call    cs:__imp_LocalFree
0x14001147f  nop     dword ptr [rax+rax+00h]
0x140011484  nop
0x140011485  mov     rax, [rsp+128h+var_E8]
0x14001148a  mov     [rax+50h], r12b
0x14001148e  mov     eax, ebx
0x140011490  jmp     loc_140011582
0x140011495  inc     [rsp+128h+var_70]
0x14001149d  add     [rsp+128h+var_58], r14
0x1400114a5  lea     rdx, [rsp+128h+var_B8]; struct _LOCK_BOX_FILE_HEADER *
0x1400114aa  mov     rcx, rsi; struct CacheBuffer *
0x1400114ad  call    ?CacheReplaceFileHeader@@YAJPEAVCacheBuffer@@PEAU_LOCK_BOX_FILE_HEADER@@@Z; CacheReplaceFileHeader(CacheBuffer *,_LOCK_BOX_FILE_HEADER *)
0x1400114b2  mov     ebx, eax
0x1400114b4  test    eax, eax
0x1400114b6  jns     short loc_140011501
0x1400114b8  mov     rcx, [rsp+128h]; this
0x1400114c0  mov     r9d, eax; char *
0x1400114c3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400114ca  mov     edx, 784h; void *
0x1400114cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400114d4  nop
0x1400114d5  mov     rcx, [rsp+128h+hMem]; hMem
0x1400114da  mov     [rsp+128h+hMem], r12
0x1400114df  test    rcx, rcx
0x1400114e2  jz      short loc_1400114F1
0x1400114e4  call    cs:__imp_LocalFree
0x1400114eb  nop     dword ptr [rax+rax+00h]
0x1400114f0  nop
0x1400114f1  mov     rax, [rsp+128h+var_E8]
0x1400114f6  mov     [rax+50h], r12b
0x1400114fa  mov     eax, ebx
0x1400114fc  jmp     loc_140011582
0x140011501  mov     rcx, [rsp+128h+hMem]; hMem
0x140011506  mov     [rsp+128h+hMem], r12
0x14001150b  test    rcx, rcx
0x14001150e  jz      short loc_14001151D
0x140011510  call    cs:__imp_LocalFree
0x140011517  nop     dword ptr [rax+rax+00h]
0x14001151c  nop
0x14001151d  mov     rax, [rsp+128h+var_E8]
0x140011522  mov     [rax+50h], r12b
0x140011526  xor     eax, eax
0x140011528  jmp     short loc_140011582
0x14001152a  mov     rcx, [rsp+128h]; this
0x140011532  mov     ebx, 8009801Bh
0x140011537  mov     r9d, ebx; char *
0x14001153a  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140011541  mov     edx, 71Ah; void *
0x140011546  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001154b  nop
0x14001154c  mov     rcx, [rsp+128h+var_E8]
0x140011551  mov     [rcx+50h], r14b
0x140011555  mov     eax, ebx
0x140011557  jmp     short loc_140011582
0x140011559  mov     rcx, [rsp+128h]; this
0x140011561  mov     ebx, 80004003h
0x140011566  mov     r9d, ebx; char *
0x140011569  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
  ... truncated ...
```
