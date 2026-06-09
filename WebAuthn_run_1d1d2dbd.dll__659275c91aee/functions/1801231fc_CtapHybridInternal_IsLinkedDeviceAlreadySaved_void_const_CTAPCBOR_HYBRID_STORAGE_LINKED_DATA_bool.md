# CtapHybridInternal::IsLinkedDeviceAlreadySaved(void * const,_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *,bool *)

- ea: `0x1801231fc`
- end: `0x1801233dd`
- name: `?IsLinkedDeviceAlreadySaved@CtapHybridInternal@@YAJQEAXPEAU_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA@@PEA_N@Z`
- size: `481`
- prototype: `__int64 __fastcall(CtapHybridInternal *__hidden this, void *const, struct _CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *, bool *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a8a78`
- `0x1800a9848`

## callees

- `0x1800350b4`
- `0x180036da4`
- `0x180036dc8`
- `0x18003a9e8`
- `0x180042df8`
- `0x18004349c`
- `0x180067630`
- `0x1800859d8`
- `0x18010bfa8`
- `0x180122d70`
- `0x1801231fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180123385`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180123385`
- `CRYPT32!CryptBinaryToStringW` at `0x180123311`
- `CRYPT32!CryptBinaryToStringW` at `0x180123311`
- `bcrypt!BCryptHash` at `0x18012329b`
- `bcrypt!BCryptHash` at `0x18012329b`

## string_xrefs

- `0x180123237`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x1801232b0`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x180123323`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CtapHybridInternal::IsLinkedDeviceAlreadySaved(
        CtapHybridInternal *this,
        _DWORD *a2,
        struct _CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *a3,
        bool *a4)
{
  int UserLinkedDevicesRegKey; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  int v10; // eax
  unsigned int v11; // ebx
  const char *v12; // r9
  unsigned int LastError; // ebx
  HKEY *v14; // rax
  int pcchString; // [rsp+20h] [rbp-78h]
  int pcchStringa; // [rsp+20h] [rbp-78h]
  DWORD v17; // [rsp+40h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-50h] BYREF
  __int64 v19; // [rsp+50h] [rbp-48h] BYREF
  BYTE *pbBinary; // [rsp+58h] [rbp-40h] BYREF
  LPWSTR pszString[4]; // [rsp+70h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  int v23; // [rsp+B8h] [rbp+20h] BYREF

  hKey = 0;
  try
  {
    UserLinkedDevicesRegKey = CtapHybridInternal::GetUserLinkedDevicesRegKey((__int64)this, (__int64)&hKey);
    v7 = UserLinkedDevicesRegKey;
    if ( UserLinkedDevicesRegKey >= 0 )
    {
      std::vector<unsigned char>::vector<unsigned char>(&pbBinary, 32, &v23);
      pcchStringa = a2[12];
      v10 = BCryptHash(177, 0, 0, *((_QWORD *)a2 + 7));
      if ( v10 >= 0 )
      {
        v17 = 33;
        std::vector<unsigned short>::vector<unsigned short>(pszString, 33);
        if ( CryptBinaryToStringW(pbBinary, 0x10u, 0x4000000Cu, pszString[0], &v17) )
        {
          v19 = 0;
          v14 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v19);
          *(_BYTE *)a3 = RegOpenKeyExW(hKey, pszString[0], 0, 0xF003Fu, v14) == 0;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v19);
          std::vector<unsigned short>::_Tidy(pszString);
          std::vector<unsigned char>::_Tidy(&pbBinary);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          result = 0;
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x139,
                        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
                        v12);
          std::vector<unsigned short>::_Tidy(pszString);
          std::vector<unsigned char>::_Tidy(&pbBinary);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          result = LastError;
        }
      }
      else
      {
        v11 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x134,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
                (const char *)(unsigned int)v10,
                pcchStringa);
        std::vector<unsigned char>::_Tidy(&pbBinary);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        result = v11;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x130,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
        (const char *)(unsigned int)UserLinkedDevicesRegKey,
        pcchString);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      result = v7;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x149,
                           (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x1801231fc  mov     rax, rsp
0x1801231ff  mov     [rax+8], rbx
0x180123203  mov     [rax+10h], rsi
0x180123207  push    rdi
0x180123208  sub     rsp, 90h
0x18012320f  mov     rsi, r8
0x180123212  mov     rdi, rdx
0x180123215  mov     qword ptr [rax-50h], 0
0x18012321d  lea     rdx, [rax-50h]
0x180123221  call    ?GetUserLinkedDevicesRegKey@CtapHybridInternal@@YAJQEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CtapHybridInternal::GetUserLinkedDevicesRegKey(void * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x180123226  mov     ebx, eax
0x180123228  test    eax, eax
0x18012322a  jns     short loc_18012325A
0x18012322c  mov     rcx, [rsp+98h]; this
0x180123234  mov     r9d, eax; char *
0x180123237  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18012323e  mov     edx, 130h; void *
0x180123243  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123248  nop
0x180123249  lea     rcx, [rsp+98h+hKey]
0x18012324e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123253  mov     eax, ebx
0x180123255  jmp     loc_1801233C7
0x18012325a  lea     r8, [rsp+98h+arg_18]
0x180123262  mov     edx, 20h ; ' '
0x180123267  lea     rcx, [rsp+98h+pbBinary]
0x18012326c  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180123271  nop
0x180123272  mov     rcx, [rsp+98h+pbBinary]
0x180123277  mov     eax, [rsp+98h+var_38]
0x18012327b  sub     eax, ecx
0x18012327d  mov     [rsp+98h+var_68], eax
0x180123281  mov     [rsp+98h+var_70], rcx
0x180123286  mov     eax, [rdi+30h]
0x180123289  mov     dword ptr [rsp+98h+pcchString], eax; int
0x18012328d  mov     r9, [rdi+38h]
0x180123291  xor     r8d, r8d
0x180123294  xor     edx, edx
0x180123296  mov     ecx, 0B1h
0x18012329b  call    cs:__imp_BCryptHash
0x1801232a1  test    eax, eax
0x1801232a3  jns     short loc_1801232DF
0x1801232a5  mov     rcx, [rsp+98h]; this
0x1801232ad  mov     r9d, eax; char *
0x1801232b0  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801232b7  mov     edx, 134h; void *
0x1801232bc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801232c1  mov     ebx, eax
0x1801232c3  lea     rcx, [rsp+98h+pbBinary]
0x1801232c8  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801232cd  nop
0x1801232ce  lea     rcx, [rsp+98h+hKey]
0x1801232d3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801232d8  mov     eax, ebx
0x1801232da  jmp     loc_1801233C7
0x1801232df  mov     edx, 21h ; '!'
0x1801232e4  mov     [rsp+98h+var_58], edx
0x1801232e8  lea     rcx, [rsp+98h+pszString]
0x1801232ed  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x1801232f2  lea     rax, [rsp+98h+var_58]
0x1801232f7  mov     [rsp+98h+pcchString], rax; pcchString
0x1801232fc  mov     r9, [rsp+98h+pszString]; pszString
0x180123301  mov     edx, 10h; cbBinary
0x180123306  mov     r8d, 4000000Ch; dwFlags
0x18012330c  mov     rcx, [rsp+98h+pbBinary]; pbBinary
0x180123311  call    cs:__imp_CryptBinaryToStringW
0x180123317  test    eax, eax
0x180123319  jnz     short loc_18012335A
0x18012331b  mov     rcx, [rsp+98h]; this
0x180123323  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18012332a  mov     edx, 139h; void *
0x18012332f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180123334  mov     ebx, eax
0x180123336  lea     rcx, [rsp+98h+pszString]
0x18012333b  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180123340  nop
0x180123341  lea     rcx, [rsp+98h+pbBinary]
0x180123346  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18012334b  nop
0x18012334c  lea     rcx, [rsp+98h+hKey]
0x180123351  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123356  mov     eax, ebx
0x180123358  jmp     short loc_1801233C7
0x18012335a  mov     [rsp+98h+var_48], 0
0x180123363  lea     rcx, [rsp+98h+var_48]
0x180123368  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18012336d  mov     [rsp+98h+pcchString], rax; phkResult
0x180123372  mov     r9d, 0F003Fh; samDesired
0x180123378  xor     r8d, r8d; ulOptions
0x18012337b  mov     rdx, [rsp+98h+pszString]; lpSubKey
0x180123380  mov     rcx, [rsp+98h+hKey]; hKey
0x180123385  call    cs:__imp_RegOpenKeyExW
0x18012338b  test    eax, eax
0x18012338d  setz    al
0x180123390  mov     [rsi], al
0x180123392  lea     rcx, [rsp+98h+var_48]
0x180123397  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012339c  lea     rcx, [rsp+98h+pszString]
0x1801233a1  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1801233a6  nop
0x1801233a7  lea     rcx, [rsp+98h+pbBinary]
0x1801233ac  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801233b1  nop
0x1801233b2  lea     rcx, [rsp+98h+hKey]
0x1801233b7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801233bc  xor     eax, eax
0x1801233be  jmp     short loc_1801233C7
0x1801233c0  mov     eax, [rsp+98h+arg_18]
0x1801233c7  lea     r11, [rsp+98h+var_8]
0x1801233cf  mov     rbx, [r11+10h]
0x1801233d3  mov     rsi, [r11+18h]
0x1801233d7  mov     rsp, r11
0x1801233da  pop     rdi
0x1801233db  retn
```
