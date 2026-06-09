# Microsoft::Resources::MrmFile::GetDefaultQualifierMapping(int,Microsoft::Resources::RemapAtomPool const * *)

- ea: `0x18001c530`
- end: `0x18001cb01`
- name: `?GetDefaultQualifierMapping@MrmFile@Resources@Microsoft@@UEBAJHPEAPEBVRemapAtomPool@23@@Z`
- size: `1489`
- prototype: `__int64 __fastcall(Microsoft::Resources::MrmFile *__hidden this, int, const struct Microsoft::Resources::RemapAtomPool **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180016b00`
- `0x18001c2ec`
- `0x18001c530`
- `0x18001cb08`
- `0x18001cc48`
- `0x1800204c0`
- `0x180028ad0`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x18002ec70`
- `0x180061954`
- `0x18006fe40`
- `0x1800959a0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c920`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c920`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c92e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c92e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001c9ce`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001c9ce`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::MrmFile::GetDefaultQualifierMapping(
        Microsoft::Resources::MrmFile *this,
        int a2,
        const struct Microsoft::Resources::RemapAtomPool **a3)
{
  const WCHAR *v3; // r15
  int v6; // eax
  unsigned int v7; // esi
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  Microsoft::Resources *v16; // rsi
  Microsoft::Resources *v17; // r14
  int v18; // eax
  unsigned int v19; // r15d
  void *v20; // rbx
  __int64 v22; // r13
  int v23; // r12d
  const WCHAR *v24; // rax
  int v25; // ecx
  const struct Microsoft::Resources::IEnvironment *v26; // r8
  const WCHAR *v27; // r9
  char v28; // al
  __int64 v29; // rdx
  unsigned int v30; // r13d
  __int64 v31; // r14
  __int64 (__fastcall *v32)(__int64, LPVOID, Microsoft::Resources *, __int64); // r15
  __int64 v33; // rax
  __int64 v34; // r9
  LPVOID v35; // rax
  int v36; // ecx
  LPVOID v37; // rdx
  int v38; // eax
  int v39; // r14d
  Microsoft::Resources::UnifiedEnvironment *v40; // r10
  const unsigned __int16 *v41; // rax
  const unsigned __int16 *v42; // rdx
  int v43; // eax
  int v44; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v46; // rdx
  const WCHAR *v47; // rsi
  unsigned __int16 *v48; // rcx
  const WCHAR *Ref; // rax
  int v50; // eax
  const struct Microsoft::Resources::IEnvironmentVersionInfo *v51; // r8
  bool v52; // al
  int v53; // eax
  Microsoft::Resources::MrmFileResolver *v54; // rcx
  int GlobalIndex; // eax
  unsigned int v56; // edi
  int EnvironmentInfo; // eax
  int v58; // r14d
  int v59; // eax
  unsigned int v60; // ebx
  int bIgnoreCase; // [rsp+20h] [rbp-49h]
  int bIgnoreCasea; // [rsp+20h] [rbp-49h]
  Microsoft::Resources::EnvironmentMapping *v63; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int16 **v64; // [rsp+48h] [rbp-21h]
  __int64 v65; // [rsp+50h] [rbp-19h] BYREF
  LPCWCH lpString1; // [rsp+58h] [rbp-11h] BYREF
  const int *v67; // [rsp+60h] [rbp-9h] BYREF
  Microsoft::Resources *v68; // [rsp+68h] [rbp-1h] BYREF
  LPVOID *p_lpMem; // [rsp+70h] [rbp+7h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp+Fh] BYREF
  int v71; // [rsp+80h] [rbp+17h]
  __int64 v72; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int v74; // [rsp+D8h] [rbp+6Fh] BYREF
  const struct Microsoft::Resources::RemapAtomPool **v75; // [rsp+E0h] [rbp+77h]
  unsigned __int16 *v76; // [rsp+E8h] [rbp+7Fh]

  v75 = a3;
  v3 = 0;
  *a3 = 0;
  if ( a2 )
  {
    if ( !*((_QWORD *)this + 4) )
      return 2147942487LL;
    v54 = (Microsoft::Resources::MrmFileResolver *)*((_QWORD *)this + 5);
    v74 = 0;
    GlobalIndex = Microsoft::Resources::MrmFileResolver::GetGlobalIndex(v54, a2, &v74);
    v56 = GlobalIndex;
    if ( GlobalIndex >= 0 )
    {
      v59 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const struct Microsoft::Resources::RemapAtomPool **))(**((_QWORD **)this + 4) + 152LL))(
              *((_QWORD *)this + 4),
              (unsigned int)v74,
              a3);
      v60 = v59;
      if ( v59 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x489,
          (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\mrmfile.cpp",
          (const char *)(unsigned int)v59,
          bIgnoreCase);
        return v60;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x487,
        (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\mrmfile.cpp",
        (const char *)(unsigned int)GlobalIndex,
        bIgnoreCase);
      return v56;
    }
  }
  lpMem = 0;
  p_lpMem = &lpMem;
  v71 = 0;
  v67 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UserLanguageProfileQVProvider>::`vftable';
  v72 = 0;
  v68 = 0;
  v6 = Microsoft::Resources::EnvironmentVersionInfo::CreateEmpty(&v68);
  v7 = v6;
  if ( v6 < 0 )
  {
    v46 = 1113;
LABEL_66:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v46,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\mrmfile.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
    if ( v68 )
      (**(void (__fastcall ***)(Microsoft::Resources *, __int64))v68)(v68, 1);
    goto LABEL_58;
  }
  v8 = *(_QWORD *)this;
  v65 = 0;
  v6 = (*(__int64 (__fastcall **)(Microsoft::Resources::MrmFile *, __int64 *))(v8 + 168))(this, &v65);
  v7 = v6;
  if ( v6 < 0 )
  {
    v46 = 1116;
    goto LABEL_66;
  }
  v11 = *(_QWORD *)(v65 + 16);
  if ( v11 )
  {
    v9 = gEnvironmentMappingSectionType;
    v12 = 0;
    v10 = *((_QWORD *)&gEnvironmentMappingSectionType + 1);
    v13 = *(_QWORD *)(v65 + 24);
    while ( (__int16)v12 < *(__int16 *)(v11 + 24) )
    {
      if ( *(_DWORD *)(v13 + 28) && *(_OWORD *)v13 == gEnvironmentMappingSectionType )
        goto LABEL_12;
      LOWORD(v12) = v12 + 1;
      v13 += 32;
    }
  }
  v12 = 0xFFFF;
LABEL_12:
  v14 = *(_QWORD *)this;
  v63 = 0;
  if ( (_WORD)v12 != 0xFFFF )
  {
    v53 = (*(__int64 (__fastcall **)(Microsoft::Resources::MrmFile *, _QWORD, __int64, Microsoft::Resources::EnvironmentMapping **))(v14 + 120))(
            this,
            0,
            v12,
            &v63);
    v7 = v53;
    if ( v53 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x463,
        (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\mrmfile.cpp",
        (const char *)(unsigned int)v53,
        bIgnoreCase);
      goto LABEL_93;
    }
    v16 = v68;
    EnvironmentInfo = Microsoft::Resources::EnvironmentMapping::GetEnvironmentInfo(
                        v63,
                        (struct Microsoft::Resources::StringResult *)&p_lpMem,
                        v68);
    v58 = EnvironmentInfo;
    if ( EnvironmentInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x464,
        (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\mrmfile.cpp",
        (const char *)(unsigned int)EnvironmentInfo,
        bIgnoreCase);
      v7 = v58;
      goto LABEL_93;
    }
    v17 = v16;
LABEL_24:
    v22 = (*(__int64 (__fastcall **)(Microsoft::Resources::MrmFile *))(*(_QWORD *)this + 16LL))(this);
    v76 = (unsigned __int16 *)v22;
    v23 = -2147024809;
    if ( p_lpMem && (*p_lpMem || !*((_DWORD *)p_lpMem + 2)) && (*((_DWORD *)p_lpMem + 2) || !*p_lpMem) )
    {
      v24 = (const WCHAR *)p_lpMem[2];
      v25 = 0;
    }
    else
    {
      v24 = 0;
      v25 = -2147024809;
    }
    v26 = *(const struct Microsoft::Resources::IEnvironment **)(v22 + 16);
    v27 = 0;
    if ( v25 >= 0 )
      v27 = v24;
    lpString1 = v27;
    v28 = Microsoft::Resources::EnvironmentReference::CheckIsCompatible(v27, v17, v26);
    LOBYTE(v74) = v28;
    if ( !v28 )
    {
      v29 = *(_QWORD *)(v22 + 40);
      v30 = 0;
      if ( v29 )
      {
        if ( *(_DWORD *)(v29 + 12) )
        {
          v47 = lpString1;
          v48 = v76;
          while ( 1 )
          {
            if ( v28 )
            {
LABEL_63:
              v16 = v68;
              break;
            }
            if ( v30 < *(_DWORD *)(v29 + 12) )
            {
              v64 = *(unsigned __int16 ***)(*(_QWORD *)v29 + 8LL * v30);
              lpString1 = v64[5];
              Ref = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)(v64 + 1));
              v50 = CompareStringOrdinal(v47, -1, Ref, -1, 1);
              if ( (unsigned int)IntToComparison((unsigned int)(v50 - 2)) )
              {
                v48 = v76;
LABEL_79:
                v28 = v74;
                goto LABEL_75;
              }
              v52 = Microsoft::Resources::CheckEnvironmentVersionIsIdentical(
                      v17,
                      (const struct Microsoft::Resources::IEnvironmentVersionInfo *)lpString1,
                      v51);
              v48 = v76;
              if ( !v52 )
                goto LABEL_79;
              v28 = 1;
              LOBYTE(v74) = 1;
              v3 = v64[6];
            }
LABEL_75:
            v29 = *((_QWORD *)v48 + 5);
            if ( ++v30 >= *(_DWORD *)(v29 + 12) )
              goto LABEL_63;
          }
        }
      }
    }
    lpString1 = v3;
    if ( v28 )
      goto LABEL_55;
    v74 = 0;
    v64 = 0;
    v76 = 0;
    if ( v63 )
    {
      v74 = *((unsigned __int16 *)v63 + 9);
      v64 = (unsigned __int16 **)*((_QWORD *)v63 + 6);
      v76 = (unsigned __int16 *)*((_QWORD *)v63 + 5);
    }
    else
    {
      v31 = (*(__int64 (__fastcall **)(Microsoft::Resources::MrmFile *))(*(_QWORD *)this + 8LL))(this);
      v32 = *(__int64 (__fastcall **)(__int64, LPVOID, Microsoft::Resources *, __int64))(*(_QWORD *)v31 + 168LL);
      v33 = (*(__int64 (__fastcall **)(Microsoft::Resources::MrmFile *))(*(_QWORD *)this + 16LL))(this);
      v34 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
      if ( p_lpMem && (*p_lpMem || !*((_DWORD *)p_lpMem + 2)) && (*((_DWORD *)p_lpMem + 2) || !*p_lpMem) )
      {
        v35 = p_lpMem[2];
        v36 = 0;
      }
      else
      {
        v35 = 0;
        v36 = -2147024809;
      }
      v37 = 0;
      if ( v36 >= 0 )
        v37 = v35;
      v38 = v32(v31, v37, v16, v34);
      v39 = v38;
      if ( v38 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x478,
          (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\mrmfile.cpp",
          (const char *)(unsigned int)v38,
          (int)&v74);
        if ( v16 )
          (**(void (__fastcall ***)(Microsoft::Resources *, __int64))v16)(v16, 1);
        v7 = v39;
        goto LABEL_58;
      }
    }
    v40 = (Microsoft::Resources::UnifiedEnvironment *)(*(__int64 (__fastcall **)(Microsoft::Resources::MrmFile *))(*(_QWORD *)this + 16LL))(this);
    if ( p_lpMem && (*p_lpMem || !*((_DWORD *)p_lpMem + 2)) && (*((_DWORD *)p_lpMem + 2) || !*p_lpMem) )
    {
      v41 = (const unsigned __int16 *)p_lpMem[2];
      v23 = 0;
    }
    else
    {
      v41 = 0;
    }
    v42 = 0;
    if ( v23 >= 0 )
      v42 = v41;
    v43 = Microsoft::Resources::UnifiedEnvironment::AddCompatibleEnvironment(
            v40,
            v42,
            v16,
            v74,
            (const unsigned __int16 *const *)v64,
            v76,
            (const struct Microsoft::Resources::RemapAtomPool **)&lpString1);
    v44 = v43;
    if ( v43 >= 0 )
    {
      v3 = lpString1;
LABEL_55:
      *v75 = (const struct Microsoft::Resources::RemapAtomPool *)v3;
      if ( v16 )
        (**(void (__fastcall ***)(Microsoft::Resources *, __int64))v16)(v16, 1);
      v7 = 0;
LABEL_58:
      DefStringResult_Clear(&lpMem, 1);
      return v7;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47C,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\mrmfile.cpp",
      (const char *)(unsigned int)v43,
      bIgnoreCasea);
    v7 = v44;
LABEL_93:
    Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::EnvironmentReferenceBuilder>::~AutoDeletePtr<Microsoft::Resources::Build::EnvironmentReferenceBuilder>(&v67);
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
    return v7;
  }
  v15 = (*(__int64 (__fastcall **)(Microsoft::Resources::MrmFile *, __int64, __int64, __int64))(v14 + 8))(
          this,
          v9,
          v12,
          v10);
  v16 = v68;
  v17 = v68;
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID **, Microsoft::Resources *))(*(_QWORD *)v15 + 152LL))(
          v15,
          *(_QWORD *)(*((_QWORD *)this + 1) + 16LL),
          &p_lpMem,
          v68);
  v19 = v18;
  if ( v18 >= 0 )
  {
    v3 = 0;
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x468,
    (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\mrmfile.cpp",
    (const char *)(unsigned int)v18,
    bIgnoreCase);
  if ( v16 )
    (**(void (__fastcall ***)(Microsoft::Resources *, __int64))v16)(v16, 1);
  v20 = lpMem;
  if ( (lpMem || !v71) && (v71 || !lpMem) )
  {
    v72 = 0;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v20);
    }
  }
  return v19;
}

```

## disassembly

```asm
0x18001c530  mov     [rsp-8+arg_0], rbx
0x18001c535  mov     [rsp-8+arg_10], r8
0x18001c53a  push    rbp
0x18001c53b  push    rsi
0x18001c53c  push    rdi
0x18001c53d  push    r12
0x18001c53f  push    r13
0x18001c541  push    r14
0x18001c543  push    r15
0x18001c545  lea     rbp, [rsp-27h]
0x18001c54a  sub     rsp, 90h
0x18001c551  xor     r15d, r15d
0x18001c554  mov     rsi, r8
0x18001c557  mov     [r8], r15
0x18001c55a  mov     rbx, rcx
0x18001c55d  test    edx, edx
0x18001c55f  jnz     loc_18001CA61
0x18001c565  lea     rax, [rbp+57h+lpMem]
0x18001c569  mov     [rbp+57h+lpMem], r15
0x18001c56d  mov     [rbp+57h+var_50], rax
0x18001c571  lea     rcx, [rbp+57h+var_58]; struct Microsoft::Resources::EnvironmentVersionInfo **
0x18001c575  lea     rax, ??_7?$AutoDeletePtr@VUserLanguageProfileQVProvider@Resources@Microsoft@@@Resources@Microsoft@@6B@; const Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UserLanguageProfileQVProvider>::`vftable'
0x18001c57c  mov     [rbp+57h+var_40], r15d
0x18001c580  mov     [rbp+57h+var_60], rax
0x18001c584  mov     [rbp+57h+var_38], r15
0x18001c588  mov     [rbp+57h+var_58], r15
0x18001c58c  call    ?CreateEmpty@EnvironmentVersionInfo@Resources@Microsoft@@SAJPEAPEAV123@@Z; Microsoft::Resources::EnvironmentVersionInfo::CreateEmpty(Microsoft::Resources::EnvironmentVersionInfo * *)
0x18001c591  mov     esi, eax
0x18001c593  test    eax, eax
0x18001c595  js      loc_18001CA57
0x18001c59b  mov     rax, [rbx]
0x18001c59e  lea     rdx, [rbp+57h+var_70]
0x18001c5a2  mov     rcx, rbx
0x18001c5a5  mov     [rbp+57h+var_70], r15
0x18001c5a9  mov     rax, [rax+0A8h]
0x18001c5b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5b5  mov     esi, eax
0x18001c5b7  test    eax, eax
0x18001c5b9  js      loc_18001C945
0x18001c5bf  mov     rax, [rbp+57h+var_70]
0x18001c5c3  lea     edi, [r15+1]
0x18001c5c7  or      r11d, 0FFFFFFFFh
0x18001c5cb  mov     rcx, [rax+10h]
0x18001c5cf  test    rcx, rcx
0x18001c5d2  jz      short loc_18001C611
0x18001c5d4  mov     rdx, qword ptr cs:gEnvironmentMappingSectionType
0x18001c5db  mov     r8d, r15d
0x18001c5de  mov     r9, qword ptr cs:gEnvironmentMappingSectionType+8
0x18001c5e5  mov     rax, [rax+18h]
0x18001c5e9  movzx   r10d, word ptr [rcx+18h]
0x18001c5ee  cmp     r8w, r10w
0x18001c5f2  jge     short loc_18001C611
0x18001c5f4  cmp     [rax+1Ch], r15d
0x18001c5f8  jz      short loc_18001C5FF
0x18001c5fa  cmp     [rax], rdx
0x18001c5fd  jz      short loc_18001C609
0x18001c5ff  add     r8w, di
0x18001c603  add     rax, 20h ; ' '
0x18001c607  jmp     short loc_18001C5EE
0x18001c609  cmp     [rax+8], r9
0x18001c60d  jnz     short loc_18001C5FF
0x18001c60f  jmp     short loc_18001C615
0x18001c611  movzx   r8d, r11w
0x18001c615  mov     rax, [rbx]
0x18001c618  mov     rcx, rbx
0x18001c61b  mov     [rbp+57h+var_80], r15
0x18001c61f  cmp     r8w, r11w
0x18001c623  jnz     loc_18001CA71
0x18001c629  mov     rax, [rax+8]
0x18001c62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c632  mov     rdx, [rbx+8]
0x18001c636  lea     r8, [rbp+57h+var_50]
0x18001c63a  mov     rsi, [rbp+57h+var_58]
0x18001c63e  mov     r10, rax
0x18001c641  mov     r9, rsi
0x18001c644  mov     r14, rsi
0x18001c647  mov     rcx, [rax]
0x18001c64a  mov     rdx, [rdx+10h]
0x18001c64e  mov     rax, [rcx+98h]
0x18001c655  mov     rcx, r10
0x18001c658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c65d  mov     r15d, eax
0x18001c660  test    eax, eax
0x18001c662  jns     short loc_18001C6D9
0x18001c664  mov     rcx, [rbp+5Fh]; this
0x18001c668  lea     r8, aMinkernelMrtMr_32; "minkernel\\mrt\\mrm\\mrmmin\\mrmfile.cp"...
0x18001c66f  mov     r9d, eax; char *
0x18001c672  mov     edx, 468h; void *
0x18001c677  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c67c  test    rsi, rsi
0x18001c67f  jz      short loc_18001C691
0x18001c681  mov     r8, [rsi]
0x18001c684  mov     edx, edi
0x18001c686  mov     rcx, rsi
0x18001c689  mov     rax, [r8]
0x18001c68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c691  mov     rbx, [rbp+57h+lpMem]
0x18001c695  mov     eax, [rbp+57h+var_40]
0x18001c698  test    rbx, rbx
0x18001c69b  jnz     short loc_18001C6A1
0x18001c69d  test    eax, eax
0x18001c69f  jnz     short loc_18001C6BB
0x18001c6a1  test    eax, eax
0x18001c6a3  jnz     short loc_18001C6AA
0x18001c6a5  test    rbx, rbx
0x18001c6a8  jnz     short loc_18001C6BB
0x18001c6aa  mov     [rbp+57h+var_38], 0
0x18001c6b2  test    rbx, rbx
0x18001c6b5  jnz     loc_18001C920
0x18001c6bb  mov     eax, r15d
0x18001c6be  mov     rbx, [rsp+0C0h+arg_0]
0x18001c6c6  add     rsp, 90h
0x18001c6cd  pop     r15
0x18001c6cf  pop     r14
0x18001c6d1  pop     r13
0x18001c6d3  pop     r12
0x18001c6d5  pop     rdi
0x18001c6d6  pop     rsi
0x18001c6d7  pop     rbp
0x18001c6d8  retn
0x18001c6d9  xor     r15d, r15d
0x18001c6dc  mov     rax, [rbx]
0x18001c6df  mov     rcx, rbx
0x18001c6e2  mov     rax, [rax+10h]
0x18001c6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6eb  mov     rdx, [rbp+57h+var_50]
0x18001c6ef  mov     r13, rax
0x18001c6f2  mov     [rbp+57h+arg_18], rax
0x18001c6f6  mov     r12d, 80070057h
0x18001c6fc  test    rdx, rdx
0x18001c6ff  jz      loc_18001CA14
0x18001c705  cmp     [rdx], r15
0x18001c708  jnz     short loc_18001C714
0x18001c70a  cmp     [rdx+8], r15d
0x18001c70e  ja      loc_18001CA14
0x18001c714  cmp     [rdx+8], r15d
0x18001c718  jnz     short loc_18001C723
0x18001c71a  cmp     [rdx], r15
0x18001c71d  jnz     loc_18001CA14
0x18001c723  mov     rax, [rdx+10h]
0x18001c727  mov     ecx, r15d
0x18001c72a  mov     r8, [r13+10h]; struct Microsoft::Resources::IEnvironment *
0x18001c72e  test    ecx, ecx
0x18001c730  mov     r9, r15
0x18001c733  mov     rdx, r14; struct Microsoft::Resources::IEnvironmentVersionInfo *
0x18001c736  cmovns  r9, rax
0x18001c73a  mov     rcx, r9; lpString1
0x18001c73d  mov     [rbp+57h+lpString1], r9
0x18001c741  call    ?CheckIsCompatible@EnvironmentReference@Resources@Microsoft@@SA_NPEBGPEBVIEnvironmentVersionInfo@23@PEBVIEnvironment@23@@Z; Microsoft::Resources::EnvironmentReference::CheckIsCompatible(ushort const *,Microsoft::Resources::IEnvironmentVersionInfo const *,Microsoft::Resources::IEnvironment const *)
0x18001c746  mov     byte ptr [rbp+57h+arg_8], al
0x18001c749  test    al, al
0x18001c74b  jnz     loc_18001C93D
0x18001c751  mov     rdx, [r13+28h]
0x18001c755  xor     r13d, r13d
0x18001c758  test    rdx, rdx
0x18001c75b  jnz     loc_18001C981
0x18001c761  mov     [rbp+57h+lpString1], r15
0x18001c765  test    al, al
0x18001c767  jnz     loc_18001C8BB
0x18001c76d  mov     rcx, [rbp+57h+var_80]
0x18001c771  mov     [rbp+57h+arg_8], r13d
0x18001c775  mov     [rbp+57h+var_78], r13
0x18001c779  mov     [rbp+57h+arg_18], r13
0x18001c77d  test    rcx, rcx
0x18001c780  jnz     loc_18001CA3B
0x18001c786  mov     rax, [rbx]
0x18001c789  mov     rcx, rbx
0x18001c78c  mov     rax, [rax+8]
0x18001c790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c795  mov     r14, rax
0x18001c798  mov     rcx, [rax]
0x18001c79b  mov     r15, [rcx+0A8h]
0x18001c7a2  mov     rcx, [rbx]
0x18001c7a5  mov     rax, [rcx+10h]
0x18001c7a9  mov     rcx, rbx
0x18001c7ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7b1  mov     rdx, rax
0x18001c7b4  mov     rcx, [rax]
0x18001c7b7  mov     rax, [rcx+8]
0x18001c7bb  mov     rcx, rdx
0x18001c7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7c3  mov     rdx, [rbp+57h+var_50]
0x18001c7c7  mov     r9, rax
0x18001c7ca  test    rdx, rdx
0x18001c7cd  jz      loc_18001CA28
0x18001c7d3  cmp     [rdx], r13
0x18001c7d6  jnz     short loc_18001C7E2
0x18001c7d8  cmp     [rdx+8], r13d
0x18001c7dc  ja      loc_18001CA28
0x18001c7e2  cmp     [rdx+8], r13d
0x18001c7e6  jnz     short loc_18001C7F1
0x18001c7e8  cmp     [rdx], r13
0x18001c7eb  jnz     loc_18001CA28
0x18001c7f1  mov     rax, [rdx+10h]
0x18001c7f5  mov     ecx, r13d
0x18001c7f8  test    ecx, ecx
0x18001c7fa  mov     rdx, r13
0x18001c7fd  mov     r8, rsi
0x18001c800  mov     rcx, r14
0x18001c803  cmovns  rdx, rax
0x18001c807  lea     rax, [rbp+57h+arg_18]
0x18001c80b  mov     [rsp+0C0h+var_90], rax
0x18001c810  lea     rax, [rbp+57h+var_78]
0x18001c814  mov     [rsp+0C0h+var_98], rax
0x18001c819  lea     rax, [rbp+57h+arg_8]
0x18001c81d  mov     qword ptr [rsp+0C0h+bIgnoreCase], rax; int
0x18001c822  mov     rax, r15
0x18001c825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c82a  mov     r14d, eax
0x18001c82d  test    eax, eax
0x18001c82f  js      loc_18001C8EE
0x18001c835  mov     rax, [rbx]
0x18001c838  mov     rcx, rbx
0x18001c83b  mov     rax, [rax+10h]
0x18001c83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c844  mov     rdx, [rbp+57h+var_50]
0x18001c848  mov     r10, rax
0x18001c84b  mov     r8, [rbp+57h+arg_18]
0x18001c84f  mov     r9, [rbp+57h+var_78]
0x18001c853  test    rdx, rdx
0x18001c856  jz      loc_18001CA33
0x18001c85c  cmp     [rdx], r13
0x18001c85f  jnz     short loc_18001C86B
0x18001c861  cmp     [rdx+8], r13d
0x18001c865  ja      loc_18001CA33
0x18001c86b  cmp     [rdx+8], r13d
0x18001c86f  jnz     short loc_18001C87A
0x18001c871  cmp     [rdx], r13
0x18001c874  jnz     loc_18001CA33
0x18001c87a  mov     rax, [rdx+10h]
0x18001c87e  mov     r12d, r13d
0x18001c881  test    r12d, r12d
0x18001c884  mov     rdx, r13
0x18001c887  mov     rcx, r10; this
0x18001c88a  cmovns  rdx, rax; unsigned __int16 *
0x18001c88e  lea     rax, [rbp+57h+lpString1]
0x18001c892  mov     [rsp+0C0h+var_90], rax; struct Microsoft::Resources::RemapAtomPool **
0x18001c897  mov     [rsp+0C0h+var_98], r8; unsigned __int16 *
0x18001c89c  mov     r8, rsi; struct Microsoft::Resources::EnvironmentVersionInfo *
0x18001c89f  mov     qword ptr [rsp+0C0h+bIgnoreCase], r9; int
0x18001c8a4  mov     r9d, [rbp+57h+arg_8]; int
0x18001c8a8  call    ?AddCompatibleEnvironment@UnifiedEnvironment@Resources@Microsoft@@QEAAJPEBGPEBVEnvironmentVersionInfo@23@HPEBQEBG0PEAPEBVRemapAtomPool@23@@Z; Microsoft::Resources::UnifiedEnvironment::AddCompatibleEnvironment(ushort const *,Microsoft::Resources::EnvironmentVersionInfo const *,int,ushort const * const *,ushort const *,Microsoft::Resources::RemapAtomPool const * *)
0x18001c8ad  mov     ebx, eax
0x18001c8af  test    eax, eax
0x18001c8b1  js      loc_18001CAA8
0x18001c8b7  mov     r15, [rbp+57h+lpString1]
0x18001c8bb  mov     rax, [rbp+57h+arg_10]
0x18001c8bf  mov     [rax], r15
0x18001c8c2  test    rsi, rsi
0x18001c8c5  jnz     short loc_18001C8DC
0x18001c8c7  mov     esi, r13d
0x18001c8ca  mov     edx, edi
0x18001c8cc  lea     rcx, [rbp+57h+lpMem]
0x18001c8d0  call    DefStringResult_Clear
0x18001c8d5  mov     eax, esi
0x18001c8d7  jmp     loc_18001C6BE
0x18001c8dc  mov     rax, [rsi]
0x18001c8df  mov     edx, edi
0x18001c8e1  mov     rcx, rsi
0x18001c8e4  mov     rax, [rax]
0x18001c8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8ec  jmp     short loc_18001C8C7
0x18001c8ee  mov     rcx, [rbp+5Fh]; this
0x18001c8f2  lea     r8, aMinkernelMrtMr_32; "minkernel\\mrt\\mrm\\mrmmin\\mrmfile.cp"...
0x18001c8f9  mov     r9d, r14d; char *
0x18001c8fc  mov     edx, 478h; void *
0x18001c901  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c906  test    rsi, rsi
0x18001c909  jz      short loc_18001C91B
0x18001c90b  mov     rcx, [rsi]
0x18001c90e  mov     edx, edi
0x18001c910  mov     rax, [rcx]
0x18001c913  mov     rcx, rsi
0x18001c916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c91b  mov     esi, r14d
0x18001c91e  jmp     short loc_18001C8CA
0x18001c920  call    cs:__imp_GetProcessHeap
0x18001c926  mov     r8, rbx; lpMem
0x18001c929  xor     edx, edx; dwFlags
0x18001c92b  mov     rcx, rax; hHeap
0x18001c92e  call    cs:__imp_HeapFree
0x18001c934  jmp     loc_18001C6BB
0x18001c939  mov     rsi, [rbp+57h+var_58]
0x18001c93d  xor     r13d, r13d
0x18001c940  jmp     loc_18001C761
0x18001c945  mov     edx, 45Ch; void *
0x18001c94a  mov     rcx, [rbp+5Fh]; this
0x18001c94e  lea     r8, aMinkernelMrtMr_32; "minkernel\\mrt\\mrm\\mrmmin\\mrmfile.cp"...
0x18001c955  mov     r9d, eax; char *
0x18001c958  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c95d  mov     rcx, [rbp+57h+var_58]
0x18001c961  mov     edi, 1
0x18001c966  test    rcx, rcx
0x18001c969  jz      loc_18001C8CA
0x18001c96f  mov     rax, [rcx]
0x18001c972  mov     edx, edi
0x18001c974  mov     rax, [rax]
0x18001c977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c97c  jmp     loc_18001C8CA
0x18001c981  cmp     [rdx+0Ch], r13d
  ... truncated ...
```
