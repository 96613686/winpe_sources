# ModelUpdate::UnpackAndCompressModel(std::filesystem::path const &)

- ea: `0x140344d44`
- end: `0x140345232`
- name: `?UnpackAndCompressModel@ModelUpdate@@AEAAXAEBVpath@filesystem@std@@@Z`
- size: `1262`
- prototype: `void(ModelUpdate *__hidden this, const struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140345384`

## callees

- `0x14003c578`
- `0x140040184`
- `0x1400413a8`
- `0x1400430dc`
- `0x140043354`
- `0x1400447ac`
- `0x140045404`
- `0x140057a20`
- `0x1400c75e4`
- `0x1400d697c`
- `0x140118960`
- `0x140118b80`
- `0x14012d7d8`
- `0x140150f10`
- `0x14018c370`
- `0x140344d44`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1403450c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1403450c5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14034506e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14034506e`
- `WOFUTIL!WofSetFileDataLocation` at `0x14034509f`
- `WOFUTIL!WofSetFileDataLocation` at `0x14034509f`
- `SETUPAPI!SetupIterateCabinetW` at `0x140344da3`
- `SETUPAPI!SetupIterateCabinetW` at `0x140344da3`

## string_xrefs

- `0x1403451f5`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1403451e4`: `directory_iterator::operator++`
- `0x14034521f`: `directory_iterator::directory_iterator`
- `0x1403451d0`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\ModelUpdate.cpp`
- `0x140345207`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\ModelUpdate.cpp`
- `0x140344df9`: `ModelCompressionDisabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall ModelUpdate::UnpackAndCompressModel(ModelUpdate *this, const WCHAR *a2)
{
  const WCHAR *v2; // rax
  char **v4; // rdi
  char *v5; // r9
  const char *v6; // r9
  __int64 System; // rax
  __int64 v8; // rcx
  void (__fastcall *v9)(__int64, _DWORD *, _QWORD *, __int128 *, __int128 *); // rbx
  __int16 *traits_2_unsigned_short; // rax
  const char *v11; // r9
  __int64 v12; // r11
  __int64 v13; // rax
  __int64 v14; // rax
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rbx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  unsigned int v20; // eax
  volatile signed __int32 *v21; // rdi
  __int64 v22; // rdx
  const WCHAR *v23; // rcx
  char *FileW; // rbx
  __int64 v25; // rdx
  HRESULT v26; // eax
  unsigned int v27; // eax
  volatile signed __int32 *v28; // rbx
  __int64 v29; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  __int128 v31; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v32; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v33[2]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v35; // [rsp+90h] [rbp-70h]
  _BYTE v36[8]; // [rsp+A0h] [rbp-60h] BYREF
  volatile signed __int32 *v37; // [rsp+A8h] [rbp-58h]
  _BYTE v38[8]; // [rsp+B0h] [rbp-50h] BYREF
  volatile signed __int32 *v39; // [rsp+B8h] [rbp-48h]
  __int64 ExternalFileInfo; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v41[8]; // [rsp+C8h] [rbp-38h] BYREF
  char v42; // [rsp+E8h] [rbp-18h]
  char v43; // [rsp+F0h] [rbp-10h]
  _BYTE Src[32]; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v2 = a2;
  v4 = (char **)((char *)this + 488);
  v5 = (char *)this + 488;
  if ( *((_QWORD *)this + 64) > 7u )
    v5 = *v4;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v2 = *(const WCHAR **)a2;
  if ( !SetupIterateCabinetW(v2, 0, CabinetCallbackToExpand, v5) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB1,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\ModelUpdate.cpp",
      v6);
  System = SystemInterface::Providers::GetSystem(v38);
  v8 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
  v9 = *(void (__fastcall **)(__int64, _DWORD *, _QWORD *, __int128 *, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v8 + 32LL))(
                                                                                                   v8,
                                                                                                   v36)
                                                                                  + 56LL);
  traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                         L"ModelCompressionDisabled",
                                         word_140483DBA,
                                         0);
  if ( traits_2_unsigned_short == word_140483DBA
    || (v13 = ((char *)traits_2_unsigned_short - (char *)L"ModelCompressionDisabled") >> 1, v13 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v11);
  }
  *(_QWORD *)&v31 = L"ModelCompressionDisabled";
  *((_QWORD *)&v31 + 1) = v13;
  v32 = 0u;
  v33[0] = SystemInterface::Registry::UXCONFIGURATIONROOT_REDIRECTION_ID;
  v14 = -1;
  do
    ++v14;
  while ( SystemInterface::Registry::UXCONFIGURATIONROOT_REDIRECTION_ID[v14] );
  v33[1] = v14;
  v9(v12, v41, v33, &v32, &v31);
  v15 = v37;
  if ( v37 )
  {
    if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  v16 = v39;
  if ( v39 )
  {
    if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  if ( !v43 )
    goto LABEL_21;
  if ( v42 )
    std::_Throw_bad_variant_access();
  if ( v41[0] != 1 )
  {
LABEL_21:
    v17 = (_QWORD *)((char *)this + 304);
    v18 = *((_QWORD *)this + 40);
    if ( *((_QWORD *)this + 41) > 7u )
      v17 = (_QWORD *)*v17;
    *(_QWORD *)&v31 = v17;
    *((_QWORD *)&v31 + 1) = v18;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(lpFileName, &v31);
    std::filesystem::operator/(Src, v4, lpFileName);
    std::wstring::~wstring(lpFileName, v19);
    v31 = 0;
    v20 = std::filesystem::_Dir_enum_impl::_Initialize_dir_enum<std::filesystem::_Dir_enum_impl>(&v31, Src);
    if ( v20 )
      std::filesystem::_Throw_fs_error("directory_iterator::directory_iterator", v20, Src);
    v32 = 0;
    v21 = (volatile signed __int32 *)*((_QWORD *)&v31 + 1);
    if ( *((_QWORD *)&v31 + 1) )
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v31 + 1) + 8LL), 1u);
    v32 = v31;
    if ( v21 )
      _InterlockedAdd(v21 + 2, 1u);
    v35 = 0;
    if ( v21 )
    {
      if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
    while ( 1 )
    {
      v22 = v32;
      if ( !(_QWORD)v32 )
        break;
      std::wstring::wstring(lpFileName, v32 + 32);
      v23 = (const WCHAR *)lpFileName;
      if ( lpFileName[3] > (LPCWSTR)7 )
        v23 = lpFileName[0];
      FileW = (char *)CreateFileW(v23, 0xC0000000, 1u, 0, 3u, 0x80u, 0);
      v33[0] = FileW;
      std::wstring::~wstring(lpFileName, v25);
      ExternalFileInfo = 1;
      v26 = WofSetFileDataLocation(FileW, 2u, &ExternalFileInfo, 8u);
      if ( v26 != -2147024552 && v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC5,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\ModelUpdate.cpp",
          (const char *)(unsigned int)v26,
          dwCreationDisposition);
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(FileW);
      v27 = std::filesystem::_Dir_enum_impl::_Advance_and_reset_if_no_more_files(&v32);
      if ( v27 )
        std::filesystem::_Throw_fs_error("directory_iterator::operator++", v27);
    }
    v28 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
    if ( *((_QWORD *)&v32 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
        if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
      }
    }
    if ( v21 )
    {
      if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
    std::wstring::~wstring(Src, v22);
  }
  UpdateDatabase::UpdateSignalState(*((_QWORD *)this + 48), this, 2);
  if ( v43 && v42 != -1 && (unsigned __int64)v42 >= 2 )
    std::wstring::~wstring(v41, v29);
}

```

## disassembly

```asm
0x140344d44  mov     [rsp-8+arg_10], rbx
0x140344d49  mov     [rsp-8+arg_18], rsi
0x140344d4e  push    rbp
0x140344d4f  push    rdi
0x140344d50  push    r12
0x140344d52  push    r14
0x140344d54  push    r15
0x140344d56  lea     rbp, [rsp-20h]
0x140344d5b  sub     rsp, 120h
0x140344d62  mov     rax, cs:__security_cookie
0x140344d69  xor     rax, rsp
0x140344d6c  mov     [rbp+40h+var_28], rax
0x140344d70  mov     rax, rdx
0x140344d73  mov     rsi, rcx
0x140344d76  xor     r15d, r15d
0x140344d79  lea     rdi, [rcx+1E8h]
0x140344d80  mov     r9, rdi
0x140344d83  cmp     qword ptr [rdi+18h], 7
0x140344d88  jbe     short loc_140344D8D
0x140344d8a  mov     r9, [rdi]; Context
0x140344d8d  cmp     qword ptr [rdx+18h], 7
0x140344d92  jbe     short loc_140344D97
0x140344d94  mov     rax, [rdx]
0x140344d97  lea     r8, ?CabinetCallbackToExpand@@YAIPEAXI_K1@Z; MsgHandler
0x140344d9e  xor     edx, edx; Reserved
0x140344da0  mov     rcx, rax; CabinetFile
0x140344da3  call    cs:__imp_SetupIterateCabinetW
0x140344da9  mov     rcx, [rbp+48h]; this
0x140344dad  test    eax, eax
0x140344daf  jz      loc_140345207
0x140344db5  lea     rcx, [rbp+40h+var_90]
0x140344db9  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140344dbe  nop
0x140344dbf  mov     rdx, [rax]
0x140344dc2  mov     rax, [rdx+8]
0x140344dc6  movsxd  rcx, dword ptr [rax+4]
0x140344dca  add     rdx, 8
0x140344dce  add     rcx, rdx
0x140344dd1  mov     rax, [rcx]
0x140344dd4  lea     rdx, [rbp+40h+var_A0]
0x140344dd8  mov     rax, [rax+20h]
0x140344ddc  call    _guard_dispatch_icall
0x140344de1  nop
0x140344de2  mov     r11, [rax]
0x140344de5  mov     rax, [r11]
0x140344de8  mov     rbx, [rax+38h]
0x140344dec  xor     r8d, r8d
0x140344def  lea     r14, word_140483DBA
0x140344df6  mov     rdx, r14
0x140344df9  lea     r12, aModelcompressi; "ModelCompressionDisabled"
0x140344e00  mov     rcx, r12
0x140344e03  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140344e08  cmp     rax, r14
0x140344e0b  jz      loc_1403451F1
0x140344e11  sub     rax, r12
0x140344e14  sar     rax, 1
0x140344e17  or      r14, 0FFFFFFFFFFFFFFFFh
0x140344e1b  cmp     rax, r14
0x140344e1e  jz      loc_1403451F1
0x140344e24  mov     qword ptr [rsp+140h+var_100], r12
0x140344e29  mov     qword ptr [rsp+140h+var_100+8], rax
0x140344e2e  mov     qword ptr [rsp+140h+var_F0], r15
0x140344e33  mov     qword ptr [rsp+140h+var_F0+8], r15
0x140344e38  mov     rcx, cs:?UXCONFIGURATIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UXCONFIGURATIONROOT_REDIRECTION_ID
0x140344e3f  mov     qword ptr [rsp+140h+var_E0], rcx
0x140344e44  mov     rax, r14
0x140344e47  inc     rax
0x140344e4a  cmp     [rcx+rax*2], r15w
0x140344e4f  jnz     short loc_140344E47
0x140344e51  mov     qword ptr [rsp+140h+var_E0+8], rax
0x140344e56  movups  xmm0, [rsp+140h+var_100]
0x140344e5b  movdqu  [rsp+140h+var_100], xmm0
0x140344e61  movaps  xmm1, [rsp+140h+var_F0]
0x140344e66  movdqa  [rsp+140h+var_F0], xmm1
0x140344e6c  movaps  xmm0, [rsp+140h+var_E0]
0x140344e71  movdqa  [rsp+140h+var_E0], xmm0
0x140344e77  lea     rax, [rsp+140h+var_100]
0x140344e7c  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x140344e81  lea     r9, [rsp+140h+var_F0]
0x140344e86  lea     r8, [rsp+140h+var_E0]
0x140344e8b  lea     rdx, [rbp+40h+var_78]
0x140344e8f  mov     rcx, r11
0x140344e92  mov     rax, rbx
0x140344e95  call    _guard_dispatch_icall
0x140344e9a  nop
0x140344e9b  mov     rbx, [rbp+40h+var_98]
0x140344e9f  test    rbx, rbx
0x140344ea2  jz      short loc_140344EDC
0x140344ea4  mov     eax, r14d
0x140344ea7  lock xadd [rbx+8], eax
0x140344eac  add     eax, r14d
0x140344eaf  jnz     short loc_140344EDC
0x140344eb1  mov     rax, [rbx]
0x140344eb4  mov     rcx, rbx
0x140344eb7  mov     rax, [rax]
0x140344eba  call    _guard_dispatch_icall
0x140344ebf  mov     eax, r14d
0x140344ec2  lock xadd [rbx+0Ch], eax
0x140344ec7  add     eax, r14d
0x140344eca  jnz     short loc_140344EDC
0x140344ecc  mov     rax, [rbx]
0x140344ecf  mov     rcx, rbx
0x140344ed2  mov     rax, [rax+8]
0x140344ed6  call    _guard_dispatch_icall
0x140344edb  nop
0x140344edc  mov     rbx, [rbp+40h+var_88]
0x140344ee0  test    rbx, rbx
0x140344ee3  jz      short loc_140344F1C
0x140344ee5  mov     eax, r14d
0x140344ee8  lock xadd [rbx+8], eax
0x140344eed  add     eax, r14d
0x140344ef0  jnz     short loc_140344F1C
0x140344ef2  mov     rax, [rbx]
0x140344ef5  mov     rcx, rbx
0x140344ef8  mov     rax, [rax]
0x140344efb  call    _guard_dispatch_icall
0x140344f00  mov     eax, r14d
0x140344f03  lock xadd [rbx+0Ch], eax
0x140344f08  add     eax, r14d
0x140344f0b  jnz     short loc_140344F1C
0x140344f0d  mov     rax, [rbx]
0x140344f10  mov     rcx, rbx
0x140344f13  mov     rax, [rax+8]
0x140344f17  call    _guard_dispatch_icall
0x140344f1c  mov     r12d, 1
0x140344f22  cmp     [rbp+40h+var_50], r15b
0x140344f26  jz      short loc_140344F3C
0x140344f28  cmp     [rbp+40h+var_58], r15b
0x140344f2c  jnz     loc_14034522C
0x140344f32  cmp     [rbp+40h+var_78], r12d
0x140344f36  jz      loc_14034516A
0x140344f3c  lea     rax, [rsi+130h]
0x140344f43  mov     rcx, [rax+10h]
0x140344f47  cmp     qword ptr [rax+18h], 7
0x140344f4c  jbe     short loc_140344F51
0x140344f4e  mov     rax, [rax]
0x140344f51  mov     qword ptr [rsp+140h+var_100], rax
0x140344f56  mov     qword ptr [rsp+140h+var_100+8], rcx
0x140344f5b  movaps  xmm0, [rsp+140h+var_100]
0x140344f60  movdqa  [rsp+140h+var_100], xmm0
0x140344f66  lea     rdx, [rsp+140h+var_100]
0x140344f6b  lea     rcx, [rsp+140h+lpFileName]
0x140344f70  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x140344f75  nop
0x140344f76  lea     r8, [rsp+140h+lpFileName]; void *
0x140344f7b  mov     rdx, rdi; void *
0x140344f7e  lea     rcx, [rbp+40h+Src]; Src
0x140344f82  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x140344f87  nop
0x140344f88  lea     rcx, [rsp+140h+lpFileName]
0x140344f8d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140344f92  xorps   xmm0, xmm0
0x140344f95  movdqa  [rsp+140h+var_100], xmm0
0x140344f9b  lea     rdx, [rbp+40h+Src]
0x140344f9f  lea     rcx, [rsp+140h+var_100]
0x140344fa4  call    ??$_Initialize_dir_enum@U_Dir_enum_impl@filesystem@std@@@_Dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAV?$shared_ptr@U_Dir_enum_impl@filesystem@std@@@2@AEBVpath@12@W4directory_options@12@@Z; std::filesystem::_Dir_enum_impl::_Initialize_dir_enum<std::filesystem::_Dir_enum_impl>(std::shared_ptr<std::filesystem::_Dir_enum_impl> &,std::filesystem::path const &,std::filesystem::directory_options)
0x140344fa9  test    eax, eax
0x140344fab  jnz     loc_140345219
0x140344fb1  xorps   xmm0, xmm0
0x140344fb4  movups  [rsp+140h+var_F0], xmm0
0x140344fb9  mov     rdi, qword ptr [rsp+140h+var_100+8]
0x140344fbe  test    rdi, rdi
0x140344fc1  jz      short loc_140344FC8
0x140344fc3  lock add [rdi+8], r12d
0x140344fc8  movaps  xmm0, [rsp+140h+var_100]
0x140344fcd  movdqa  [rsp+140h+var_F0], xmm0
0x140344fd3  test    rdi, rdi
0x140344fd6  jz      short loc_140344FDD
0x140344fd8  lock add [rdi+8], r12d
0x140344fdd  xorps   xmm1, xmm1
0x140344fe0  movdqu  [rbp+40h+var_B0], xmm1
0x140344fe5  test    rdi, rdi
0x140344fe8  jz      short loc_140345022
0x140344fea  mov     eax, r14d
0x140344fed  lock xadd [rdi+8], eax
0x140344ff2  add     eax, r14d
0x140344ff5  jnz     short loc_140345022
0x140344ff7  mov     rax, [rdi]
0x140344ffa  mov     rcx, rdi
0x140344ffd  mov     rax, [rax]
0x140345000  call    _guard_dispatch_icall
0x140345005  mov     eax, r14d
0x140345008  lock xadd [rdi+0Ch], eax
0x14034500d  add     eax, r14d
0x140345010  jnz     short loc_140345022
0x140345012  mov     rax, [rdi]
0x140345015  mov     rcx, rdi
0x140345018  mov     rax, [rax+8]
0x14034501c  call    _guard_dispatch_icall
0x140345021  nop
0x140345022  mov     rdx, qword ptr [rsp+140h+var_F0]
0x140345027  test    rdx, rdx
0x14034502a  jz      loc_1403450E2
0x140345030  add     rdx, 20h ; ' '
0x140345034  lea     rcx, [rsp+140h+lpFileName]
0x140345039  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14034503e  lea     rcx, [rsp+140h+lpFileName]
0x140345043  cmp     [rbp+40h+var_B8], 7
0x140345048  cmova   rcx, [rsp+140h+lpFileName]; lpFileName
0x14034504e  mov     [rsp+140h+hTemplateFile], r15; hTemplateFile
0x140345053  mov     [rsp+140h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14034505b  mov     [rsp+140h+dwCreationDisposition], 3; int
0x140345063  xor     r9d, r9d; lpSecurityAttributes
0x140345066  mov     r8d, r12d; dwShareMode
0x140345069  mov     edx, 0C0000000h; dwDesiredAccess
0x14034506e  call    cs:__imp_CreateFileW
0x140345074  mov     rbx, rax
0x140345077  mov     qword ptr [rsp+140h+var_E0], rax
0x14034507c  lea     rcx, [rsp+140h+lpFileName]
0x140345081  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140345086  mov     [rbp+40h+ExternalFileInfo], 1
0x14034508e  mov     r9d, 8; Length
0x140345094  lea     r8, [rbp+40h+ExternalFileInfo]; ExternalFileInfo
0x140345098  lea     edx, [r9-6]; Provider
0x14034509c  mov     rcx, rbx; FileHandle
0x14034509f  call    cs:__imp_WofSetFileDataLocation
0x1403450a5  cmp     eax, 80070158h
0x1403450aa  jz      short loc_1403450B8
0x1403450ac  mov     rcx, [rbp+48h]; this
0x1403450b0  test    eax, eax
0x1403450b2  js      loc_1403451CD
0x1403450b8  lea     rax, [rbx-1]
0x1403450bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1403450c0  ja      short loc_1403450CB
0x1403450c2  mov     rcx, rbx; hObject
0x1403450c5  call    cs:__imp_CloseHandle
0x1403450cb  lea     rcx, [rsp+140h+var_F0]
0x1403450d0  call    ?_Advance_and_reset_if_no_more_files@_Dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAV?$shared_ptr@U_Dir_enum_impl@filesystem@std@@@3@@Z; std::filesystem::_Dir_enum_impl::_Advance_and_reset_if_no_more_files(std::shared_ptr<std::filesystem::_Dir_enum_impl> &)
0x1403450d5  test    eax, eax
0x1403450d7  jnz     loc_1403451E2
0x1403450dd  jmp     loc_140345022
0x1403450e2  mov     rbx, qword ptr [rsp+140h+var_F0+8]
0x1403450e7  test    rbx, rbx
0x1403450ea  jz      short loc_140345124
0x1403450ec  mov     eax, r14d
0x1403450ef  lock xadd [rbx+8], eax
0x1403450f4  add     eax, r14d
0x1403450f7  jnz     short loc_140345124
0x1403450f9  mov     rax, [rbx]
0x1403450fc  mov     rcx, rbx
0x1403450ff  mov     rax, [rax]
0x140345102  call    _guard_dispatch_icall
0x140345107  mov     eax, r14d
0x14034510a  lock xadd [rbx+0Ch], eax
0x14034510f  add     eax, r14d
0x140345112  jnz     short loc_140345124
0x140345114  mov     rax, [rbx]
0x140345117  mov     rcx, rbx
0x14034511a  mov     rax, [rax+8]
0x14034511e  call    _guard_dispatch_icall
0x140345123  nop
0x140345124  test    rdi, rdi
0x140345127  jz      short loc_140345161
0x140345129  mov     eax, r14d
0x14034512c  lock xadd [rdi+8], eax
0x140345131  add     eax, r14d
0x140345134  jnz     short loc_140345161
0x140345136  mov     rax, [rdi]
0x140345139  mov     rcx, rdi
0x14034513c  mov     rax, [rax]
0x14034513f  call    _guard_dispatch_icall
0x140345144  mov     eax, r14d
0x140345147  lock xadd [rdi+0Ch], eax
0x14034514c  add     eax, r14d
0x14034514f  jnz     short loc_140345161
0x140345151  mov     rax, [rdi]
0x140345154  mov     rcx, rdi
0x140345157  mov     rax, [rax+8]
0x14034515b  call    _guard_dispatch_icall
0x140345160  nop
0x140345161  lea     rcx, [rbp+40h+Src]
0x140345165  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14034516a  mov     r8d, 2
0x140345170  mov     rdx, rsi
0x140345173  mov     rcx, [rsi+180h]
0x14034517a  call    ?UpdateSignalState@UpdateDatabase@@QEAAXAEBVUpdate@@W4SignalUpdateState@SystemInterface@@@Z; UpdateDatabase::UpdateSignalState(Update const &,SystemInterface::SignalUpdateState)
0x14034517f  nop
0x140345180  cmp     [rbp+40h+var_50], r15b
0x140345184  jz      short loc_1403451A5
0x140345186  movsx   rax, [rbp+40h+var_58]
0x14034518b  add     rax, r12
0x14034518e  jz      short loc_1403451A5
0x140345190  sub     rax, 1
0x140345194  jz      short loc_1403451A5
0x140345196  cmp     rax, 1
0x14034519a  jz      short loc_1403451A5
0x14034519c  lea     rcx, [rbp+40h+var_78]
0x1403451a0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403451a5  mov     rcx, [rbp+40h+var_28]
0x1403451a9  xor     rcx, rsp; StackCookie
0x1403451ac  call    __security_check_cookie
0x1403451b1  lea     r11, [rsp+140h+var_20]
0x1403451b9  mov     rbx, [r11+40h]
0x1403451bd  mov     rsi, [r11+48h]
0x1403451c1  mov     rsp, r11
0x1403451c4  pop     r15
0x1403451c6  pop     r14
0x1403451c8  pop     r12
0x1403451ca  pop     rdi
0x1403451cb  pop     rbp
  ... truncated ...
```
