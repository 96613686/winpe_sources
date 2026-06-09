# Windows::Management::MdmSession::WaitAndListenToOmaDmSession(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800999d4`
- end: `0x180099c99`
- name: `?WaitAndListenToOmaDmSession@MdmSession@Management@Windows@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800993e0`

## callees

- `0x180004d50`
- `0x180005904`
- `0x18000a284`
- `0x18000a2a4`
- `0x18000d724`
- `0x180014af0`
- `0x180015e4c`
- `0x180015f40`
- `0x180015f70`
- `0x1800168d0`
- `0x18003446c`
- `0x180078f9c`
- `0x1800999d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180099b4b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180099b4b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180099b60`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180099b60`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099aa0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099b95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099b95`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180099aec`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180099aec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180099a5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180099a5b`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x180099b27`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x180099b27`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x180099b6b`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x180099b7b`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x180099baf`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x180099bbf`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x180099c0f`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x180099b6b`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x180099b7b`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x180099baf`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x180099bbf`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x180099c0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::Management::MdmSession::WaitAndListenToOmaDmSession()
{
  __int64 v0; // rdx
  const WCHAR *v1; // rax
  unsigned int v2; // ebx
  unsigned int v3; // ebx
  HANDLE EventW; // rbx
  const char *v5; // r9
  int v6; // eax
  unsigned int v7; // eax
  __int64 v8; // rax
  int InitiationInfo; // eax
  unsigned int v10; // edi
  DWORD v11; // eax
  signed int LastError; // eax
  const char *v13; // r9
  __int64 result; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-B8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-B8h]
  HANDLE v17; // [rsp+30h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-A0h] BYREF
  HKEY *p_hKey; // [rsp+40h] [rbp-98h] BYREF
  HKEY v20; // [rsp+48h] [rbp-90h] BYREF
  char v21; // [rsp+50h] [rbp-88h]
  _DWORD v22[16]; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v23[32]; // [rsp+A0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  std::wstring::wstring(v23);
  try
  {
    std::wstring::operator=(v23, v0);
    hKey = 0;
    p_hKey = &hKey;
    v20 = 0;
    v21 = 1;
    v1 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
    v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0x20019u, &v20);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v2 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xCF,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
             (const char *)v2,
             phkResult);
    }
    else
    {
      EventW = CreateEventW(0, 1, 0, 0);
      v17 = EventW;
      if ( EventW )
      {
        while ( 1 )
        {
          v7 = RegNotifyChangeKeyValue(hKey, 1, 0x10000005u, EventW, 1);
          if ( v7 )
          {
            v6 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0xDD,
                   (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
                   (const char *)v7,
                   phkResulta);
            goto LABEL_19;
          }
          memset_0(v22, 0, sizeof(v22));
          v22[0] = 64;
          v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
          InitiationInfo = OmaDmGetInitiationInfo(v8, v22);
          v10 = InitiationInfo;
          if ( InitiationInfo < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE2,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
              (const char *)(unsigned int)InitiationInfo,
              phkResulta);
            OmaDmFreeInitiationInfo(v22);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
            v3 = v10;
            goto LABEL_21;
          }
          if ( (unsigned int)(v22[5] - 5) <= 1 )
          {
            OmaDmFreeInitiationInfo(v22);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            std::wstring::~wstring(v23);
            return 0;
          }
          v11 = WaitForSingleObject(EventW, 0x36EE80u);
          if ( v11 == -1 )
            break;
          if ( v11 == 258 )
          {
            OmaDmFreeInitiationInfo(v22);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
            v3 = -2147023436;
            goto LABEL_21;
          }
          ResetEvent(EventW);
          OmaDmFreeInitiationInfo(v22);
        }
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        OmaDmFreeInitiationInfo(v22);
      }
      else
      {
        v6 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xD2,
               (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
               v5);
LABEL_19:
        v3 = v6;
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
    }
LABEL_21:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::~wstring(v23);
    result = v3;
  }
  catch ( ... )
  {
    LODWORD(v17) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xC6,
                     (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
                     v13);
    std::wstring::~wstring(v23);
    return (unsigned int)v17;
  }
  return result;
}

```

## disassembly

```asm
0x1800999d4  mov     r11, rsp
0x1800999d7  mov     [r11+10h], rbx
0x1800999db  push    rdi
0x1800999dc  sub     rsp, 0D0h
0x1800999e3  mov     rax, cs:__security_cookie
0x1800999ea  xor     rax, rsp
0x1800999ed  mov     [rsp+0D8h+var_18], rax
0x1800999f5  mov     rdx, rcx
0x1800999f8  lea     rcx, [r11-38h]
0x1800999fc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180099a01  nop
0x180099a02  lea     rcx, [rsp+0D8h+var_38]
0x180099a0a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180099a0f  nop
0x180099a10  mov     [rsp+0D8h+hKey], 0
0x180099a19  lea     rax, [rsp+0D8h+hKey]
0x180099a1e  mov     [rsp+0D8h+var_98], rax
0x180099a23  mov     [rsp+0D8h+var_90], 0
0x180099a2c  mov     [rsp+0D8h+var_88], 1
0x180099a31  lea     rcx, [rsp+0D8h+var_38]
0x180099a39  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180099a3e  mov     rdx, rax; lpSubKey
0x180099a41  lea     rax, [rsp+0D8h+var_90]
0x180099a46  mov     qword ptr [rsp+0D8h+phkResult], rax; unsigned int
0x180099a4b  mov     r9d, 20019h; samDesired
0x180099a51  xor     r8d, r8d; ulOptions
0x180099a54  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180099a5b  call    cs:__imp_RegOpenKeyExW
0x180099a61  mov     ebx, eax
0x180099a63  lea     rcx, [rsp+0D8h+var_98]
0x180099a68  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180099a6d  test    ebx, ebx
0x180099a6f  jz      short loc_180099A94
0x180099a71  mov     rcx, [rsp+0D8h]; this
0x180099a79  mov     r9d, ebx; char *
0x180099a7c  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x180099a83  mov     edx, 0CFh; void *
0x180099a88  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180099a8d  mov     ebx, eax
0x180099a8f  jmp     loc_180099C4B
0x180099a94  xor     r9d, r9d; lpName
0x180099a97  xor     r8d, r8d; bInitialState
0x180099a9a  lea     edx, [r9+1]; bManualReset
0x180099a9e  xor     ecx, ecx; lpEventAttributes
0x180099aa0  call    cs:__imp_CreateEventW
0x180099aa6  mov     rbx, rax
0x180099aa9  mov     [rsp+0D8h+var_A8], rax
0x180099aae  test    rax, rax
0x180099ab1  jnz     short loc_180099AD1
0x180099ab3  mov     rcx, [rsp+0D8h]; this
0x180099abb  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x180099ac2  mov     edx, 0D2h; void *
0x180099ac7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180099acc  jmp     loc_180099C3F
0x180099ad1  mov     [rsp+0D8h+phkResult], 1; unsigned int
0x180099ad9  mov     r9, rbx; hEvent
0x180099adc  mov     edx, 1; bWatchSubtree
0x180099ae1  mov     r8d, 10000005h; dwNotifyFilter
0x180099ae7  mov     rcx, [rsp+0D8h+hKey]; hKey
0x180099aec  call    cs:__imp_RegNotifyChangeKeyValue
0x180099af2  test    eax, eax
0x180099af4  jnz     loc_180099C23
0x180099afa  xor     edx, edx; Val
0x180099afc  lea     r8d, [rax+40h]; Size
0x180099b00  lea     rcx, [rsp+0D8h+var_78]; void *
0x180099b05  call    memset_0
0x180099b0a  mov     [rsp+0D8h+var_78], 40h ; '@'
0x180099b12  lea     rcx, [rsp+0D8h+var_38]
0x180099b1a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180099b1f  mov     rcx, rax
0x180099b22  lea     rdx, [rsp+0D8h+var_78]
0x180099b27  call    cs:__imp_OmaDmGetInitiationInfo
0x180099b2d  mov     edi, eax
0x180099b2f  test    eax, eax
0x180099b31  js      loc_180099BEE
0x180099b37  mov     eax, [rsp+0D8h+var_64]
0x180099b3b  add     eax, 0FFFFFFFBh
0x180099b3e  cmp     eax, 1
0x180099b41  jbe     short loc_180099BBA
0x180099b43  mov     edx, 36EE80h; dwMilliseconds
0x180099b48  mov     rcx, rbx; hHandle
0x180099b4b  call    cs:__imp_WaitForSingleObject
0x180099b51  cmp     eax, 0FFFFFFFFh
0x180099b54  jz      short loc_180099B95
0x180099b56  cmp     eax, 102h
0x180099b5b  jz      short loc_180099B76
0x180099b5d  mov     rcx, rbx; hEvent
0x180099b60  call    cs:__imp_ResetEvent
0x180099b66  lea     rcx, [rsp+0D8h+var_78]
0x180099b6b  call    cs:__imp_OmaDmFreeInitiationInfo
0x180099b71  jmp     loc_180099AD1
0x180099b76  lea     rcx, [rsp+0D8h+var_78]
0x180099b7b  call    cs:__imp_OmaDmFreeInitiationInfo
0x180099b81  lea     rcx, [rsp+0D8h+var_A8]
0x180099b86  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180099b8b  mov     ebx, 800705B4h
0x180099b90  jmp     loc_180099C4B
0x180099b95  call    cs:__imp_GetLastError
0x180099b9b  mov     ebx, eax
0x180099b9d  test    eax, eax
0x180099b9f  jle     short loc_180099BAA
0x180099ba1  movzx   ebx, ax
0x180099ba4  or      ebx, 80070000h
0x180099baa  lea     rcx, [rsp+0D8h+var_78]
0x180099baf  call    cs:__imp_OmaDmFreeInitiationInfo
0x180099bb5  jmp     loc_180099C41
0x180099bba  lea     rcx, [rsp+0D8h+var_78]
0x180099bbf  call    cs:__imp_OmaDmFreeInitiationInfo
0x180099bc5  lea     rcx, [rsp+0D8h+var_A8]
0x180099bca  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180099bcf  lea     rcx, [rsp+0D8h+hKey]
0x180099bd4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180099bd9  nop
0x180099bda  lea     rcx, [rsp+0D8h+var_38]
0x180099be2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180099be7  xor     eax, eax
0x180099be9  jmp     loc_180099C78
0x180099bee  mov     rcx, [rsp+0D8h]; this
0x180099bf6  mov     r9d, edi; char *
0x180099bf9  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x180099c00  mov     edx, 0E2h; void *
0x180099c05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099c0a  lea     rcx, [rsp+0D8h+var_78]
0x180099c0f  call    cs:__imp_OmaDmFreeInitiationInfo
0x180099c15  lea     rcx, [rsp+0D8h+var_A8]
0x180099c1a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180099c1f  mov     ebx, edi
0x180099c21  jmp     short loc_180099C4B
0x180099c23  mov     rcx, [rsp+0D8h]; this
0x180099c2b  mov     r9d, eax; char *
0x180099c2e  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x180099c35  mov     edx, 0DDh; void *
0x180099c3a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180099c3f  mov     ebx, eax
0x180099c41  lea     rcx, [rsp+0D8h+var_A8]
0x180099c46  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180099c4b  lea     rcx, [rsp+0D8h+hKey]
0x180099c50  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180099c55  nop
0x180099c56  lea     rcx, [rsp+0D8h+var_38]
0x180099c5e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180099c63  mov     eax, ebx
0x180099c65  jmp     short loc_180099C78
0x180099c67  lea     rcx, [rsp+0D8h+var_38]
0x180099c6f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180099c74  mov     eax, dword ptr [rsp+0D8h+var_A8]
0x180099c78  mov     rcx, [rsp+0D8h+var_18]
0x180099c80  xor     rcx, rsp; StackCookie
0x180099c83  call    __security_check_cookie
0x180099c88  mov     rbx, [rsp+0D8h+arg_8]
0x180099c90  add     rsp, 0D0h
0x180099c97  pop     rdi
0x180099c98  retn
```
