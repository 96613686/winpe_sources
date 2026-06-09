# OrphanFileFinder::GetListOfDirectoriesToSearch(void)

- ea: `0x180038dec`
- end: `0x180039108`
- name: `?GetListOfDirectoriesToSearch@OrphanFileFinder@@KA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `796`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800388dc`

## callees

- `0x180018a60`
- `0x18001e0d0`
- `0x180038dec`
- `0x18003e070`
- `0x1800404c4`
- `0x180044c88`
- `0x18004f380`
- `0x180050128`
- `0x180052f28`
- `0x180053020`
- `0x180059920`
- `0x180105ae4`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x180038e72`
- `KERNEL32!GetSystemInfo` at `0x180038e72`
- `SHELL32!SHGetKnownFolderPath` at `0x180038edd`
- `SHELL32!SHGetKnownFolderPath` at `0x180038edd`

## string_xrefs

- `0x180039064`: `\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch\User Pinned\TaskBar`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall OrphanFileFinder::GetListOfDirectoriesToSearch(_QWORD *a1)
{
  bool v2; // si
  const KNOWNFOLDERID *const *v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int128 *UserProfilePaths; // rax
  __int128 i; // rdi
  PWSTR ppszPath; // [rsp+28h] [rbp-E0h] BYREF
  int v10; // [rsp+30h] [rbp-D8h]
  __int128 v11; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-C0h]
  _QWORD v13[4]; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v14[2]; // [rsp+70h] [rbp-98h] BYREF
  struct _SYSTEM_INFO SystemInfo_8; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v16[32]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v17[32]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE Src[32]; // [rsp+F0h] [rbp-18h] BYREF

  v14[0] = -2;
  v14[1] = a1;
  v13[0] = &FOLDERID_CommonStartMenu;
  v13[1] = &FOLDERID_PublicDesktop;
  v13[2] = &FOLDERID_ProgramFiles;
  v13[3] = &FOLDERID_ProgramFilesX86;
  memset(&SystemInfo_8, 0, sizeof(SystemInfo_8));
  GetSystemInfo(&SystemInfo_8);
  v2 = SystemInfo_8.wProcessorArchitecture == 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v10 = 1;
  v3 = (const KNOWNFOLDERID *const *)v13;
  v4 = *(_QWORD *)FOLDERID_ProgramFilesX86.Data4;
  v5 = *(_QWORD *)&FOLDERID_ProgramFilesX86.Data1;
  do
  {
    if ( !v2 || **(_QWORD **)v3 != v5 || *(_QWORD *)(*v3)->Data4 != v4 )
    {
      ppszPath = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &ppszPath,
        0);
      if ( !SHGetKnownFolderPath(*v3, 0, 0, &ppszPath) )
      {
        std::wstring::wstring(&SystemInfo_8, ppszPath);
        if ( a1[1] == a1[2] )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, a1[1], &SystemInfo_8);
        }
        else
        {
          std::wstring::wstring(a1[1], &SystemInfo_8);
          a1[1] += 32LL;
        }
        std::wstring::~wstring(&SystemInfo_8);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
      v4 = *(_QWORD *)FOLDERID_ProgramFilesX86.Data4;
      v5 = *(_QWORD *)&FOLDERID_ProgramFilesX86.Data1;
    }
    ++v3;
  }
  while ( v3 != v14 );
  v11 = 0;
  v12 = 0;
  UserProfilePaths = (__int128 *)Utility::GetUserProfilePaths(v4, v5);
  if ( &v11 != UserProfilePaths )
    std::vector<std::wstring>::_Assign_counted_range<std::wstring *>(
      &v11,
      *(_QWORD *)UserProfilePaths,
      (__int64)(*((_QWORD *)UserProfilePaths + 1) - *(_QWORD *)UserProfilePaths) >> 5);
  for ( i = v11; (_QWORD)i != *((_QWORD *)&i + 1); *(_QWORD *)&i = i + 32 )
  {
    std::wstring::wstring(&SystemInfo_8, i);
    std::wstring::wstring(Src, &SystemInfo_8);
    std::wstring::_Append<unsigned short>(Src);
    if ( a1[1] == a1[2] )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, a1[1], Src);
    }
    else
    {
      std::wstring::wstring(a1[1], Src);
      a1[1] += 32LL;
    }
    std::wstring::wstring(v17, &SystemInfo_8);
    std::wstring::_Append<unsigned short>(v17);
    if ( a1[1] == a1[2] )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, a1[1], v17);
    }
    else
    {
      std::wstring::wstring(a1[1], v17);
      a1[1] += 32LL;
    }
    std::wstring::wstring(v16, &SystemInfo_8);
    std::wstring::_Append<unsigned short>(v16);
    if ( a1[1] == a1[2] )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, a1[1], v16);
    }
    else
    {
      std::wstring::wstring(a1[1], v16);
      a1[1] += 32LL;
    }
    std::wstring::~wstring(v16);
    std::wstring::~wstring(v17);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(&SystemInfo_8);
  }
  std::vector<std::wstring>::_Tidy(&v11);
  return a1;
}

```

## disassembly

```asm
0x180038dec  mov     rax, rsp
0x180038def  push    rbp
0x180038df0  push    rdi
0x180038df1  push    r14
0x180038df3  lea     rbp, [rax-28h]
0x180038df7  sub     rsp, 110h
0x180038dfe  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180038e07  mov     [rax+10h], rbx
0x180038e0b  mov     [rax+18h], rsi
0x180038e0f  mov     rax, cs:__security_cookie
0x180038e16  xor     rax, rsp
0x180038e19  mov     [rbp+20h+var_18], rax
0x180038e1d  mov     rbx, rcx
0x180038e20  mov     qword ptr [rsp+120h+SystemInfo], rcx
0x180038e25  xor     r14d, r14d
0x180038e28  mov     dword ptr [rsp+120h+var_F8], r14d
0x180038e2d  lea     rax, FOLDERID_CommonStartMenu
0x180038e34  mov     [rsp+120h+var_D8], rax
0x180038e39  lea     rax, FOLDERID_PublicDesktop
0x180038e40  mov     [rsp+120h+var_D0], rax
0x180038e45  lea     rax, FOLDERID_ProgramFiles
0x180038e4c  mov     [rsp+120h+var_C8], rax
0x180038e51  lea     rax, FOLDERID_ProgramFilesX86
0x180038e58  mov     [rsp+120h+var_C0], rax
0x180038e5d  xorps   xmm0, xmm0
0x180038e60  movups  xmmword ptr [rsp+120h+SystemInfo+8], xmm0
0x180038e65  movups  xmmword ptr [rbp+20h+SystemInfo+18h], xmm0
0x180038e69  movups  xmmword ptr [rbp+20h+SystemInfo+28h], xmm0
0x180038e6d  lea     rcx, [rsp+120h+SystemInfo+8]; lpSystemInfo
0x180038e72  call    cs:__imp_GetSystemInfo
0x180038e78  cmp     word ptr [rsp+120h+SystemInfo+8], r14w
0x180038e7e  setz    sil
0x180038e82  mov     [rbx], r14
0x180038e85  mov     [rbx+8], r14
0x180038e89  mov     [rbx+10h], r14
0x180038e8d  mov     dword ptr [rsp+120h+var_F8], 1
0x180038e95  lea     rdi, [rsp+120h+var_D8]
0x180038e9a  mov     rcx, qword ptr cs:FOLDERID_ProgramFilesX86.Data4
0x180038ea1  mov     rdx, qword ptr cs:FOLDERID_ProgramFilesX86.Data1
0x180038ea8  test    sil, sil
0x180038eab  jz      short loc_180038EBF
0x180038ead  mov     rax, [rdi]
0x180038eb0  cmp     [rax], rdx
0x180038eb3  jnz     short loc_180038EBF
0x180038eb5  cmp     [rax+8], rcx
0x180038eb9  jz      loc_180038F49
0x180038ebf  mov     [rsp+120h+ppszPath], r14
0x180038ec4  xor     edx, edx
0x180038ec6  lea     rcx, [rsp+120h+ppszPath]
0x180038ecb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180038ed0  lea     r9, [rsp+120h+ppszPath]; ppszPath
0x180038ed5  xor     r8d, r8d; hToken
0x180038ed8  xor     edx, edx; dwFlags
0x180038eda  mov     rcx, [rdi]; rfid
0x180038edd  call    cs:__imp_SHGetKnownFolderPath
0x180038ee3  test    eax, eax
0x180038ee5  jnz     short loc_180038F31
0x180038ee7  mov     rdx, [rsp+120h+ppszPath]
0x180038eec  lea     rcx, [rsp+120h+SystemInfo+8]
0x180038ef1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180038ef6  nop
0x180038ef7  mov     rax, [rbx+8]
0x180038efb  cmp     rax, [rbx+10h]
0x180038eff  jz      short loc_180038F15
0x180038f01  lea     rdx, [rsp+120h+SystemInfo+8]
0x180038f06  mov     rcx, rax
0x180038f09  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180038f0e  add     qword ptr [rbx+8], 20h ; ' '
0x180038f13  jmp     short loc_180038F26
0x180038f15  lea     r8, [rsp+120h+SystemInfo+8]
0x180038f1a  mov     rdx, rax
0x180038f1d  mov     rcx, rbx
0x180038f20  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180038f25  nop
0x180038f26  lea     rcx, [rsp+120h+SystemInfo+8]
0x180038f2b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038f30  nop
0x180038f31  lea     rcx, [rsp+120h+ppszPath]
0x180038f36  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180038f3b  mov     rcx, qword ptr cs:FOLDERID_ProgramFilesX86.Data4
0x180038f42  mov     rdx, qword ptr cs:FOLDERID_ProgramFilesX86.Data1
0x180038f49  add     rdi, 8
0x180038f4d  lea     rax, [rsp+120h+var_B8]
0x180038f52  cmp     rdi, rax
0x180038f55  jnz     loc_180038EA8
0x180038f5b  xorps   xmm0, xmm0
0x180038f5e  movdqu  [rsp+120h+var_F8+8], xmm0
0x180038f64  mov     [rsp+120h+var_E0], r14
0x180038f69  call    ?GetUserProfilePaths@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; Utility::GetUserProfilePaths(void)
0x180038f6e  lea     rcx, [rsp+120h+var_F8+8]
0x180038f73  cmp     rcx, rax
0x180038f76  jz      short loc_180038F90
0x180038f78  mov     r8, [rax+8]
0x180038f7c  sub     r8, [rax]
0x180038f7f  sar     r8, 5
0x180038f83  mov     rdx, [rax]
0x180038f86  lea     rcx, [rsp+120h+var_F8+8]
0x180038f8b  call    ??$_Assign_counted_range@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::vector<std::wstring>::_Assign_counted_range<std::wstring *>(std::wstring *,unsigned __int64)
0x180038f90  mov     rdi, qword ptr [rsp+120h+var_F8+8]
0x180038f95  mov     rsi, [rsp+120h+var_E8]
0x180038f9a  jmp     loc_1800390CD
0x180038f9f  mov     rdx, rdi
0x180038fa2  lea     rcx, [rsp+120h+SystemInfo+8]
0x180038fa7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180038fac  nop
0x180038fad  lea     rdx, [rsp+120h+SystemInfo+8]
0x180038fb2  lea     rcx, [rbp+20h+Src]
0x180038fb6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180038fbb  nop
0x180038fbc  mov     r8d, 8
0x180038fc2  lea     rdx, aDesktop; "\\Desktop"
0x180038fc9  lea     rcx, [rbp+20h+Src]; Src
0x180038fcd  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180038fd2  mov     rax, [rbx+8]
0x180038fd6  cmp     rax, [rbx+10h]
0x180038fda  jz      short loc_180038FEF
0x180038fdc  lea     rdx, [rbp+20h+Src]
0x180038fe0  mov     rcx, rax
0x180038fe3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180038fe8  add     qword ptr [rbx+8], 20h ; ' '
0x180038fed  jmp     short loc_180038FFE
0x180038fef  lea     r8, [rbp+20h+Src]
0x180038ff3  mov     rdx, rax
0x180038ff6  mov     rcx, rbx
0x180038ff9  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180038ffe  lea     rdx, [rsp+120h+SystemInfo+8]
0x180039003  lea     rcx, [rbp+20h+var_58]
0x180039007  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003900c  nop
0x18003900d  mov     r8d, 2Dh ; '-'
0x180039013  lea     rdx, aAppdataRoaming; "\\AppData\\Roaming\\Microsoft\\Windows"...
0x18003901a  lea     rcx, [rbp+20h+var_58]; Src
0x18003901e  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180039023  mov     rax, [rbx+8]
0x180039027  cmp     rax, [rbx+10h]
0x18003902b  jz      short loc_180039040
0x18003902d  lea     rdx, [rbp+20h+var_58]
0x180039031  mov     rcx, rax
0x180039034  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180039039  add     qword ptr [rbx+8], 20h ; ' '
0x18003903e  jmp     short loc_18003904F
0x180039040  lea     r8, [rbp+20h+var_58]
0x180039044  mov     rdx, rax
0x180039047  mov     rcx, rbx
0x18003904a  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18003904f  lea     rdx, [rsp+120h+SystemInfo+8]
0x180039054  lea     rcx, [rbp+20h+var_78]
0x180039058  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003905d  nop
0x18003905e  mov     r8d, 4Dh ; 'M'
0x180039064  lea     rdx, aAppdataRoaming_0; "\\AppData\\Roaming\\Microsoft\\Internet"...
0x18003906b  lea     rcx, [rbp+20h+var_78]; Src
0x18003906f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180039074  mov     rax, [rbx+8]
0x180039078  cmp     rax, [rbx+10h]
0x18003907c  jz      short loc_180039091
0x18003907e  lea     rdx, [rbp+20h+var_78]
0x180039082  mov     rcx, rax
0x180039085  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003908a  add     qword ptr [rbx+8], 20h ; ' '
0x18003908f  jmp     short loc_1800390A1
0x180039091  lea     r8, [rbp+20h+var_78]
0x180039095  mov     rdx, rax
0x180039098  mov     rcx, rbx
0x18003909b  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x1800390a0  nop
0x1800390a1  lea     rcx, [rbp+20h+var_78]
0x1800390a5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800390aa  nop
0x1800390ab  lea     rcx, [rbp+20h+var_58]
0x1800390af  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800390b4  nop
0x1800390b5  lea     rcx, [rbp+20h+Src]
0x1800390b9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800390be  nop
0x1800390bf  lea     rcx, [rsp+120h+SystemInfo+8]
0x1800390c4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800390c9  add     rdi, 20h ; ' '
0x1800390cd  cmp     rdi, rsi
0x1800390d0  jnz     loc_180038F9F
0x1800390d6  lea     rcx, [rsp+120h+var_F8+8]
0x1800390db  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800390e0  mov     rax, rbx
0x1800390e3  mov     rcx, [rbp+20h+var_18]
0x1800390e7  xor     rcx, rsp; StackCookie
0x1800390ea  call    __security_check_cookie
0x1800390ef  lea     r11, [rsp+120h+var_10]
0x1800390f7  mov     rbx, [r11+28h]
0x1800390fb  mov     rsi, [r11+30h]
0x1800390ff  mov     rsp, r11
0x180039102  pop     r14
0x180039104  pop     rdi
0x180039105  pop     rbp
0x180039106  retn
```
