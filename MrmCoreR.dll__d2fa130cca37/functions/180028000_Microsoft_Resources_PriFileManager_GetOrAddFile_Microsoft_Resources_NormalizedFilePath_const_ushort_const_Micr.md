# Microsoft::Resources::PriFileManager::GetOrAddFile(Microsoft::Resources::NormalizedFilePath const *,ushort const *,Microsoft::Resources::LoadPriFlags,Microsoft::Resources::ManagedFile * *)

- ea: `0x180028000`
- end: `0x180028426`
- name: `?GetOrAddFile@PriFileManager@Resources@Microsoft@@QEBAJPEBVNormalizedFilePath@23@PEBGW4LoadPriFlags@23@PEAPEAVManagedFile@23@@Z`
- size: `1062`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `10`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000fda8`
- `0x18001028c`
- `0x1800130e0`
- `0x180018934`
- `0x18001a374`

## callees

- `0x180011054`
- `0x180026630`
- `0x1800268c0`
- `0x180028000`
- `0x180028510`
- `0x180028ad0`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x1800324f0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180028353`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180028353`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c1612`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c1612`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c1620`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c1620`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800281e4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028308`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800281e4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028308`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::PriFileManager::GetOrAddFile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        BOOL a4,
        _QWORD *a5)
{
  __int64 v9; // rax
  _WORD *v10; // rcx
  __int64 v11; // rdx
  int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rdx
  unsigned __int64 v16; // r9
  int v17; // edi
  __int64 v18; // rax
  int v19; // ecx
  __int64 v20; // rdx
  unsigned int i; // ebx
  __int64 v22; // rax
  __int64 v23; // rsi
  __int64 v24; // rcx
  const WCHAR *v25; // rax
  int v26; // edx
  const WCHAR *v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // r9
  int Instance; // eax
  __int64 *v31; // rdi
  unsigned int v32; // edx
  __int64 v33; // rcx
  __int64 v34; // rax
  WCHAR *v35; // rcx
  WCHAR *v36; // r14
  void **v37; // rbx
  int v38; // eax
  int v39; // eax
  wchar_t *v40; // rax
  int v41; // esi
  __int64 v42; // rdx
  void *v43; // rdi
  HANDLE ProcessHeap; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-38h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-38h]
  __int64 *v47; // [rsp+30h] [rbp-28h] BYREF
  __int64 v48; // [rsp+38h] [rbp-20h] BYREF
  int v49; // [rsp+40h] [rbp-18h]
  __int64 v50; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  __int64 v52; // [rsp+C0h] [rbp+68h]

  *a5 = 0;
  if ( !a2 )
  {
    v11 = 74;
    goto LABEL_10;
  }
  v9 = *(_QWORD *)(a2 + 8);
  if ( !v9
    || !*(_QWORD *)v9 && *(_DWORD *)(v9 + 8)
    || !*(_DWORD *)(v9 + 8) && *(_QWORD *)v9
    || (v10 = *(_WORD **)(v9 + 16)) == 0
    || !*v10 )
  {
    v11 = 75;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\prifilemanager.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    return 2147942487LL;
  }
  v48 = 0;
  v47 = &v48;
  v17 = -2147024809;
  v49 = 0;
  v50 = 0;
  v52 = 0;
  if ( !*(_QWORD *)v9 && *(_DWORD *)(v9 + 8) || !*(_DWORD *)(v9 + 8) && *(_QWORD *)v9 )
  {
    v18 = 0;
    v19 = -2147024809;
  }
  else
  {
    v18 = *(_QWORD *)(v9 + 16);
    v19 = 0;
  }
  v20 = 0;
  if ( v19 >= 0 )
    v20 = v18;
  if ( a3 )
  {
    v13 = DefStringResult_SetCopy(&v48, a3);
    if ( v13 >= 0 )
      goto LABEL_30;
    v14 = 701;
  }
  else
  {
    v13 = DefStringResult_SetCopy(&v48, v20);
    if ( v13 < 0 )
    {
      v14 = 686;
    }
    else
    {
      if ( v47 && (*v47 || !*((_DWORD *)v47 + 2)) && (*((_DWORD *)v47 + 2) || !*v47) )
      {
        v13 = DefStringResult_EnsureBuffer(v47, 0);
        if ( v13 >= 0 )
        {
          v40 = wcsrchr((const wchar_t *)*v47, 0x5Cu);
          if ( v40 )
            *v40 = 0;
LABEL_30:
          for ( i = 0; ; ++i )
          {
            v22 = *(_QWORD *)(a1 + 16);
            if ( i >= *(_DWORD *)(v22 + 12) )
              break;
            v23 = *(_QWORD *)(*(_QWORD *)v22 + 8LL * i);
            v52 = v23;
            if ( v23 )
            {
              v24 = *(_QWORD *)(a2 + 8);
              if ( v24 && (*(_QWORD *)v24 || !*(_DWORD *)(v24 + 8)) && (*(_DWORD *)(v24 + 8) || !*(_QWORD *)v24) )
              {
                v25 = *(const WCHAR **)(v24 + 16);
                v26 = 0;
              }
              else
              {
                v25 = 0;
                v26 = -2147024809;
              }
              v27 = 0;
              if ( v26 >= 0 )
                v27 = v25;
              if ( CompareStringOrdinal(v27, -1, *(LPCWCH *)(v23 + 48), -1, 1) == 2 )
              {
                if ( v47 && (*v47 || !*((_DWORD *)v47 + 2)) && (*((_DWORD *)v47 + 2) || !*v47) )
                {
                  v35 = (WCHAR *)v47[2];
                  v17 = 0;
                }
                else
                {
                  v35 = 0;
                }
                v36 = 0;
                v37 = (void **)(v23 + 72);
                if ( v17 >= 0 )
                  v36 = v35;
                v38 = CompareStringOrdinal(v36, -1, *(LPCWCH *)(v23 + 72), -1, 1);
                if ( (unsigned int)IntToComparison((unsigned int)(v38 - 2)) )
                {
                  if ( *(_QWORD *)(v23 + 32) )
                  {
                    v13 = -554692559;
                    v42 = 281;
                  }
                  else
                  {
                    v43 = *v37;
                    if ( *v37 )
                    {
                      ProcessHeap = GetProcessHeap();
                      HeapFree(ProcessHeap, 0, v43);
                      *v37 = 0;
                    }
                    if ( !v36 )
                      goto LABEL_65;
                    v13 = DefString_Dup(v36);
                    if ( v13 >= 0 )
                      goto LABEL_65;
                    v42 = 292;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v42,
                    (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\managedfiles.cpp",
                    (const char *)(unsigned int)v13,
                    bIgnoreCasea);
                  v15 = 96;
                  goto LABEL_18;
                }
LABEL_65:
                if ( (a4 & 4) == 0
                  || (v39 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 184LL))(v23), v13 = v39, v39 >= 0) )
                {
                  *a5 = v23;
                  v13 = 0;
                  goto LABEL_20;
                }
                v16 = (unsigned int)v39;
                v15 = 100;
                goto LABEL_19;
              }
            }
          }
          if ( v47 && (*v47 || !*((_DWORD *)v47 + 2)) && (*((_DWORD *)v47 + 2) || !*v47) )
          {
            v28 = v47[2];
            v17 = 0;
          }
          else
          {
            v28 = 0;
          }
          v29 = 0;
          if ( v17 >= 0 )
            v29 = v28;
          bIgnoreCasea = a4;
          Instance = Microsoft::Resources::ManagedFile::CreateInstance(a1, 0xFFFFFFFFLL, a2, v29);
          v13 = Instance;
          if ( Instance >= 0 )
          {
            v31 = *(__int64 **)(a1 + 16);
            v32 = *((_DWORD *)v31 + 3);
            if ( v32 < *((_DWORD *)v31 + 2)
              || (v41 = Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo *>::Extend(
                          *(_QWORD *)(a1 + 16),
                          v32 + 1),
                  v41 >= 0) )
            {
              v33 = *((unsigned int *)v31 + 3);
              v34 = *v31;
              *a5 = v52;
              *(_QWORD *)(v34 + 8 * v33) = v52;
              LODWORD(v33) = *((_DWORD *)v31 + 3);
              *((_DWORD *)v31 + 3) = v33 + 1;
              *(_DWORD *)(v52 + 24) = v33;
              Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v47);
              return 0;
            }
            if ( v52 )
              (**(void (__fastcall ***)(__int64, __int64))v52)(v52, 1);
            v13 = v41;
            goto LABEL_20;
          }
          if ( (unsigned int)(Instance + 2147024894) <= 1 )
            goto LABEL_20;
          v16 = (unsigned int)Instance;
          v15 = 112;
          goto LABEL_19;
        }
      }
      else
      {
        v13 = -2147024809;
      }
      v14 = 690;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\managedfiles.cpp",
    (const char *)(unsigned int)v13,
    bIgnoreCase);
  v15 = 81;
LABEL_18:
  v16 = (unsigned int)v13;
LABEL_19:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\prifilemanager.cpp",
    (const char *)v16,
    bIgnoreCasea);
LABEL_20:
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v47);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180028000  push    rbp
0x180028002  push    rbx
0x180028003  push    rsi
0x180028004  push    rdi
0x180028005  push    r12
0x180028007  push    r13
0x180028009  push    r14
0x18002800b  push    r15
0x18002800d  mov     rbp, rsp
0x180028010  sub     rsp, 58h
0x180028014  mov     r12, [rbp+arg_20]
0x180028018  xor     esi, esi
0x18002801a  mov     r13d, r9d
0x18002801d  mov     r14, rdx
0x180028020  mov     r15, rcx
0x180028023  mov     [r12], rsi
0x180028027  test    rdx, rdx
0x18002802a  jz      loc_180028402
0x180028030  mov     rax, [rdx+8]
0x180028034  test    rax, rax
0x180028037  jz      short loc_18002805F
0x180028039  cmp     [rax], rsi
0x18002803c  jnz     short loc_180028043
0x18002803e  cmp     [rax+8], esi
0x180028041  ja      short loc_18002805F
0x180028043  cmp     [rax+8], esi
0x180028046  jnz     short loc_18002804D
0x180028048  cmp     [rax], rsi
0x18002804b  jnz     short loc_18002805F
0x18002804d  mov     rcx, [rax+10h]
0x180028051  test    rcx, rcx
0x180028054  jz      short loc_18002805F
0x180028056  cmp     [rcx], si
0x180028059  jnz     loc_180028110
0x18002805f  mov     edx, 4Bh ; 'K'; void *
0x180028064  mov     rcx, [rbp+40h]; this
0x180028068  lea     r8, aMinkernelMrtMr_44; "minkernel\\mrt\\mrm\\mrmmin\\prifileman"...
0x18002806f  mov     edi, 80070057h
0x180028074  mov     r9d, edi; char *
0x180028077  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002807c  mov     eax, edi
0x18002807e  jmp     short loc_1800280FF
0x180028080  call    DefStringResult_SetCopy
0x180028085  mov     ebx, eax
0x180028087  test    eax, eax
0x180028089  js      loc_18002839B
0x18002808f  mov     rsi, [rbp+var_28]
0x180028093  xor     ecx, ecx
0x180028095  test    rsi, rsi
0x180028098  jz      loc_180028389
0x18002809e  cmp     [rsi], rcx
0x1800280a1  jz      loc_180028390
0x1800280a7  cmp     [rsi+8], ecx
0x1800280aa  jz      loc_180028380
0x1800280b0  xor     edx, edx
0x1800280b2  mov     rcx, rsi
0x1800280b5  call    _DefStringResult_EnsureBuffer
0x1800280ba  mov     ebx, eax
0x1800280bc  test    eax, eax
0x1800280be  jns     loc_18002834B
0x1800280c4  mov     edx, 2B2h; void *
0x1800280c9  mov     rcx, [rbp+40h]; this
0x1800280cd  lea     r8, aMinkernelMrtMr_46; "minkernel\\mrt\\mrm\\mrmmin\\managedfil"...
0x1800280d4  mov     r9d, ebx; char *
0x1800280d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800280dc  mov     edx, 51h ; 'Q'; void *
0x1800280e1  mov     r9d, ebx; char *
0x1800280e4  mov     rcx, [rbp+40h]; this
0x1800280e8  lea     r8, aMinkernelMrtMr_44; "minkernel\\mrt\\mrm\\mrmmin\\prifileman"...
0x1800280ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800280f4  lea     rcx, [rbp+var_28]; this
0x1800280f8  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x1800280fd  mov     eax, ebx
0x1800280ff  add     rsp, 58h
0x180028103  pop     r15
0x180028105  pop     r14
0x180028107  pop     r13
0x180028109  pop     r12
0x18002810b  pop     rdi
0x18002810c  pop     rsi
0x18002810d  pop     rbx
0x18002810e  pop     rbp
0x18002810f  retn
0x180028110  lea     rcx, [rbp+var_20]
0x180028114  mov     [rbp+var_20], rsi
0x180028118  mov     [rbp+var_28], rcx
0x18002811c  mov     edi, 80070057h
0x180028121  mov     [rbp+var_18], esi
0x180028124  mov     [rbp+var_10], rsi
0x180028128  mov     [rbp+arg_20], rsi
0x18002812c  cmp     [rax], rsi
0x18002812f  jnz     short loc_18002813A
0x180028131  cmp     [rax+8], esi
0x180028134  ja      loc_180028376
0x18002813a  cmp     [rax+8], esi
0x18002813d  jnz     short loc_180028148
0x18002813f  cmp     [rax], rsi
0x180028142  jnz     loc_180028376
0x180028148  mov     rax, [rax+10h]
0x18002814c  mov     ecx, esi
0x18002814e  test    ecx, ecx
0x180028150  mov     rdx, rsi
0x180028153  lea     rcx, [rbp+var_20]
0x180028157  cmovns  rdx, rax
0x18002815b  test    r8, r8
0x18002815e  jz      loc_180028080
0x180028164  mov     rdx, r8
0x180028167  call    DefStringResult_SetCopy
0x18002816c  mov     ebx, eax
0x18002816e  test    eax, eax
0x180028170  js      loc_1800283F8
0x180028176  mov     ebx, esi
0x180028178  mov     rax, [r15+10h]
0x18002817c  cmp     ebx, [rax+0Ch]
0x18002817f  jnb     short loc_1800281FF
0x180028181  mov     rax, [rax]
0x180028184  xor     r8d, r8d
0x180028187  mov     ecx, ebx
0x180028189  mov     rsi, [rax+rcx*8]
0x18002818d  mov     [rbp+arg_20], rsi
0x180028191  test    rsi, rsi
0x180028194  jz      short loc_1800281F8
0x180028196  mov     rcx, [r14+8]
0x18002819a  test    rcx, rcx
0x18002819d  jz      loc_18002836C
0x1800281a3  cmp     [rcx], r8
0x1800281a6  jnz     short loc_1800281B2
0x1800281a8  cmp     [rcx+8], r8d
0x1800281ac  ja      loc_18002836C
0x1800281b2  cmp     [rcx+8], r8d
0x1800281b6  jnz     short loc_1800281C1
0x1800281b8  cmp     [rcx], r8
0x1800281bb  jnz     loc_18002836C
0x1800281c1  mov     rax, [rcx+10h]
0x1800281c5  mov     edx, r8d
0x1800281c8  test    edx, edx
0x1800281ca  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1800281d2  mov     rcx, r8
0x1800281d5  mov     r8, [rsi+30h]; lpString2
0x1800281d9  cmovns  rcx, rax; lpString1
0x1800281dd  or      r9d, 0FFFFFFFFh; cchCount2
0x1800281e1  or      edx, r9d; cchCount1
0x1800281e4  call    cs:__imp_CompareStringOrdinal
0x1800281ea  xor     r8d, r8d
0x1800281ed  lea     ecx, [rax-2]
0x1800281f0  test    ecx, ecx
0x1800281f2  jz      loc_1800282B5
0x1800281f8  inc     ebx
0x1800281fa  jmp     loc_180028178
0x1800281ff  mov     rax, [rbp+var_28]
0x180028203  xor     esi, esi
0x180028205  test    rax, rax
0x180028208  jz      loc_1800283AD
0x18002820e  cmp     [rax], rsi
0x180028211  jnz     short loc_18002821C
0x180028213  cmp     [rax+8], esi
0x180028216  ja      loc_1800283AD
0x18002821c  cmp     [rax+8], esi
0x18002821f  jnz     short loc_18002822A
0x180028221  cmp     [rax], rsi
0x180028224  jnz     loc_1800283AD
0x18002822a  mov     rcx, [rax+10h]
0x18002822e  mov     edi, esi
0x180028230  lea     rax, [rbp+arg_20]
0x180028234  test    edi, edi
0x180028236  mov     [rsp+58h+var_30], rax
0x18002823b  mov     r9, rsi
0x18002823e  cmovns  r9, rcx
0x180028242  mov     [rsp+58h+bIgnoreCase], r13d
0x180028247  or      edx, 0FFFFFFFFh
0x18002824a  mov     rcx, r15
0x18002824d  mov     r8, r14
0x180028250  call    ?CreateInstance@ManagedFile@Resources@Microsoft@@SAJPEBVPriFileManager@23@HPEBVNormalizedFilePath@23@PEBGW4LoadPriFlags@23@PEAPEAV123@@Z; Microsoft::Resources::ManagedFile::CreateInstance(Microsoft::Resources::PriFileManager const *,int,Microsoft::Resources::NormalizedFilePath const *,ushort const *,Microsoft::Resources::LoadPriFlags,Microsoft::Resources::ManagedFile * *)
0x180028255  mov     ebx, eax
0x180028257  test    eax, eax
0x180028259  js      short loc_180028299
0x18002825b  mov     rdi, [r15+10h]
0x18002825f  mov     rbx, [rbp+arg_20]
0x180028263  mov     edx, [rdi+0Ch]
0x180028266  cmp     edx, [rdi+8]
0x180028269  jnb     loc_1800283B5
0x18002826f  mov     ecx, [rdi+0Ch]
0x180028272  mov     rax, [rdi]
0x180028275  mov     [r12], rbx
0x180028279  mov     [rax+rcx*8], rbx
0x18002827d  mov     ecx, [rdi+0Ch]
0x180028280  lea     eax, [rcx+1]
0x180028283  mov     [rdi+0Ch], eax
0x180028286  mov     [rbx+18h], ecx
0x180028289  lea     rcx, [rbp+var_28]; this
0x18002828d  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180028292  xor     eax, eax
0x180028294  jmp     loc_1800280FF
0x180028299  lea     ecx, [rax+7FF8FFFEh]
0x18002829f  cmp     ecx, 1
0x1800282a2  jbe     loc_1800280F4
0x1800282a8  mov     r9d, eax
0x1800282ab  mov     edx, 70h ; 'p'
0x1800282b0  jmp     loc_1800280E4
0x1800282b5  mov     rax, [rbp+var_28]
0x1800282b9  test    rax, rax
0x1800282bc  jz      loc_1800283A5
0x1800282c2  cmp     [rax], r8
0x1800282c5  jnz     short loc_1800282D1
0x1800282c7  cmp     [rax+8], r8d
0x1800282cb  ja      loc_1800283A5
0x1800282d1  cmp     [rax+8], r8d
0x1800282d5  jnz     short loc_1800282E0
0x1800282d7  cmp     [rax], r8
0x1800282da  jnz     loc_1800283A5
0x1800282e0  mov     rcx, [rax+10h]
0x1800282e4  mov     edi, r8d
0x1800282e7  mov     r14, r8
0x1800282ea  mov     [rsp+58h+bIgnoreCase], 1; int
0x1800282f2  test    edi, edi
0x1800282f4  lea     rbx, [rsi+48h]
0x1800282f8  mov     r8, [rbx]; lpString2
0x1800282fb  cmovns  r14, rcx
0x1800282ff  or      edx, 0FFFFFFFFh; cchCount1
0x180028302  mov     r9d, edx; cchCount2
0x180028305  mov     rcx, r14; lpString1
0x180028308  call    cs:__imp_CompareStringOrdinal
0x18002830e  lea     ecx, [rax-2]
0x180028311  call    _IntToComparison
0x180028316  test    eax, eax
0x180028318  jnz     loc_18002840C
0x18002831e  test    r13b, 4
0x180028322  jz      short loc_180028340
0x180028324  mov     rax, [rsi]
0x180028327  mov     rcx, rsi
0x18002832a  mov     rax, [rax+0B8h]
0x180028331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028336  mov     ebx, eax
0x180028338  test    eax, eax
0x18002833a  js      loc_1800283EB
0x180028340  mov     [r12], rsi
0x180028344  xor     ebx, ebx
0x180028346  jmp     loc_1800280F4
0x18002834b  mov     rcx, [rsi]; Str
0x18002834e  mov     edx, 5Ch ; '\'; Ch
0x180028353  call    cs:__imp_wcsrchr
0x180028359  xor     esi, esi
0x18002835b  test    rax, rax
0x18002835e  jz      loc_180028176
0x180028364  mov     [rax], si
0x180028367  jmp     loc_180028176
0x18002836c  mov     rax, r8
0x18002836f  mov     edx, edi
0x180028371  jmp     loc_1800281C8
0x180028376  mov     rax, rsi
0x180028379  mov     ecx, edi
0x18002837b  jmp     loc_18002814E
0x180028380  cmp     [rsi], rcx
0x180028383  jz      loc_1800280B0
0x180028389  mov     ebx, edi
0x18002838b  jmp     loc_1800280C4
0x180028390  cmp     [rsi+8], ecx
0x180028393  jbe     loc_1800280A7
0x180028399  jmp     short loc_180028389
0x18002839b  mov     edx, 2AEh
0x1800283a0  jmp     loc_1800280C9
0x1800283a5  mov     rcx, r8
0x1800283a8  jmp     loc_1800282E7
0x1800283ad  mov     rcx, rsi
0x1800283b0  jmp     loc_180028230
0x1800283b5  inc     edx
0x1800283b7  mov     rcx, rdi
0x1800283ba  call    ?Extend@?$DynamicArray@PEAVUnifiedViewFileInfo@UnifiedResourceView@Resources@Microsoft@@@Resources@Microsoft@@IEAAJI_N@Z; Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo *>::Extend(uint,bool)
0x1800283bf  mov     esi, eax
0x1800283c1  test    eax, eax
0x1800283c3  jns     loc_18002826F
0x1800283c9  test    rbx, rbx
0x1800283cc  jz      loc_1800C166D
0x1800283d2  mov     rcx, [rbx]
0x1800283d5  mov     edx, 1
0x1800283da  mov     rax, [rcx]
0x1800283dd  mov     rcx, rbx
0x1800283e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283e5  nop
0x1800283e6  jmp     loc_1800C166D
0x1800283eb  mov     r9d, eax
0x1800283ee  mov     edx, 64h ; 'd'
0x1800283f3  jmp     loc_1800280E4
0x1800283f8  mov     edx, 2BDh
0x1800283fd  jmp     loc_1800280C9
0x180028402  mov     edx, 4Ah ; 'J'
0x180028407  jmp     loc_180028064
0x18002840c  cmp     qword ptr [rsi+20h], 0
0x180028411  jz      loc_1800C160A
0x180028417  mov     ebx, 0DEF01031h
0x18002841c  mov     edx, 119h
0x180028421  jmp     loc_1800C1650
0x1800c160a  mov     rdi, [rbx]
0x1800c160d  test    rdi, rdi
0x1800c1610  jz      short loc_1800C162D
0x1800c1612  call    cs:__imp_GetProcessHeap
0x1800c1618  mov     r8, rdi; lpMem
0x1800c161b  xor     edx, edx; dwFlags
0x1800c161d  mov     rcx, rax; hHeap
0x1800c1620  call    cs:__imp_HeapFree
  ... truncated ...
```
