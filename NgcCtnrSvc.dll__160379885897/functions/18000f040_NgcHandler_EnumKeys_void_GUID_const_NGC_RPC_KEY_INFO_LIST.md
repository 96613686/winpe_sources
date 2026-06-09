# NgcHandler::EnumKeys(void *,_GUID const &,_NGC_RPC_KEY_INFO_LIST * *)

- ea: `0x18000f040`
- end: `0x18001025d`
- name: `?EnumKeys@NgcHandler@@QEAAJPEAXAEBU_GUID@@PEAPEAU_NGC_RPC_KEY_INFO_LIST@@@Z`
- size: `4637`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, void *, const struct _GUID *, struct _NGC_RPC_KEY_INFO_LIST **)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ef80`

## callees

- `0x1800061a4`
- `0x180006290`
- `0x180006330`
- `0x1800066d0`
- `0x18000c7e0`
- `0x18000d450`
- `0x18000f040`
- `0x180011020`
- `0x180016b98`
- `0x18001764c`
- `0x180018194`
- `0x18001e950`
- `0x180025634`
- `0x180029488`
- `0x18002c640`
- `0x18002cae0`
- `0x18002cdec`
- `0x18002d500`
- `0x18002d518`
- `0x1800347f0`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fcba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fcba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f9ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f9ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa40`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fcd4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fcd4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f15e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f252`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f365`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f43e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f588`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f691`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001001d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001014a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f15e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f252`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f365`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f43e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f588`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f691`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001001d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001014a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f089`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f089`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f170`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f280`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f493`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f737`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800101fd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f170`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f280`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f493`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f737`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800101fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f59f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f709`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010076`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800101cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f59f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f709`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010076`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800101cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall NgcHandler::EnumKeys(
        __int64 (__fastcall **this)(EVENT_DESCRIPTOR *, __int64 **),
        void *a2,
        EVENT_DESCRIPTOR *a3,
        struct _NGC_RPC_KEY_INFO_LIST **a4)
{
  HRESULT v6; // eax
  unsigned int v7; // edi
  bool v8; // r13
  int v10; // eax
  unsigned int v11; // ebx
  __int64 *v12; // rcx
  int v13; // eax
  int v14; // eax
  __int64 *v15; // rcx
  __int64 *v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  __int64 *v19; // rcx
  int v20; // eax
  int v21; // r15d
  _BYTE *v22; // rdi
  char *v23; // r14
  char *i; // rbx
  unsigned __int64 v25; // rdx
  _BYTE *v26; // rcx
  __int64 *v27; // rcx
  bool v28; // zf
  struct _EVENT_DATA_DESCRIPTOR *v29; // r14
  struct _EVENT_DATA_DESCRIPTOR *v30; // r13
  unsigned __int64 v31; // rbx
  size_t v32; // rbx
  _QWORD *v33; // rdi
  void *v34; // rax
  _QWORD *v35; // r9
  _QWORD *v36; // r8
  _QWORD *j; // rdx
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rax
  unsigned __int64 v41; // rdx
  void *v42; // rcx
  unsigned __int64 Ptr; // rdi
  struct _EVENT_DATA_DESCRIPTOR *v44; // r14
  unsigned __int64 v45; // rbx
  size_t v46; // rcx
  void *v47; // rax
  void *v48; // rcx
  void *v49; // rax
  void *v50; // rbx
  HANDLE ProcessHeap; // rax
  void *Keyword; // rbx
  HANDLE v53; // rax
  void *v54; // rbx
  HANDLE v55; // rax
  _QWORD *v56; // rbx
  signed __int64 v57; // rdi
  unsigned __int64 v58; // rcx
  unsigned __int64 v59; // rdx
  signed __int64 v60; // r12
  unsigned __int64 v61; // r15
  size_t v62; // r15
  char *v63; // r14
  void *v64; // rax
  __int64 v65; // rdi
  _QWORD *v66; // r8
  char *k; // rcx
  _QWORD *v68; // rdx
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  _QWORD *v75; // rdx
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  unsigned __int64 v79; // rdx
  void *v80; // rcx
  HANDLE v81; // rax
  _QWORD *v82; // rax
  _QWORD *v83; // rbx
  signed __int64 v84; // r14
  size_t v85; // r14
  char *v86; // rax
  char *v87; // rdi
  unsigned int v88; // r8d
  _BYTE *v89; // rdx
  _BYTE *m; // r9
  __int64 v91; // rcx
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  unsigned __int64 v95; // rdx
  void *v96; // rcx
  __int64 *v97; // rcx
  __int64 v98; // rcx
  __int64 *v99; // rcx
  unsigned __int64 v100; // rdx
  void *v101; // rcx
  __int64 *v102; // rcx
  unsigned int v103; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v104; // [rsp+34h] [rbp-CCh] BYREF
  __int64 *v105; // [rsp+38h] [rbp-C8h] BYREF
  void *v106[2]; // [rsp+40h] [rbp-C0h]
  char *v107; // [rsp+50h] [rbp-B0h]
  unsigned int v108; // [rsp+58h] [rbp-A8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  bool v111; // [rsp+78h] [rbp-88h]
  EVENT_DESCRIPTOR v112; // [rsp+80h] [rbp-80h] BYREF
  LPVOID lpMem[2]; // [rsp+90h] [rbp-70h]
  int v114; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v115; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int v116; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v117; // [rsp+ACh] [rbp-54h] BYREF
  _QWORD *v118; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v119; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v120; // [rsp+C0h] [rbp-40h] BYREF
  void *v121[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v122; // [rsp+D8h] [rbp-28h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+E0h] [rbp-20h] BYREF
  int *v124; // [rsp+F0h] [rbp-10h]
  __int64 v125; // [rsp+F8h] [rbp-8h]
  unsigned int *v126; // [rsp+100h] [rbp+0h]
  __int64 v127; // [rsp+108h] [rbp+8h]
  struct _EVENT_DATA_DESCRIPTOR v128; // [rsp+110h] [rbp+10h] BYREF
  char *v129; // [rsp+120h] [rbp+20h]
  int v130; // [rsp+128h] [rbp+28h]
  int v131; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v132; // [rsp+130h] [rbp+30h]
  __int64 v133; // [rsp+138h] [rbp+38h]
  __int64 *v134; // [rsp+140h] [rbp+40h]
  __int64 v135; // [rsp+148h] [rbp+48h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+150h] [rbp+50h]
  __int64 v137; // [rsp+158h] [rbp+58h]
  unsigned int *v138; // [rsp+160h] [rbp+60h]
  __int64 v139; // [rsp+168h] [rbp+68h]
  unsigned int *v140; // [rsp+170h] [rbp+70h]
  __int64 v141; // [rsp+178h] [rbp+78h]

  v119 = (__int64)a4;
  std::chrono::steady_clock::now(&v120);
  v6 = CoInitializeEx(0, 0);
  v7 = v6;
  v8 = v6 >= 0;
  v108 = v6 >= 0;
  v111 = v6 >= 0;
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v108 = v6;
      v126 = &v108;
      v127 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v124 = (int *)byte_1800AA575;
      v125 = 0x10000002FLL;
      v104 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    if ( v8 )
      CoUninitialize();
    return v7;
  }
  v105 = 0;
  v112 = *a3;
  v10 = (*this)(&v112, &v105);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v104 = v10;
      v126 = &v104;
      v127 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v124 = &dword_1800AA534;
      v125 = 0x100000035LL;
      v108 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    v12 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(__int64 *))(*v12 + 16))(v12);
    }
LABEL_12:
    if ( v8 )
      CoUninitialize();
    return v11;
  }
  v117 = 0;
  v116 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, unsigned int *))(*v105 + 72))(v105, &v117, &v116);
  if ( v13 < 0 && (unsigned int)dword_1800BE0B8 > 3 )
  {
    v104 = v13;
    v126 = &v104;
    v127 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 3;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_1800BE0C0;
    UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
    UserData.Reserved = 2;
    v124 = &dword_1800AA4CC;
    v125 = 0x100000024LL;
    v103 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  v114 = 0;
  v112 = (EVENT_DESCRIPTOR)xmmword_18008F2D8;
  v14 = (*(__int64 (__fastcall **)(__int64 *, EVENT_DESCRIPTOR *, int *))(*v105 + 88))(v105, &v112, &v114);
  v11 = v14;
  if ( v14 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 3 )
    {
      v103 = v14;
      v126 = &v103;
      v127 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 3;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v124 = (int *)&word_1800AA48E;
      v125 = 0x100000032LL;
      v104 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    v15 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
    }
    goto LABEL_12;
  }
  if ( !v114 )
  {
    v16 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
    }
    if ( v8 )
      CoUninitialize();
    return 2147942487LL;
  }
  pv = 0;
  v115 = 0;
  v17 = *v105;
  pv = 0;
  v112 = (EVENT_DESCRIPTOR)xmmword_18008F2D8;
  v18 = (*(__int64 (__fastcall **)(__int64 *, EVENT_DESCRIPTOR *, LPVOID *, unsigned int *))(v17 + 328))(
          v105,
          &v112,
          &pv,
          &v115);
  v11 = v18;
  if ( v18 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v103 = v18;
      v126 = &v103;
      v127 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v124 = &dword_1800AA4FC;
      v125 = 0x10000002CLL;
      v104 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    if ( pv )
      CoTaskMemFree(pv);
    v19 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
    }
    goto LABEL_12;
  }
  *(_OWORD *)v121 = 0;
  v122 = 0;
  v20 = NgcUtils::ConvertMultiStringToStringVector<std::allocator<unsigned short>>((__int64)pv, v115, v121);
  v21 = v20;
  if ( v20 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v103 = v20;
      v126 = &v103;
      v127 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v124 = (int *)&word_1800AA416;
      v125 = 0x100000036LL;
      v104 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    v22 = v121[0];
    if ( v121[0] )
    {
      v23 = (char *)v121[1];
      for ( i = (char *)v121[0]; i != v23; i += 32 )
        std::wstring::`scalar deleting destructor'(i);
      v25 = (v122 - (_QWORD)v22) & 0xFFFFFFFFFFFFFFE0uLL;
      if ( v25 < 0x1000 )
      {
        v26 = v22;
      }
      else
      {
        v26 = (_BYTE *)*((_QWORD *)v22 - 1);
        if ( (unsigned __int64)(v22 - v26 - 8) > 0x1F )
          __fastfail(5u);
        v25 += 39LL;
      }
      operator delete(v26, v25);
    }
    if ( pv )
      CoTaskMemFree(pv);
    v27 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
    }
    v28 = !v8;
LABEL_55:
    if ( !v28 )
      CoUninitialize();
    return (unsigned int)v21;
  }
  *(_OWORD *)v106 = 0;
  v107 = 0;
  v29 = (struct _EVENT_DATA_DESCRIPTOR *)v121[1];
  v30 = (struct _EVENT_DATA_DESCRIPTOR *)v121[0];
  v31 = ((char *)v121[1] - (char *)v121[0]) >> 5;
  if ( v31 )
  {
    if ( v31 > 0x7FFFFFFFFFFFFFFLL )
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Xlength();
    v32 = 32 * v31;
    if ( v32 )
    {
      if ( v32 < 0x1000 )
      {
        v33 = operator new(v32);
      }
      else
      {
        if ( v32 + 39 < v32 )
          std::_Throw_bad_array_new_length();
        v34 = operator new(v32 + 39);
        if ( !v34 )
          goto LABEL_73;
        v33 = (_QWORD *)(((unsigned __int64)v34 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v33 - 1) = v34;
      }
    }
    else
    {
      v33 = 0;
    }
    v35 = v106[1];
    v36 = v33;
    for ( j = v106[0]; j != v35; j += 4 )
    {
      v38 = *j;
      *j = 0;
      *v36 = v38;
      v39 = j[1];
      j[1] = 0;
      v36[1] = v39;
      v40 = j[2];
      j[2] = 0;
      v36[2] = v40;
      *((_DWORD *)v36 + 6) = *((_DWORD *)j + 6);
      *((_DWORD *)v36 + 7) = *((_DWORD *)j + 7);
      v36 += 4;
    }
    std::_Destroy_range<std::allocator<NgcRpcKeyInfo>>(v36, v36);
    if ( !v106[0] )
      goto LABEL_76;
    std::_Destroy_range<std::allocator<NgcRpcKeyInfo>>(v106[0], v106[1]);
    v41 = (v107 - (char *)v106[0]) & 0xFFFFFFFFFFFFFFE0uLL;
    if ( v41 < 0x1000 )
    {
      v42 = v106[0];
      goto LABEL_75;
    }
    v42 = (void *)*((_QWORD *)v106[0] - 1);
    if ( (unsigned __int64)((char *)v106[0] - (char *)v42 - 8) <= 0x1F )
    {
      v41 += 39LL;
LABEL_75:
      operator delete(v42, v41);
LABEL_76:
      v106[0] = v33;
      v106[1] = v33;
      v107 = (char *)&v33[v32 / 8];
      goto LABEL_77;
    }
LABEL_73:
    __fastfail(5u);
  }
LABEL_77:
  if ( v30 != v29 )
  {
    while ( 1 )
    {
      v112 = 0;
      lpMem[0] = 0;
      lpMem[1] = 0;
      UserData = 0;
      v124 = 0;
      v125 = 0;
      Ptr = v30[1].Ptr;
      if ( *(_QWORD *)&v30[1].Size <= 7u )
        v44 = v30;
      else
        v44 = (struct _EVENT_DATA_DESCRIPTOR *)v30->Ptr;
      if ( Ptr > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      if ( Ptr <= 7 )
      {
        v124 = (int *)v30[1].Ptr;
        v125 = 7;
        UserData = *v44;
        goto LABEL_97;
      }
      v45 = Ptr | 7;
      if ( (Ptr | 7) > 0x7FFFFFFFFFFFFFFELL )
        break;
      if ( v45 < 0xA )
        v45 = 10;
      if ( v45 + 1 > 0x7FFFFFFFFFFFFFFFLL )
LABEL_187:
        std::_Throw_bad_array_new_length();
      v46 = 2 * (v45 + 1);
      if ( v46 )
        goto LABEL_86;
      v49 = 0;
LABEL_96:
      UserData.Ptr = (ULONGLONG)v49;
      v124 = (int *)Ptr;
      v125 = v45;
      memcpy_0(v49, v44, 2 * Ptr + 2);
LABEL_97:
      v21 = NgcHandler::AllocateAndCopyKeyInfo(&v105, &UserData, &v112);
      v103 = v21;
      if ( v21 >= 0 )
      {
        v56 = v106[1];
        if ( v106[1] == v107 )
        {
          v57 = ((char *)v106[1] - (char *)v106[0]) >> 5;
          if ( v57 == 0x7FFFFFFFFFFFFFFLL )
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Xlength();
          v58 = (v107 - (char *)v106[0]) >> 5;
          v59 = v58 >> 1;
          if ( v58 > 0x7FFFFFFFFFFFFFFLL - (v58 >> 1) )
            goto LABEL_185;
          v60 = v57 + 1;
          v61 = v57 + 1;
          if ( v59 + v58 >= v57 + 1 )
            v61 = v59 + v58;
          if ( v61 > 0x7FFFFFFFFFFFFFFLL )
LABEL_185:
            std::_Throw_bad_array_new_length();
          v62 = 32 * v61;
          if ( v62 )
          {
            if ( v62 < 0x1000 )
            {
              v63 = (char *)operator new(v62);
            }
            else
            {
              if ( v62 + 39 < v62 )
                goto LABEL_185;
              v64 = operator new(v62 + 39);
              if ( !v64 )
LABEL_140:
                __fastfail(5u);
              v63 = (char *)(((unsigned __int64)v64 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *((_QWORD *)v63 - 1) = v64;
            }
          }
          else
          {
            v63 = 0;
          }
          v65 = 32 * v57;
          *(EVENT_DESCRIPTOR *)&v63[v65] = v112;
          *(_OWORD *)&v63[v65 + 16] = *(_OWORD *)lpMem;
          v66 = v106[1];
          k = v63;
          v68 = v106[0];
          if ( v56 == v106[1] )
          {
            if ( v106[0] != v106[1] )
            {
              do
              {
                v69 = *v68;
                *v68 = 0;
                *(_QWORD *)k = v69;
                v70 = v68[1];
                v68[1] = 0;
                *((_QWORD *)k + 1) = v70;
                v71 = v68[2];
                v68[2] = 0;
                *((_QWORD *)k + 2) = v71;
                *((_DWORD *)k + 6) = *((_DWORD *)v68 + 6);
                *((_DWORD *)k + 7) = *((_DWORD *)v68 + 7);
                k += 32;
                v68 += 4;
              }
              while ( v68 != v66 );
            }
          }
          else
          {
            if ( v106[0] != v56 )
            {
              do
              {
                v72 = *v68;
                *v68 = 0;
                *(_QWORD *)k = v72;
                v73 = v68[1];
                v68[1] = 0;
                *((_QWORD *)k + 1) = v73;
                v74 = v68[2];
                v68[2] = 0;
                *((_QWORD *)k + 2) = v74;
                *((_DWORD *)k + 6) = *((_DWORD *)v68 + 6);
                *((_DWORD *)k + 7) = *((_DWORD *)v68 + 7);
                k += 32;
                v68 += 4;
              }
              while ( v68 != v56 );
            }
            std::_Destroy_range<std::allocator<NgcRpcKeyInfo>>(k, k);
            v75 = v106[1];
            for ( k = &v63[v65 + 32]; v56 != v75; v56 += 4 )
            {
              v76 = *v56;
              *v56 = 0;
              *(_QWORD *)k = v76;
              v77 = v56[1];
              v56[1] = 0;
              *((_QWORD *)k + 1) = v77;
              v78 = v56[2];
              v56[2] = 0;
              *((_QWORD *)k + 2) = v78;
              *((_DWORD *)k + 6) = *((_DWORD *)v56 + 6);
              *((_DWORD *)k + 7) = *((_DWORD *)v56 + 7);
              k += 32;
            }
          }
          std::_Destroy_range<std::allocator<NgcRpcKeyInfo>>(k, k);
          if ( v106[0] )
          {
            std::_Destroy_range<std::allocator<NgcRpcKeyInfo>>(v106[0], v106[1]);
            v79 = (v107 - (char *)v106[0]) & 0xFFFFFFFFFFFFFFE0uLL;
            if ( v79 < 0x1000 )
            {
              v80 = v106[0];
            }
            else
            {
              v80 = (void *)*((_QWORD *)v106[0] - 1);
              if ( (unsigned __int64)((char *)v106[0] - (char *)v80 - 8) > 0x1F )
                goto LABEL_140;
              v79 += 39LL;
            }
            operator delete(v80, v79);
          }
          v106[0] = v63;
          v106[1] = &v63[32 * v60];
          v107 = &v63[v62];
          v21 = v103;
        }
        else
        {
          *(EVENT_DESCRIPTOR *)v106[1] = v112;
          *((_OWORD *)v56 + 1) = *(_OWORD *)lpMem;
          v106[1] = (char *)v106[1] + 32;
        }
      }
      else
      {
        v21 = 0;
        v50 = lpMem[0];
        if ( lpMem[0] )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v50);
        }
        Keyword = (void *)v112.Keyword;
        if ( v112.Keyword )
        {
          v53 = GetProcessHeap();
          HeapFree(v53, 0, Keyword);
        }
        v54 = *(void **)&v112.Id;
        if ( *(_QWORD *)&v112.Id )
        {
          v55 = GetProcessHeap();
          HeapFree(v55, 0, v54);
        }
      }
      v30 += 2;
      if ( v30 == v121[1] )
        goto LABEL_134;
    }
    v45 = 0x7FFFFFFFFFFFFFFELL;
    v46 = -2;
LABEL_86:
    if ( v46 < 0x1000 )
    {
      v49 = operator new(v46);
    }
    else
    {
      if ( v46 + 39 < v46 )
        goto LABEL_187;
      v47 = operator new(v46 + 39);
      v48 = v47;
      if ( !v47 )
        goto LABEL_140;
      v49 = (void *)(((unsigned __int64)v47 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *((_QWORD *)v49 - 1) = v48;
    }
    goto LABEL_96;
  }
LABEL_134:
  v81 = GetProcessHeap();
  v82 = HeapAlloc(v81, 8u, 0x10u);
  v83 = v82;
  v118 = v82;
  if ( !v82 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v118) = -2147024882;
      v126 = (unsigned int *)&v118;
      v127 = 4;
      *(_DWORD *)&v112.Id = 184549376;
      *(_DWORD *)&v112.Level = 2;
      v112.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v124 = (int *)&unk_1800AA458;
      v125 = 0x10000002ALL;
      v103 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v112, 0, 0, 3u, &UserData);
    }
    if ( v106[0] )
    {
      std::_Destroy_range<std::allocator<NgcRpcKeyInfo>>(v106[0], v106[1]);
      v100 = (v107 - (char *)v106[0]) & 0xFFFFFFFFFFFFFFE0uLL;
      if ( v100 < 0x1000 )
      {
        v101 = v106[0];
      }
      else
      {
        v101 = (void *)*((_QWORD *)v106[0] - 1);
        if ( (unsigned __int64)((char *)v106[0] - (char *)v101 - 8) > 0x1F )
          goto LABEL_172;
        v100 += 39LL;
      }
      operator delete(v101, v100);
      *(_OWORD *)v106 = 0;
      v107 = 0;
    }
    std::vector<std::wstring>::_Tidy(v121);
    if ( pv )
      CoTaskMemFree(pv);
    v102 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(__int64 *))(*v102 + 16))(v102);
    }
    goto LABEL_179;
  }
  v84 = ((char *)v106[1] - (char *)v106[0]) >> 5;
  if ( !v84 )
  {
    *(_DWORD *)v82 = 0;
    v82[1] = 0;
LABEL_155:
    *(_QWORD *)v119 = v83;
    std::chrono::steady_clock::now(&v119);
    if ( (unsigned int)dword_1800BE0B8 > 5
      && (qword_1800BE0C8 & 0x400000000000LL) != 0
      && (qword_1800BE0D0 & 0x400000000000LL) == qword_1800BE0D0 )
    {
      v103 = v116;
      v104 = v117;
      *(_QWORD *)&EventDescriptor.Id = ((char *)v106[1] - (char *)v106[0]) >> 5;
      v120 = (v119 - v120) / 1000000;
      v119 = 0x1000000;
      v140 = &v103;
      v141 = 4;
      v138 = &v104;
      v139 = 4;
      p_EventDescriptor = &EventDescriptor;
      v137 = 8;
      v134 = &v120;
      v135 = 8;
      v132 = &v119;
      v133 = 8;
      *(_DWORD *)&v112.Id = 184549376;
      *(_DWORD *)&v112.Level = 5;
      v112.Keyword = 0x400000000000LL;
      v128.Ptr = (ULONGLONG)off_1800BE0C0;
      v128.Size = *(unsigned __int16 *)off_1800BE0C0;
      v128.Reserved = 2;
      v129 = byte_1800AA3C1;
      v130 = 73;
      v131 = 1;
      LODWORD(v118) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v112, 0, 0, 7u, &v128);
    }
    if ( v106[0] )
    {
      std::_Destroy_range<std::allocator<NgcRpcKeyInfo>>(v106[0], v106[1]);
      std::allocator<NgcRpcKeyInfo>::deallocate(v98, v106[0], (v107 - (char *)v106[0]) >> 5);
      *(_OWORD *)v106 = 0;
      v107 = 0;
    }
    std::vector<std::wstring>::~vector<std::wstring>(v121);
    if ( pv )
      CoTaskMemFree(pv);
    v99 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(__int64 *))(*v99 + 16))(v99);
    }
    v28 = (_BYTE)v108 == 0;
    goto LABEL_55;
  }
  v85 = 32 * v84;
  v86 = (char *)MIDL_user_allocate(v85);
  v87 = v86;
  if ( v86 )
  {
    memset_0(v86, 0, v85);
    v88 = 0;
    v89 = v106[1];
    for ( m = v106[0]; v88 < (unsigned __int64)(((char *)v106[1] - (char *)v106[0]) >> 5); m = v106[0] )
    {
      v91 = 32LL * v88;
      v92 = *(_QWORD *)&m[v91];
      *(_QWORD *)&m[v91] = 0;
      *(_QWORD *)&v87[v91] = v92;
      v93 = *(_QWORD *)&m[v91 + 8];
      *(_QWORD *)&m[v91 + 8] = 0;
      *(_QWORD *)&v87[v91 + 8] = v93;
      v94 = *(_QWORD *)&m[v91 + 16];
      *(_QWORD *)&m[v91 + 16] = 0;
      *(_QWORD *)&v87[v91 + 16] = v94;
      *(_DWORD *)&v87[v91 + 24] = *(_DWORD *)&m[v91 + 24];
      *(_DWORD *)&v87[v91 + 28] = *(_DWORD *)&m[v91 + 28];
      ++v88;
      v89 = v106[1];
    }
    *(_DWORD *)v83 = (v89 - m) >> 5;
    v83[1] = v87;
    goto LABEL_155;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    v103 = -2147024882;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)&word_1800AA37E,
      0,
      0,
      (__int64)&v103);
  }
  std::unique_ptr<unsigned char,rpcmem_delete<unsigned char>>::~unique_ptr<unsigned char,rpcmem_delete<unsigned char>>(&v118);
  if ( !v106[0] )
    goto LABEL_149;
  std::_Destroy_range<std::allocator<NgcRpcKeyInfo>>(v106[0], v106[1]);
  v95 = (v107 - (char *)v106[0]) & 0xFFFFFFFFFFFFFFE0uLL;
  if ( v95 < 0x1000 )
  {
    v96 = v106[0];
    goto LABEL_148;
  }
  v96 = (void *)*((_QWORD *)v106[0] - 1);
  if ( (unsigned __int64)((char *)v106[0] - (char *)v96 - 8) > 0x1F )
LABEL_172:
    __fastfail(5u);
  v95 += 39LL;
LABEL_148:
  operator delete(v96, v95);
  *(_OWORD *)v106 = 0;
  v107 = 0;
LABEL_149:
  std::vector<std::wstring>::_Tidy(v121);
  if ( pv )
    CoTaskMemFree(pv);
  v97 = v105;
  if ( v105 )
  {
    v105 = 0;
    (*(void (__fastcall **)(__int64 *))(*v97 + 16))(v97);
  }
LABEL_179:
  if ( (_BYTE)v108 )
    CoUninitialize();
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000f040  mov     [rsp-8+arg_8], rbx
0x18000f045  push    rbp
0x18000f046  push    rsi
0x18000f047  push    rdi
0x18000f048  push    r12
0x18000f04a  push    r13
0x18000f04c  push    r14
0x18000f04e  push    r15
0x18000f050  lea     rbp, [rsp-90h]
0x18000f058  sub     rsp, 190h
0x18000f05f  mov     rax, cs:__security_cookie
0x18000f066  xor     rax, rsp
0x18000f069  mov     [rbp+0C0h+var_40], rax
0x18000f070  mov     [rbp+0C0h+var_108], r9
0x18000f074  mov     r15, r8
0x18000f077  mov     r14, rcx
0x18000f07a  lea     rcx, [rbp+0C0h+var_100]
0x18000f07e  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18000f083  xor     bl, bl
0x18000f085  xor     edx, edx; dwCoInit
0x18000f087  xor     ecx, ecx; pvReserved
0x18000f089  call    cs:__imp_CoInitializeEx
0x18000f090  nop     dword ptr [rax+rax+00h]
0x18000f095  mov     edi, eax
0x18000f097  movzx   r13d, bl
0x18000f09b  mov     r12d, 1
0x18000f0a1  test    eax, eax
0x18000f0a3  cmovns  r13d, r12d
0x18000f0a7  mov     [rsp+1C0h+var_168], r13d
0x18000f0ac  mov     [rsp+1C0h+var_148], r13b
0x18000f0b1  jns     loc_18000F183
0x18000f0b7  mov     ecx, cs:dword_1800BE0B8
0x18000f0bd  cmp     ecx, 2
0x18000f0c0  jbe     loc_18000F16B
0x18000f0c6  mov     [rsp+1C0h+var_168], eax
0x18000f0ca  lea     rax, [rsp+1C0h+var_168]
0x18000f0cf  mov     [rbp+0C0h+var_C0], rax
0x18000f0d3  mov     [rbp+0C0h+var_B8], 4
0x18000f0db  xor     esi, esi
0x18000f0dd  mov     dword ptr [rsp+1C0h+EventDescriptor.Id], 0B000000h
0x18000f0e5  movzx   eax, cs:word_1800AA56B
0x18000f0ec  mov     dword ptr [rsp+1C0h+EventDescriptor.Level], eax
0x18000f0f0  mov     [rsp+1C0h+EventDescriptor.Keyword], rsi
0x18000f0f5  mov     rax, cs:off_1800BE0C0
0x18000f0fc  mov     [rbp+0C0h+var_E0.Ptr], rax
0x18000f100  movzx   eax, word ptr [rax]
0x18000f103  mov     [rbp+0C0h+var_E0.Size], eax
0x18000f106  mov     dword ptr [rbp+0C0h+var_E0.0Ch], 2
0x18000f10d  lea     rax, byte_1800AA575
0x18000f114  mov     [rbp+0C0h+var_D0], rax
0x18000f118  mov     dword ptr [rbp+0C0h+var_C8], 2Fh ; '/'
0x18000f11f  mov     dword ptr [rbp+0C0h+var_C8+4], r12d
0x18000f123  lea     rax, _TraceLoggingMetadataEnd
0x18000f12a  lea     rcx, _TraceLoggingMetadata
0x18000f131  sub     eax, ecx
0x18000f133  mov     [rsp+1C0h+var_18C], eax
0x18000f137  mov     eax, [rsp+1C0h+var_18C]
0x18000f13b  lea     rax, [rbp+0C0h+var_E0]
0x18000f13f  mov     [rsp+1C0h+UserData], rax; UserData
0x18000f144  mov     [rsp+1C0h+UserDataCount], 3; UserDataCount
0x18000f14c  xor     r9d, r9d; RelatedActivityId
0x18000f14f  xor     r8d, r8d; ActivityId
0x18000f152  lea     rdx, [rsp+1C0h+EventDescriptor]; EventDescriptor
0x18000f157  mov     rcx, cs:RegHandle; RegHandle
0x18000f15e  call    cs:__imp_EventWriteTransfer
0x18000f165  nop     dword ptr [rax+rax+00h]
0x18000f16a  nop
0x18000f16b  test    r13b, r13b
0x18000f16e  jz      short loc_18000F17C
0x18000f170  call    cs:__imp_CoUninitialize
0x18000f177  nop     dword ptr [rax+rax+00h]
0x18000f17c  mov     eax, edi
0x18000f17e  jmp     loc_18001020E
0x18000f183  xor     esi, esi
0x18000f185  mov     [rsp+1C0h+var_188], rsi
0x18000f18a  movups  xmm0, xmmword ptr [r15]
0x18000f18e  movaps  xmmword ptr [rbp+0C0h+var_140.Id], xmm0
0x18000f192  lea     rdx, [rsp+1C0h+var_188]
0x18000f197  lea     rcx, [rbp+0C0h+var_140]
0x18000f19b  mov     rax, [r14]
0x18000f19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1a3  mov     ebx, eax
0x18000f1a5  test    eax, eax
0x18000f1a7  jns     loc_18000F293
0x18000f1ad  mov     ecx, cs:dword_1800BE0B8
0x18000f1b3  cmp     ecx, 2
0x18000f1b6  jbe     loc_18000F25F
0x18000f1bc  mov     [rsp+1C0h+var_18C], eax
0x18000f1c0  lea     rax, [rsp+1C0h+var_18C]
0x18000f1c5  mov     [rbp+0C0h+var_C0], rax
0x18000f1c9  mov     [rbp+0C0h+var_B8], 4
0x18000f1d1  mov     dword ptr [rsp+1C0h+EventDescriptor.Id], 0B000000h
0x18000f1d9  movzx   eax, cs:word_1800AA52A
0x18000f1e0  mov     dword ptr [rsp+1C0h+EventDescriptor.Level], eax
0x18000f1e4  mov     [rsp+1C0h+EventDescriptor.Keyword], rsi
0x18000f1e9  mov     rax, cs:off_1800BE0C0
0x18000f1f0  mov     [rbp+0C0h+var_E0.Ptr], rax
0x18000f1f4  movzx   eax, word ptr [rax]
0x18000f1f7  mov     [rbp+0C0h+var_E0.Size], eax
0x18000f1fa  mov     dword ptr [rbp+0C0h+var_E0.0Ch], 2
0x18000f201  lea     rax, dword_1800AA534
0x18000f208  mov     [rbp+0C0h+var_D0], rax
0x18000f20c  mov     dword ptr [rbp+0C0h+var_C8], 35h ; '5'
0x18000f213  mov     dword ptr [rbp+0C0h+var_C8+4], r12d
0x18000f217  lea     rax, _TraceLoggingMetadataEnd
0x18000f21e  lea     rcx, _TraceLoggingMetadata
0x18000f225  sub     eax, ecx
0x18000f227  mov     [rsp+1C0h+var_168], eax
0x18000f22b  mov     eax, [rsp+1C0h+var_168]
0x18000f22f  lea     rax, [rbp+0C0h+var_E0]
0x18000f233  mov     [rsp+1C0h+UserData], rax; UserData
0x18000f238  mov     [rsp+1C0h+UserDataCount], 3; UserDataCount
0x18000f240  xor     r9d, r9d; RelatedActivityId
0x18000f243  xor     r8d, r8d; ActivityId
0x18000f246  lea     rdx, [rsp+1C0h+EventDescriptor]; EventDescriptor
0x18000f24b  mov     rcx, cs:RegHandle; RegHandle
0x18000f252  call    cs:__imp_EventWriteTransfer
0x18000f259  nop     dword ptr [rax+rax+00h]
0x18000f25e  nop
0x18000f25f  mov     rcx, [rsp+1C0h+var_188]
0x18000f264  test    rcx, rcx
0x18000f267  jz      short loc_18000F27B
0x18000f269  mov     [rsp+1C0h+var_188], rsi
0x18000f26e  mov     rax, [rcx]
0x18000f271  mov     rax, [rax+10h]
0x18000f275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f27a  nop
0x18000f27b  test    r13b, r13b
0x18000f27e  jz      short loc_18000F28C
0x18000f280  call    cs:__imp_CoUninitialize
0x18000f287  nop     dword ptr [rax+rax+00h]
0x18000f28c  mov     eax, ebx
0x18000f28e  jmp     loc_18001020E
0x18000f293  mov     [rbp+0C0h+var_114], esi
0x18000f296  mov     [rbp+0C0h+var_118], esi
0x18000f299  mov     rcx, [rsp+1C0h+var_188]
0x18000f29e  mov     rax, [rcx]
0x18000f2a1  lea     r8, [rbp+0C0h+var_118]
0x18000f2a5  lea     rdx, [rbp+0C0h+var_114]
0x18000f2a9  mov     rax, [rax+48h]
0x18000f2ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2b2  lea     r12, _TraceLoggingMetadataEnd
0x18000f2b9  lea     rdi, _TraceLoggingMetadata
0x18000f2c0  test    eax, eax
0x18000f2c2  jns     loc_18000F371
0x18000f2c8  mov     ecx, cs:dword_1800BE0B8
0x18000f2ce  cmp     ecx, 3
0x18000f2d1  jbe     loc_18000F371
0x18000f2d7  mov     [rsp+1C0h+var_18C], eax
0x18000f2db  lea     rax, [rsp+1C0h+var_18C]
0x18000f2e0  mov     [rbp+0C0h+var_C0], rax
0x18000f2e4  mov     [rbp+0C0h+var_B8], 4
0x18000f2ec  mov     dword ptr [rsp+1C0h+EventDescriptor.Id], 0B000000h
0x18000f2f4  movzx   eax, cs:word_1800AA4C2
0x18000f2fb  mov     dword ptr [rsp+1C0h+EventDescriptor.Level], eax
0x18000f2ff  mov     [rsp+1C0h+EventDescriptor.Keyword], rsi
0x18000f304  mov     rax, cs:off_1800BE0C0
0x18000f30b  mov     [rbp+0C0h+var_E0.Ptr], rax
0x18000f30f  movzx   eax, word ptr [rax]
0x18000f312  mov     [rbp+0C0h+var_E0.Size], eax
0x18000f315  mov     dword ptr [rbp+0C0h+var_E0.0Ch], 2
0x18000f31c  lea     rax, dword_1800AA4CC
0x18000f323  mov     [rbp+0C0h+var_D0], rax
0x18000f327  mov     dword ptr [rbp+0C0h+var_C8], 24h ; '$'
0x18000f32e  mov     dword ptr [rbp+0C0h+var_C8+4], 1
0x18000f335  mov     rax, r12
0x18000f338  sub     eax, edi
0x18000f33a  mov     [rsp+1C0h+var_190], eax
0x18000f33e  mov     eax, [rsp+1C0h+var_190]
0x18000f342  lea     rax, [rbp+0C0h+var_E0]
0x18000f346  mov     [rsp+1C0h+UserData], rax; UserData
0x18000f34b  mov     [rsp+1C0h+UserDataCount], 3; UserDataCount
0x18000f353  xor     r9d, r9d; RelatedActivityId
0x18000f356  xor     r8d, r8d; ActivityId
0x18000f359  lea     rdx, [rsp+1C0h+EventDescriptor]; EventDescriptor
0x18000f35e  mov     rcx, cs:RegHandle; RegHandle
0x18000f365  call    cs:__imp_EventWriteTransfer
0x18000f36c  nop     dword ptr [rax+rax+00h]
0x18000f371  mov     [rbp+0C0h+var_120], esi
0x18000f374  mov     rcx, [rsp+1C0h+var_188]
0x18000f379  movups  xmm0, cs:xmmword_18008F2D8
0x18000f380  movaps  xmmword ptr [rbp+0C0h+var_140.Id], xmm0
0x18000f384  mov     rax, [rcx]
0x18000f387  lea     r8, [rbp+0C0h+var_120]
0x18000f38b  lea     rdx, [rbp+0C0h+var_140]
0x18000f38f  mov     rax, [rax+58h]
0x18000f393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f398  mov     ebx, eax
0x18000f39a  test    eax, eax
0x18000f39c  jns     loc_18000F46C
0x18000f3a2  mov     ecx, cs:dword_1800BE0B8
0x18000f3a8  cmp     ecx, 3
0x18000f3ab  jbe     loc_18000F44B
0x18000f3b1  mov     [rsp+1C0h+var_190], eax
0x18000f3b5  lea     rax, [rsp+1C0h+var_190]
0x18000f3ba  mov     [rbp+0C0h+var_C0], rax
0x18000f3be  mov     [rbp+0C0h+var_B8], 4
0x18000f3c6  mov     dword ptr [rsp+1C0h+EventDescriptor.Id], 0B000000h
0x18000f3ce  movzx   eax, cs:word_1800AA484
0x18000f3d5  mov     dword ptr [rsp+1C0h+EventDescriptor.Level], eax
0x18000f3d9  mov     [rsp+1C0h+EventDescriptor.Keyword], rsi
0x18000f3de  mov     rax, cs:off_1800BE0C0
0x18000f3e5  mov     [rbp+0C0h+var_E0.Ptr], rax
0x18000f3e9  movzx   eax, word ptr [rax]
0x18000f3ec  mov     [rbp+0C0h+var_E0.Size], eax
0x18000f3ef  mov     dword ptr [rbp+0C0h+var_E0.0Ch], 2
0x18000f3f6  lea     rax, word_1800AA48E
0x18000f3fd  mov     [rbp+0C0h+var_D0], rax
0x18000f401  mov     dword ptr [rbp+0C0h+var_C8], 32h ; '2'
0x18000f408  mov     dword ptr [rbp+0C0h+var_C8+4], 1
0x18000f40f  sub     r12d, edi
0x18000f412  mov     [rsp+1C0h+var_18C], r12d
0x18000f417  mov     eax, [rsp+1C0h+var_18C]
0x18000f41b  lea     rax, [rbp+0C0h+var_E0]
0x18000f41f  mov     [rsp+1C0h+UserData], rax; UserData
0x18000f424  mov     [rsp+1C0h+UserDataCount], 3; UserDataCount
0x18000f42c  xor     r9d, r9d; RelatedActivityId
0x18000f42f  xor     r8d, r8d; ActivityId
0x18000f432  lea     rdx, [rsp+1C0h+EventDescriptor]; EventDescriptor
0x18000f437  mov     rcx, cs:RegHandle; RegHandle
0x18000f43e  call    cs:__imp_EventWriteTransfer
0x18000f445  nop     dword ptr [rax+rax+00h]
0x18000f44a  nop
0x18000f44b  mov     rcx, [rsp+1C0h+var_188]
0x18000f450  test    rcx, rcx
0x18000f453  jz      short loc_18000F467
0x18000f455  mov     [rsp+1C0h+var_188], rsi
0x18000f45a  mov     rax, [rcx]
0x18000f45d  mov     rax, [rax+10h]
0x18000f461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f466  nop
0x18000f467  jmp     loc_18000F27B
0x18000f46c  cmp     [rbp+0C0h+var_120], 0
0x18000f470  jnz     short loc_18000F4A9
0x18000f472  mov     rcx, [rsp+1C0h+var_188]
0x18000f477  test    rcx, rcx
0x18000f47a  jz      short loc_18000F48E
0x18000f47c  mov     [rsp+1C0h+var_188], rsi
0x18000f481  mov     rax, [rcx]
0x18000f484  mov     rax, [rax+10h]
0x18000f488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f48d  nop
0x18000f48e  test    r13b, r13b
0x18000f491  jz      short loc_18000F49F
0x18000f493  call    cs:__imp_CoUninitialize
0x18000f49a  nop     dword ptr [rax+rax+00h]
0x18000f49f  mov     eax, 80070057h
0x18000f4a4  jmp     loc_18001020E
0x18000f4a9  mov     [rsp+1C0h+pv], rsi
0x18000f4ae  mov     [rbp+0C0h+var_11C], esi
0x18000f4b1  mov     rcx, [rsp+1C0h+var_188]
0x18000f4b6  mov     rax, [rcx]
0x18000f4b9  mov     [rsp+1C0h+pv], rsi
0x18000f4be  movups  xmm0, cs:xmmword_18008F2D8
0x18000f4c5  movaps  xmmword ptr [rbp+0C0h+var_140.Id], xmm0
0x18000f4c9  lea     r9, [rbp+0C0h+var_11C]
0x18000f4cd  lea     r8, [rsp+1C0h+pv]
0x18000f4d2  lea     rdx, [rbp+0C0h+var_140]
0x18000f4d6  mov     rax, [rax+148h]
0x18000f4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4e2  mov     ebx, eax
0x18000f4e4  test    eax, eax
0x18000f4e6  jns     loc_18000F5CD
0x18000f4ec  mov     ecx, cs:dword_1800BE0B8
0x18000f4f2  cmp     ecx, 2
0x18000f4f5  jbe     loc_18000F595
0x18000f4fb  mov     [rsp+1C0h+var_190], eax
0x18000f4ff  lea     rax, [rsp+1C0h+var_190]
0x18000f504  mov     [rbp+0C0h+var_C0], rax
0x18000f508  mov     [rbp+0C0h+var_B8], 4
0x18000f510  mov     dword ptr [rsp+1C0h+EventDescriptor.Id], 0B000000h
0x18000f518  movzx   eax, cs:word_1800AA4F2
0x18000f51f  mov     dword ptr [rsp+1C0h+EventDescriptor.Level], eax
0x18000f523  mov     [rsp+1C0h+EventDescriptor.Keyword], rsi
0x18000f528  mov     rax, cs:off_1800BE0C0
0x18000f52f  mov     [rbp+0C0h+var_E0.Ptr], rax
0x18000f533  movzx   eax, word ptr [rax]
0x18000f536  mov     [rbp+0C0h+var_E0.Size], eax
0x18000f539  mov     dword ptr [rbp+0C0h+var_E0.0Ch], 2
0x18000f540  lea     rax, dword_1800AA4FC
0x18000f547  mov     [rbp+0C0h+var_D0], rax
0x18000f54b  mov     dword ptr [rbp+0C0h+var_C8], 2Ch ; ','
0x18000f552  mov     dword ptr [rbp+0C0h+var_C8+4], 1
0x18000f559  sub     r12d, edi
0x18000f55c  mov     [rsp+1C0h+var_18C], r12d
0x18000f561  mov     eax, [rsp+1C0h+var_18C]
0x18000f565  lea     rax, [rbp+0C0h+var_E0]
0x18000f569  mov     [rsp+1C0h+UserData], rax; UserData
0x18000f56e  mov     [rsp+1C0h+UserDataCount], 3; UserDataCount
0x18000f576  xor     r9d, r9d; RelatedActivityId
0x18000f579  xor     r8d, r8d; ActivityId
0x18000f57c  lea     rdx, [rsp+1C0h+EventDescriptor]; EventDescriptor
0x18000f581  mov     rcx, cs:RegHandle; RegHandle
0x18000f588  call    cs:__imp_EventWriteTransfer
0x18000f58f  nop     dword ptr [rax+rax+00h]
0x18000f594  nop
0x18000f595  mov     rcx, [rsp+1C0h+pv]; pv
0x18000f59a  test    rcx, rcx
0x18000f59d  jz      short loc_18000F5AC
0x18000f59f  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
