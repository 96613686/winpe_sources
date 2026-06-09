# Windows::Management::MdmSession::WaitAndListenToOmaDmSession(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18009c5bc`
- end: `0x18009c8ce`
- name: `?WaitAndListenToOmaDmSession@MdmSession@Management@Windows@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18009bf90`

## callees

- `0x180004eb0`
- `0x180005a74`
- `0x18000a5a4`
- `0x18000a5c4`
- `0x18000dc18`
- `0x1800151e0`
- `0x18001656c`
- `0x180016668`
- `0x180016698`
- `0x180017024`
- `0x180033500`
- `0x18007a7a0`
- `0x18009c5bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009c68e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009c68e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18009c76a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18009c76a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009c74f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009c74f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c7b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c7b1`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18009c6e0`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18009c6e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009c643`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009c643`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x18009c721`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x18009c721`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x18009c77b`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x18009c791`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x18009c7d1`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x18009c7e7`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x18009c83d`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x18009c77b`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x18009c791`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x18009c7d1`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x18009c7e7`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x18009c83d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::Management::MdmSession::WaitAndListenToOmaDmSession()
{
  const WCHAR *v0; // rax
  unsigned int v1; // ebx
  unsigned int v2; // ebx
  HANDLE EventW; // rbx
  const char *v4; // r9
  int v5; // eax
  unsigned int v6; // eax
  __int64 v7; // rax
  int InitiationInfo; // eax
  unsigned int v9; // edi
  DWORD v10; // eax
  signed int LastError; // eax
  const char *v12; // r9
  __int64 result; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-B8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-B8h]
  HANDLE v16; // [rsp+30h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-A0h] BYREF
  HKEY *p_hKey; // [rsp+40h] [rbp-98h] BYREF
  HKEY v19; // [rsp+48h] [rbp-90h] BYREF
  char v20; // [rsp+50h] [rbp-88h]
  _DWORD v21[16]; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v22[32]; // [rsp+A0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  std::wstring::wstring(v22);
  try
  {
    std::wstring::operator=(v22);
    hKey = 0;
    p_hKey = &hKey;
    v19 = 0;
    v20 = 1;
    v0 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
    v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v0, 0, 0x20019u, &v19);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v1 )
    {
      v2 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xCF,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
             (const char *)v1,
             phkResult);
    }
    else
    {
      EventW = CreateEventW(0, 1, 0, 0);
      v16 = EventW;
      if ( EventW )
      {
        while ( 1 )
        {
          v6 = RegNotifyChangeKeyValue(hKey, 1, 0x10000005u, EventW, 1);
          if ( v6 )
          {
            v5 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0xDD,
                   (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
                   (const char *)v6,
                   phkResulta);
            goto LABEL_19;
          }
          memset_0(v21, 0, sizeof(v21));
          v21[0] = 64;
          v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
          InitiationInfo = OmaDmGetInitiationInfo(v7, v21);
          v9 = InitiationInfo;
          if ( InitiationInfo < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE2,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
              (const char *)(unsigned int)InitiationInfo,
              phkResulta);
            OmaDmFreeInitiationInfo(v21);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
            v2 = v9;
            goto LABEL_21;
          }
          if ( (unsigned int)(v21[5] - 5) <= 1 )
          {
            OmaDmFreeInitiationInfo(v21);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            std::wstring::~wstring(v22);
            return 0;
          }
          v10 = WaitForSingleObject(EventW, 0x36EE80u);
          if ( v10 == -1 )
            break;
          if ( v10 == 258 )
          {
            OmaDmFreeInitiationInfo(v21);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
            v2 = -2147023436;
            goto LABEL_21;
          }
          ResetEvent(EventW);
          OmaDmFreeInitiationInfo(v21);
        }
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        OmaDmFreeInitiationInfo(v21);
      }
      else
      {
        v5 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xD2,
               (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
               v4);
LABEL_19:
        v2 = v5;
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
    }
LABEL_21:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::~wstring(v22);
    result = v2;
  }
  catch ( ... )
  {
    LODWORD(v16) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xC6,
                     (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
                     v12);
    std::wstring::~wstring(v22);
    return (unsigned int)v16;
  }
  return result;
}

```

## disassembly

```asm
0x18009c5bc  mov     r11, rsp
0x18009c5bf  mov     [r11+10h], rbx
0x18009c5c3  push    rdi
0x18009c5c4  sub     rsp, 0D0h
0x18009c5cb  mov     rax, cs:__security_cookie
0x18009c5d2  xor     rax, rsp
0x18009c5d5  mov     [rsp+0D8h+var_18], rax
0x18009c5dd  mov     rdx, rcx
0x18009c5e0  lea     rcx, [r11-38h]
0x18009c5e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009c5e9  nop
0x18009c5ea  lea     rcx, [rsp+0D8h+var_38]
0x18009c5f2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18009c5f7  nop
0x18009c5f8  mov     [rsp+0D8h+hKey], 0
0x18009c601  lea     rax, [rsp+0D8h+hKey]
0x18009c606  mov     [rsp+0D8h+var_98], rax
0x18009c60b  mov     [rsp+0D8h+var_90], 0
0x18009c614  mov     [rsp+0D8h+var_88], 1
0x18009c619  lea     rcx, [rsp+0D8h+var_38]
0x18009c621  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009c626  mov     rdx, rax; lpSubKey
0x18009c629  lea     rax, [rsp+0D8h+var_90]
0x18009c62e  mov     qword ptr [rsp+0D8h+phkResult], rax; unsigned int
0x18009c633  mov     r9d, 20019h; samDesired
0x18009c639  xor     r8d, r8d; ulOptions
0x18009c63c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009c643  call    cs:__imp_RegOpenKeyExW
0x18009c64a  nop     dword ptr [rax+rax+00h]
0x18009c64f  mov     ebx, eax
0x18009c651  lea     rcx, [rsp+0D8h+var_98]
0x18009c656  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18009c65b  test    ebx, ebx
0x18009c65d  jz      short loc_18009C682
0x18009c65f  mov     rcx, [rsp+0D8h]; this
0x18009c667  mov     r9d, ebx; char *
0x18009c66a  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009c671  mov     edx, 0CFh; void *
0x18009c676  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009c67b  mov     ebx, eax
0x18009c67d  jmp     loc_18009C87F
0x18009c682  xor     r9d, r9d; lpName
0x18009c685  xor     r8d, r8d; bInitialState
0x18009c688  lea     edx, [r9+1]; bManualReset
0x18009c68c  xor     ecx, ecx; lpEventAttributes
0x18009c68e  call    cs:__imp_CreateEventW
0x18009c695  nop     dword ptr [rax+rax+00h]
0x18009c69a  mov     rbx, rax
0x18009c69d  mov     [rsp+0D8h+var_A8], rax
0x18009c6a2  test    rax, rax
0x18009c6a5  jnz     short loc_18009C6C5
0x18009c6a7  mov     rcx, [rsp+0D8h]; this
0x18009c6af  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009c6b6  mov     edx, 0D2h; void *
0x18009c6bb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009c6c0  jmp     loc_18009C873
0x18009c6c5  mov     [rsp+0D8h+phkResult], 1; unsigned int
0x18009c6cd  mov     r9, rbx; hEvent
0x18009c6d0  mov     edx, 1; bWatchSubtree
0x18009c6d5  mov     r8d, 10000005h; dwNotifyFilter
0x18009c6db  mov     rcx, [rsp+0D8h+hKey]; hKey
0x18009c6e0  call    cs:__imp_RegNotifyChangeKeyValue
0x18009c6e7  nop     dword ptr [rax+rax+00h]
0x18009c6ec  test    eax, eax
0x18009c6ee  jnz     loc_18009C857
0x18009c6f4  xor     edx, edx; Val
0x18009c6f6  lea     r8d, [rax+40h]; Size
0x18009c6fa  lea     rcx, [rsp+0D8h+var_78]; void *
0x18009c6ff  call    memset_0
0x18009c704  mov     [rsp+0D8h+var_78], 40h ; '@'
0x18009c70c  lea     rcx, [rsp+0D8h+var_38]
0x18009c714  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009c719  mov     rcx, rax
0x18009c71c  lea     rdx, [rsp+0D8h+var_78]
0x18009c721  call    cs:__imp_OmaDmGetInitiationInfo
0x18009c728  nop     dword ptr [rax+rax+00h]
0x18009c72d  mov     edi, eax
0x18009c72f  test    eax, eax
0x18009c731  js      loc_18009C81C
0x18009c737  mov     eax, [rsp+0D8h+var_64]
0x18009c73b  add     eax, 0FFFFFFFBh
0x18009c73e  cmp     eax, 1
0x18009c741  jbe     loc_18009C7E2
0x18009c747  mov     edx, 36EE80h; dwMilliseconds
0x18009c74c  mov     rcx, rbx; hHandle
0x18009c74f  call    cs:__imp_WaitForSingleObject
0x18009c756  nop     dword ptr [rax+rax+00h]
0x18009c75b  cmp     eax, 0FFFFFFFFh
0x18009c75e  jz      short loc_18009C7B1
0x18009c760  cmp     eax, 102h
0x18009c765  jz      short loc_18009C78C
0x18009c767  mov     rcx, rbx; hEvent
0x18009c76a  call    cs:__imp_ResetEvent
0x18009c771  nop     dword ptr [rax+rax+00h]
0x18009c776  lea     rcx, [rsp+0D8h+var_78]
0x18009c77b  call    cs:__imp_OmaDmFreeInitiationInfo
0x18009c782  nop     dword ptr [rax+rax+00h]
0x18009c787  jmp     loc_18009C6C5
0x18009c78c  lea     rcx, [rsp+0D8h+var_78]
0x18009c791  call    cs:__imp_OmaDmFreeInitiationInfo
0x18009c798  nop     dword ptr [rax+rax+00h]
0x18009c79d  lea     rcx, [rsp+0D8h+var_A8]
0x18009c7a2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009c7a7  mov     ebx, 800705B4h
0x18009c7ac  jmp     loc_18009C87F
0x18009c7b1  call    cs:__imp_GetLastError
0x18009c7b8  nop     dword ptr [rax+rax+00h]
0x18009c7bd  mov     ebx, eax
0x18009c7bf  test    eax, eax
0x18009c7c1  jle     short loc_18009C7CC
0x18009c7c3  movzx   ebx, ax
0x18009c7c6  or      ebx, 80070000h
0x18009c7cc  lea     rcx, [rsp+0D8h+var_78]
0x18009c7d1  call    cs:__imp_OmaDmFreeInitiationInfo
0x18009c7d8  nop     dword ptr [rax+rax+00h]
0x18009c7dd  jmp     loc_18009C875
0x18009c7e2  lea     rcx, [rsp+0D8h+var_78]
0x18009c7e7  call    cs:__imp_OmaDmFreeInitiationInfo
0x18009c7ee  nop     dword ptr [rax+rax+00h]
0x18009c7f3  lea     rcx, [rsp+0D8h+var_A8]
0x18009c7f8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009c7fd  lea     rcx, [rsp+0D8h+hKey]
0x18009c802  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009c807  nop
0x18009c808  lea     rcx, [rsp+0D8h+var_38]
0x18009c810  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009c815  xor     eax, eax
0x18009c817  jmp     loc_18009C8AC
0x18009c81c  mov     rcx, [rsp+0D8h]; this
0x18009c824  mov     r9d, edi; char *
0x18009c827  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009c82e  mov     edx, 0E2h; void *
0x18009c833  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009c838  lea     rcx, [rsp+0D8h+var_78]
0x18009c83d  call    cs:__imp_OmaDmFreeInitiationInfo
0x18009c844  nop     dword ptr [rax+rax+00h]
0x18009c849  lea     rcx, [rsp+0D8h+var_A8]
0x18009c84e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009c853  mov     ebx, edi
0x18009c855  jmp     short loc_18009C87F
0x18009c857  mov     rcx, [rsp+0D8h]; this
0x18009c85f  mov     r9d, eax; char *
0x18009c862  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009c869  mov     edx, 0DDh; void *
0x18009c86e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009c873  mov     ebx, eax
0x18009c875  lea     rcx, [rsp+0D8h+var_A8]
0x18009c87a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009c87f  lea     rcx, [rsp+0D8h+hKey]
0x18009c884  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009c889  nop
0x18009c88a  lea     rcx, [rsp+0D8h+var_38]
0x18009c892  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009c897  mov     eax, ebx
0x18009c899  jmp     short loc_18009C8AC
0x18009c89b  lea     rcx, [rsp+0D8h+var_38]
0x18009c8a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009c8a8  mov     eax, dword ptr [rsp+0D8h+var_A8]
0x18009c8ac  mov     rcx, [rsp+0D8h+var_18]
0x18009c8b4  xor     rcx, rsp; StackCookie
0x18009c8b7  call    __security_check_cookie
0x18009c8bc  mov     rbx, [rsp+0D8h+arg_8]
0x18009c8c4  add     rsp, 0D0h
0x18009c8cb  pop     rdi
0x18009c8cc  retn
```
