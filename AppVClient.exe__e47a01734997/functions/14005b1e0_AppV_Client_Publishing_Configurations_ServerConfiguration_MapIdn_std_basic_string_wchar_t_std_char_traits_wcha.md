# AppV::Client::Publishing::Configurations::ServerConfiguration::MapIdn(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x14005b1e0`
- end: `0x14005b380`
- name: `?MapIdn@ServerConfiguration@Configurations@Publishing@Client@AppV@@AEAA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV67@@Z`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005ae3c`

## callees

- `0x140004280`
- `0x140006304`
- `0x1400165b4`
- `0x140018bec`
- `0x14001a100`
- `0x140020c60`
- `0x140041a60`
- `0x14005b1e0`
- `0x14005ba3c`
- `0x14005bb3c`
- `0x140064b6c`
- `0x140064c70`
- `0x140064ce4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14005b30b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14005b30b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005b256`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005b256`

## string_xrefs

- `0x14005b24f`: `admin\appman\appv\client\publishing\configurations\serverconfiguration.cpp`
- `0x14005b266`: `admin\appman\appv\client\publishing\configurations\serverconfiguration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppV::Client::Publishing::Configurations::ServerConfiguration::MapIdn(
        __int64 a1,
        const wchar_t *a2,
        char **a3)
{
  const wchar_t *v4; // rdi
  char *v5; // rax
  const char *v6; // rax
  unsigned __int64 FileId; // rax
  __int64 v8; // rbx
  __int64 *v10; // rdx
  const wchar_t *v11; // rcx
  bool v12; // bl
  char *v13[5]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v14[304]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v15; // [rsp+180h] [rbp+80h]

  v4 = a2;
  if ( !(unsigned __int8)softricity::shared::is_http_uri(a2) )
  {
    v10 = &softricity::shared::FILE_URL_PREFIX;
    if ( (unsigned __int64)qword_1400B1418 > 7 )
      v10 = (__int64 *)softricity::shared::FILE_URL_PREFIX;
    if ( *((_QWORD *)v4 + 3) <= 7u )
      v11 = v4;
    else
      v11 = *(const wchar_t **)v4;
    if ( (unsigned int)_o__wcsnicmp(v11, v10, qword_1400B1410) )
    {
      softricity::shared::get_drive_component(v13);
      v12 = v13[2] != 0;
      std::wstring::~wstring(v13);
      if ( !v12 && !(unsigned __int8)softricity::shared::is_unc_path_format(v4) )
        return 0;
    }
    std::wstring::operator=(a3, v4);
    return 0x8000000000LL;
  }
  CUrl::CUrl((CUrl *)v14);
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(const wchar_t **)v4;
  if ( CUrl::Crack((CUrl *)v14, v4) )
  {
    std::wstring::wstring((__int64)v13, (__int64)v14);
    std::wstring::operator=(a3, (__int64)v13);
    std::wstring::~wstring(v13);
    CUrl::~CUrl((CUrl *)v14);
    return 0x8000000000LL;
  }
  v5 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverconfiguration.cpp", 92);
  if ( v5 )
    v6 = v5 + 1;
  else
    v6 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverconfiguration.cpp";
  FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v6);
  v8 = v15 | (FileId << 52) | 0x142700000000LL;
  CUrl::~CUrl((CUrl *)v14);
  return v8;
}

```

## disassembly

```asm
0x14005b1e0  mov     [rsp-8+arg_0], rbx
0x14005b1e5  push    rbp
0x14005b1e6  push    rsi
0x14005b1e7  push    rdi
0x14005b1e8  lea     rbp, [rsp-0A0h]
0x14005b1f0  sub     rsp, 1A0h
0x14005b1f7  mov     rax, cs:__security_cookie
0x14005b1fe  xor     rax, rsp
0x14005b201  mov     [rbp+0B0h+var_20], rax
0x14005b208  mov     rsi, r8
0x14005b20b  mov     rdi, rdx
0x14005b20e  mov     rcx, rdx
0x14005b211  call    ?is_http_uri@shared@softricity@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; softricity::shared::is_http_uri(std::wstring const &)
0x14005b216  test    al, al
0x14005b218  jz      loc_14005B2DE
0x14005b21e  lea     rcx, [rsp+1B0h+var_160]; this
0x14005b223  call    ??0CUrl@@QEAA@XZ; CUrl::CUrl(void)
0x14005b228  nop
0x14005b229  cmp     qword ptr [rdi+18h], 7
0x14005b22e  jbe     short loc_14005B233
0x14005b230  mov     rdi, [rdi]
0x14005b233  mov     r8d, 90000000h; unsigned int
0x14005b239  mov     rdx, rdi; Str
0x14005b23c  lea     rcx, [rsp+1B0h+var_160]; this
0x14005b241  call    ?Crack@CUrl@@QEAA_NPEB_WK@Z; CUrl::Crack(wchar_t const *,ulong)
0x14005b246  test    al, al
0x14005b248  jnz     short loc_14005B2AB
0x14005b24a  mov     edx, 5Ch ; '\'; Ch
0x14005b24f  lea     rcx, aAdminAppmanApp_8; "admin\\appman\\appv\\client\\publishing"...
0x14005b256  call    cs:__imp_strrchr
0x14005b25c  test    rax, rax
0x14005b25f  jz      short loc_14005B266
0x14005b261  inc     rax
0x14005b264  jmp     short loc_14005B26D
0x14005b266  lea     rax, aAdminAppmanApp_8; "admin\\appman\\appv\\client\\publishing"...
0x14005b26d  mov     rdx, rax; char *
0x14005b270  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005b277  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005b27c  mov     rbx, rax
0x14005b27f  shl     rbx, 34h
0x14005b283  mov     ecx, [rbp+0B0h+var_30]
0x14005b289  or      rbx, rcx
0x14005b28c  mov     rax, 142700000000h
0x14005b296  or      rbx, rax
0x14005b299  lea     rcx, [rsp+1B0h+var_160]; this
0x14005b29e  call    ??1CUrl@@QEAA@XZ; CUrl::~CUrl(void)
0x14005b2a3  mov     rax, rbx
0x14005b2a6  jmp     loc_14005B35E
0x14005b2ab  lea     rdx, [rsp+1B0h+var_160]
0x14005b2b0  lea     rcx, [rsp+1B0h+var_188]
0x14005b2b5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14005b2ba  lea     rdx, [rsp+1B0h+var_188]
0x14005b2bf  mov     rcx, rsi
0x14005b2c2  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14005b2c7  lea     rcx, [rsp+1B0h+var_188]
0x14005b2cc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005b2d1  nop
0x14005b2d2  lea     rcx, [rsp+1B0h+var_160]; this
0x14005b2d7  call    ??1CUrl@@QEAA@XZ; CUrl::~CUrl(void)
0x14005b2dc  jmp     short loc_14005B354
0x14005b2de  lea     rdx, ?FILE_URL_PREFIX@shared@softricity@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const softricity::shared::FILE_URL_PREFIX
0x14005b2e5  cmp     cs:qword_1400B1418, 7
0x14005b2ed  cmova   rdx, cs:?FILE_URL_PREFIX@shared@softricity@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const softricity::shared::FILE_URL_PREFIX
0x14005b2f5  cmp     qword ptr [rdi+18h], 7
0x14005b2fa  jbe     short loc_14005B301
0x14005b2fc  mov     rcx, [rdi]
0x14005b2ff  jmp     short loc_14005B304
0x14005b301  mov     rcx, rdi
0x14005b304  mov     r8, cs:qword_1400B1410
0x14005b30b  call    cs:__imp__o__wcsnicmp
0x14005b311  test    eax, eax
0x14005b313  jz      short loc_14005B349
0x14005b315  mov     rdx, rdi
0x14005b318  lea     rcx, [rsp+1B0h+var_188]; void *
0x14005b31d  call    ?get_drive_component@shared@softricity@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@@Z; softricity::shared::get_drive_component(std::wstring const &)
0x14005b322  cmp     [rsp+1B0h+var_178], 0
0x14005b328  setnz   bl
0x14005b32b  lea     rcx, [rsp+1B0h+var_188]
0x14005b330  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005b335  test    bl, bl
0x14005b337  jnz     short loc_14005B349
0x14005b339  mov     rcx, rdi
0x14005b33c  call    ?is_unc_path_format@shared@softricity@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; softricity::shared::is_unc_path_format(std::wstring const &)
0x14005b341  test    al, al
0x14005b343  jnz     short loc_14005B349
0x14005b345  xor     eax, eax
0x14005b347  jmp     short loc_14005B35E
0x14005b349  mov     rdx, rdi
0x14005b34c  mov     rcx, rsi
0x14005b34f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14005b354  mov     rax, 8000000000h
0x14005b35e  mov     rcx, [rbp+0B0h+var_20]
0x14005b365  xor     rcx, rsp; StackCookie
0x14005b368  call    __security_check_cookie
0x14005b36d  mov     rbx, [rsp+1B0h+arg_0]
0x14005b375  add     rsp, 1A0h
0x14005b37c  pop     rdi
0x14005b37d  pop     rsi
0x14005b37e  pop     rbp
0x14005b37f  retn
```
