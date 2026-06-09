# RecipCallback(_ADRENTRY *,bool *,bool *,ulong,__int64)

- ea: `0x14172a650`
- end: `0x14172afd2`
- name: `?RecipCallback@@YAJPEAU_ADRENTRY@@PEA_N1K_J@Z`
- size: `2434`
- prototype: `__int64 __fastcall(struct _ADRENTRY *, bool *, bool *, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task`

## callees

- `0x1400d3de0`
- `0x1400d3e10`
- `0x1400d4d0c`
- `0x1400dd670`
- `0x1400dd700`
- `0x140186928`
- `0x1402d4114`
- `0x1405049f0`
- `0x140505260`
- `0x1406232b0`
- `0x14063b728`
- `0x14069806c`
- `0x1407e9990`
- `0x140b65a04`
- `0x14144eb5c`
- `0x14172a650`

## import_xrefs

- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172a7ee`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172a8c1`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172a9e6`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172ac96`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172aef0`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172af5c`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172a7ee`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172a8c1`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172a9e6`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172ac96`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172aef0`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14172af5c`
- `ole32!CoTaskMemFree` at `0x14172a76f`
- `ole32!CoTaskMemFree` at `0x14172a777`
- `ole32!CoTaskMemFree` at `0x14172a77f`
- `ole32!CoTaskMemFree` at `0x14172a787`
- `ole32!CoTaskMemFree` at `0x14172a792`
- `ole32!CoTaskMemFree` at `0x14172a846`
- `ole32!CoTaskMemFree` at `0x14172a84e`
- `ole32!CoTaskMemFree` at `0x14172a856`
- `ole32!CoTaskMemFree` at `0x14172a85e`
- `ole32!CoTaskMemFree` at `0x14172a866`
- `ole32!CoTaskMemFree` at `0x14172a970`
- `ole32!CoTaskMemFree` at `0x14172a978`
- `ole32!CoTaskMemFree` at `0x14172a980`
- `ole32!CoTaskMemFree` at `0x14172a988`
- `ole32!CoTaskMemFree` at `0x14172a990`
- `ole32!CoTaskMemFree` at `0x14172aefa`
- `ole32!CoTaskMemFree` at `0x14172af03`
- `ole32!CoTaskMemFree` at `0x14172af0c`
- `ole32!CoTaskMemFree` at `0x14172af15`
- `ole32!CoTaskMemFree` at `0x14172af1e`
- `ole32!CoTaskMemFree` at `0x14172a76f`
- `ole32!CoTaskMemFree` at `0x14172a777`
- `ole32!CoTaskMemFree` at `0x14172a77f`
- `ole32!CoTaskMemFree` at `0x14172a787`
- `ole32!CoTaskMemFree` at `0x14172a792`
- `ole32!CoTaskMemFree` at `0x14172a846`
- `ole32!CoTaskMemFree` at `0x14172a84e`
- `ole32!CoTaskMemFree` at `0x14172a856`
- `ole32!CoTaskMemFree` at `0x14172a85e`
- `ole32!CoTaskMemFree` at `0x14172a866`
- `ole32!CoTaskMemFree` at `0x14172a970`
- `ole32!CoTaskMemFree` at `0x14172a978`
- `ole32!CoTaskMemFree` at `0x14172a980`
- `ole32!CoTaskMemFree` at `0x14172a988`
- `ole32!CoTaskMemFree` at `0x14172a990`
- `ole32!CoTaskMemFree` at `0x14172aefa`
- `ole32!CoTaskMemFree` at `0x14172af03`
- `ole32!CoTaskMemFree` at `0x14172af0c`
- `ole32!CoTaskMemFree` at `0x14172af15`
- `ole32!CoTaskMemFree` at `0x14172af1e`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x14172ac13`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x14172ad44`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x14172ac13`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x14172ad44`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x14172a751`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x14172a751`
- `Mso98Win32Client!__imp_?HrSetProps@@YAJPEAUIMAPIProp@@KPEAU_SPropValue@@PEAPEAU_SPropProblemArray@@PEAJ@Z` at `0x14172ae01`
- `Mso98Win32Client!__imp_?HrSetProps@@YAJPEAUIMAPIProp@@KPEAU_SPropValue@@PEAPEAU_SPropProblemArray@@PEAJ@Z` at `0x14172ae01`

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
0x14172a650  push    rbx
0x14172a652  push    rsi
0x14172a653  push    rdi
0x14172a654  push    r12
0x14172a656  push    r13
0x14172a658  push    r14
0x14172a65a  push    r15
0x14172a65c  sub     rsp, 230h
0x14172a663  mov     rax, cs:__security_cookie
0x14172a66a  xor     rax, rsp
0x14172a66d  mov     [rsp+268h+var_48], rax
0x14172a675  mov     [rsp+268h+var_220], r9d
0x14172a67a  mov     [rsp+268h+var_1E8], r8
0x14172a682  mov     [rsp+268h+var_1F0], rdx
0x14172a687  mov     r13, rcx
0x14172a68a  mov     rax, [rsp+268h+arg_20]
0x14172a692  mov     [rsp+268h+var_208], rax
0x14172a697  xor     eax, eax
0x14172a699  mov     ebx, eax
0x14172a69b  mov     [rsp+268h+var_200], rax
0x14172a6a0  mov     [rsp+268h+pv], rax
0x14172a6a5  mov     [rsp+268h+var_228], rax
0x14172a6aa  mov     edi, eax
0x14172a6ac  mov     [rsp+268h+var_1E0], rax
0x14172a6b4  mov     esi, eax
0x14172a6b6  mov     [rsp+268h+var_1D8], rax
0x14172a6be  mov     r14d, eax
0x14172a6c1  mov     [rsp+268h+var_1D0], rax
0x14172a6c9  mov     r15d, eax
0x14172a6cc  mov     [rsp+268h+var_1C8], rax
0x14172a6d4  mov     r12d, eax
0x14172a6d7  mov     [rsp+268h+var_1C0], rax
0x14172a6df  mov     dword ptr [rsp+268h+var_1A8+4], eax
0x14172a6e6  mov     qword ptr [rsp+268h+var_198+4], rax
0x14172a6ee  mov     dword ptr [rsp+268h+var_198+0Ch], eax
0x14172a6f5  xor     edx, edx; Val
0x14172a6f7  lea     r8d, [rax+48h]; Size
0x14172a6fb  lea     rcx, [rsp+268h+var_188]; void *
0x14172a703  call    memset_0
0x14172a708  xor     eax, eax
0x14172a70a  mov     qword ptr [rsp+268h+var_F8.cEntries], rax
0x14172a712  mov     qword ptr [rsp+268h+var_F8.aEntries.ulReserved1], rax
0x14172a71a  mov     [rsp+268h+var_210], eax
0x14172a71e  mov     rcx, [rsp+268h+var_1F0]
0x14172a723  mov     [rcx], al
0x14172a725  mov     rcx, [rsp+268h+var_1E8]
0x14172a72d  mov     [rcx], al
0x14172a72f  mov     [rsp+268h+var_F8.aEntries.rgPropVals], rax
0x14172a737  lea     ecx, [rax+1]
0x14172a73a  mov     dword ptr [rsp+268h+var_240], ecx
0x14172a73e  mov     [rsp+268h+var_248], rax
0x14172a743  xor     r9d, r9d
0x14172a746  mov     r8d, ecx
0x14172a749  mov     edx, 0FFF0102h
0x14172a74e  mov     rcx, r13
0x14172a751  call    cs:__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z; PmvalFindFromPmrow(_SRow const *,ulong,int,int,ulong *,int)
0x14172a757  mov     [rsp+268h+var_1F8], rax
0x14172a75c  xor     r13d, r13d
0x14172a75f  mov     rcx, [rsp+268h+var_208]
0x14172a764  cmp     [rcx], r13d
0x14172a767  jz      loc_14172A7F9
0x14172a76d  xor     ecx, ecx; pv
0x14172a76f  call    cs:__imp_CoTaskMemFree
0x14172a775  xor     ecx, ecx; pv
0x14172a777  call    cs:__imp_CoTaskMemFree
0x14172a77d  xor     ecx, ecx; pv
0x14172a77f  call    cs:__imp_CoTaskMemFree
0x14172a785  xor     ecx, ecx; pv
0x14172a787  call    cs:__imp_CoTaskMemFree
0x14172a78d  nop     dword ptr [rax]
0x14172a790  xor     ecx, ecx; pv
0x14172a792  call    cs:__imp_CoTaskMemFree
0x14172a798  mov     rcx, [rsp+268h+var_228]; this
0x14172a79d  mov     [rsp+268h+var_228], r13
0x14172a7a2  test    rcx, rcx
0x14172a7a5  jz      short loc_14172A7E0
0x14172a7a7  mov     rax, [rcx]
0x14172a7aa  mov     rdx, [rax+10h]
0x14172a7ae  lea     rax, ?Release@MAPIRowRef@@UEAAKXZ; MAPIRowRef::Release(void)
0x14172a7b5  cmp     rdx, rax
0x14172a7b8  jnz     short loc_14172A7C1
0x14172a7ba  call    ?Release@MAPIRowRef@@UEAAKXZ; MAPIRowRef::Release(void)
0x14172a7bf  jmp     short loc_14172A7E0
0x14172a7c1  lea     rax, ?Release@MAPIValRef@@UEAAKXZ; MAPIValRef::Release(void)
0x14172a7c8  cmp     rdx, rax
0x14172a7cb  jnz     short loc_14172A7D4
0x14172a7cd  call    ?Release@MAPIValRef@@UEAAKXZ; MAPIValRef::Release(void)
0x14172a7d2  jmp     short loc_14172A7E0
0x14172a7d4  mov     rax, rdx
0x14172a7d7  call    cs:__guard_dispatch_icall_fptr
0x14172a7dd  nop
0x14172a7de  xchg    ax, ax
0x14172a7e0  mov     rcx, [rsp+268h+pv]; pv
0x14172a7e5  test    rcx, rcx
0x14172a7e8  jz      loc_14172A8CD
0x14172a7ee  call    cs:__imp_MAPIFreeBuffer
0x14172a7f4  jmp     loc_14172A8CD
0x14172a7f9  cmp     [rcx+8], r13
0x14172a7fd  jnz     loc_14172A8D5
0x14172a803  xor     r9d, r9d; struct _MAPIUID *
0x14172a806  mov     rdx, [rcx+10h]; char *
0x14172a80a  add     rcx, 8; struct IFreeBusySupport **
0x14172a80e  call    ?GetFreeBusySupportObject@@YAJPEAPEAUIFreeBusySupport@@PEBDKPEBU_MAPIUID@@@Z; GetFreeBusySupportObject(IFreeBusySupport * *,char const *,ulong,_MAPIUID const *)
0x14172a813  test    eax, eax
0x14172a815  js      short loc_14172A844
0x14172a817  mov     rdx, [rsp+268h+var_208]
0x14172a81c  mov     rcx, [rdx+8]
0x14172a820  test    rcx, rcx
0x14172a823  jz      short loc_14172A844
0x14172a825  mov     rax, [rcx]
0x14172a828  xor     r9d, r9d
0x14172a82b  xor     r8d, r8d
0x14172a82e  mov     rdx, [rdx+28h]
0x14172a832  mov     rax, [rax+18h]
0x14172a836  call    cs:__guard_dispatch_icall_fptr
0x14172a83c  test    eax, eax
0x14172a83e  jns     loc_14172A8D5
0x14172a844  xor     ecx, ecx; pv
0x14172a846  call    cs:__imp_CoTaskMemFree
0x14172a84c  xor     ecx, ecx; pv
0x14172a84e  call    cs:__imp_CoTaskMemFree
0x14172a854  xor     ecx, ecx; pv
0x14172a856  call    cs:__imp_CoTaskMemFree
0x14172a85c  xor     ecx, ecx; pv
0x14172a85e  call    cs:__imp_CoTaskMemFree
0x14172a864  xor     ecx, ecx; pv
0x14172a866  call    cs:__imp_CoTaskMemFree
0x14172a86c  nop     dword ptr [rax+00h]
0x14172a870  mov     rcx, [rsp+268h+var_228]; this
0x14172a875  mov     [rsp+268h+var_228], r13
0x14172a87a  test    rcx, rcx
0x14172a87d  jz      short loc_14172A8B7
0x14172a87f  nop
0x14172a880  mov     rax, [rcx]
0x14172a883  mov     rdx, [rax+10h]
0x14172a887  lea     rax, ?Release@MAPIRowRef@@UEAAKXZ; MAPIRowRef::Release(void)
0x14172a88e  cmp     rdx, rax
0x14172a891  jnz     short loc_14172A89A
0x14172a893  call    ?Release@MAPIRowRef@@UEAAKXZ; MAPIRowRef::Release(void)
0x14172a898  jmp     short loc_14172A8B7
0x14172a89a  lea     rax, ?Release@MAPIValRef@@UEAAKXZ; MAPIValRef::Release(void)
0x14172a8a1  cmp     rdx, rax
0x14172a8a4  jnz     short loc_14172A8AD
0x14172a8a6  call    ?Release@MAPIValRef@@UEAAKXZ; MAPIValRef::Release(void)
0x14172a8ab  jmp     short loc_14172A8B7
0x14172a8ad  mov     rax, rdx
0x14172a8b0  call    cs:__guard_dispatch_icall_fptr
0x14172a8b6  nop
0x14172a8b7  mov     rcx, [rsp+268h+pv]; pv
0x14172a8bc  test    rcx, rcx
0x14172a8bf  jz      short loc_14172A8C7
0x14172a8c1  call    cs:__imp_MAPIFreeBuffer
0x14172a8c7  mov     r13d, 1
0x14172a8cd  mov     eax, r13d
0x14172a8d0  jmp     loc_14172AFAF
0x14172a8d5  cmp     [rsp+268h+var_1F8], r13
0x14172a8da  jz      loc_14172AEE3
0x14172a8e0  lea     rcx, [rsp+268h+var_130]; this
0x14172a8e8  call    ??0AFX_EXCEPTION_LINK@@QEAA@XZ; AFX_EXCEPTION_LINK::AFX_EXCEPTION_LINK(void)
0x14172a8ed  mov     rcx, [rsp+268h+var_1F8]
0x14172a8f2  add     rcx, 8
0x14172a8f6  mov     [rsp+268h+var_1B0], rcx
0x14172a8fe  mov     dword ptr [rsp+268h+var_198], r13d
0x14172a906  mov     eax, [rcx]
0x14172a908  mov     dword ptr [rsp+268h+var_1A8], eax
0x14172a90f  mov     rax, [rcx+8]
0x14172a913  mov     qword ptr [rsp+268h+var_1A8+8], rax
0x14172a91b  mov     rax, [rsp+268h+var_208]
0x14172a920  mov     rcx, [rax+8]
0x14172a924  mov     rax, [rcx]
0x14172a927  movups  xmm0, [rsp+268h+var_1A8]
0x14172a92f  movaps  [rsp+268h+var_118], xmm0
0x14172a937  movups  xmm1, [rsp+268h+var_198]
0x14172a93f  movaps  [rsp+268h+var_108], xmm1
0x14172a947  lea     r8, [rsp+268h+var_188]
0x14172a94f  lea     rdx, [rsp+268h+var_118]
0x14172a957  mov     rax, [rax+40h]
0x14172a95b  call    cs:__guard_dispatch_icall_fptr
0x14172a961  test    eax, eax
0x14172a963  jns     loc_14172A9F9
0x14172a969  call    ?AfxTryCleanup@@YAXXZ; AfxTryCleanup(void)
0x14172a96e  xor     ecx, ecx; pv
0x14172a970  call    cs:__imp_CoTaskMemFree
0x14172a976  xor     ecx, ecx; pv
0x14172a978  call    cs:__imp_CoTaskMemFree
0x14172a97e  xor     ecx, ecx; pv
0x14172a980  call    cs:__imp_CoTaskMemFree
0x14172a986  xor     ecx, ecx; pv
0x14172a988  call    cs:__imp_CoTaskMemFree
0x14172a98e  xor     ecx, ecx; pv
0x14172a990  call    cs:__imp_CoTaskMemFree
0x14172a996  mov     rcx, [rsp+268h+var_228]; this
0x14172a99b  mov     [rsp+268h+var_228], r13
0x14172a9a0  test    rcx, rcx
0x14172a9a3  jz      short loc_14172A9DC
0x14172a9a5  mov     rax, [rcx]
0x14172a9a8  mov     rdx, [rax+10h]
0x14172a9ac  lea     rax, ?Release@MAPIRowRef@@UEAAKXZ; MAPIRowRef::Release(void)
0x14172a9b3  cmp     rdx, rax
0x14172a9b6  jnz     short loc_14172A9BF
0x14172a9b8  call    ?Release@MAPIRowRef@@UEAAKXZ; MAPIRowRef::Release(void)
0x14172a9bd  jmp     short loc_14172A9DC
0x14172a9bf  lea     rax, ?Release@MAPIValRef@@UEAAKXZ; MAPIValRef::Release(void)
0x14172a9c6  cmp     rdx, rax
0x14172a9c9  jnz     short loc_14172A9D2
0x14172a9cb  call    ?Release@MAPIValRef@@UEAAKXZ; MAPIValRef::Release(void)
0x14172a9d0  jmp     short loc_14172A9DC
0x14172a9d2  mov     rax, rdx
0x14172a9d5  call    cs:__guard_dispatch_icall_fptr
0x14172a9db  nop
0x14172a9dc  mov     rcx, [rsp+268h+pv]; pv
0x14172a9e1  test    rcx, rcx
0x14172a9e4  jz      short loc_14172A9ED
0x14172a9e6  call    cs:__imp_MAPIFreeBuffer
0x14172a9ec  nop
0x14172a9ed  mov     [rsp+268h+var_200], r13
0x14172a9f2  xor     eax, eax
0x14172a9f4  jmp     loc_14172AFAF
0x14172a9f9  mov     r12, [rsp+268h+var_180]
0x14172aa01  mov     [rsp+268h+var_1C0], r12
0x14172aa09  mov     rdi, [rsp+268h+var_178]
0x14172aa11  mov     [rsp+268h+var_1E0], rdi
0x14172aa19  mov     rsi, [rsp+268h+var_170]
0x14172aa21  mov     [rsp+268h+var_1D8], rsi
0x14172aa29  mov     r14, [rsp+268h+var_168]
0x14172aa31  mov     [rsp+268h+var_1D0], r14
0x14172aa39  mov     r15, [rsp+268h+var_148]
0x14172aa41  mov     [rsp+268h+var_1C8], r15
0x14172aa49  cmp     [rsp+268h+var_184], r13d
0x14172aa51  jz      loc_14172AEA4
0x14172aa57  cmp     [rsp+268h+var_158], r13d
0x14172aa5f  jnz     loc_14172AEA4
0x14172aa65  mov     rax, [rsp+268h+var_208]
0x14172aa6a  lea     rbx, [rax+18h]
0x14172aa6e  cmp     [rbx], r13
0x14172aa71  jnz     short loc_14172AA9A
0x14172aa73  mov     [rsp+268h+var_248], rbx; struct IMAPIFolder **
0x14172aa78  xor     r9d, r9d; struct _SBinary **
0x14172aa7b  lea     edx, [r9+4]; int
0x14172aa7f  mov     r8d, 10000h; unsigned int
0x14172aa85  mov     rcx, [rax+28h]; struct IUnknown *
0x14172aa89  call    ?HrGetDefaultStoreSpecialFolderFromSession@@YAJPEAUIUnknown@@HKPEAPEAU_SBinary@@PEAPEAUIMAPIFolder@@@Z; HrGetDefaultStoreSpecialFolderFromSession(IUnknown *,int,ulong,_SBinary * *,IMAPIFolder * *)
0x14172aa8e  mov     edx, 1212A0h; unsigned int
0x14172aa93  mov     ecx, eax; int
0x14172aa95  call    ?CheckOleResultTagRaw@@YAJJK@Z; CheckOleResultTagRaw(long,ulong)
0x14172aa9a  mov     rcx, [rbx]
0x14172aa9d  mov     rax, [rcx]
0x14172aaa0  lea     r9, [rsp+268h+var_228]
0x14172aaa5  xor     edx, edx
0x14172aaa7  lea     r8d, [rdx+8]
0x14172aaab  mov     rax, [rax+98h]
0x14172aab2  call    cs:__guard_dispatch_icall_fptr
0x14172aab8  mov     r8d, 1212A1h
0x14172aabe  mov     rdx, rbx
0x14172aac1  mov     ecx, eax
0x14172aac3  call    ??$CheckMapiResultTag@AEAVSPIMsgStore@@@@YAJJAEAVSPIMsgStore@@K@Z; CheckMapiResultTag<SPIMsgStore &>(long,SPIMsgStore &,ulong)
0x14172aac8  xor     r9d, r9d; unsigned int
0x14172aacb  mov     rdx, [rsp+268h+var_228]; struct IMessage *
0x14172aad0  mov     rax, [rsp+268h+var_208]
0x14172aad5  mov     rcx, [rax+30h]; this
0x14172aad9  call    ?HrPersistSave@ItemUIHost@@QEAAJPEAUIMessage@@PEAU_SPropTagArray@@K@Z; ItemUIHost::HrPersistSave(IMessage *,_SPropTagArray *,ulong)
0x14172aade  mov     edx, 1212A2h; unsigned int
0x14172aae3  mov     ecx, eax; int
0x14172aae5  call    ?CheckOleResultTagRaw@@YAJJK@Z; CheckOleResultTagRaw(long,ulong)
0x14172aaea  mov     eax, 1
0x14172aaef  mov     [rsp+268h+var_F8.cEntries], eax
0x14172aaf6  mov     [rsp+268h+var_F8.aEntries.cValues], 4
0x14172ab01  xor     edx, edx; void *
0x14172ab03  lea     ecx, [rax+5Fh]; unsigned __int64
0x14172ab06  call    ?MMemAllocNoThrow@@YAPEAX_KPEAX@Z; MMemAllocNoThrow(unsigned __int64,void *)
0x14172ab0b  mov     [rsp+268h+var_F8.aEntries.rgPropVals], rax
0x14172ab13  mov     dword ptr [rsp+268h+var_D8], 3001001Eh
0x14172ab1e  mov     [rsp+268h+var_C0], 3002001Eh
0x14172ab29  mov     dword ptr [rsp+268h+var_A8], 0FFF0102h
0x14172ab34  mov     [rsp+268h+var_90], 0C150003h
0x14172ab3f  mov     ecx, [rsp+268h+var_220]
0x14172ab43  mov     dword ptr [rsp+268h+var_88], ecx
0x14172ab4a  movaps  xmm0, [rsp+268h+var_D8]
0x14172ab52  movups  xmmword ptr [rax], xmm0
0x14172ab55  movaps  xmm1, xmmword ptr [rsp+1A0h]
0x14172ab5d  movups  xmmword ptr [rax+10h], xmm1
0x14172ab61  movaps  xmm0, [rsp+268h+var_B8]
0x14172ab69  movups  xmmword ptr [rax+20h], xmm0
0x14172ab6d  movaps  xmm1, [rsp+268h+var_A8]
0x14172ab75  movups  xmmword ptr [rax+30h], xmm1
0x14172ab79  movaps  xmm0, xmmword ptr [rsp+1D0h]
0x14172ab81  movups  xmmword ptr [rax+40h], xmm0
0x14172ab85  movaps  xmm1, [rsp+268h+var_88]
0x14172ab8d  movups  xmmword ptr [rax+50h], xmm1
0x14172ab91  mov     eax, r13d
0x14172ab94  lea     rbx, ?Release@MAPIValRef@@UEAAKXZ; MAPIValRef::Release(void)
0x14172ab9b  mov     [rsp+268h+var_220], eax
0x14172ab9f  mov     rcx, [rsp+268h+var_208]
0x14172aba4  mov     rdx, [rcx+28h]; struct IMAPISession *
0x14172aba8  mov     [rsp+268h+var_248], r13; struct _MAPIUID *
0x14172abad  mov     r9d, 8; unsigned int
0x14172abb3  cmp     eax, [rsp+268h+var_184]
0x14172abba  jge     loc_14172ACED
0x14172abc0  movsxd  rcx, eax
0x14172abc3  shl     rcx, 4
  ... truncated ...
```
