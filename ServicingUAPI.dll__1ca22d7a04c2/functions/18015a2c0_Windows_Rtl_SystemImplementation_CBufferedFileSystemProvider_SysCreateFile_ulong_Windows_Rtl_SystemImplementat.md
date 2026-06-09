# Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile(ulong,Windows::Rtl::SystemImplementation::CSilHandle *,ulong,_OBJECT_ATTRIBUTES &,_IO_STATUS_BLOCK *,_LARGE_INTEGER *,ulong,ulong,ulong,ulong,void *,ulong,Windows::Rtl::KtmTransactionInfoPointer,ulong *)

- ea: `0x18015a2c0`
- end: `0x18015b516`
- name: `?SysCreateFile@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@UEAAJKPEAVCSilHandle@234@KAEAU_OBJECT_ATTRIBUTES@@PEAU_IO_STATUS_BLOCK@@PEAT_LARGE_INTEGER@@KKKKPEAXKUKtmTransactionInfoPointer@34@PEAK@Z`
- size: `4694`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18000e098`
- `0x1800497c0`
- `0x18004d970`
- `0x18004f350`
- `0x18011c474`
- `0x180127540`
- `0x18012d4e4`
- `0x18012fa2c`
- `0x180130898`
- `0x180130944`
- `0x180131fd8`
- `0x180137414`
- `0x180137614`
- `0x180137870`
- `0x1801378f0`
- `0x180137d48`
- `0x180137f90`
- `0x1801381bc`
- `0x1801568a8`
- `0x180156ae4`
- `0x180156f10`
- `0x180156f54`
- `0x1801570e0`
- `0x1801572f0`
- `0x18015760c`
- `0x180157bb0`
- `0x1801596a0`
- `0x18015a2c0`
- `0x1801a28c0`
- `0x1801bd010`

## string_xrefs

- `0x18015aab8`: `Parsed.IsDirectory || Parsed.IsNonDirectory`
- `0x18015a3c2`: `CreateOptions`
- `0x18015a33f`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015a375`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015a3ad`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015a4e2`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015a54d`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015a61a`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015a698`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015aaa3`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015ab07`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015ac90`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015acec`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015ad9d`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015aeff`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015af77`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015b343`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015b3e6`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`
- `0x18015b4aa`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile(
        __int64 a1,
        unsigned int a2,
        void **a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        unsigned int a8,
        int a9,
        unsigned int a10,
        unsigned int a11,
        __int64 a12,
        int a13,
        __int64 a14,
        unsigned int *a15)
{
  unsigned int v15; // r12d
  __int64 v16; // r14
  const char *v17; // rax
  Windows::Rtl::SystemImplementation *v18; // rcx
  struct Windows::Rtl::SystemImplementation::ParsedOptionsDisposition *v19; // r9
  __int64 result; // rax
  struct Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *v21; // rdx
  int File; // esi
  Windows::Rtl::SystemImplementation::CBufferedFileHierarchy *v23; // rcx
  bool v24; // r8
  struct Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *v25; // r13
  unsigned int v26; // r15d
  PWSTR v27; // rcx
  int exists; // r14d
  int UniqueFileIdOrZero; // ebx
  volatile signed __int32 *v30; // rbx
  utl::_RefCountBase *v31; // r14
  unsigned int v32; // eax
  __int64 v33; // rcx
  unsigned int v34; // eax
  Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider *v35; // r12
  unsigned int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  void (__fastcall ***v39)(_QWORD); // rdx
  void (__fastcall ***v40)(_QWORD); // rcx
  unsigned __int64 v41; // rcx
  __int64 v42; // r8
  __int64 **v43; // r14
  __int64 *v44; // r12
  __int64 *i; // rbx
  const char *v46; // rax
  __int64 v47; // rax
  void (__fastcall ***v48)(_QWORD); // rcx
  __int64 v49; // rdx
  int v50; // r12d
  void (__fastcall ***v51)(_QWORD); // rcx
  void (__fastcall ***v52)(_QWORD); // rcx
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rax
  volatile signed __int32 *v56; // rcx
  utl::_RefCountBase *v57; // rax
  __int64 v58; // rdx
  int inserted; // r15d
  __int64 v60; // rcx
  char v61; // al
  unsigned int v62; // r12d
  __int64 v63; // r15
  __int64 v64; // rax
  void *v65; // r14
  const struct _SECURITY_DESCRIPTOR *v66; // rax
  _DWORD *v67; // rcx
  void **v68; // rdx
  void *v69; // rcx
  void (__fastcall ***v70)(_QWORD); // rcx
  bool *v71; // [rsp+20h] [rbp-E0h]
  char v72; // [rsp+50h] [rbp-B0h]
  utl::_RefCountBase *v73[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v74; // [rsp+68h] [rbp-98h]
  const char *v75; // [rsp+70h] [rbp-90h]
  char v76[4]; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v77[3]; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v78[2]; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v79; // [rsp+90h] [rbp-70h]
  struct Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *v80; // [rsp+98h] [rbp-68h] BYREF
  __int64 v81; // [rsp+A0h] [rbp-60h]
  void **v82; // [rsp+A8h] [rbp-58h]
  __int64 v83; // [rsp+B0h] [rbp-50h]
  __int128 v84; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v85; // [rsp+C8h] [rbp-38h]
  bool *v86[2]; // [rsp+D8h] [rbp-28h]
  struct _UNICODE_STRING v87; // [rsp+F0h] [rbp-10h] BYREF
  void *v88[2]; // [rsp+100h] [rbp+0h] BYREF
  PWSTR Buffer; // [rsp+110h] [rbp+10h]
  unsigned int v90; // [rsp+118h] [rbp+18h] BYREF
  __int64 v91; // [rsp+120h] [rbp+20h] BYREF
  utl::_RefCountBase *v92; // [rsp+128h] [rbp+28h]
  __int128 v93; // [rsp+130h] [rbp+30h] BYREF
  __int128 v94; // [rsp+140h] [rbp+40h] BYREF
  __int64 v95; // [rsp+150h] [rbp+50h]
  __int64 v96; // [rsp+158h] [rbp+58h]
  __int128 v97; // [rsp+160h] [rbp+60h] BYREF
  __int64 v98; // [rsp+170h] [rbp+70h]
  char v99; // [rsp+178h] [rbp+78h]
  __int16 v100; // [rsp+17Ah] [rbp+7Ah]
  __int128 v101; // [rsp+180h] [rbp+80h]
  __int128 v102; // [rsp+190h] [rbp+90h]
  __int128 v103; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v104; // [rsp+1B0h] [rbp+B0h]
  char v105; // [rsp+1B8h] [rbp+B8h]
  __int16 v106; // [rsp+1BAh] [rbp+BAh]
  __int128 v107; // [rsp+1C0h] [rbp+C0h]
  __int128 v108; // [rsp+1D0h] [rbp+D0h]

  v83 = -2;
  v82 = a3;
  v15 = a2;
  v79 = a2;
  v16 = a1;
  *(_QWORD *)&v77[1] = a1;
  v81 = a6;
  if ( a15 )
    *a15 = 0;
  if ( a12 )
  {
    v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
    v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
    v74 = 778;
    v17 = "!EaBuffer";
LABEL_227:
    v75 = v17;
    RtlReportErrorOrigination(v73, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  if ( a13 )
  {
    v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
    v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
    v74 = 779;
    v17 = "!EaLength";
    goto LABEL_227;
  }
  if ( (a11 & 0x20) == 0 )
  {
    v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
    v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
    v74 = 780;
    v17 = "CreateOptions";
    goto LABEL_227;
  }
  if ( a14 )
  {
    v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
    v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
    v74 = 781;
    v17 = "!Transaction";
    goto LABEL_227;
  }
  *(_OWORD *)v73 = 0;
  v80 = 0;
  v78[0] = Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::AccessMaskFilter(
             (Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider *)a11,
             a4 | 0x80);
  LOWORD(v77[0]) = 0;
  BYTE2(v77[0]) = 0;
  result = Windows::Rtl::SystemImplementation::ParseOptionsDisposition(v18, a10, (unsigned int)v77, v19);
  if ( (int)result < 0 )
    return result;
  v87 = 0;
  v84 = 0;
  v85 = 0;
  *(_OWORD *)v86 = 0;
  File = Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::CanonicalizePath(v16, a5, &v87, &v84);
  if ( File < 0
    || (v88[0] = (void *)v87.Length,
        v88[1] = (void *)v87.MaximumLength,
        Buffer = v87.Buffer,
        File = Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::FindFile(
                 (Windows::Rtl::SystemImplementation::CBufferedFileHierarchy *)(v16 + 40),
                 v21,
                 (const struct _LUNICODE_STRING *)v88,
                 &v80),
        File < 0) )
  {
    if ( v87.Buffer )
      anonymous_namespace_::OurRtlFreeStringRoutine(v87.Buffer);
    return (unsigned int)File;
  }
  v72 = 0;
  LOBYTE(v23) = v77[0];
  v25 = v80;
  v26 = 2;
  if ( !v80 )
  {
    if ( a10 == 2 && (v15 & 1) == 0 )
    {
      exists = Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::AssertFileExistence(
                 (Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider *)v16,
                 &v87,
                 v24);
      if ( exists < 0 )
        goto LABEL_35;
      v16 = *(_QWORD *)&v77[1];
    }
    if ( (v15 & 2) != 0
      || a10 == 1
      || (exists = Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::AssertParentDirectoryExistsSomewhere(
                     (Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider *)v16,
                     &v87),
          exists >= 0) )
    {
      *(_OWORD *)v88 = 0;
      v90 = 0;
      switch ( a10 )
      {
        case 1u:
          v36 = Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::AccessMaskFilter(0, v78[0]);
          v37 = v15 & 0xFFF1FFFF;
          v35 = *(Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider **)&v77[1];
          UniqueFileIdOrZero = Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::SysOpenFile(
                                 *(_QWORD *)(*(_QWORD *)&v77[1] + 200LL),
                                 v37,
                                 v88,
                                 v36,
                                 &v84,
                                 a9,
                                 a11,
                                 v38,
                                 &v90);
          if ( UniqueFileIdOrZero >= 0 )
          {
            v34 = v90;
LABEL_86:
            if ( v34 != 1 )
            {
              if ( a15 )
                *a15 = v34;
              Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v88);
              v70 = (void (__fastcall ***)(_QWORD))v88[0];
              if ( v88[0] )
              {
                v88[0] = 0;
                (**v70)(v70);
              }
              v27 = v87.Buffer;
              if ( !v87.Buffer )
                return 0;
              goto LABEL_223;
            }
            v93 = 0;
            v94 = 0;
            v95 = 0;
            v96 = 0;
            UniqueFileIdOrZero = Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetUniqueFileIdOrZero(
                                   v35,
                                   v88[1],
                                   (struct Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::FileId *)&v93);
            if ( UniqueFileIdOrZero < 0 )
            {
              Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v94);
              Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v88);
              v40 = (void (__fastcall ***)(_QWORD))v88[0];
              if ( v88[0] )
              {
                v88[0] = 0;
                (**v40)(v40);
              }
              goto LABEL_58;
            }
            v41 = v93;
            if ( (_QWORD)v93 )
            {
              v42 = v93;
              v91 = v93;
              v43 = (__int64 **)(*((_QWORD *)v35 + 28) + 32 * ((unsigned __int64)v93 % *((_QWORD *)v35 + 30)));
              v44 = 0;
              for ( i = *v43; i && i != (__int64 *)v43; i = (__int64 *)*i )
              {
                if ( i[4] == v42
                  && (_DWORD)v96 == *((_DWORD *)i + 20)
                  && __PAIR128__(*((unsigned __int64 *)&v93 + 1), v41) == *(_OWORD *)(i + 5) )
                {
                  if ( (unsigned __int8)Windows::StringUtil::AreStringsEqualByOrdinalCaseInvariantNonReflexive<Windows::Auto<_LUNICODE_STRING>,Windows::Auto<_LUNICODE_STRING>>(
                                          &v94,
                                          i + 7) )
                  {
                    v44 = i + 11;
                    break;
                  }
                  v41 = v93;
                  v42 = v91;
                }
              }
              if ( v44 )
              {
                v31 = (utl::_RefCountBase *)*v44;
                v30 = (volatile signed __int32 *)v44[1];
                if ( v30 )
                  _InterlockedIncrement(v30 + 2);
                goto LABEL_104;
              }
              v47 = utl::make_shared<Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::SharedFileInfo,>(&v91);
              v31 = *(utl::_RefCountBase **)v47;
              v30 = *(volatile signed __int32 **)(v47 + 8);
              *(_QWORD *)v47 = 0;
              *(_QWORD *)(v47 + 8) = 0;
              v73[0] = v31;
              v73[1] = (utl::_RefCountBase *)v30;
              if ( v92 )
                utl::_RefCountBase::_DecStrong(v92);
              if ( !v31 )
              {
                v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
                v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
                v74 = 1016;
                v75 = "SharedInfo.get()";
                RtlReportErrorOrigination(v73, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
                Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v94);
                Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v88);
                v48 = (void (__fastcall ***)(_QWORD))v88[0];
                if ( !v88[0] )
                  goto LABEL_156;
                v88[0] = 0;
LABEL_116:
                (**v48)(v48);
                goto LABEL_156;
              }
              if ( (a11 & 1) != 0 )
                v49 = 2;
              else
                v49 = ((unsigned __int8)a11 >> 6) & 1;
              v50 = Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::InitializeInfoForExistingFile(
                      a11,
                      v49,
                      v31,
                      v88);
              if ( v50 >= 0 )
              {
                *(_QWORD *)v78 = 0;
                v76[0] = 0;
                BUCL::HashTable::CTable<Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::CFileIdToPathElementTableTraits>::CBucketChain::FindOrInsertIfNotPresent<Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::FileId,utl::shared_ptr<Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::SharedFileInfo>>(
                  *(_DWORD *)(*(_QWORD *)&v77[1] + 224LL)
                + 32 * ((unsigned __int64)v93 % *(_QWORD *)(*(_QWORD *)&v77[1] + 240LL)),
                  (unsigned int)&v91,
                  v77[1] + 216,
                  (unsigned int)&v93,
                  (__int64)v73,
                  v93,
                  (__int64)v78,
                  (__int64)v76);
                v50 = v91;
                if ( (int)v91 >= 0 )
                {
                  if ( v76[0] )
                  {
                    v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
                    v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
                    v74 = 1036;
                    v75 = "!fExists";
                    RtlReportErrorOrigination(v73, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
                    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v94);
                    Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v88);
                    v52 = (void (__fastcall ***)(_QWORD))v88[0];
                    if ( v88[0] )
                    {
                      v88[0] = 0;
                      (**v52)(v52);
                    }
                    goto LABEL_214;
                  }
                  goto LABEL_104;
                }
                v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
                v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
                v74 = 1033;
                v75 = "m_FileIdTable.FindOrInsertIfNotPresent( Id, SharedInfo, &SharedInfoStored, &fExists)";
                RtlReportErrorOrigination(v73, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v91);
                Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v94);
              }
              else
              {
                Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v94);
              }
            }
            else
            {
              v53 = utl::make_shared<Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::SharedFileInfo,>(v73);
              v31 = *(utl::_RefCountBase **)v53;
              v30 = *(volatile signed __int32 **)(v53 + 8);
              *(_QWORD *)v53 = 0;
              *(_QWORD *)(v53 + 8) = 0;
              if ( v73[1] )
                utl::_RefCountBase::_DecStrong(v73[1]);
              if ( !v31 )
              {
                v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
                v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
                v74 = 1042;
                v75 = "SharedInfo.get()";
                RtlReportErrorOrigination(v73, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
                Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v94);
                Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v88);
                v48 = (void (__fastcall ***)(_QWORD))v88[0];
                if ( !v88[0] )
                  goto LABEL_156;
                v88[0] = 0;
                goto LABEL_116;
              }
              if ( (a11 & 1) != 0 )
                v54 = 2;
              else
                v54 = ((unsigned __int8)a11 >> 6) & 1;
              v71 = (bool *)v85;
              v50 = Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::InitializeInfoForExistingFile(
                      a11,
                      v54,
                      v31,
                      v88);
              if ( v50 >= 0 )
              {
LABEL_104:
                Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v94);
                v15 = v79;
LABEL_105:
                Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v88);
                v23 = (Windows::Rtl::SystemImplementation::CBufferedFileHierarchy *)v88[0];
                if ( v88[0] )
                {
                  v88[0] = 0;
                  (**(void (__fastcall ***)(Windows::Rtl::SystemImplementation::CBufferedFileHierarchy *))v23)(v23);
                }
LABEL_107:
                v103 = 0;
                v104 = 0;
                v105 = 0;
                v106 = 0;
                v107 = 0;
                v108 = 0;
                v97 = 0;
                v98 = 0;
                v99 = 0;
                v100 = 0;
                v101 = 0;
                v102 = 0;
                if ( !v72 && (v15 & 0x20000) == 0 )
                  goto LABEL_147;
                if ( !LOWORD(v77[0]) )
                {
                  v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
                  v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
                  v74 = 1067;
                  v46 = "Parsed.IsDirectory || Parsed.IsNonDirectory";
LABEL_213:
                  v75 = v46;
                  RtlReportErrorOrigination(v73, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
                  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v97);
                  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v103);
LABEL_214:
                  if ( v87.Buffer )
                  {
                    anonymous_namespace_::OurRtlFreeStringRoutine(v87.Buffer);
                    v87 = 0;
                  }
                  if ( v30 )
                    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
                  return 3221225485LL;
                }
                v71 = v86[0];
                v50 = Windows::Rtl::SystemImplementation::IRtlObjectProvider::CalculateSecurityForCreate(
                        *(_QWORD *)&v77[1],
                        LOBYTE(v77[0]) != 0 ? 4 : 2,
                        0,
                        &v87);
                if ( v50 < 0 )
                {
                  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v97);
                  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v103);
LABEL_124:
                  if ( v87.Buffer )
                  {
                    anonymous_namespace_::OurRtlFreeStringRoutine(v87.Buffer);
                    v87 = 0;
                  }
                  if ( v30 )
                    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
                  return (unsigned int)v50;
                }
                if ( !v72 )
                {
LABEL_147:
                  if ( v25 )
                    goto LABEL_179;
                  goto LABEL_148;
                }
                v55 = utl::make_shared<Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::SharedFileInfo,>(v73);
                v31 = *(utl::_RefCountBase **)v55;
                v56 = *(volatile signed __int32 **)(v55 + 8);
                *(_QWORD *)v55 = 0;
                *(_QWORD *)(v55 + 8) = 0;
                v57 = (utl::_RefCountBase *)v30;
                v30 = v56;
                if ( v57 )
                  utl::_RefCountBase::_DecStrong(v57);
                if ( v73[1] )
                  utl::_RefCountBase::_DecStrong(v73[1]);
                if ( v31 )
                {
                  Windows::Rtl::SecurityDescriptor::Get((Windows::Rtl::SecurityDescriptor *)&v103);
                  if ( (a11 & 1) == 0 )
                    v26 = ((unsigned __int8)a11 >> 6) & 1;
                  LOBYTE(v58) = v86[0] == 0;
                  LODWORD(v71) = a8;
                  inserted = Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::InitializeInfoForNewFile(
                               a11,
                               v58,
                               v26,
                               v31);
                  if ( inserted < 0 )
                    goto LABEL_164;
LABEL_148:
                  if ( (*((_BYTE *)v31 + 164) & 1) == 0 )
                  {
                    v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
                    v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
                    v74 = 1099;
                    v46 = "SharedInfo->fInitializedInHierarchy";
                    goto LABEL_213;
                  }
                  if ( !v25 )
                  {
                    v73[0] = (utl::_RefCountBase *)v87.Length;
                    v73[1] = (utl::_RefCountBase *)v87.MaximumLength;
                    v74 = (__int64)v87.Buffer;
                    inserted = Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::FindOrInsertFile(
                                 (Windows::Rtl::SystemImplementation::CBufferedFileHierarchy *)(*(_QWORD *)&v77[1] + 40LL),
                                 (const struct _LUNICODE_STRING *)v73,
                                 *(struct Windows::Rtl::SystemImplementation::IRtlFileSystemProvider **)(*(_QWORD *)&v77[1] + 200LL),
                                 &v80,
                                 v71);
                    if ( inserted < 0 )
                      goto LABEL_164;
                    v25 = v80;
                  }
                  v73[0] = v31;
                  v73[1] = (utl::_RefCountBase *)v30;
                  if ( v30 )
                    _InterlockedIncrement(v30 + 2);
                  v88[0] = (void *)v87.Length;
                  v88[1] = (void *)v87.MaximumLength;
                  Buffer = v87.Buffer;
                  exists = Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::InitializeElement(
                             v23,
                             v25,
                             v88,
                             v73);
                  if ( exists < 0 )
                    goto LABEL_175;
LABEL_179:
                  if ( (*((_BYTE *)v25 + 144) & 1) == 0
                    || (v60 = *((_QWORD *)v25 + 14)) == 0
                    || (v61 = *(_BYTE *)(v60 + 164), (v61 & 1) == 0) )
                  {
                    v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
                    v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
                    v74 = 1126;
                    v46 = "Element->fInitializedInHierarchy && Element->SharedInfo && Element->SharedInfo->fInitializedInHierarchy";
                    goto LABEL_213;
                  }
                  v62 = v79;
                  if ( (v79 & 0x2000) != 0 )
                    *(_BYTE *)(v60 + 164) = v61 | 8;
                  *(_OWORD *)v88 = 0;
                  v63 = *(_QWORD *)&v77[1];
                  exists = Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedHandleObject::Create(
                             v25,
                             (struct Windows::Rtl::SystemImplementation::CSilHandle *)v88,
                             *(struct Windows::Rtl::SystemImplementation::IRtlObjectProvider **)&v77[1]);
                  if ( exists < 0 )
                  {
                    Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v88);
                    if ( v88[0] )
                      (**(void (__fastcall ***)(void *))v88[0])(v88[0]);
LABEL_175:
                    Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v97);
                    Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v103);
                    if ( v87.Buffer )
                    {
                      anonymous_namespace_::OurRtlFreeStringRoutine(v87.Buffer);
                      v87 = 0;
                    }
                    if ( v30 )
                      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
                    return (unsigned int)exists;
                  }
                  v64 = *((_QWORD *)v25 + 17);
                  if ( v64 == -1 )
                  {
                    v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
                    v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
                    v74 = 1139;
                    v75 = "BUCL::Rtl::Increment(Element->HandleCount)";
                    RtlReportErrorOrigination(v73, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225621LL);
                    Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v88);
                    if ( v88[0] )
                      (**(void (__fastcall ***)(void *))v88[0])(v88[0]);
                    Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v97);
                    Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v103);
                    if ( v87.Buffer )
                    {
                      anonymous_namespace_::OurRtlFreeStringRoutine(v87.Buffer);
                      v87 = 0;
                    }
                    if ( v30 )
                      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
                    return 3221225621LL;
                  }
                  *((_QWORD *)v25 + 17) = v64 + 1;
                  v65 = v88[1];
                  if ( !v72 )
                  {
                    v66 = Windows::Rtl::SecurityDescriptor::Get((Windows::Rtl::SecurityDescriptor *)&v97);
                    if ( (v62 & 0x20000) != 0 )
                    {
                      inserted = Windows::Rtl::SystemImplementation::IRtlObjectProvider::EnsureSetSecurityIfRequired(
                                   v63,
                                   v65,
                                   v66,
                                   0);
                      if ( inserted < 0 )
                      {
                        Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v88);
                        if ( v88[0] )
LABEL_192:
                          (**(void (__fastcall ***)(void *))v88[0])(v88[0]);
LABEL_164:
                        Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v97);
                        Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v103);
                        if ( v87.Buffer )
                        {
                          anonymous_namespace_::OurRtlFreeStringRoutine(v87.Buffer);
                          v87 = 0;
                        }
                        if ( v30 )
                          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
                        return (unsigned int)inserted;
                      }
                      v63 = *(_QWORD *)&v77[1];
                    }
                    inserted = Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::EnsureSetAttributesIfRequired(
                                 v63,
                                 v62,
                                 v65,
                                 a8,
                                 0);
                    if ( inserted < 0 )
                    {
                      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v88);
                      if ( !v88[0] )
                        goto LABEL_164;
                      goto LABEL_192;
                    }
                  }
                  v67 = (_DWORD *)v81;
                  *(_QWORD *)(v81 + 8) = (v72 != 0) + 1LL;
                  *v67 = 0;
                  if ( a15 )
                    *a15 = 1;
                  v68 = v82;
                  v88[1] = v82[1];
                  v82[1] = v65;
                  v69 = *v68;
                  *v68 = v88[0];
                  v88[0] = v69;
                  Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v88);
                  if ( v88[0] )
                    (**(void (__fastcall ***)(void *))v88[0])(v88[0]);
                  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v97);
                  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v103);
                  if ( v87.Buffer )
                  {
                    anonymous_namespace_::OurRtlFreeStringRoutine(v87.Buffer);
                    v87 = 0;
                  }
                  if ( v30 )
                    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
                  return 0;
                }
                v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
                v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
                v74 = 1088;
                v75 = "SharedInfo.get()";
                RtlReportErrorOrigination(v73, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
                Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v97);
                Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v103);
LABEL_156:
                if ( v87.Buffer )
                {
                  anonymous_namespace_::OurRtlFreeStringRoutine(v87.Buffer);
                  v87 = 0;
                }
                if ( v30 )
                  utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
                return 3221225495LL;
              }
              Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v94);
            }
            Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v88);
            v51 = (void (__fastcall ***)(_QWORD))v88[0];
            if ( v88[0] )
            {
              v88[0] = 0;
              (**v51)(v51);
            }
            goto LABEL_124;
          }
          break;
        case 2u:
          goto LABEL_77;
        case 3u:
          LODWORD(v91) = 0;
          v32 = Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::AccessMaskFilter(0, v78[0]);
          UniqueFileIdOrZero = Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::SysOpenFile(
                                 *(_QWORD *)(*(_QWORD *)&v77[1] + 200LL),
                                 v15 & 0xFFE1FFFD | 0x100002,
                                 v88,
                                 v32,
                                 &v84,
                                 a9,
                                 a11,
                                 v33,
                                 &v91);
          if ( UniqueFileIdOrZero >= 0 )
          {
            v34 = v91;
            if ( (_DWORD)v91 != 3 && (_DWORD)v91 != 15 )
            {
              v90 = v91;
              v35 = *(Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider **)&v77[1];
              goto LABEL_86;
            }
LABEL_77:
            v72 = 1;
            v30 = (volatile signed __int32 *)v73[1];
            v31 = v73[0];
            goto LABEL_105;
          }
          break;
        case 5u:
          goto LABEL_77;
        default:
          INTERNAL_ERROR_ACTION(-1073741595);
          JUMPOUT(0x18015B515LL);
      }
      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v88);
      v39 = (void (__fastcall ***)(_QWORD))v88[0];
      if ( v88[0] )
      {
        v88[0] = 0;
        (**v39)(v39);
      }
      goto LABEL_58;
    }
LABEL_35:
    if ( v87.Buffer )
      anonymous_namespace_::OurRtlFreeStringRoutine(v87.Buffer);
    return (unsigned int)exists;
  }
  if ( (*((_BYTE *)v80 + 144) & 2) != 0 )
  {
    if ( a10 == 1 )
    {
      if ( (v15 & 2) != 0 )
      {
        if ( a15 )
          *a15 = 3;
        goto LABEL_22;
      }
      v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
      v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
      v74 = 837;
      v75 = 0;
      RtlReportErrorOrigination(v73, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225524LL);
      if ( v87.Buffer )
        anonymous_namespace_::OurRtlFreeStringRoutine(v87.Buffer);
      return 3221225524LL;
    }
  }
  else if ( a10 == 2 )
  {
    if ( (v15 & 1) != 0 )
    {
      if ( a15 )
        *a15 = 2;
LABEL_22:
      v27 = v87.Buffer;
LABEL_223:
      if ( v27 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v27);
      return 0;
    }
    v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
    v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
    v74 = 821;
    v75 = 0;
    RtlReportErrorOrigination(v73, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225525LL);
    if ( v87.Buffer )
      anonymous_namespace_::OurRtlFreeStringRoutine(v87.Buffer);
    return 3221225525LL;
  }
  if ( a10 == 5 )
  {
    exists = Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::DeleteElement(v23, v80);
    if ( exists < 0 )
      goto LABEL_35;
    v16 = *(_QWORD *)&v77[1];
    LOBYTE(v23) = v77[0];
  }
  if ( (*((_BYTE *)v25 + 144) & 2) != 0 )
  {
    v72 = 1;
LABEL_65:
    v30 = (volatile signed __int32 *)v73[1];
    v31 = v73[0];
    goto LABEL_107;
  }
  if ( ((a10 - 1) & 0xFFFFFFFD) != 0 )
  {
LABEL_57:
    v90 = 0;
    UniqueFileIdOrZero = Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::CheckOpenLowerHandle(
                           (Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider *)v16,
                           v15,
                           v78[0],
                           *((struct Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::SharedFileInfo **)v25
                           + 14),
                           &v90);
    if ( UniqueFileIdOrZero < 0 )
    {
LABEL_58:
      if ( v87.Buffer )
        anonymous_namespace_::OurRtlFreeStringRoutine(v87.Buffer);
      return (unsigned int)UniqueFileIdOrZero;
    }
    if ( v90 != 1 )
    {
      if ( a15 )
        *a15 = v90;
      goto LABEL_22;
    }
    goto LABEL_65;
  }
  if ( !(_BYTE)v23 || (*(_BYTE *)(*((_QWORD *)v25 + 14) + 80LL) & 0x10) != 0 )
  {
    if ( BYTE1(v77[0]) && (*(_BYTE *)(*((_QWORD *)v25 + 14) + 80LL) & 0x10) != 0 )
    {
      if ( (v15 & 0x80u) != 0 )
      {
        if ( a15 )
          *a15 = 9;
        goto LABEL_22;
      }
      v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
      v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
      v74 = 874;
      v75 = 0;
      RtlReportErrorOrigination(v73, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225658LL);
      if ( v87.Buffer )
        anonymous_namespace_::OurRtlFreeStringRoutine(v87.Buffer);
      return 3221225658LL;
    }
    goto LABEL_57;
  }
  if ( (v15 & 0x100) != 0 )
  {
    if ( a15 )
      *a15 = 10;
    goto LABEL_22;
  }
  v73[0] = (utl::_RefCountBase *)"onecore\\base\\wcp\\sil\\fs_buffered.cpp";
  v73[1] = (utl::_RefCountBase *)"Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::SysCreateFile";
  v74 = 862;
  v75 = 0;
  RtlReportErrorOrigination(v73, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225731LL);
  if ( v87.Buffer )
    anonymous_namespace_::OurRtlFreeStringRoutine(v87.Buffer);
  return 3221225731LL;
}

```

## disassembly

```asm
0x18015a2c0  push    rbp
0x18015a2c2  push    rbx
0x18015a2c3  push    rsi
0x18015a2c4  push    rdi
0x18015a2c5  push    r12
0x18015a2c7  push    r13
0x18015a2c9  push    r14
0x18015a2cb  push    r15
0x18015a2cd  lea     rbp, [rsp-0F8h]
0x18015a2d5  sub     rsp, 1F8h
0x18015a2dc  mov     [rbp+130h+var_180], 0FFFFFFFFFFFFFFFEh
0x18015a2e4  mov     rax, cs:__security_cookie
0x18015a2eb  xor     rax, rsp
0x18015a2ee  mov     [rbp+130h+var_50], rax
0x18015a2f5  mov     [rbp+130h+var_188], r8
0x18015a2f9  mov     r12d, edx
0x18015a2fc  mov     [rbp+130h+var_1A0], edx
0x18015a2ff  mov     r14, rcx
0x18015a302  mov     qword ptr [rbp+130h+var_1B4+4], rcx
0x18015a306  mov     rax, [rbp+130h+arg_28]
0x18015a30d  mov     [rbp+130h+var_190], rax
0x18015a311  mov     rsi, [rbp+130h+arg_20]
0x18015a318  mov     rdi, [rbp+130h+arg_70]
0x18015a31f  xor     r15d, r15d
0x18015a322  test    rdi, rdi
0x18015a325  jz      short loc_18015A32A
0x18015a327  mov     [rdi], r15d
0x18015a32a  cmp     [rbp+130h+arg_58], r15
0x18015a331  jz      short loc_18015A360
0x18015a333  lea     rax, aOnecoreBaseWcp_26; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x18015a33a  mov     [rsp+230h+var_1D8], rax
0x18015a33f  lea     rax, aWindowsRtlSyst_129; "Windows::Rtl::SystemImplementation::CBu"...
0x18015a346  mov     [rsp+230h+var_1D8+8], rax
0x18015a34b  mov     [rsp+230h+var_1C8], 30Ah
0x18015a354  lea     rax, aEabuffer; "!EaBuffer"
0x18015a35b  jmp     loc_18015B4C6
0x18015a360  cmp     [rbp+130h+arg_60], r15d
0x18015a367  jz      short loc_18015A396
0x18015a369  lea     rax, aOnecoreBaseWcp_26; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x18015a370  mov     [rsp+230h+var_1D8], rax
0x18015a375  lea     rax, aWindowsRtlSyst_129; "Windows::Rtl::SystemImplementation::CBu"...
0x18015a37c  mov     [rsp+230h+var_1D8+8], rax
0x18015a381  mov     [rsp+230h+var_1C8], 30Bh
0x18015a38a  lea     rax, aEalength; "!EaLength"
0x18015a391  jmp     loc_18015B4C6
0x18015a396  mov     ecx, dword ptr [rbp+130h+arg_50]; this
0x18015a39c  test    cl, 20h
0x18015a39f  jnz     short loc_18015A3CE
0x18015a3a1  lea     rax, aOnecoreBaseWcp_26; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x18015a3a8  mov     [rsp+230h+var_1D8], rax
0x18015a3ad  lea     rax, aWindowsRtlSyst_129; "Windows::Rtl::SystemImplementation::CBu"...
0x18015a3b4  mov     [rsp+230h+var_1D8+8], rax
0x18015a3b9  mov     [rsp+230h+var_1C8], 30Ch
0x18015a3c2  lea     rax, aCreateoptions; "CreateOptions"
0x18015a3c9  jmp     loc_18015B4C6
0x18015a3ce  cmp     [rbp+130h+arg_68], r15
0x18015a3d5  jnz     loc_18015B49E
0x18015a3db  xorps   xmm0, xmm0
0x18015a3de  movdqu  xmmword ptr [rsp+230h+var_1D8], xmm0
0x18015a3e4  mov     [rbp+130h+var_198], r15
0x18015a3e8  bts     r9d, 7
0x18015a3ed  mov     edx, r9d; unsigned int
0x18015a3f0  call    ?AccessMaskFilter@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAKK@Z; Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::AccessMaskFilter(ulong)
0x18015a3f5  mov     [rbp+130h+var_1A8], eax
0x18015a3f8  mov     word ptr [rsp+230h+var_1B4], r15w
0x18015a3fe  mov     [rsp+230h+var_1B4+2], r15b
0x18015a403  lea     r8, [rsp+230h+var_1B4]; unsigned int
0x18015a408  mov     ebx, [rbp+130h+arg_48]
0x18015a40e  mov     edx, ebx; unsigned int
0x18015a410  call    ?ParseOptionsDisposition@SystemImplementation@Rtl@Windows@@YAJKKAEAUParsedOptionsDisposition@123@@Z; Windows::Rtl::SystemImplementation::ParseOptionsDisposition(ulong,ulong,Windows::Rtl::SystemImplementation::ParsedOptionsDisposition &)
0x18015a415  test    eax, eax
0x18015a417  js      loc_18015B4E7
0x18015a41d  xorps   xmm0, xmm0
0x18015a420  movups  xmmword ptr [rbp+130h+var_140.Length], xmm0
0x18015a424  xorps   xmm1, xmm1
0x18015a427  movups  [rbp+130h+var_178], xmm1
0x18015a42b  movups  [rbp+130h+var_168], xmm1
0x18015a42f  movups  xmmword ptr [rbp+130h+var_158], xmm1
0x18015a433  lea     r9, [rbp+130h+var_178]
0x18015a437  lea     r8, [rbp+130h+var_140]
0x18015a43b  mov     rdx, rsi
0x18015a43e  mov     rcx, r14
0x18015a441  call    ?CanonicalizePath@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJAEBU_OBJECT_ATTRIBUTES@@PEAV?$Auto@U_UNICODE_STRING@@@4@PEAU5@@Z; Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::CanonicalizePath(_OBJECT_ATTRIBUTES const &,Windows::Auto<_UNICODE_STRING> *,_OBJECT_ATTRIBUTES *)
0x18015a446  mov     esi, eax
0x18015a448  test    eax, eax
0x18015a44a  jns     short loc_18015A461
0x18015a44c  mov     rcx, [rbp+130h+var_140.Buffer]
0x18015a450  test    rcx, rcx
0x18015a453  jz      short loc_18015A45A
0x18015a455  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18015a45a  mov     eax, esi
0x18015a45c  jmp     loc_18015B4E7
0x18015a461  lea     rcx, [r14+28h]; this
0x18015a465  movzx   eax, [rbp+130h+var_140.Length]
0x18015a469  mov     [rbp+130h+var_130], rax
0x18015a46d  movzx   eax, [rbp+130h+var_140.MaximumLength]
0x18015a471  mov     [rbp+130h+var_130+8], rax
0x18015a475  mov     rax, [rbp+130h+var_140.Buffer]
0x18015a479  mov     [rbp+130h+var_120], rax
0x18015a47d  lea     r9, [rbp+130h+var_198]; struct Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement **
0x18015a481  lea     r8, [rbp+130h+var_130]; struct _LUNICODE_STRING *
0x18015a485  call    ?FindFile@CBufferedFileHierarchy@SystemImplementation@Rtl@Windows@@QEAAJPEAUBufferedPathElement@1234@AEBU_LUNICODE_STRING@@PEAPEAU51234@@Z; Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::FindFile(Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *,_LUNICODE_STRING const &,Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement * *)
0x18015a48a  mov     esi, eax
0x18015a48c  xor     edx, edx
0x18015a48e  test    eax, eax
0x18015a490  js      short loc_18015A44C
0x18015a492  mov     [rsp+230h+var_1E0], dl
0x18015a496  mov     cl, [rsp+230h+var_1B4]; this
0x18015a49a  mov     r13, [rbp+130h+var_198]
0x18015a49e  lea     esi, [rdx+1]
0x18015a4a1  lea     r15d, [rdx+2]
0x18015a4a5  test    r13, r13
0x18015a4a8  jz      loc_18015A746
0x18015a4ae  test    [r13+90h], r15b
0x18015a4b5  jnz     short loc_18015A52B
0x18015a4b7  cmp     ebx, r15d
0x18015a4ba  jnz     loc_18015A596
0x18015a4c0  test    sil, r12b
0x18015a4c3  jz      short loc_18015A4D6
0x18015a4c5  test    rdi, rdi
0x18015a4c8  jz      short loc_18015A4CD
0x18015a4ca  mov     [rdi], r15d
0x18015a4cd  mov     rcx, [rbp+130h+var_140.Buffer]
0x18015a4d1  jmp     loc_18015B490
0x18015a4d6  lea     rax, aOnecoreBaseWcp_26; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x18015a4dd  mov     [rsp+230h+var_1D8], rax
0x18015a4e2  lea     rax, aWindowsRtlSyst_129; "Windows::Rtl::SystemImplementation::CBu"...
0x18015a4e9  mov     [rsp+230h+var_1D8+8], rax
0x18015a4ee  mov     [rsp+230h+var_1C8], 335h
0x18015a4f7  mov     [rsp+230h+var_1C0], rdx
0x18015a4fc  mov     r8d, 0C0000035h
0x18015a502  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18015a509  lea     rcx, [rsp+230h+var_1D8]
0x18015a50e  call    RtlReportErrorOrigination
0x18015a513  mov     rcx, [rbp+130h+var_140.Buffer]
0x18015a517  test    rcx, rcx
0x18015a51a  jz      short loc_18015A521
0x18015a51c  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18015a521  mov     eax, 0C0000035h
0x18015a526  jmp     loc_18015B4E7
0x18015a52b  cmp     ebx, esi
0x18015a52d  jnz     short loc_18015A596
0x18015a52f  test    r15b, r12b
0x18015a532  jz      short loc_18015A541
0x18015a534  test    rdi, rdi
0x18015a537  jz      short loc_18015A4CD
0x18015a539  mov     dword ptr [rdi], 3
0x18015a53f  jmp     short loc_18015A4CD
0x18015a541  lea     rax, aOnecoreBaseWcp_26; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x18015a548  mov     [rsp+230h+var_1D8], rax
0x18015a54d  lea     rax, aWindowsRtlSyst_129; "Windows::Rtl::SystemImplementation::CBu"...
0x18015a554  mov     [rsp+230h+var_1D8+8], rax
0x18015a559  mov     [rsp+230h+var_1C8], 345h
0x18015a562  mov     [rsp+230h+var_1C0], rdx
0x18015a567  mov     r8d, 0C0000034h
0x18015a56d  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18015a574  lea     rcx, [rsp+230h+var_1D8]
0x18015a579  call    RtlReportErrorOrigination
0x18015a57e  mov     rcx, [rbp+130h+var_140.Buffer]
0x18015a582  test    rcx, rcx
0x18015a585  jz      short loc_18015A58C
0x18015a587  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18015a58c  mov     eax, 0C0000034h
0x18015a591  jmp     loc_18015B4E7
0x18015a596  cmp     ebx, 5
0x18015a599  jnz     short loc_18015A5CA
0x18015a59b  mov     rdx, r13; struct Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *
0x18015a59e  call    ?DeleteElement@CBufferedFileHierarchy@SystemImplementation@Rtl@Windows@@QEAAJPEAUBufferedPathElement@1234@@Z; Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::DeleteElement(Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *)
0x18015a5a3  mov     r14d, eax
0x18015a5a6  xor     edx, edx
0x18015a5a8  test    eax, eax
0x18015a5aa  jns     short loc_18015A5C2
0x18015a5ac  mov     rcx, [rbp+130h+var_140.Buffer]
0x18015a5b0  test    rcx, rcx
0x18015a5b3  jz      short loc_18015A5BA
0x18015a5b5  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18015a5ba  mov     eax, r14d
0x18015a5bd  jmp     loc_18015B4E7
0x18015a5c2  mov     r14, qword ptr [rbp+130h+var_1B4+4]
0x18015a5c6  mov     cl, [rsp+230h+var_1B4]
0x18015a5ca  test    [r13+90h], r15b
0x18015a5d1  jnz     loc_18015A732
0x18015a5d7  lea     eax, [rbx-1]
0x18015a5da  test    eax, 0FFFFFFFDh
0x18015a5df  jnz     loc_18015A6E1
0x18015a5e5  test    cl, cl
0x18015a5e7  jz      short loc_18015A663
0x18015a5e9  mov     rax, [r13+70h]
0x18015a5ed  test    byte ptr [rax+50h], 10h
0x18015a5f1  jnz     short loc_18015A663
0x18015a5f3  bt      r12d, 8
0x18015a5f8  jnb     short loc_18015A60E
0x18015a5fa  test    rdi, rdi
0x18015a5fd  jz      loc_18015A4CD
0x18015a603  mov     dword ptr [rdi], 0Ah
0x18015a609  jmp     loc_18015A4CD
0x18015a60e  lea     rax, aOnecoreBaseWcp_26; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x18015a615  mov     [rsp+230h+var_1D8], rax
0x18015a61a  lea     rax, aWindowsRtlSyst_129; "Windows::Rtl::SystemImplementation::CBu"...
0x18015a621  mov     [rsp+230h+var_1D8+8], rax
0x18015a626  mov     [rsp+230h+var_1C8], 35Eh
0x18015a62f  mov     [rsp+230h+var_1C0], rdx
0x18015a634  mov     r8d, 0C0000103h
0x18015a63a  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18015a641  lea     rcx, [rsp+230h+var_1D8]
0x18015a646  call    RtlReportErrorOrigination
0x18015a64b  mov     rcx, [rbp+130h+var_140.Buffer]
0x18015a64f  test    rcx, rcx
0x18015a652  jz      short loc_18015A659
0x18015a654  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18015a659  mov     eax, 0C0000103h
0x18015a65e  jmp     loc_18015B4E7
0x18015a663  cmp     [rsp+230h+var_1B4+1], dl
0x18015a667  jz      short loc_18015A6E1
0x18015a669  mov     rax, [r13+70h]
0x18015a66d  test    byte ptr [rax+50h], 10h
0x18015a671  jz      short loc_18015A6E1
0x18015a673  test    r12b, r12b
0x18015a676  jns     short loc_18015A68C
0x18015a678  test    rdi, rdi
0x18015a67b  jz      loc_18015A4CD
0x18015a681  mov     dword ptr [rdi], 9
0x18015a687  jmp     loc_18015A4CD
0x18015a68c  lea     rax, aOnecoreBaseWcp_26; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x18015a693  mov     [rsp+230h+var_1D8], rax
0x18015a698  lea     rax, aWindowsRtlSyst_129; "Windows::Rtl::SystemImplementation::CBu"...
0x18015a69f  mov     [rsp+230h+var_1D8+8], rax
0x18015a6a4  mov     [rsp+230h+var_1C8], 36Ah
0x18015a6ad  mov     [rsp+230h+var_1C0], rdx
0x18015a6b2  mov     r8d, 0C00000BAh
0x18015a6b8  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18015a6bf  lea     rcx, [rsp+230h+var_1D8]
0x18015a6c4  call    RtlReportErrorOrigination
0x18015a6c9  mov     rcx, [rbp+130h+var_140.Buffer]
0x18015a6cd  test    rcx, rcx
0x18015a6d0  jz      short loc_18015A6D7
0x18015a6d2  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18015a6d7  mov     eax, 0C00000BAh
0x18015a6dc  jmp     loc_18015B4E7
0x18015a6e1  mov     [rbp+130h+var_118], edx
0x18015a6e4  lea     rax, [rbp+130h+var_118]
0x18015a6e8  mov     [rsp+230h+var_210], rax; unsigned int *
0x18015a6ed  mov     r9, [r13+70h]; struct Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::SharedFileInfo *
0x18015a6f1  mov     r8d, [rbp+130h+var_1A8]; unsigned int
0x18015a6f5  mov     edx, r12d; unsigned int
0x18015a6f8  mov     rcx, r14; this
0x18015a6fb  call    ?CheckOpenLowerHandle@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJKKAEAUSharedFileInfo@CBufferedFileHierarchy@234@PEAK@Z; Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::CheckOpenLowerHandle(ulong,ulong,Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::SharedFileInfo &,ulong *)
0x18015a700  mov     ebx, eax
0x18015a702  test    eax, eax
0x18015a704  jns     short loc_18015A71B
0x18015a706  mov     rcx, [rbp+130h+var_140.Buffer]
0x18015a70a  test    rcx, rcx
0x18015a70d  jz      short loc_18015A714
0x18015a70f  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18015a714  mov     eax, ebx
0x18015a716  jmp     loc_18015B4E7
0x18015a71b  mov     eax, [rbp+130h+var_118]
0x18015a71e  cmp     eax, esi
0x18015a720  jz      short loc_18015A737
0x18015a722  test    rdi, rdi
0x18015a725  jz      loc_18015A4CD
0x18015a72b  mov     [rdi], eax
0x18015a72d  jmp     loc_18015A4CD
0x18015a732  mov     [rsp+230h+var_1E0], sil
0x18015a737  mov     rbx, [rsp+230h+var_1D8+8]
0x18015a73c  mov     r14, [rsp+230h+var_1D8]
0x18015a741  jmp     loc_18015AA15
0x18015a746  cmp     ebx, r15d
0x18015a749  jnz     short loc_18015A76D
0x18015a74b  test    sil, r12b
0x18015a74e  jnz     short loc_18015A76D
0x18015a750  lea     rdx, [rbp+130h+var_140]; struct _UNICODE_STRING *
0x18015a754  mov     rcx, r14; this
0x18015a757  call    ?AssertFileExistence@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJAEBU_UNICODE_STRING@@_N@Z; Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::AssertFileExistence(_UNICODE_STRING const &,bool)
0x18015a75c  mov     r14d, eax
0x18015a75f  xor     edx, edx
0x18015a761  test    eax, eax
0x18015a763  js      loc_18015A5AC
0x18015a769  mov     r14, qword ptr [rbp+130h+var_1B4+4]
0x18015a76d  test    r15b, r12b
0x18015a770  jnz     short loc_18015A78F
0x18015a772  cmp     ebx, esi
0x18015a774  jz      short loc_18015A78F
0x18015a776  lea     rdx, [rbp+130h+var_140]; struct _UNICODE_STRING *
0x18015a77a  mov     rcx, r14; this
0x18015a77d  call    ?AssertParentDirectoryExistsSomewhere@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJAEBU_UNICODE_STRING@@@Z; Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::AssertParentDirectoryExistsSomewhere(_UNICODE_STRING const &)
0x18015a782  mov     r14d, eax
0x18015a785  xor     edx, edx
0x18015a787  test    eax, eax
0x18015a789  js      loc_18015A5AC
0x18015a78f  xorps   xmm0, xmm0
0x18015a792  movdqu  xmmword ptr [rbp+130h+var_130], xmm0
0x18015a797  mov     [rbp+130h+var_118], edx
0x18015a79a  sub     ebx, esi
0x18015a79c  jz      loc_18015A854
0x18015a7a2  sub     ebx, esi
0x18015a7a4  jz      short loc_18015A7B3
0x18015a7a6  sub     ebx, esi
0x18015a7a8  jz      short loc_18015A7C7
0x18015a7aa  cmp     ebx, r15d
  ... truncated ...
```
