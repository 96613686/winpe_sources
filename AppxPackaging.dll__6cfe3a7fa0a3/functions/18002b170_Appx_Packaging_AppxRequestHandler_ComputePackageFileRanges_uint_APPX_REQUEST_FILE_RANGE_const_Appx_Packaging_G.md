# Appx::Packaging::AppxRequestHandler::ComputePackageFileRanges(uint,APPX_REQUEST_FILE_RANGE const *,Appx::Packaging::GenericList<Appx::Packaging::FileBlockRange> &,bool,uint *,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003 * *)

- ea: `0x18002b170`
- end: `0x18002bbc8`
- name: `?ComputePackageFileRanges@AppxRequestHandler@Packaging@Appx@@AEAAJIPEBUAPPX_REQUEST_FILE_RANGE@@AEAV?$GenericList@UFileBlockRange@Packaging@Appx@@@23@_NPEAIPEAPEAU__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@@Z`
- size: `2648`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, void *, __int64, void (__fastcall *)(__int64), _QWORD *)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a8f0`
- `0x1800771e0`
- `0x180077eb0`

## callees

- `0x180005eb8`
- `0x180006f24`
- `0x1800133fc`
- `0x18002a224`
- `0x18002b170`
- `0x18002bbd0`
- `0x18002c8c0`
- `0x18002c8fc`
- `0x18002cf44`
- `0x1800992a0`
- `0x18009d3d0`
- `0x180106010`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b45c`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b559`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b5be`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b623`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b684`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b6e9`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b74a`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b7ab`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b80c`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b86d`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b45c`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b559`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b5be`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b623`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b684`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b6e9`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b74a`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b7ab`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b80c`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002b86d`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18002b215`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18002b215`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b439`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b536`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b59b`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b600`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b661`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b6c6`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b727`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b788`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b7e9`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b84a`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b439`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b536`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b59b`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b600`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b661`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b6c6`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b727`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b788`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b7e9`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002b84a`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002b274`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002b274`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::AppxRequestHandler::ComputePackageFileRanges(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        void *a4,
        __int64 a5,
        void (__fastcall *a6)(__int64),
        _QWORD *a7)
{
  void (__fastcall *v7)(__int64); // r14
  int v8; // r12d
  unsigned int v10; // ebx
  __int64 v11; // rdi
  unsigned int v12; // r13d
  __int64 v13; // rcx
  _QWORD *v14; // rax
  char v15; // al
  int FileBlockRangeForByteRange; // eax
  unsigned int v17; // ebx
  __int64 v18; // rsi
  unsigned __int64 i; // rbx
  __int64 v20; // r8
  int v21; // eax
  int v22; // edi
  void (__fastcall *v23)(__int64); // rcx
  int v25; // esi
  __int64 *v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rdi
  __int64 v29; // r8
  int v30; // eax
  unsigned __int64 j; // rbx
  int v32; // eax
  __int64 *v33; // rax
  __int64 v34; // rdi
  __int64 v35; // rsi
  __int64 *v36; // rax
  __int64 v37; // rdi
  __int64 v38; // rsi
  __int64 *v39; // rax
  __int64 v40; // rbx
  __int64 v41; // rsi
  __int64 *v42; // rax
  __int64 v43; // rdi
  __int64 v44; // rsi
  __int64 *v45; // rax
  __int64 v46; // rdi
  __int64 v47; // rsi
  __int64 *v48; // rax
  __int64 v49; // rbx
  __int64 v50; // rsi
  __int64 *v51; // rax
  __int64 v52; // rdi
  __int64 v53; // rsi
  __int64 *v54; // rax
  __int64 v55; // rbx
  __int64 v56; // rdi
  __int64 *v57; // rax
  __int64 v58; // rbx
  __int64 v59; // rdi
  __int64 v60; // rdi
  __int64 (__fastcall *v61)(__int64, _QWORD, _QWORD); // rbx
  int v62; // eax
  __int64 (__fastcall ***v63)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v64)(_QWORD, GUID *, __int64 *); // rdi
  int v65; // eax
  unsigned int v66; // r12d
  int v67; // eax
  unsigned __int64 v68; // rbx
  unsigned __int64 v69; // rax
  _OWORD *v70; // rax
  unsigned __int64 v71; // rdx
  __int64 v72; // r9
  bool v73; // cf
  void (__fastcall *v74)(__int64); // r8
  unsigned __int64 v75; // rcx
  int TableContext; // [rsp+20h] [rbp-E0h]
  char v77; // [rsp+40h] [rbp-C0h]
  PVOID RestartKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v79)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  char v80; // [rsp+58h] [rbp-A8h] BYREF
  int v81; // [rsp+59h] [rbp-A7h]
  __int16 v82; // [rsp+5Dh] [rbp-A3h]
  char v83; // [rsp+5Fh] [rbp-A1h]
  void (__fastcall *v84)(__int64); // [rsp+60h] [rbp-A0h]
  __int64 v85; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v86; // [rsp+70h] [rbp-90h]
  _QWORD v87[2]; // [rsp+78h] [rbp-88h] BYREF
  void (__fastcall *v88)(__int64); // [rsp+88h] [rbp-78h]
  char v89; // [rsp+90h] [rbp-70h]
  __int64 v90; // [rsp+98h] [rbp-68h]
  _QWORD v91[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v92; // [rsp+B0h] [rbp-50h]
  char v93; // [rsp+B8h] [rbp-48h]
  _QWORD *v94; // [rsp+C0h] [rbp-40h]
  void (__fastcall *v95)(__int64); // [rsp+C8h] [rbp-38h]
  _QWORD Buffer[2]; // [rsp+D0h] [rbp-30h] BYREF
  struct _RTL_AVL_TABLE Table; // [rsp+E0h] [rbp-20h] BYREF
  void (__fastcall *v98)(__int64); // [rsp+148h] [rbp+48h]
  __int64 (__fastcall *v99)(); // [rsp+150h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v7 = a6;
  v8 = (int)a4;
  RestartKey = a4;
  v86 = a2;
  v10 = a2;
  v90 = a1;
  v11 = a1;
  v95 = a6;
  v94 = a7;
  v91[0] = 0;
  v91[1] = 0;
  v92 = 0;
  v93 = 1;
  if ( a6 && (v7 = 0, a7) )
    v77 = 1;
  else
    v77 = (char)v7;
  v98 = v7;
  v99 = Common::DeallocateRaw<Appx::Packaging::Bitmap *>;
  RtlInitializeGenericTableAvl(
    &Table,
    Common::GenericMap<unsigned short const *,Appx::Packaging::Bitmap *>::GenericMapCompare,
    Common::GenericMap<unsigned short *,void *>::GenericMapAllocate,
    Common::GenericMap<unsigned short const *,Appx::Packaging::Bitmap *>::GenericMapFree,
    v7);
  v87[0] = v7;
  v12 = (unsigned int)v7;
  v87[1] = v7;
  v88 = v7;
  v89 = 1;
  while ( 1 )
  {
    if ( v12 >= v10 )
    {
      if ( v77 != (_BYTE)v7 )
      {
        v68 = v92;
        v69 = 16 * v92;
        if ( !is_mul_ok(v92, 0x10u) )
          v69 = -1;
        v70 = operator new[](v69, (const struct std::nothrow_t *)&std::nothrow);
        if ( !v70 )
        {
          v25 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x22C,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxrequesthandler.cpp",
            (const char *)0x8007000ELL,
            TableContext);
          Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v87);
          while ( 1 )
          {
            RestartKey = v7;
            v57 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
            if ( !v57 )
              break;
            v58 = *v57;
            v59 = v57[1];
            RtlDeleteElementGenericTableAvl(&Table, v57);
            if ( v98 )
              v98(v58);
            if ( v99 )
              ((void (__fastcall *)(__int64))v99)(v59);
          }
          goto LABEL_103;
        }
        v71 = (unsigned __int64)v7;
        if ( v68 )
        {
          v72 = v91[0];
          v73 = (unsigned __int64)v7 < v68;
          do
          {
            v74 = v7;
            if ( v73 )
              v74 = *(void (__fastcall **)(__int64))(v72 + 8 * v71);
            v75 = v71++;
            v70[v75] = *(_OWORD *)v74;
            v73 = v71 < v68;
          }
          while ( v71 < v68 );
        }
        *v94 = v70;
        *(_DWORD *)v95 = v68;
      }
      Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v87);
      Common::GenericMap<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::RemoveAll(&Table);
      v17 = (unsigned int)v7;
      goto LABEL_26;
    }
    if ( *(_DWORD *)(v11 + 48) == 2 )
    {
      v25 = -2147467260;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C6,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxrequesthandler.cpp",
        (const char *)0x80004004LL,
        TableContext);
      Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v87);
      while ( 1 )
      {
        RestartKey = v7;
        v54 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
        if ( !v54 )
          break;
        v55 = *v54;
        v56 = v54[1];
        RtlDeleteElementGenericTableAvl(&Table, v54);
        if ( v98 )
          v98(v55);
        if ( v99 )
          ((void (__fastcall *)(__int64))v99)(v56);
      }
LABEL_103:
      v17 = v25;
      goto LABEL_26;
    }
    if ( *(_DWORD *)(a3 + 24LL * v12 + 16) <= (unsigned int)v7 )
      goto LABEL_23;
    v13 = *(_QWORD *)(v11 + 16);
    Buffer[0] = *(_QWORD *)(a3 + 24LL * v12);
    Buffer[1] = v7;
    v14 = RtlLookupElementGenericTableAvl(*(PRTL_AVL_TABLE *)(v13 + 48), Buffer);
    if ( !v14 || (v7 = (void (__fastcall *)(__int64))v14[1]) == 0 )
    {
      v25 = -2147024894;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1D0,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxrequesthandler.cpp",
        (const char *)0x80070002LL,
        (int)"Filename: %ws",
        *(const char **)(a3 + 24LL * v12));
      Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v87);
      while ( 1 )
      {
        RestartKey = v7;
        v26 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
        if ( !v26 )
          break;
        v27 = *v26;
        v28 = v26[1];
        RtlDeleteElementGenericTableAvl(&Table, v26);
        if ( v98 )
          v98(v27);
        if ( v99 )
          ((void (__fastcall *)(__int64))v99)(v28);
      }
      goto LABEL_103;
    }
    if ( !*((_BYTE *)v7 + 156) || (v15 = 1, !*(_BYTE *)(a3 + 24LL * v12 + 20)) )
      v15 = 0;
    v80 = v15;
    v84 = v7;
    v81 = 0;
    v82 = 0;
    v83 = 0;
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v7 + 8LL))(v7);
    v85 = 0;
    if ( v80 )
    {
      v60 = *(_QWORD *)(v11 + 32);
      v79 = 0;
      v61 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v60 + 40LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
      v62 = v61(v60, *(_QWORD *)(a3 + 24LL * v12), &v79);
      v17 = v62;
      if ( v62 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D9,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxrequesthandler.cpp",
          (const char *)(unsigned int)v62,
          TableContext);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
        Appx::Packaging::FileDownloadInfo::~FileDownloadInfo((Appx::Packaging::FileDownloadInfo *)&v80);
        Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v87);
        while ( 1 )
        {
          RestartKey = 0;
          v36 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
          if ( !v36 )
            break;
          v37 = *v36;
          v38 = v36[1];
          RtlDeleteElementGenericTableAvl(&Table, v36);
          if ( v98 )
            v98(v37);
          if ( v99 )
            ((void (__fastcall *)(__int64))v99)(v38);
        }
        goto LABEL_26;
      }
      v63 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v79;
      v64 = **v79;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v85);
      v65 = v64(v63, &GUID_e24b3f40_e824_444f_a224_cac9df163ef0, &v85);
      v17 = v65;
      if ( v65 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1DA,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxrequesthandler.cpp",
          (const char *)(unsigned int)v65,
          TableContext);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
        Appx::Packaging::FileDownloadInfo::~FileDownloadInfo((Appx::Packaging::FileDownloadInfo *)&v80);
        Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v87);
        while ( 1 )
        {
          RestartKey = 0;
          v33 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
          if ( !v33 )
            break;
          v34 = *v33;
          v35 = v33[1];
          RtlDeleteElementGenericTableAvl(&Table, v33);
          if ( v98 )
            v98(v34);
          if ( v99 )
            ((void (__fastcall *)(__int64))v99)(v35);
        }
        goto LABEL_26;
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
      v11 = v90;
    }
    FileBlockRangeForByteRange = Appx::Packaging::GetFileBlockRangeForByteRange(
                                   (__int64 *)v7,
                                   *(_QWORD *)(a3 + 24LL * v12 + 8),
                                   *(_DWORD *)(a3 + 24LL * v12 + 16),
                                   (__int64)v87);
    v17 = FileBlockRangeForByteRange;
    if ( FileBlockRangeForByteRange == -2146958840 )
      break;
    v7 = 0;
    if ( FileBlockRangeForByteRange < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x217,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxrequesthandler.cpp",
        (const char *)(unsigned int)FileBlockRangeForByteRange,
        TableContext);
      Appx::Packaging::FileDownloadInfo::~FileDownloadInfo((Appx::Packaging::FileDownloadInfo *)&v80);
      Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v87);
      while ( 1 )
      {
        RestartKey = 0;
        v51 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
        if ( !v51 )
          break;
        v52 = *v51;
        v53 = v51[1];
        RtlDeleteElementGenericTableAvl(&Table, v51);
        if ( v98 )
          v98(v52);
        if ( v99 )
          ((void (__fastcall *)(__int64))v99)(v53);
      }
      goto LABEL_26;
    }
LABEL_14:
    v18 = v87[0];
    for ( i = 0; (void (__fastcall *)(__int64))i != v88; ++i )
    {
      v20 = 0;
      if ( i < (unsigned __int64)v88 )
        v20 = *(_QWORD *)(v18 + 8 * i);
      TableContext = v8;
      v21 = Appx::Packaging::AppxRequestHandler::AddFileBlocksForDownloading(v11, &v80, v20, &Table);
      v22 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x223,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxrequesthandler.cpp",
          (const char *)(unsigned int)v21,
          v8);
        Appx::Packaging::FileDownloadInfo::~FileDownloadInfo((Appx::Packaging::FileDownloadInfo *)&v80);
        Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v87);
        while ( 1 )
        {
          RestartKey = 0;
          v48 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
          if ( !v48 )
            break;
          v49 = *v48;
          v50 = v48[1];
          RtlDeleteElementGenericTableAvl(&Table, v48);
          if ( v98 )
            v98(v49);
          if ( v99 )
            ((void (__fastcall *)(__int64))v99)(v50);
        }
        goto LABEL_98;
      }
      v11 = v90;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v85);
    v23 = v84;
    if ( v84 )
    {
      v84 = 0;
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v10 = v86;
LABEL_23:
    ++v12;
  }
  v66 = *(_DWORD *)(a3 + 24LL * v12 + 16) >> 1;
  v67 = Appx::Packaging::GetFileBlockRangeForByteRange(
          (__int64 *)v7,
          *(_QWORD *)(a3 + 24LL * v12 + 8),
          v66,
          (__int64)v87);
  v17 = v67;
  if ( v67 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxrequesthandler.cpp",
      (const char *)(unsigned int)v67,
      TableContext);
    Appx::Packaging::FileDownloadInfo::~FileDownloadInfo((Appx::Packaging::FileDownloadInfo *)&v80);
    Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v87);
    while ( 1 )
    {
      RestartKey = 0;
      v45 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
      if ( !v45 )
        break;
      v46 = *v45;
      v47 = v45[1];
      RtlDeleteElementGenericTableAvl(&Table, v45);
      if ( v98 )
        v98(v46);
      if ( v99 )
        ((void (__fastcall *)(__int64))v99)(v47);
    }
  }
  else
  {
    for ( j = 0; (void (__fastcall *)(__int64))j != v88; ++j )
    {
      if ( j < (unsigned __int64)v88 )
        v29 = *(_QWORD *)(v87[0] + 8 * j);
      else
        v29 = 0;
      TableContext = (int)RestartKey;
      v30 = Appx::Packaging::AppxRequestHandler::AddFileBlocksForDownloading(v11, &v80, v29, &Table);
      v22 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x207,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxrequesthandler.cpp",
          (const char *)(unsigned int)v30,
          (int)RestartKey);
        Appx::Packaging::FileDownloadInfo::~FileDownloadInfo((Appx::Packaging::FileDownloadInfo *)&v80);
        Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v87);
        while ( 1 )
        {
          RestartKey = 0;
          v39 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
          if ( !v39 )
            break;
          v40 = *v39;
          v41 = v39[1];
          RtlDeleteElementGenericTableAvl(&Table, v39);
          if ( v98 )
            v98(v40);
          if ( v99 )
            ((void (__fastcall *)(__int64))v99)(v41);
        }
LABEL_98:
        v17 = v22;
        goto LABEL_26;
      }
      v11 = v90;
    }
    v32 = Appx::Packaging::GetFileBlockRangeForByteRange(
            (__int64 *)v7,
            *(_QWORD *)(a3 + 24LL * v12 + 8) + v66,
            *(_DWORD *)(a3 + 24LL * v12 + 16) - v66,
            (__int64)v87);
    v7 = 0;
    v17 = v32;
    if ( v32 >= 0 )
    {
      v8 = (int)RestartKey;
      goto LABEL_14;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x210,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxrequesthandler.cpp",
      (const char *)(unsigned int)v32,
      TableContext);
    Appx::Packaging::FileDownloadInfo::~FileDownloadInfo((Appx::Packaging::FileDownloadInfo *)&v80);
    Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v87);
    while ( 1 )
    {
      RestartKey = 0;
      v42 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
      if ( !v42 )
        break;
      v43 = *v42;
      v44 = v42[1];
      RtlDeleteElementGenericTableAvl(&Table, v42);
      if ( v98 )
        v98(v43);
      if ( v99 )
        ((void (__fastcall *)(__int64))v99)(v44);
    }
  }
LABEL_26:
  Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(v91);
  return v17;
}

```

## disassembly

```asm
0x18002b170  mov     [rsp-8+arg_8], rbx
0x18002b175  push    rbp
0x18002b176  push    rsi
0x18002b177  push    rdi
0x18002b178  push    r12
0x18002b17a  push    r13
0x18002b17c  push    r14
0x18002b17e  push    r15
0x18002b180  lea     rbp, [rsp-70h]
0x18002b185  sub     rsp, 170h
0x18002b18c  mov     rax, cs:__security_cookie
0x18002b193  xor     rax, rsp
0x18002b196  mov     [rbp+0A0h+var_40], rax
0x18002b19a  mov     r14, [rbp+0A0h+arg_28]
0x18002b1a1  xor     eax, eax
0x18002b1a3  mov     rsi, [rbp+0A0h+arg_30]
0x18002b1aa  mov     r12, r9
0x18002b1ad  mov     [rsp+1A0h+RestartKey], r9
0x18002b1b2  mov     r15, r8
0x18002b1b5  mov     [rsp+1A0h+var_130], edx
0x18002b1b9  mov     ebx, edx
0x18002b1bb  mov     [rbp+0A0h+var_108], rcx
0x18002b1bf  mov     rdi, rcx
0x18002b1c2  mov     [rbp+0A0h+var_D8], r14
0x18002b1c6  mov     [rbp+0A0h+var_E0], rsi
0x18002b1ca  mov     [rbp+0A0h+var_100], rax
0x18002b1ce  mov     [rbp+0A0h+var_F8], rax
0x18002b1d2  mov     [rbp+0A0h+var_F0], rax
0x18002b1d6  mov     [rbp+0A0h+var_E8], 1
0x18002b1da  test    r14, r14
0x18002b1dd  jnz     loc_18002B89D
0x18002b1e3  mov     [rsp+1A0h+var_160], r14b
0x18002b1e8  lea     rax, ??$DeallocateRaw@PEAVBitmap@Packaging@Appx@@@Common@@YAXPEAVBitmap@Packaging@Appx@@@Z; Common::DeallocateRaw<Appx::Packaging::Bitmap *>(Appx::Packaging::Bitmap *)
0x18002b1ef  mov     [rbp+0A0h+var_58], r14
0x18002b1f3  lea     r9, ?GenericMapFree@?$GenericMap@PEBGPEAVBitmap@Packaging@Appx@@@Common@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x18002b1fa  mov     [rbp+0A0h+var_50], rax
0x18002b1fe  lea     r8, ?GenericMapAllocate@?$GenericMap@PEAGPEAX@Common@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18002b205  mov     [rsp+1A0h+TableContext], r14; int
0x18002b20a  lea     rdx, ?GenericMapCompare@?$GenericMap@PEBGPEAVBitmap@Packaging@Appx@@@Common@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18002b211  lea     rcx, [rbp+0A0h+Table]; Table
0x18002b215  call    cs:__imp_RtlInitializeGenericTableAvl
0x18002b21c  nop     dword ptr [rax+rax+00h]
0x18002b221  mov     [rsp+1A0h+var_128], r14
0x18002b226  mov     r13d, r14d
0x18002b229  mov     [rbp+0A0h+var_120], r14
0x18002b22d  mov     [rbp+0A0h+var_118], r14
0x18002b231  mov     [rbp+0A0h+var_110], 1
0x18002b235  cmp     r13d, ebx
0x18002b238  jnb     loc_18002B398
0x18002b23e  mov     eax, [rdi+30h]
0x18002b241  cmp     eax, 2
0x18002b244  jz      loc_18002BAFE
0x18002b24a  mov     eax, r13d
0x18002b24d  lea     rsi, [rax+rax*2]
0x18002b251  cmp     [r15+rsi*8+10h], r14d
0x18002b256  jbe     loc_18002B390
0x18002b25c  mov     rcx, [rdi+10h]
0x18002b260  lea     rdx, [rbp+0A0h+Buffer]; Buffer
0x18002b264  mov     rax, [r15+rsi*8]
0x18002b268  mov     [rbp+0A0h+Buffer], rax
0x18002b26c  mov     [rbp+0A0h+var_C8], r14
0x18002b270  mov     rcx, [rcx+30h]; Table
0x18002b274  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18002b27b  nop     dword ptr [rax+rax+00h]
0x18002b280  test    rax, rax
0x18002b283  jz      loc_18002B3EC
0x18002b289  mov     r14, [rax+8]
0x18002b28d  xor     ebx, ebx
0x18002b28f  test    r14, r14
0x18002b292  jz      loc_18002B3EC
0x18002b298  cmp     [r14+9Ch], bl
0x18002b29f  jnz     loc_18002B8B3
0x18002b2a5  mov     al, bl
0x18002b2a7  mov     [rsp+1A0h+var_148], al
0x18002b2ab  mov     rcx, r14
0x18002b2ae  xor     eax, eax
0x18002b2b0  mov     [rsp+1A0h+var_140], r14
0x18002b2b5  mov     [rsp+1A0h+var_147], eax
0x18002b2b9  mov     [rsp+1A0h+var_143], ax
0x18002b2be  mov     [rsp+1A0h+var_141], al
0x18002b2c2  mov     rax, [r14]
0x18002b2c5  mov     rax, [rax+8]
0x18002b2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2ce  mov     [rsp+1A0h+var_138], rbx
0x18002b2d3  cmp     [rsp+1A0h+var_148], bl
0x18002b2d7  jnz     loc_18002B8C5
0x18002b2dd  mov     r8d, [r15+rsi*8+10h]
0x18002b2e2  lea     r9, [rsp+1A0h+var_128]
0x18002b2e7  mov     rdx, [r15+rsi*8+8]
0x18002b2ec  mov     rcx, r14
0x18002b2ef  call    ?GetFileBlockRangeForByteRange@Packaging@Appx@@YAJPEAVAppxBlockMapFile@BlockMap@12@_KIAEAV?$Array@UBlockRangeInfo@Packaging@Appx@@V?$ContainerOperations@UBlockRangeInfo@Packaging@Appx@@U123@@Common@@VNoKey@5@V?$ContainerOperations@VNoKey@Common@@UBlockRangeInfo@Packaging@Appx@@@5@V?$ArrayOperations@UBlockRangeInfo@Packaging@Appx@@VNoKey@Common@@@5@@Common@@@Z; Appx::Packaging::GetFileBlockRangeForByteRange(Appx::Packaging::BlockMap::AppxBlockMapFile *,unsigned __int64,uint,Common::Array<Appx::Packaging::BlockRangeInfo,Common::ContainerOperations<Appx::Packaging::BlockRangeInfo,Appx::Packaging::BlockRangeInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockRangeInfo>,Common::ArrayOperations<Appx::Packaging::BlockRangeInfo,Common::NoKey>> &)
0x18002b2f4  mov     ebx, eax
0x18002b2f6  cmp     eax, 80080208h
0x18002b2fb  jz      loc_18002B942
0x18002b301  xor     r14d, r14d
0x18002b304  test    eax, eax
0x18002b306  js      loc_18002BAC3
0x18002b30c  mov     rsi, [rsp+1A0h+var_128]
0x18002b311  mov     rbx, r14
0x18002b314  cmp     rbx, [rbp+0A0h+var_118]
0x18002b318  jz      short loc_18002B367
0x18002b31a  mov     r8, r14
0x18002b31d  jnb     short loc_18002B323
0x18002b31f  mov     r8, [rsi+rbx*8]
0x18002b323  lea     rax, [rbp+0A0h+var_100]
0x18002b327  mov     rcx, rdi
0x18002b32a  mov     [rsp+1A0h+var_168], rax
0x18002b32f  lea     r9, [rbp+0A0h+Table]
0x18002b333  mov     al, [rsp+1A0h+var_160]
0x18002b337  lea     rdx, [rsp+1A0h+var_148]
0x18002b33c  mov     [rsp+1A0h+var_170], al
0x18002b340  mov     al, [rbp+0A0h+arg_20]
0x18002b346  mov     byte ptr [rsp+1A0h+var_178], al
0x18002b34a  mov     [rsp+1A0h+TableContext], r12; int
0x18002b34f  call    ?AddFileBlocksForDownloading@AppxRequestHandler@Packaging@Appx@@AEAAJAEAUFileDownloadInfo@23@AEAUBlockRangeInfo@23@AEAV?$GenericMap@PEBGPEAVBitmap@Packaging@Appx@@@Common@@AEAV?$GenericList@UFileBlockRange@Packaging@Appx@@@23@_N4AEAV?$Array@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@V?$ContainerOperations@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@U1@@Common@@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@@3@V?$ArrayOperations@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@VNoKey@Common@@@3@@7@@Z; Appx::Packaging::AppxRequestHandler::AddFileBlocksForDownloading(Appx::Packaging::FileDownloadInfo &,Appx::Packaging::BlockRangeInfo &,Common::GenericMap<ushort const *,Appx::Packaging::Bitmap *> &,Appx::Packaging::GenericList<Appx::Packaging::FileBlockRange> &,bool,bool,Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>> &)
0x18002b354  mov     edi, eax
0x18002b356  test    eax, eax
0x18002b358  js      loc_18002BA8F
0x18002b35e  mov     rdi, [rbp+0A0h+var_108]
0x18002b362  inc     rbx
0x18002b365  jmp     short loc_18002B314
0x18002b367  lea     rcx, [rsp+1A0h+var_138]
0x18002b36c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18002b371  mov     rcx, [rsp+1A0h+var_140]
0x18002b376  test    rcx, rcx
0x18002b379  jz      short loc_18002B38C
0x18002b37b  mov     [rsp+1A0h+var_140], r14
0x18002b380  mov     rax, [rcx]
0x18002b383  mov     rax, [rax+10h]
0x18002b387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b38c  mov     ebx, [rsp+1A0h+var_130]
0x18002b390  inc     r13d
0x18002b393  jmp     loc_18002B235
0x18002b398  cmp     [rsp+1A0h+var_160], r14b
0x18002b39d  jnz     loc_18002BB2D
0x18002b3a3  lea     rcx, [rsp+1A0h+var_128]
0x18002b3a8  call    ??1?$Array@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@V?$ContainerOperations@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@U1@@Common@@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@@3@V?$ArrayOperations@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@VNoKey@Common@@@3@@Common@@QEAA@XZ; Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(void)
0x18002b3ad  lea     rcx, [rbp+0A0h+Table]; Table
0x18002b3b1  call    ?RemoveAll@?$GenericMap@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@Common@@QEAAXXZ; Common::GenericMap<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::RemoveAll(void)
0x18002b3b6  mov     ebx, r14d
0x18002b3b9  lea     rcx, [rbp+0A0h+var_100]
0x18002b3bd  call    ??1?$Array@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@V?$ContainerOperations@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@U1@@Common@@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@@3@V?$ArrayOperations@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@VNoKey@Common@@@3@@Common@@QEAA@XZ; Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(void)
0x18002b3c2  mov     eax, ebx
0x18002b3c4  mov     rcx, [rbp+0A0h+var_40]
0x18002b3c8  xor     rcx, rsp; StackCookie
0x18002b3cb  call    __security_check_cookie
0x18002b3d0  mov     rbx, [rsp+1A0h+arg_8]
0x18002b3d8  add     rsp, 170h
0x18002b3df  pop     r15
0x18002b3e1  pop     r14
0x18002b3e3  pop     r13
0x18002b3e5  pop     r12
0x18002b3e7  pop     rdi
0x18002b3e8  pop     rsi
0x18002b3e9  pop     rbp
0x18002b3ea  retn
0x18002b3ec  mov     rax, [r15+rsi*8]
0x18002b3f0  lea     r8, aOnecorePrintsc_134; "onecore\\printscan\\appxpackaging\\cons"...
0x18002b3f7  mov     rcx, [rbp+0A8h]; this
0x18002b3fe  mov     esi, 80070002h
0x18002b403  mov     [rsp+1A0h+var_178], rax; char *
0x18002b408  mov     r9d, esi; char *
0x18002b40b  lea     rax, aFilenameWs; "Filename: %ws"
0x18002b412  mov     edx, 1D0h; void *
0x18002b417  mov     [rsp+1A0h+TableContext], rax; int
0x18002b41c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002b421  lea     rcx, [rsp+1A0h+var_128]
0x18002b426  call    ??1?$Array@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@V?$ContainerOperations@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@U1@@Common@@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@@3@V?$ArrayOperations@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@VNoKey@Common@@@3@@Common@@QEAA@XZ; Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(void)
0x18002b42b  lea     rdx, [rsp+1A0h+RestartKey]; RestartKey
0x18002b430  mov     [rsp+1A0h+RestartKey], r14
0x18002b435  lea     rcx, [rbp+0A0h+Table]; Table
0x18002b439  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x18002b440  nop     dword ptr [rax+rax+00h]
0x18002b445  test    rax, rax
0x18002b448  jz      loc_18002BAF7
0x18002b44e  mov     rbx, [rax]
0x18002b451  lea     rcx, [rbp+0A0h+Table]; Table
0x18002b455  mov     rdi, [rax+8]
0x18002b459  mov     rdx, rax; Buffer
0x18002b45c  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18002b463  nop     dword ptr [rax+rax+00h]
0x18002b468  mov     rax, [rbp+0A0h+var_58]
0x18002b46c  test    rax, rax
0x18002b46f  jz      short loc_18002B479
0x18002b471  mov     rcx, rbx
0x18002b474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b479  mov     rax, [rbp+0A0h+var_50]
0x18002b47d  test    rax, rax
0x18002b480  jz      short loc_18002B42B
0x18002b482  mov     rcx, rdi
0x18002b485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b48a  jmp     short loc_18002B42B
0x18002b48c  jb      loc_18002B516
0x18002b492  xor     r8d, r8d
0x18002b495  lea     rax, [rbp+0A0h+var_100]
0x18002b499  mov     rcx, rdi
0x18002b49c  mov     [rsp+1A0h+var_168], rax
0x18002b4a1  lea     r9, [rbp+0A0h+Table]
0x18002b4a5  mov     al, [rsp+1A0h+var_160]
0x18002b4a9  lea     rdx, [rsp+1A0h+var_148]
0x18002b4ae  mov     [rsp+1A0h+var_170], al
0x18002b4b2  mov     al, [rbp+0A0h+arg_20]
0x18002b4b8  mov     byte ptr [rsp+1A0h+var_178], al
0x18002b4bc  mov     rax, [rsp+1A0h+RestartKey]
0x18002b4c1  mov     [rsp+1A0h+TableContext], rax; int
0x18002b4c6  call    ?AddFileBlocksForDownloading@AppxRequestHandler@Packaging@Appx@@AEAAJAEAUFileDownloadInfo@23@AEAUBlockRangeInfo@23@AEAV?$GenericMap@PEBGPEAVBitmap@Packaging@Appx@@@Common@@AEAV?$GenericList@UFileBlockRange@Packaging@Appx@@@23@_N4AEAV?$Array@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@V?$ContainerOperations@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@U1@@Common@@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@@3@V?$ArrayOperations@U__MIDL___MIDL_itf_appxdatasource_0000_0000_0003@@VNoKey@Common@@@3@@7@@Z; Appx::Packaging::AppxRequestHandler::AddFileBlocksForDownloading(Appx::Packaging::FileDownloadInfo &,Appx::Packaging::BlockRangeInfo &,Common::GenericMap<ushort const *,Appx::Packaging::Bitmap *> &,Appx::Packaging::GenericList<Appx::Packaging::FileBlockRange> &,bool,bool,Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>> &)
0x18002b4cb  mov     edi, eax
0x18002b4cd  test    eax, eax
0x18002b4cf  js      loc_18002B9EC
0x18002b4d5  mov     rdi, [rbp+0A0h+var_108]
0x18002b4d9  inc     rbx
0x18002b4dc  cmp     rbx, [rbp+0A0h+var_118]
0x18002b4e0  jnz     short loc_18002B48C
0x18002b4e2  mov     r8d, [r15+rsi*8+10h]
0x18002b4e7  lea     r9, [rsp+1A0h+var_128]
0x18002b4ec  mov     edx, r12d
0x18002b4ef  sub     r8d, r12d
0x18002b4f2  add     rdx, [r15+rsi*8+8]
0x18002b4f7  mov     rcx, r14
0x18002b4fa  call    ?GetFileBlockRangeForByteRange@Packaging@Appx@@YAJPEAVAppxBlockMapFile@BlockMap@12@_KIAEAV?$Array@UBlockRangeInfo@Packaging@Appx@@V?$ContainerOperations@UBlockRangeInfo@Packaging@Appx@@U123@@Common@@VNoKey@5@V?$ContainerOperations@VNoKey@Common@@UBlockRangeInfo@Packaging@Appx@@@5@V?$ArrayOperations@UBlockRangeInfo@Packaging@Appx@@VNoKey@Common@@@5@@Common@@@Z; Appx::Packaging::GetFileBlockRangeForByteRange(Appx::Packaging::BlockMap::AppxBlockMapFile *,unsigned __int64,uint,Common::Array<Appx::Packaging::BlockRangeInfo,Common::ContainerOperations<Appx::Packaging::BlockRangeInfo,Appx::Packaging::BlockRangeInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockRangeInfo>,Common::ArrayOperations<Appx::Packaging::BlockRangeInfo,Common::NoKey>> &)
0x18002b4ff  xor     r14d, r14d
0x18002b502  mov     ebx, eax
0x18002b504  test    eax, eax
0x18002b506  js      loc_18002BA27
0x18002b50c  mov     r12, [rsp+1A0h+RestartKey]
0x18002b511  jmp     loc_18002B30C
0x18002b516  mov     rax, [rsp+1A0h+var_128]
0x18002b51b  mov     r8, [rax+rbx*8]
0x18002b51f  jmp     loc_18002B495
0x18002b524  lea     rdx, [rsp+1A0h+RestartKey]; RestartKey
0x18002b529  mov     [rsp+1A0h+RestartKey], 0
0x18002b532  lea     rcx, [rbp+0A0h+Table]; Table
0x18002b536  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x18002b53d  nop     dword ptr [rax+rax+00h]
0x18002b542  test    rax, rax
0x18002b545  jz      loc_18002B3B9
0x18002b54b  mov     rdi, [rax]
0x18002b54e  lea     rcx, [rbp+0A0h+Table]; Table
0x18002b552  mov     rsi, [rax+8]
0x18002b556  mov     rdx, rax; Buffer
0x18002b559  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18002b560  nop     dword ptr [rax+rax+00h]
0x18002b565  mov     rax, [rbp+0A0h+var_58]
0x18002b569  test    rax, rax
0x18002b56c  jz      short loc_18002B576
0x18002b56e  mov     rcx, rdi
0x18002b571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b576  mov     rax, [rbp+0A0h+var_50]
0x18002b57a  test    rax, rax
0x18002b57d  jz      short loc_18002B524
0x18002b57f  mov     rcx, rsi
0x18002b582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b587  jmp     short loc_18002B524
0x18002b589  lea     rdx, [rsp+1A0h+RestartKey]; RestartKey
0x18002b58e  mov     [rsp+1A0h+RestartKey], 0
0x18002b597  lea     rcx, [rbp+0A0h+Table]; Table
0x18002b59b  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x18002b5a2  nop     dword ptr [rax+rax+00h]
0x18002b5a7  test    rax, rax
0x18002b5aa  jz      loc_18002B3B9
0x18002b5b0  mov     rdi, [rax]
0x18002b5b3  lea     rcx, [rbp+0A0h+Table]; Table
0x18002b5b7  mov     rsi, [rax+8]
0x18002b5bb  mov     rdx, rax; Buffer
0x18002b5be  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18002b5c5  nop     dword ptr [rax+rax+00h]
0x18002b5ca  mov     rax, [rbp+0A0h+var_58]
0x18002b5ce  test    rax, rax
0x18002b5d1  jz      short loc_18002B5DB
0x18002b5d3  mov     rcx, rdi
0x18002b5d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5db  mov     rax, [rbp+0A0h+var_50]
0x18002b5df  test    rax, rax
0x18002b5e2  jz      short loc_18002B589
0x18002b5e4  mov     rcx, rsi
0x18002b5e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5ec  jmp     short loc_18002B589
0x18002b5ee  lea     rdx, [rsp+1A0h+RestartKey]; RestartKey
0x18002b5f3  mov     [rsp+1A0h+RestartKey], 0
0x18002b5fc  lea     rcx, [rbp+0A0h+Table]; Table
0x18002b600  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x18002b607  nop     dword ptr [rax+rax+00h]
0x18002b60c  test    rax, rax
0x18002b60f  jz      loc_18002BA20
0x18002b615  mov     rbx, [rax]
0x18002b618  lea     rcx, [rbp+0A0h+Table]; Table
0x18002b61c  mov     rsi, [rax+8]
0x18002b620  mov     rdx, rax; Buffer
0x18002b623  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18002b62a  nop     dword ptr [rax+rax+00h]
0x18002b62f  mov     rax, [rbp+0A0h+var_58]
0x18002b633  test    rax, rax
0x18002b636  jz      short loc_18002B640
0x18002b638  mov     rcx, rbx
0x18002b63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b640  mov     rax, [rbp+0A0h+var_50]
0x18002b644  test    rax, rax
0x18002b647  jz      short loc_18002B5EE
0x18002b649  mov     rcx, rsi
0x18002b64c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
