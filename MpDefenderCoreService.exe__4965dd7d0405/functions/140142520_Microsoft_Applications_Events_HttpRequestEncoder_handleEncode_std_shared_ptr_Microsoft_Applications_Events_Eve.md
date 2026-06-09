# Microsoft::Applications::Events::HttpRequestEncoder::handleEncode(std::shared_ptr<Microsoft::Applications::Events::EventsUploadContext> const &)

- ea: `0x140142520`
- end: `0x140143584`
- name: `?handleEncode@HttpRequestEncoder@Events@Applications@Microsoft@@IEAA_NAEBV?$shared_ptr@VEventsUploadContext@Events@Applications@Microsoft@@@std@@@Z`
- size: `4196`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x14003a5c0`
- `0x14007dacc`
- `0x14007deb8`
- `0x14007e088`
- `0x140084a18`
- `0x140084b3c`
- `0x140085a00`
- `0x14009d4d0`
- `0x1400bead4`
- `0x1400e1560`
- `0x1400ea848`
- `0x1400fe950`
- `0x1400fedd4`
- `0x140116c34`
- `0x14012c87c`
- `0x14014248c`
- `0x140142520`
- `0x140166250`

## string_xrefs

- `0x1401427d0`: `application/bond-compact-binary`
- `0x140142c7a`: `AadDeviceToken`
- `0x140142bd1`: `Aad-Jwt-Token`
- `0x140142b24`: `Aad-Token`
- `0x140142a77`: `AuthXToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
char __fastcall Microsoft::Applications::Events::HttpRequestEncoder::handleEncode(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, __int128 *); // rbx
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, __int64); // rbx
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 SdkVersion; // rbx
  __int64 v12; // rbx
  __int64 v13; // rbx
  __int64 v14; // rbx
  Microsoft::Applications::Events::PlatformAbstraction *v15; // rcx
  Microsoft::Applications::Events::PlatformAbstraction::PlatformAbstractionLayer *v16; // rcx
  __int64 UtcSystemTimeMs; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // r14
  __int64 v24; // rax
  __int64 v25; // r9
  __int64 v26; // r8
  int v27; // edx
  __int64 *v28; // rcx
  __int64 v29; // rdi
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 *v34; // rcx
  __int64 v35; // rdi
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 *v40; // rcx
  __int64 v41; // rdi
  __int64 v42; // rbx
  __int64 v43; // rax
  __int64 v44; // r8
  __int64 v45; // rdx
  __int64 *v46; // rcx
  __int64 v47; // rdi
  __int64 v48; // rbx
  __int64 v49; // rax
  __int64 v50; // r8
  __int64 v51; // rdx
  __int64 *v52; // rcx
  __int64 v53; // rdi
  __int64 v54; // rbx
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rbx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // r8
  __int64 v66; // rdx
  __int64 *v67; // rcx
  char *v68; // r9
  unsigned int v69; // r8d
  __int64 v70; // rax
  __int64 v71; // r8
  __int64 v72; // rdx
  __int64 *v73; // rcx
  char *v74; // r9
  unsigned int v75; // r8d
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 *v79; // rcx
  char *v80; // r9
  unsigned int v81; // r8d
  __int64 v82; // rbx
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rbx
  __int64 *v87; // rbx
  unsigned __int64 v88; // rcx
  __int128 *p_Src; // rax
  __int64 **v90; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v93; // rbx
  __int64 v94; // rbx
  __int64 v95; // rcx
  void (__fastcall *v96)(__int64, __int64); // rbx
  __int64 v97; // rax
  int v99; // [rsp+20h] [rbp-89h] BYREF
  _BYTE v100[32]; // [rsp+28h] [rbp-81h] BYREF
  _BYTE v101[32]; // [rsp+48h] [rbp-61h] BYREF
  __int128 v102; // [rsp+68h] [rbp-41h] BYREF
  __int128 v103; // [rsp+78h] [rbp-31h]
  __int128 Src; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int64 v105; // [rsp+98h] [rbp-11h]
  unsigned __int64 v106; // [rsp+A0h] [rbp-9h]
  __int128 v107; // [rsp+A8h] [rbp-1h] BYREF
  __int128 v108; // [rsp+B8h] [rbp+Fh] BYREF

  *(_QWORD *)(*(_QWORD *)a2 + 128LL) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 40) + 24LL))(*(_QWORD *)(a1 + 40));
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 8LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
  std::string::operator=((void *)(*(_QWORD *)a2 + 136LL));
  v4 = *(_QWORD *)(*(_QWORD *)a2 + 128LL);
  v5 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v4 + 16LL);
  v102 = 0;
  v103 = 0;
  std::string::_Construct<1,char const *>(&v102, "POST", 4u);
  v5(v4, &v102);
  std::string::_Tidy_deallocate(&v102);
  v6 = *(_QWORD *)(*(_QWORD *)a2 + 128LL);
  v7 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 24LL);
  v8 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 48) + 16LL))(*(_QWORD *)(a1 + 48), v100);
  v7(v6, v8);
  std::string::_Tidy_deallocate(v100);
  v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
  v107 = 0;
  v108 = 0;
  std::string::_Construct<1,char const *>(&v107, "100-continue", 0xCu);
  v102 = 0;
  v103 = 0;
  std::string::_Construct<1,char const *>(&v102, "Expect", 6u);
  Microsoft::Applications::Events::HttpHeaders::set(v9, &v102, &v107);
  std::string::_Tidy_deallocate(&v102);
  std::string::_Tidy_deallocate(&v107);
  v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
  SdkVersion = Microsoft::Applications::Events::PlatformAbstraction::getSdkVersion();
  v102 = 0;
  v103 = 0;
  std::string::_Construct<1,char const *>(&v102, "SDK-Version", 0xBu);
  Microsoft::Applications::Events::HttpHeaders::set(v10, &v102, SdkVersion);
  std::string::_Tidy_deallocate(&v102);
  v12 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
  v107 = 0;
  v108 = 0;
  std::string::_Construct<1,char const *>(&v107, "NO_AUTH", 7u);
  v102 = 0;
  v103 = 0;
  std::string::_Construct<1,char const *>(&v102, "Client-Id", 9u);
  Microsoft::Applications::Events::HttpHeaders::set(v12, &v102, &v107);
  std::string::_Tidy_deallocate(&v102);
  std::string::_Tidy_deallocate(&v107);
  v13 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
  v107 = 0;
  v108 = 0;
  std::string::_Construct<1,char const *>(&v107, "application/bond-compact-binary", 0x1Fu);
  v102 = 0;
  v103 = 0;
  std::string::_Construct<1,char const *>(&v102, "Content-Type", 0xCu);
  Microsoft::Applications::Events::HttpHeaders::set(v13, &v102, &v107);
  std::string::_Tidy_deallocate(&v102);
  std::string::_Tidy_deallocate(&v107);
  v14 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
  Microsoft::Applications::Events::PlatformAbstraction::GetPAL(v15);
  UtcSystemTimeMs = Microsoft::Applications::Events::PlatformAbstraction::PlatformAbstractionLayer::getUtcSystemTimeMs(v16);
  std::to_string(&v107, UtcSystemTimeMs);
  v102 = 0;
  v103 = 0;
  std::string::_Construct<1,char const *>(&v102, "Upload-Time", 0xBu);
  Microsoft::Applications::Events::HttpHeaders::set(v14, &v102, &v107);
  std::string::_Tidy_deallocate(&v102);
  std::string::_Tidy_deallocate(&v107);
  v18 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 64LL))(*(_QWORD *)(a1 + 32));
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v18 + 8) + 8LL))(v18 + 8) )
  {
    v19 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 64LL))(*(_QWORD *)(a1 + 32));
    v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v19 + 8) + 8LL))(v19 + 8);
    if ( *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 48LL))(v20) + 8) )
    {
      v21 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 64LL))(*(_QWORD *)(a1 + 32));
      v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v21 + 8) + 8LL))(v21 + 8);
      v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 48LL))(v22);
      v24 = *(_QWORD *)v23;
      v25 = *(_QWORD *)(*(_QWORD *)v23 + 8LL);
      HIDWORD(v107) = 0;
      v26 = v24;
      while ( !*(_BYTE *)(v25 + 25) )
      {
        v27 = *(_DWORD *)(v25 + 32);
        if ( v27 >= 0 )
          v26 = v25;
        v28 = (__int64 *)(v25 + 16);
        if ( v27 >= 0 )
          v28 = (__int64 *)v25;
        v25 = *v28;
      }
      if ( !*(_BYTE *)(v26 + 25) && *(int *)(v26 + 32) <= 0 && v24 != v26 )
      {
        v29 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
        v99 = 0;
        v30 = std::map<enum Microsoft::Applications::Events::TicketType,std::string>::operator[](v23, &v99);
        v102 = 0;
        v103 = 0;
        std::string::_Construct<1,char const *>(&v102, "AuthMsaDeviceTicket", 0x13u);
        Microsoft::Applications::Events::HttpHeaders::set(v29, &v102, v30);
        std::string::_Tidy_deallocate(&v102);
      }
      v31 = *(_QWORD *)v23;
      v32 = *(_QWORD *)(*(_QWORD *)v23 + 8LL);
      HIDWORD(v107) = 0;
      v33 = v31;
      while ( !*(_BYTE *)(v32 + 25) )
      {
        if ( *(int *)(v32 + 32) >= 2 )
          v33 = v32;
        v34 = (__int64 *)(v32 + 16);
        if ( *(int *)(v32 + 32) >= 2 )
          v34 = (__int64 *)v32;
        v32 = *v34;
      }
      if ( !*(_BYTE *)(v33 + 25) && *(int *)(v33 + 32) <= 2 && v31 != v33 )
      {
        v35 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
        v99 = 2;
        v36 = std::map<enum Microsoft::Applications::Events::TicketType,std::string>::operator[](v23, &v99);
        v102 = 0;
        v103 = 0;
        std::string::_Construct<1,char const *>(&v102, "AuthXToken", 0xAu);
        Microsoft::Applications::Events::HttpHeaders::set(v35, &v102, v36);
        std::string::_Tidy_deallocate(&v102);
      }
      v37 = *(_QWORD *)v23;
      v38 = *(_QWORD *)(*(_QWORD *)v23 + 8LL);
      HIDWORD(v107) = 0;
      v39 = v37;
      while ( !*(_BYTE *)(v38 + 25) )
      {
        if ( *(int *)(v38 + 32) >= 4 )
          v39 = v38;
        v40 = (__int64 *)(v38 + 16);
        if ( *(int *)(v38 + 32) >= 4 )
          v40 = (__int64 *)v38;
        v38 = *v40;
      }
      if ( !*(_BYTE *)(v39 + 25) && *(int *)(v39 + 32) <= 4 && v37 != v39 )
      {
        v41 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
        v99 = 4;
        v42 = std::map<enum Microsoft::Applications::Events::TicketType,std::string>::operator[](v23, &v99);
        v102 = 0;
        v103 = 0;
        std::string::_Construct<1,char const *>(&v102, "Aad-Token", 9u);
        Microsoft::Applications::Events::HttpHeaders::set(v41, &v102, v42);
        std::string::_Tidy_deallocate(&v102);
      }
      v43 = *(_QWORD *)v23;
      v44 = *(_QWORD *)(*(_QWORD *)v23 + 8LL);
      HIDWORD(v107) = 0;
      v45 = v43;
      while ( !*(_BYTE *)(v44 + 25) )
      {
        if ( *(int *)(v44 + 32) >= 6 )
          v45 = v44;
        v46 = (__int64 *)(v44 + 16);
        if ( *(int *)(v44 + 32) >= 6 )
          v46 = (__int64 *)v44;
        v44 = *v46;
      }
      if ( !*(_BYTE *)(v45 + 25) && *(int *)(v45 + 32) <= 6 && v43 != v45 )
      {
        v47 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
        v99 = 6;
        v48 = std::map<enum Microsoft::Applications::Events::TicketType,std::string>::operator[](v23, &v99);
        v102 = 0;
        v103 = 0;
        std::string::_Construct<1,char const *>(&v102, "Aad-Jwt-Token", 0xDu);
        Microsoft::Applications::Events::HttpHeaders::set(v47, &v102, v48);
        std::string::_Tidy_deallocate(&v102);
      }
      v49 = *(_QWORD *)v23;
      v50 = *(_QWORD *)(*(_QWORD *)v23 + 8LL);
      HIDWORD(v107) = 0;
      v51 = v49;
      while ( !*(_BYTE *)(v50 + 25) )
      {
        if ( *(int *)(v50 + 32) >= 7 )
          v51 = v50;
        v52 = (__int64 *)(v50 + 16);
        if ( *(int *)(v50 + 32) >= 7 )
          v52 = (__int64 *)v50;
        v50 = *v52;
      }
      if ( !*(_BYTE *)(v51 + 25) && *(int *)(v51 + 32) <= 7 && v49 != v51 )
      {
        v53 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
        v99 = 7;
        v54 = std::map<enum Microsoft::Applications::Events::TicketType,std::string>::operator[](v23, &v99);
        v102 = 0;
        v103 = 0;
        std::string::_Construct<1,char const *>(&v102, "AadDeviceToken", 0xEu);
        Microsoft::Applications::Events::HttpHeaders::set(v53, &v102, v54);
        std::string::_Tidy_deallocate(&v102);
      }
    }
  }
  v55 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 64LL))(*(_QWORD *)(a1 + 32));
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v55 + 8) + 8LL))(v55 + 8) )
  {
    v56 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 64LL))(*(_QWORD *)(a1 + 32));
    v57 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v56 + 8) + 8LL))(v56 + 8);
    if ( *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v57 + 56LL))(v57) + 8) )
    {
      v58 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 64LL))(*(_QWORD *)(a1 + 32));
      v59 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v58 + 8) + 8LL))(v58 + 8);
      v60 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v59 + 56LL))(v59);
      v102 = 0;
      *(_QWORD *)&v103 = 0;
      *((_QWORD *)&v103 + 1) = 15;
      LOBYTE(v102) = 0;
      v61 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 64LL))(*(_QWORD *)(a1 + 32));
      v62 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v61 + 8) + 8LL))(v61 + 8);
      v63 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 56LL))(v62);
      std::string::reserve(&v102, *(_QWORD *)(v63 + 8) << 10);
      v64 = *(_QWORD *)v60;
      v65 = *(_QWORD *)(*(_QWORD *)v60 + 8LL);
      HIDWORD(v107) = 0;
      v66 = v64;
      while ( !*(_BYTE *)(v65 + 25) )
      {
        if ( *(int *)(v65 + 32) >= 1 )
          v66 = v65;
        v67 = (__int64 *)(v65 + 16);
        if ( *(int *)(v65 + 32) >= 1 )
          v67 = (__int64 *)v65;
        v65 = *v67;
      }
      if ( !*(_BYTE *)(v66 + 25) && *(int *)(v66 + 32) <= 1 && v64 != v66 )
      {
        std::string::append(&v102);
        v68 = (char *)&v108 + 5;
        v69 = 1;
        do
        {
          *--v68 = v69 % 0xA + 48;
          v69 /= 0xAu;
        }
        while ( v69 );
        std::string::string(v100, v68, (char *)&v108 + 5);
        std::operator+<char>(v101, "1000", v100);
        std::string::append(&v102);
        std::string::_Tidy_deallocate(v101);
        std::string::_Tidy_deallocate(v100);
        std::string::append(&v102);
        std::string::append(&v102);
        v99 = 1;
        std::map<enum Microsoft::Applications::Events::TicketType,std::string>::operator[](v60, &v99);
        std::string::append(&v102);
        std::string::append(&v102);
      }
      v70 = *(_QWORD *)v60;
      v71 = *(_QWORD *)(*(_QWORD *)v60 + 8LL);
      HIDWORD(v107) = 0;
      v72 = v70;
      while ( !*(_BYTE *)(v71 + 25) )
      {
        if ( *(int *)(v71 + 32) >= 3 )
          v72 = v71;
        v73 = (__int64 *)(v71 + 16);
        if ( *(int *)(v71 + 32) >= 3 )
          v73 = (__int64 *)v71;
        v71 = *v73;
      }
      if ( !*(_BYTE *)(v72 + 25) && *(int *)(v72 + 32) <= 3 && v70 != v72 )
      {
        if ( (_QWORD)v103 )
          std::string::append(&v102);
        std::string::append(&v102);
        v74 = (char *)&v108 + 5;
        v75 = 3;
        do
        {
          *--v74 = v75 % 0xA + 48;
          v75 /= 0xAu;
        }
        while ( v75 );
        std::string::string(v100, v74, (char *)&v108 + 5);
        std::operator+<char>(v101, "1000", v100);
        std::string::append(&v102);
        std::string::_Tidy_deallocate(v101);
        std::string::_Tidy_deallocate(v100);
        std::string::append(&v102);
        std::string::append(&v102);
        v99 = 3;
        std::map<enum Microsoft::Applications::Events::TicketType,std::string>::operator[](v60, &v99);
        std::string::append(&v102);
        std::string::append(&v102);
      }
      v76 = *(_QWORD *)v60;
      v77 = *(_QWORD *)(*(_QWORD *)v60 + 8LL);
      HIDWORD(v107) = 0;
      v78 = v76;
      while ( !*(_BYTE *)(v77 + 25) )
      {
        if ( *(int *)(v77 + 32) >= 5 )
          v78 = v77;
        v79 = (__int64 *)(v77 + 16);
        if ( *(int *)(v77 + 32) >= 5 )
          v79 = (__int64 *)v77;
        v77 = *v79;
      }
      if ( !*(_BYTE *)(v78 + 25) && *(int *)(v78 + 32) <= 5 && v76 != v78 )
      {
        if ( (_QWORD)v103 )
          std::string::append(&v102);
        std::string::append(&v102);
        v80 = (char *)&v108 + 5;
        v81 = 5;
        do
        {
          *--v80 = v81 % 0xA + 48;
          v81 /= 0xAu;
        }
        while ( v81 );
        std::string::string(v100, v80, (char *)&v108 + 5);
        std::operator+<char>(v101, "1000", v100);
        std::string::append(&v102);
        std::string::_Tidy_deallocate(v101);
        std::string::_Tidy_deallocate(v100);
        std::string::append(&v102);
        std::string::append(&v102);
        v99 = 5;
        std::map<enum Microsoft::Applications::Events::TicketType,std::string>::operator[](v60, &v99);
        std::string::append(&v102);
        std::string::append(&v102);
      }
      if ( (_QWORD)v103 )
      {
        v82 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
        v107 = 0;
        v108 = 0;
        std::string::_Construct<1,char const *>(&v107, "Tickets", 7u);
        Microsoft::Applications::Events::HttpHeaders::set(v82, &v107, &v102);
        std::string::_Tidy_deallocate(&v107);
      }
      std::string::_Tidy_deallocate(&v102);
    }
  }
  v83 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 64LL))(*(_QWORD *)(a1 + 32));
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v83 + 8) + 8LL))(v83 + 8) )
  {
    v84 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 64LL))(*(_QWORD *)(a1 + 32));
    v85 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v84 + 8) + 8LL))(v84 + 8);
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v85 + 32LL))(v85) == 1 )
    {
      v86 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
      v107 = 0;
      v108 = 0;
      std::string::_Construct<1,char const *>(&v107, "true", 4u);
      v102 = 0;
      v103 = 0;
      std::string::_Construct<1,char const *>(&v102, "Strict", 6u);
      Microsoft::Applications::Events::HttpHeaders::set(v86, &v102, &v107);
      std::string::_Tidy_deallocate(&v102);
      std::string::_Tidy_deallocate(&v107);
    }
  }
  Src = 0;
  v105 = 0;
  v106 = 15;
  LOBYTE(Src) = 0;
  std::string::reserve(&Src, 75LL * *(_QWORD *)(*(_QWORD *)a2 + 40LL));
  v87 = **(__int64 ***)(*(_QWORD *)a2 + 32LL);
  while ( !*((_BYTE *)v87 + 25) )
  {
    v88 = v105;
    if ( v105 )
    {
      if ( v105 >= v106 )
      {
        std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(&Src);
      }
      else
      {
        ++v105;
        p_Src = &Src;
        if ( v106 > 0xF )
          p_Src = (__int128 *)Src;
        *(_WORD *)((char *)p_Src + v88) = 44;
      }
    }
    std::string::append(&Src);
    v90 = (__int64 **)v87[2];
    if ( *((_BYTE *)v90 + 25) )
    {
      for ( i = (__int64 *)v87[1]; !*((_BYTE *)i + 25) && v87 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v87 = i;
      v87 = i;
    }
    else
    {
      v87 = (__int64 *)v87[2];
      for ( j = *v90; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v87 = j;
    }
  }
  v93 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
  v102 = 0;
  v103 = 0;
  std::string::_Construct<1,char const *>(&v102, "APIKey", 6u);
  Microsoft::Applications::Events::HttpHeaders::set(v93, &v102, &Src);
  std::string::_Tidy_deallocate(&v102);
  if ( *(_BYTE *)(*(_QWORD *)a2 + 120LL) )
  {
    v94 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
    v107 = 0;
    v108 = 0;
    std::string::_Construct<1,char const *>(&v107, "deflate", 7u);
    v102 = 0;
    v103 = 0;
    std::string::_Construct<1,char const *>(&v102, "Content-Encoding", 0x10u);
    Microsoft::Applications::Events::HttpHeaders::add(v94, &v102, &v107);
    std::string::_Tidy_deallocate(&v102);
    std::string::_Tidy_deallocate(&v107);
  }
  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 40LL))(
    *(_QWORD *)(*(_QWORD *)a2 + 128LL),
    *(_QWORD *)a2 + 96LL);
  v95 = *(_QWORD *)(*(_QWORD *)a2 + 96LL);
  if ( v95 != *(_QWORD *)(*(_QWORD *)a2 + 104LL) )
    *(_QWORD *)(*(_QWORD *)a2 + 104LL) = v95;
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 56LL))(
    *(_QWORD *)(*(_QWORD *)a2 + 128LL),
    *(unsigned int *)(*(_QWORD *)a2 + 28LL));
  v96 = **(void (__fastcall ***)(__int64, __int64))a1;
  v97 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a2 + 128LL) + 48LL))(*(_QWORD *)(*(_QWORD *)a2 + 128LL));
  v96(a1, v97);
  std::string::_Tidy_deallocate(&Src);
  return 1;
}

```

## disassembly

```asm
0x140142520  mov     [rsp-8+arg_10], rbx
0x140142525  push    rbp
0x140142526  push    rsi
0x140142527  push    rdi
0x140142528  push    r12
0x14014252a  push    r13
0x14014252c  push    r14
0x14014252e  push    r15
0x140142530  lea     rbp, [rsp-27h]
0x140142535  sub     rsp, 0D0h
0x14014253c  mov     rax, cs:__security_cookie
0x140142543  xor     rax, rsp
0x140142546  mov     [rbp+57h+var_38], rax
0x14014254a  mov     rsi, rdx
0x14014254d  mov     r15, rcx
0x140142550  xor     r12d, r12d
0x140142553  mov     rcx, [rcx+28h]
0x140142557  mov     rax, [rcx]
0x14014255a  mov     rax, [rax+18h]
0x14014255e  call    cs:__guard_dispatch_icall_fptr
0x140142564  mov     rcx, [rsi]
0x140142567  mov     [rcx+80h], rax
0x14014256e  mov     rax, [rsi]
0x140142571  mov     rcx, [rax+80h]
0x140142578  mov     rax, [rcx]
0x14014257b  mov     rax, [rax+8]
0x14014257f  call    cs:__guard_dispatch_icall_fptr
0x140142585  mov     rcx, [rsi]
0x140142588  add     rcx, 88h; void *
0x14014258f  mov     rdx, rax
0x140142592  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x140142597  mov     rax, [rsi]
0x14014259a  mov     rdi, [rax+80h]
0x1401425a1  mov     rax, [rdi]
0x1401425a4  mov     rbx, [rax+10h]
0x1401425a8  xorps   xmm0, xmm0
0x1401425ab  movups  [rbp+57h+var_98], xmm0
0x1401425af  xorps   xmm1, xmm1
0x1401425b2  movdqu  [rbp+57h+var_88], xmm1
0x1401425b7  lea     r8d, [r12+4]
0x1401425bc  lea     rdx, aPost; "POST"
0x1401425c3  lea     rcx, [rbp+57h+var_98]
0x1401425c7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1401425cc  nop
0x1401425cd  lea     rdx, [rbp+57h+var_98]
0x1401425d1  mov     rcx, rdi
0x1401425d4  mov     rax, rbx
0x1401425d7  call    cs:__guard_dispatch_icall_fptr
0x1401425dd  nop
0x1401425de  lea     rcx, [rbp+57h+var_98]
0x1401425e2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1401425e7  mov     rax, [rsi]
0x1401425ea  mov     rdi, [rax+80h]
0x1401425f1  mov     rax, [rdi]
0x1401425f4  mov     rbx, [rax+18h]
0x1401425f8  mov     r8, [r15+30h]
0x1401425fc  mov     rcx, [r8]
0x1401425ff  mov     rax, [rcx+10h]
0x140142603  lea     rdx, [rsp+100h+var_D8]
0x140142608  mov     rcx, r8
0x14014260b  call    cs:__guard_dispatch_icall_fptr
0x140142611  nop
0x140142612  mov     rdx, rax
0x140142615  mov     rcx, rdi
0x140142618  mov     rax, rbx
0x14014261b  call    cs:__guard_dispatch_icall_fptr
0x140142621  nop
0x140142622  lea     rcx, [rsp+100h+var_D8]
0x140142627  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14014262c  mov     rax, [rsi]
0x14014262f  mov     rcx, [rax+80h]
0x140142636  mov     rax, [rcx]
0x140142639  mov     rax, [rax+20h]
0x14014263d  call    cs:__guard_dispatch_icall_fptr
0x140142643  mov     rbx, rax
0x140142646  xorps   xmm0, xmm0
0x140142649  movups  [rbp+57h+var_58], xmm0
0x14014264d  xorps   xmm1, xmm1
0x140142650  movdqu  [rbp+57h+var_48], xmm1
0x140142655  lea     r14d, [r12+0Ch]
0x14014265a  mov     r8d, r14d
0x14014265d  lea     rdx, a100Continue; "100-continue"
0x140142664  lea     rcx, [rbp+57h+var_58]
0x140142668  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14014266d  nop
0x14014266e  xorps   xmm0, xmm0
0x140142671  movups  [rbp+57h+var_98], xmm0
0x140142675  xorps   xmm1, xmm1
0x140142678  movdqu  [rbp+57h+var_88], xmm1
0x14014267d  lea     r8d, [r12+6]
0x140142682  lea     rdx, aExpect; "Expect"
0x140142689  lea     rcx, [rbp+57h+var_98]
0x14014268d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140142692  nop
0x140142693  lea     r8, [rbp+57h+var_58]
0x140142697  lea     rdx, [rbp+57h+var_98]
0x14014269b  mov     rcx, rbx
0x14014269e  call    ?set@HttpHeaders@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; Microsoft::Applications::Events::HttpHeaders::set(std::string const &,std::string const &)
0x1401426a3  nop
0x1401426a4  lea     rcx, [rbp+57h+var_98]
0x1401426a8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1401426ad  nop
0x1401426ae  lea     rcx, [rbp+57h+var_58]
0x1401426b2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1401426b7  mov     rax, [rsi]
0x1401426ba  mov     rcx, [rax+80h]
0x1401426c1  mov     rax, [rcx]
0x1401426c4  mov     rax, [rax+20h]
0x1401426c8  call    cs:__guard_dispatch_icall_fptr
0x1401426ce  mov     rdi, rax
0x1401426d1  call    ?getSdkVersion@PlatformAbstraction@Events@Applications@Microsoft@@YAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Microsoft::Applications::Events::PlatformAbstraction::getSdkVersion(void)
0x1401426d6  mov     rbx, rax
0x1401426d9  xorps   xmm0, xmm0
0x1401426dc  movups  [rbp+57h+var_98], xmm0
0x1401426e0  xorps   xmm1, xmm1
0x1401426e3  movdqu  [rbp+57h+var_88], xmm1
0x1401426e8  lea     r8d, [r12+0Bh]
0x1401426ed  lea     rdx, aSdkVersion; "SDK-Version"
0x1401426f4  lea     rcx, [rbp+57h+var_98]
0x1401426f8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1401426fd  nop
0x1401426fe  mov     r8, rbx
0x140142701  lea     rdx, [rbp+57h+var_98]
0x140142705  mov     rcx, rdi
0x140142708  call    ?set@HttpHeaders@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; Microsoft::Applications::Events::HttpHeaders::set(std::string const &,std::string const &)
0x14014270d  nop
0x14014270e  lea     rcx, [rbp+57h+var_98]
0x140142712  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140142717  mov     rax, [rsi]
0x14014271a  mov     rcx, [rax+80h]
0x140142721  mov     rax, [rcx]
0x140142724  mov     rax, [rax+20h]
0x140142728  call    cs:__guard_dispatch_icall_fptr
0x14014272e  mov     rbx, rax
0x140142731  xorps   xmm0, xmm0
0x140142734  movups  [rbp+57h+var_58], xmm0
0x140142738  xorps   xmm1, xmm1
0x14014273b  movdqu  [rbp+57h+var_48], xmm1
0x140142740  lea     r13d, [r12+7]
0x140142745  mov     r8d, r13d
0x140142748  lea     rdx, aNoAuth; "NO_AUTH"
0x14014274f  lea     rcx, [rbp+57h+var_58]
0x140142753  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140142758  nop
0x140142759  xorps   xmm0, xmm0
0x14014275c  movups  [rbp+57h+var_98], xmm0
0x140142760  xorps   xmm1, xmm1
0x140142763  movdqu  [rbp+57h+var_88], xmm1
0x140142768  lea     r8d, [r12+9]
0x14014276d  lea     rdx, aClientId; "Client-Id"
0x140142774  lea     rcx, [rbp+57h+var_98]
0x140142778  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14014277d  nop
0x14014277e  lea     r8, [rbp+57h+var_58]
0x140142782  lea     rdx, [rbp+57h+var_98]
0x140142786  mov     rcx, rbx
0x140142789  call    ?set@HttpHeaders@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; Microsoft::Applications::Events::HttpHeaders::set(std::string const &,std::string const &)
0x14014278e  nop
0x14014278f  lea     rcx, [rbp+57h+var_98]
0x140142793  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140142798  nop
0x140142799  lea     rcx, [rbp+57h+var_58]
0x14014279d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1401427a2  mov     rax, [rsi]
0x1401427a5  mov     rcx, [rax+80h]
0x1401427ac  mov     rax, [rcx]
0x1401427af  mov     rax, [rax+20h]
0x1401427b3  call    cs:__guard_dispatch_icall_fptr
0x1401427b9  mov     rbx, rax
0x1401427bc  xorps   xmm0, xmm0
0x1401427bf  movups  [rbp+57h+var_58], xmm0
0x1401427c3  xorps   xmm1, xmm1
0x1401427c6  movdqu  [rbp+57h+var_48], xmm1
0x1401427cb  lea     r8d, [r12+1Fh]
0x1401427d0  lea     rdx, aApplicationBon; "application/bond-compact-binary"
0x1401427d7  lea     rcx, [rbp+57h+var_58]
0x1401427db  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1401427e0  nop
0x1401427e1  xorps   xmm0, xmm0
0x1401427e4  movups  [rbp+57h+var_98], xmm0
0x1401427e8  xorps   xmm1, xmm1
0x1401427eb  movdqu  [rbp+57h+var_88], xmm1
0x1401427f0  mov     r8d, r14d
0x1401427f3  lea     rdx, aContentType; "Content-Type"
0x1401427fa  lea     rcx, [rbp+57h+var_98]
0x1401427fe  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140142803  nop
0x140142804  lea     r8, [rbp+57h+var_58]
0x140142808  lea     rdx, [rbp+57h+var_98]
0x14014280c  mov     rcx, rbx
0x14014280f  call    ?set@HttpHeaders@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; Microsoft::Applications::Events::HttpHeaders::set(std::string const &,std::string const &)
0x140142814  nop
0x140142815  lea     rcx, [rbp+57h+var_98]
0x140142819  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14014281e  nop
0x14014281f  lea     rcx, [rbp+57h+var_58]
0x140142823  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140142828  mov     rax, [rsi]
0x14014282b  mov     rcx, [rax+80h]
0x140142832  mov     rax, [rcx]
0x140142835  mov     rax, [rax+20h]
0x140142839  call    cs:__guard_dispatch_icall_fptr
0x14014283f  mov     rbx, rax
0x140142842  call    ?GetPAL@PlatformAbstraction@Events@Applications@Microsoft@@YAAEAVPlatformAbstractionLayer@1234@XZ; Microsoft::Applications::Events::PlatformAbstraction::GetPAL(void)
0x140142847  call    ?getUtcSystemTimeMs@PlatformAbstractionLayer@PlatformAbstraction@Events@Applications@Microsoft@@QEBA_JXZ; Microsoft::Applications::Events::PlatformAbstraction::PlatformAbstractionLayer::getUtcSystemTimeMs(void)
0x14014284c  mov     rdx, rax
0x14014284f  lea     rcx, [rbp+57h+var_58]
0x140142853  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_J@Z; std::to_string(__int64)
0x140142858  nop
0x140142859  xorps   xmm0, xmm0
0x14014285c  movups  [rbp+57h+var_98], xmm0
0x140142860  xorps   xmm1, xmm1
0x140142863  movdqu  [rbp+57h+var_88], xmm1
0x140142868  lea     r8d, [r12+0Bh]
0x14014286d  lea     rdx, aUploadTime; "Upload-Time"
0x140142874  lea     rcx, [rbp+57h+var_98]
0x140142878  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14014287d  nop
0x14014287e  lea     r8, [rbp+57h+var_58]
0x140142882  lea     rdx, [rbp+57h+var_98]
0x140142886  mov     rcx, rbx
0x140142889  call    ?set@HttpHeaders@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; Microsoft::Applications::Events::HttpHeaders::set(std::string const &,std::string const &)
0x14014288e  nop
0x14014288f  lea     rcx, [rbp+57h+var_98]
0x140142893  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140142898  nop
0x140142899  lea     rcx, [rbp+57h+var_58]
0x14014289d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1401428a2  mov     rcx, [r15+20h]
0x1401428a6  mov     rax, [rcx]
0x1401428a9  mov     rax, [rax+40h]
0x1401428ad  call    cs:__guard_dispatch_icall_fptr
0x1401428b3  lea     rcx, [rax+8]
0x1401428b7  mov     rax, [rcx]
0x1401428ba  mov     rax, [rax+8]
0x1401428be  call    cs:__guard_dispatch_icall_fptr
0x1401428c4  test    rax, rax
0x1401428c7  jz      loc_140142CA4
0x1401428cd  mov     rcx, [r15+20h]
0x1401428d1  mov     rax, [rcx]
0x1401428d4  mov     rax, [rax+40h]
0x1401428d8  call    cs:__guard_dispatch_icall_fptr
0x1401428de  lea     rcx, [rax+8]
0x1401428e2  mov     rax, [rcx]
0x1401428e5  mov     rax, [rax+8]
0x1401428e9  call    cs:__guard_dispatch_icall_fptr
0x1401428ef  mov     rdx, rax
0x1401428f2  mov     rcx, [rax]
0x1401428f5  mov     rax, [rcx+30h]
0x1401428f9  mov     rcx, rdx
0x1401428fc  call    cs:__guard_dispatch_icall_fptr
0x140142902  cmp     [rax+8], r12
0x140142906  jbe     loc_140142CA4
0x14014290c  mov     rcx, [r15+20h]
0x140142910  mov     rax, [rcx]
0x140142913  mov     rax, [rax+40h]
0x140142917  call    cs:__guard_dispatch_icall_fptr
0x14014291d  lea     rcx, [rax+8]
0x140142921  mov     rax, [rcx]
0x140142924  mov     rax, [rax+8]
0x140142928  call    cs:__guard_dispatch_icall_fptr
0x14014292e  mov     rdx, rax
0x140142931  mov     rcx, [rax]
0x140142934  mov     rax, [rcx+30h]
0x140142938  mov     rcx, rdx
0x14014293b  call    cs:__guard_dispatch_icall_fptr
0x140142941  mov     r14, rax
0x140142944  mov     rax, [rax]
0x140142947  mov     r9, [rax+8]
0x14014294b  xor     ecx, ecx
0x14014294d  mov     dword ptr [rbp+57h+var_58+0Ch], ecx
0x140142950  mov     r8, rax
0x140142953  jmp     short loc_14014296F
0x140142955  mov     edx, [r9+20h]
0x140142959  test    edx, edx
0x14014295b  cmovns  r8, r9
0x14014295f  shr     edx, 1Fh
0x140142962  lea     rcx, [r9+10h]
0x140142966  test    dl, dl
0x140142968  cmovz   rcx, r9
0x14014296c  mov     r9, [rcx]
0x14014296f  cmp     [r9+19h], r12b
0x140142973  jz      short loc_140142955
0x140142975  cmp     [r8+19h], r12b
0x140142979  jnz     short loc_1401429F4
0x14014297b  cmp     [r8+20h], r12d
0x14014297f  jg      short loc_1401429F4
0x140142981  cmp     rax, r8
0x140142984  jz      short loc_1401429F4
0x140142986  mov     rax, [rsi]
0x140142989  mov     rcx, [rax+80h]
0x140142990  mov     rax, [rcx]
0x140142993  mov     rax, [rax+20h]
0x140142997  call    cs:__guard_dispatch_icall_fptr
0x14014299d  mov     rdi, rax
0x1401429a0  mov     [rsp+100h+var_E0], r12d
0x1401429a5  lea     rdx, [rsp+100h+var_E0]
0x1401429aa  mov     rcx, r14
0x1401429ad  call    ??A?$map@W4TicketType@Events@Applications@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@W4TicketType@Events@Applications@Microsoft@@@6@V?$allocator@U?$pair@$$CBW4TicketType@Events@Applications@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@6@@std@@QEAAAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@$$QEAW4TicketType@Events@Applications@Microsoft@@@Z; std::map<Microsoft::Applications::Events::TicketType,std::string>::operator[](Microsoft::Applications::Events::TicketType &&)
0x1401429b2  mov     rbx, rax
  ... truncated ...
```
