# winreBuildCanDeleteMap(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<bool>> &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<bool>> &)

- ea: `0x18003552c`
- end: `0x180035c6c`
- name: `?winreBuildCanDeleteMap@@YAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@2@AEAV?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_NV?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@_N@2@@2@2@Z`
- size: `1856`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800346cc`

## callees

- `0x180004978`
- `0x180004af8`
- `0x1800050bc`
- `0x180005c70`
- `0x1800074b8`
- `0x18000d92c`
- `0x180011ef4`
- `0x180033a88`
- `0x180033b18`
- `0x180033be0`
- `0x180033c44`
- `0x180033c94`
- `0x180033fbc`
- `0x180034098`
- `0x1800340cc`
- `0x18003552c`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18004cc1c`
- `0x18004d7a0`
- `0x18004e9dc`
- `0x18004ea8c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180035b1f`
- `msvcrt!_wcsicmp` at `0x180035b1f`

## string_xrefs

- `0x18003584a`: `base\diagnosis\srt\winreagent\lib\api\src\enumeration.cpp`
- `0x180035969`: `base\diagnosis\srt\winreagent\lib\api\src\enumeration.cpp`
- `0x180035a16`: `base\diagnosis\srt\winreagent\lib\api\src\enumeration.cpp`
- `0x180035baa`: `base\diagnosis\srt\winreagent\lib\api\src\enumeration.cpp`
- `0x1800355c6`: `Get unexpected path info [%s]`
- `0x1800355ef`: `Get path info in unexpected format: [%s]`
- `0x180035c03`: `Unexpected path type [%c]`
- `0x18003566d`: `Get empty path info [%s]`
- `0x1800356ac`: `[%s] is a format of directory without a directory type`
- `0x180035836`: `Failed to construt full path of [%s]`
- `0x180035851`: `winreBuildCanDeleteMap`
- `0x180035970`: `winreBuildCanDeleteMap`
- `0x180035a1d`: `winreBuildCanDeleteMap`
- `0x180035bb1`: `winreBuildCanDeleteMap`
- `0x180035955`: `Failed to enum path [%s] in [%s]`
- `0x180035a02`: `Failed to construct full path of [%s] in [%s]`
- `0x180035b96`: `Failed to get directory of [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall winreBuildCanDeleteMap(const wchar_t **a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rbx
  const wchar_t **v6; // r13
  int Directory; // r15d
  __int64 v8; // r8
  unsigned __int64 v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // rbx
  int v12; // edi
  unsigned int v13; // ebx
  int v14; // r12d
  __int64 v15; // rsi
  int v16; // ebx
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  int *v19; // rbx
  __int64 v20; // rsi
  wchar_t *v21; // rcx
  int *v22; // rdi
  __int64 v23; // rbx
  _QWORD *v24; // rcx
  int *v25; // rdi
  __int64 v26; // rbx
  int v27; // eax
  __int64 v28; // rbx
  ATL::CStringData *v29; // rcx
  __int64 v30; // rdx
  _QWORD *v31; // rcx
  int *v32; // rdi
  __int64 v33; // rbx
  __int64 v34; // r8
  wchar_t *v35; // rdi
  __int64 v36; // rbx
  __int64 v37; // r12
  unsigned __int64 v38; // r13
  int v39; // esi
  _QWORD *v40; // rax
  __int64 v41; // rbx
  __int64 v42; // rdi
  ATL::CStringData *v43; // rcx
  __int64 v44; // rdi
  __int64 v45; // rbx
  char IsFile; // al
  __int64 v47; // rcx
  wchar_t *v48; // rbx
  char v49; // al
  __int64 v50; // rbx
  unsigned __int16 v51; // ax
  char v53[8]; // [rsp+48h] [rbp-79h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-71h] BYREF
  __int64 v55; // [rsp+58h] [rbp-69h] BYREF
  __int64 v56; // [rsp+60h] [rbp-61h] BYREF
  __int64 v57; // [rsp+68h] [rbp-59h] BYREF
  int v58; // [rsp+70h] [rbp-51h]
  __int64 v59; // [rsp+78h] [rbp-49h] BYREF
  __int64 v60; // [rsp+80h] [rbp-41h] BYREF
  __int64 v61; // [rsp+88h] [rbp-39h] BYREF
  __int64 v62; // [rsp+90h] [rbp-31h] BYREF
  unsigned __int64 v63; // [rsp+98h] [rbp-29h]
  __int64 v64; // [rsp+A0h] [rbp-21h] BYREF
  unsigned __int64 v65; // [rsp+A8h] [rbp-19h]
  __int64 v66; // [rsp+B0h] [rbp-11h]
  int v67; // [rsp+B8h] [rbp-9h]
  __int64 v68; // [rsp+C0h] [rbp-1h] BYREF
  __int64 v69; // [rsp+C8h] [rbp+7h] BYREF
  ATL::CStringData *v70; // [rsp+D0h] [rbp+Fh]

  v5 = a2;
  v6 = a1;
  if ( a2 && *(_QWORD *)(a2 + 8) )
  {
    Directory = 0;
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::RemoveAll(a3);
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::RemoveAll(a4);
    v9 = 0;
    v63 = 0;
    if ( *(_QWORD *)(v5 + 8) )
    {
      do
      {
        v10 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                          v5,
                          v9,
                          v8);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v59,
          v10);
        v11 = v59;
        v70 = (ATL::CStringData *)(v59 - 24);
        v12 = *(_DWORD *)(v59 - 24 + 8);
        if ( v12 >= 3 )
        {
          if ( (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(&v59, (unsigned int)(v12 - 2)) == 44 )
          {
            v13 = v12 - 1;
            if ( (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(&v59, (unsigned int)(v12 - 1)) == 70 )
            {
              v14 = 1;
            }
            else if ( (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(&v59, v13) == 68 )
            {
              v14 = 2;
            }
            else
            {
              if ( (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(&v59, v13) != 80 )
              {
                v51 = ATL::CSimpleStringT<unsigned short,0>::GetAt(&v59, v13);
                PushButtonReset::Logging::Trace(1, L"Unexpected path type [%c]", v51);
                goto LABEL_81;
              }
              v14 = 3;
            }
            v58 = v14;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
              &v59,
              &v56,
              (unsigned int)(v12 - 2));
            v15 = v56;
            if ( !*(_DWORD *)(v56 - 16) )
            {
              PushButtonReset::Logging::Trace(1, L"Get empty path info [%s]", v56);
LABEL_16:
              ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
              goto LABEL_81;
            }
            v16 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::ReverseFind(&v56);
            if ( *(_DWORD *)(v15 - 16) - 1 == v16 )
            {
              if ( v14 == 1 )
              {
                PushButtonReset::Logging::Trace(1, L"[%s] is a format of directory without a directory type", v15);
                goto LABEL_16;
              }
              do
              {
                if ( v16 )
                {
                  v17 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                                     &v56,
                                     &v68,
                                     (unsigned int)v16);
                  v18 = (_QWORD *)(v17 - 24);
                  v19 = (int *)(v15 - 24);
                  if ( v17 - 24 != v15 - 24 )
                  {
                    if ( v19[4] >= 0 && *v18 == *(_QWORD *)v19 )
                    {
                      v20 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v18);
                      ATL::CStringData::Release((ATL::CStringData *)v19);
                      v15 = v20 + 24;
                      v56 = v15;
                    }
                    else
                    {
                      ATL::CSimpleStringT<unsigned short,0>::SetString(&v56, v17, *(unsigned int *)(v17 - 16));
                      v15 = v56;
                    }
                  }
                  ATL::CStringData::Release((ATL::CStringData *)(v68 - 24));
                  v16 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::ReverseFind(&v56);
                }
                else
                {
                  PushButtonReset::Logging::Trace(1, L"[%s] only contains '\\'", v15);
                }
              }
              while ( *(_DWORD *)(v15 - 16) - 1 == v16 );
            }
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&String1);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v57);
            if ( v16 < 0 )
            {
              v21 = (wchar_t *)(*v6 - 12);
              v22 = (int *)(String1 - 12);
              if ( v21 != String1 - 12 )
              {
                if ( v22[4] >= 0 && *(_QWORD *)v21 == *(_QWORD *)v22 )
                {
                  v23 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v21);
                  ATL::CStringData::Release((ATL::CStringData *)v22);
                  String1 = (wchar_t *)(v23 + 24);
                }
                else
                {
                  ATL::CSimpleStringT<unsigned short,0>::SetString(&String1, *v6, *((unsigned int *)*v6 - 4));
                }
              }
              v24 = (_QWORD *)(v15 - 24);
              v25 = (int *)(v57 - 24);
              if ( v15 - 24 != v57 - 24 )
              {
                if ( v25[4] >= 0 && *v24 == *(_QWORD *)v25 )
                {
                  v26 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v24);
                  ATL::CStringData::Release((ATL::CStringData *)v25);
                  v57 = v26 + 24;
                }
                else
                {
                  ATL::CSimpleStringT<unsigned short,0>::SetString(&v57, v15, *(unsigned int *)(v15 - 16));
                }
              }
              goto LABEL_49;
            }
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
              &v56,
              &v60,
              (unsigned int)v16);
            v27 = PushButtonReset::Path::Combine(v6, &v60, &String1);
            if ( v27 < 0 )
            {
              v28 = v60;
              PushButtonReset::Logging::TraceErr(
                1,
                (unsigned int)v27,
                "winreBuildCanDeleteMap",
                "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
                339,
                L"Failed to construt full path of [%s]",
                v60);
              Directory = 0;
              ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
              ATL::CStringData::Release((ATL::CStringData *)(v57 - 24));
              v29 = (ATL::CStringData *)(String1 - 12);
LABEL_42:
              ATL::CStringData::Release(v29);
              goto LABEL_16;
            }
            v30 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Right(
                               &v56,
                               &v69,
                               (unsigned int)(*(_DWORD *)(v15 - 16) - v16 - 1));
            v31 = (_QWORD *)(v30 - 24);
            v32 = (int *)(v57 - 24);
            if ( v30 - 24 != v57 - 24 )
            {
              if ( v32[4] >= 0 && *v31 == *(_QWORD *)v32 )
              {
                v33 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v31);
                ATL::CStringData::Release((ATL::CStringData *)v32);
                v57 = v33 + 24;
              }
              else
              {
                ATL::CSimpleStringT<unsigned short,0>::SetString(&v57, v30, *(unsigned int *)(v30 - 16));
              }
            }
            ATL::CStringData::Release((ATL::CStringData *)(v69 - 24));
            ATL::CStringData::Release((ATL::CStringData *)(v60 - 24));
LABEL_49:
            v64 = 0;
            v65 = 0;
            v66 = 0;
            v67 = 0;
            Directory = PushButtonReset::Directory::EnumMatches(&String1, &v57, &v64);
            if ( Directory < 0 )
            {
              v35 = String1;
              v36 = v57;
              PushButtonReset::Logging::TraceErr(
                1,
                (unsigned int)Directory,
                "winreBuildCanDeleteMap",
                "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
                351,
                L"Failed to enum path [%s] in [%s]",
                v57,
                String1);
              Directory = 0;
              ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v64);
              ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
              v29 = (ATL::CStringData *)(v35 - 12);
              goto LABEL_42;
            }
            v37 = 0;
            v38 = v65;
            if ( !v65 )
            {
LABEL_72:
              v48 = String1;
              v49 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::Lookup(
                      a4,
                      String1,
                      v53);
              v6 = a1;
              while ( !v49 && _wcsicmp(v48, *a1) )
              {
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&String1);
                *(_BYTE *)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::operator[](
                            a4,
                            String1) = 0;
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                  &v62,
                  &String1);
                Directory = PushButtonReset::Path::GetDirectory(&v62, &String1);
                if ( Directory < 0 )
                {
                  v50 = v62;
                  PushButtonReset::Logging::TraceErr(
                    1,
                    (unsigned int)Directory,
                    "winreBuildCanDeleteMap",
                    "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
                    412,
                    L"Failed to get directory of [%s]",
                    v62);
                  Directory = 0;
                  ATL::CStringData::Release((ATL::CStringData *)(v50 - 24));
                  v48 = String1;
                  break;
                }
                ATL::CStringData::Release((ATL::CStringData *)(v62 - 24));
                v48 = String1;
                v49 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::Lookup(
                        a4,
                        String1,
                        v53);
              }
              ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v64);
              ATL::CStringData::Release((ATL::CStringData *)(v57 - 24));
              v29 = (ATL::CStringData *)(v48 - 12);
              goto LABEL_42;
            }
            v39 = v58;
            while ( 2 )
            {
              v40 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                &v64,
                                v37,
                                v34);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                &v61,
                v40);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v55);
              Directory = PushButtonReset::Path::Combine(&String1, &v61, &v55);
              if ( Directory < 0 )
              {
                v41 = v55;
                v42 = v61;
                PushButtonReset::Logging::TraceErr(
                  1,
                  (unsigned int)Directory,
                  "winreBuildCanDeleteMap",
                  "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
                  365,
                  L"Failed to construct full path of [%s] in [%s]",
                  v61,
                  v55);
                Directory = 0;
                ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
                v43 = (ATL::CStringData *)(v42 - 24);
                goto LABEL_70;
              }
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v55);
              switch ( v39 )
              {
                case 1:
                  if ( (unsigned __int8)PushButtonReset::Path::IsFile(&v55) )
                  {
                    v44 = a3;
LABEL_61:
                    v45 = v55;
                    if ( !(unsigned __int8)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::Lookup(
                                             v44,
                                             v55,
                                             v53) )
                      *(_BYTE *)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::operator[](
                                  v44,
                                  v45) = 0;
LABEL_69:
                    ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
                    v43 = (ATL::CStringData *)(v61 - 24);
LABEL_70:
                    ATL::CStringData::Release(v43);
                    if ( ++v37 >= v38 )
                    {
                      v15 = v56;
                      goto LABEL_72;
                    }
                    continue;
                  }
                  break;
                case 2:
                  if ( (unsigned __int8)PushButtonReset::Path::IsDirectory(&v55) )
                  {
                    v44 = a4;
                    goto LABEL_61;
                  }
                  break;
                case 3:
                  IsFile = PushButtonReset::Path::IsFile(&v55);
                  v45 = v55;
                  if ( IsFile )
                    v47 = a3;
                  else
                    v47 = a4;
                  *(_BYTE *)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::operator[](
                              v47,
                              v55) = 1;
                  goto LABEL_69;
              }
              break;
            }
            v45 = v55;
            goto LABEL_69;
          }
          PushButtonReset::Logging::Trace(1, L"Get path info in unexpected format: [%s]", v11);
        }
        else
        {
          PushButtonReset::Logging::Trace(1, L"Get unexpected path info [%s]", v59);
        }
LABEL_81:
        ATL::CStringData::Release(v70);
        v9 = v63 + 1;
        v63 = v9;
        v5 = a2;
      }
      while ( v9 < *(_QWORD *)(a2 + 8) );
    }
    ATL::CStringData::Release((ATL::CStringData *)(*v6 - 12));
    return (unsigned int)Directory;
  }
  else
  {
    ATL::CStringData::Release((ATL::CStringData *)(*a1 - 12));
    return 1;
  }
}

```

## disassembly

```asm
0x18003552c  mov     rax, rsp
0x18003552f  mov     [rax+20h], r9
0x180035533  mov     [rax+18h], r8
0x180035537  mov     [rax+10h], rdx
0x18003553b  mov     [rax+8], rcx
0x18003553f  push    rbp
0x180035540  push    rbx
0x180035541  push    rsi
0x180035542  push    rdi
0x180035543  push    r12
0x180035545  push    r13
0x180035547  push    r14
0x180035549  push    r15
0x18003554b  lea     rbp, [rax-5Fh]
0x18003554f  sub     rsp, 0D8h
0x180035556  mov     r12, r9
0x180035559  mov     rbx, rdx
0x18003555c  mov     r13, rcx
0x18003555f  test    rdx, rdx
0x180035562  jz      loc_180035C47
0x180035568  cmp     qword ptr [rdx+8], 0
0x18003556d  jz      loc_180035C47
0x180035573  xor     r15d, r15d
0x180035576  mov     rcx, r8
0x180035579  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_NV?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@_N@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<bool>>::RemoveAll(void)
0x18003557e  mov     rcx, r12
0x180035581  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_NV?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@_N@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<bool>>::RemoveAll(void)
0x180035586  xor     eax, eax
0x180035588  mov     [rbp+57h+var_80], rax
0x18003558c  cmp     [rbx+8], rax
0x180035590  jbe     loc_180035C35
0x180035596  lea     r14d, [r15+1]
0x18003559a  mov     rdx, rax
0x18003559d  mov     rcx, rbx
0x1800355a0  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x1800355a5  mov     rdx, rax
0x1800355a8  lea     rcx, [rbp+57h+var_A0]
0x1800355ac  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800355b1  nop
0x1800355b2  mov     rbx, [rbp+57h+var_A0]
0x1800355b6  lea     rax, [rbx-18h]
0x1800355ba  mov     [rbp+57h+var_48], rax
0x1800355be  mov     edi, [rax+8]
0x1800355c1  cmp     edi, 3
0x1800355c4  jge     short loc_1800355DD
0x1800355c6  lea     rdx, aGetUnexpectedP; "Get unexpected path info [%s]"
0x1800355cd  mov     r8, rbx
0x1800355d0  mov     ecx, r14d
0x1800355d3  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800355d8  jmp     loc_180035C13
0x1800355dd  lea     edx, [rdi-2]
0x1800355e0  lea     rcx, [rbp+57h+var_A0]
0x1800355e4  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x1800355e9  cmp     ax, 2Ch ; ','
0x1800355ed  jz      short loc_1800355F8
0x1800355ef  lea     rdx, aGetPathInfoInU; "Get path info in unexpected format: [%s"...
0x1800355f6  jmp     short loc_1800355CD
0x1800355f8  lea     ebx, [rdi-1]
0x1800355fb  mov     edx, ebx
0x1800355fd  lea     rcx, [rbp+57h+var_A0]
0x180035601  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x180035606  mov     ecx, 46h ; 'F'
0x18003560b  cmp     cx, ax
0x18003560e  jnz     short loc_180035615
0x180035610  mov     r12d, r14d
0x180035613  jmp     short loc_18003564D
0x180035615  mov     edx, ebx
0x180035617  lea     rcx, [rbp+57h+var_A0]
0x18003561b  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x180035620  mov     ecx, 44h ; 'D'
0x180035625  cmp     cx, ax
0x180035628  jnz     short loc_180035630
0x18003562a  lea     r12d, [rcx-42h]
0x18003562e  jmp     short loc_18003564D
0x180035630  mov     edx, ebx
0x180035632  lea     rcx, [rbp+57h+var_A0]
0x180035636  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18003563b  mov     ecx, 50h ; 'P'
0x180035640  cmp     cx, ax
0x180035643  jnz     loc_180035BF4
0x180035649  lea     r12d, [rcx-4Dh]
0x18003564d  mov     [rbp+57h+var_A8], r12d
0x180035651  lea     r8d, [rdi-2]
0x180035655  lea     rdx, [rbp+57h+var_B8]
0x180035659  lea     rcx, [rbp+57h+var_A0]
0x18003565d  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x180035662  nop
0x180035663  mov     rsi, [rbp+57h+var_B8]
0x180035667  cmp     dword ptr [rsi-10h], 0
0x18003566b  jnz     short loc_18003568E
0x18003566d  lea     rdx, aGetEmptyPathIn; "Get empty path info [%s]"
0x180035674  mov     r8, rsi
0x180035677  mov     ecx, r14d
0x18003567a  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18003567f  nop
0x180035680  lea     rcx, [rsi-18h]; this
0x180035684  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180035689  jmp     loc_180035C13
0x18003568e  lea     rcx, [rbp+57h+var_B8]
0x180035692  call    ?ReverseFind@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::ReverseFind(ushort)
0x180035697  mov     ebx, eax
0x180035699  mov     ecx, [rsi-10h]
0x18003569c  sub     ecx, r14d
0x18003569f  cmp     ecx, eax
0x1800356a1  jnz     loc_18003574D
0x1800356a7  cmp     r12d, r14d
0x1800356aa  jnz     short loc_1800356B5
0x1800356ac  lea     rdx, aSIsAFormatOfDi; "[%s] is a format of directory without a"...
0x1800356b3  jmp     short loc_180035674
0x1800356b5  test    ebx, ebx
0x1800356b7  jnz     short loc_1800356CD
0x1800356b9  mov     r8, rsi
0x1800356bc  lea     rdx, aSOnlyContains; "[%s] only contains '\\'"
0x1800356c3  mov     ecx, r14d
0x1800356c6  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800356cb  jmp     short loc_18003573F
0x1800356cd  mov     r8d, ebx
0x1800356d0  lea     rdx, [rbp+57h+var_58]
0x1800356d4  lea     rcx, [rbp+57h+var_B8]
0x1800356d8  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x1800356dd  nop
0x1800356de  mov     rdx, [rax]
0x1800356e1  lea     rcx, [rdx-18h]
0x1800356e5  lea     rbx, [rsi-18h]
0x1800356e9  cmp     rcx, rbx
0x1800356ec  jz      short loc_180035727
0x1800356ee  cmp     dword ptr [rbx+10h], 0
0x1800356f2  jl      short loc_180035716
0x1800356f4  mov     rax, [rbx]
0x1800356f7  cmp     [rcx], rax
0x1800356fa  jnz     short loc_180035716
0x1800356fc  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180035701  mov     rsi, rax
0x180035704  mov     rcx, rbx; this
0x180035707  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003570c  add     rsi, 18h
0x180035710  mov     [rbp+57h+var_B8], rsi
0x180035714  jmp     short loc_180035727
0x180035716  mov     r8d, [rdx-10h]
0x18003571a  lea     rcx, [rbp+57h+var_B8]
0x18003571e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180035723  mov     rsi, [rbp+57h+var_B8]
0x180035727  mov     rcx, [rbp+57h+var_58]
0x18003572b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003572f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180035734  lea     rcx, [rbp+57h+var_B8]
0x180035738  call    ?ReverseFind@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::ReverseFind(ushort)
0x18003573d  mov     ebx, eax
0x18003573f  mov     eax, [rsi-10h]
0x180035742  sub     eax, r14d
0x180035745  cmp     eax, ebx
0x180035747  jz      loc_1800356B5
0x18003574d  lea     rcx, [rbp+57h+String1]
0x180035751  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180035756  nop
0x180035757  lea     rcx, [rbp+57h+var_B0]
0x18003575b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180035760  nop
0x180035761  test    ebx, ebx
0x180035763  jns     loc_180035808
0x180035769  mov     rdx, [r13+0]
0x18003576d  lea     rcx, [rdx-18h]
0x180035771  mov     rdi, [rbp+57h+String1]
0x180035775  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180035779  cmp     rcx, rdi
0x18003577c  jz      short loc_1800357B3
0x18003577e  cmp     dword ptr [rdi+10h], 0
0x180035782  jl      short loc_1800357A6
0x180035784  mov     rax, [rdi]
0x180035787  cmp     [rcx], rax
0x18003578a  jnz     short loc_1800357A6
0x18003578c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180035791  mov     rbx, rax
0x180035794  mov     rcx, rdi; this
0x180035797  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003579c  lea     rax, [rbx+18h]
0x1800357a0  mov     [rbp+57h+String1], rax
0x1800357a4  jmp     short loc_1800357B3
0x1800357a6  mov     r8d, [rdx-10h]
0x1800357aa  lea     rcx, [rbp+57h+String1]
0x1800357ae  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800357b3  lea     rcx, [rsi-18h]
0x1800357b7  mov     rdi, [rbp+57h+var_B0]
0x1800357bb  add     rdi, 0FFFFFFFFFFFFFFE8h
0x1800357bf  cmp     rcx, rdi
0x1800357c2  jz      loc_18003590C
0x1800357c8  cmp     dword ptr [rdi+10h], 0
0x1800357cc  jl      short loc_1800357F3
0x1800357ce  mov     rax, [rdi]
0x1800357d1  cmp     [rcx], rax
0x1800357d4  jnz     short loc_1800357F3
0x1800357d6  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800357db  mov     rbx, rax
0x1800357de  mov     rcx, rdi; this
0x1800357e1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800357e6  lea     rax, [rbx+18h]
0x1800357ea  mov     [rbp+57h+var_B0], rax
0x1800357ee  jmp     loc_18003590C
0x1800357f3  mov     r8d, [rsi-10h]
0x1800357f7  mov     rdx, rsi
0x1800357fa  lea     rcx, [rbp+57h+var_B0]
0x1800357fe  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180035803  jmp     loc_18003590C
0x180035808  mov     r8d, ebx
0x18003580b  lea     rdx, [rbp+57h+var_98]
0x18003580f  lea     rcx, [rbp+57h+var_B8]
0x180035813  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x180035818  nop
0x180035819  lea     r8, [rbp+57h+String1]
0x18003581d  lea     rdx, [rbp+57h+var_98]
0x180035821  mov     rcx, r13
0x180035824  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180035829  test    eax, eax
0x18003582b  jns     short loc_18003588F
0x18003582d  mov     rbx, [rbp+57h+var_98]
0x180035831  mov     [rsp+110h+var_E0], rbx
0x180035836  lea     rcx, aFailedToConstr; "Failed to construt full path of [%s]"
0x18003583d  mov     [rsp+110h+var_E8], rcx
0x180035842  mov     dword ptr [rsp+110h+var_F0], 153h
0x18003584a  lea     r9, aBaseDiagnosisS_21; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180035851  lea     r8, aWinrebuildcand; "winreBuildCanDeleteMap"
0x180035858  mov     edx, eax
0x18003585a  mov     ecx, r14d
0x18003585d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180035862  xor     r15d, r15d
0x180035865  lea     rcx, [rbx-18h]; this
0x180035869  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003586e  nop
0x18003586f  mov     rcx, [rbp+57h+var_B0]
0x180035873  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180035877  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003587c  nop
0x18003587d  mov     rcx, [rbp+57h+String1]
0x180035881  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180035885  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003588a  jmp     loc_180035680
0x18003588f  mov     r8d, [rsi-10h]
0x180035893  sub     r8d, ebx
0x180035896  sub     r8d, r14d
0x180035899  lea     rdx, [rbp+57h+var_50]
0x18003589d  lea     rcx, [rbp+57h+var_B8]
0x1800358a1  call    ?Right@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Right(int)
0x1800358a6  nop
0x1800358a7  mov     rdx, [rax]
0x1800358aa  lea     rcx, [rdx-18h]
0x1800358ae  mov     rdi, [rbp+57h+var_B0]
0x1800358b2  add     rdi, 0FFFFFFFFFFFFFFE8h
0x1800358b6  cmp     rcx, rdi
0x1800358b9  jz      short loc_1800358F1
0x1800358bb  cmp     dword ptr [rdi+10h], 0
0x1800358bf  jl      short loc_1800358E3
0x1800358c1  mov     rax, [rdi]
0x1800358c4  cmp     [rcx], rax
0x1800358c7  jnz     short loc_1800358E3
0x1800358c9  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800358ce  mov     rbx, rax
0x1800358d1  mov     rcx, rdi; this
0x1800358d4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800358d9  lea     rax, [rbx+18h]
0x1800358dd  mov     [rbp+57h+var_B0], rax
0x1800358e1  jmp     short loc_1800358F1
0x1800358e3  mov     r8d, [rdx-10h]
0x1800358e7  lea     rcx, [rbp+57h+var_B0]
0x1800358eb  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800358f0  nop
0x1800358f1  mov     rcx, [rbp+57h+var_50]
0x1800358f5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800358f9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800358fe  nop
0x1800358ff  mov     rcx, [rbp+57h+var_98]
0x180035903  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180035907  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003590c  mov     [rbp+57h+var_78], 0
0x180035914  mov     [rbp+57h+var_70], 0
0x18003591c  mov     [rbp+57h+var_68], 0
0x180035924  mov     [rbp+57h+var_60], 0
0x18003592b  lea     r8, [rbp+57h+var_78]
0x18003592f  lea     rdx, [rbp+57h+var_B0]
0x180035933  lea     rcx, [rbp+57h+String1]
0x180035937  call    ?EnumMatches@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@4@@Z; PushButtonReset::Directory::EnumMatches(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x18003593c  mov     r15d, eax
0x18003593f  test    eax, eax
0x180035941  jns     short loc_1800359A2
0x180035943  mov     rdi, [rbp+57h+String1]
0x180035947  mov     [rsp+38h], rdi
0x18003594c  mov     rbx, [rbp+57h+var_B0]
0x180035950  mov     [rsp+110h+var_E0], rbx
0x180035955  lea     rax, aFailedToEnumPa; "Failed to enum path [%s] in [%s]"
0x18003595c  mov     [rsp+110h+var_E8], rax
0x180035961  mov     dword ptr [rsp+110h+var_F0], 15Fh
0x180035969  lea     r9, aBaseDiagnosisS_21; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180035970  lea     r8, aWinrebuildcand; "winreBuildCanDeleteMap"
0x180035977  mov     edx, r15d
0x18003597a  mov     ecx, r14d
0x18003597d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180035982  xor     r15d, r15d
0x180035985  lea     rcx, [rbp+57h+var_78]
0x180035989  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x18003598e  nop
0x18003598f  lea     rcx, [rbx-18h]; this
  ... truncated ...
```
