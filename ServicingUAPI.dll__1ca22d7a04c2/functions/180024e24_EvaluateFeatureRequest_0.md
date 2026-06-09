# EvaluateFeatureRequest_0

- ea: `0x180024e24`
- end: `0x18002572a`
- name: `EvaluateFeatureRequest_0`
- size: `2310`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180025984`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x180006198`
- `0x180009750`
- `0x18000aedc`
- `0x18000c468`
- `0x180012218`
- `0x1800126b8`
- `0x1800126d4`
- `0x18001ba80`
- `0x18001c1d0`
- `0x18001d3dc`
- `0x18001d650`
- `0x180023390`
- `0x180024334`
- `0x180024e24`
- `0x18002bc54`
- `0x18002c0d0`
- `0x18002dfe0`
- `0x18002fee4`
- `0x180070f18`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180024f47`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180024f47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002563a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002566d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002563a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002566d`

## string_xrefs

- `0x180025280`: `ActionList.xml`
- `0x180024f88`: `CbsTemp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall EvaluateFeatureRequest_0(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6,
        _QWORD *a7,
        void *a8,
        __int64 *a9,
        _QWORD *a10)
{
  __int64 v11; // r15
  _QWORD *v12; // rdi
  int v13; // eax
  wil::details::in1diag3 *v14; // rcx
  WCHAR *v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // r8
  const char *v18; // r9
  __int128 *v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  int TemporaryFileName; // eax
  __int64 *v23; // rbx
  __int64 v24; // rsi
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 *v27; // rbx
  __int64 v28; // rsi
  __int64 v29; // rcx
  const char *v30; // r9
  wchar_t *v31; // r12
  __int64 v32; // rcx
  _QWORD *v33; // rax
  _QWORD *v34; // rax
  __int64 Path; // rax
  int v36; // esi
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r10
  _QWORD *v40; // rdx
  _QWORD *v41; // r8
  __int64 v42; // r9
  __int64 v43; // r9
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  void (__fastcall ***v50)(_QWORD, __int64, __int64, __int64); // rcx
  _DWORD *v51; // rax
  int v52; // eax
  unsigned int v53; // esi
  _QWORD *v54; // rbx
  _QWORD *v55; // r8
  int v56; // eax
  int v57; // [rsp+28h] [rbp-E0h]
  int v58; // [rsp+28h] [rbp-E0h]
  int v59; // [rsp+28h] [rbp-E0h]
  _QWORD v61[3]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v62; // [rsp+88h] [rbp-80h]
  __int128 v63; // [rsp+90h] [rbp-78h] BYREF
  __int64 v64; // [rsp+A0h] [rbp-68h]
  wchar_t *v65; // [rsp+A8h] [rbp-60h]
  _QWORD v66[2]; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD v67[2]; // [rsp+C0h] [rbp-48h] BYREF
  _QWORD v68[2]; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD v69[2]; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD v70[2]; // [rsp+F0h] [rbp-18h] BYREF
  _QWORD v71[2]; // [rsp+100h] [rbp-8h] BYREF
  _QWORD v72[2]; // [rsp+110h] [rbp+8h] BYREF
  _QWORD v73[4]; // [rsp+120h] [rbp+18h] BYREF
  _BYTE v74[40]; // [rsp+140h] [rbp+38h] BYREF
  void **v75; // [rsp+168h] [rbp+60h] BYREF
  int v76; // [rsp+170h] [rbp+68h]
  __int64 v77; // [rsp+178h] [rbp+70h]
  __int64 v78; // [rsp+180h] [rbp+78h]
  int v79; // [rsp+188h] [rbp+80h]
  __int64 v80; // [rsp+190h] [rbp+88h]
  __int64 v81; // [rsp+198h] [rbp+90h]
  int v82; // [rsp+1A0h] [rbp+98h]
  __int128 v83; // [rsp+1A8h] [rbp+A0h]
  int v84; // [rsp+1B8h] [rbp+B0h]
  __int64 v85; // [rsp+1C0h] [rbp+B8h]
  int v86; // [rsp+1C8h] [rbp+C0h]
  LPVOID pv; // [rsp+1D0h] [rbp+C8h]
  __int64 v88; // [rsp+1D8h] [rbp+D0h] BYREF
  __int128 v89; // [rsp+1E0h] [rbp+D8h] BYREF
  __int64 v90; // [rsp+1F0h] [rbp+E8h]
  LPVOID v91; // [rsp+1F8h] [rbp+F0h] BYREF
  __int128 v92; // [rsp+200h] [rbp+F8h] BYREF
  __int64 v93; // [rsp+210h] [rbp+108h]
  unsigned __int64 v94; // [rsp+218h] [rbp+110h]
  _QWORD v95[4]; // [rsp+220h] [rbp+118h] BYREF
  _QWORD v96[4]; // [rsp+240h] [rbp+138h] BYREF
  int v97[10]; // [rsp+260h] [rbp+158h] BYREF
  WCHAR Buffer[264]; // [rsp+288h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E0h] [rbp+3D8h]

  v73[2] = -2;
  v86 = a3;
  v11 = a2;
  v88 = a2;
  v12 = a7;
  pv = a8;
  v91 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)a1 + 88LL))(a1, &v91);
  v14 = retaddr;
  if ( v13 < 0 )
LABEL_84:
    wil::details::in1diag3::Throw_Hr(
      v14,
      (void *)0x28A,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_desktop.cpp",
      (const char *)(unsigned int)v13,
      v57);
  v92 = 0;
  v93 = 0;
  v94 = 7;
  LOWORD(v92) = 0;
  if ( (*(_BYTE *)(v11 + 160) & 1) != 0 )
  {
    v15 = *(WCHAR **)(v11 + 192);
    v16 = -1;
    v17 = -1;
    do
      ++v17;
    while ( v15[v17] );
  }
  else
  {
    memset_0(Buffer, 0, 0x208u);
    if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x294,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_desktop.cpp",
        v18);
    v16 = -1;
    v17 = -1;
    do
      ++v17;
    while ( Buffer[v17] );
    v15 = Buffer;
  }
  std::wstring::_Assign<wchar_t>(&v92, v15, v17);
  v66[0] = L"CbsTemp";
  v66[1] = 7;
  v19 = &v92;
  if ( v94 > 7 )
    v19 = (__int128 *)v92;
  v67[0] = v19;
  v67[1] = v93;
  CreatePath(v96, v67, v66);
  v68[0] = v91;
  do
    ++v16;
  while ( *((_WORD *)v91 + v16) );
  v68[1] = v16;
  v20 = v96;
  if ( v96[3] > 7u )
    v20 = (_QWORD *)v96[0];
  v69[0] = v20;
  v69[1] = v96[2];
  CreatePath(v95, v69, v68);
  v21 = v95;
  if ( v95[3] > 7u )
    v21 = (_QWORD *)v95[0];
  v70[0] = v21;
  v70[1] = v95[2];
  TemporaryFileName = GetTemporaryFileName(v70, a7);
  if ( TemporaryFileName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29B,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_desktop.cpp",
      (const char *)(unsigned int)TemporaryFileName,
      v57);
  std::wstring::~wstring(v95);
  std::wstring::~wstring(v96);
  v89 = 0;
  v90 = 0;
  std::vector<FeatureDescriptor>::reserve(&v89, *(_QWORD *)(a4 + 8) + *(_QWORD *)(a5 + 8));
  v23 = *(__int64 **)a4;
  v24 = *(_QWORD *)a4 + 8LL * *(_QWORD *)(a4 + 8);
  v25 = *((_QWORD *)&v89 + 1);
  if ( v23 != (__int64 *)v24 )
  {
    do
    {
      v26 = *v23;
      v61[2] = 0;
      HIDWORD(v62) = 0;
      v61[1] = *(_QWORD *)(v26 + 8);
      LODWORD(v62) = *(_DWORD *)(v26 + 20);
      if ( v25 == v90 )
      {
        std::vector<ActionList::CustomInfoPair>::_Emplace_reallocate<ActionList::CustomInfoPair>(&v89, v25, &v61[1]);
        v25 = *((_QWORD *)&v89 + 1);
      }
      else
      {
        *(_OWORD *)v25 = *(_OWORD *)&v61[1];
        *(_QWORD *)(v25 + 16) = v62;
        v25 = *((_QWORD *)&v89 + 1) + 24LL;
        *((_QWORD *)&v89 + 1) += 24LL;
      }
      ++v23;
    }
    while ( v23 != (__int64 *)v24 );
    v11 = v88;
  }
  v27 = *(__int64 **)a5;
  v28 = *(_QWORD *)a5 + 8LL * *(_QWORD *)(a5 + 8);
  if ( *(_QWORD *)a5 != v28 )
  {
    do
    {
      v29 = *v27;
      *((_QWORD *)&v63 + 1) = 0;
      LODWORD(v64) = 0;
      *(_QWORD *)&v63 = *(_QWORD *)(v29 + 8);
      HIDWORD(v64) = *(_DWORD *)(v29 + 20);
      if ( v25 == v90 )
      {
        std::vector<ActionList::CustomInfoPair>::_Emplace_reallocate<ActionList::CustomInfoPair>(&v89, v25, &v63);
        v25 = *((_QWORD *)&v89 + 1);
      }
      else
      {
        *(_OWORD *)v25 = v63;
        *(_QWORD *)(v25 + 16) = v64;
        v25 = *((_QWORD *)&v89 + 1) + 24LL;
        *((_QWORD *)&v89 + 1) += 24LL;
      }
      ++v27;
    }
    while ( v27 != (__int64 *)v28 );
    v11 = v88;
  }
  v65 = 0;
  v75 = &SessionData::`vftable';
  v77 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v76 = 18;
  v78 = v89;
  v79 = -1431655765 * ((v25 - (__int64)v89) >> 3);
  v31 = SessionDataToJson((const struct SessionData *)&v75);
  v65 = v31;
  if ( !v31 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x2B8,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_desktop.cpp",
      v30);
  to_wstring(v97, v11 + 8);
  v32 = a7[2];
  if ( a7[3] <= 7u )
    v33 = a7;
  else
    v33 = (_QWORD *)*a7;
  v71[0] = v33;
  v71[1] = v32;
  DestroyDirectory(v71);
  v72[0] = L"ActionList.xml";
  v72[1] = 14;
  if ( a7[3] <= 7u )
    v34 = a7;
  else
    v34 = (_QWORD *)*a7;
  v73[0] = v34;
  v73[1] = a7[2];
  Path = CreatePath(v74, v73, v72);
  std::wstring::operator=(a10, Path);
  std::wstring::~wstring(v74);
  if ( *a9 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    goto LABEL_84;
  }
  v36 = v86 & 4;
  CallFacilitator_0(
    v11,
    2,
    (unsigned int)&v75,
    (_DWORD)v31,
    (__int64)v97,
    (__int64)a7,
    (__int64)&v92,
    (__int64)a10,
    (__int64)pv,
    (__int64)a9);
  v37 = *a9;
  v38 = *(_QWORD *)(*a9 + 64);
  v39 = v38 + 168LL * *(unsigned int *)(*a9 + 72);
  if ( v38 != v39 )
  {
    do
    {
      v40 = *(_QWORD **)(v38 + 112);
      v41 = &v40[23 * *(unsigned int *)(v38 + 120)];
      if ( v40 != v41 )
      {
        v42 = *a6;
        do
        {
          v42 += *v40;
          *a6 = v42;
          v40 += 23;
        }
        while ( v40 != v41 );
      }
      v38 += 168;
    }
    while ( v38 != v39 );
    v37 = *a9;
  }
  v43 = *a6;
  v44 = *(_QWORD *)(v37 + 88);
  v45 = v44 + 168LL * *(unsigned int *)(v37 + 96);
  if ( v44 != v45 )
  {
    v46 = a6[2];
    do
    {
      v46 += *(_QWORD *)(v44 + 8);
      a6[2] = v46;
      if ( !v43 )
        *a6 += *(_QWORD *)(v44 + 8);
      v44 += 168;
    }
    while ( v44 != v45 );
  }
  v47 = a6[2];
  a6[1] += v47 + *a6;
  v48 = *(_QWORD *)(*a9 + 104);
  v49 = v48 + 56LL * *(unsigned int *)(*a9 + 112);
  while ( v48 != v49 )
  {
    v47 -= *(_QWORD *)(v48 + 32);
    a6[2] = v47;
    v48 += 56;
  }
  if ( !v36 )
  {
    v50 = (void (__fastcall ***)(_QWORD, __int64, __int64, __int64))*a9;
    if ( *(_DWORD *)(*a9 + 72) )
    {
      if ( v50 )
      {
        (**v50)(v50, v47, v49, v43);
        *a9 = 0;
      }
      CallFacilitator_0(
        v11,
        0,
        (unsigned int)&v75,
        (_DWORD)v31,
        (__int64)v97,
        (__int64)a7,
        (__int64)&v92,
        (__int64)a10,
        (__int64)pv,
        (__int64)a9);
    }
  }
  PublishOperationProgress(v11, 1, 0, 0);
  v51 = (_DWORD *)*a9;
  if ( *(_DWORD *)(*a9 + 128) || v51[36] || v51[24] || v51[28] )
  {
    if ( v36 )
    {
      if ( (*(_BYTE *)(v11 + 160) & 1) == 0 && a6 != (__int64 *)-56LL )
        *((_DWORD *)a6 + 14) = 0;
    }
    else
    {
      v88 = 0;
      v52 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
              a1,
              &GUID_be996087_7c81_465a_9bb1_39ce7350adcd,
              &v88);
      if ( v52 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x316,
          (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_desktop.cpp",
          (const char *)(unsigned int)v52,
          v58);
      v53 = ((*(_DWORD *)(v11 + 160) & 4) << 6) | 9;
      v86 = 0;
      v54 = operator new(0x20u);
      v54[2] = 0;
      v54[3] = 0;
      *v54 = &UapiCbsUIHandler::`vftable';
      v54[1] = 0;
      *((_DWORD *)v54 + 4) = 1;
      *(_QWORD *)((char *)v54 + 20) = 0;
      v73[3] = v54;
      v54[1] = v11;
      pv = 0;
      if ( a7[3] > 7u )
        v12 = (_QWORD *)*a7;
      v55 = a10;
      if ( a10[3] > 7u )
        v55 = (_QWORD *)*a10;
      v59 = *(_QWORD *)v11;
      v56 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, _QWORD *))(*(_QWORD *)v88 + 24LL))(v88, v53, v55, v12);
      if ( v56 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x332,
          (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_desktop.cpp",
          (const char *)(unsigned int)v56,
          v59);
      if ( v86 == 1 && a6 != (__int64 *)-56LL )
        *((_DWORD *)a6 + 14) = 2;
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      (*(void (__fastcall **)(_QWORD *))(*v54 + 16LL))(v54);
      if ( v88 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    }
  }
  std::wstring::~wstring(v97);
  CoTaskMemFree(v31);
  std::vector<FeatureDescriptor>::~vector<FeatureDescriptor>(&v89);
  std::wstring::~wstring(&v92);
  if ( v91 )
    CoTaskMemFree(v91);
}

```

## disassembly

```asm
0x180024e24  mov     rax, rsp
0x180024e27  push    rbp
0x180024e28  push    rsi
0x180024e29  push    rdi
0x180024e2a  push    r12
0x180024e2c  push    r13
0x180024e2e  push    r14
0x180024e30  push    r15
0x180024e32  lea     rbp, [rax-3D8h]
0x180024e39  sub     rsp, 4A0h
0x180024e40  mov     [rbp+3D0h+var_3A8], 0FFFFFFFFFFFFFFFEh
0x180024e48  mov     [rax+18h], rbx
0x180024e4c  mov     rax, cs:__security_cookie
0x180024e53  xor     rax, rsp
0x180024e56  mov     [rbp+3D0h+var_40], rax
0x180024e5d  mov     rsi, r9
0x180024e60  mov     [rbp+3D0h+var_310], r8d
0x180024e67  mov     r15, rdx
0x180024e6a  mov     [rbp+3D0h+var_300], rdx
0x180024e71  mov     [rsp+4D0h+var_470], rcx
0x180024e76  mov     r12, [rbp+3D0h+arg_20]
0x180024e7d  mov     r14, [rbp+3D0h+arg_28]
0x180024e84  mov     rdi, [rbp+3D0h+arg_30]
0x180024e8b  mov     rax, [rbp+3D0h+arg_38]
0x180024e92  mov     [rbp+3D0h+pv], rax
0x180024e99  mov     r13, [rbp+3D0h+arg_40]
0x180024ea0  mov     rax, [rbp+3D0h+arg_48]
0x180024ea7  mov     qword ptr [rsp+4D0h+var_468], rax
0x180024eac  xor     ebx, ebx
0x180024eae  mov     [rbp+3D0h+var_2E0], rbx
0x180024eb5  mov     rax, [rcx]
0x180024eb8  lea     rdx, [rbp+3D0h+var_2E0]
0x180024ebf  mov     rax, [rax+58h]
0x180024ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ec8  mov     rcx, [rbp+3D8h]
0x180024ecf  test    eax, eax
0x180024ed1  js      loc_1800256C4
0x180024ed7  xorps   xmm0, xmm0
0x180024eda  movups  [rbp+3D0h+var_2D8], xmm0
0x180024ee1  mov     [rbp+3D0h+var_2C8], rbx
0x180024ee8  mov     [rbp+3D0h+var_2C0], 7
0x180024ef3  mov     word ptr [rbp+3D0h+var_2D8], bx
0x180024efa  test    byte ptr [r15+0A0h], 1
0x180024f02  jz      short loc_180024F20
0x180024f04  mov     rdx, [r15+0C0h]
0x180024f0b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180024f0f  mov     r8, rbx
0x180024f12  xor     eax, eax
0x180024f14  inc     r8
0x180024f17  cmp     [rdx+r8*2], ax
0x180024f1c  jnz     short loc_180024F14
0x180024f1e  jmp     short loc_180024F7C
0x180024f20  xor     edx, edx; Val
0x180024f22  mov     r8d, 208h; Size
0x180024f28  lea     rcx, [rbp+3D0h+Buffer]; void *
0x180024f2f  call    memset_0
0x180024f34  mov     rbx, [rbp+3D8h]
0x180024f3b  mov     edx, 104h; uSize
0x180024f40  lea     rcx, [rbp+3D0h+Buffer]; lpBuffer
0x180024f47  call    cs:__imp_GetSystemWindowsDirectoryW
0x180024f4e  nop     dword ptr [rax+rax+00h]
0x180024f53  xor     ecx, ecx
0x180024f55  test    eax, eax
0x180024f57  jz      loc_1800256D9
0x180024f5d  lea     rax, [rbp+3D0h+Buffer]
0x180024f64  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180024f68  mov     r8, rbx
0x180024f6b  inc     r8
0x180024f6e  cmp     [rax+r8*2], cx
0x180024f73  jnz     short loc_180024F6B
0x180024f75  lea     rdx, [rbp+3D0h+Buffer]
0x180024f7c  lea     rcx, [rbp+3D0h+var_2D8]
0x180024f83  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180024f88  lea     rax, aCbstemp; "CbsTemp"
0x180024f8f  mov     [rbp+3D0h+var_428], rax
0x180024f93  mov     [rbp+3D0h+var_420], 7
0x180024f9b  lea     rax, [rbp+3D0h+var_2D8]
0x180024fa2  cmp     [rbp+3D0h+var_2C0], 7
0x180024faa  cmova   rax, qword ptr [rbp+3D0h+var_2D8]
0x180024fb2  mov     [rbp+3D0h+var_418], rax
0x180024fb6  mov     rax, [rbp+3D0h+var_2C8]
0x180024fbd  mov     [rbp+3D0h+var_410], rax
0x180024fc1  lea     r8, [rbp+3D0h+var_428]
0x180024fc5  lea     rdx, [rbp+3D0h+var_418]
0x180024fc9  lea     rcx, [rbp+3D0h+var_298]
0x180024fd0  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x180024fd5  nop
0x180024fd6  mov     rax, [rbp+3D0h+var_2E0]
0x180024fdd  mov     [rbp+3D0h+var_408], rax
0x180024fe1  xor     ecx, ecx
0x180024fe3  inc     rbx
0x180024fe6  cmp     [rax+rbx*2], cx
0x180024fea  jnz     short loc_180024FE3
0x180024fec  mov     [rbp+3D0h+var_400], rbx
0x180024ff0  lea     rax, [rbp+3D0h+var_298]
0x180024ff7  cmp     [rbp+3D0h+var_280], 7
0x180024fff  cmova   rax, [rbp+3D0h+var_298]
0x180025007  mov     [rbp+3D0h+var_3F8], rax
0x18002500b  mov     rax, [rbp+3D0h+var_288]
0x180025012  mov     [rbp+3D0h+var_3F0], rax
0x180025016  lea     r8, [rbp+3D0h+var_408]
0x18002501a  lea     rdx, [rbp+3D0h+var_3F8]
0x18002501e  lea     rcx, [rbp+3D0h+var_2B8]
0x180025025  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x18002502a  nop
0x18002502b  mov     rcx, [rbp+3D0h+var_2A8]
0x180025032  lea     rax, [rbp+3D0h+var_2B8]
0x180025039  cmp     [rbp+3D0h+var_2A0], 7
0x180025041  cmova   rax, [rbp+3D0h+var_2B8]
0x180025049  mov     [rbp+3D0h+var_3E8], rax
0x18002504d  mov     [rbp+3D0h+var_3E0], rcx
0x180025051  mov     rdx, rdi
0x180025054  lea     rcx, [rbp+3D0h+var_3E8]
0x180025058  call    ?GetTemporaryFileName@@YAJAEBV?$basic_zstring_view@_W@wil@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; GetTemporaryFileName(wil::basic_zstring_view<wchar_t> const &,std::wstring *)
0x18002505d  mov     rcx, [rbp+3D8h]; this
0x180025064  xor     ebx, ebx
0x180025066  test    eax, eax
0x180025068  js      loc_1800256EE
0x18002506e  lea     rcx, [rbp+3D0h+var_2B8]; void *
0x180025075  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002507a  nop
0x18002507b  lea     rcx, [rbp+3D0h+var_298]; void *
0x180025082  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025087  xorps   xmm0, xmm0
0x18002508a  movdqu  [rbp+3D0h+var_2F8], xmm0
0x180025092  mov     [rbp+3D0h+var_2E8], rbx
0x180025099  mov     rdx, [r12+8]
0x18002509e  add     rdx, [rsi+8]
0x1800250a2  lea     rcx, [rbp+3D0h+var_2F8]
0x1800250a9  call    ?reserve@?$vector@UFeatureDescriptor@@V?$allocator@UFeatureDescriptor@@@std@@@std@@QEAAX_K@Z; std::vector<FeatureDescriptor>::reserve(unsigned __int64)
0x1800250ae  mov     rbx, [rsi]
0x1800250b1  mov     rax, [rsi+8]
0x1800250b5  lea     rsi, [rbx+rax*8]
0x1800250b9  mov     rdx, qword ptr [rbp+3D0h+var_2F8+8]
0x1800250c0  cmp     rbx, rsi
0x1800250c3  jz      short loc_18002513A
0x1800250c5  xor     r15d, r15d
0x1800250c8  mov     rcx, [rbx]
0x1800250cb  mov     qword ptr [rsp+4D0h+var_468+10h], r15
0x1800250d0  mov     dword ptr [rbp+3D0h+var_450+4], r15d
0x1800250d4  mov     rax, [rcx+8]
0x1800250d8  mov     qword ptr [rsp+4D0h+var_468+8], rax
0x1800250dd  mov     eax, [rcx+14h]
0x1800250e0  mov     dword ptr [rbp+3D0h+var_450], eax
0x1800250e3  cmp     rdx, [rbp+3D0h+var_2E8]
0x1800250ea  jz      short loc_180025112
0x1800250ec  movups  xmm0, xmmword ptr [rsp+4D0h+var_468+8]
0x1800250f1  movups  xmmword ptr [rdx], xmm0
0x1800250f4  movsd   xmm1, [rbp+3D0h+var_450]
0x1800250f9  movsd   qword ptr [rdx+10h], xmm1
0x1800250fe  mov     rdx, qword ptr [rbp+3D0h+var_2F8+8]
0x180025105  add     rdx, 18h
0x180025109  mov     qword ptr [rbp+3D0h+var_2F8+8], rdx
0x180025110  jmp     short loc_18002512A
0x180025112  lea     r8, [rsp+4D0h+var_468+8]
0x180025117  lea     rcx, [rbp+3D0h+var_2F8]
0x18002511e  call    ??$_Emplace_reallocate@UCustomInfoPair@ActionList@@@?$vector@UCustomInfoPair@ActionList@@V?$allocator@UCustomInfoPair@ActionList@@@std@@@std@@AEAAPEAUCustomInfoPair@ActionList@@QEAU23@$$QEAU23@@Z; std::vector<ActionList::CustomInfoPair>::_Emplace_reallocate<ActionList::CustomInfoPair>(ActionList::CustomInfoPair * const,ActionList::CustomInfoPair &&)
0x180025123  mov     rdx, qword ptr [rbp+3D0h+var_2F8+8]
0x18002512a  add     rbx, 8
0x18002512e  cmp     rbx, rsi
0x180025131  jnz     short loc_1800250C8
0x180025133  mov     r15, [rbp+3D0h+var_300]
0x18002513a  mov     rbx, [r12]
0x18002513e  mov     rax, [r12+8]
0x180025143  lea     rsi, [rbx+rax*8]
0x180025147  cmp     rbx, rsi
0x18002514a  jz      short loc_1800251BD
0x18002514c  xor     r15d, r15d
0x18002514f  mov     rcx, [rbx]
0x180025152  mov     qword ptr [rbp+3D0h+var_448+8], r15
0x180025156  mov     dword ptr [rbp+3D0h+var_438], r15d
0x18002515a  mov     rax, [rcx+8]
0x18002515e  mov     qword ptr [rbp+3D0h+var_448], rax
0x180025162  mov     eax, [rcx+14h]
0x180025165  mov     dword ptr [rbp+3D0h+var_438+4], eax
0x180025168  cmp     rdx, [rbp+3D0h+var_2E8]
0x18002516f  jz      short loc_180025196
0x180025171  movups  xmm0, [rbp+3D0h+var_448]
0x180025175  movups  xmmword ptr [rdx], xmm0
0x180025178  movsd   xmm1, [rbp+3D0h+var_438]
0x18002517d  movsd   qword ptr [rdx+10h], xmm1
0x180025182  mov     rdx, qword ptr [rbp+3D0h+var_2F8+8]
0x180025189  add     rdx, 18h
0x18002518d  mov     qword ptr [rbp+3D0h+var_2F8+8], rdx
0x180025194  jmp     short loc_1800251AD
0x180025196  lea     r8, [rbp+3D0h+var_448]
0x18002519a  lea     rcx, [rbp+3D0h+var_2F8]
0x1800251a1  call    ??$_Emplace_reallocate@UCustomInfoPair@ActionList@@@?$vector@UCustomInfoPair@ActionList@@V?$allocator@UCustomInfoPair@ActionList@@@std@@@std@@AEAAPEAUCustomInfoPair@ActionList@@QEAU23@$$QEAU23@@Z; std::vector<ActionList::CustomInfoPair>::_Emplace_reallocate<ActionList::CustomInfoPair>(ActionList::CustomInfoPair * const,ActionList::CustomInfoPair &&)
0x1800251a6  mov     rdx, qword ptr [rbp+3D0h+var_2F8+8]
0x1800251ad  add     rbx, 8
0x1800251b1  cmp     rbx, rsi
0x1800251b4  jnz     short loc_18002514F
0x1800251b6  mov     r15, [rbp+3D0h+var_300]
0x1800251bd  xor     esi, esi
0x1800251bf  mov     [rbp+3D0h+var_430], rsi
0x1800251c3  lea     rax, ??_7SessionData@@6B@; const SessionData::`vftable'
0x1800251ca  mov     [rbp+3D0h+var_370], rax
0x1800251ce  mov     [rbp+3D0h+var_360], rsi
0x1800251d2  mov     [rbp+3D0h+var_348], rsi
0x1800251d9  mov     [rbp+3D0h+var_340], rsi
0x1800251e0  mov     [rbp+3D0h+var_338], esi
0x1800251e6  xorps   xmm0, xmm0
0x1800251e9  movdqa  [rbp+3D0h+var_330], xmm0
0x1800251f1  mov     [rbp+3D0h+var_320], esi
0x1800251f7  mov     [rbp+3D0h+var_318], rsi
0x1800251fe  mov     [rbp+3D0h+var_368], 12h
0x180025205  mov     rax, qword ptr [rbp+3D0h+var_2F8]
0x18002520c  mov     [rbp+3D0h+var_358], rax
0x180025210  sub     rdx, rax
0x180025213  sar     rdx, 3
0x180025217  mov     rax, 0AAAAAAAAAAAAAAABh
0x180025221  imul    rdx, rax
0x180025225  mov     [rbp+3D0h+var_350], edx
0x18002522b  lea     rcx, [rbp+3D0h+var_370]; struct SessionData *
0x18002522f  call    ?SessionDataToJson@@YAPEA_WAEBUSessionData@@@Z; SessionDataToJson(SessionData const &)
0x180025234  mov     r12, rax
0x180025237  mov     [rbp+3D0h+var_430], rax
0x18002523b  mov     rcx, [rbp+3D8h]; this
0x180025242  test    rax, rax
0x180025245  jz      loc_180025703
0x18002524b  lea     rdx, [r15+8]
0x18002524f  lea     rcx, [rbp+3D0h+var_278]
0x180025256  call    ?to_wstring@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBD@Z; to_wstring(char const * const)
0x18002525b  nop
0x18002525c  mov     rcx, [rdi+10h]
0x180025260  cmp     qword ptr [rdi+18h], 7
0x180025265  jbe     short loc_18002526C
0x180025267  mov     rax, [rdi]
0x18002526a  jmp     short loc_18002526F
0x18002526c  mov     rax, rdi
0x18002526f  mov     [rbp+3D0h+var_3D8], rax
0x180025273  mov     [rbp+3D0h+var_3D0], rcx
0x180025277  lea     rcx, [rbp+3D0h+var_3D8]
0x18002527b  call    ?DestroyDirectory@@YAXAEBV?$basic_zstring_view@_W@wil@@@Z; DestroyDirectory(wil::basic_zstring_view<wchar_t> const &)
0x180025280  lea     rax, aActionlistXml; "ActionList.xml"
0x180025287  mov     [rbp+3D0h+var_3C8], rax
0x18002528b  mov     [rbp+3D0h+var_3C0], 0Eh
0x180025293  cmp     qword ptr [rdi+18h], 7
0x180025298  jbe     short loc_18002529F
0x18002529a  mov     rax, [rdi]
0x18002529d  jmp     short loc_1800252A2
0x18002529f  mov     rax, rdi
0x1800252a2  mov     [rbp+3D0h+var_3B8], rax
0x1800252a6  mov     rax, [rdi+10h]
0x1800252aa  mov     [rbp+3D0h+var_3B0], rax
0x1800252ae  lea     r8, [rbp+3D0h+var_3C8]
0x1800252b2  lea     rdx, [rbp+3D0h+var_3B8]
0x1800252b6  lea     rcx, [rbp+3D0h+var_398]
0x1800252ba  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x1800252bf  mov     rdx, rax
0x1800252c2  mov     rbx, qword ptr [rsp+4D0h+var_468]
0x1800252c7  mov     rcx, rbx
0x1800252ca  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800252cf  lea     rcx, [rbp+3D0h+var_398]; void *
0x1800252d3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800252d8  cmp     [r13+0], rsi
0x1800252dc  jnz     loc_1800256B9
0x1800252e2  mov     esi, [rbp+3D0h+var_310]
0x1800252e8  and     esi, 4
0x1800252eb  mov     [rsp+48h], r13
0x1800252f0  mov     rax, [rbp+3D0h+pv]
0x1800252f7  mov     [rsp+4D0h+var_490], rax
0x1800252fc  mov     [rsp+4D0h+var_498], rbx
0x180025301  lea     rax, [rbp+3D0h+var_2D8]
0x180025308  mov     [rsp+4D0h+var_4A0], rax
0x18002530d  mov     [rsp+4D0h+var_4A8], rdi
0x180025312  lea     rax, [rbp+3D0h+var_278]
0x180025319  mov     qword ptr [rsp+4D0h+var_4B0], rax
0x18002531e  mov     r9, r12
0x180025321  lea     r8, [rbp+3D0h+var_370]
0x180025325  mov     edx, 2
0x18002532a  mov     rcx, r15
0x18002532d  call    CallFacilitator_0
0x180025332  mov     rdx, [r13+0]
0x180025336  mov     rcx, [rdx+40h]
0x18002533a  mov     eax, [rdx+48h]
0x18002533d  imul    r10, rax, 0A8h
0x180025344  add     r10, rcx
0x180025347  mov     r11d, 0A8h
0x18002534d  cmp     rcx, r10
0x180025350  jz      short loc_180025389
0x180025352  mov     rdx, [rcx+70h]
0x180025356  mov     eax, [rcx+78h]
0x180025359  imul    r8, rax, 0B8h
0x180025360  add     r8, rdx
0x180025363  cmp     rdx, r8
0x180025366  jz      short loc_18002537D
0x180025368  mov     r9, [r14]
0x18002536b  add     r9, [rdx]
0x18002536e  mov     [r14], r9
0x180025371  add     rdx, 0B8h
0x180025378  cmp     rdx, r8
0x18002537b  jnz     short loc_18002536B
0x18002537d  add     rcx, r11
0x180025380  cmp     rcx, r10
0x180025383  jnz     short loc_180025352
0x180025385  mov     rdx, [r13+0]
0x180025389  mov     r9, [r14]
0x18002538c  mov     rcx, [rdx+58h]
0x180025390  mov     eax, [rdx+60h]
  ... truncated ...
```
