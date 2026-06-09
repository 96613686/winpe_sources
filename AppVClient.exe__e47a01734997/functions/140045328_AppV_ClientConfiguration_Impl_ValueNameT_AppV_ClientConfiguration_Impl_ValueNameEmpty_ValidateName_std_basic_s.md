# AppV::ClientConfiguration::Impl::ValueNameT<AppV::ClientConfiguration::Impl::ValueNameEmpty>::ValidateName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,AppV::ClientConfiguration::ConfigurationType,bool &)

- ea: `0x140045328`
- end: `0x14004551d`
- name: `?ValidateName@?$ValueNameT@UValueNameEmpty@Impl@ClientConfiguration@AppV@@@Impl@ClientConfiguration@AppV@@QEAA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4ConfigurationType@34@AEA_N@Z`
- size: `501`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140042bc0`
- `0x140042c74`
- `0x140058258`

## callees

- `0x140004280`
- `0x140006304`
- `0x140018bec`
- `0x140042d28`
- `0x14004517c`
- `0x140045328`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140045395`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140045395`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400453be`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140045448`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400454c5`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400453be`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140045448`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400454c5`

## string_xrefs

- `0x1400453b7`: `admin\appman\appv\shared\clientconfiguration\ValueName.h`
- `0x1400453ce`: `admin\appman\appv\shared\clientconfiguration\ValueName.h`
- `0x140045441`: `admin\appman\appv\shared\clientconfiguration\ValueName.h`
- `0x140045458`: `admin\appman\appv\shared\clientconfiguration\ValueName.h`
- `0x1400454be`: `admin\appman\appv\shared\clientconfiguration\ValueName.h`
- `0x1400454d5`: `admin\appman\appv\shared\clientconfiguration\ValueName.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppV::ClientConfiguration::Impl::ValueNameT<AppV::ClientConfiguration::Impl::ValueNameEmpty>::ValidateName(
        __int64 a1,
        _QWORD *a2,
        int a3,
        _BYTE *a4)
{
  __int64 *i; // rbx
  __int64 *v8; // rdx
  _QWORD *v9; // rcx
  int v10; // ecx
  char *v11; // rax
  const char *v12; // rax
  unsigned __int64 FileId; // rax
  __int64 v14; // rcx
  char *v15; // rax
  const char *v16; // rax
  unsigned __int64 v17; // rbx
  char *v19; // rax
  const char *v20; // rax
  __int128 v21; // [rsp+20h] [rbp-50h] BYREF
  __int64 v22; // [rsp+30h] [rbp-40h]
  __int64 v23; // [rsp+38h] [rbp-38h]
  _OWORD v24[2]; // [rsp+40h] [rbp-30h] BYREF

  if ( a2[2] )
  {
    for ( i = *(__int64 **)(Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance() + 24);
          i != *(__int64 **)(Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance() + 32);
          i += 5 )
    {
      if ( (unsigned __int64)i[3] <= 7 )
        v8 = i;
      else
        v8 = (__int64 *)*i;
      if ( a2[3] <= 7u )
        v9 = a2;
      else
        v9 = (_QWORD *)*a2;
      if ( !(unsigned int)_o__wcsicmp(v9, v8) )
      {
        v10 = *((_DWORD *)i + 8);
        *a4 = *((_BYTE *)i + 37);
        if ( v10 != a3 )
        {
          v11 = strrchr("admin\\appman\\appv\\shared\\clientconfiguration\\ValueName.h", 92);
          if ( v11 )
            v12 = v11 + 1;
          else
            v12 = "admin\\appman\\appv\\shared\\clientconfiguration\\ValueName.h";
          FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v12);
          v14 = 0x60500040002LL;
          return v14 | (FileId << 52);
        }
        v24[0] = 0;
        v24[1] = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v24[0]) = 0;
        v21 = 0;
        v22 = 0;
        v23 = 7;
        LOWORD(v21) = 0;
        ((void (__fastcall *)(_QWORD *, _OWORD *, __int128 *, __int64))AppV::ClientConfiguration::Impl::RelativePathToValueAndKey)(
          a2,
          v24,
          &v21,
          2);
        if ( v22 )
        {
          std::wstring::~wstring((char **)&v21);
          std::wstring::~wstring((char **)v24);
          return 0x8000000000LL;
        }
        else
        {
          v15 = strrchr("admin\\appman\\appv\\shared\\clientconfiguration\\ValueName.h", 92);
          if ( v15 )
            v16 = v15 + 1;
          else
            v16 = "admin\\appman\\appv\\shared\\clientconfiguration\\ValueName.h";
          v17 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v16) << 52)
              | 0x60500040004LL;
          std::wstring::~wstring((char **)&v21);
          std::wstring::~wstring((char **)v24);
          return v17;
        }
      }
    }
  }
  v19 = strrchr("admin\\appman\\appv\\shared\\clientconfiguration\\ValueName.h", 92);
  if ( v19 )
    v20 = v19 + 1;
  else
    v20 = "admin\\appman\\appv\\shared\\clientconfiguration\\ValueName.h";
  FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v20);
  v14 = 0x50500040005LL;
  return v14 | (FileId << 52);
}

```

## disassembly

```asm
0x140045328  mov     [rsp-18h+arg_0], rbx
0x14004532d  mov     [rsp-18h+arg_10], rsi
0x140045332  push    rbp
0x140045333  push    rdi
0x140045334  push    r14
0x140045336  mov     rbp, rsp
0x140045339  sub     rsp, 70h
0x14004533d  mov     rax, cs:__security_cookie
0x140045344  xor     rax, rsp
0x140045347  mov     [rbp+var_10], rax
0x14004534b  mov     r14, r9
0x14004534e  mov     esi, r8d
0x140045351  mov     rdi, rdx
0x140045354  cmp     qword ptr [rdx+10h], 0
0x140045359  jz      loc_1400454B9
0x14004535f  call    ?Instance@?$Singleton@VConfigurationValuesClass@ClientConfiguration@AppV@@@@SAAEAVConfigurationValuesClass@ClientConfiguration@AppV@@XZ; Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance(void)
0x140045364  mov     rbx, [rax+18h]
0x140045368  call    ?Instance@?$Singleton@VConfigurationValuesClass@ClientConfiguration@AppV@@@@SAAEAVConfigurationValuesClass@ClientConfiguration@AppV@@XZ; Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance(void)
0x14004536d  cmp     rbx, [rax+20h]
0x140045371  jz      loc_1400454B9
0x140045377  cmp     qword ptr [rbx+18h], 7
0x14004537c  jbe     short loc_140045383
0x14004537e  mov     rdx, [rbx]
0x140045381  jmp     short loc_140045386
0x140045383  mov     rdx, rbx
0x140045386  cmp     qword ptr [rdi+18h], 7
0x14004538b  jbe     short loc_140045392
0x14004538d  mov     rcx, [rdi]
0x140045390  jmp     short loc_140045395
0x140045392  mov     rcx, rdi
0x140045395  call    cs:__imp__o__wcsicmp
0x14004539b  test    eax, eax
0x14004539d  jz      short loc_1400453A5
0x14004539f  add     rbx, 28h ; '('
0x1400453a3  jmp     short loc_140045368
0x1400453a5  mov     ecx, [rbx+20h]
0x1400453a8  mov     al, [rbx+25h]
0x1400453ab  mov     [r14], al
0x1400453ae  cmp     ecx, esi
0x1400453b0  jz      short loc_1400453F3
0x1400453b2  mov     edx, 5Ch ; '\'; Ch
0x1400453b7  lea     rcx, aAdminAppmanApp; "admin\\appman\\appv\\shared\\clientconf"...
0x1400453be  call    cs:__imp_strrchr
0x1400453c4  test    rax, rax
0x1400453c7  jz      short loc_1400453CE
0x1400453c9  inc     rax
0x1400453cc  jmp     short loc_1400453D5
0x1400453ce  lea     rax, aAdminAppmanApp; "admin\\appman\\appv\\shared\\clientconf"...
0x1400453d5  mov     rdx, rax; char *
0x1400453d8  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400453df  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400453e4  mov     rcx, 60500040002h
0x1400453ee  jmp     loc_1400454F5
0x1400453f3  xorps   xmm0, xmm0
0x1400453f6  movups  [rbp+var_30], xmm0
0x1400453fa  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140045402  movdqu  [rbp+var_20], xmm1
0x140045407  xor     eax, eax
0x140045409  mov     word ptr [rbp+var_30], ax
0x14004540d  movups  [rbp+var_50], xmm0
0x140045411  mov     [rbp+var_40], rax
0x140045415  mov     [rbp+var_38], 7
0x14004541d  mov     word ptr [rbp+var_50], ax
0x140045421  lea     r9d, [rax+2]
0x140045425  lea     r8, [rbp+var_50]
0x140045429  lea     rdx, [rbp+var_30]
0x14004542d  mov     rcx, rdi
0x140045430  call    ?RelativePathToValueAndKey@Impl@ClientConfiguration@AppV@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV45@1W4ConfigurationControlType@23@@Z; AppV::ClientConfiguration::Impl::RelativePathToValueAndKey(std::wstring const &,std::wstring &,std::wstring &,AppV::ClientConfiguration::ConfigurationControlType)
0x140045435  cmp     [rbp+var_40], 0
0x14004543a  jnz     short loc_14004549A
0x14004543c  mov     edx, 5Ch ; '\'; Ch
0x140045441  lea     rcx, aAdminAppmanApp; "admin\\appman\\appv\\shared\\clientconf"...
0x140045448  call    cs:__imp_strrchr
0x14004544e  test    rax, rax
0x140045451  jz      short loc_140045458
0x140045453  inc     rax
0x140045456  jmp     short loc_14004545F
0x140045458  lea     rax, aAdminAppmanApp; "admin\\appman\\appv\\shared\\clientconf"...
0x14004545f  mov     rdx, rax; char *
0x140045462  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140045469  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004546e  mov     rbx, rax
0x140045471  shl     rbx, 34h
0x140045475  mov     rax, 60500040004h
0x14004547f  or      rbx, rax
0x140045482  lea     rcx, [rbp+var_50]
0x140045486  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004548b  nop
0x14004548c  lea     rcx, [rbp+var_30]
0x140045490  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045495  mov     rax, rbx
0x140045498  jmp     short loc_1400454FC
0x14004549a  lea     rcx, [rbp+var_50]
0x14004549e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400454a3  nop
0x1400454a4  lea     rcx, [rbp+var_30]
0x1400454a8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400454ad  mov     rax, 8000000000h
0x1400454b7  jmp     short loc_1400454FC
0x1400454b9  mov     edx, 5Ch ; '\'; Ch
0x1400454be  lea     rcx, aAdminAppmanApp; "admin\\appman\\appv\\shared\\clientconf"...
0x1400454c5  call    cs:__imp_strrchr
0x1400454cb  test    rax, rax
0x1400454ce  jz      short loc_1400454D5
0x1400454d0  inc     rax
0x1400454d3  jmp     short loc_1400454DC
0x1400454d5  lea     rax, aAdminAppmanApp; "admin\\appman\\appv\\shared\\clientconf"...
0x1400454dc  mov     rdx, rax; char *
0x1400454df  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400454e6  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400454eb  mov     rcx, 50500040005h
0x1400454f5  shl     rax, 34h
0x1400454f9  or      rax, rcx
0x1400454fc  mov     rcx, [rbp+var_10]
0x140045500  xor     rcx, rsp; StackCookie
0x140045503  call    __security_check_cookie
0x140045508  lea     r11, [rsp+70h+var_s0]
0x14004550d  mov     rbx, [r11+20h]
0x140045511  mov     rsi, [r11+30h]
0x140045515  mov     rsp, r11
0x140045518  pop     r14
0x14004551a  pop     rdi
0x14004551b  pop     rbp
0x14004551c  retn
```
