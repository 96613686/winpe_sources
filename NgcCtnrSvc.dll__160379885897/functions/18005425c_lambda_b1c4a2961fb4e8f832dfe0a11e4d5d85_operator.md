# _lambda_b1c4a2961fb4e8f832dfe0a11e4d5d85_::operator()

- ea: `0x18005425c`
- end: `0x18005447d`
- name: `_lambda_b1c4a2961fb4e8f832dfe0a11e4d5d85_::operator()`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053e30`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x180012300`
- `0x180018194`
- `0x180019c94`
- `0x1800260ac`
- `0x18002c640`
- `0x18005425c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180054399`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180054399`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180054344`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180054344`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_b1c4a2961fb4e8f832dfe0a11e4d5d85_::operator()(__int64 a1)
{
  const wchar_t *v2; // rdx
  __int64 v3; // r8
  unsigned int v4; // ebx
  const WCHAR *v5; // rdx
  LSTATUS ValueW; // edi
  const WCHAR *v7; // r8
  unsigned __int8 *v8; // rdx
  LSTATUS v10; // [rsp+40h] [rbp-29h] BYREF
  int pvData; // [rsp+44h] [rbp-25h] BYREF
  void **v12; // [rsp+48h] [rbp-21h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-19h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-11h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+60h] [rbp-9h] BYREF
  LPCWSTR lpValue[4]; // [rsp+80h] [rbp+17h] BYREF

  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)lpSubKey);
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)lpValue);
  if ( **(_DWORD **)a1 == 1 )
  {
    v2 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\PreBoot\\AccountInfo";
    v3 = 76;
    goto LABEL_5;
  }
  if ( **(_DWORD **)a1 == 2 )
  {
    v2 = L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailUnlock\\AccountInfo";
    v3 = 66;
LABEL_5:
    std::wstring::_Assign<unsigned short>((char **)lpSubKey, v2, (char *)v3);
    v4 = 0;
    std::wstring::_Assign<unsigned short>((char **)lpValue, L"ProvisioningRequired", (char *)0x14);
    std::wstring::append(lpSubKey, L"\\");
    std::wstring::append(lpSubKey, **(_QWORD **)(a1 + 8));
    v12 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
    hkey = 0;
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v12);
    v5 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v5 = lpSubKey[0];
    ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 1u, &hkey);
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        if ( (unsigned int)dword_1800BE0B8 <= 2 )
          goto LABEL_20;
        v8 = (unsigned __int8 *)word_1800AD77A;
LABEL_19:
        v10 = ValueW;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          v8,
          0,
          0,
          (__int64)&v10);
LABEL_20:
        if ( ValueW > 0 )
          v4 = (unsigned __int16)ValueW | 0x80070000;
        else
          v4 = ValueW;
      }
    }
    else
    {
      ***(_BYTE ***)(a1 + 16) = 1;
      pvData = 0;
      pcbData = 4;
      v7 = (const WCHAR *)lpValue;
      if ( lpValue[3] > (LPCWSTR)7 )
        v7 = lpValue[0];
      ValueW = RegGetValueW(hkey, 0, v7, 0x10u, 0, &pvData, &pcbData);
      if ( !ValueW )
      {
        if ( pvData )
          ***(_BYTE ***)(a1 + 24) = 1;
        goto LABEL_23;
      }
      if ( ValueW != 2 )
      {
        if ( (unsigned int)dword_1800BE0B8 <= 2 )
          goto LABEL_20;
        v8 = (unsigned __int8 *)&byte_1800AD6A7;
        goto LABEL_19;
      }
    }
LABEL_23:
    v12 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v12);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpValue);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
    return v4;
  }
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpValue);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
  return 2148073517LL;
}

```

## disassembly

```asm
0x18005425c  mov     [rsp-8+arg_8], rbx
0x180054261  mov     [rsp-8+arg_10], rsi
0x180054266  push    rbp
0x180054267  push    rdi
0x180054268  push    r15
0x18005426a  lea     rbp, [rsp-47h]
0x18005426f  sub     rsp, 0B0h
0x180054276  mov     rax, cs:__security_cookie
0x18005427d  xor     rax, rsp
0x180054280  mov     [rbp+57h+var_20], rax
0x180054284  mov     rsi, rcx
0x180054287  lea     rcx, [rbp+57h+lpSubKey]
0x18005428b  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180054290  nop
0x180054291  lea     rcx, [rbp+57h+lpValue]
0x180054295  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18005429a  nop
0x18005429b  mov     rax, [rsi]
0x18005429e  cmp     dword ptr [rax], 1
0x1800542a1  jnz     short loc_1800542B2
0x1800542a3  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800542aa  mov     r8d, 4Ch ; 'L'
0x1800542b0  jmp     short loc_1800542C8
0x1800542b2  cmp     dword ptr [rax], 2
0x1800542b5  jnz     loc_180054440
0x1800542bb  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800542c2  mov     r8d, 42h ; 'B'
0x1800542c8  lea     rcx, [rbp+57h+lpSubKey]
0x1800542cc  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800542d1  xor     ebx, ebx
0x1800542d3  lea     r8d, [rbx+14h]
0x1800542d7  lea     rdx, aProvisioningre; "ProvisioningRequired"
0x1800542de  lea     rcx, [rbp+57h+lpValue]
0x1800542e2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800542e7  lea     rdx, asc_18008F0A4; "\\"
0x1800542ee  lea     rcx, [rbp+57h+lpSubKey]
0x1800542f2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800542f7  mov     rdx, [rsi+8]
0x1800542fb  mov     rdx, [rdx]
0x1800542fe  lea     rcx, [rbp+57h+lpSubKey]
0x180054302  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180054307  lea     r15, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x18005430e  mov     [rbp+57h+var_78], r15
0x180054312  mov     [rbp+57h+hkey], rbx
0x180054316  lea     rcx, [rbp+57h+var_78]
0x18005431a  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18005431f  lea     rdx, [rbp+57h+lpSubKey]
0x180054323  cmp     [rbp+57h+var_48], 7
0x180054328  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18005432d  lea     rax, [rbp+57h+hkey]
0x180054331  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180054336  lea     r9d, [rbx+1]; samDesired
0x18005433a  xor     r8d, r8d; ulOptions
0x18005433d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180054344  call    cs:__imp_RegOpenKeyExW
0x18005434b  nop     dword ptr [rax+rax+00h]
0x180054350  mov     edi, eax
0x180054352  test    eax, eax
0x180054354  jnz     short loc_1800543D5
0x180054356  mov     rax, [rsi+10h]
0x18005435a  mov     rcx, [rax]
0x18005435d  mov     byte ptr [rcx], 1
0x180054360  mov     [rbp+57h+var_7C], ebx
0x180054363  mov     [rbp+57h+var_68], 4
0x18005436a  lea     r8, [rbp+57h+lpValue]
0x18005436e  cmp     [rbp+57h+var_28], 7
0x180054373  cmova   r8, [rbp+57h+lpValue]; lpValue
0x180054378  lea     rax, [rbp+57h+var_68]
0x18005437c  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180054381  lea     rax, [rbp+57h+var_7C]
0x180054385  mov     [rsp+0C0h+pvData], rax; pvData
0x18005438a  mov     [rsp+0C0h+phkResult], rbx; pdwType
0x18005438f  xor     edx, edx; lpSubKey
0x180054391  lea     r9d, [rbx+10h]; dwFlags
0x180054395  mov     rcx, [rbp+57h+hkey]; hkey
0x180054399  call    cs:__imp_RegGetValueW
0x1800543a0  nop     dword ptr [rax+rax+00h]
0x1800543a5  mov     edi, eax
0x1800543a7  test    eax, eax
0x1800543a9  jnz     short loc_1800543BC
0x1800543ab  cmp     [rbp+57h+var_7C], ebx
0x1800543ae  jz      short loc_18005441B
0x1800543b0  mov     rax, [rsi+18h]
0x1800543b4  mov     rcx, [rax]
0x1800543b7  mov     byte ptr [rcx], 1
0x1800543ba  jmp     short loc_18005441B
0x1800543bc  cmp     edi, 2
0x1800543bf  jz      short loc_18005441B
0x1800543c1  mov     eax, cs:dword_1800BE0B8
0x1800543c7  cmp     eax, 2
0x1800543ca  jbe     short loc_18005440A
0x1800543cc  lea     rdx, byte_1800AD6A7
0x1800543d3  jmp     short loc_1800543EC
0x1800543d5  cmp     edi, 2
0x1800543d8  jz      short loc_18005441B
0x1800543da  mov     eax, cs:dword_1800BE0B8
0x1800543e0  cmp     eax, 2
0x1800543e3  jbe     short loc_18005440A
0x1800543e5  lea     rdx, word_1800AD77A
0x1800543ec  xor     r9d, r9d
0x1800543ef  lea     rax, [rbp+57h+var_80]
0x1800543f3  xor     r8d, r8d
0x1800543f6  mov     [rsp+0C0h+phkResult], rax
0x1800543fb  mov     [rbp+57h+var_80], edi
0x1800543fe  lea     rcx, dword_1800BE0B8
0x180054405  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005440a  test    edi, edi
0x18005440c  jg      short loc_180054412
0x18005440e  mov     ebx, edi
0x180054410  jmp     short loc_18005441B
0x180054412  movzx   ebx, di
0x180054415  or      ebx, 80070000h
0x18005441b  mov     [rbp+57h+var_78], r15
0x18005441f  lea     rcx, [rbp+57h+var_78]
0x180054423  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180054428  nop
0x180054429  lea     rcx, [rbp+57h+lpValue]
0x18005442d  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180054432  nop
0x180054433  lea     rcx, [rbp+57h+lpSubKey]
0x180054437  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18005443c  mov     eax, ebx
0x18005443e  jmp     short loc_180054458
0x180054440  lea     rcx, [rbp+57h+lpValue]
0x180054444  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180054449  nop
0x18005444a  lea     rcx, [rbp+57h+lpSubKey]
0x18005444e  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180054453  mov     eax, 8009002Dh
0x180054458  mov     rcx, [rbp+57h+var_20]
0x18005445c  xor     rcx, rsp; StackCookie
0x18005445f  call    __security_check_cookie
0x180054464  lea     r11, [rsp+0C0h+var_10]
0x18005446c  mov     rbx, [r11+28h]
0x180054470  mov     rsi, [r11+30h]
0x180054474  mov     rsp, r11
0x180054477  pop     r15
0x180054479  pop     rdi
0x18005447a  pop     rbp
0x18005447b  retn
```
