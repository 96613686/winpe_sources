# Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddImageIdEvents(ulong,_EVENT_TRACE *)

- ea: `0x18000a30c`
- end: `0x18000b468`
- name: `?AddImageIdEvents@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJKPEAU_EVENT_TRACE@@@Z`
- size: `4444`
- prototype: `HRESULT __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this, int, struct _EVENT_TRACE *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a0f0`

## callees

- `0x1800056c8`
- `0x1800061c8`
- `0x1800091c0`
- `0x1800093c0`
- `0x180009704`
- `0x18000a30c`
- `0x18000b468`
- `0x18000ba1c`
- `0x18000bc98`
- `0x18000d6e0`
- `0x180011644`
- `0x180011860`
- `0x18001285c`
- `0x180012b8c`
- `0x180026410`
- `0x1800268f4`
- `0x180026e30`
- `0x180026f6c`
- `0x1800278f0`
- `0x180027910`

## import_xrefs

- `msvcrt!_stricmp` at `0x18000ae4d`
- `msvcrt!_stricmp` at `0x18000ae4d`
- `ole32!CoInitializeEx` at `0x18000b1bb`
- `ole32!CoInitializeEx` at `0x18000b1bb`
- `ole32!CoCreateGuid` at `0x18000b1d1`
- `ole32!CoCreateGuid` at `0x18000b1d1`
- `ole32!CoUninitialize` at `0x18000b1d9`
- `ole32!CoUninitialize` at `0x18000b1d9`
- `KERNEL32!CloseHandle` at `0x18000a92c`
- `KERNEL32!CloseHandle` at `0x18000a944`
- `KERNEL32!CloseHandle` at `0x18000a99d`
- `KERNEL32!CloseHandle` at `0x18000a9b1`
- `KERNEL32!CloseHandle` at `0x18000ab35`
- `KERNEL32!CloseHandle` at `0x18000ab50`
- `KERNEL32!CloseHandle` at `0x18000ab9f`
- `KERNEL32!CloseHandle` at `0x18000abb7`
- `KERNEL32!CloseHandle` at `0x18000a92c`
- `KERNEL32!CloseHandle` at `0x18000a944`
- `KERNEL32!CloseHandle` at `0x18000a99d`
- `KERNEL32!CloseHandle` at `0x18000a9b1`
- `KERNEL32!CloseHandle` at `0x18000ab35`
- `KERNEL32!CloseHandle` at `0x18000ab50`
- `KERNEL32!CloseHandle` at `0x18000ab9f`
- `KERNEL32!CloseHandle` at `0x18000abb7`
- `KERNEL32!UnmapViewOfFile` at `0x18000a919`
- `KERNEL32!UnmapViewOfFile` at `0x18000a98a`
- `KERNEL32!UnmapViewOfFile` at `0x18000ab1f`
- `KERNEL32!UnmapViewOfFile` at `0x18000ab8c`
- `KERNEL32!UnmapViewOfFile` at `0x18000a919`
- `KERNEL32!UnmapViewOfFile` at `0x18000a98a`
- `KERNEL32!UnmapViewOfFile` at `0x18000ab1f`
- `KERNEL32!UnmapViewOfFile` at `0x18000ab8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddImageIdEvents(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        int a2,
        struct _EVENT_TRACE *a3)
{
  struct _EVENT_TRACE *v3; // r13
  unsigned int v6; // r9d
  unsigned __int64 v7; // r10
  unsigned int v8; // ebx
  unsigned int *v9; // r12
  unsigned int *MofData; // rcx
  ULONG MofLength; // edx
  int Version; // eax
  int v13; // r15d
  int v14; // eax
  HRESULT result; // eax
  LARGE_INTEGER TimeStamp; // rax
  char *v17; // rax
  char FileName; // al
  unsigned __int16 *v19; // rax
  int v20; // eax
  unsigned int **v21; // r13
  union _CVDD **v22; // r12
  __int64 v23; // r10
  const unsigned __int16 *v24; // rbx
  int v25; // eax
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v26; // rcx
  size_t v27; // r13
  XPerf::Internal *v28; // r12
  unsigned int v29; // r12d
  __int64 v30; // rax
  int v31; // esp
  __int64 v32; // rax
  unsigned int v33; // ecx
  Microsoft::Windows::Performance::CCvDDCache *v34; // rdx
  union _CVDD *v35; // r8
  XPerf::Internal *v36; // rbx
  unsigned int v37; // eax
  BOOLEAN v38; // al
  unsigned __int64 v39; // rax
  int v40; // ecx
  unsigned int i; // ebx
  int v43; // ecx
  HRESULT v44; // ebx
  GUID *p_pguid; // rbx
  char v46; // [rsp+20h] [rbp-868h]
  char v47; // [rsp+20h] [rbp-868h]
  unsigned int **v48; // [rsp+28h] [rbp-860h]
  struct CODEVIEW_INFORMATION_1 **v49; // [rsp+30h] [rbp-858h]
  unsigned int v50; // [rsp+60h] [rbp-828h]
  bool *v51; // [rsp+60h] [rbp-828h]
  bool *v52; // [rsp+60h] [rbp-828h]
  bool *v53; // [rsp+88h] [rbp-800h]
  bool *v54; // [rsp+88h] [rbp-800h]
  BOOLEAN MappedAsImage; // [rsp+90h] [rbp-7F8h] BYREF
  bool v56[3]; // [rsp+91h] [rbp-7F7h] BYREF
  unsigned int v57; // [rsp+94h] [rbp-7F4h] BYREF
  unsigned int v58; // [rsp+98h] [rbp-7F0h] BYREF
  __int64 v59; // [rsp+A0h] [rbp-7E8h] BYREF
  unsigned __int64 v60; // [rsp+A8h] [rbp-7E0h]
  unsigned int v61; // [rsp+B0h] [rbp-7D8h]
  unsigned int v62[5]; // [rsp+B4h] [rbp-7D4h] BYREF
  struct CODEVIEW_INFORMATION_1 *v63; // [rsp+C8h] [rbp-7C0h] BYREF
  XPerf::Internal *v64; // [rsp+D0h] [rbp-7B8h] BYREF
  size_t Size; // [rsp+D8h] [rbp-7B0h]
  union _CVDD *v66; // [rsp+E0h] [rbp-7A8h] BYREF
  Microsoft::Windows::Performance::CCvDDCache *v67; // [rsp+E8h] [rbp-7A0h]
  bool v68[8]; // [rsp+F0h] [rbp-798h] BYREF
  __int64 v69; // [rsp+F8h] [rbp-790h]
  __int64 v70; // [rsp+100h] [rbp-788h]
  HANDLE hObject[2]; // [rsp+108h] [rbp-780h] BYREF
  LPCVOID lpBaseAddress; // [rsp+118h] [rbp-770h]
  void *v73; // [rsp+120h] [rbp-768h]
  struct _EVENT_TRACE *v74; // [rsp+128h] [rbp-760h]
  __int64 v75; // [rsp+130h] [rbp-758h]
  ATL::CAtlException *v76; // [rsp+138h] [rbp-750h] BYREF
  __int128 v77; // [rsp+140h] [rbp-748h] BYREF
  __m256i v78; // [rsp+150h] [rbp-738h]
  __int128 v79; // [rsp+170h] [rbp-718h]
  __int128 v80; // [rsp+180h] [rbp-708h]
  int v81; // [rsp+190h] [rbp-6F8h]
  int v82; // [rsp+194h] [rbp-6F4h]
  __int128 v83; // [rsp+1A0h] [rbp-6E8h] BYREF
  __m256i v84; // [rsp+1B0h] [rbp-6D8h]
  __int128 v85; // [rsp+1D0h] [rbp-6B8h]
  __int128 v86; // [rsp+1E0h] [rbp-6A8h]
  int v87; // [rsp+1F0h] [rbp-698h]
  int v88; // [rsp+1F4h] [rbp-694h]
  GUID pguid; // [rsp+200h] [rbp-688h] BYREF
  unsigned __int64 v90; // [rsp+210h] [rbp-678h] BYREF
  unsigned __int64 v91; // [rsp+218h] [rbp-670h] BYREF
  unsigned __int16 v92[8]; // [rsp+220h] [rbp-668h] BYREF
  int v93; // [rsp+230h] [rbp-658h]

  v75 = -2;
  v3 = a3;
  v74 = a3;
  *(_QWORD *)&pguid.Data1 = this;
  v6 = 0;
  v59 = 0;
  v7 = 0;
  v60 = 0;
  v8 = 0;
  v61 = 0;
  v62[0] = 0;
  v9 = 0;
  MofData = (unsigned int *)a3->MofData;
  MofLength = a3->MofLength;
  Version = a3->Header.Class.Version;
  if ( Version != 1 )
  {
    if ( (unsigned int)(Version - 2) > 1 )
      goto LABEL_26;
    if ( *((_DWORD *)this + 8) < 0xBu )
    {
      if ( a2 != 4 )
        goto LABEL_5;
      if ( MofLength >= 0x2C )
      {
        v9 = MofData + 10;
        goto LABEL_12;
      }
    }
    else
    {
      if ( a2 != 4 )
      {
LABEL_5:
        v13 = 8;
        if ( a2 != 8 )
          goto LABEL_26;
        if ( MofLength < 0x40 )
          goto LABEL_7;
        HIDWORD(v59) = MofData[2];
        v9 = MofData + 14;
        v8 = MofData[5];
        v62[0] = MofData[6];
LABEL_9:
        v7 = *(_QWORD *)MofData;
        v6 = MofData[4];
        v61 = v8;
        v60 = v7;
        LODWORD(v59) = v6;
        v14 = 0;
        goto LABEL_25;
      }
      if ( MofLength >= 0x30 )
      {
        v9 = MofData + 11;
LABEL_12:
        HIDWORD(v59) = MofData[1];
        v8 = MofData[3];
        v62[0] = MofData[4];
LABEL_23:
        v6 = MofData[2];
        v7 = *MofData;
        LODWORD(v59) = v6;
        v60 = v7;
        v61 = v8;
        v14 = 0;
        goto LABEL_24;
      }
    }
LABEL_21:
    v14 = -2147024883;
LABEL_24:
    v13 = 8;
    goto LABEL_25;
  }
  if ( a2 == 4 )
  {
    if ( MofLength >= 0x10 )
    {
      HIDWORD(v59) = MofData[1];
      v9 = MofData + 3;
      v62[0] = 0;
      goto LABEL_23;
    }
    goto LABEL_21;
  }
  v13 = 8;
  if ( a2 != 8 )
    goto LABEL_26;
  if ( MofLength >= 0x18 )
  {
    HIDWORD(v59) = MofData[2];
    v9 = MofData + 5;
    v62[0] = 0;
    goto LABEL_9;
  }
LABEL_7:
  v14 = -2147024883;
LABEL_25:
  if ( v14 >= 0 )
  {
    TimeStamp = a3->Header.TimeStamp;
    if ( *((_QWORD *)this + 5) != TimeStamp.QuadPart || *((_DWORD *)this + 12) != v6 || *((_QWORD *)this + 7) != v7 )
    {
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v17 = (char *)this + 64;
        if ( !*((_BYTE *)this + 208) )
        {
          Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize((Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)this + 64));
          v17 = (char *)this + 64;
        }
        FileName = Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(v17, v9, (char *)this + 216);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          __eh34_try_continuation(0, std::bad_alloc `RTTI Type Descriptor', &loc_18000B42E);
          goto LABEL_158;
        }
        if ( __eh34_catch_type(0, ATL::CAtlException `RTTI Type Descriptor', &v76) )
        {
          if ( *(_DWORD *)v76 == -2147024882 )
          {
            __eh34_try_continuation(0, ATL::CAtlException `RTTI Type Descriptor', &loc_18000B42E);
            goto LABEL_158;
          }
          *(_BYTE *)(*(_QWORD *)&pguid.Data1 + 224LL) = 1;
          result = 1;
          __eh34_try_continuation(0, ATL::CAtlException `RTTI Type Descriptor', &loc_18000B435);
LABEL_174:
          ;
        }
      }
      if ( !FileName )
      {
        result = 1;
        goto LABEL_174;
      }
      memset_0(&v90, 0, 0x640u);
      if ( a2 == 4 )
        v19 = v92;
      else
        v19 = &v92[4];
      Size = (size_t)v19;
      v57 = 0;
      v66 = 0;
      v64 = 0;
      v63 = 0;
      *(_DWORD *)v68 = 0;
      v69 = 0;
      v70 = 0;
      v56[0] = 0;
      v67 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)this + 232);
      v20 = ((int (__stdcall *)(Microsoft::Windows::Performance::CCvDDCache *, const unsigned __int16 *, unsigned int, unsigned int *, const union _CVDD **, const unsigned int **, const struct CODEVIEW_INFORMATION_1 **, unsigned int *, unsigned int *, struct EMBEDDED_PDB_INFORMATION *, bool *, unsigned __int16 *, unsigned int))Microsoft::Windows::Performance::CCvDDCache::Find)(
              (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)this + 232),
              *((const unsigned __int16 **)this + 27),
              v8,
              &v57,
              &v66,
              (const unsigned int **)&v64,
              &v63,
              v62,
              (unsigned int *)&v59 + 1,
              (struct EMBEDDED_PDB_INFORMATION *)v68,
              v56,
              v19,
              v50);
      if ( v20 >= 0 )
      {
        v29 = v59;
        v67 = v66;
        v66 = v64;
        *(_QWORD *)&pguid.Data1 = v63;
LABEL_94:
        if ( a2 == 4 )
        {
          v90 = __PAIR64__(HIDWORD(v59), v60);
          v91 = __PAIR64__(v62[0], v29);
        }
        else
        {
          v90 = v60;
          v91 = HIDWORD(v59);
          *(_DWORD *)v92 = v29;
          *(_DWORD *)&v92[2] = v62[0];
        }
        v30 = -1;
        do
          ++v30;
        while ( *(_WORD *)(Size + 2 * v30) );
        v83 = *(_OWORD *)&v3->Header.Size;
        v84 = *(__m256i *)&v3->Header.TimeStamp.LowPart;
        v85 = *(_OWORD *)&v3->InstanceId;
        v86 = *(_OWORD *)v3->ParentGuid.Data4;
        v88 = HIDWORD(*(_QWORD *)&v3->MofLength);
        *(_OWORD *)&v84.m256i_u64[1] = *(_OWORD *)ImageIdGuid;
        DWORD1(v83) = 0x20000;
        HIDWORD(v83) = v29;
        *((_QWORD *)&v86 + 1) = &v90;
        v87 = Size + 2 * (v30 + 1) - (v31 + 528);
        result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                   *((_QWORD *)this + 2),
                   &v83,
                   0,
                   0);
        if ( result >= 0 )
        {
          v64 = 0;
          v32 = 0;
          LODWORD(v63) = 0;
          v33 = v57;
          if ( v57 )
          {
            v34 = v67;
            v35 = v66;
            do
            {
              v36 = (Microsoft::Windows::Performance::CCvDDCache *)((char *)v34 + 1576 * v32);
              v37 = *((_DWORD *)v35 + v32);
              LODWORD(Size) = v37;
              if ( v37 >= 4 )
              {
                if ( v37 > 0x628 )
                  goto LABEL_38;
                if ( *(_DWORD *)v36 )
                {
                  switch ( *(_DWORD *)v36 )
                  {
                    case 1:
                      v38 = 33;
                      break;
                    case 2:
                      v38 = 34;
                      break;
                    case 3:
                      v38 = 37;
                      break;
                    case 0x3031424E:
                      v38 = 35;
                      break;
                    case 0x53445352:
                      v38 = 36;
                      break;
                    default:
                      goto LABEL_26;
                  }
                }
                else
                {
                  v38 = 32;
                }
                MappedAsImage = v38;
                if ( *(_DWORD *)v68 )
                {
                  if ( v38 == 36 )
                  {
                    v39 = -1;
                    do
                      ++v39;
                    while ( *((_BYTE *)v36 + v39 + 24) );
                    if ( v39 <= 7 || _stricmp((const char *)v36 + v39 + 17, ".ni.pdb") )
                      v64 = v36;
                  }
                }
                if ( a2 == 4 )
                {
                  if ( (unsigned int)Size > 0x63C )
                    goto LABEL_26;
                  memcpy_0((char *)&v90 + 4, v36, (unsigned int)Size);
                  v90 = __PAIR64__(v29, v60);
                  v40 = 4;
                }
                else
                {
                  if ( (unsigned int)Size > 0x638 )
                    goto LABEL_26;
                  memcpy_0(&v91, v36, (unsigned int)Size);
                  v90 = v60;
                  LODWORD(v91) = v29;
                  v40 = 8;
                }
                v83 = *(_OWORD *)&v3->Header.Size;
                v84 = *(__m256i *)&v3->Header.TimeStamp.LowPart;
                v85 = *(_OWORD *)&v3->InstanceId;
                v86 = *(_OWORD *)v3->ParentGuid.Data4;
                v88 = HIDWORD(*(_QWORD *)&v3->MofLength);
                *(_OWORD *)&v84.m256i_u64[1] = *(_OWORD *)ImageIdGuid;
                DWORD1(v83) = MappedAsImage | 0x20000;
                HIDWORD(v83) = v29;
                *((_QWORD *)&v86 + 1) = &v90;
                v87 = v40 + Size;
                result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                           *((_QWORD *)this + 2),
                           &v83,
                           0,
                           0);
                if ( result < 0 )
                  goto LABEL_174;
                v33 = v57;
                v34 = v67;
                v35 = v66;
              }
              v32 = (unsigned int)((_DWORD)v63 + 1);
              LODWORD(v63) = v32;
            }
            while ( (unsigned int)v32 < v33 );
          }
          for ( i = 0; i < v33; ++i )
          {
            if ( a2 == 4 )
            {
              v90 = __PAIR64__(v29, v60);
            }
            else
            {
              v90 = v60;
              LODWORD(v91) = v29;
            }
            if ( *(_DWORD *)(*(_QWORD *)&pguid.Data1 + 8LL * i) )
            {
              HIDWORD(v91) = *(_DWORD *)(*(_QWORD *)&pguid.Data1 + 8LL * i);
              v92[0] = *(_WORD *)(*(_QWORD *)&pguid.Data1 + 8LL * i + 4);
              v92[1] = *(_WORD *)(*(_QWORD *)&pguid.Data1 + 8LL * i + 6);
              v77 = *(_OWORD *)&v3->Header.Size;
              v78 = *(__m256i *)&v3->Header.TimeStamp.LowPart;
              v79 = *(_OWORD *)&v3->InstanceId;
              v80 = *(_OWORD *)v3->ParentGuid.Data4;
              v82 = HIDWORD(*(_QWORD *)&v3->MofLength);
              *(_OWORD *)&v78.m256i_u64[1] = *(_OWORD *)ImageIdGuid;
              DWORD1(v77) = 131110;
              HIDWORD(v77) = v29;
              *((_QWORD *)&v80 + 1) = &v90;
              v81 = 20;
              result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                         *((_QWORD *)this + 2),
                         &v77,
                         0,
                         0);
              if ( result < 0 )
                goto LABEL_174;
              v33 = v57;
            }
          }
          if ( !*(_DWORD *)v68 )
            goto LABEL_176;
          *(_QWORD *)&pguid.Data1 = 0;
          *(_QWORD *)pguid.Data4 = 0;
          LODWORD(v63) = 1;
          if ( v64 )
          {
            if ( __eh34_try(-1, 2) )
            {
              __eh34_scope_strut(2);
              p_pguid = (GUID *)((char *)v64 + 4);
              result = Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(
                         this,
                         (const char *)v64 + 24,
                         (const struct _GUID *)((char *)v64 + 4),
                         *((_DWORD *)v64 + 5),
                         (const struct EMBEDDED_PDB_INFORMATION *)v68);
            }
            if ( __eh34_catch(2) )
            {
              if ( __eh34_catch_type(2, std::bad_alloc `RTTI Type Descriptor', 0) )
              {
                __eh34_try_continuation(2, std::bad_alloc `RTTI Type Descriptor', &loc_18000B42E);
                goto LABEL_158;
              }
            }
            if ( result < 0 )
              goto LABEL_174;
            v43 = *((_DWORD *)v64 + 5);
          }
          else
          {
            result = CoInitializeEx(0, 2u);
            if ( result < 0 )
              goto LABEL_174;
            v44 = CoCreateGuid(&pguid);
            CoUninitialize();
            if ( v44 < 0 )
            {
              result = v44;
              goto LABEL_174;
            }
            p_pguid = &pguid;
            v43 = (int)v63;
          }
          if ( a2 == 4 )
          {
            v90 = __PAIR64__(v29, v60);
          }
          else
          {
            v90 = v60;
            LODWORD(v91) = v29;
          }
          HIDWORD(v91) = v70;
          *(GUID *)v92 = *p_pguid;
          v93 = v43;
          v77 = *(_OWORD *)&v3->Header.Size;
          v78 = *(__m256i *)&v3->Header.TimeStamp.LowPart;
          v79 = *(_OWORD *)&v3->InstanceId;
          v80 = *(_OWORD *)v3->ParentGuid.Data4;
          v82 = HIDWORD(*(_QWORD *)&v3->MofLength);
          *(_OWORD *)&v78.m256i_u64[1] = *(_OWORD *)ImageIdGuid;
          DWORD1(v77) = 65575;
          HIDWORD(v77) = v29;
          *((_QWORD *)&v80 + 1) = &v90;
          v81 = 36;
          result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                     *((_QWORD *)this + 2),
                     &v77,
                     0,
                     0);
          if ( result >= 0 )
          {
LABEL_176:
            if ( !v56[0] )
              goto LABEL_157;
            if ( a2 == 4 )
            {
              v90 = __PAIR64__(v29, v60);
            }
            else
            {
              v90 = v60;
              LODWORD(v91) = v29;
              v13 = 12;
            }
            v77 = *(_OWORD *)&v3->Header.Size;
            v78 = *(__m256i *)&v3->Header.TimeStamp.LowPart;
            v79 = *(_OWORD *)&v3->InstanceId;
            v80 = *(_OWORD *)v3->ParentGuid.Data4;
            v82 = HIDWORD(*(_QWORD *)&v3->MofLength);
            *(_OWORD *)&v78.m256i_u64[1] = *(_OWORD *)ImageIdGuid;
            DWORD1(v77) = 65576;
            HIDWORD(v77) = v29;
            *((_QWORD *)&v80 + 1) = &v90;
            v81 = v13;
            result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                       *((_QWORD *)this + 2),
                       &v77,
                       0,
                       0);
            if ( result >= 0 )
LABEL_157:
              result = 0;
          }
        }
        goto LABEL_174;
      }
      if ( v20 == -2147023728 )
      {
        v57 = *((_DWORD *)this + 106);
        v21 = (unsigned int **)((char *)this + 400);
        if ( !*((_QWORD *)this + 50)
          || (v22 = (union _CVDD **)((char *)this + 408), !*((_QWORD *)this + 51))
          || !*((_QWORD *)this + 52) )
        {
LABEL_38:
          result = -2147418113;
          goto LABEL_174;
        }
        MappedAsImage = Performance::COSVersionInfo::IsWin8AndUp();
        *(__m128i *)hObject = _mm_load_si128((const __m128i *)&_xmm);
        lpBaseAddress = 0;
        v73 = 0;
        v64 = (XPerf::Internal *)*((_QWORD *)this + 27);
        if ( ((int (__stdcall *)(XPerfCore::CFileMapping *, const unsigned __int16 *, bool))XPerfCore::CFileMapping::MapExistingFileReadOnly)(
               (XPerfCore::CFileMapping *)hObject,
               (const unsigned __int16 *)v64,
               MappedAsImage) < 0 )
        {
          v24 = (const unsigned __int16 *)lpBaseAddress;
        }
        else
        {
          v23 = 0xFFFFFFFFLL;
          if ( (unsigned __int64)v73 < 0xFFFFFFFF )
            v23 = (unsigned int)v73;
          *(_QWORD *)&pguid.Data1 = v23;
          LODWORD(v51) = 780;
          v24 = (const unsigned __int16 *)lpBaseAddress;
          v25 = ((__int64 (__fastcall *)(XPerf::Internal *, const unsigned __int16 *, void *, unsigned int, char, unsigned int *, unsigned int *, union _CVDD *, unsigned int *, struct CODEVIEW_INFORMATION_1 *, unsigned int *, unsigned int *, unsigned __int16 *, unsigned int, BOOLEAN, bool, struct EMBEDDED_PDB_INFORMATION *, bool *))XPerf::Internal::CvDbgInfoFromImage2)(
                  v64,
                  (const unsigned __int16 *)lpBaseAddress,
                  (void *)(unsigned int)v23,
                  v61,
                  v46,
                  &v57,
                  *v21,
                  *v22,
                  *((unsigned int **)this + 52),
                  (struct CODEVIEW_INFORMATION_1 *)v62,
                  (unsigned int *)&v59 + 1,
                  (unsigned int *)Size,
                  (unsigned __int16 *)v51,
                  (unsigned int)&v58,
                  MappedAsImage,
                  (bool)v68,
                  (struct EMBEDDED_PDB_INFORMATION *)v56,
                  v53);
          if ( v25 >= 0 )
            goto LABEL_177;
          if ( v25 == -2146893023 )
          {
            *((_DWORD *)this + 106) = 0;
            operator delete(*v21);
            *v21 = 0;
            operator delete(*v22);
            *v22 = 0;
            operator delete(*((void **)this + 52));
            *((_QWORD *)this + 52) = 0;
            if ( !ATL::CAutoVectorPtr<_CVDD>::Allocate((_QWORD *)this + 50, v57)
              || !ATL::CAutoVectorPtr<unsigned long>::Allocate((_QWORD *)this + 51, v57)
              || !ATL::CAutoVectorPtr<unsigned __int64>::Allocate((_QWORD *)this + 52, v57) )
            {
              if ( v24 )
                UnmapViewOfFile(v24);
              if ( hObject[1] )
                CloseHandle(hObject[1]);
              if ( hObject[0] != (HANDLE)-1LL )
                CloseHandle(hObject[0]);
              goto LABEL_158;
            }
            *((_DWORD *)this + 106) = v57;
            LODWORD(v52) = 780;
            v25 = ((__int64 (__fastcall *)(XPerf::Internal *, const unsigned __int16 *, void *, unsigned int, char, unsigned int *, unsigned int *, union _CVDD *, unsigned int *, struct CODEVIEW_INFORMATION_1 *, unsigned int *, unsigned int *, unsigned __int16 *, unsigned int, BOOLEAN, bool, struct EMBEDDED_PDB_INFORMATION *, bool *))XPerf::Internal::CvDbgInfoFromImage2)(
                    v64,
                    v24,
                    (void *)pguid.Data1,
                    v61,
                    v47,
                    &v57,
                    *v21,
                    *v22,
                    *((unsigned int **)this + 52),
                    (struct CODEVIEW_INFORMATION_1 *)v62,
                    (unsigned int *)&v59 + 1,
                    (unsigned int *)Size,
                    (unsigned __int16 *)v52,
                    (unsigned int)&v58,
                    MappedAsImage,
                    (bool)v68,
                    (struct EMBEDDED_PDB_INFORMATION *)v56,
                    v54);
          }
          if ( v25 >= 0 )
          {
LABEL_177:
            if ( !*((_BYTE *)this + 225) )
            {
              LODWORD(v63) = Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(
                               v26,
                               v57,
                               (union _CVDD *)*v21,
                               (unsigned int *)*v22);
              if ( (int)v63 < 0 )
                goto LABEL_63;
            }
            v67 = (Microsoft::Windows::Performance::CCvDDCache *)*v21;
            v66 = *v22;
            *(_QWORD *)&pguid.Data1 = *((_QWORD *)this + 52);
            MappedAsImage = 0;
            v27 = Size;
            v28 = v64;
            LODWORD(v63) = Microsoft::Windows::Performance::CCvDDCache::Add(
                             (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)this + 232),
                             (const unsigned __int16 *)v64,
                             v61,
                             v57,
                             v67,
                             (const unsigned int *)v66,
                             *(const struct CODEVIEW_INFORMATION_1 **)&pguid.Data1,
                             v62[0],
                             HIDWORD(v59),
                             (struct EMBEDDED_PDB_INFORMATION *)v68,
                             v56[0],
                             (const unsigned __int16 *)Size,
                             (bool *)&MappedAsImage);
            if ( (int)v63 < 0 )
            {
LABEL_63:
              if ( v24 )
                UnmapViewOfFile(v24);
              if ( hObject[1] )
                CloseHandle(hObject[1]);
              if ( hObject[0] != (HANDLE)-1LL )
                CloseHandle(hObject[0]);
              result = (int)v63;
              goto LABEL_174;
            }
            if ( MappedAsImage )
            {
              v49 = (struct CODEVIEW_INFORMATION_1 **)v28;
              v48 = (unsigned int **)v27;
              v29 = v59;
              v3 = v74;
              Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddFileVersionEvent(
                (void **)this,
                v74,
                v59,
                HIDWORD(v59),
                v62[0],
                (const unsigned __int16 *)v48,
                (const unsigned __int16 *)v49,
                (struct XPerfCore::CFileMapping *)hObject);
              v24 = (const unsigned __int16 *)lpBaseAddress;
            }
            else
            {
              v29 = v59;
              v3 = v74;
            }
            if ( (*((_DWORD *)this + 107) & 0x100) == 0 )
            {
              *(_QWORD *)v68 = 0;
              v69 = 0;
              v70 = 0;
            }
            if ( v24 )
              UnmapViewOfFile(v24);
            if ( hObject[1] )
              CloseHandle(hObject[1]);
            if ( hObject[0] != (HANDLE)-1LL )
              CloseHandle(hObject[0]);
            goto LABEL_94;
          }
        }
        Microsoft::Windows::Performance::CCvDDCache::AddFailure(v67, (const unsigned __int16 *)v64, v61);
        if ( v24 )
          UnmapViewOfFile(v24);
        if ( hObject[1] )
          CloseHandle(hObject[1]);
        if ( hObject[0] != (HANDLE)-1LL )
          CloseHandle(hObject[0]);
      }
      else if ( v20 != -2147467259 && v20 != -2147024774 )
      {
        if ( v20 == -2147024882 )
        {
LABEL_158:
          result = -2147024882;
          goto LABEL_174;
        }
        *((_BYTE *)this + 224) = 1;
      }
    }
  }
LABEL_26:
  result = 1;
  goto LABEL_174;
}

```

## disassembly

```asm
0x18000a30c  mov     r11, rsp
0x18000a30f  push    rdi
0x18000a310  push    r12
0x18000a312  push    r13
0x18000a314  push    r14
0x18000a316  push    r15
0x18000a318  sub     rsp, 860h
0x18000a31f  mov     qword ptr [r11-758h], 0FFFFFFFFFFFFFFFEh
0x18000a32a  mov     [r11+10h], rbx
0x18000a32e  mov     [r11+20h], rsi
0x18000a332  mov     rax, cs:__security_cookie
0x18000a339  xor     rax, rsp
0x18000a33c  mov     [rsp+888h+var_38], rax
0x18000a344  mov     r13, r8
0x18000a347  mov     [rsp+888h+var_760], r8
0x18000a34f  mov     r14d, edx
0x18000a352  mov     rsi, rcx
0x18000a355  mov     qword ptr [rsp+888h+pguid.Data1], rcx
0x18000a35d  xor     r8d, r8d
0x18000a360  mov     r9d, r8d
0x18000a363  mov     [r11-7E8h], r8
0x18000a36a  mov     r10d, r8d
0x18000a36d  mov     [r11-7E0h], r8
0x18000a374  mov     ebx, r8d
0x18000a377  mov     [rsp+888h+var_7D8], ebx
0x18000a37e  mov     [r11-7D4h], r8d
0x18000a385  mov     r12d, r8d
0x18000a388  mov     rcx, [r13+48h]
0x18000a38c  mov     edx, [r13+50h]
0x18000a390  movzx   eax, word ptr [r13+6]
0x18000a395  lea     edi, [r8+1]
0x18000a399  cmp     eax, edi
0x18000a39b  jz      loc_18000A452
0x18000a3a1  add     eax, 0FFFFFFFEh
0x18000a3a4  cmp     eax, edi
0x18000a3a6  ja      loc_18000A4D4
0x18000a3ac  cmp     dword ptr [rsi+20h], 0Bh
0x18000a3b0  jb      loc_18000A43D
0x18000a3b6  cmp     r14d, 4
0x18000a3ba  jz      short loc_18000A41B
0x18000a3bc  mov     r15d, 8
0x18000a3c2  cmp     r14d, r15d
0x18000a3c5  jnz     loc_18000A4D4
0x18000a3cb  cmp     edx, 40h ; '@'
0x18000a3ce  jnb     short loc_18000A3DA
0x18000a3d0  mov     eax, 8007000Dh
0x18000a3d5  jmp     loc_18000A4D0
0x18000a3da  mov     eax, [rcx+8]
0x18000a3dd  mov     [rsp+888h+var_7E4], eax
0x18000a3e4  lea     r12, [rcx+38h]
0x18000a3e8  mov     ebx, [rcx+14h]
0x18000a3eb  mov     eax, [rcx+18h]
0x18000a3ee  mov     [rsp+888h+var_7D4], eax
0x18000a3f5  mov     r10, [rcx]
0x18000a3f8  mov     r9d, [rcx+10h]
0x18000a3fc  mov     [rsp+888h+var_7D8], ebx
0x18000a403  mov     [rsp+888h+var_7E0], r10
0x18000a40b  mov     [rsp+888h+var_7E8], r9d
0x18000a413  mov     eax, r8d
0x18000a416  jmp     loc_18000A4D0
0x18000a41b  cmp     edx, 30h ; '0'
0x18000a41e  jb      short loc_18000A48C
0x18000a420  lea     r12, [rcx+2Ch]
0x18000a424  mov     eax, [rcx+4]
0x18000a427  mov     [rsp+888h+var_7E4], eax
0x18000a42e  mov     ebx, [rcx+0Ch]
0x18000a431  mov     eax, [rcx+10h]
0x18000a434  mov     [rsp+888h+var_7D4], eax
0x18000a43b  jmp     short loc_18000A4A9
0x18000a43d  cmp     r14d, 4
0x18000a441  jnz     loc_18000A3BC
0x18000a447  cmp     edx, 2Ch ; ','
0x18000a44a  jb      short loc_18000A48C
0x18000a44c  lea     r12, [rcx+28h]
0x18000a450  jmp     short loc_18000A424
0x18000a452  cmp     r14d, 4
0x18000a456  jz      short loc_18000A487
0x18000a458  mov     r15d, 8
0x18000a45e  cmp     r14d, r15d
0x18000a461  jnz     short loc_18000A4D4
0x18000a463  cmp     edx, 18h
0x18000a466  jb      loc_18000A3D0
0x18000a46c  mov     eax, [rcx+8]
0x18000a46f  mov     [rsp+888h+var_7E4], eax
0x18000a476  lea     r12, [rcx+14h]
0x18000a47a  mov     [rsp+888h+var_7D4], r8d
0x18000a482  jmp     loc_18000A3F5
0x18000a487  cmp     edx, 10h
0x18000a48a  jnb     short loc_18000A493
0x18000a48c  mov     eax, 8007000Dh
0x18000a491  jmp     short loc_18000A4CA
0x18000a493  mov     eax, [rcx+4]
0x18000a496  mov     [rsp+888h+var_7E4], eax
0x18000a49d  lea     r12, [rcx+0Ch]
0x18000a4a1  mov     [rsp+888h+var_7D4], r8d
0x18000a4a9  mov     r9d, [rcx+8]
0x18000a4ad  mov     r10d, [rcx]
0x18000a4b0  mov     [rsp+888h+var_7E8], r9d
0x18000a4b8  mov     [rsp+888h+var_7E0], r10
0x18000a4c0  mov     [rsp+888h+var_7D8], ebx
0x18000a4c7  mov     eax, r8d
0x18000a4ca  mov     r15d, 8
0x18000a4d0  test    eax, eax
0x18000a4d2  jns     short loc_18000A4DB
0x18000a4d4  mov     eax, edi
0x18000a4d6  jmp     loc_18000B43A
0x18000a4db  mov     rax, [r13+10h]
0x18000a4df  cmp     [rsi+28h], rax
0x18000a4e3  jnz     short loc_18000A4F1
0x18000a4e5  cmp     [rsi+30h], r9d
0x18000a4e9  jnz     short loc_18000A4F1
0x18000a4eb  cmp     [rsi+38h], r10
0x18000a4ef  jz      short loc_18000A4D4
0x18000a4f1  lea     rax, [rsi+40h]
0x18000a4f5  cmp     [rax+90h], r8b
0x18000a4fc  jnz     short loc_18000A50A
0x18000a4fe  mov     rcx, rax; this
0x18000a501  call    ?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ; Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)
0x18000a506  lea     rax, [rsi+40h]
0x18000a50a  lea     r8, [rsi+0D8h]
0x18000a511  mov     rdx, r12
0x18000a514  mov     rcx, rax
0x18000a517  call    ?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18000a51c  xor     r12d, r12d
0x18000a51f  test    al, al
0x18000a521  jnz     short loc_18000A52A
0x18000a523  mov     eax, edi
0x18000a525  jmp     loc_18000B43A
0x18000a52a  xor     edx, edx; Val
0x18000a52c  mov     r8d, 640h; Size
0x18000a532  lea     rcx, [rsp+888h+var_678]; void *
0x18000a53a  call    memset_0
0x18000a53f  cmp     r14d, 4
0x18000a543  jz      short loc_18000A55E
0x18000a545  cmp     r14d, r15d
0x18000a548  jz      short loc_18000A554
0x18000a54a  mov     eax, 8000FFFFh
0x18000a54f  jmp     loc_18000B43A
0x18000a554  lea     rax, [rsp+888h+var_668+8]
0x18000a55c  jmp     short loc_18000A566
0x18000a55e  lea     rax, [rsp+888h+var_668]
0x18000a566  mov     [rsp+888h+Size], rax
0x18000a56e  mov     [rsp+888h+var_7F4], r12d
0x18000a576  mov     [rsp+888h+var_7A8], r12
0x18000a57e  mov     [rsp+888h+var_7B8], r12
0x18000a586  mov     [rsp+888h+var_7C0], r12
0x18000a58e  mov     dword ptr [rsp+888h+var_798], r12d
0x18000a596  xor     ecx, ecx
0x18000a598  mov     [rsp+888h+var_790], rcx
0x18000a5a0  mov     [rsp+888h+var_788], rcx
0x18000a5a8  mov     [rsp+888h+var_7F7], r12b
0x18000a5b0  lea     rcx, [rsi+0E8h]; this
0x18000a5b7  mov     [rsp+888h+var_7A0], rcx
0x18000a5bf  mov     [rsp+888h+var_830], rax; unsigned __int16 *
0x18000a5c4  lea     rax, [rsp+888h+var_7F7]
0x18000a5cc  mov     [rsp+888h+var_838], rax; bool *
0x18000a5d1  lea     rax, [rsp+888h+var_798]
0x18000a5d9  mov     [rsp+888h+var_840], rax; struct EMBEDDED_PDB_INFORMATION *
0x18000a5de  lea     rax, [rsp+888h+var_7E4]
0x18000a5e6  mov     [rsp+888h+var_848], rax; unsigned int *
0x18000a5eb  lea     rax, [rsp+888h+var_7D4]
0x18000a5f3  mov     [rsp+888h+var_850], rax; unsigned int *
0x18000a5f8  lea     rax, [rsp+888h+var_7C0]
0x18000a600  mov     [rsp+888h+var_858], rax; struct CODEVIEW_INFORMATION_1 **
0x18000a605  lea     rax, [rsp+888h+var_7B8]
0x18000a60d  mov     [rsp+888h+var_860], rax; unsigned int **
0x18000a612  lea     rax, [rsp+888h+var_7A8]
0x18000a61a  mov     [rsp+888h+var_868], rax; char
0x18000a61f  lea     r9, [rsp+888h+var_7F4]; unsigned int *
0x18000a627  mov     r8d, ebx; unsigned int
0x18000a62a  mov     rdx, [rsi+0D8h]; unsigned __int16 *
0x18000a631  call    ?Find@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKPEAKPEAPEBT_CVDD@@PEAPEBKPEAPEBUCODEVIEW_INFORMATION_1@@11AEAUEMBEDDED_PDB_INFORMATION@@AEA_NPEAGK@Z; Microsoft::Windows::Performance::CCvDDCache::Find(ushort const *,ulong,ulong *,_CVDD const * *,ulong const * *,CODEVIEW_INFORMATION_1 const * *,ulong *,ulong *,EMBEDDED_PDB_INFORMATION &,bool &,ushort *,ulong)
0x18000a636  xor     r9d, r9d
0x18000a639  test    eax, eax
0x18000a63b  jns     loc_18000ABEF
0x18000a641  cmp     eax, 80070490h
0x18000a646  jnz     loc_18000ABC2
0x18000a64c  mov     eax, [rsi+1A8h]
0x18000a652  mov     [rsp+888h+var_7F4], eax
0x18000a659  lea     r13, [rsi+190h]
0x18000a660  cmp     [r13+0], r9
0x18000a664  jz      loc_18000A54A
0x18000a66a  lea     r12, [rsi+198h]
0x18000a671  cmp     [r12], r9
0x18000a675  jz      loc_18000A54A
0x18000a67b  lea     rbx, [rsi+1A0h]
0x18000a682  cmp     [rbx], r9
0x18000a685  jz      loc_18000A54A
0x18000a68b  call    ?IsWin8AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin8AndUp(void)
0x18000a690  mov     cl, al
0x18000a692  mov     [rsp+888h+var_7F8], al
0x18000a699  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x18000a6a1  movdqu  xmmword ptr [rsp+888h+hObject], xmm0
0x18000a6aa  xor     eax, eax
0x18000a6ac  mov     [rsp+888h+lpBaseAddress], rax
0x18000a6b4  mov     [rsp+888h+var_768], rax
0x18000a6bc  mov     rax, [rsi+0D8h]
0x18000a6c3  mov     [rsp+888h+var_7B8], rax
0x18000a6cb  mov     r8b, cl; bool
0x18000a6ce  mov     rdx, rax; unsigned __int16 *
0x18000a6d1  lea     rcx, [rsp+888h+hObject]; this
0x18000a6d9  call    ?MapExistingFileReadOnly@CFileMapping@XPerfCore@@QEAAJPEBG_N@Z; XPerfCore::CFileMapping::MapExistingFileReadOnly(ushort const *,bool)
0x18000a6de  test    eax, eax
0x18000a6e0  js      loc_18000AB5E
0x18000a6e6  mov     r10d, 0FFFFFFFFh
0x18000a6ec  cmp     [rsp+888h+var_768], r10
0x18000a6f4  cmovb   r10d, dword ptr [rsp+888h+var_768]
0x18000a6fd  mov     qword ptr [rsp+888h+pguid.Data1], r10
0x18000a705  mov     rax, [rbx]
0x18000a708  mov     rcx, [r12]
0x18000a70c  mov     rdx, [r13+0]
0x18000a710  lea     r8, [rsp+888h+var_7F7]
0x18000a718  mov     [rsp+888h+var_808], r8; struct EMBEDDED_PDB_INFORMATION *
0x18000a720  lea     r8, [rsp+888h+var_798]
0x18000a728  mov     qword ptr [rsp+888h+var_810], r8; bool
0x18000a72d  mov     r8b, [rsp+888h+var_7F8]
0x18000a735  mov     [rsp+888h+MappedAsImage], r8b; MappedAsImage
0x18000a73a  lea     r8, [rsp+888h+var_7F0]
0x18000a742  mov     qword ptr [rsp+888h+var_820], r8; unsigned int
0x18000a747  mov     dword ptr [rsp+888h+var_828], 30Ch; unsigned __int16 *
0x18000a74f  mov     r8, [rsp+888h+Size]
0x18000a757  mov     [rsp+888h+var_830], r8; unsigned int *
0x18000a75c  lea     r8, [rsp+888h+var_7E4]
0x18000a764  mov     [rsp+888h+var_838], r8; unsigned int *
0x18000a769  lea     r8, [rsp+888h+var_7D4]
0x18000a771  mov     [rsp+888h+var_840], r8; struct CODEVIEW_INFORMATION_1 *
0x18000a776  mov     [rsp+888h+var_848], rax; unsigned int *
0x18000a77b  mov     [rsp+888h+var_850], rcx; union _CVDD *
0x18000a780  mov     [rsp+888h+var_858], rdx; unsigned int *
0x18000a785  lea     rax, [rsp+888h+var_7F4]
0x18000a78d  mov     [rsp+888h+var_860], rax; unsigned int *
0x18000a792  mov     r9d, [rsp+888h+var_7D8]; unsigned int
0x18000a79a  mov     r8d, r10d; void *
0x18000a79d  mov     rbx, [rsp+888h+lpBaseAddress]
0x18000a7a5  mov     rdx, rbx; unsigned __int16 *
0x18000a7a8  mov     rcx, [rsp+888h+var_7B8]; this
0x18000a7b0  call    ?CvDbgInfoFromImage2@Internal@XPerf@@YAJPEBGPEAXKK_NPEAKPEAT_CVDD@@3PEAUCODEVIEW_INFORMATION_1@@33PEAGKAEA_N2AEAUEMBEDDED_PDB_INFORMATION@@7@Z; XPerf::Internal::CvDbgInfoFromImage2(ushort const *,void *,ulong,ulong,bool,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,ulong *,ulong *,ushort *,ulong,bool &,bool,EMBEDDED_PDB_INFORMATION &,bool &)
0x18000a7b5  xor     r9d, r9d
0x18000a7b8  test    eax, eax
0x18000a7ba  jns     loc_18000A957
0x18000a7c0  cmp     eax, 80090321h
0x18000a7c5  jnz     loc_18000A94F
0x18000a7cb  mov     [rsi+1A8h], r9d
0x18000a7d2  mov     rcx, [r13+0]; Block
0x18000a7d6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a7db  xor     eax, eax
0x18000a7dd  mov     [r13+0], rax
0x18000a7e1  mov     rcx, [r12]; Block
0x18000a7e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a7ea  xor     eax, eax
0x18000a7ec  mov     [r12], rax
0x18000a7f0  mov     rcx, [rsi+1A0h]; Block
0x18000a7f7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a7fc  xor     eax, eax
0x18000a7fe  mov     [rsi+1A0h], rax
0x18000a805  mov     edx, [rsp+888h+var_7F4]
0x18000a80c  mov     rcx, r13
0x18000a80f  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18000a814  test    al, al
0x18000a816  jz      loc_18000A911
0x18000a81c  mov     edx, [rsp+888h+var_7F4]
0x18000a823  mov     rcx, r12
0x18000a826  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x18000a82b  test    al, al
0x18000a82d  jz      loc_18000A911
0x18000a833  mov     edx, [rsp+888h+var_7F4]
0x18000a83a  lea     rcx, [rsi+1A0h]
0x18000a841  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x18000a846  test    al, al
0x18000a848  jz      loc_18000A911
0x18000a84e  mov     eax, [rsp+888h+var_7F4]
0x18000a855  mov     [rsi+1A8h], eax
0x18000a85b  mov     rax, [rsi+1A0h]
0x18000a862  mov     rcx, [r12]
0x18000a866  mov     rdx, [r13+0]
0x18000a86a  lea     r8, [rsp+888h+var_7F7]
0x18000a872  mov     [rsp+888h+var_808], r8; struct EMBEDDED_PDB_INFORMATION *
0x18000a87a  lea     r8, [rsp+888h+var_798]
0x18000a882  mov     qword ptr [rsp+888h+var_810], r8; bool
0x18000a887  mov     r8b, [rsp+888h+var_7F8]
0x18000a88f  mov     [rsp+888h+MappedAsImage], r8b; MappedAsImage
0x18000a894  lea     r8, [rsp+888h+var_7F0]
0x18000a89c  mov     qword ptr [rsp+888h+var_820], r8; unsigned int
0x18000a8a1  mov     dword ptr [rsp+888h+var_828], 30Ch; unsigned __int16 *
0x18000a8a9  mov     r8, [rsp+888h+Size]
0x18000a8b1  mov     [rsp+888h+var_830], r8; unsigned int *
0x18000a8b6  lea     r8, [rsp+888h+var_7E4]
0x18000a8be  mov     [rsp+888h+var_838], r8; unsigned int *
0x18000a8c3  lea     r8, [rsp+888h+var_7D4]
0x18000a8cb  mov     [rsp+888h+var_840], r8; struct CODEVIEW_INFORMATION_1 *
0x18000a8d0  mov     [rsp+888h+var_848], rax; unsigned int *
0x18000a8d5  mov     [rsp+888h+var_850], rcx; union _CVDD *
0x18000a8da  mov     [rsp+888h+var_858], rdx; unsigned int *
0x18000a8df  lea     rax, [rsp+888h+var_7F4]
0x18000a8e7  mov     [rsp+888h+var_860], rax; unsigned int *
0x18000a8ec  mov     r9d, [rsp+888h+var_7D8]; unsigned int
0x18000a8f4  mov     r8d, [rsp+888h+pguid.Data1]; void *
0x18000a8fc  mov     rdx, rbx; unsigned __int16 *
0x18000a8ff  mov     rcx, [rsp+888h+var_7B8]; this
0x18000a907  call    ?CvDbgInfoFromImage2@Internal@XPerf@@YAJPEBGPEAXKK_NPEAKPEAT_CVDD@@3PEAUCODEVIEW_INFORMATION_1@@33PEAGKAEA_N2AEAUEMBEDDED_PDB_INFORMATION@@7@Z; XPerf::Internal::CvDbgInfoFromImage2(ushort const *,void *,ulong,ulong,bool,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,ulong *,ulong *,ushort *,ulong,bool &,bool,EMBEDDED_PDB_INFORMATION &,bool &)
  ... truncated ...
```
