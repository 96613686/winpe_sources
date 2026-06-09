# GetConfidenceFileMetadataInfo(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18002cfac`
- end: `0x18002da04`
- name: `?GetConfidenceFileMetadataInfo@@YAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `2648`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180031170`

## callees

- `0x1800078b0`
- `0x180008610`
- `0x18000eb18`
- `0x18000eb54`
- `0x180023634`
- `0x18002386c`
- `0x180026b9c`
- `0x180026dbc`
- `0x180029acc`
- `0x180029cfc`
- `0x18002a2f4`
- `0x18002a5b8`
- `0x18002a738`
- `0x18002a9ec`
- `0x18002acf4`
- `0x18002ad1c`
- `0x18002b300`
- `0x18002b504`
- `0x18002b600`
- `0x18002b68c`
- `0x18002b724`
- `0x18002ba18`
- `0x18002ba74`
- `0x18002bb44`
- `0x18002bf4c`
- `0x18002c020`
- `0x18002cfac`
- `0x18002da0c`
- `0x18002db78`
- `0x18002fa88`
- `0x18003084c`
- `0x180030b6c`
- `0x180031cd8`
- `0x180031d2c`
- `0x180033488`
- `0x1800334d4`
- `0x1800339b8`
- `0x18003c0b8`

## import_xrefs

- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x18002d1b0`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x18002d1b0`

## string_xrefs

- `0x18002d0e2`: `Failed to get OEMManufacturerName from registry: %x`
- `0x18002d176`: `Loading Metadata JSON from %s`
- `0x18002d1ca`: `Failed to open Metadata JSON from %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall GetConfidenceFileMetadataInfo(__int64 a1)
{
  int DeviceOEMName; // eax
  unsigned int v3; // ebx
  __int64 result; // rax
  __int64 FirstWord; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  _QWORD *v11; // rax
  _BYTE *v12; // rbx
  __int64 v13; // rax
  _BYTE *v14; // rax
  int v15; // ecx
  __int64 v16; // rax
  _BYTE *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  _QWORD *v21; // rax
  _BYTE *v22; // rax
  int v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // ebx
  __int64 v26; // rax
  _QWORD *v27; // rax
  _BYTE *v28; // rax
  __int64 v29; // r9
  _BYTE *v30; // rax
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // [rsp+30h] [rbp-348h] BYREF
  bool v38; // [rsp+38h] [rbp-340h]
  char v39; // [rsp+39h] [rbp-33Fh]
  int v40; // [rsp+3Ah] [rbp-33Eh]
  __int16 v41; // [rsp+3Eh] [rbp-33Ah]
  char v42[16]; // [rsp+50h] [rbp-328h] BYREF
  unsigned __int8 *v43; // [rsp+60h] [rbp-318h] BYREF
  __int16 v44; // [rsp+68h] [rbp-310h]
  int v45; // [rsp+6Ah] [rbp-30Eh]
  __int16 v46; // [rsp+6Eh] [rbp-30Ah]
  const std::exception *v47; // [rsp+80h] [rbp-2F8h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+88h] [rbp-2F0h] BYREF
  _QWORD v49[34]; // [rsp+A0h] [rbp-2D8h] BYREF
  _BYTE v50[32]; // [rsp+1B0h] [rbp-1C8h] BYREF
  _OWORD v51[2]; // [rsp+1D0h] [rbp-1A8h] BYREF
  _BYTE v52[32]; // [rsp+1F0h] [rbp-188h] BYREF
  _QWORD Src[4]; // [rsp+210h] [rbp-168h] BYREF
  __int64 v54; // [rsp+230h] [rbp-148h] BYREF
  __int128 v55; // [rsp+238h] [rbp-140h] BYREF
  __int64 v56; // [rsp+248h] [rbp-130h]
  __int64 v57; // [rsp+250h] [rbp-128h]
  __int128 v58; // [rsp+258h] [rbp-120h] BYREF
  __int64 v59; // [rsp+268h] [rbp-110h]
  __int64 v60; // [rsp+270h] [rbp-108h]
  __int128 v61; // [rsp+278h] [rbp-100h] BYREF
  __int64 v62; // [rsp+288h] [rbp-F0h]
  __int64 v63; // [rsp+290h] [rbp-E8h]
  __int128 v64; // [rsp+298h] [rbp-E0h] BYREF
  __int64 v65; // [rsp+2A8h] [rbp-D0h]
  __int64 v66; // [rsp+2B0h] [rbp-C8h]
  __int128 v67; // [rsp+2B8h] [rbp-C0h] BYREF
  __int64 v68; // [rsp+2C8h] [rbp-B0h]
  __int64 v69; // [rsp+2D0h] [rbp-A8h]
  __int128 v70; // [rsp+2D8h] [rbp-A0h]
  __int64 v71; // [rsp+2E8h] [rbp-90h]
  __int64 v72; // [rsp+2F0h] [rbp-88h]
  __int64 v73; // [rsp+2F8h] [rbp-80h]
  _QWORD v74[4]; // [rsp+300h] [rbp-78h] BYREF
  _BYTE v75[56]; // [rsp+320h] [rbp-58h] BYREF
  __int64 v76; // [rsp+358h] [rbp-20h]

  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 7;
  LOWORD(v55) = 0;
  v58 = 0;
  v59 = 0;
  v60 = 7;
  LOWORD(v58) = 0;
  v61 = 0;
  v62 = 0;
  v63 = 7;
  LOWORD(v61) = 0;
  v64 = 0;
  v65 = 0;
  v66 = 7;
  LOWORD(v64) = 0;
  v67 = 0;
  v68 = 0;
  v69 = 7;
  LOWORD(v67) = 0;
  v70 = 0;
  v71 = 0;
  v72 = 7;
  LOWORD(v70) = 0;
  v73 = 0;
  Utf8ToWide(v52, a1);
  v51[0] = 0;
  v51[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v51[0]) = 0;
  DeviceOEMName = GetDeviceOEMName(v51);
  try
  {
    v3 = DeviceOEMName;
    if ( DeviceOEMName < 0 )
    {
      SBServicingLogMessage(
        (wchar_t *)L"Failed to get OEMManufacturerName from registry: %x",
        (unsigned int)DeviceOEMName);
      std::wstring::_Tidy_deallocate(v51);
      std::wstring::_Tidy_deallocate(v52);
      MetadataInfo::~MetadataInfo((MetadataInfo *)&v54);
      return v3;
    }
    std::wstring::operator=(&v64, v51);
    FirstWord = GetFirstWord(v50, v51);
    std::wstring::operator=(&v67, FirstWord);
    std::wstring::_Tidy_deallocate(v50);
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52);
    SBServicingLogMessage((wchar_t *)L"Loading Metadata JSON from %s", v6);
    std::ifstream::ifstream(v49, a1, 32);
    if ( (unsigned __int8)std::ios_base::operator!((char *)v49 + *(int *)(v49[0] + 4LL)) )
    {
      v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52);
      SBServicingLogMessage((wchar_t *)L"Failed to open Metadata JSON from %s", v7);
      std::ifstream::`vbase destructor'(v49);
      std::wstring::_Tidy_deallocate(v51);
      std::wstring::_Tidy_deallocate(v52);
      MetadataInfo::~MetadataInfo((MetadataInfo *)&v54);
      return 2147942402LL;
    }
    v8 = *(_QWORD *)((char *)&v49[9] + *(int *)(v49[0] + 4LL));
    v43 = 0;
    v44 = 1;
    v45 = v40;
    v46 = v41;
    v37 = v8;
    v38 = v8 == 0;
    v39 = 0;
    std::string::string(Src);
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>((__int64)v42);
    try
    {
      v76 = 0;
      v9 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::parse<std::string,0>(
             (__int64)&v37,
             Src,
             (__int64)v75);
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::operator=(
        v42,
        v9);
    }
    catch ( ... )
    {
      v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52);
      SBServicingLogMessage((wchar_t *)L"JSON parse failed: %s", v35);
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>((__int64)v42);
      std::string::_Tidy_deallocate(Src);
      std::ifstream::`vbase destructor'(v49);
      std::wstring::_Tidy_deallocate(v51);
      std::wstring::_Tidy_deallocate(v52);
      MetadataInfo::~MetadataInfo((MetadataInfo *)&v54);
      return 2147942413LL;
    }
    v10 = std::string::string(v50, "Header");
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::find(
      v42,
      &v37,
      v10);
    v11 = (_QWORD *)nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::end(
                      v42,
                      v75);
    if ( nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator==(
           (__int64)&v37,
           v11)
      || *nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator->(&v37) != 1 )
    {
      SBServicingLogMessage((wchar_t *)L"Header missing or invalid");
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>((__int64)v42);
      std::string::_Tidy_deallocate(Src);
      std::ifstream::`vbase destructor'(v49);
      std::wstring::_Tidy_deallocate(v51);
      std::wstring::_Tidy_deallocate(v52);
      MetadataInfo::~MetadataInfo((MetadataInfo *)&v54);
      result = 2147942413LL;
    }
    else
    {
      v12 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator*(&v37);
      v13 = std::string::string(v50, "Version");
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::find(
        v12,
        &v37,
        v13);
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::const_iterator(
        &v43,
        (__int64)v12);
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::set_end(&v43);
      if ( nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator==(
             (__int64)&v37,
             &v43)
        || *nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator->(&v37) != 6 )
      {
        SBServicingLogMessage((wchar_t *)L"Header.Version missing or invalid");
        nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>((__int64)v42);
        std::string::_Tidy_deallocate(Src);
        std::ifstream::`vbase destructor'(v49);
        std::wstring::_Tidy_deallocate(v51);
        std::wstring::_Tidy_deallocate(v52);
        MetadataInfo::~MetadataInfo((MetadataInfo *)&v54);
        result = 2147942413LL;
      }
      else
      {
        v14 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator->(&v37);
        if ( *v14 == 5 || *v14 == 6 )
        {
          v15 = *((_DWORD *)v14 + 2);
        }
        else
        {
          if ( *v14 != 7 )
          {
            v33 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::type_name(
                    v14,
                    v75);
            v34 = std::operator+<char>(v50, "type must be number, but is ", v33);
            std::invalid_argument::invalid_argument(pExceptionObject, v34);
            throw (std::domain_error *)pExceptionObject;
          }
          v15 = (int)*((double *)v14 + 1);
        }
        LODWORD(v54) = v15;
        v16 = std::string::string(v50, "Timestamp");
        nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::find(
          v12,
          &v37,
          v16);
        nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::const_iterator(
          &v43,
          (__int64)v12);
        nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::set_end(&v43);
        if ( nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator==(
               (__int64)&v37,
               &v43)
          || *nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator->(&v37) != 3 )
        {
          SBServicingLogMessage((wchar_t *)L"Header.Timestamp missing or invalid");
          nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>((__int64)v42);
          std::string::_Tidy_deallocate(Src);
          std::ifstream::`vbase destructor'(v49);
          std::wstring::_Tidy_deallocate(v51);
          std::wstring::_Tidy_deallocate(v52);
          MetadataInfo::~MetadataInfo((MetadataInfo *)&v54);
          result = 2147942413LL;
        }
        else
        {
          v17 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator->(&v37);
          v18 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::get<std::string,0>(
                  (__int64)v17,
                  (__int64)v74);
          v19 = Utf8ToWide(v50, v18);
          std::wstring::operator=(&v55, v19);
          std::wstring::_Tidy_deallocate(v50);
          std::string::_Tidy_deallocate(v74);
          v20 = std::string::string(v50, "OEMEntries");
          nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::find(
            v42,
            &v37,
            v20);
          v21 = (_QWORD *)nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::end(
                            v42,
                            v75);
          if ( nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator==(
                 (__int64)&v37,
                 v21)
            || *nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator->(&v37) != 1 )
          {
            SBServicingLogMessage((wchar_t *)L"OEMEntries missing or invalid");
            nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>((__int64)v42);
            std::string::_Tidy_deallocate(Src);
            std::ifstream::`vbase destructor'(v49);
            std::wstring::_Tidy_deallocate(v51);
            std::wstring::_Tidy_deallocate(v52);
            MetadataInfo::~MetadataInfo((MetadataInfo *)&v54);
            result = 2147942413LL;
          }
          else
          {
            v22 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator*(&v37);
            v23 = CalculateBucketId((__int64)v22, (__int64)&v58, (__int64)&v61);
            v25 = v23;
            if ( v23 >= 0 )
            {
              MetadataInfo::operator=(v24, &v54);
              v26 = std::string::string(v50, "KnownOEMs");
              nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::find(
                v42,
                &v37,
                v26);
              v27 = (_QWORD *)nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::end(
                                v42,
                                v75);
              if ( nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator==(
                     (__int64)&v37,
                     v27)
                || *nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator->(&v37) != 2 )
              {
                SBServicingLogMessage((wchar_t *)L"KnownOEMs missing or invalid");
                nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>((__int64)v42);
                std::string::_Tidy_deallocate(Src);
                std::ifstream::`vbase destructor'(v49);
                std::wstring::_Tidy_deallocate(v51);
                std::wstring::_Tidy_deallocate(v52);
                MetadataInfo::~MetadataInfo((MetadataInfo *)&v54);
                result = 2147942413LL;
              }
              else
              {
                v28 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator*(&v37);
                nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::const_iterator(
                  &v43,
                  (__int64)v28);
                nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::set_begin(&v43);
                nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::const_iterator(
                  v74,
                  v29);
                nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::set_end(v74);
                while ( !nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator==(
                           (__int64)&v43,
                           v74) )
                {
                  v30 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator*(&v43);
                  if ( *v30 == 3 )
                  {
                    v31 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::get<std::string,0>(
                            (__int64)v30,
                            (__int64)v75);
                    Utf8ToWide(v50, v31);
                    std::string::_Tidy_deallocate(v75);
                    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
                      v32,
                      (__int64)&v37,
                      (__int64)v50);
                    std::wstring::_Tidy_deallocate(v50);
                  }
                  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator++(&v43);
                }
                nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>((__int64)v42);
                std::string::_Tidy_deallocate(Src);
                std::ifstream::`vbase destructor'(v49);
                std::wstring::_Tidy_deallocate(v51);
                std::wstring::_Tidy_deallocate(v52);
                MetadataInfo::~MetadataInfo((MetadataInfo *)&v54);
                result = 0;
              }
            }
            else
            {
              SBServicingLogMessage((wchar_t *)L"Failed CalculateBucketId : %x", (unsigned int)v23);
              nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>((__int64)v42);
              std::string::_Tidy_deallocate(Src);
              std::ifstream::`vbase destructor'(v49);
              std::wstring::_Tidy_deallocate(v51);
              std::wstring::_Tidy_deallocate(v52);
              MetadataInfo::~MetadataInfo((MetadataInfo *)&v54);
              result = v25;
            }
          }
        }
      }
    }
  }
  catch ( std::bad_alloc )
  {
    SBServicingLogMessage((wchar_t *)L"GetConfidenceFileMetadataInfo failed with out of memory");
    std::wstring::_Tidy_deallocate(v52);
    MetadataInfo::~MetadataInfo((MetadataInfo *)&v54);
    return 2147942414LL;
  }
  catch ( const std::exception *v47 )
  {
    v36 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v47 + 8LL))(v47);
    SBServicingLogMessage((wchar_t *)L"GetConfidenceFileMetadataInfo failed with Error: %hs", v36);
    std::wstring::_Tidy_deallocate(v52);
    MetadataInfo::~MetadataInfo((MetadataInfo *)&v54);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002cfac  mov     r11, rsp
0x18002cfaf  mov     [r11+10h], rbx
0x18002cfb3  push    rdi
0x18002cfb4  sub     rsp, 370h
0x18002cfbb  mov     rax, cs:__security_cookie
0x18002cfc2  xor     rax, rsp
0x18002cfc5  mov     [rsp+378h+var_18], rax
0x18002cfcd  mov     rdi, rcx
0x18002cfd0  xor     eax, eax
0x18002cfd2  mov     [r11-148h], rax
0x18002cfd9  xorps   xmm0, xmm0
0x18002cfdc  movups  [rsp+378h+var_140], xmm0
0x18002cfe4  mov     [r11-130h], rax
0x18002cfeb  lea     ecx, [rax+7]
0x18002cfee  mov     [r11-128h], rcx
0x18002cff5  mov     word ptr [rsp+378h+var_140], ax
0x18002cffd  movups  [rsp+378h+var_120], xmm0
0x18002d005  mov     [r11-110h], rax
0x18002d00c  mov     [r11-108h], rcx
0x18002d013  mov     word ptr [rsp+378h+var_120], ax
0x18002d01b  movups  [rsp+378h+var_100], xmm0
0x18002d023  mov     [r11-0F0h], rax
0x18002d02a  mov     [r11-0E8h], rcx
0x18002d031  mov     word ptr [rsp+378h+var_100], ax
0x18002d039  movups  [rsp+378h+var_E0], xmm0
0x18002d041  mov     [r11-0D0h], rax
0x18002d048  mov     [r11-0C8h], rcx
0x18002d04f  mov     word ptr [rsp+378h+var_E0], ax
0x18002d057  movups  [rsp+378h+var_C0], xmm0
0x18002d05f  mov     [r11-0B0h], rax
0x18002d066  mov     [r11-0A8h], rcx
0x18002d06d  mov     word ptr [rsp+378h+var_C0], ax
0x18002d075  movups  [rsp+378h+var_A0], xmm0
0x18002d07d  mov     [r11-90h], rax
0x18002d084  mov     [r11-88h], rcx
0x18002d08b  mov     word ptr [rsp+378h+var_A0], ax
0x18002d093  mov     [r11-80h], rax
0x18002d097  mov     rdx, rdi
0x18002d09a  lea     rcx, [r11-188h]
0x18002d0a1  call    ?Utf8ToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; Utf8ToWide(std::string const &)
0x18002d0a6  nop
0x18002d0a7  xorps   xmm0, xmm0
0x18002d0aa  movups  [rsp+378h+var_1A8], xmm0
0x18002d0b2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002d0ba  movdqu  [rsp+378h+var_198], xmm1
0x18002d0c3  xor     eax, eax
0x18002d0c5  mov     word ptr [rsp+378h+var_1A8], ax
0x18002d0cd  lea     rcx, [rsp+378h+var_1A8]
0x18002d0d5  call    ?GetDeviceOEMName@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetDeviceOEMName(std::wstring &)
0x18002d0da  mov     ebx, eax
0x18002d0dc  test    eax, eax
0x18002d0de  jns     short loc_18002D11F
0x18002d0e0  mov     edx, eax
0x18002d0e2  lea     rcx, aFailedToGetOem; "Failed to get OEMManufacturerName from "...
0x18002d0e9  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002d0ee  nop
0x18002d0ef  lea     rcx, [rsp+378h+var_1A8]
0x18002d0f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d0fc  nop
0x18002d0fd  lea     rcx, [rsp+378h+var_188]
0x18002d105  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d10a  nop
0x18002d10b  lea     rcx, [rsp+378h+var_148]; this
0x18002d113  call    ??1MetadataInfo@@QEAA@XZ; MetadataInfo::~MetadataInfo(void)
0x18002d118  mov     eax, ebx
0x18002d11a  jmp     loc_18002D994
0x18002d11f  lea     rdx, [rsp+378h+var_1A8]
0x18002d127  lea     rcx, [rsp+378h+var_E0]
0x18002d12f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002d134  lea     rdx, [rsp+378h+var_1A8]
0x18002d13c  lea     rcx, [rsp+378h+var_1C8]
0x18002d144  call    ?GetFirstWord@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; GetFirstWord(std::wstring const &)
0x18002d149  mov     rdx, rax
0x18002d14c  lea     rcx, [rsp+378h+var_C0]
0x18002d154  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002d159  lea     rcx, [rsp+378h+var_1C8]
0x18002d161  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d166  lea     rcx, [rsp+378h+var_188]
0x18002d16e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002d173  mov     rdx, rax
0x18002d176  lea     rcx, aLoadingMetadat; "Loading Metadata JSON from %s"
0x18002d17d  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002d182  mov     r8d, 20h ; ' '
0x18002d188  mov     rdx, rdi
0x18002d18b  lea     rcx, [rsp+378h+var_2D8]
0x18002d193  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@HH@Z; std::ifstream::ifstream(std::string const &,int,int)
0x18002d198  nop
0x18002d199  mov     rax, [rsp+378h+var_2D8]
0x18002d1a1  movsxd  rcx, dword ptr [rax+4]
0x18002d1a5  lea     rax, [rsp+378h+var_2D8]
0x18002d1ad  add     rcx, rax
0x18002d1b0  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x18002d1b6  test    al, al
0x18002d1b8  jz      short loc_18002D218
0x18002d1ba  lea     rcx, [rsp+378h+var_188]
0x18002d1c2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002d1c7  mov     rdx, rax
0x18002d1ca  lea     rcx, aFailedToOpenMe; "Failed to open Metadata JSON from %s"
0x18002d1d1  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002d1d6  nop
0x18002d1d7  lea     rcx, [rsp+378h+var_2D8]
0x18002d1df  call    ??_D?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ifstream::`vbase destructor'(void)
0x18002d1e4  nop
0x18002d1e5  lea     rcx, [rsp+378h+var_1A8]
0x18002d1ed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d1f2  nop
0x18002d1f3  lea     rcx, [rsp+378h+var_188]
0x18002d1fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d200  nop
0x18002d201  lea     rcx, [rsp+378h+var_148]; this
0x18002d209  call    ??1MetadataInfo@@QEAA@XZ; MetadataInfo::~MetadataInfo(void)
0x18002d20e  mov     eax, 80070002h
0x18002d213  jmp     loc_18002D994
0x18002d218  mov     rax, [rsp+378h+var_2D8]
0x18002d220  movsxd  rcx, dword ptr [rax+4]
0x18002d224  mov     rdx, [rsp+rcx+378h+var_290]
0x18002d22c  mov     [rsp+378h+var_318], 0
0x18002d235  mov     [rsp+378h+var_310], 1
0x18002d23c  mov     eax, [rsp+378h+var_33E]
0x18002d240  mov     [rsp+378h+var_30E], eax
0x18002d244  movzx   eax, [rsp+378h+var_33A]
0x18002d249  mov     [rsp+378h+var_30A], ax
0x18002d24e  mov     [rsp+378h+var_348], rdx
0x18002d253  test    rdx, rdx
0x18002d256  setz    [rsp+378h+var_340]
0x18002d25b  mov     [rsp+378h+var_33F], 0
0x18002d260  mov     eax, [rsp+378h+var_33E]
0x18002d264  mov     [rsp+378h+var_33E], eax
0x18002d268  movzx   eax, [rsp+378h+var_33A]
0x18002d26d  mov     [rsp+378h+var_33A], ax
0x18002d272  lea     r8, [rsp+378h+var_318]
0x18002d277  lea     rdx, [rsp+378h+var_348]
0x18002d27c  lea     rcx, [rsp+378h+Src]; Src
0x18002d284  call    ??$?0V?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@V?$istreambuf_iterator@DU?$char_traits@D@std@@@1@0AEBV?$allocator@D@1@@Z; std::string::string(std::istreambuf_iterator<char>,std::istreambuf_iterator<char>,std::allocator<char> const &)
0x18002d289  nop
0x18002d28a  lea     rcx, [rsp+378h+var_328]
0x18002d28f  call    ??0?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEAA@$$T@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>(std::nullptr_t)
0x18002d294  nop
0x18002d295  mov     [rsp+378h+var_20], 0
0x18002d2a1  lea     r8, [rsp+378h+var_58]
0x18002d2a9  lea     rdx, [rsp+378h+Src]
0x18002d2b1  lea     rcx, [rsp+378h+var_348]
0x18002d2b6  call    ??$parse@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@SA?AV01@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$function@$$A6A_NHW4parse_event_t@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@AEAV23@@Z@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::parse<std::string,0>(std::string const &,std::function<bool (int,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::parse_event_t,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator> &)>)
0x18002d2bb  mov     rdx, rax
0x18002d2be  lea     rcx, [rsp+378h+var_328]
0x18002d2c3  call    ??4?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEAAAEAV01@V01@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::operator=(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>)
0x18002d2c8  nop
0x18002d2c9  lea     rdx, aHeader; "Header"
0x18002d2d0  lea     rcx, [rsp+378h+var_1C8]
0x18002d2d8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002d2dd  mov     r8, rax
0x18002d2e0  lea     rdx, [rsp+378h+var_348]
0x18002d2e5  lea     rcx, [rsp+378h+var_328]
0x18002d2ea  call    ?find@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEAA?AViterator@12@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::find(std::string)
0x18002d2ef  lea     rdx, [rsp+378h+var_58]
0x18002d2f7  lea     rcx, [rsp+378h+var_328]
0x18002d2fc  call    ?end@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEAA?AViterator@12@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::end(void)
0x18002d301  mov     rdx, rax
0x18002d304  lea     rcx, [rsp+378h+var_348]
0x18002d309  call    ??8const_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBA_NAEBV012@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator==(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator const &)
0x18002d30e  test    al, al
0x18002d310  jnz     loc_18002D894
0x18002d316  lea     rcx, [rsp+378h+var_348]
0x18002d31b  call    ??Cconst_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBAPEBV12@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator->(void)
0x18002d320  cmp     byte ptr [rax], 1
0x18002d323  jnz     loc_18002D894
0x18002d329  lea     rcx, [rsp+378h+var_348]
0x18002d32e  call    ??Dconst_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBAAEBV12@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator*(void)
0x18002d333  mov     rbx, rax
0x18002d336  lea     rdx, aVersion; "Version"
0x18002d33d  lea     rcx, [rsp+378h+var_1C8]
0x18002d345  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002d34a  mov     r8, rax
0x18002d34d  lea     rdx, [rsp+378h+var_348]
0x18002d352  mov     rcx, rbx
0x18002d355  call    ?find@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBA?AVconst_iterator@12@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::find(std::string)
0x18002d35a  mov     rdx, rbx
0x18002d35d  lea     rcx, [rsp+378h+var_318]
0x18002d362  call    ??0const_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEAA@PEBV12@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::const_iterator(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator> const *)
0x18002d367  lea     rcx, [rsp+378h+var_318]
0x18002d36c  call    ?set_end@const_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@AEAAXXZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::set_end(void)
0x18002d371  lea     rdx, [rsp+378h+var_318]
0x18002d376  lea     rcx, [rsp+378h+var_348]
0x18002d37b  call    ??8const_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBA_NAEBV012@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator==(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator const &)
0x18002d380  test    al, al
0x18002d382  jnz     loc_18002D82D
0x18002d388  lea     rcx, [rsp+378h+var_348]
0x18002d38d  call    ??Cconst_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBAPEBV12@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator->(void)
0x18002d392  cmp     byte ptr [rax], 6
0x18002d395  jnz     loc_18002D82D
0x18002d39b  lea     rcx, [rsp+378h+var_348]
0x18002d3a0  call    ??Cconst_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBAPEBV12@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator->(void)
0x18002d3a5  movzx   edx, byte ptr [rax]
0x18002d3a8  sub     edx, 5
0x18002d3ab  jz      short loc_18002D3C3
0x18002d3ad  sub     edx, 1
0x18002d3b0  jz      short loc_18002D3C3
0x18002d3b2  cmp     edx, 1
0x18002d3b5  jnz     loc_18002D9B5
0x18002d3bb  cvttsd2si rcx, qword ptr [rax+8]
0x18002d3c1  jmp     short loc_18002D3C6
0x18002d3c3  mov     ecx, [rax+8]
0x18002d3c6  mov     dword ptr [rsp+378h+var_148], ecx
0x18002d3cd  lea     rdx, aTimestamp; "Timestamp"
0x18002d3d4  lea     rcx, [rsp+378h+var_1C8]
0x18002d3dc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002d3e1  mov     r8, rax
0x18002d3e4  lea     rdx, [rsp+378h+var_348]
0x18002d3e9  mov     rcx, rbx
0x18002d3ec  call    ?find@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBA?AVconst_iterator@12@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::find(std::string)
0x18002d3f1  mov     rdx, rbx
0x18002d3f4  lea     rcx, [rsp+378h+var_318]
0x18002d3f9  call    ??0const_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEAA@PEBV12@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::const_iterator(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator> const *)
0x18002d3fe  lea     rcx, [rsp+378h+var_318]
0x18002d403  call    ?set_end@const_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@AEAAXXZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::set_end(void)
0x18002d408  lea     rdx, [rsp+378h+var_318]
0x18002d40d  lea     rcx, [rsp+378h+var_348]
0x18002d412  call    ??8const_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBA_NAEBV012@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator==(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator const &)
0x18002d417  test    al, al
0x18002d419  jnz     loc_18002D7C6
0x18002d41f  lea     rcx, [rsp+378h+var_348]
0x18002d424  call    ??Cconst_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBAPEBV12@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator->(void)
0x18002d429  cmp     byte ptr [rax], 3
0x18002d42c  jnz     loc_18002D7C6
0x18002d432  lea     rcx, [rsp+378h+var_348]
0x18002d437  call    ??Cconst_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBAPEBV12@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator->(void)
0x18002d43c  lea     rdx, [rsp+378h+var_78]
0x18002d444  mov     rcx, rax
0x18002d447  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::get<std::string,0>(void)
0x18002d44c  mov     rdx, rax
0x18002d44f  lea     rcx, [rsp+378h+var_1C8]
0x18002d457  call    ?Utf8ToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; Utf8ToWide(std::string const &)
0x18002d45c  mov     rdx, rax
0x18002d45f  lea     rcx, [rsp+378h+var_140]
0x18002d467  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002d46c  lea     rcx, [rsp+378h+var_1C8]
0x18002d474  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d479  lea     rcx, [rsp+378h+var_78]
0x18002d481  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002d486  lea     rdx, aOementries; "OEMEntries"
0x18002d48d  lea     rcx, [rsp+378h+var_1C8]
0x18002d495  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002d49a  mov     r8, rax
0x18002d49d  lea     rdx, [rsp+378h+var_348]
0x18002d4a2  lea     rcx, [rsp+378h+var_328]
0x18002d4a7  call    ?find@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEAA?AViterator@12@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::find(std::string)
0x18002d4ac  lea     rdx, [rsp+378h+var_58]
0x18002d4b4  lea     rcx, [rsp+378h+var_328]
0x18002d4b9  call    ?end@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEAA?AViterator@12@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::end(void)
0x18002d4be  mov     rdx, rax
0x18002d4c1  lea     rcx, [rsp+378h+var_348]
0x18002d4c6  call    ??8const_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBA_NAEBV012@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator==(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator const &)
0x18002d4cb  test    al, al
0x18002d4cd  jnz     loc_18002D75F
0x18002d4d3  lea     rcx, [rsp+378h+var_348]
0x18002d4d8  call    ??Cconst_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBAPEBV12@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator->(void)
0x18002d4dd  cmp     byte ptr [rax], 1
0x18002d4e0  jnz     loc_18002D75F
0x18002d4e6  lea     rcx, [rsp+378h+var_348]
0x18002d4eb  call    ??Dconst_iterator@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBAAEBV12@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::const_iterator::operator*(void)
0x18002d4f0  lea     r8, [rsp+378h+var_100]
0x18002d4f8  lea     rdx, [rsp+378h+var_120]
0x18002d500  mov     rcx, rax
0x18002d503  call    ?CalculateBucketId@@YAJAEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; CalculateBucketId(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator> const &,std::wstring &,std::wstring &)
0x18002d508  mov     ebx, eax
0x18002d50a  test    eax, eax
0x18002d50c  jns     short loc_18002D574
0x18002d50e  mov     edx, eax
0x18002d510  lea     rcx, aFailedCalculat; "Failed CalculateBucketId : %x"
0x18002d517  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002d51c  nop
0x18002d51d  lea     rcx, [rsp+378h+var_328]
0x18002d522  call    ??1?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEAA@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>(void)
0x18002d527  nop
0x18002d528  lea     rcx, [rsp+378h+Src]
0x18002d530  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002d535  nop
0x18002d536  lea     rcx, [rsp+378h+var_2D8]
0x18002d53e  call    ??_D?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ifstream::`vbase destructor'(void)
0x18002d543  nop
0x18002d544  lea     rcx, [rsp+378h+var_1A8]
0x18002d54c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d551  nop
0x18002d552  lea     rcx, [rsp+378h+var_188]
0x18002d55a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d55f  nop
0x18002d560  lea     rcx, [rsp+378h+var_148]; this
0x18002d568  call    ??1MetadataInfo@@QEAA@XZ; MetadataInfo::~MetadataInfo(void)
0x18002d56d  mov     eax, ebx
0x18002d56f  jmp     loc_18002D994
0x18002d574  lea     rdx, [rsp+378h+var_148]
0x18002d57c  call    ??4MetadataInfo@@QEAAAEAU0@AEBU0@@Z; MetadataInfo::operator=(MetadataInfo const &)
0x18002d581  lea     rdx, aKnownoems; "KnownOEMs"
0x18002d588  lea     rcx, [rsp+378h+var_1C8]
0x18002d590  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002d595  mov     r8, rax
0x18002d598  lea     rdx, [rsp+378h+var_348]
0x18002d59d  lea     rcx, [rsp+378h+var_328]
0x18002d5a2  call    ?find@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEAA?AViterator@12@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::find(std::string)
0x18002d5a7  lea     rdx, [rsp+378h+var_58]
  ... truncated ...
```
