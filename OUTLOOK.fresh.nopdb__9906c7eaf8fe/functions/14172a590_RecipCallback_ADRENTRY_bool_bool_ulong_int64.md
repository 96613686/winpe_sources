# RecipCallback(_ADRENTRY *,bool *,bool *,ulong,__int64)

- ea: `0x14172a590`
- end: `0x14172af12`
- name: `?RecipCallback@@YAJPEAU_ADRENTRY@@PEA_N1K_J@Z`
- size: `2434`
- prototype: `__int64 __fastcall(struct _ADRENTRY *, bool *, bool *, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task`

## callees

- `0x1400d3df0`
- `0x1400d3e20`
- `0x1400d4d1c`
- `0x1400dd680`
- `0x1400dd710`
- `0x1401868a8`
- `0x1402d3894`
- `0x140503f00`
- `0x140504770`
- `0x14062f110`
- `0x14063fe88`
- `0x14069b5dc`
- `0x1407e99f0`
- `0x140b65944`
- `0x14144ea9c`
- `0x14172a590`

## import_xrefs

- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172a72e`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172a801`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172a926`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172abd6`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172ae30`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172ae9c`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172a72e`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172a801`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172a926`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172abd6`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172ae30`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172ae9c`
- `ole32!CoTaskMemFree` at `0x14172a6af`
- `ole32!CoTaskMemFree` at `0x14172a6b7`
- `ole32!CoTaskMemFree` at `0x14172a6bf`
- `ole32!CoTaskMemFree` at `0x14172a6c7`
- `ole32!CoTaskMemFree` at `0x14172a6d2`
- `ole32!CoTaskMemFree` at `0x14172a786`
- `ole32!CoTaskMemFree` at `0x14172a78e`
- `ole32!CoTaskMemFree` at `0x14172a796`
- `ole32!CoTaskMemFree` at `0x14172a79e`
- `ole32!CoTaskMemFree` at `0x14172a7a6`
- `ole32!CoTaskMemFree` at `0x14172a8b0`
- `ole32!CoTaskMemFree` at `0x14172a8b8`
- `ole32!CoTaskMemFree` at `0x14172a8c0`
- `ole32!CoTaskMemFree` at `0x14172a8c8`
- `ole32!CoTaskMemFree` at `0x14172a8d0`
- `ole32!CoTaskMemFree` at `0x14172ae3a`
- `ole32!CoTaskMemFree` at `0x14172ae43`
- `ole32!CoTaskMemFree` at `0x14172ae4c`
- `ole32!CoTaskMemFree` at `0x14172ae55`
- `ole32!CoTaskMemFree` at `0x14172ae5e`
- `ole32!CoTaskMemFree` at `0x14172a6af`
- `ole32!CoTaskMemFree` at `0x14172a6b7`
- `ole32!CoTaskMemFree` at `0x14172a6bf`
- `ole32!CoTaskMemFree` at `0x14172a6c7`
- `ole32!CoTaskMemFree` at `0x14172a6d2`
- `ole32!CoTaskMemFree` at `0x14172a786`
- `ole32!CoTaskMemFree` at `0x14172a78e`
- `ole32!CoTaskMemFree` at `0x14172a796`
- `ole32!CoTaskMemFree` at `0x14172a79e`
- `ole32!CoTaskMemFree` at `0x14172a7a6`
- `ole32!CoTaskMemFree` at `0x14172a8b0`
- `ole32!CoTaskMemFree` at `0x14172a8b8`
- `ole32!CoTaskMemFree` at `0x14172a8c0`
- `ole32!CoTaskMemFree` at `0x14172a8c8`
- `ole32!CoTaskMemFree` at `0x14172a8d0`
- `ole32!CoTaskMemFree` at `0x14172ae3a`
- `ole32!CoTaskMemFree` at `0x14172ae43`
- `ole32!CoTaskMemFree` at `0x14172ae4c`
- `ole32!CoTaskMemFree` at `0x14172ae55`
- `ole32!CoTaskMemFree` at `0x14172ae5e`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x14172ab53`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x14172ac84`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x14172ab53`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x14172ac84`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x14172a691`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x14172a691`
- `Mso98Win32Client!__imp_?HrSetProps@@YAJPEAUIMAPIProp@@KPEAU_SPropValue@@PEAPEAU_SPropProblemArray@@PEAJ@Z` at `0x14172ad41`
- `Mso98Win32Client!__imp_?HrSetProps@@YAJPEAUIMAPIProp@@KPEAU_SPropValue@@PEAPEAU_SPropProblemArray@@PEAJ@Z` at `0x14172ad41`

## pseudocode

```c
__int64 __fastcall RecipCallback(const struct _SRow *a1, bool *a2, bool *a3, LONG a4, __int64 a5)
{
  struct IMAPIProp *v6; // rbx
  void *v7; // rdi
  void *v8; // rsi
  void *v9; // r14
  void *v10; // r15
  void *v11; // r12
  unsigned int v12; // r8d
  unsigned int v13; // r13d
  struct IMessage *v14; // rcx
  unsigned int (__fastcall *Release)(MAPIValRef *__hidden); // rdx
  __int64 v16; // rcx
  struct IMessage *v17; // rcx
  unsigned int (__fastcall *v18)(MAPIValRef *__hidden); // rdx
  __int64 *v20; // rcx
  __int64 v21; // rax
  struct IMessage *v22; // rcx
  unsigned int (__fastcall *v23)(MAPIValRef *__hidden); // rdx
  _QWORD *v24; // rbx
  int DefaultStoreSpecialFolderFromSession; // eax
  unsigned int v26; // eax
  struct _SPropTagArray *v27; // r8
  int v28; // eax
  struct _SPropValue *v29; // rax
  LONG i; // eax
  struct IMAPISession *v31; // rdx
  int v32; // eax
  int Props; // eax
  unsigned int (__fastcall *v34)(MAPIValRef *__hidden); // rdx
  int v35; // eax
  int v36; // eax
  int v37; // eax
  unsigned int v38; // eax
  struct IMessage *v39; // rcx
  unsigned int (__fastcall *v40)(MAPIValRef *__hidden); // rdx
  struct IMessage *v41; // rcx
  void (*v42)(void); // rax
  ULONG (__stdcall *v43)(IMAPIProp *); // rax
  struct IMAPIFolder **v44; // [rsp+20h] [rbp-248h]
  struct IMAPIFolder **v45; // [rsp+20h] [rbp-248h]
  __int64 v46; // [rsp+28h] [rbp-240h]
  struct IMessage *v47; // [rsp+40h] [rbp-228h] BYREF
  LONG v48; // [rsp+48h] [rbp-220h]
  LPVOID pv; // [rsp+50h] [rbp-218h] BYREF
  unsigned int v50; // [rsp+58h] [rbp-210h]
  __int64 v51; // [rsp+60h] [rbp-208h]
  struct IMAPIProp *v52; // [rsp+68h] [rbp-200h] BYREF
  struct _SPropValue *v53; // [rsp+70h] [rbp-1F8h]
  bool *v54; // [rsp+78h] [rbp-1F0h]
  bool *v55; // [rsp+80h] [rbp-1E8h]
  char *v56; // [rsp+88h] [rbp-1E0h]
  void *v57; // [rsp+90h] [rbp-1D8h]
  void *v58; // [rsp+98h] [rbp-1D0h]
  void *v59; // [rsp+A0h] [rbp-1C8h]
  void *v60; // [rsp+A8h] [rbp-1C0h]
  MAPIRowRef *v61; // [rsp+B0h] [rbp-1B8h]
  struct _SBinary *p_Value; // [rsp+B8h] [rbp-1B0h]
  __int128 v63; // [rsp+C0h] [rbp-1A8h]
  __int128 v64; // [rsp+D0h] [rbp-198h]
  _BYTE v65[4]; // [rsp+E0h] [rbp-188h] BYREF
  LONG v66; // [rsp+E4h] [rbp-184h]
  void *v67; // [rsp+E8h] [rbp-180h]
  char *v68; // [rsp+F0h] [rbp-178h]
  void *v69; // [rsp+F8h] [rbp-170h]
  void *v70; // [rsp+100h] [rbp-168h]
  int v71; // [rsp+108h] [rbp-160h]
  int v72; // [rsp+110h] [rbp-158h]
  void *v73; // [rsp+120h] [rbp-148h]
  char v74[24]; // [rsp+138h] [rbp-130h] BYREF
  _OWORD v75[2]; // [rsp+150h] [rbp-118h] BYREF
  struct _ADRLIST v76; // [rsp+170h] [rbp-F8h] BYREF
  __m256i v77; // [rsp+190h] [rbp-D8h] BYREF
  union _PV v78; // [rsp+1B0h] [rbp-B8h]
  __int128 v79; // [rsp+1C0h] [rbp-A8h]
  union _PV v80; // [rsp+1D0h] [rbp-98h]
  union _PV v81; // [rsp+1E0h] [rbp-88h]
  int v82; // [rsp+1F0h] [rbp-78h]
  __int128 v83; // [rsp+1F8h] [rbp-70h]
  int v84; // [rsp+208h] [rbp-60h]
  __int64 v85; // [rsp+210h] [rbp-58h]

  v48 = a4;
  v55 = a3;
  v54 = a2;
  v51 = a5;
  v6 = 0;
  v52 = 0;
  pv = 0;
  v47 = 0;
  v7 = 0;
  v56 = 0;
  v8 = 0;
  v57 = 0;
  v9 = 0;
  v58 = 0;
  v10 = 0;
  v59 = 0;
  v11 = 0;
  v60 = 0;
  DWORD1(v63) = 0;
  *(_QWORD *)((char *)&v64 + 4) = 0;
  HIDWORD(v64) = 0;
  memset_0(v65, 0, 0x48u);
  *(_QWORD *)&v76.cEntries = 0;
  *(_QWORD *)&v76.aEntries[0].ulReserved1 = 0;
  v50 = 0;
  *v54 = 0;
  *v55 = 0;
  v76.aEntries[0].rgPropVals = 0;
  v53 = PmvalFindFromPmrow(a1, 0xFFF0102u, 1, 0, 0, 1);
  v13 = 0;
  if ( *(_DWORD *)v51 )
  {
    CoTaskMemFree(0);
    CoTaskMemFree(0);
    CoTaskMemFree(0);
    CoTaskMemFree(0);
    CoTaskMemFree(0);
    v14 = v47;
    v47 = 0;
    if ( v14 )
    {
      Release = (unsigned int (__fastcall *)(MAPIValRef *__hidden))v14->lpVtbl->Release;
      if ( Release == MAPIRowRef::Release )
      {
        MAPIRowRef::Release((MAPIRowRef *)v14);
      }
      else if ( Release == MAPIValRef::Release )
      {
        MAPIValRef::Release((MAPIValRef *)v14);
      }
      else
      {
        ((void (__fastcall *)(struct IMessage *))v14->lpVtbl->Release)(v14);
      }
    }
    if ( pv )
      MAPIFreeBuffer(pv);
    return v13;
  }
  if ( !*(_QWORD *)(v51 + 8)
    && (GetFreeBusySupportObject((struct IFreeBusySupport **)(v51 + 8), *(const char **)(v51 + 16), v12, 0) < 0
     || (v16 = *(_QWORD *)(v51 + 8)) == 0
     || (*(int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v16 + 24LL))(
          v16,
          *(_QWORD *)(v51 + 40),
          0,
          0) < 0) )
  {
    CoTaskMemFree(0);
    CoTaskMemFree(0);
    CoTaskMemFree(0);
    CoTaskMemFree(0);
    CoTaskMemFree(0);
    v17 = v47;
    v47 = 0;
    if ( v17 )
    {
      v18 = (unsigned int (__fastcall *)(MAPIValRef *__hidden))v17->lpVtbl->Release;
      if ( v18 == MAPIRowRef::Release )
      {
        MAPIRowRef::Release((MAPIRowRef *)v17);
      }
      else if ( v18 == MAPIValRef::Release )
      {
        MAPIValRef::Release((MAPIValRef *)v17);
      }
      else
      {
        ((void (__fastcall *)(struct IMessage *))v17->lpVtbl->Release)(v17);
      }
    }
    if ( pv )
      MAPIFreeBuffer(pv);
    return 1;
  }
  if ( v53 )
  {
    AFX_EXCEPTION_LINK::AFX_EXCEPTION_LINK((AFX_EXCEPTION_LINK *)v74);
    p_Value = (struct _SBinary *)&v53->Value;
    LODWORD(v64) = 0;
    LODWORD(v63) = v53->Value.l;
    *((_QWORD *)&v63 + 1) = v53->Value.bin.lpb;
    v20 = *(__int64 **)(v51 + 8);
    v21 = *v20;
    v75[0] = v63;
    v75[1] = v64;
    if ( (*(int (__fastcall **)(__int64 *, _OWORD *, _BYTE *))(v21 + 64))(v20, v75, v65) < 0 )
    {
      AfxTryCleanup();
      CoTaskMemFree(0);
      CoTaskMemFree(0);
      CoTaskMemFree(0);
      CoTaskMemFree(0);
      CoTaskMemFree(0);
      v22 = v47;
      v47 = 0;
      if ( v22 )
      {
        v23 = (unsigned int (__fastcall *)(MAPIValRef *__hidden))v22->lpVtbl->Release;
        if ( v23 == MAPIRowRef::Release )
        {
          MAPIRowRef::Release((MAPIRowRef *)v22);
        }
        else if ( v23 == MAPIValRef::Release )
        {
          MAPIValRef::Release((MAPIValRef *)v22);
        }
        else
        {
          ((void (__fastcall *)(struct IMessage *))v22->lpVtbl->Release)(v22);
        }
      }
      if ( pv )
        MAPIFreeBuffer(pv);
      v52 = 0;
      return 0;
    }
    v11 = v67;
    v60 = v67;
    v7 = v68;
    v56 = v68;
    v8 = v69;
    v57 = v69;
    v9 = v70;
    v58 = v70;
    v10 = v73;
    v59 = v73;
    if ( v66 && !v72 )
    {
      v24 = (_QWORD *)(v51 + 24);
      if ( !*(_QWORD *)(v51 + 24) )
      {
        DefaultStoreSpecialFolderFromSession = HrGetDefaultStoreSpecialFolderFromSession(
                                                 *(struct IUnknown **)(v51 + 40),
                                                 4,
                                                 0x10000u,
                                                 0,
                                                 (struct IMAPIFolder **)(v51 + 24));
        CheckOleResultTagRaw(DefaultStoreSpecialFolderFromSession, 0x1212A0u);
      }
      v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, struct IMessage **))(*(_QWORD *)*v24 + 152LL))(
              *v24,
              0,
              8,
              &v47);
      CheckMapiResultTag<SPIMsgStore &>(v26, v24, 1184417);
      v28 = ItemUIHost::HrPersistSave(*(ItemUIHost **)(v51 + 48), v47, v27, 0);
      CheckOleResultTagRaw(v28, 0x1212A2u);
      v76.cEntries = 1;
      v76.aEntries[0].cValues = 4;
      v29 = (struct _SPropValue *)MMemAllocNoThrow(0x60u, 0);
      v76.aEntries[0].rgPropVals = v29;
      v77.m256i_i32[0] = 805371934;
      v77.m256i_i32[6] = 805437470;
      LODWORD(v79) = 268370178;
      *((_DWORD *)&v80.at + 2) = 202702851;
      v81.l = v48;
      *(__m256i *)&v29->ulPropTag = v77;
      v29[1].Value = v78;
      *(_OWORD *)&v29[2].ulPropTag = v79;
      *(union _PV *)((char *)&v29[2].Value + 8) = v80;
      v29[3].Value = v81;
      for ( i = 0; ; i = v48 + 1 )
      {
        v48 = i;
        v31 = *(struct IMAPISession **)(v51 + 40);
        if ( i >= v66 )
          break;
        v53 = (struct _SPropValue *)(16LL * i);
        v32 = HrOpenAddrEntry(&v52, v31, (struct _SBinary *)&v68[(_QWORD)v53], 8u, 0);
        CheckOleResultTagRaw(v32, 0x1212A3u);
        LODWORD(v44) = 0x10000;
        v61 = (MAPIRowRef *)v52;
        Props = HrGetProps(v52, (struct _SPropValue **)&pv, 0x3001001Eu, 805437470, v44);
        CheckOleResultTagRaw(Props, 0x1212C0u);
        v76.aEntries[0].rgPropVals->Value.cur.int64 = *((_QWORD *)pv + 1);
        v76.aEntries[0].rgPropVals[1].Value.cur.int64 = *((_QWORD *)pv + 4);
        v76.aEntries[0].rgPropVals[2].Value = *(union _PV *)((char *)&v53->ulPropTag + (_QWORD)v68);
        SetPmessPmadl(v47, &v76, v48 != 0 ? 2 : 0);
        if ( pv )
          MAPIFreeBuffer(pv);
        pv = 0;
        v52 = 0;
        if ( v61 )
        {
          v34 = *(unsigned int (__fastcall **)(MAPIValRef *__hidden))(*(_QWORD *)v61 + 16LL);
          if ( v34 == MAPIRowRef::Release )
          {
            MAPIRowRef::Release(v61);
          }
          else if ( v34 == MAPIValRef::Release )
          {
            MAPIValRef::Release(v61);
          }
          else
          {
            (*(void (**)(void))(*(_QWORD *)v61 + 16LL))();
          }
        }
      }
      v35 = HrOpenAddrEntry(&v52, v31, p_Value, 8u, 0);
      CheckOleResultTagRaw(v35, 0x1212C1u);
      LODWORD(v46) = 806027522;
      LODWORD(v45) = 805503006;
      v6 = v52;
      v36 = HrGetProps(v52, (struct _SPropValue **)&pv, 0xFFF0102u, 805437470, v45, v46, 805371934, 0x10000);
      CheckOleResultTagRaw(v36, 0x1212C2u);
      v77.m256i_i32[0] = 4391170;
      *(_OWORD *)&v77.m256i_u64[1] = *(_OWORD *)((char *)pv + 8);
      v77.m256i_i32[6] = 234946571;
      v78.i = 1;
      LODWORD(v79) = 7798814;
      *((_QWORD *)&v79 + 1) = *((_QWORD *)pv + 4);
      *((_DWORD *)&v80.at + 2) = 7864350;
      v81.cur.int64 = *((_QWORD *)pv + 7);
      v82 = 5374210;
      v83 = *((_OWORD *)pv + 5);
      v84 = 4456478;
      v85 = *((_QWORD *)pv + 13);
      v37 = HrSetProps((struct IMAPIProp *)v47, 6u, (struct _SPropValue *)&v77, 0, 0);
      CheckOleResultTagRaw(v37, 0x1212C3u);
      v38 = ((__int64 (__fastcall *)(struct IMessage *, _QWORD))v47->lpVtbl->put_Newsgroups)(
              v47,
              *(unsigned int *)(v51 + 56));
      CheckMapiResultTag<SPIMsgStore &>(v38, &v47, 1184452);
      v39 = v47;
      v47 = 0;
      if ( v39 )
      {
        v40 = (unsigned int (__fastcall *)(MAPIValRef *__hidden))v39->lpVtbl->Release;
        if ( v40 == MAPIRowRef::Release )
        {
          MAPIRowRef::Release((MAPIRowRef *)v39);
        }
        else if ( v40 == MAPIValRef::Release )
        {
          MAPIValRef::Release((MAPIValRef *)v39);
        }
        else
        {
          ((void (__fastcall *)(struct IMessage *))v39->lpVtbl->Release)(v39);
        }
      }
      *v54 = 1;
      *v55 = v71 == 0;
    }
    AfxTryCleanup();
  }
  if ( v76.aEntries[0].rgPropVals )
    MAPIFreeBuffer(v76.aEntries[0].rgPropVals);
  CoTaskMemFree(v11);
  CoTaskMemFree(v10);
  CoTaskMemFree(v9);
  CoTaskMemFree(v8);
  CoTaskMemFree(v7);
  v41 = v47;
  v47 = 0;
  if ( v41 )
  {
    v42 = (void (*)(void))v41->lpVtbl->Release;
    if ( (char *)v42 == (char *)MAPIRowRef::Release )
    {
      MAPIRowRef::Release((MAPIRowRef *)v41);
    }
    else if ( (char *)v42 == (char *)MAPIValRef::Release )
    {
      MAPIValRef::Release((MAPIValRef *)v41);
    }
    else
    {
      v42();
    }
  }
  if ( pv )
    MAPIFreeBuffer(pv);
  if ( v6 )
  {
    v43 = v6->lpVtbl->Release;
    if ( (char *)v43 == (char *)MAPIRowRef::Release )
    {
      MAPIRowRef::Release((MAPIRowRef *)v6);
    }
    else if ( (char *)v43 == (char *)MAPIValRef::Release )
    {
      MAPIValRef::Release((MAPIValRef *)v6);
    }
    else
    {
      ((void (__fastcall *)(struct IMAPIProp *))v43)(v6);
    }
  }
  return v50;
}

```

## disassembly

```asm
0x14172a590  push    rbx
0x14172a592  push    rsi
0x14172a593  push    rdi
0x14172a594  push    r12
0x14172a596  push    r13
0x14172a598  push    r14
0x14172a59a  push    r15
0x14172a59c  sub     rsp, 230h
0x14172a5a3  mov     rax, cs:__security_cookie
0x14172a5aa  xor     rax, rsp
0x14172a5ad  mov     [rsp+268h+var_48], rax
0x14172a5b5  mov     [rsp+268h+var_220], r9d
0x14172a5ba  mov     [rsp+268h+var_1E8], r8
0x14172a5c2  mov     [rsp+268h+var_1F0], rdx
0x14172a5c7  mov     r13, rcx
0x14172a5ca  mov     rax, [rsp+268h+arg_20]
0x14172a5d2  mov     [rsp+268h+var_208], rax
0x14172a5d7  xor     eax, eax
0x14172a5d9  mov     ebx, eax
0x14172a5db  mov     [rsp+268h+var_200], rax
0x14172a5e0  mov     [rsp+268h+pv], rax
0x14172a5e5  mov     [rsp+268h+var_228], rax
0x14172a5ea  mov     edi, eax
0x14172a5ec  mov     [rsp+268h+var_1E0], rax
0x14172a5f4  mov     esi, eax
0x14172a5f6  mov     [rsp+268h+var_1D8], rax
0x14172a5fe  mov     r14d, eax
0x14172a601  mov     [rsp+268h+var_1D0], rax
0x14172a609  mov     r15d, eax
0x14172a60c  mov     [rsp+268h+var_1C8], rax
0x14172a614  mov     r12d, eax
0x14172a617  mov     [rsp+268h+var_1C0], rax
0x14172a61f  mov     dword ptr [rsp+268h+var_1A8+4], eax
0x14172a626  mov     qword ptr [rsp+268h+var_198+4], rax
0x14172a62e  mov     dword ptr [rsp+268h+var_198+0Ch], eax
0x14172a635  xor     edx, edx; Val
0x14172a637  lea     r8d, [rax+48h]; Size
0x14172a63b  lea     rcx, [rsp+268h+var_188]; void *
0x14172a643  call    memset_0
0x14172a648  xor     eax, eax
0x14172a64a  mov     qword ptr [rsp+268h+var_F8.cEntries], rax
0x14172a652  mov     qword ptr [rsp+268h+var_F8.aEntries.ulReserved1], rax
0x14172a65a  mov     [rsp+268h+var_210], eax
0x14172a65e  mov     rcx, [rsp+268h+var_1F0]
0x14172a663  mov     [rcx], al
0x14172a665  mov     rcx, [rsp+268h+var_1E8]
0x14172a66d  mov     [rcx], al
0x14172a66f  mov     [rsp+268h+var_F8.aEntries.rgPropVals], rax
0x14172a677  lea     ecx, [rax+1]
0x14172a67a  mov     dword ptr [rsp+268h+var_240], ecx
0x14172a67e  mov     [rsp+268h+var_248], rax
0x14172a683  xor     r9d, r9d
0x14172a686  mov     r8d, ecx
0x14172a689  mov     edx, 0FFF0102h
0x14172a68e  mov     rcx, r13
0x14172a691  call    cs:__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z; PmvalFindFromPmrow(_SRow const *,ulong,int,int,ulong *,int)
0x14172a697  mov     [rsp+268h+var_1F8], rax
0x14172a69c  xor     r13d, r13d
0x14172a69f  mov     rcx, [rsp+268h+var_208]
0x14172a6a4  cmp     [rcx], r13d
0x14172a6a7  jz      loc_14172A739
0x14172a6ad  xor     ecx, ecx; pv
0x14172a6af  call    cs:__imp_CoTaskMemFree
0x14172a6b5  xor     ecx, ecx; pv
0x14172a6b7  call    cs:__imp_CoTaskMemFree
0x14172a6bd  xor     ecx, ecx; pv
0x14172a6bf  call    cs:__imp_CoTaskMemFree
0x14172a6c5  xor     ecx, ecx; pv
0x14172a6c7  call    cs:__imp_CoTaskMemFree
0x14172a6cd  nop     dword ptr [rax]
0x14172a6d0  xor     ecx, ecx; pv
0x14172a6d2  call    cs:__imp_CoTaskMemFree
0x14172a6d8  mov     rcx, [rsp+268h+var_228]; this
0x14172a6dd  mov     [rsp+268h+var_228], r13
0x14172a6e2  test    rcx, rcx
0x14172a6e5  jz      short loc_14172A720
0x14172a6e7  mov     rax, [rcx]
0x14172a6ea  mov     rdx, [rax+10h]
0x14172a6ee  lea     rax, ?Release@MAPIRowRef@@UEAAKXZ; MAPIRowRef::Release(void)
0x14172a6f5  cmp     rdx, rax
0x14172a6f8  jnz     short loc_14172A701
0x14172a6fa  call    ?Release@MAPIRowRef@@UEAAKXZ; MAPIRowRef::Release(void)
0x14172a6ff  jmp     short loc_14172A720
0x14172a701  lea     rax, ?Release@MAPIValRef@@UEAAKXZ; MAPIValRef::Release(void)
0x14172a708  cmp     rdx, rax
0x14172a70b  jnz     short loc_14172A714
0x14172a70d  call    ?Release@MAPIValRef@@UEAAKXZ; MAPIValRef::Release(void)
0x14172a712  jmp     short loc_14172A720
0x14172a714  mov     rax, rdx
0x14172a717  call    cs:__guard_dispatch_icall_fptr
0x14172a71d  nop
0x14172a71e  xchg    ax, ax
0x14172a720  mov     rcx, [rsp+268h+pv]; pv
0x14172a725  test    rcx, rcx
0x14172a728  jz      loc_14172A80D
0x14172a72e  call    cs:__imp_MAPIFreeBuffer
0x14172a734  jmp     loc_14172A80D
0x14172a739  cmp     [rcx+8], r13
0x14172a73d  jnz     loc_14172A815
0x14172a743  xor     r9d, r9d; struct _MAPIUID *
0x14172a746  mov     rdx, [rcx+10h]; char *
0x14172a74a  add     rcx, 8; struct IFreeBusySupport **
0x14172a74e  call    ?GetFreeBusySupportObject@@YAJPEAPEAUIFreeBusySupport@@PEBDKPEBU_MAPIUID@@@Z; GetFreeBusySupportObject(IFreeBusySupport * *,char const *,ulong,_MAPIUID const *)
0x14172a753  test    eax, eax
0x14172a755  js      short loc_14172A784
0x14172a757  mov     rdx, [rsp+268h+var_208]
0x14172a75c  mov     rcx, [rdx+8]
0x14172a760  test    rcx, rcx
0x14172a763  jz      short loc_14172A784
0x14172a765  mov     rax, [rcx]
0x14172a768  xor     r9d, r9d
0x14172a76b  xor     r8d, r8d
0x14172a76e  mov     rdx, [rdx+28h]
0x14172a772  mov     rax, [rax+18h]
0x14172a776  call    cs:__guard_dispatch_icall_fptr
0x14172a77c  test    eax, eax
0x14172a77e  jns     loc_14172A815
0x14172a784  xor     ecx, ecx; pv
0x14172a786  call    cs:__imp_CoTaskMemFree
0x14172a78c  xor     ecx, ecx; pv
0x14172a78e  call    cs:__imp_CoTaskMemFree
0x14172a794  xor     ecx, ecx; pv
0x14172a796  call    cs:__imp_CoTaskMemFree
0x14172a79c  xor     ecx, ecx; pv
0x14172a79e  call    cs:__imp_CoTaskMemFree
0x14172a7a4  xor     ecx, ecx; pv
0x14172a7a6  call    cs:__imp_CoTaskMemFree
0x14172a7ac  nop     dword ptr [rax+00h]
0x14172a7b0  mov     rcx, [rsp+268h+var_228]; this
0x14172a7b5  mov     [rsp+268h+var_228], r13
0x14172a7ba  test    rcx, rcx
0x14172a7bd  jz      short loc_14172A7F7
0x14172a7bf  nop
0x14172a7c0  mov     rax, [rcx]
0x14172a7c3  mov     rdx, [rax+10h]
0x14172a7c7  lea     rax, ?Release@MAPIRowRef@@UEAAKXZ; MAPIRowRef::Release(void)
0x14172a7ce  cmp     rdx, rax
0x14172a7d1  jnz     short loc_14172A7DA
0x14172a7d3  call    ?Release@MAPIRowRef@@UEAAKXZ; MAPIRowRef::Release(void)
0x14172a7d8  jmp     short loc_14172A7F7
0x14172a7da  lea     rax, ?Release@MAPIValRef@@UEAAKXZ; MAPIValRef::Release(void)
0x14172a7e1  cmp     rdx, rax
0x14172a7e4  jnz     short loc_14172A7ED
0x14172a7e6  call    ?Release@MAPIValRef@@UEAAKXZ; MAPIValRef::Release(void)
0x14172a7eb  jmp     short loc_14172A7F7
0x14172a7ed  mov     rax, rdx
0x14172a7f0  call    cs:__guard_dispatch_icall_fptr
0x14172a7f6  nop
0x14172a7f7  mov     rcx, [rsp+268h+pv]; pv
0x14172a7fc  test    rcx, rcx
0x14172a7ff  jz      short loc_14172A807
0x14172a801  call    cs:__imp_MAPIFreeBuffer
0x14172a807  mov     r13d, 1
0x14172a80d  mov     eax, r13d
0x14172a810  jmp     loc_14172AEEF
0x14172a815  cmp     [rsp+268h+var_1F8], r13
0x14172a81a  jz      loc_14172AE23
0x14172a820  lea     rcx, [rsp+268h+var_130]; this
0x14172a828  call    ??0AFX_EXCEPTION_LINK@@QEAA@XZ; AFX_EXCEPTION_LINK::AFX_EXCEPTION_LINK(void)
0x14172a82d  mov     rcx, [rsp+268h+var_1F8]
0x14172a832  add     rcx, 8
0x14172a836  mov     [rsp+268h+var_1B0], rcx
0x14172a83e  mov     dword ptr [rsp+268h+var_198], r13d
0x14172a846  mov     eax, [rcx]
0x14172a848  mov     dword ptr [rsp+268h+var_1A8], eax
0x14172a84f  mov     rax, [rcx+8]
0x14172a853  mov     qword ptr [rsp+268h+var_1A8+8], rax
0x14172a85b  mov     rax, [rsp+268h+var_208]
0x14172a860  mov     rcx, [rax+8]
0x14172a864  mov     rax, [rcx]
0x14172a867  movups  xmm0, [rsp+268h+var_1A8]
0x14172a86f  movaps  [rsp+268h+var_118], xmm0
0x14172a877  movups  xmm1, [rsp+268h+var_198]
0x14172a87f  movaps  [rsp+268h+var_108], xmm1
0x14172a887  lea     r8, [rsp+268h+var_188]
0x14172a88f  lea     rdx, [rsp+268h+var_118]
0x14172a897  mov     rax, [rax+40h]
0x14172a89b  call    cs:__guard_dispatch_icall_fptr
0x14172a8a1  test    eax, eax
0x14172a8a3  jns     loc_14172A939
0x14172a8a9  call    ?AfxTryCleanup@@YAXXZ; AfxTryCleanup(void)
0x14172a8ae  xor     ecx, ecx; pv
0x14172a8b0  call    cs:__imp_CoTaskMemFree
0x14172a8b6  xor     ecx, ecx; pv
0x14172a8b8  call    cs:__imp_CoTaskMemFree
0x14172a8be  xor     ecx, ecx; pv
0x14172a8c0  call    cs:__imp_CoTaskMemFree
0x14172a8c6  xor     ecx, ecx; pv
0x14172a8c8  call    cs:__imp_CoTaskMemFree
0x14172a8ce  xor     ecx, ecx; pv
0x14172a8d0  call    cs:__imp_CoTaskMemFree
0x14172a8d6  mov     rcx, [rsp+268h+var_228]; this
0x14172a8db  mov     [rsp+268h+var_228], r13
0x14172a8e0  test    rcx, rcx
0x14172a8e3  jz      short loc_14172A91C
0x14172a8e5  mov     rax, [rcx]
0x14172a8e8  mov     rdx, [rax+10h]
0x14172a8ec  lea     rax, ?Release@MAPIRowRef@@UEAAKXZ; MAPIRowRef::Release(void)
0x14172a8f3  cmp     rdx, rax
0x14172a8f6  jnz     short loc_14172A8FF
0x14172a8f8  call    ?Release@MAPIRowRef@@UEAAKXZ; MAPIRowRef::Release(void)
0x14172a8fd  jmp     short loc_14172A91C
0x14172a8ff  lea     rax, ?Release@MAPIValRef@@UEAAKXZ; MAPIValRef::Release(void)
0x14172a906  cmp     rdx, rax
0x14172a909  jnz     short loc_14172A912
0x14172a90b  call    ?Release@MAPIValRef@@UEAAKXZ; MAPIValRef::Release(void)
0x14172a910  jmp     short loc_14172A91C
0x14172a912  mov     rax, rdx
0x14172a915  call    cs:__guard_dispatch_icall_fptr
0x14172a91b  nop
0x14172a91c  mov     rcx, [rsp+268h+pv]; pv
0x14172a921  test    rcx, rcx
0x14172a924  jz      short loc_14172A92D
0x14172a926  call    cs:__imp_MAPIFreeBuffer
0x14172a92c  nop
0x14172a92d  mov     [rsp+268h+var_200], r13
0x14172a932  xor     eax, eax
0x14172a934  jmp     loc_14172AEEF
0x14172a939  mov     r12, [rsp+268h+var_180]
0x14172a941  mov     [rsp+268h+var_1C0], r12
0x14172a949  mov     rdi, [rsp+268h+var_178]
0x14172a951  mov     [rsp+268h+var_1E0], rdi
0x14172a959  mov     rsi, [rsp+268h+var_170]
0x14172a961  mov     [rsp+268h+var_1D8], rsi
0x14172a969  mov     r14, [rsp+268h+var_168]
0x14172a971  mov     [rsp+268h+var_1D0], r14
0x14172a979  mov     r15, [rsp+268h+var_148]
0x14172a981  mov     [rsp+268h+var_1C8], r15
0x14172a989  cmp     [rsp+268h+var_184], r13d
0x14172a991  jz      loc_14172ADE4
0x14172a997  cmp     [rsp+268h+var_158], r13d
0x14172a99f  jnz     loc_14172ADE4
0x14172a9a5  mov     rax, [rsp+268h+var_208]
0x14172a9aa  lea     rbx, [rax+18h]
0x14172a9ae  cmp     [rbx], r13
0x14172a9b1  jnz     short loc_14172A9DA
0x14172a9b3  mov     [rsp+268h+var_248], rbx; struct IMAPIFolder **
0x14172a9b8  xor     r9d, r9d; struct _SBinary **
0x14172a9bb  lea     edx, [r9+4]; int
0x14172a9bf  mov     r8d, 10000h; unsigned int
0x14172a9c5  mov     rcx, [rax+28h]; struct IUnknown *
0x14172a9c9  call    ?HrGetDefaultStoreSpecialFolderFromSession@@YAJPEAUIUnknown@@HKPEAPEAU_SBinary@@PEAPEAUIMAPIFolder@@@Z; HrGetDefaultStoreSpecialFolderFromSession(IUnknown *,int,ulong,_SBinary * *,IMAPIFolder * *)
0x14172a9ce  mov     edx, 1212A0h; unsigned int
0x14172a9d3  mov     ecx, eax; int
0x14172a9d5  call    ?CheckOleResultTagRaw@@YAJJK@Z; CheckOleResultTagRaw(long,ulong)
0x14172a9da  mov     rcx, [rbx]
0x14172a9dd  mov     rax, [rcx]
0x14172a9e0  lea     r9, [rsp+268h+var_228]
0x14172a9e5  xor     edx, edx
0x14172a9e7  lea     r8d, [rdx+8]
0x14172a9eb  mov     rax, [rax+98h]
0x14172a9f2  call    cs:__guard_dispatch_icall_fptr
0x14172a9f8  mov     r8d, 1212A1h
0x14172a9fe  mov     rdx, rbx
0x14172aa01  mov     ecx, eax
0x14172aa03  call    ??$CheckMapiResultTag@AEAVSPIMsgStore@@@@YAJJAEAVSPIMsgStore@@K@Z; CheckMapiResultTag<SPIMsgStore &>(long,SPIMsgStore &,ulong)
0x14172aa08  xor     r9d, r9d; unsigned int
0x14172aa0b  mov     rdx, [rsp+268h+var_228]; struct IMessage *
0x14172aa10  mov     rax, [rsp+268h+var_208]
0x14172aa15  mov     rcx, [rax+30h]; this
0x14172aa19  call    ?HrPersistSave@ItemUIHost@@QEAAJPEAUIMessage@@PEAU_SPropTagArray@@K@Z; ItemUIHost::HrPersistSave(IMessage *,_SPropTagArray *,ulong)
0x14172aa1e  mov     edx, 1212A2h; unsigned int
0x14172aa23  mov     ecx, eax; int
0x14172aa25  call    ?CheckOleResultTagRaw@@YAJJK@Z; CheckOleResultTagRaw(long,ulong)
0x14172aa2a  mov     eax, 1
0x14172aa2f  mov     [rsp+268h+var_F8.cEntries], eax
0x14172aa36  mov     [rsp+268h+var_F8.aEntries.cValues], 4
0x14172aa41  xor     edx, edx; void *
0x14172aa43  lea     ecx, [rax+5Fh]; unsigned __int64
0x14172aa46  call    ?MMemAllocNoThrow@@YAPEAX_KPEAX@Z; MMemAllocNoThrow(unsigned __int64,void *)
0x14172aa4b  mov     [rsp+268h+var_F8.aEntries.rgPropVals], rax
0x14172aa53  mov     dword ptr [rsp+268h+var_D8], 3001001Eh
0x14172aa5e  mov     [rsp+268h+var_C0], 3002001Eh
0x14172aa69  mov     dword ptr [rsp+268h+var_A8], 0FFF0102h
0x14172aa74  mov     [rsp+268h+var_90], 0C150003h
0x14172aa7f  mov     ecx, [rsp+268h+var_220]
0x14172aa83  mov     dword ptr [rsp+268h+var_88], ecx
0x14172aa8a  movaps  xmm0, [rsp+268h+var_D8]
0x14172aa92  movups  xmmword ptr [rax], xmm0
0x14172aa95  movaps  xmm1, xmmword ptr [rsp+1A0h]
0x14172aa9d  movups  xmmword ptr [rax+10h], xmm1
0x14172aaa1  movaps  xmm0, [rsp+268h+var_B8]
0x14172aaa9  movups  xmmword ptr [rax+20h], xmm0
0x14172aaad  movaps  xmm1, [rsp+268h+var_A8]
0x14172aab5  movups  xmmword ptr [rax+30h], xmm1
0x14172aab9  movaps  xmm0, xmmword ptr [rsp+1D0h]
0x14172aac1  movups  xmmword ptr [rax+40h], xmm0
0x14172aac5  movaps  xmm1, [rsp+268h+var_88]
0x14172aacd  movups  xmmword ptr [rax+50h], xmm1
0x14172aad1  mov     eax, r13d
0x14172aad4  lea     rbx, ?Release@MAPIValRef@@UEAAKXZ; MAPIValRef::Release(void)
0x14172aadb  mov     [rsp+268h+var_220], eax
0x14172aadf  mov     rcx, [rsp+268h+var_208]
0x14172aae4  mov     rdx, [rcx+28h]; struct IMAPISession *
0x14172aae8  mov     [rsp+268h+var_248], r13; struct _MAPIUID *
0x14172aaed  mov     r9d, 8; unsigned int
0x14172aaf3  cmp     eax, [rsp+268h+var_184]
0x14172aafa  jge     loc_14172AC2D
0x14172ab00  movsxd  rcx, eax
0x14172ab03  shl     rcx, 4
  ... truncated ...
```
