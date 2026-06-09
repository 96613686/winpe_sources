# Pal::IOImplWindows::createFolderWithSubFolders(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180016538`
- end: `0x180016794`
- name: `?createFolderWithSubFolders@IOImplWindows@Pal@@AEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `604`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800164e0`

## callees

- `0x1800094a0`
- `0x18000b938`
- `0x18000c2f8`
- `0x18000c354`
- `0x18000cb0c`
- `0x18000ddd0`
- `0x18000ef50`
- `0x180010354`
- `0x180011628`
- `0x180016538`
- `0x18001a860`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001657b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800166f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001657b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800166f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016729`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001656d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800165ee`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800166e8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001671f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001656d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800165ee`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800166e8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001671f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Pal::IOImplWindows::createFolderWithSubFolders(__int64 a1, __int64 a2)
{
  const WCHAR *v3; // rax
  DWORD LastError; // eax
  bool v5; // bl
  __int64 v7; // rax
  __int64 v8; // rbx
  const WCHAR *v9; // rax
  DWORD v10; // eax
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rbx
  char v14; // di
  const WCHAR *v15; // rax
  const WCHAR *v16; // rax
  _BYTE v17[8]; // [rsp+20h] [rbp-58h] BYREF
  __int128 v18; // [rsp+28h] [rbp-50h] BYREF
  __int64 v19; // [rsp+38h] [rbp-40h]
  int v20; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v21[32]; // [rsp+48h] [rbp-30h] BYREF

  CallingStateTracker::CallingStateTracker(v17);
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  if ( CreateDirectoryW(v3, 0) )
  {
    CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v17);
    return 1;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 3 )
    {
      std::vector<std::map<enum MapControl::ConfigurationKeys,std::wstring>>::vector<std::map<enum MapControl::ConfigurationKeys,std::wstring>>(&v18);
      v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      v8 = std::_Traits_rfind_ch<std::char_traits<unsigned short>>(v7, *(_QWORD *)(a2 + 16), -1);
      while ( v8 != -1 )
      {
        std::wstring::substr(a2, v21, 0, v8);
        v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
        if ( CreateDirectoryW(v9, 0) || (v10 = GetLastError(), v10 == 183) )
        {
          std::wstring::_Tidy_deallocate(v21);
          break;
        }
        if ( v10 != 3 )
        {
LABEL_13:
          std::wstring::_Tidy_deallocate(v21);
          if ( (_QWORD)v18 )
          {
            std::_Deallocate<16>((void *)v18, (v19 - v18) & 0xFFFFFFFFFFFFFFFCuLL);
            v18 = 0;
            v19 = 0;
          }
          CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v17);
          return 0;
        }
        v20 = v8;
        if ( *((_QWORD *)&v18 + 1) == v19 )
        {
          std::vector<int>::_Emplace_reallocate<int>(&v18, *((_QWORD *)&v18 + 1), &v20);
        }
        else
        {
          **((_DWORD **)&v18 + 1) = v8;
          *((_QWORD *)&v18 + 1) += 4LL;
        }
        v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
        v8 = std::_Traits_rfind_ch<std::char_traits<unsigned short>>(v11, *(_QWORD *)(a2 + 16), v8 - 1);
        std::wstring::_Tidy_deallocate(v21);
      }
      v12 = v18;
      v13 = (__int64)(*((_QWORD *)&v18 + 1) - v18) >> 2;
      v14 = 1;
      while ( 1 )
      {
        LODWORD(v13) = v13 - 1;
        if ( (int)v13 < 0 )
          break;
        std::wstring::substr(a2, v21, 0, *(int *)(v12 + 4LL * (int)v13));
        v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
        if ( !CreateDirectoryW(v15, 0) && GetLastError() != 183 )
          goto LABEL_13;
        std::wstring::_Tidy_deallocate(v21);
        v12 = v18;
      }
      v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      if ( !CreateDirectoryW(v16, 0) && GetLastError() != 183 )
        v14 = 0;
      if ( (_QWORD)v18 )
      {
        std::_Deallocate<16>((void *)v18, (v19 - v18) & 0xFFFFFFFFFFFFFFFCuLL);
        v18 = 0;
        v19 = 0;
      }
      CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v17);
      return v14;
    }
    else
    {
      v5 = LastError == 183;
      CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v17);
      return v5;
    }
  }
}

```

## disassembly

```asm
0x180016538  push    rbp
0x18001653a  push    rbx
0x18001653b  push    rdi
0x18001653c  push    r14
0x18001653e  mov     rbp, rsp
0x180016541  sub     rsp, 78h
0x180016545  mov     rax, cs:__security_cookie
0x18001654c  xor     rax, rsp
0x18001654f  mov     [rbp+var_10], rax
0x180016553  mov     r14, rdx
0x180016556  lea     rcx, [rbp+var_58]
0x18001655a  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x18001655f  nop
0x180016560  mov     rcx, r14
0x180016563  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016568  xor     edx, edx; lpSecurityAttributes
0x18001656a  mov     rcx, rax; lpPathName
0x18001656d  call    cs:__imp_CreateDirectoryW
0x180016573  test    eax, eax
0x180016575  jnz     loc_180016770
0x18001657b  call    cs:__imp_GetLastError
0x180016581  cmp     eax, 3
0x180016584  jz      short loc_18001659E
0x180016586  cmp     eax, 0B7h
0x18001658b  setz    bl
0x18001658e  lea     rcx, [rbp+var_58]; this
0x180016592  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x180016597  mov     al, bl
0x180016599  jmp     loc_18001677E
0x18001659e  lea     rcx, [rbp+var_50]
0x1800165a2  call    ??0?$vector@V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@V?$allocator@V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@@2@@std@@QEAA@XZ; std::vector<std::map<MapControl::ConfigurationKeys,std::wstring>>::vector<std::map<MapControl::ConfigurationKeys,std::wstring>>(void)
0x1800165a7  nop
0x1800165a8  mov     rcx, r14
0x1800165ab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800165b0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800165b4  mov     rdx, [r14+10h]
0x1800165b8  mov     rcx, rax
0x1800165bb  call    ??$_Traits_rfind_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_rfind_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1800165c0  mov     rbx, rax
0x1800165c3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800165c7  jz      loc_1800166AA
0x1800165cd  mov     r9, rbx
0x1800165d0  xor     r8d, r8d
0x1800165d3  lea     rdx, [rbp+var_30]
0x1800165d7  mov     rcx, r14
0x1800165da  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800165df  nop
0x1800165e0  lea     rcx, [rbp+var_30]
0x1800165e4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800165e9  mov     rcx, rax; lpPathName
0x1800165ec  xor     edx, edx; lpSecurityAttributes
0x1800165ee  call    cs:__imp_CreateDirectoryW
0x1800165f4  test    eax, eax
0x1800165f6  jnz     loc_1800166A1
0x1800165fc  call    cs:__imp_GetLastError
0x180016602  cmp     eax, 0B7h
0x180016607  jz      loc_1800166A1
0x18001660d  cmp     eax, 3
0x180016610  jnz     short loc_18001665E
0x180016612  mov     [rbp+var_38], ebx
0x180016615  mov     rdx, qword ptr [rbp+var_50+8]
0x180016619  cmp     rdx, [rbp+var_40]
0x18001661d  jz      short loc_180016628
0x18001661f  mov     [rdx], ebx
0x180016621  add     qword ptr [rbp+var_50+8], 4
0x180016626  jmp     short loc_180016635
0x180016628  lea     r8, [rbp+var_38]
0x18001662c  lea     rcx, [rbp+var_50]
0x180016630  call    ??$_Emplace_reallocate@H@?$vector@HV?$allocator@H@std@@@std@@AEAAPEAHQEAH$$QEAH@Z; std::vector<int>::_Emplace_reallocate<int>(int * const,int &&)
0x180016635  mov     rcx, r14
0x180016638  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001663d  lea     r8, [rbx-1]
0x180016641  mov     rdx, [r14+10h]
0x180016645  mov     rcx, rax
0x180016648  call    ??$_Traits_rfind_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_rfind_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18001664d  mov     rbx, rax
0x180016650  lea     rcx, [rbp+var_30]
0x180016654  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016659  jmp     loc_1800165C3
0x18001665e  lea     rcx, [rbp+var_30]
0x180016662  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016667  nop
0x180016668  mov     rcx, qword ptr [rbp+var_50]
0x18001666c  test    rcx, rcx
0x18001666f  jz      short loc_180016691
0x180016671  mov     rdx, [rbp+var_40]
0x180016675  sub     rdx, rcx
0x180016678  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18001667c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180016681  xorps   xmm0, xmm0
0x180016684  movdqu  [rbp+var_50], xmm0
0x180016689  mov     [rbp+var_40], 0
0x180016691  lea     rcx, [rbp+var_58]; this
0x180016695  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x18001669a  xor     al, al
0x18001669c  jmp     loc_18001677E
0x1800166a1  lea     rcx, [rbp+var_30]
0x1800166a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800166aa  mov     rbx, qword ptr [rbp+var_50+8]
0x1800166ae  mov     rcx, qword ptr [rbp+var_50]
0x1800166b2  sub     rbx, rcx
0x1800166b5  sar     rbx, 2
0x1800166b9  mov     edi, 1
0x1800166be  sub     ebx, edi
0x1800166c0  test    ebx, ebx
0x1800166c2  js      short loc_180016712
0x1800166c4  movsxd  rax, ebx
0x1800166c7  movsxd  r9, dword ptr [rcx+rax*4]
0x1800166cb  xor     r8d, r8d
0x1800166ce  lea     rdx, [rbp+var_30]
0x1800166d2  mov     rcx, r14
0x1800166d5  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800166da  lea     rcx, [rbp+var_30]
0x1800166de  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800166e3  mov     rcx, rax; lpPathName
0x1800166e6  xor     edx, edx; lpSecurityAttributes
0x1800166e8  call    cs:__imp_CreateDirectoryW
0x1800166ee  test    eax, eax
0x1800166f0  jnz     short loc_180016703
0x1800166f2  call    cs:__imp_GetLastError
0x1800166f8  cmp     eax, 0B7h
0x1800166fd  jnz     loc_18001665E
0x180016703  lea     rcx, [rbp+var_30]
0x180016707  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001670c  mov     rcx, qword ptr [rbp+var_50]
0x180016710  jmp     short loc_1800166BE
0x180016712  mov     rcx, r14
0x180016715  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001671a  xor     edx, edx; lpSecurityAttributes
0x18001671c  mov     rcx, rax; lpPathName
0x18001671f  call    cs:__imp_CreateDirectoryW
0x180016725  test    eax, eax
0x180016727  jnz     short loc_180016739
0x180016729  call    cs:__imp_GetLastError
0x18001672f  cmp     eax, 0B7h
0x180016734  jz      short loc_180016739
0x180016736  xor     dil, dil
0x180016739  mov     rcx, qword ptr [rbp+var_50]
0x18001673d  test    rcx, rcx
0x180016740  jz      short loc_180016762
0x180016742  mov     rdx, [rbp+var_40]
0x180016746  sub     rdx, rcx
0x180016749  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18001674d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180016752  xorps   xmm0, xmm0
0x180016755  movdqu  [rbp+var_50], xmm0
0x18001675a  mov     [rbp+var_40], 0
0x180016762  lea     rcx, [rbp+var_58]; this
0x180016766  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x18001676b  mov     al, dil
0x18001676e  jmp     short loc_18001677E
0x180016770  lea     rcx, [rbp+var_58]; this
0x180016774  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x180016779  mov     eax, 1
0x18001677e  mov     rcx, [rbp+var_10]
0x180016782  xor     rcx, rsp; StackCookie
0x180016785  call    __security_check_cookie
0x18001678a  add     rsp, 78h
0x18001678e  pop     r14
0x180016790  pop     rdi
0x180016791  pop     rbx
0x180016792  pop     rbp
0x180016793  retn
```
