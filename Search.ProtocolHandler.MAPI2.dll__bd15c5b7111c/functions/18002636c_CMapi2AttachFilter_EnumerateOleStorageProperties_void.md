# CMapi2AttachFilter::EnumerateOleStorageProperties(void)

- ea: `0x18002636c`
- end: `0x1800268b8`
- name: `?EnumerateOleStorageProperties@CMapi2AttachFilter@@AEAAJXZ`
- size: `1356`
- prototype: `__int64 __fastcall(CMapi2AttachFilter *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002781c`

## callees

- `0x180002300`
- `0x180002780`
- `0x18000306c`
- `0x18000da40`
- `0x18000e328`
- `0x18000ea18`
- `0x180025e58`
- `0x180025e74`
- `0x180025fa0`
- `0x18002636c`
- `0x1800268f4`
- `0x18002812c`
- `0x18002b184`
- `0x18002b428`
- `0x18002b784`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800265aa`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800265aa`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x180026400`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x180026400`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800265a2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800265fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026750`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800265a2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800265fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002676d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002676d`

## string_xrefs

- `0x1800267b9`: `onecoreuap\base\appmodel\Search\common\include\tpslist.hxx`

## pseudocode

```c
__int64 __fastcall CMapi2AttachFilter::EnumerateOleStorageProperties(CMapi2AttachFilter *this)
{
  __int64 v2; // rbx
  HRESULT v4; // ebx
  int v5; // r14d
  int v6; // r8d
  FMTID v7; // xmm0
  int v8; // eax
  unsigned int uiVal; // esi
  int v10; // edi
  unsigned int v11; // r8d
  struct tagPROPVARIANT *v12; // rdx
  CValChunk *v13; // rax
  CValChunk *v14; // rbx
  _QWORD *v15; // rax
  HRESULT v16; // eax
  DWORD reserved; // [rsp+20h] [rbp-E0h]
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  IStorage *ppstgOpen; // [rsp+50h] [rbp-B0h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h] BYREF
  ILockBytes plkbyt; // [rsp+78h] [rbp-88h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h]
  CValChunk *v27; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v28[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v29; // [rsp+A0h] [rbp-60h] BYREF
  CValChunk *v30; // [rsp+B0h] [rbp-50h]
  _QWORD *v31; // [rsp+B8h] [rbp-48h]
  tagSTAT_CHUNK v32; // [rsp+C0h] [rbp-40h] BYREF
  GUID v33; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v34[4]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v2 = *((_QWORD *)this + 4);
  if ( !v2 )
    return 2147500035LL;
  CNoLockStream::CNoLockStream((CNoLockStream *)&plkbyt);
  CNoLockStream::Free((CNoLockStream *)&plkbyt);
  v26 = v2;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  ppstgOpen = 0;
  v19 = 0;
  v21 = 0;
  v4 = StgOpenStorageOnILockBytes(&plkbyt, 0, 0x20u, 0, 0, &ppstgOpen);
  if ( v4 >= 0 )
  {
    if ( !ppstgOpen
      || (v4 = ((__int64 (__fastcall *)(IStorage *, GUID *, __int64 *))ppstgOpen->lpVtbl->QueryInterface)(
                 ppstgOpen,
                 &IID_IPropertySetStorage,
                 &v19),
          v4 >= 0) )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 48LL))(v19, &v21);
      if ( v4 >= 0 )
      {
        memset_0(v34, 0, sizeof(v34));
        v5 = 0;
        v33 = GUID_NULL;
        while ( 1 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64, __int64, _OWORD *, _QWORD))(*(_QWORD *)v21 + 24LL))(v21, 1, v34, 0);
          if ( v6 )
          {
            if ( v5 )
              goto LABEL_47;
            v7 = FMTID_UserDefinedProperties;
            v5 = 1;
          }
          else
          {
            if ( (unsigned int)InlineIsEqualGUID(&v33, v34, 0) )
            {
LABEL_47:
              v16 = 0;
              if ( v6 < 0 )
                v16 = v6;
              v4 = 0;
              if ( v16 != -2147467263 )
                v4 = v16;
              TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v21);
              TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v19);
              TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&ppstgOpen);
              plkbyt.lpVtbl = (struct ILockBytesVtbl *)&CNoLockStream::`vftable';
              CNoLockStream::Free((CNoLockStream *)&plkbyt);
              return (unsigned int)v4;
            }
            v7 = (FMTID)v34[0];
          }
          v33 = v7;
          v18 = 0;
          v8 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, __int64 *))(*(_QWORD *)v19 + 32LL))(
                 v19,
                 &v33,
                 16,
                 &v18);
          v24 = 0;
          if ( v8 >= 0 && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 88LL))(v18, &v24) >= 0 )
          {
            v29 = 0;
            v20 = 0;
            memset(&pvar, 0, sizeof(pvar));
            memset_0(&v32, 0, sizeof(v32));
            v32.breakType = CHUNK_EOS;
            v32.flags = CHUNK_VALUE;
            v32.attribute.guidPropSet = v33;
            v32.attribute.psProperty.ulKind = 1;
            LODWORD(v32.attribute.psProperty.propid) = 0x80000000;
            if ( (*(int (__fastcall **)(__int64, __int64, PROPSPEC *, struct tagPROPVARIANT *))(*(_QWORD *)v18 + 24LL))(
                   v18,
                   1,
                   &v32.attribute.psProperty,
                   &pvar) >= 0
              && pvar.vt )
            {
              v32.locale = pvar.ulVal;
              PropVariantClear((PROPVARIANT *)&pvar);
            }
            else
            {
              v32.locale = GetSystemDefaultLCID();
            }
            v28[0] = 1;
            v28[1] = 1;
            uiVal = 0;
            v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, struct tagPROPVARIANT *))(*(_QWORD *)v18 + 24LL))(
                    v18,
                    1,
                    v28,
                    &pvar);
            if ( v10 >= 0 )
            {
              if ( pvar.vt == 2 )
                uiVal = pvar.uiVal;
              PropVariantClear((PROPVARIANT *)&pvar);
            }
            while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int128 *, int *))(*(_QWORD *)v24 + 24LL))(
                       v24,
                       1,
                       &v29,
                       &v20)
                 && v20 == 1
                 && v10 >= 0 )
            {
              if ( (_QWORD)v29 )
              {
                v32.attribute.psProperty.ulKind = 0;
                v32.attribute.psProperty.propid = (PROPID)v29;
              }
              else
              {
                v32.attribute.psProperty.ulKind = 1;
                LODWORD(v32.attribute.psProperty.propid) = DWORD2(v29);
              }
              if ( (*(int (__fastcall **)(__int64, __int64, PROPSPEC *, struct tagPROPVARIANT *))(*(_QWORD *)v18 + 24LL))(
                     v18,
                     1,
                     &v32.attribute.psProperty,
                     &pvar) >= 0 )
              {
                if ( (unsigned int)ShouldNotIgnoreProperty(&pvar, &v32.attribute) )
                {
                  v10 = PropvarCvt::PropVariantConvertStrToWStr(
                          (PropvarCvt *)&pvar,
                          (struct tagPROPVARIANT *)uiVal,
                          v11);
                  if ( v10 >= 0 )
                  {
                    if ( pvar.vt != 3
                      || (v10 = PropvarCvt::ConvertIntBoolPropvariantToI8((PropvarCvt *)&pvar, v12), v10 >= 0) )
                    {
                      v13 = (CValChunk *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
                      v30 = v13;
                      if ( v13 )
                        v14 = CValChunk::CValChunk(v13, &v32, &pvar);
                      else
                        v14 = 0;
                      v27 = v14;
                      if ( v14 )
                      {
                        v15 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
                        v31 = v15;
                        if ( !v15 )
                          wil::details::in1diag3::Throw_Hr(
                            retaddr,
                            (void *)0x13D,
                            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\tpslist.hxx",
                            (const char *)0x8007000ELL,
                            reserved);
                        *v15 = 0;
                        v15[1] = 0;
                        v15[1] = v14;
                        CLnkList::InsertAfter(
                          (CMapi2AttachFilter *)((char *)this + 17024),
                          *((struct CSingleLink **)this + 2130),
                          (struct CSingleLink *)v15);
                        v27 = 0;
                      }
                      TPointer<CValChunk>::~TPointer<CValChunk>(&v27);
                    }
                  }
                }
                PropVariantClear((PROPVARIANT *)&pvar);
              }
              if ( !v32.attribute.psProperty.ulKind )
              {
                if ( v32.attribute.psProperty.propid )
                  CoTaskMemFree(v32.attribute.psProperty.propid);
              }
            }
          }
          TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v24);
          TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v18);
        }
      }
    }
  }
  if ( ((v4 + 2147467263) & 0xFFFFFFFB) != 0 )
  {
    TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v21);
    TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v19);
    TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&ppstgOpen);
    plkbyt.lpVtbl = (struct ILockBytesVtbl *)&CNoLockStream::`vftable';
    CNoLockStream::Free((CNoLockStream *)&plkbyt);
    return (unsigned int)v4;
  }
  TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v21);
  TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v19);
  TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&ppstgOpen);
  plkbyt.lpVtbl = (struct ILockBytesVtbl *)&CNoLockStream::`vftable';
  CNoLockStream::Free((CNoLockStream *)&plkbyt);
  return 0;
}

```

## disassembly

```asm
0x18002636c  push    rbp
0x18002636e  push    rbx
0x18002636f  push    rsi
0x180026370  push    rdi
0x180026371  push    r12
0x180026373  push    r13
0x180026375  push    r14
0x180026377  push    r15
0x180026379  lea     rbp, [rsp-68h]
0x18002637e  sub     rsp, 168h
0x180026385  mov     rax, cs:__security_cookie
0x18002638c  xor     rax, rsp
0x18002638f  mov     [rbp+0A0h+var_50], rax
0x180026393  mov     r15, rcx
0x180026396  mov     rbx, [rcx+20h]
0x18002639a  xor     r12d, r12d
0x18002639d  test    rbx, rbx
0x1800263a0  jnz     short loc_1800263AC
0x1800263a2  mov     eax, 80004003h
0x1800263a7  jmp     loc_180026898
0x1800263ac  lea     rcx, [rsp+1A0h+plkbyt]; this
0x1800263b1  call    ??0CNoLockStream@@QEAA@XZ; CNoLockStream::CNoLockStream(void)
0x1800263b6  nop
0x1800263b7  lea     rcx, [rsp+1A0h+plkbyt]; this
0x1800263bc  call    ?Free@CNoLockStream@@QEAAXXZ; CNoLockStream::Free(void)
0x1800263c1  mov     [rbp+0A0h+var_120], rbx
0x1800263c5  mov     rax, [rbx]
0x1800263c8  mov     rcx, rbx
0x1800263cb  mov     rax, [rax+8]
0x1800263cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263d4  mov     [rsp+1A0h+var_150], r12
0x1800263d9  mov     [rsp+1A0h+var_168], r12
0x1800263de  mov     [rsp+1A0h+var_158], r12
0x1800263e3  lea     rax, [rsp+1A0h+var_150]
0x1800263e8  mov     [rsp+1A0h+ppstgOpen], rax; ppstgOpen
0x1800263ed  mov     [rsp+1A0h+reserved], r12d; int
0x1800263f2  xor     r9d, r9d; snbExclude
0x1800263f5  xor     edx, edx; pstgPriority
0x1800263f7  lea     r8d, [r9+20h]; grfMode
0x1800263fb  lea     rcx, [rsp+1A0h+plkbyt]; plkbyt
0x180026400  call    cs:__imp_StgOpenStorageOnILockBytes
0x180026406  mov     ebx, eax
0x180026408  test    eax, eax
0x18002640a  js      loc_18002681A
0x180026410  mov     rcx, [rsp+1A0h+var_150]
0x180026415  test    rcx, rcx
0x180026418  jz      short loc_18002643B
0x18002641a  mov     rax, [rcx]
0x18002641d  lea     r8, [rsp+1A0h+var_168]
0x180026422  lea     rdx, IID_IPropertySetStorage
0x180026429  mov     rax, [rax]
0x18002642c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026431  mov     ebx, eax
0x180026433  test    eax, eax
0x180026435  js      loc_18002681A
0x18002643b  mov     rcx, [rsp+1A0h+var_168]
0x180026440  mov     rax, [rcx]
0x180026443  lea     rdx, [rsp+1A0h+var_158]
0x180026448  mov     rax, [rax+30h]
0x18002644c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026451  mov     ebx, eax
0x180026453  test    eax, eax
0x180026455  js      loc_18002681A
0x18002645b  xor     edx, edx; Val
0x18002645d  lea     r8d, [rdx+40h]; Size
0x180026461  lea     rcx, [rbp+0A0h+var_90]; void *
0x180026465  call    memset_0
0x18002646a  mov     r14d, r12d
0x18002646d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180026474  movdqu  [rbp+0A0h+var_A0], xmm0
0x180026479  mov     r13d, 1
0x18002647f  mov     ebx, 2
0x180026484  mov     rcx, [rsp+1A0h+var_158]
0x180026489  mov     rax, [rcx]
0x18002648c  xor     r9d, r9d
0x18002648f  lea     r8, [rbp+0A0h+var_90]
0x180026493  mov     edx, r13d
0x180026496  mov     rax, [rax+18h]
0x18002649a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002649f  mov     r8d, eax
0x1800264a2  test    eax, eax
0x1800264a4  jz      short loc_1800264BB
0x1800264a6  test    r14d, r14d
0x1800264a9  jnz     loc_1800267CB
0x1800264af  movups  xmm0, xmmword ptr cs:FMTID_UserDefinedProperties.Data1
0x1800264b6  mov     r14d, r13d
0x1800264b9  jmp     short loc_1800264D4
0x1800264bb  lea     rdx, [rbp+0A0h+var_90]
0x1800264bf  lea     rcx, [rbp+0A0h+var_A0]
0x1800264c3  call    InlineIsEqualGUID
0x1800264c8  test    eax, eax
0x1800264ca  jnz     loc_1800267CB
0x1800264d0  movaps  xmm0, [rbp+0A0h+var_90]
0x1800264d4  movdqu  [rbp+0A0h+var_A0], xmm0
0x1800264d9  mov     [rsp+1A0h+var_170], r12
0x1800264de  mov     rcx, [rsp+1A0h+var_168]
0x1800264e3  mov     rax, [rcx]
0x1800264e6  lea     r9, [rsp+1A0h+var_170]
0x1800264eb  mov     r8d, 10h
0x1800264f1  lea     rdx, [rbp+0A0h+var_A0]
0x1800264f5  mov     rax, [rax+20h]
0x1800264f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264fe  mov     [rsp+1A0h+var_130], r12
0x180026503  test    eax, eax
0x180026505  js      loc_180026792
0x18002650b  mov     rcx, [rsp+1A0h+var_170]
0x180026510  mov     rax, [rcx]
0x180026513  lea     rdx, [rsp+1A0h+var_130]
0x180026518  mov     rax, [rax+58h]
0x18002651c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026521  test    eax, eax
0x180026523  js      loc_180026792
0x180026529  xorps   xmm0, xmm0
0x18002652c  movups  [rbp+0A0h+var_100], xmm0
0x180026530  mov     [rsp+1A0h+var_160], r12d
0x180026535  xorps   xmm1, xmm1
0x180026538  xor     eax, eax
0x18002653a  movups  xmmword ptr [rsp+1A0h+pvar], xmm1
0x18002653f  mov     [rsp+1A0h+var_138], rax
0x180026544  xor     edx, edx; Val
0x180026546  lea     r8d, [rax+40h]; Size
0x18002654a  lea     rcx, [rbp+0A0h+var_E0]; void *
0x18002654e  call    memset_0
0x180026553  mov     [rbp+0A0h+var_E0.breakType], ebx
0x180026556  mov     [rbp+0A0h+var_E0.flags], ebx
0x180026559  movups  xmm0, [rbp+0A0h+var_A0]
0x18002655d  movdqu  xmmword ptr [rbp+0A0h+var_E0.attribute.guidPropSet.Data1], xmm0
0x180026562  mov     [rbp+0A0h+var_E0.attribute.psProperty.ulKind], r13d
0x180026566  mov     dword ptr [rbp+0A0h+var_E0.attribute.psProperty.8], 80000000h
0x18002656d  mov     rcx, [rsp+1A0h+var_170]
0x180026572  mov     rax, [rcx]
0x180026575  lea     r9, [rsp+1A0h+pvar]
0x18002657a  lea     r8, [rbp+0A0h+var_E0.attribute.psProperty]
0x18002657e  mov     edx, r13d
0x180026581  mov     rax, [rax+18h]
0x180026585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002658a  test    eax, eax
0x18002658c  js      short loc_1800265AA
0x18002658e  cmp     word ptr [rsp+1A0h+pvar], r12w
0x180026594  jz      short loc_1800265AA
0x180026596  mov     eax, dword ptr [rsp+1A0h+pvar+8]
0x18002659a  mov     [rbp+0A0h+var_E0.locale], eax
0x18002659d  lea     rcx, [rsp+1A0h+pvar]; pvar
0x1800265a2  call    cs:__imp_PropVariantClear
0x1800265a8  jmp     short loc_1800265B3
0x1800265aa  call    cs:__imp_GetSystemDefaultLCID
0x1800265b0  mov     [rbp+0A0h+var_E0.locale], eax
0x1800265b3  mov     [rbp+0A0h+var_110], 1
0x1800265bb  mov     [rbp+0A0h+var_108], 1
0x1800265c3  mov     esi, r12d
0x1800265c6  mov     rcx, [rsp+1A0h+var_170]
0x1800265cb  mov     rax, [rcx]
0x1800265ce  lea     r9, [rsp+1A0h+pvar]
0x1800265d3  lea     r8, [rbp+0A0h+var_110]
0x1800265d7  mov     edx, r13d
0x1800265da  mov     rax, [rax+18h]
0x1800265de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265e3  mov     edi, eax
0x1800265e5  test    eax, eax
0x1800265e7  js      short loc_180026600
0x1800265e9  cmp     bx, word ptr [rsp+1A0h+pvar]
0x1800265ee  jnz     short loc_1800265F5
0x1800265f0  movzx   esi, word ptr [rsp+1A0h+pvar+8]
0x1800265f5  lea     rcx, [rsp+1A0h+pvar]; pvar
0x1800265fa  call    cs:__imp_PropVariantClear
0x180026600  mov     rcx, [rsp+1A0h+var_130]
0x180026605  mov     rax, [rcx]
0x180026608  lea     r9, [rsp+1A0h+var_160]
0x18002660d  lea     r8, [rbp+0A0h+var_100]
0x180026611  mov     edx, r13d
0x180026614  mov     rax, [rax+18h]
0x180026618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002661d  test    eax, eax
0x18002661f  jnz     loc_180026778
0x180026625  cmp     [rsp+1A0h+var_160], r13d
0x18002662a  jnz     loc_180026778
0x180026630  test    edi, edi
0x180026632  js      loc_180026778
0x180026638  mov     rax, qword ptr [rbp+0A0h+var_100]
0x18002663c  test    rax, rax
0x18002663f  jz      short loc_18002664B
0x180026641  mov     [rbp+0A0h+var_E0.attribute.psProperty.ulKind], r12d
0x180026645  mov     qword ptr [rbp+0A0h+var_E0.attribute.psProperty.8], rax
0x180026649  jmp     short loc_180026655
0x18002664b  mov     [rbp+0A0h+var_E0.attribute.psProperty.ulKind], r13d
0x18002664f  mov     eax, dword ptr [rbp+0A0h+var_100+8]
0x180026652  mov     dword ptr [rbp+0A0h+var_E0.attribute.psProperty.8], eax
0x180026655  mov     rcx, [rsp+1A0h+var_170]
0x18002665a  mov     rax, [rcx]
0x18002665d  lea     r9, [rsp+1A0h+pvar]
0x180026662  lea     r8, [rbp+0A0h+var_E0.attribute.psProperty]
0x180026666  mov     edx, r13d
0x180026669  mov     rax, [rax+18h]
0x18002666d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026672  test    eax, eax
0x180026674  js      loc_180026756
0x18002667a  lea     rdx, [rbp+0A0h+var_E0.attribute]
0x18002667e  lea     rcx, [rsp+1A0h+pvar]
0x180026683  call    ShouldNotIgnoreProperty
0x180026688  test    eax, eax
0x18002668a  jz      loc_18002674B
0x180026690  mov     edx, esi; struct tagPROPVARIANT *
0x180026692  lea     rcx, [rsp+1A0h+pvar]; this
0x180026697  call    ?PropVariantConvertStrToWStr@PropvarCvt@@YAJPEAUtagPROPVARIANT@@I@Z; PropvarCvt::PropVariantConvertStrToWStr(tagPROPVARIANT *,uint)
0x18002669c  mov     edi, eax
0x18002669e  test    eax, eax
0x1800266a0  js      loc_18002674B
0x1800266a6  mov     eax, 3
0x1800266ab  cmp     ax, word ptr [rsp+1A0h+pvar]
0x1800266b0  jnz     short loc_1800266C6
0x1800266b2  lea     rcx, [rsp+1A0h+pvar]; this
0x1800266b7  call    ?ConvertIntBoolPropvariantToI8@PropvarCvt@@YAJPEAUtagPROPVARIANT@@@Z; PropvarCvt::ConvertIntBoolPropvariantToI8(tagPROPVARIANT *)
0x1800266bc  mov     edi, eax
0x1800266be  test    eax, eax
0x1800266c0  js      loc_18002674B
0x1800266c6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800266cd  mov     ecx, 50h ; 'P'; unsigned __int64
0x1800266d2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800266d7  mov     [rbp+0A0h+var_F0], rax
0x1800266db  test    rax, rax
0x1800266de  jz      short loc_1800266F6
0x1800266e0  lea     r8, [rsp+1A0h+pvar]; struct tagPROPVARIANT *
0x1800266e5  lea     rdx, [rbp+0A0h+var_E0]; struct tagSTAT_CHUNK *
0x1800266e9  mov     rcx, rax; this
0x1800266ec  call    ??0CValChunk@@QEAA@PEAUtagSTAT_CHUNK@@PEAUtagPROPVARIANT@@@Z; CValChunk::CValChunk(tagSTAT_CHUNK *,tagPROPVARIANT *)
0x1800266f1  mov     rbx, rax
0x1800266f4  jmp     short loc_1800266F9
0x1800266f6  mov     rbx, r12
0x1800266f9  mov     [rbp+0A0h+var_118], rbx
0x1800266fd  test    rbx, rbx
0x180026700  jz      short loc_180026742
0x180026702  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026709  mov     ecx, 10h; unsigned __int64
0x18002670e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026713  mov     [rbp+0A0h+var_E8], rax
0x180026717  test    rax, rax
0x18002671a  jz      loc_1800267AC
0x180026720  mov     [rax], r12
0x180026723  mov     [rax+8], r12
0x180026727  lea     rcx, [r15+4280h]; this
0x18002672e  mov     [rax+8], rbx
0x180026732  mov     r8, rax; struct CSingleLink *
0x180026735  mov     rdx, [rcx+10h]; struct CSingleLink *
0x180026739  call    ?InsertAfter@CLnkList@@IEAAXPEAVCSingleLink@@0@Z; CLnkList::InsertAfter(CSingleLink *,CSingleLink *)
0x18002673e  mov     [rbp+0A0h+var_118], r12
0x180026742  lea     rcx, [rbp+0A0h+var_118]
0x180026746  call    ??1?$TPointer@VCValChunk@@@@QEAA@XZ; TPointer<CValChunk>::~TPointer<CValChunk>(void)
0x18002674b  lea     rcx, [rsp+1A0h+pvar]; pvar
0x180026750  call    cs:__imp_PropVariantClear
0x180026756  cmp     [rbp+0A0h+var_E0.attribute.psProperty.ulKind], r12d
0x18002675a  jnz     loc_180026600
0x180026760  mov     rcx, qword ptr [rbp+0A0h+var_E0.attribute.psProperty.8]; pv
0x180026764  test    rcx, rcx
0x180026767  jz      loc_180026600
0x18002676d  call    cs:__imp_CoTaskMemFree
0x180026773  jmp     loc_180026600
0x180026778  lea     rcx, [rsp+1A0h+var_130]
0x18002677d  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x180026782  nop
0x180026783  lea     rcx, [rsp+1A0h+var_170]
0x180026788  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x18002678d  jmp     loc_18002647F
0x180026792  lea     rcx, [rsp+1A0h+var_130]
0x180026797  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x18002679c  nop
0x18002679d  lea     rcx, [rsp+1A0h+var_170]
0x1800267a2  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x1800267a7  jmp     loc_180026484
0x1800267ac  mov     rcx, [rbp+0A8h]; this
0x1800267b3  mov     r9d, 8007000Eh; char *
0x1800267b9  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800267c0  mov     edx, 13Dh; void *
0x1800267c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800267cb  mov     eax, r12d
0x1800267ce  test    r8d, r8d
0x1800267d1  cmovs   eax, r8d
0x1800267d5  mov     ebx, r12d
0x1800267d8  cmp     eax, 80004001h
0x1800267dd  cmovnz  ebx, eax
0x1800267e0  lea     rcx, [rsp+1A0h+var_158]
0x1800267e5  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x1800267ea  nop
0x1800267eb  lea     rcx, [rsp+1A0h+var_168]
0x1800267f0  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x1800267f5  nop
0x1800267f6  lea     rcx, [rsp+1A0h+var_150]
0x1800267fb  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x180026800  nop
0x180026801  lea     rax, ??_7CNoLockStream@@6B@; const CNoLockStream::`vftable'
0x180026808  mov     [rsp+1A0h+plkbyt.lpVtbl], rax
0x18002680d  lea     rcx, [rsp+1A0h+plkbyt]; this
0x180026812  call    ?Free@CNoLockStream@@QEAAXXZ; CNoLockStream::Free(void)
0x180026817  nop
0x180026818  jmp     short loc_18002685F
0x18002681a  lea     eax, [rbx+7FFFBFFFh]
0x180026820  lea     rcx, [rsp+1A0h+var_158]
0x180026825  test    eax, 0FFFFFFFBh
0x18002682a  jz      short loc_180026863
0x18002682c  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x180026831  nop
  ... truncated ...
```
