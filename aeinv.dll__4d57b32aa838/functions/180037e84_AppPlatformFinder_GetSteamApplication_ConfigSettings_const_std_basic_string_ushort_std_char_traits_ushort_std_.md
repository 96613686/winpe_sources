# AppPlatformFinder::GetSteamApplication(ConfigSettings const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<Application,std::allocator<Application>> &)

- ea: `0x180037e84`
- end: `0x1800387ac`
- name: `?GetSteamApplication@AppPlatformFinder@@CAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@4@@Z`
- size: `2344`
- prototype: `__int64 __fastcall(struct ConfigSettings *, __int64, const WCHAR *, __int64 *)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180104984`

## callees

- `0x18000b364`
- `0x18000b7cc`
- `0x18000dfc4`
- `0x18000eb5c`
- `0x18000ecac`
- `0x1800118d0`
- `0x1800150ac`
- `0x18001716c`
- `0x1800175b0`
- `0x180017c98`
- `0x180018450`
- `0x1800188f4`
- `0x180018a60`
- `0x1800197d4`
- `0x18001becc`
- `0x18001e0d0`
- `0x180022500`
- `0x18002f4b4`
- `0x180031604`
- `0x180034908`
- `0x180037e84`
- `0x1800403ac`
- `0x1800404c4`
- `0x1800417a8`
- `0x180044c88`
- `0x180044d04`
- `0x1800493b8`
- `0x18004f820`
- `0x1800515d8`
- `0x180052f28`
- `0x180059920`
- `0x18005d690`
- `0x1800ff5e4`
- `0x1800ff85c`
- `0x180130010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003848c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003848c`
- `KERNEL32!FileTimeToSystemTime` at `0x18003830a`
- `KERNEL32!FileTimeToSystemTime` at `0x18003830a`
- `KERNEL32!GetFileTime` at `0x1800382ee`
- `KERNEL32!GetFileTime` at `0x1800382ee`
- `KERNEL32!CreateFileW` at `0x1800382c2`
- `KERNEL32!CreateFileW` at `0x1800382c2`

## string_xrefs

- `0x18003815e`: `\common\`
- `0x1800380ab`: `"installdir"`
- `0x18003872e`: `Failed to open Steam app manifest file %ws`

## pseudocode

```c
__int64 __fastcall AppPlatformFinder::GetSteamApplication(
        struct ConfigSettings *a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 *a4)
{
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int16 *v11; // rax
  __int64 v12; // rax
  _BYTE *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned __int16 *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  unsigned int v22; // r15d
  __int64 v23; // rsi
  __int64 v24; // rax
  HANDLE FileW; // rax
  __int64 v26; // rax
  char v27; // r15
  __int64 *v28; // rbx
  _QWORD *v29; // rax
  int v30; // eax
  const struct File *i; // rbx
  __int64 v32; // rbx
  __int64 v33; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-D0h]
  struct _FILETIME CreationTime; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v39; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B0h]
  _QWORD v41[34]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v42[2]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v43; // [rsp+180h] [rbp+80h]
  struct _SYSTEMTIME SystemTime; // [rsp+190h] [rbp+90h] BYREF
  __int64 v45; // [rsp+1A0h] [rbp+A0h]
  _BYTE v46[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v47; // [rsp+1C0h] [rbp+C0h]
  _BYTE v48[16]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v49; // [rsp+1E0h] [rbp+E0h]
  struct File *v50[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v51; // [rsp+200h] [rbp+100h]
  _BYTE Src[32]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v53[32]; // [rsp+230h] [rbp+130h] BYREF
  __int64 v54[4]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v55[32]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v56[32]; // [rsp+290h] [rbp+190h] BYREF
  void **v57; // [rsp+2B0h] [rbp+1B0h] BYREF
  void **v58; // [rsp+2B8h] [rbp+1B8h]
  void **v59; // [rsp+2C0h] [rbp+1C0h]
  __int64 v60; // [rsp+318h] [rbp+218h]
  char v61; // [rsp+5D6h] [rbp+4D6h]
  _BYTE v62[1008]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v40 = -2;
  std::wstring::wstring(v53);
  std::wstring::wstring(v55);
  std::wstring::wstring(Src);
  std::wstring::wstring(v54);
  std::basic_ifstream<unsigned short>::basic_ifstream<unsigned short>(v41, v8);
  if ( !v41[18] )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"AppPlatformFinder::GetSteamApplication",
      423,
      (unsigned int)"Failed to open Steam app manifest file %ws");
    goto LABEL_47;
  }
  std::wstring::wstring(v42);
  while ( (*((_BYTE *)&v41[2] + *(int *)(v41[0] + 4LL)) & 1) == 0 )
  {
    std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v41, v42);
    if ( v43 > 2 )
    {
      std::wstring::wstring(v50, L"\"appid\"");
      v9 = std::wstring::find(v42, v50);
      if ( v9 == -1 )
      {
        std::wstring::wstring(v46, L"\"name\"");
        v14 = std::wstring::find(v42, v46);
        if ( v14 == -1 )
        {
          std::wstring::wstring(v48, L"\"installdir\"");
          v18 = std::wstring::find(v42, v48);
          if ( v18 != -1 )
          {
            v19 = std::wstring::substr(v42, v56, v18 + v49, v43 - (v18 + v49));
            std::wstring::operator=(v42, v19);
            std::wstring::~wstring(v56);
            v20 = Utility::TrimSpace(v42);
            std::wstring::operator=(v42, v20);
            std::wstring::substr(v42, &SystemTime, 1, v43 - 2);
            std::wstring::operator=(Src, a2);
            std::wstring::_Append<unsigned short>(Src);
            std::wstring::_Append<unsigned short>(Src);
            std::wstring::~wstring(&SystemTime);
          }
        }
        else
        {
          v15 = std::wstring::substr(v42, v48, v14 + v47, v43 - (v14 + v47));
          std::wstring::operator=(v42, v15);
          std::wstring::~wstring(v48);
          v16 = Utility::TrimSpace(v42);
          std::wstring::operator=(v42, v16);
          v17 = std::wstring::substr(v42, v48, 1, v43 - 2);
          std::wstring::operator=(v55, v17);
        }
        std::wstring::~wstring(v48);
        v13 = v46;
      }
      else
      {
        v10 = std::wstring::substr(v42, v48, v9 + v51, v43 - (v9 + v51));
        std::wstring::operator=(v42, v10);
        std::wstring::~wstring(v48);
        v11 = Utility::TrimSpace(v42);
        std::wstring::operator=(v42, v11);
        v12 = std::wstring::substr(v42, v48, 1, v43 - 2);
        std::wstring::operator=(v53, v12);
        v13 = v48;
      }
      std::wstring::~wstring(v13);
      std::wstring::~wstring(v50);
    }
  }
  std::wstring::~wstring(v42);
  v21 = *a4;
  if ( 0xEFBEFBEFBEFBEFBFuLL * ((a4[1] - *a4) >> 4) )
  {
    v22 = 0;
    while ( 1 )
    {
      v23 = 1008LL * v22;
      v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v23 + v21 + 16) + 48LL))(v23 + v21 + 16);
      std::wstring::wstring(v48, v24);
      if ( std::wstring::find(v48, v53) != -1 )
        break;
      std::wstring::~wstring(v48);
      ++v22;
      v21 = *a4;
      if ( v22 >= 0xEFBEFBEFBEFBEFBFuLL * ((a4[1] - *a4) >> 4) )
        goto LABEL_17;
    }
    v27 = 0;
    v28 = &Application::ApplicationSourceSteam;
    if ( (unsigned __int64)qword_180182698 > 7 )
      v28 = (__int64 *)Application::ApplicationSourceSteam;
    v29 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v23 + *a4 + 16) + 64LL))(v23 + *a4 + 16);
    if ( v29[3] > 7u )
      v29 = (_QWORD *)*v29;
    if ( (unsigned int)_o__wcsicmp(v29, v28) )
    {
      std::wstring::operator=(v23 + *a4 + 336, &Application::ApplicationSourceSteam);
      v27 = 1;
    }
    if ( *(_QWORD *)(*a4 + v23 + 32) )
    {
      if ( !v27 )
      {
LABEL_43:
        std::wstring::~wstring(v48);
        goto LABEL_47;
      }
    }
    else
    {
      SystemTime = 0;
      v45 = 0;
      std::wstring::wstring(v46, L".exe");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&SystemTime, v46);
      std::wstring::~wstring(v46);
      std::wstring::wstring(v46, L".dll");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&SystemTime, v46);
      std::wstring::~wstring(v46);
      std::wstring::wstring(v46, L".cpl");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&SystemTime, v46);
      std::wstring::~wstring(v46);
      std::wstring::wstring(v46, L".sys");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&SystemTime, v46);
      std::wstring::~wstring(v46);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v23 + *a4 + 16) + 16LL))(v23 + *a4 + 16);
      v30 = std::vector<std::wstring>::vector<std::wstring>(v42, &SystemTime);
      File::SearchForPeFiles((unsigned int)v50, (_DWORD)a1, (unsigned int)Src, v30);
      for ( i = v50[0]; i != v50[1]; i = (const struct File *)((char *)i + 816) )
      {
        File::File((File *)&v57, i);
        if ( v61 )
        {
          Application::SetSupplimentalFile((Application *)(v23 + *a4), (const struct File *)&v57);
        }
        else if ( v60 )
        {
          Application::SetFile((Application *)(v23 + *a4), (const struct File *)&v57);
        }
        File::~File((File *)&v57);
      }
      v32 = v23 + *a4;
      v33 = Application::ComputeProgramInstanceId(v32, (__int64)v56);
      std::wstring::operator=(v32 + 400, v33);
      std::wstring::~wstring(v56);
      if ( *((_BYTE *)a1 + 219) )
        (*(void (__fastcall **)(__int64, struct ConfigSettings *))(*(_QWORD *)(v23 + *a4) + 96LL))(v23 + *a4, a1);
      std::vector<File>::_Tidy(v50);
      std::vector<std::wstring>::_Tidy(&SystemTime);
    }
    Application::SaveApplicationToCache((Application *)(v23 + *a4), a1);
    goto LABEL_43;
  }
LABEL_17:
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  FileW = CreateFileW(a3, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v39 = FileW;
  CreationTime = 0;
  if ( FileW != (HANDLE)-1LL )
  {
    GetFileTime(FileW, &CreationTime, 0, 0);
    SystemTime = 0;
    if ( FileTimeToSystemTime(&CreationTime, &SystemTime) )
    {
      LODWORD(hTemplateFile) = SystemTime.wMinute;
      dwFlagsAndAttributes[0] = SystemTime.wHour;
      dwCreationDisposition[0] = SystemTime.wYear;
      v26 = Utility::FormatWstring(
              v56,
              L"%02d/%02d/%04d %02d:%02d:%02d",
              SystemTime.wMonth,
              SystemTime.wDay,
              *(_QWORD *)dwCreationDisposition,
              *(_QWORD *)dwFlagsAndAttributes,
              hTemplateFile,
              SystemTime.wSecond,
              CreationTime,
              v39,
              v40);
      std::wstring::operator=(v54, v26);
      std::wstring::~wstring(v56);
    }
  }
  Application::Application((Application *)&v57);
  v57 = &EpicGamesApplication::`vftable'{for `IAmiInventoryTelemetryItem'};
  v58 = &AppvApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
  v59 = &SteamApplication::`vftable';
  SteamApplication::GetSteamApplication((Application *)&v57, a1, (__int64)v54, (__int64)Src);
  Application::Application((Application *)v62, (const struct Application *)&v57);
  v57 = &EpicGamesApplication::`vftable'{for `IAmiInventoryTelemetryItem'};
  v58 = &AppvApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
  v59 = &SteamApplication::`vftable';
  Application::~Application((Application *)&v57);
  if ( a4[1] == a4[2] )
  {
    std::vector<Application>::_Emplace_reallocate<Application const &>(a4, a4[1], v62);
  }
  else
  {
    Application::Application((Application *)a4[1], (const struct Application *)v62);
    a4[1] += 1008;
  }
  Application::~Application((Application *)v62);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v39);
LABEL_47:
  std::basic_ifstream<unsigned short>::`vbase destructor'(v41);
  std::wstring::~wstring(v54);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(v55);
  return std::wstring::~wstring(v53);
}

```

## disassembly

```asm
0x180037e84  push    rbp
0x180037e86  push    rbx
0x180037e87  push    rsi
0x180037e88  push    rdi
0x180037e89  push    r12
0x180037e8b  push    r14
0x180037e8d  push    r15
0x180037e8f  lea     rbp, [rsp-9A0h]
0x180037e97  sub     rsp, 0AA0h
0x180037e9e  mov     [rsp+0AD0h+var_A80], 0FFFFFFFFFFFFFFFEh
0x180037ea7  mov     rax, cs:__security_cookie
0x180037eae  xor     rax, rsp
0x180037eb1  mov     [rbp+9D0h+var_40], rax
0x180037eb8  mov     rdi, r9
0x180037ebb  mov     rbx, r8
0x180037ebe  mov     rsi, rdx
0x180037ec1  mov     r12, rcx
0x180037ec4  lea     rcx, [rbp+9D0h+var_8A0]
0x180037ecb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180037ed0  nop
0x180037ed1  lea     rcx, [rbp+9D0h+var_860]
0x180037ed8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180037edd  nop
0x180037ede  lea     rcx, [rbp+9D0h+Src]
0x180037ee5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180037eea  nop
0x180037eeb  lea     rcx, [rbp+9D0h+var_880]
0x180037ef2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180037ef7  nop
0x180037ef8  mov     rdx, r8
0x180037efb  lea     rcx, [rsp+0AD0h+var_A70]
0x180037f00  call    ??0?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@HH@Z; std::basic_ifstream<ushort>::basic_ifstream<ushort>(std::wstring const &,int,int)
0x180037f05  nop
0x180037f06  cmp     [rbp+9D0h+var_9E0], 0
0x180037f0b  jz      loc_18003871F
0x180037f11  lea     rcx, [rbp+9D0h+var_960]
0x180037f15  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180037f1a  nop
0x180037f1b  mov     r14d, 1
0x180037f21  jmp     loc_1800381CF
0x180037f26  lea     rdx, [rbp+9D0h+var_960]
0x180037f2a  lea     rcx, [rsp+0AD0h+var_A70]
0x180037f2f  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180037f34  cmp     [rbp+9D0h+var_950], 2
0x180037f3c  jbe     loc_1800381CF
0x180037f42  lea     rdx, aAppid; "\"appid\""
0x180037f49  lea     rcx, [rbp+9D0h+var_8E0]
0x180037f50  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180037f55  nop
0x180037f56  lea     rdx, [rbp+9D0h+var_8E0]
0x180037f5d  lea     rcx, [rbp+9D0h+var_960]
0x180037f61  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x180037f66  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037f6a  jz      loc_180037FFA
0x180037f70  mov     r8, [rbp+9D0h+var_8D0]
0x180037f77  add     r8, rax
0x180037f7a  mov     r9, [rbp+9D0h+var_950]
0x180037f81  sub     r9, r8
0x180037f84  lea     rdx, [rbp+9D0h+var_900]
0x180037f8b  lea     rcx, [rbp+9D0h+var_960]
0x180037f8f  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180037f94  mov     rdx, rax
0x180037f97  lea     rcx, [rbp+9D0h+var_960]
0x180037f9b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180037fa0  lea     rcx, [rbp+9D0h+var_900]
0x180037fa7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180037fac  lea     rcx, [rbp+9D0h+var_960]
0x180037fb0  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x180037fb5  mov     rdx, rax
0x180037fb8  lea     rcx, [rbp+9D0h+var_960]
0x180037fbc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180037fc1  mov     r9, [rbp+9D0h+var_950]
0x180037fc8  add     r9, 0FFFFFFFFFFFFFFFEh
0x180037fcc  mov     r8, r14
0x180037fcf  lea     rdx, [rbp+9D0h+var_900]
0x180037fd6  lea     rcx, [rbp+9D0h+var_960]
0x180037fda  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180037fdf  mov     rdx, rax
0x180037fe2  lea     rcx, [rbp+9D0h+var_8A0]
0x180037fe9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180037fee  lea     rcx, [rbp+9D0h+var_900]
0x180037ff5  jmp     loc_1800381BD
0x180037ffa  lea     rdx, aName_0; "\"name\""
0x180038001  lea     rcx, [rbp+9D0h+var_920]
0x180038008  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003800d  nop
0x18003800e  lea     rdx, [rbp+9D0h+var_920]
0x180038015  lea     rcx, [rbp+9D0h+var_960]
0x180038019  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x18003801e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038022  jz      loc_1800380AB
0x180038028  mov     r8, [rbp+9D0h+var_910]
0x18003802f  add     r8, rax
0x180038032  mov     r9, [rbp+9D0h+var_950]
0x180038039  sub     r9, r8
0x18003803c  lea     rdx, [rbp+9D0h+var_900]
0x180038043  lea     rcx, [rbp+9D0h+var_960]
0x180038047  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18003804c  mov     rdx, rax
0x18003804f  lea     rcx, [rbp+9D0h+var_960]
0x180038053  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180038058  lea     rcx, [rbp+9D0h+var_900]
0x18003805f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038064  lea     rcx, [rbp+9D0h+var_960]
0x180038068  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x18003806d  mov     rdx, rax
0x180038070  lea     rcx, [rbp+9D0h+var_960]
0x180038074  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180038079  mov     r9, [rbp+9D0h+var_950]
0x180038080  add     r9, 0FFFFFFFFFFFFFFFEh
0x180038084  mov     r8, r14
0x180038087  lea     rdx, [rbp+9D0h+var_900]
0x18003808e  lea     rcx, [rbp+9D0h+var_960]
0x180038092  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180038097  mov     rdx, rax
0x18003809a  lea     rcx, [rbp+9D0h+var_860]
0x1800380a1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800380a6  jmp     loc_1800381A9
0x1800380ab  lea     rdx, aInstalldir; "\"installdir\""
0x1800380b2  lea     rcx, [rbp+9D0h+var_900]
0x1800380b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800380be  nop
0x1800380bf  lea     rdx, [rbp+9D0h+var_900]
0x1800380c6  lea     rcx, [rbp+9D0h+var_960]
0x1800380ca  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x1800380cf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800380d3  jz      loc_1800381A9
0x1800380d9  mov     r8, [rbp+9D0h+var_8F0]
0x1800380e0  add     r8, rax
0x1800380e3  mov     r9, [rbp+9D0h+var_950]
0x1800380ea  sub     r9, r8
0x1800380ed  lea     rdx, [rbp+9D0h+var_840]
0x1800380f4  lea     rcx, [rbp+9D0h+var_960]
0x1800380f8  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800380fd  mov     rdx, rax
0x180038100  lea     rcx, [rbp+9D0h+var_960]
0x180038104  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180038109  lea     rcx, [rbp+9D0h+var_840]
0x180038110  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038115  lea     rcx, [rbp+9D0h+var_960]
0x180038119  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x18003811e  mov     rdx, rax
0x180038121  lea     rcx, [rbp+9D0h+var_960]
0x180038125  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003812a  mov     r9, [rbp+9D0h+var_950]
0x180038131  add     r9, 0FFFFFFFFFFFFFFFEh
0x180038135  mov     r8, r14
0x180038138  lea     rdx, [rbp+9D0h+SystemTime]
0x18003813f  lea     rcx, [rbp+9D0h+var_960]
0x180038143  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180038148  nop
0x180038149  mov     rdx, rsi
0x18003814c  lea     rcx, [rbp+9D0h+Src]
0x180038153  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180038158  mov     r8d, 8
0x18003815e  lea     rdx, aCommon; "\\common\\"
0x180038165  lea     rcx, [rbp+9D0h+Src]; Src
0x18003816c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180038171  lea     rdx, [rbp+9D0h+SystemTime]
0x180038178  cmp     [rbp+9D0h+var_928], 7
0x180038180  cmova   rdx, qword ptr [rbp+9D0h+SystemTime.wYear]
0x180038188  mov     r8, [rbp+9D0h+var_930]
0x18003818f  lea     rcx, [rbp+9D0h+Src]; Src
0x180038196  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003819b  nop
0x18003819c  lea     rcx, [rbp+9D0h+SystemTime]
0x1800381a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800381a8  nop
0x1800381a9  lea     rcx, [rbp+9D0h+var_900]
0x1800381b0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800381b5  nop
0x1800381b6  lea     rcx, [rbp+9D0h+var_920]
0x1800381bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800381c2  nop
0x1800381c3  lea     rcx, [rbp+9D0h+var_8E0]
0x1800381ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800381cf  mov     rax, [rsp+0AD0h+var_A70]
0x1800381d4  movsxd  rcx, dword ptr [rax+4]
0x1800381d8  test    [rsp+rcx+0AD0h+var_A60], r14b
0x1800381dd  jz      loc_180037F26
0x1800381e3  lea     rcx, [rbp+9D0h+var_960]
0x1800381e7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800381ec  mov     rdx, [rdi]
0x1800381ef  mov     rax, [rdi+8]
0x1800381f3  sub     rax, rdx
0x1800381f6  sar     rax, 4
0x1800381fa  mov     rcx, 0EFBEFBEFBEFBEFBFh
0x180038204  imul    rax, rcx
0x180038208  test    rax, rax
0x18003820b  jz      loc_180038291
0x180038211  xor     r15d, r15d
0x180038214  mov     eax, r15d
0x180038217  imul    rsi, rax, 3F0h
0x18003821e  lea     rcx, [rdx+10h]
0x180038222  add     rcx, rsi
0x180038225  mov     rax, [rcx]
0x180038228  mov     rax, [rax+30h]
0x18003822c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038231  mov     rdx, rax
0x180038234  lea     rcx, [rbp+9D0h+var_900]
0x18003823b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180038240  nop
0x180038241  lea     rdx, [rbp+9D0h+var_8A0]
0x180038248  lea     rcx, [rbp+9D0h+var_900]
0x18003824f  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x180038254  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038258  jnz     loc_18003844C
0x18003825e  lea     rcx, [rbp+9D0h+var_900]
0x180038265  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003826a  add     r15d, r14d
0x18003826d  mov     rdx, [rdi]
0x180038270  mov     rcx, [rdi+8]
0x180038274  sub     rcx, rdx
0x180038277  sar     rcx, 4
0x18003827b  mov     rax, 0EFBEFBEFBEFBEFBFh
0x180038285  imul    rcx, rax
0x180038289  mov     eax, r15d
0x18003828c  cmp     rax, rcx
0x18003828f  jb      short loc_180038214
0x180038291  cmp     qword ptr [rbx+18h], 7
0x180038296  jbe     short loc_18003829B
0x180038298  mov     rbx, [rbx]
0x18003829b  mov     [rsp+0AD0h+hTemplateFile], 0; hTemplateFile
0x1800382a4  mov     [rsp+0AD0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800382ac  mov     [rsp+0AD0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800382b4  xor     r9d, r9d; lpSecurityAttributes
0x1800382b7  mov     r8d, r14d; dwShareMode
0x1800382ba  mov     edx, 80000000h; dwDesiredAccess
0x1800382bf  mov     rcx, rbx; lpFileName
0x1800382c2  call    cs:__imp_CreateFileW
0x1800382c8  mov     [rsp+0AD0h+var_A88], rax
0x1800382cd  mov     qword ptr [rsp+0AD0h+CreationTime.dwLowDateTime], 0
0x1800382d6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800382da  jz      loc_180038380
0x1800382e0  xor     r9d, r9d; lpLastWriteTime
0x1800382e3  xor     r8d, r8d; lpLastAccessTime
0x1800382e6  lea     rdx, [rsp+0AD0h+CreationTime]; lpCreationTime
0x1800382eb  mov     rcx, rax; hFile
0x1800382ee  call    cs:__imp_GetFileTime
0x1800382f4  xorps   xmm0, xmm0
0x1800382f7  movups  xmmword ptr [rbp+9D0h+SystemTime.wYear], xmm0
0x1800382fe  lea     rdx, [rbp+9D0h+SystemTime]; lpSystemTime
0x180038305  lea     rcx, [rsp+0AD0h+CreationTime]; lpFileTime
0x18003830a  call    cs:__imp_FileTimeToSystemTime
0x180038310  test    eax, eax
0x180038312  jz      short loc_180038380
0x180038314  movzx   eax, [rbp+9D0h+SystemTime.wSecond]
0x18003831b  movzx   ecx, [rbp+9D0h+SystemTime.wMinute]
0x180038322  movzx   edx, [rbp+9D0h+SystemTime.wHour]
0x180038329  movzx   r10d, [rbp+9D0h+SystemTime.wYear]
0x180038331  movzx   r9d, [rbp+9D0h+SystemTime.wDay]
0x180038339  movzx   r8d, [rbp+9D0h+SystemTime.wMonth]
0x180038341  mov     [rsp+0AD0h+var_A98], eax
0x180038345  mov     dword ptr [rsp+0AD0h+hTemplateFile], ecx
0x180038349  mov     [rsp+0AD0h+dwFlagsAndAttributes], edx
0x18003834d  mov     [rsp+0AD0h+dwCreationDisposition], r10d
0x180038352  lea     rdx, a02d02d04d02d02; "%02d/%02d/%04d %02d:%02d:%02d"
0x180038359  lea     rcx, [rbp+9D0h+var_840]
0x180038360  call    ?FormatWstring@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Utility::FormatWstring(ushort const *,...)
0x180038365  mov     rdx, rax
0x180038368  lea     rcx, [rbp+9D0h+var_880]
0x18003836f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180038374  lea     rcx, [rbp+9D0h+var_840]
0x18003837b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038380  lea     rcx, [rbp+9D0h+var_820]; this
0x180038387  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x18003838c  nop
0x18003838d  lea     r14, ??_7EpicGamesApplication@@6BIAmiInventoryTelemetryItem@@@; const EpicGamesApplication::`vftable'{for `IAmiInventoryTelemetryItem'}
0x180038394  mov     [rbp+9D0h+var_820], r14
0x18003839b  lea     rsi, ??_7AppvApplication@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const AppvApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x1800383a2  mov     [rbp+9D0h+var_818], rsi
0x1800383a9  lea     rbx, ??_7SteamApplication@@6B@; const SteamApplication::`vftable'
0x1800383b0  mov     [rbp+9D0h+var_810], rbx
0x1800383b7  lea     rax, [rbp+9D0h+Src]
0x1800383be  mov     qword ptr [rsp+0AD0h+dwFlagsAndAttributes], rax; __int64
0x1800383c3  lea     rax, [rbp+9D0h+var_880]
0x1800383ca  mov     qword ptr [rsp+0AD0h+dwCreationDisposition], rax; __int64
0x1800383cf  lea     r9, [rbp+9D0h+var_860]
0x1800383d6  lea     r8, [rbp+9D0h+var_8A0]
0x1800383dd  mov     rdx, r12; struct ConfigSettings *
0x1800383e0  lea     rcx, [rbp+9D0h+var_820]; this
0x1800383e7  call    ?GetSteamApplication@SteamApplication@@QEAAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; SteamApplication::GetSteamApplication(ConfigSettings const &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x1800383ec  nop
0x1800383ed  lea     rdx, [rbp+9D0h+var_820]; struct Application *
0x1800383f4  lea     rcx, [rbp+9D0h+var_430]; this
0x1800383fb  call    ??0Application@@QEAA@AEBV0@@Z; Application::Application(Application const &)
0x180038400  nop
0x180038401  mov     [rbp+9D0h+var_820], r14
0x180038408  mov     [rbp+9D0h+var_818], rsi
0x18003840f  mov     [rbp+9D0h+var_810], rbx
0x180038416  lea     rcx, [rbp+9D0h+var_820]; this
0x18003841d  call    ??1Application@@UEAA@XZ; Application::~Application(void)
0x180038422  mov     rax, [rdi+8]
0x180038426  cmp     rax, [rdi+10h]
0x18003842a  jz      loc_1800386F3
0x180038430  lea     rdx, [rbp+9D0h+var_430]; struct Application *
0x180038437  mov     rcx, rax; this
0x18003843a  call    ??0Application@@QEAA@AEBV0@@Z; Application::Application(Application const &)
0x18003843f  add     qword ptr [rdi+8], 3F0h
0x180038447  jmp     loc_180038706
  ... truncated ...
```
