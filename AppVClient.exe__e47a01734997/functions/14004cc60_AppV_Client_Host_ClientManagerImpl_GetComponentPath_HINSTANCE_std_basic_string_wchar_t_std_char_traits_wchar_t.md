# AppV::Client::Host::ClientManagerImpl::GetComponentPath(HINSTANCE__ *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x14004cc60`
- end: `0x14004cf81`
- name: `?GetComponentPath@ClientManagerImpl@Host@Client@AppV@@MEBA_KPEAUHINSTANCE__@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `801`
- prototype: `unsigned __int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x140004280`
- `0x140006061`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140007404`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14003c034`
- `0x14003c414`
- `0x14003c5d4`
- `0x14003c660`
- `0x140040884`
- `0x1400417bc`
- `0x14004cc60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004cd58`
- `KERNEL32!GetLastError` at `0x14004cd58`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004ce3c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004cf26`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004ce3c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004cf26`

## string_xrefs

- `0x14004ce35`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004ce4c`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004cf1f`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004cf36`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004cd93`: `failed to get current module path, error = %1%`
- `0x14004cd62`: `AppV::Client::Host::ClientManagerImpl::GetComponentPath`

## pseudocode

```c
unsigned __int64 __fastcall AppV::Client::Host::ClientManagerImpl::GetComponentPath(__int64 a1, __int64 a2, _QWORD *a3)
{
  _WORD *v6; // rcx
  __int64 *v7; // r8
  __int64 *v8; // rcx
  __int64 *v9; // rsi
  __int64 *v10; // rax
  __int64 ModuleFileName; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rbx
  char *v15; // rax
  const char *v16; // rax
  unsigned __int64 FileId; // rax
  __int64 v18; // rbx
  __int64 last_of; // rax
  __int64 v21; // r8
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rax
  void **v24; // r9
  char *v25; // r14
  __int64 v26; // rbx
  char *v27; // rax
  const char *v28; // rax
  DWORD LastError; // [rsp+20h] [rbp-89h] BYREF
  void *Src[2]; // [rsp+28h] [rbp-81h] BYREF
  __int128 v31; // [rsp+38h] [rbp-71h]
  _OWORD v32[2]; // [rsp+48h] [rbp-61h] BYREF
  _OWORD v33[2]; // [rsp+68h] [rbp-41h] BYREF
  _BYTE v34[32]; // [rsp+88h] [rbp-21h] BYREF
  int v35; // [rsp+A8h] [rbp-1h]
  void **v36; // [rsp+B0h] [rbp+7h] BYREF
  _BYTE v37[32]; // [rsp+C0h] [rbp+17h] BYREF

  a3[2] = 0;
  if ( a3[3] <= 7u )
    v6 = a3;
  else
    v6 = (_WORD *)*a3;
  *v6 = 0;
  v7 = **(__int64 ***)(a1 + 8);
  v8 = (__int64 *)v7[1];
  HIDWORD(v33[0]) = 0;
  v9 = v7;
  if ( !*((_BYTE *)v8 + 25) )
  {
    do
    {
      if ( *((int *)v8 + 8) >= 1 )
        v9 = v8;
      v10 = v8 + 2;
      if ( *((int *)v8 + 8) >= 1 )
        v10 = v8;
      v8 = (__int64 *)*v10;
    }
    while ( !*(_BYTE *)(*v10 + 25) );
  }
  if ( *((_BYTE *)v9 + 25) || *((int *)v9 + 8) > 1 || v7 == v9 )
  {
    v27 = strrchr("admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp", 92);
    if ( v27 )
      v28 = v27 + 1;
    else
      v28 = "admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp";
    return (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v28) << 52)
         | 0x190E00000103LL;
  }
  else
  {
    ModuleFileName = AppUtils::getModuleFileName(v32, a2);
    *(_OWORD *)Src = 0;
    v31 = 0u;
    *(_OWORD *)Src = *(_OWORD *)ModuleFileName;
    v31 = *(_OWORD *)(ModuleFileName + 16);
    *(_QWORD *)(ModuleFileName + 16) = 0;
    *(_QWORD *)(ModuleFileName + 24) = 7;
    *(_WORD *)ModuleFileName = 0;
    std::wstring::~wstring(v32);
    if ( (_QWORD)v31 )
    {
      last_of = std::wstring::find_last_of(Src);
      if ( last_of != -1 )
      {
        v22 = v31;
        v23 = last_of + 1;
        if ( (unsigned __int64)v31 >= v23 )
          v22 = v23;
        v24 = Src;
        if ( *((_QWORD *)&v31 + 1) > 7u )
          v24 = (void **)Src[0];
        if ( v22 > a3[3] )
        {
          std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(a3, v22, v21, v24);
        }
        else
        {
          if ( a3[3] <= 7u )
            v25 = (char *)a3;
          else
            v25 = (char *)*a3;
          a3[2] = v22;
          v26 = 2 * v22;
          memmove_0(v25, v24, 2 * v22);
          *(_WORD *)&v25[v26] = 0;
        }
        std::wstring::append(a3);
      }
      std::wstring::~wstring(Src);
      return 0x8000000000LL;
    }
    else
    {
      LastError = GetLastError();
      std::string::string(v34, "AppV::Client::Host::ClientManagerImpl::GetComponentPath");
      v35 = 208;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
      memset(v32, 0, sizeof(v32));
      std::wstring::_Construct<1,wchar_t const *>(v32, L"failed to get current module path, error = %1%", 46);
      v13 = AppV::Log::fmt(v12, &v36, v32);
      v14 = AppV::LogFormatter::operator%<unsigned long>(v13, &LastError);
      memset(v33, 0, sizeof(v33));
      std::wstring::_Construct<1,wchar_t const *>(v33, L"Client", 6);
      AppV::DecoratedLog::operator()(v34, 1, v33, v14);
      std::wstring::~wstring(v33);
      v36 = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v37);
      std::wstring::~wstring(v32);
      std::string::~string(v34);
      v15 = strrchr("admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp", 92);
      if ( v15 )
        v16 = v15 + 1;
      else
        v16 = "admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp";
      FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v16);
      v18 = LastError | (FileId << 52) | 0x1A2E00000000LL;
      std::wstring::~wstring(Src);
      return v18;
    }
  }
}

```

## disassembly

```asm
0x14004cc60  mov     [rsp-8+arg_0], rbx
0x14004cc65  mov     [rsp-8+arg_18], rsi
0x14004cc6a  push    rbp
0x14004cc6b  push    rdi
0x14004cc6c  push    r14
0x14004cc6e  lea     rbp, [rsp-47h]
0x14004cc73  sub     rsp, 0F0h
0x14004cc7a  mov     rax, cs:__security_cookie
0x14004cc81  xor     rax, rsp
0x14004cc84  mov     [rbp+57h+var_20], rax
0x14004cc88  mov     rdi, r8
0x14004cc8b  mov     r9, rdx
0x14004cc8e  mov     rdx, rcx
0x14004cc91  mov     qword ptr [r8+10h], 0
0x14004cc99  mov     ebx, 7
0x14004cc9e  cmp     [r8+18h], rbx
0x14004cca2  jbe     short loc_14004CCA9
0x14004cca4  mov     rcx, [r8]
0x14004cca7  jmp     short loc_14004CCAC
0x14004cca9  mov     rcx, rdi
0x14004ccac  xor     eax, eax
0x14004ccae  mov     [rcx], ax
0x14004ccb1  mov     rax, [rdx+8]
0x14004ccb5  mov     r8, [rax]
0x14004ccb8  mov     rcx, [r8+8]
0x14004ccbc  xor     eax, eax
0x14004ccbe  mov     dword ptr [rbp+57h+var_98+0Ch], eax
0x14004ccc1  mov     rsi, r8
0x14004ccc4  cmp     [rcx+19h], al
0x14004ccc7  jnz     short loc_14004CCE2
0x14004ccc9  cmp     dword ptr [rcx+20h], 1
0x14004cccd  cmovge  rsi, rcx
0x14004ccd1  lea     rax, [rcx+10h]
0x14004ccd5  cmovge  rax, rcx
0x14004ccd9  mov     rcx, [rax]
0x14004ccdc  cmp     byte ptr [rcx+19h], 0
0x14004cce0  jz      short loc_14004CCC9
0x14004cce2  cmp     byte ptr [rsi+19h], 0
0x14004cce6  jnz     loc_14004CF1A
0x14004ccec  cmp     dword ptr [rsi+20h], 1
0x14004ccf0  jg      loc_14004CF1A
0x14004ccf6  cmp     r8, rsi
0x14004ccf9  jz      loc_14004CF1A
0x14004ccff  mov     rdx, r9
0x14004cd02  lea     rcx, [rbp+57h+var_B8]
0x14004cd06  call    ?getModuleFileName@AppUtils@@SA?AV?$extended_string@_W@shared@softricity@@PEAUHINSTANCE__@@@Z; AppUtils::getModuleFileName(HINSTANCE__ *)
0x14004cd0b  xorps   xmm0, xmm0
0x14004cd0e  movups  xmmword ptr [rsp+100h+Src], xmm0
0x14004cd13  mov     qword ptr [rbp+57h+var_C8], 0
0x14004cd1b  mov     qword ptr [rbp+57h+var_C8+8], 0
0x14004cd23  movups  xmm0, xmmword ptr [rax]
0x14004cd26  movups  xmmword ptr [rsp+100h+Src], xmm0
0x14004cd2b  movups  xmm1, xmmword ptr [rax+10h]
0x14004cd2f  movups  [rbp+57h+var_C8], xmm1
0x14004cd33  mov     qword ptr [rax+10h], 0
0x14004cd3b  mov     [rax+18h], rbx
0x14004cd3f  xor     ecx, ecx
0x14004cd41  mov     [rax], cx
0x14004cd44  lea     rcx, [rbp+57h+var_B8]
0x14004cd48  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004cd4d  cmp     qword ptr [rbp+57h+var_C8], 0
0x14004cd52  jnz     loc_14004CE8F
0x14004cd58  call    cs:__imp_GetLastError
0x14004cd5e  mov     [rsp+100h+var_E0], eax
0x14004cd62  lea     rdx, aAppvClientHost_8; "AppV::Client::Host::ClientManagerImpl::"...
0x14004cd69  lea     rcx, [rbp+57h+var_78]
0x14004cd6d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004cd72  mov     [rbp+57h+var_58], 0D0h
0x14004cd79  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004cd7e  xorps   xmm0, xmm0
0x14004cd81  movups  [rbp+57h+var_B8], xmm0
0x14004cd85  xorps   xmm1, xmm1
0x14004cd88  movdqu  [rbp+57h+var_A8], xmm1
0x14004cd8d  mov     r8d, 2Eh ; '.'
0x14004cd93  lea     rdx, aFailedToGetCur; "failed to get current module path, erro"...
0x14004cd9a  lea     rcx, [rbp+57h+var_B8]
0x14004cd9e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004cda3  nop
0x14004cda4  lea     r8, [rbp+57h+var_B8]
0x14004cda8  lea     rdx, [rbp+57h+var_50]
0x14004cdac  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004cdb1  nop
0x14004cdb2  lea     rdx, [rsp+100h+var_E0]
0x14004cdb7  mov     rcx, rax
0x14004cdba  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004cdbf  mov     rbx, rax
0x14004cdc2  xorps   xmm0, xmm0
0x14004cdc5  movups  [rbp+57h+var_98], xmm0
0x14004cdc9  xorps   xmm1, xmm1
0x14004cdcc  movdqu  [rbp+57h+var_88], xmm1
0x14004cdd1  mov     r8d, 6
0x14004cdd7  lea     rdx, aClient; "Client"
0x14004cdde  lea     rcx, [rbp+57h+var_98]
0x14004cde2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004cde7  nop
0x14004cde8  mov     r9, rbx
0x14004cdeb  lea     r8, [rbp+57h+var_98]
0x14004cdef  mov     edx, 1
0x14004cdf4  lea     rcx, [rbp+57h+var_78]
0x14004cdf8  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004cdfd  nop
0x14004cdfe  lea     rcx, [rbp+57h+var_98]
0x14004ce02  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ce07  nop
0x14004ce08  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004ce0f  mov     [rbp+57h+var_50], rax
0x14004ce13  lea     rcx, [rbp+57h+var_40]
0x14004ce17  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ce1c  nop
0x14004ce1d  lea     rcx, [rbp+57h+var_B8]
0x14004ce21  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ce26  nop
0x14004ce27  lea     rcx, [rbp+57h+var_78]
0x14004ce2b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004ce30  mov     edx, 5Ch ; '\'; Ch
0x14004ce35  lea     rcx, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004ce3c  call    cs:__imp_strrchr
0x14004ce42  test    rax, rax
0x14004ce45  jz      short loc_14004CE4C
0x14004ce47  inc     rax
0x14004ce4a  jmp     short loc_14004CE53
0x14004ce4c  lea     rax, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004ce53  mov     rdx, rax; char *
0x14004ce56  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004ce5d  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004ce62  mov     rbx, rax
0x14004ce65  shl     rbx, 34h
0x14004ce69  mov     ecx, [rsp+100h+var_E0]
0x14004ce6d  or      rbx, rcx
0x14004ce70  mov     rax, 1A2E00000000h
0x14004ce7a  or      rbx, rax
0x14004ce7d  lea     rcx, [rsp+100h+Src]
0x14004ce82  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ce87  mov     rax, rbx
0x14004ce8a  jmp     loc_14004CF5D
0x14004ce8f  lea     rcx, [rsp+100h+Src]
0x14004ce94  call    ?find_last_of@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_K_W_K@Z; std::wstring::find_last_of(wchar_t,unsigned __int64)
0x14004ce99  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004ce9d  jz      short loc_14004CF04
0x14004ce9f  mov     rdx, qword ptr [rbp+57h+var_C8]
0x14004cea3  inc     rax
0x14004cea6  cmp     rdx, rax
0x14004cea9  cmovnb  rdx, rax
0x14004cead  lea     r9, [rsp+100h+Src]
0x14004ceb2  cmp     qword ptr [rbp+57h+var_C8+8], rbx
0x14004ceb6  cmova   r9, [rsp+100h+Src]
0x14004cebc  cmp     rdx, [rdi+18h]
0x14004cec0  ja      short loc_14004CEEF
0x14004cec2  cmp     [rdi+18h], rbx
0x14004cec6  jbe     short loc_14004CECD
0x14004cec8  mov     r14, [rdi]
0x14004cecb  jmp     short loc_14004CED0
0x14004cecd  mov     r14, rdi
0x14004ced0  mov     [rdi+10h], rdx
0x14004ced4  lea     rbx, [rdx+rdx]
0x14004ced8  mov     r8, rbx; Size
0x14004cedb  mov     rdx, r9; Src
0x14004cede  mov     rcx, r14; void *
0x14004cee1  call    memmove_0
0x14004cee6  xor     eax, eax
0x14004cee8  mov     [rbx+r14], ax
0x14004ceed  jmp     short loc_14004CEF7
0x14004ceef  mov     rcx, rdi
0x14004cef2  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x14004cef7  lea     rdx, [rsi+28h]
0x14004cefb  mov     rcx, rdi; Src
0x14004cefe  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x14004cf03  nop
0x14004cf04  lea     rcx, [rsp+100h+Src]
0x14004cf09  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004cf0e  mov     rax, 8000000000h
0x14004cf18  jmp     short loc_14004CF5D
0x14004cf1a  mov     edx, 5Ch ; '\'; Ch
0x14004cf1f  lea     rcx, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004cf26  call    cs:__imp_strrchr
0x14004cf2c  test    rax, rax
0x14004cf2f  jz      short loc_14004CF36
0x14004cf31  inc     rax
0x14004cf34  jmp     short loc_14004CF3D
0x14004cf36  lea     rax, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004cf3d  mov     rdx, rax; char *
0x14004cf40  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004cf47  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004cf4c  shl     rax, 34h
0x14004cf50  mov     rcx, 190E00000103h
0x14004cf5a  or      rax, rcx
0x14004cf5d  mov     rcx, [rbp+57h+var_20]
0x14004cf61  xor     rcx, rsp; StackCookie
0x14004cf64  call    __security_check_cookie
0x14004cf69  lea     r11, [rsp+100h+var_10]
0x14004cf71  mov     rbx, [r11+20h]
0x14004cf75  mov     rsi, [r11+38h]
0x14004cf79  mov     rsp, r11
0x14004cf7c  pop     r14
0x14004cf7e  pop     rdi
0x14004cf7f  pop     rbp
0x14004cf80  retn
```
