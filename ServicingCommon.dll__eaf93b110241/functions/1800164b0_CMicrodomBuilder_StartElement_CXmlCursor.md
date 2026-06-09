# CMicrodomBuilder::StartElement(CXmlCursor *)

- ea: `0x1800164b0`
- end: `0x18001736c`
- name: `?StartElement@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@@Z`
- size: `3772`
- prototype: `__int64 __fastcall(CMicrodomBuilder *__hidden this, struct CXmlCursor *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017380`

## callees

- `0x1800031e0`
- `0x1800032b0`
- `0x18000337c`
- `0x180003550`
- `0x18000a8d0`
- `0x18000fd04`
- `0x1800151a0`
- `0x180015d4c`
- `0x1800164b0`
- `0x18001a350`
- `0x18001e850`
- `0x18001fd90`
- `0x180022eb0`
- `0x180022f08`
- `0x1800293a0`
- `0x18009a070`
- `0x18009a700`
- `0x1800a0020`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180016594`
- `ntdll!RtlAllocateHeap` at `0x1800169d7`
- `ntdll!RtlAllocateHeap` at `0x1800171cf`
- `ntdll!RtlAllocateHeap` at `0x180016594`
- `ntdll!RtlAllocateHeap` at `0x1800169d7`
- `ntdll!RtlAllocateHeap` at `0x1800171cf`
- `ntdll!RtlRaiseStatus` at `0x1800164ec`
- `ntdll!RtlRaiseStatus` at `0x18001713e`
- `ntdll!RtlRaiseStatus` at `0x1800164ec`
- `ntdll!RtlRaiseStatus` at `0x18001713e`

## string_xrefs

- `0x18001707d`: `onecore\base\xml\udom_builder.cpp`
- `0x18001711b`: `onecore\base\xml\udom_builder.cpp`
- `0x1800172d0`: `onecore\base\xml\udom_builder.cpp`
- `0x18001731e`: `onecore\base\xml\udom_builder.cpp`

## pseudocode

```c
__int64 __fastcall CMicrodomBuilder::StartElement(__int64 **this, struct CXmlCursor *a2)
{
  bool v2; // zf
  struct CXmlCursor *v3; // r10
  CMicrodomBuilder *v4; // r15
  __int64 *v5; // rdx
  __int64 v6; // rbx
  PVOID Heap; // rdi
  __int64 *v8; // rax
  __int64 v9; // rbx
  int v10; // ecx
  char *v11; // r13
  unsigned int v12; // ecx
  unsigned int v13; // eax
  __int64 result; // rax
  _QWORD *v15; // r8
  _QWORD *v16; // r9
  __int64 v17; // rdx
  void *v18; // r11
  unsigned int v19; // r14d
  char *v20; // r13
  unsigned int v21; // eax
  __int64 v22; // rsi
  unsigned int v23; // edx
  _QWORD *v24; // r8
  unsigned int m; // ecx
  bool v26; // cf
  void *v27; // r9
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // r8
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rdi
  int v32; // ecx
  unsigned int v33; // eax
  unsigned __int64 v34; // rdi
  unsigned int v35; // ebx
  __int64 v36; // r8
  int (__fastcall *v37)(unsigned __int64, _QWORD **, __int64, void *); // rax
  unsigned int v38; // r8d
  __int64 v39; // rcx
  _QWORD *v40; // rcx
  int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // edx
  unsigned int v44; // ecx
  _QWORD *v45; // rax
  __int64 *v46; // rdx
  __int64 v47; // rbx
  PVOID v48; // rdi
  __int64 *v49; // rax
  __int64 v50; // rax
  __int64 v51; // r12
  int v52; // ecx
  struct CXmlCursor *v53; // rbx
  struct CXmlCursor *v54; // rdx
  unsigned int v55; // ecx
  unsigned int v56; // eax
  int v57; // eax
  size_t v58; // rdi
  void *v59; // r15
  unsigned __int64 v60; // rbx
  char **v61; // r14
  char *i; // rsi
  _QWORD *v63; // r14
  char *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // r8
  void *v67; // rbx
  signed int v68; // ebx
  char *v69; // rax
  unsigned __int64 v70; // rcx
  unsigned __int64 v71; // r15
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // xmm2_8
  unsigned __int64 v75; // rdx
  unsigned __int64 v76; // rax
  __int64 v77; // rdx
  unsigned __int64 v78; // rcx
  __int64 v79; // rax
  size_t v80; // rax
  unsigned __int64 *v81; // rax
  _QWORD *v82; // r12
  char *v83; // rdi
  unsigned __int64 j; // rbx
  __int64 v85; // r10
  CMicrodomBuilder *v86; // rax
  _QWORD *v87; // rcx
  _QWORD *v88; // r8
  _QWORD *v89; // rcx
  __int64 v90; // rdi
  _QWORD *v91; // r14
  char *k; // rbx
  int *v93; // rsi
  char v94; // al
  int v95; // eax
  __int64 *v96; // rax
  const char *v97; // rax
  __int64 *v98; // rdx
  __int64 v99; // rdi
  PVOID v100; // rbx
  __int64 *v101; // rax
  __int64 v102; // rdx
  char v103; // [rsp+30h] [rbp-D0h]
  const char *v104; // [rsp+38h] [rbp-C8h] BYREF
  const char *v105; // [rsp+40h] [rbp-C0h]
  __int64 v106; // [rsp+48h] [rbp-B8h]
  const char *v107; // [rsp+50h] [rbp-B0h]
  CMicrodomBuilder *v108; // [rsp+58h] [rbp-A8h]
  __int64 v109; // [rsp+60h] [rbp-A0h] BYREF
  int v110; // [rsp+68h] [rbp-98h]
  unsigned int v111; // [rsp+70h] [rbp-90h]
  struct CXmlCursor *v112; // [rsp+78h] [rbp-88h]
  __int64 v113; // [rsp+80h] [rbp-80h]
  __int128 v114; // [rsp+88h] [rbp-78h] BYREF
  void *v115; // [rsp+98h] [rbp-68h]
  size_t Size[2]; // [rsp+A0h] [rbp-60h] BYREF
  void *Buf1; // [rsp+B0h] [rbp-50h]
  __int64 v118; // [rsp+B8h] [rbp-48h]
  char *v119; // [rsp+C0h] [rbp-40h]
  _QWORD *v120; // [rsp+C8h] [rbp-38h] BYREF

  v2 = *((_DWORD *)a2 + 2282) == 3;
  v3 = a2;
  v112 = a2;
  v4 = (CMicrodomBuilder *)this;
  v108 = (CMicrodomBuilder *)this;
  if ( !v2 )
    RtlRaiseStatus(-1073741595);
  v5 = this[156];
  v109 = 0;
  v110 = 0;
  if ( v5 )
  {
    if ( *v5 != v5[1] )
      goto LABEL_14;
    v6 = 2 * *v5;
    if ( (unsigned __int64)(288 * *v5) <= 0x400000 )
    {
      if ( !v6 )
        v6 = 1;
    }
    else
    {
      v6 = 29127;
    }
  }
  else
  {
    v6 = 455;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 144 * v6);
  if ( !Heap || (v8 = (__int64 *)operator new(0x20u), (v5 = v8) == 0) )
  {
LABEL_194:
    v106 = 1290;
    v104 = "onecore\\base\\xml\\udom_builder.cpp";
    v105 = "CMicrodomBuilder::StartElement";
    v107 = "NewElement = this->AllocateStreamObject()";
    RtlReportErrorOrigination(&v104, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
    return 3221225495LL;
  }
  v3 = v112;
  v8[1] = 0;
  v8[3] = 0;
  *v8 = v6;
  v8[2] = (__int64)Heap;
  v8[3] = *((_QWORD *)v4 + 156);
  *((_QWORD *)v4 + 156) = v8;
LABEL_14:
  v9 = v5[2] + 144 * v5[1];
  if ( v9 )
  {
    *(_QWORD *)(v9 + 16) = 0;
    *(_QWORD *)(v9 + 56) = v9 + 48;
    *(_QWORD *)(v9 + 48) = v9 + 48;
    *(_QWORD *)(v9 + 96) = v9 + 88;
    *(_QWORD *)(v9 + 88) = v9 + 88;
    *(_QWORD *)v9 = 0;
    *(_QWORD *)(v9 + 8) = 0;
    *(_QWORD *)(v9 + 40) = 0;
    *(_QWORD *)(v9 + 24) = 0;
    *(_QWORD *)(v9 + 32) = 0;
    *(_QWORD *)(v9 + 64) = 0;
    *(_QWORD *)(v9 + 72) = 0;
    *(_QWORD *)(v9 + 80) = 0;
    *(_QWORD *)(v9 + 104) = 0;
  }
  ++*(_QWORD *)(*((_QWORD *)v4 + 156) + 8LL);
  if ( !v9 )
    goto LABEL_194;
  v10 = *((_DWORD *)v4 + 324);
  v11 = (char *)v3 + 9184;
  v119 = (char *)v3 + 9184;
  *((_DWORD *)v4 + 324) = v10 + 1;
  *(_DWORD *)(v9 + 72) = v10;
  v12 = *((_DWORD *)v3 + 2314);
  *(_DWORD *)(v9 + 80) = v12;
  v13 = *((_DWORD *)v3 + 2315);
  *(_DWORD *)(v9 + 84) = v13;
  if ( v12 <= v13 )
    v12 = v13;
  if ( *((_DWORD *)v4 + 325) > v12 )
    v12 = *((_DWORD *)v4 + 325);
  *((_DWORD *)v4 + 325) = v12;
  *(_DWORD *)(v9 + 112) = 16;
  result = CMicrodomBuilder::AddStringsForElement(
             v4,
             v3,
             (struct CXmlCursor *)((char *)v3 + 9208),
             (struct CXmlCursor *)((char *)v3 + 9232),
             (struct CXmlCursor *)((char *)v3 + 9184),
             (struct CMicrodomBuilder::ThreeStringIdPair *)&v109);
  if ( (int)result >= 0 )
  {
    *(_DWORD *)(v9 + 120) = v109;
    *(_DWORD *)(v9 + 116) = HIDWORD(v109);
    *(_DWORD *)(v9 + 124) = v110;
    *(_QWORD *)(v9 + 64) = *((_QWORD *)v4 + 157);
    *(_QWORD *)(v9 + 8) = *((_QWORD *)v4 + 159);
    *(_QWORD *)v9 = (char *)v4 + 1264;
    **((_QWORD **)v4 + 159) = v9;
    *((_QWORD *)v4 + 159) = v9;
    *(_QWORD *)(v9 + 16) = (char *)v4 + 1264;
    ++*((_QWORD *)v4 + 161);
    v17 = *((_QWORD *)v4 + 157);
    if ( v17 )
    {
      v15 = *(_QWORD **)(v17 + 96);
      if ( *v15 != v17 + 88 )
LABEL_169:
        __fastfail(3u);
      *(_QWORD *)(v9 + 48) = v17 + 88;
      *(_QWORD *)(v9 + 56) = v15;
      *v15 = v9 + 48;
      *(_QWORD *)(v17 + 96) = v9 + 48;
      ++*(_QWORD *)(v17 + 104);
    }
    *((_QWORD *)v4 + 157) = v9;
    if ( *((_DWORD *)v11 + 20) )
    {
      v18 = 0;
      v19 = 0;
      v111 = 0;
      v20 = (char *)v112 + 3456;
      while ( !v20 )
      {
        v22 = 0;
        LODWORD(v28) = RtlXmlReportErrorFunction(-1073741811, v17, (unsigned int)v15, v16);
LABEL_71:
        if ( (v28 & 0x80000000) != 0LL )
          goto LABEL_171;
LABEL_72:
        v46 = (__int64 *)*((_QWORD *)v4 + 156);
        if ( v46 )
        {
          if ( *v46 != v46[1] )
            goto LABEL_83;
          v47 = 2 * *v46;
          if ( (unsigned __int64)(288 * *v46) <= 0x400000 )
          {
            if ( !v47 )
              v47 = 1;
          }
          else
          {
            v47 = 29127;
          }
        }
        else
        {
          v47 = 455;
        }
        v48 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 144 * v47);
        if ( !v48 )
          goto LABEL_170;
        v49 = (__int64 *)operator new(0x20u);
        v46 = v49;
        if ( !v49 )
          goto LABEL_170;
        *v49 = v47;
        v18 = 0;
        v49[1] = 0;
        v49[3] = 0;
        v49[2] = (__int64)v48;
        v49[3] = *((_QWORD *)v4 + 156);
        *((_QWORD *)v4 + 156) = v49;
LABEL_83:
        v50 = v46[1];
        v2 = v46[2] + 144 * v50 == 0;
        v51 = v46[2] + 144 * v50;
        v118 = v51;
        if ( !v2 )
        {
          *(_QWORD *)(v51 + 16) = v18;
          *(_QWORD *)(v51 + 56) = v51 + 48;
          *(_QWORD *)(v51 + 48) = v51 + 48;
          *(_QWORD *)(v51 + 96) = v51 + 88;
          *(_QWORD *)(v51 + 88) = v51 + 88;
          *(_QWORD *)v51 = v18;
          *(_QWORD *)(v51 + 8) = v18;
          *(_QWORD *)(v51 + 40) = v18;
          *(_QWORD *)(v51 + 24) = v18;
          *(_QWORD *)(v51 + 32) = v18;
          *(_QWORD *)(v51 + 64) = v18;
          *(_QWORD *)(v51 + 72) = 0;
          *(_QWORD *)(v51 + 80) = 0;
          *(_QWORD *)(v51 + 104) = v18;
        }
        ++*(_QWORD *)(*((_QWORD *)v4 + 156) + 8LL);
        if ( !v51 )
        {
LABEL_170:
          v106 = 1339;
          v104 = "onecore\\base\\xml\\udom_builder.cpp";
          v97 = "NewAttribute = this->AllocateStreamObject()";
          goto LABEL_193;
        }
        v52 = *((_DWORD *)v4 + 324);
        v53 = v112;
        v54 = v112;
        *((_DWORD *)v4 + 324) = v52 + 1;
        *(_DWORD *)(v51 + 72) = v52;
        v55 = *(_DWORD *)(v22 + 96);
        *(_DWORD *)(v51 + 80) = v55;
        v56 = *(_DWORD *)(v22 + 100);
        *(_DWORD *)(v51 + 84) = v56;
        if ( v55 <= v56 )
          v55 = v56;
        if ( *((_DWORD *)v4 + 325) > v55 )
          v55 = *((_DWORD *)v4 + 325);
        *((_DWORD *)v4 + 325) = v55;
        ++*(_DWORD *)(*((_QWORD *)v4 + 157) + 76LL);
        *(_DWORD *)(v51 + 112) = 65560;
        *(_BYTE *)(v51 + 132) = 1;
        result = CMicrodomBuilder::AddStringsForElement(
                   v4,
                   v54,
                   (const struct _XML_EXTENT *)(v22 + 24),
                   (const struct _XML_EXTENT *)(v22 + 72),
                   (const struct _XML_EXTENT *)v22,
                   (struct CMicrodomBuilder::ThreeStringIdPair *)&v109);
        if ( (int)result < 0 )
          return result;
        *(_DWORD *)(v51 + 120) = v109;
        *(_DWORD *)(v51 + 116) = HIDWORD(v109);
        *(_DWORD *)(v51 + 124) = v110;
        if ( !*(_DWORD *)(v22 + 68) )
        {
          v95 = -1;
          goto LABEL_162;
        }
        *(_DWORD *)(v51 + 128) = -1;
        Buf1 = 0;
        *(_OWORD *)Size = 0;
        v57 = CXmlCursor::DecodeExtent((__int64)v53, (__int64 *)(v22 + 48), (_QWORD *)v4 + 198, Size);
        if ( v57 < 0 )
          return (unsigned int)v57;
        v58 = Size[0];
        v59 = Buf1;
        v60 = MurmurHash3_x64_64(Buf1, Size[0], Size[0]);
        v120 = (_QWORD *)((char *)v108 + 8);
        v61 = (char **)(*((_QWORD *)v108 + 2) + 32 * (v60 % *((_QWORD *)v108 + 4)));
        for ( i = *v61; i && i != (char *)v61; i = *(char **)i )
        {
          if ( *((_QWORD *)i + 4) == v60 && v58 == *((_QWORD *)i + 5) && !memcmp(v59, *((const void **)i + 7), v58) )
          {
            v63 = v120;
            v103 = 1;
            goto LABEL_108;
          }
        }
        v64 = (char *)operator new(0x48u);
        i = v64;
        if ( !v64 )
          return (unsigned int)-1073741801;
        *((_QWORD *)v64 + 4) = v60;
        *((_QWORD *)v64 + 2) = 0;
        *(_QWORD *)v64 = 0;
        v67 = 0;
        *((_QWORD *)v64 + 1) = 0;
        *((_QWORD *)v64 + 3) = v120;
        *(_OWORD *)(v64 + 40) = 0;
        *((_QWORD *)v64 + 7) = 0;
        *((_DWORD *)v64 + 16) = -1;
        v115 = 0;
        v114 = 0u;
        if ( v58 > Size[1] )
          goto LABEL_105;
        if ( v59 )
        {
          if ( v58 )
          {
            v68 = RtlAllocateLBlob(v58, &v114);
            if ( v68 < 0 )
            {
              if ( v115 )
                anonymous_namespace_::OurRtlFreeStringRoutine(v115, v72, v73);
              goto LABEL_155;
            }
            v67 = v115;
            memmove(v115, v59, v58);
            *(_QWORD *)&v114 = v58;
          }
        }
        else if ( v58 )
        {
LABEL_105:
          v106 = 139;
          v104 = "onecore\\base\\lstring\\lutf8_string.cpp";
          v105 = "RtlDuplicateLUtf8String";
          v107 = "RtlIsLUtf8StringValid(Source)";
          RtlReportErrorOrigination(&v104, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
          v68 = -1073741811;
LABEL_155:
          BUCL::HashTable::CTable<CMicrodomBuilder::CIntermediateStringTableTraits>::CBucket::`scalar deleting destructor'(i);
          return (unsigned int)v68;
        }
        v74 = *((_QWORD *)i + 7);
        *(_OWORD *)Size = *(_OWORD *)(i + 40);
        *(_OWORD *)(i + 40) = v114;
        *((_QWORD *)i + 7) = v67;
        if ( v74 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v74, v65, v66);
        v103 = 0;
        *((_DWORD *)i + 16) = *(_DWORD *)v108;
        v69 = v61[1];
        *(_QWORD *)i = v61;
        *((_QWORD *)i + 1) = v69;
        *(_QWORD *)v61[1] = i;
        v61[1] = i;
        *((_QWORD *)i + 2) = v61;
        ++v61[3];
        v63 = v120;
        ++v120[4];
LABEL_108:
        v70 = v63[4];
        if ( v70 <= v63[5] )
          goto LABEL_154;
        if ( v70 == -1 )
        {
          v71 = -1;
        }
        else if ( HIDWORD(v70) )
        {
          if ( ((2 * HIDWORD(v70)) & 0xFFFFFFFF00000000uLL) != 0 )
            goto LABEL_151;
          v75 = HIDWORD(v70) << 33;
          v76 = 2LL * (unsigned int)v70;
          v71 = v75 + v76;
          v68 = v75 + v76 < v76 ? 0xC0000095 : 0;
          if ( v75 + v76 < v76 )
            goto LABEL_152;
        }
        else
        {
          v71 = 2LL * (unsigned int)v70;
        }
        if ( v71 != v70 )
        {
          if ( !HIDWORD(v71) )
          {
            v113 = 5LL * (unsigned int)v71;
            goto LABEL_127;
          }
          if ( ((5 * HIDWORD(v71)) & 0xFFFFFFFF00000000uLL) != 0 )
          {
LABEL_151:
            v68 = -1073741675;
          }
          else
          {
            v77 = 0x500000000LL * HIDWORD(v71);
            v78 = 5LL * (unsigned int)v71;
            v113 = v77 + v78;
            v68 = v77 + v78 < v78 ? 0xC0000095 : 0;
            if ( v77 + v78 >= v78 )
            {
LABEL_127:
              v79 = 32 * v71;
              if ( !is_mul_ok(v71, 0x20u) )
                v79 = -1;
              v26 = __CFADD__(v79, 8);
              v80 = v79 + 8;
              if ( v26 )
                v80 = -1;
              v81 = (unsigned __int64 *)operator new(v80);
              if ( v81 )
              {
                *v81 = v71;
                v82 = v81 + 1;
                v83 = (char *)(v81 + 1);
                for ( j = v71; j; --j )
                {
                  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v83);
                  v83 += 32;
                }
                if ( v82 )
                {
                  v85 = 0;
                  if ( v63[3] )
                  {
                    v86 = v108;
                    do
                    {
                      v16 = (_QWORD *)(*((_QWORD *)v86 + 2) + 32 * v85);
                      while ( 1 )
                      {
                        v87 = (_QWORD *)*v16;
                        if ( (_QWORD *)*v16 == v16 )
                          break;
                        if ( v87 )
                        {
                          if ( (_QWORD *)v87[2] == v16 )
                          {
                            *(_QWORD *)(*v87 + 8LL) = v87[1];
                            *(_QWORD *)v87[1] = *v87;
                            v87[2] = 0;
                            --v16[3];
                          }
                        }
                        v88 = &v82[4 * (v87[4] % v71)];
                        v87[1] = v88[1];
                        *v87 = v88;
                        *(_QWORD *)v88[1] = v87;
                        v88[1] = v87;
                        v87[2] = v88;
                        ++v88[3];
                      }
                      v86 = v108;
                      ++v85;
                    }
                    while ( v85 != *((_QWORD *)v108 + 4) );
                  }
                  v89 = (_QWORD *)v63[1];
                  if ( v63 + 6 != v89 && v89 )
                  {
                    v90 = *(v89 - 1);
                    v91 = v89 - 1;
                    for ( k = (char *)&v89[4 * v90]; v90; --v90 )
                    {
                      k -= 32;
                      BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::~CBucketChain(k);
                    }
                    operator delete(v91);
                    v63 = v120;
                  }
                  v93 = (int *)(i + 64);
                  v63[5] = v113;
                  v94 = v103;
                  v63[1] = v82;
                  v51 = v118;
                  v63[3] = v71;
                  goto LABEL_157;
                }
              }
              v68 = -1073741801;
            }
          }
LABEL_152:
          if ( v68 < 0 )
            return (unsigned int)v68;
        }
        v51 = v118;
LABEL_154:
        v94 = v103;
        v93 = (int *)(i + 64);
LABEL_157:
        v4 = v108;
        if ( !v94 )
        {
          if ( *(_DWORD *)v108 == -1 )
          {
            v106 = 395;
            v104 = "onecore\\base\\xml\\udom_builder.cpp";
            v105 = "CMicrodomBuilder::AddString";
            v107 = "BUCL::Rtl::Increment(m_NextStringId)";
            RtlReportErrorOrigination(&v104, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225621LL);
            return (unsigned int)-1073741675;
          }
          ++*(_DWORD *)v108;
        }
        v95 = *v93;
        v19 = v111;
        v53 = v112;
LABEL_162:
        *(_DWORD *)(v51 + 128) = v95;
        v17 = *((_QWORD *)v4 + 157);
        v15 = *(_QWORD **)(v17 + 96);
        if ( *v15 != v17 + 88 )
          goto LABEL_169;
        *(_QWORD *)(v51 + 48) = v17 + 88;
        *(_QWORD *)(v51 + 56) = v15;
        ++v19;
        *v15 = v51 + 48;
        *(_QWORD *)(v17 + 96) = v51 + 48;
        ++*(_QWORD *)(v17 + 104);
        *(_QWORD *)(v51 + 8) = *((_QWORD *)v4 + 159);
        *(_QWORD *)v51 = (char *)v4 + 1264;
        v96 = (__int64 *)*((_QWORD *)v4 + 159);
        v111 = v19;
        *v96 = v51;
        *((_QWORD *)v4 + 159) = v51;
        *(_QWORD *)(v51 + 16) = (char *)v4 + 1264;
        ++*((_QWORD *)v4 + 161);
        if ( v19 == *((_DWORD *)v53 + 2316) )
        {
          v11 = v119;
          goto LABEL_173;
        }
        v18 = 0;
      }
      v21 = *((_DWORD *)v20 + 5);
      if ( v19 < v21 && v21 )
      {
        v22 = *((_QWORD *)v20 + 3) + *((_QWORD *)v20 + 1) * v19;
        goto LABEL_72;
      }
      v23 = *((_DWORD *)v20 + 4);
      v24 = (_QWORD *)*((_QWORD *)v20 + 7);
      for ( m = v19 - v21; m >= v23; m -= v23 )
      {
        if ( !v24 )
          break;
        v24 = (_QWORD *)v24[1];
      }
      v26 = m < v23;
      v27 = v24;
      LODWORD(v28) = 0;
      if ( !v26 )
        v27 = 0;
      v2 = v24 == 0;
      v29 = m;
      if ( v2 )
        LODWORD(v28) = -1073741275;
      if ( !v27 )
        v29 = 0;
      if ( (v28 & 0x80000000) == 0LL )
      {
LABEL_69:
        v22 = (__int64)v27 + *((_QWORD *)v20 + 1) * v29 + 16;
        goto LABEL_71;
      }
      if ( *((_QWORD *)v20 + 4) )
      {
        LODWORD(v29) = *((_DWORD *)v20 + 1);
        if ( (unsigned int)v29 > v19 )
          goto LABEL_58;
        v30 = *((_QWORD *)v20 + 1);
        v31 = *((unsigned int *)v20 + 4);
        if ( !v30 || (v28 = 0xFFFFFFFFFFFFFFEFuLL % v30, 0xFFFFFFFFFFFFFFEFuLL / v30 >= v31) )
        {
          LODWORD(v28) = (v19 - (unsigned int)v29) % (unsigned int)v31;
          v33 = (v19 - (unsigned int)v29) / (unsigned int)v31;
          v34 = v30 * v31;
          v35 = v33 + 1;
          if ( v33 == -1 )
            goto LABEL_58;
          while ( 1 )
          {
            v36 = *((_QWORD *)v20 + 6);
            v37 = (int (__fastcall *)(unsigned __int64, _QWORD **, __int64, void *))*((_QWORD *)v20 + 4);
            v120 = 0;
            if ( v37(v34 + 16, &v120, v36, v27) < 0 )
              break;
            v18 = 0;
            --v35;
            *v120 = v20;
            v120[1] = 0;
            v39 = *((_QWORD *)v20 + 8);
            if ( v39 )
              *(_QWORD *)(v39 + 8) = v120;
            *((_DWORD *)v20 + 1) += *((_DWORD *)v20 + 4);
            v40 = v120;
            *((_QWORD *)v20 + 8) = v120;
            if ( !*((_QWORD *)v20 + 7) )
              *((_QWORD *)v20 + 7) = v40;
            if ( !v35 )
              goto LABEL_58;
          }
          v41 = RtlXmlReportErrorFunction(-1073741801, v28, v38, v27);
          v18 = 0;
LABEL_57:
          LODWORD(v28) = v41;
          if ( v41 < 0 )
            goto LABEL_171;
LABEL_58:
          v42 = *((_DWORD *)v20 + 5);
          v27 = v18;
          v29 = (unsigned __int64)v18;
          if ( v19 < v42 )
          {
            LODWORD(v28) = RtlXmlReportErrorFunction(-1073741811, v28, (unsigned int)v18, v18);
          }
          else
          {
            v43 = *((_DWORD *)v20 + 4);
            v44 = v19 - v42;
            v45 = (_QWORD *)*((_QWORD *)v20 + 7);
            if ( v44 < v43 )
            {
LABEL_62:
              v27 = v45;
              if ( v45 )
                v29 = v44;
            }
            else
            {
              while ( v45 )
              {
                v45 = (_QWORD *)v45[1];
                v44 -= v43;
                if ( v44 < v43 )
                  goto LABEL_62;
              }
            }
            LODWORD(v28) = (_DWORD)v18;
            if ( !v45 )
              LODWORD(v28) = -1073741275;
          }
          if ( (v28 & 0x80000000) != 0LL )
LABEL_171:
            RtlRaiseStatus(v28);
          goto LABEL_69;
        }
        v32 = -1073741675;
      }
      else
      {
        v32 = -1073741811;
      }
      v41 = RtlXmlReportErrorFunction(v32, v28, v29, v27);
      goto LABEL_57;
    }
LABEL_173:
    result = CMicrodomBuilder::InsertDefaultAttributes(v4);
    if ( (int)result >= 0 )
    {
      if ( !v11[84] )
        return 0;
      v98 = (__int64 *)*((_QWORD *)v4 + 156);
      if ( v98 )
      {
        if ( *v98 != v98[1] )
          goto LABEL_187;
        if ( (unsigned __int64)(288 * *v98) <= 0x400000 )
        {
          v99 = 2 * *v98;
          if ( !v99 )
            v99 = 1;
        }
        else
        {
          v99 = 29127;
        }
      }
      else
      {
        v99 = 455;
      }
      v100 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 144 * v99);
      if ( !v100 || (v101 = (__int64 *)operator new(0x20u), (v98 = v101) == 0) )
      {
LABEL_192:
        v106 = 1401;
        v104 = "onecore\\base\\xml\\udom_builder.cpp";
        v97 = "CloserElement = this->AllocateStreamObject()";
LABEL_193:
        v107 = v97;
        v105 = "CMicrodomBuilder::StartElement";
        RtlReportErrorOrigination(&v104, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
        return 3221225495LL;
      }
      *v101 = v99;
      v101[1] = 0;
      v101[3] = 0;
      v101[2] = (__int64)v100;
      v101[3] = *((_QWORD *)v4 + 156);
      *((_QWORD *)v4 + 156) = v101;
LABEL_187:
      v102 = 144 * v98[1] + v98[2];
      if ( v102 )
      {
        *(_QWORD *)(v102 + 16) = 0;
        *(_QWORD *)(v102 + 56) = v102 + 48;
        *(_QWORD *)(v102 + 48) = v102 + 48;
        *(_QWORD *)(v102 + 96) = v102 + 88;
        *(_QWORD *)(v102 + 88) = v102 + 88;
        *(_QWORD *)v102 = 0;
        *(_QWORD *)(v102 + 8) = 0;
        *(_QWORD *)(v102 + 40) = 0;
        *(_QWORD *)(v102 + 24) = 0;
        *(_QWORD *)(v102 + 32) = 0;
        *(_QWORD *)(v102 + 64) = 0;
        *(_QWORD *)(v102 + 72) = 0;
        *(_QWORD *)(v102 + 80) = 0;
        *(_QWORD *)(v102 + 104) = 0;
      }
      ++*(_QWORD *)(*((_QWORD *)v4 + 156) + 8LL);
      if ( v102 )
      {
        *(_DWORD *)(v102 + 112) = 196612;
        *(_QWORD *)(v102 + 8) = *((_QWORD *)v4 + 159);
        *(_QWORD *)v102 = (char *)v4 + 1264;
        **((_QWORD **)v4 + 159) = v102;
        *((_QWORD *)v4 + 159) = v102;
        *(_QWORD *)(v102 + 16) = (char *)v4 + 1264;
        ++*((_QWORD *)v4 + 161);
        *((_QWORD *)v4 + 157) = *(_QWORD *)(*((_QWORD *)v4 + 157) + 64LL);
        return 0;
      }
      goto LABEL_192;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800164b0  push    rbp
0x1800164b2  push    r15
0x1800164b4  lea     rbp, [rsp-8]
0x1800164b9  sub     rsp, 108h
0x1800164c0  mov     rax, cs:__security_cookie
0x1800164c7  xor     rax, rsp
0x1800164ca  mov     [rbp+10h+var_40], rax
0x1800164ce  cmp     dword ptr [rdx+23A8h], 3
0x1800164d5  mov     r10, rdx
0x1800164d8  mov     [rsp+110h+var_98], rdx
0x1800164dd  mov     r15, rcx
0x1800164e0  mov     [rsp+110h+var_B8], rcx
0x1800164e5  jz      short loc_1800164F9
0x1800164e7  mov     ecx, 0C00000E5h; Status
0x1800164ec  call    cs:__imp_RtlRaiseStatus
0x1800164f3  nop     dword ptr [rax+rax+00h]
0x1800164f8  int     3; Trap to Debugger
0x1800164f9  mov     rdx, [rcx+4E0h]
0x180016500  xor     eax, eax
0x180016502  mov     [rsp+110h+arg_10], rbx
0x18001650a  xor     r11d, r11d
0x18001650d  mov     [rsp+110h+var_10], rsi
0x180016515  mov     ecx, 1
0x18001651a  mov     [rsp+110h+var_18], rdi
0x180016522  mov     [rsp+110h+var_20], r12
0x18001652a  mov     r12d, 71C7h
0x180016530  mov     [rsp+110h+var_30], r14
0x180016538  mov     [rsp+110h+var_B0], rax
0x18001653d  mov     [rsp+110h+var_A8], eax
0x180016541  test    rdx, rdx
0x180016544  jz      short loc_180016578
0x180016546  mov     rax, [rdx+8]
0x18001654a  cmp     [rdx], rax
0x18001654d  jnz     loc_1800165EB
0x180016553  mov     rax, [rdx]
0x180016556  lea     rbx, [rax+rax]
0x18001655a  lea     rax, [rbx+rbx*8]
0x18001655e  shl     rax, 4
0x180016562  cmp     rax, 400000h
0x180016568  jbe     short loc_18001656F
0x18001656a  mov     ebx, r12d
0x18001656d  jmp     short loc_18001657D
0x18001656f  test    rbx, rbx
0x180016572  cmovz   rbx, rcx
0x180016576  jmp     short loc_18001657D
0x180016578  mov     ebx, 1C7h
0x18001657d  mov     rcx, gs:60h
0x180016586  lea     r8, [rbx+rbx*8]
0x18001658a  shl     r8, 4; Size
0x18001658e  xor     edx, edx; Flags
0x180016590  mov     rcx, [rcx+30h]; HeapHandle
0x180016594  call    cs:__imp_RtlAllocateHeap
0x18001659b  nop     dword ptr [rax+rax+00h]
0x1800165a0  mov     rdi, rax
0x1800165a3  test    rax, rax
0x1800165a6  jz      loc_18001731E
0x1800165ac  mov     ecx, 20h ; ' '; Size
0x1800165b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800165b6  mov     rdx, rax
0x1800165b9  test    rax, rax
0x1800165bc  jz      loc_18001731E
0x1800165c2  mov     r10, [rsp+110h+var_98]
0x1800165c7  xor     r11d, r11d
0x1800165ca  mov     [rax+8], r11
0x1800165ce  mov     [rax+18h], r11
0x1800165d2  mov     [rax], rbx
0x1800165d5  mov     [rax+10h], rdi
0x1800165d9  mov     rcx, [r15+4E0h]
0x1800165e0  mov     [rax+18h], rcx
0x1800165e4  mov     [r15+4E0h], rax
0x1800165eb  mov     rax, [rdx+8]
0x1800165ef  lea     rbx, [rax+rax*8]
0x1800165f3  shl     rbx, 4
0x1800165f7  add     rbx, [rdx+10h]
0x1800165fb  jz      short loc_180016642
0x1800165fd  lea     rax, [rbx+30h]
0x180016601  mov     [rbx+10h], r11
0x180016605  mov     [rax+8], rax
0x180016609  mov     [rax], rax
0x18001660c  lea     rax, [rbx+58h]
0x180016610  mov     [rax+8], rax
0x180016614  mov     [rax], rax
0x180016617  mov     [rbx], r11
0x18001661a  mov     [rbx+8], r11
0x18001661e  mov     [rbx+28h], r11
0x180016622  mov     [rbx+18h], r11
0x180016626  mov     [rbx+20h], r11
0x18001662a  mov     [rbx+40h], r11
0x18001662e  mov     qword ptr [rbx+48h], 0
0x180016636  mov     qword ptr [rbx+50h], 0
0x18001663e  mov     [rbx+68h], r11
0x180016642  mov     rax, [r15+4E0h]
0x180016649  inc     qword ptr [rax+8]
0x18001664d  test    rbx, rbx
0x180016650  jz      loc_18001731E
0x180016656  mov     ecx, [r15+510h]
0x18001665d  mov     rdx, r10; struct CXmlCursor *
0x180016660  mov     [rsp+110h+var_28], r13
0x180016668  lea     r13, [r10+23E0h]
0x18001666f  lea     r9, [r13+30h]; struct _XML_EXTENT *
0x180016673  mov     [rbp+10h+var_50], r13
0x180016677  lea     r8, [r13+18h]; struct _XML_EXTENT *
0x18001667b  lea     eax, [rcx+1]
0x18001667e  mov     [r15+510h], eax
0x180016685  mov     [rbx+48h], ecx
0x180016688  mov     ecx, [r13+48h]
0x18001668c  mov     [rbx+50h], ecx
0x18001668f  mov     eax, [r13+4Ch]
0x180016693  cmp     ecx, eax
0x180016695  mov     [rbx+54h], eax
0x180016698  cmovbe  ecx, eax
0x18001669b  mov     eax, [r15+514h]
0x1800166a2  cmp     eax, ecx
0x1800166a4  cmova   ecx, eax
0x1800166a7  lea     rax, [rsp+110h+var_B0]
0x1800166ac  mov     [r15+514h], ecx
0x1800166b3  mov     rcx, r15; this
0x1800166b6  mov     [rsp+110h+var_E8], rax; struct CMicrodomBuilder::ThreeStringIdPair *
0x1800166bb  mov     [rsp+110h+var_F0], r13; struct _XML_EXTENT *
0x1800166c0  mov     dword ptr [rbx+70h], 10h
0x1800166c7  call    ?AddStringsForElement@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@AEBU_XML_EXTENT@@11PEAUThreeStringIdPair@1@@Z; CMicrodomBuilder::AddStringsForElement(CXmlCursor *,_XML_EXTENT const &,_XML_EXTENT const &,_XML_EXTENT const &,CMicrodomBuilder::ThreeStringIdPair *)
0x1800166cc  test    eax, eax
0x1800166ce  js      loc_1800170CC
0x1800166d4  mov     eax, dword ptr [rsp+110h+var_B0]
0x1800166d8  lea     rcx, [r15+4F0h]
0x1800166df  mov     [rbx+78h], eax
0x1800166e2  mov     eax, dword ptr [rsp+110h+var_B0+4]
0x1800166e6  mov     [rbx+74h], eax
0x1800166e9  mov     eax, [rsp+110h+var_A8]
0x1800166ed  mov     [rbx+7Ch], eax
0x1800166f0  mov     rax, [r15+4E8h]
0x1800166f7  mov     [rbx+40h], rax
0x1800166fb  mov     rax, [rcx+8]
0x1800166ff  mov     [rbx+8], rax
0x180016703  mov     [rbx], rcx
0x180016706  mov     rax, [rcx+8]
0x18001670a  mov     [rax], rbx
0x18001670d  mov     [rcx+8], rbx
0x180016711  mov     [rbx+10h], rcx
0x180016715  inc     qword ptr [rcx+18h]
0x180016719  mov     rdx, [r15+4E8h]; unsigned int
0x180016720  test    rdx, rdx
0x180016723  jz      short loc_18001674C
0x180016725  mov     r8, [rdx+60h]; unsigned int
0x180016729  lea     rcx, [rdx+58h]
0x18001672d  cmp     [r8], rcx
0x180016730  jnz     loc_180017114
0x180016736  lea     rax, [rbx+30h]
0x18001673a  mov     [rax], rcx
0x18001673d  mov     [rax+8], r8
0x180016741  mov     [r8], rax
0x180016744  mov     [rcx+8], rax
0x180016748  inc     qword ptr [rdx+68h]
0x18001674c  mov     [r15+4E8h], rbx
0x180016753  cmp     dword ptr [r13+50h], 0
0x180016758  jz      loc_18001714F
0x18001675e  mov     r13, [rsp+110h+var_98]
0x180016763  xor     r11d, r11d
0x180016766  mov     r14d, r11d
0x180016769  mov     [rsp+110h+var_A0], r11d
0x18001676e  add     r13, 0D80h
0x180016775  mov     r10d, 0C0000095h
0x18001677b  mov     ebx, 0C0000225h
0x180016780  test    r13, r13
0x180016783  jz      loc_180016961
0x180016789  mov     eax, [r13+14h]
0x18001678d  cmp     r14d, eax
0x180016790  jnb     short loc_1800167AC
0x180016792  test    eax, eax
0x180016794  jz      short loc_1800167A7
0x180016796  mov     esi, r14d
0x180016799  imul    rsi, [r13+8]
0x18001679e  add     rsi, [r13+18h]
0x1800167a2  jmp     loc_180016978
0x1800167a7  cmp     r14d, eax
0x1800167aa  jb      short loc_1800167ED
0x1800167ac  mov     edx, [r13+10h]
0x1800167b0  mov     ecx, r14d
0x1800167b3  mov     r8, [r13+38h]
0x1800167b7  sub     ecx, eax
0x1800167b9  cmp     ecx, edx
0x1800167bb  jb      short loc_1800167CF
0x1800167bd  nop     dword ptr [rax]
0x1800167c0  test    r8, r8
0x1800167c3  jz      short loc_1800167CF
0x1800167c5  mov     r8, [r8+8]
0x1800167c9  sub     ecx, edx
0x1800167cb  cmp     ecx, edx
0x1800167cd  jnb     short loc_1800167C0
0x1800167cf  cmp     ecx, edx
0x1800167d1  mov     r9, r8
0x1800167d4  mov     edx, r11d
0x1800167d7  cmovnb  r9, r11
0x1800167db  test    r8, r8
0x1800167de  mov     r8d, ecx
0x1800167e1  cmovz   edx, ebx
0x1800167e4  test    r9, r9
0x1800167e7  cmovz   r8, r11
0x1800167eb  jmp     short loc_1800167FF
0x1800167ed  mov     ecx, 0C000000Dh; int
0x1800167f2  call    ?RtlXmlReportErrorFunction@@YAJJKKPEAX@Z; RtlXmlReportErrorFunction(long,ulong,ulong,void *)
0x1800167f7  mov     edx, eax; unsigned int
0x1800167f9  mov     r9, r11; void *
0x1800167fc  mov     r8, r11; unsigned int
0x1800167ff  test    edx, edx
0x180016801  jns     loc_180016953
0x180016807  mov     rsi, r11
0x18001680a  cmp     edx, ebx
0x18001680c  jnz     loc_180016970
0x180016812  cmp     qword ptr [r13+20h], 0
0x180016817  jz      loc_1800168E1
0x18001681d  mov     r8d, [r13+4]
0x180016821  cmp     r8d, r14d
0x180016824  ja      loc_1800168F5
0x18001682a  mov     rcx, [r13+8]
0x18001682e  mov     edi, [r13+10h]
0x180016832  test    rcx, rcx
0x180016835  jz      short loc_180016850
0x180016837  xor     edx, edx
0x180016839  mov     rax, 0FFFFFFFFFFFFFFEFh
0x180016840  div     rcx
0x180016843  cmp     rax, rdi
0x180016846  jnb     short loc_180016850
0x180016848  mov     ecx, r10d
0x18001684b  jmp     loc_1800168E6
0x180016850  xor     edx, edx
0x180016852  mov     eax, r14d
0x180016855  sub     eax, r8d
0x180016858  div     edi
0x18001685a  imul    rdi, rcx
0x18001685e  mov     ebx, eax
0x180016860  add     ebx, 1
0x180016863  jz      loc_1800168F5
0x180016869  nop     dword ptr [rax+00000000h]
0x180016870  mov     r8, [r13+30h]
0x180016874  lea     rdx, [rbp+10h+var_48]
0x180016878  mov     rax, [r13+20h]
0x18001687c  lea     rcx, [rdi+10h]
0x180016880  mov     [rbp+10h+var_48], r11
0x180016884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016889  test    eax, eax
0x18001688b  js      short loc_1800168D2
0x18001688d  mov     rax, [rbp+10h+var_48]
0x180016891  xor     r11d, r11d
0x180016894  dec     ebx
0x180016896  mov     [rax], r13
0x180016899  mov     rax, [rbp+10h+var_48]
0x18001689d  mov     [rax+8], r11
0x1800168a1  mov     rcx, [r13+40h]
0x1800168a5  test    rcx, rcx
0x1800168a8  jz      short loc_1800168B2
0x1800168aa  mov     rax, [rbp+10h+var_48]
0x1800168ae  mov     [rcx+8], rax
0x1800168b2  mov     eax, [r13+10h]
0x1800168b6  add     [r13+4], eax
0x1800168ba  mov     rcx, [rbp+10h+var_48]
0x1800168be  mov     [r13+40h], rcx
0x1800168c2  cmp     [r13+38h], r11
0x1800168c6  jnz     short loc_1800168CC
0x1800168c8  mov     [r13+38h], rcx
0x1800168cc  test    ebx, ebx
0x1800168ce  jnz     short loc_180016870
0x1800168d0  jmp     short loc_1800168F5
0x1800168d2  mov     ecx, 0C0000017h; int
0x1800168d7  call    ?RtlXmlReportErrorFunction@@YAJJKKPEAX@Z; RtlXmlReportErrorFunction(long,ulong,ulong,void *)
0x1800168dc  xor     r11d, r11d
0x1800168df  jmp     short loc_1800168EB
0x1800168e1  mov     ecx, 0C000000Dh; int
0x1800168e6  call    ?RtlXmlReportErrorFunction@@YAJJKKPEAX@Z; RtlXmlReportErrorFunction(long,ulong,ulong,void *)
0x1800168eb  mov     edx, eax; unsigned int
0x1800168ed  test    eax, eax
0x1800168ef  js      loc_18001713C
0x1800168f5  mov     eax, [r13+14h]
0x1800168f9  mov     r9, r11; void *
0x1800168fc  mov     r8, r11; unsigned int
0x1800168ff  cmp     r14d, eax
0x180016902  jb      short loc_18001693F
0x180016904  mov     edx, [r13+10h]
0x180016908  mov     ecx, r14d
0x18001690b  sub     ecx, eax
0x18001690d  mov     rax, [r13+38h]
0x180016911  cmp     ecx, edx
0x180016913  jb      short loc_180016924
0x180016915  test    rax, rax
0x180016918  jz      short loc_18001692F
0x18001691a  mov     rax, [rax+8]
0x18001691e  sub     ecx, edx
0x180016920  cmp     ecx, edx
0x180016922  jnb     short loc_180016915
0x180016924  mov     r9, rax
0x180016927  test    rax, rax
0x18001692a  jz      short loc_18001692F
0x18001692c  mov     r8d, ecx
0x18001692f  test    rax, rax
0x180016932  mov     edx, r11d
0x180016935  mov     eax, 0C0000225h
0x18001693a  cmovz   edx, eax
0x18001693d  jmp     short loc_18001694B
0x18001693f  mov     ecx, 0C000000Dh; int
0x180016944  call    ?RtlXmlReportErrorFunction@@YAJJKKPEAX@Z; RtlXmlReportErrorFunction(long,ulong,ulong,void *)
  ... truncated ...
```
