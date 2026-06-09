# FSToastManager::UpdateUserDiscoveryToastKey(ushort const *)

- ea: `0x18004bb90`
- end: `0x18004be2a`
- name: `?UpdateUserDiscoveryToastKey@FSToastManager@@UEAAJPEBG@Z`
- size: `666`
- prototype: `__int64 __fastcall(FSToastManager *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180008cf0`
- `0x1800095c8`
- `0x180009608`
- `0x1800096f4`
- `0x18000a880`
- `0x180026ecc`
- `0x18002b510`
- `0x18004bb90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004bc0e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004bc0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004bc75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004bc75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004bbd7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004bbd7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004bd75`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004bd75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004bd1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004bd1a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004bdac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004bdac`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18004bcc2`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18004bcc2`

## pseudocode

```c
__int64 __fastcall FSToastManager::UpdateUserDiscoveryToastKey(FSToastManager *this, const unsigned __int16 *a2)
{
  unsigned int v4; // eax
  signed int v5; // esi
  __int64 v6; // rbx
  __int64 v8; // rbx
  LSTATUS v9; // eax
  __int64 v10; // rdx
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  PHKEY v13; // [rsp+20h] [rbp-30h]
  HKEY phkResult; // [rsp+40h] [rbp-10h] BYREF
  __int64 v15; // [rsp+48h] [rbp-8h] BYREF
  unsigned int Data; // [rsp+90h] [rbp+40h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp+50h] BYREF
  HKEY hkey; // [rsp+A8h] [rbp+58h] BYREF

  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 29, &WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids, this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v4 = 0;
  pcbData = 4;
  v5 = 0;
  Data = 0;
  v6 = 0;
  hkey = 0;
  phkResult = 0;
  v15 = 0;
  if ( !*((_DWORD *)this + 26) )
  {
LABEL_7:
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      LODWORD(v13) = v5;
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        34,
        &WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids,
        this,
        v13,
        v4);
    }
    goto LABEL_9;
  }
  while ( (unsigned int)_o__wcsicmp(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 12) + 8 * v6) + 80LL), a2) )
  {
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= *((_DWORD *)this + 26) )
      goto LABEL_6;
  }
  wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(
    &v15,
    *(_QWORD *)(*((_QWORD *)this + 12) + 8 * v6));
  v8 = v15;
  if ( !v15 )
    goto LABEL_6;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v9 = RegOpenCurrentUser(0x2001Fu, &phkResult);
  v5 = v9;
  if ( v9 > 0 )
    v5 = (unsigned __int16)v9 | 0x80070000;
  if ( v5 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_30;
    v10 = 30;
    goto LABEL_29;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v11 = RegOpenKeyExW(
          phkResult,
          L"Software\\Microsoft\\Windows Media Foundation\\UserCameraEffects",
          0,
          0x2001Fu,
          &hkey);
  v5 = v11;
  if ( v11 > 0 )
    v5 = (unsigned __int16)v11 | 0x80070000;
  if ( v5 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_30;
    v10 = 31;
    goto LABEL_29;
  }
  if ( RegGetValueW(hkey, 0, L"EffectsDiscoveredToast", 0x10u, 0, &Data, &pcbData) || *(_DWORD *)(v8 + 108) > Data )
    Data = *(_DWORD *)(v8 + 108);
  v12 = RegSetValueExW(hkey, L"EffectsDiscoveredToast", 0, 4u, (const BYTE *)&Data, 4u);
  v5 = v12;
  if ( v12 > 0 )
    v5 = (unsigned __int16)v12 | 0x80070000;
  if ( v5 >= 0 )
  {
LABEL_6:
    v4 = Data;
    goto LABEL_7;
  }
  if ( !g_wppLevels )
    goto LABEL_30;
  v10 = 32;
LABEL_29:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids, this, v5);
LABEL_30:
  if ( byte_18010EC4D )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 33, &WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids, this, v5);
LABEL_9:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v15);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004bb90  push    rbp
0x18004bb92  push    rbx
0x18004bb93  push    rsi
0x18004bb94  push    rdi
0x18004bb95  push    r12
0x18004bb97  push    r14
0x18004bb99  push    r15
0x18004bb9b  mov     rbp, rsp
0x18004bb9e  sub     rsp, 50h
0x18004bba2  mov     r12, rdx
0x18004bba5  mov     r14, rcx
0x18004bba8  cmp     cs:byte_18010EC4D, 8
0x18004bbaf  jb      short loc_18004BBD3
0x18004bbb1  mov     r9, rcx
0x18004bbb4  lea     r8, WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids
0x18004bbbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bbc2  mov     edx, 1Dh
0x18004bbc7  mov     rcx, [rcx+0D8h]
0x18004bbce  call    WPP_SF_q
0x18004bbd3  lea     rcx, [r14+18h]; lpCriticalSection
0x18004bbd7  call    cs:__imp_EnterCriticalSection
0x18004bbdd  xor     eax, eax
0x18004bbdf  mov     [rbp+arg_10], 4
0x18004bbe6  xor     esi, esi
0x18004bbe8  mov     [rbp+Data], eax
0x18004bbeb  xor     ebx, ebx
0x18004bbed  mov     [rbp+hkey], rsi
0x18004bbf1  mov     [rbp+phkResult], rsi
0x18004bbf5  mov     [rbp+var_8], rax
0x18004bbf9  cmp     [r14+68h], eax
0x18004bbfd  jbe     short loc_18004BC23
0x18004bbff  mov     rax, [r14+60h]
0x18004bc03  mov     rdx, r12
0x18004bc06  mov     rcx, [rax+rbx*8]
0x18004bc0a  mov     rcx, [rcx+50h]
0x18004bc0e  call    cs:__imp__o__wcsicmp
0x18004bc14  test    eax, eax
0x18004bc16  jz      short loc_18004BC8C
0x18004bc18  inc     ebx
0x18004bc1a  cmp     ebx, [r14+68h]
0x18004bc1e  jb      short loc_18004BBFF
0x18004bc20  mov     eax, [rbp+Data]
0x18004bc23  cmp     cs:byte_18010EC4D, 8
0x18004bc2a  jb      short loc_18004BC56
0x18004bc2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bc33  lea     r8, WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids
0x18004bc3a  mov     dword ptr [rsp+50h+pvData], eax
0x18004bc3e  mov     edx, 22h ; '"'
0x18004bc43  mov     r9, r14
0x18004bc46  mov     dword ptr [rsp+50h+var_30], esi
0x18004bc4a  mov     rcx, [rcx+0D8h]
0x18004bc51  call    WPP_SF_qDD
0x18004bc56  lea     rcx, [rbp+var_8]; void *
0x18004bc5a  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18004bc5f  lea     rcx, [rbp+phkResult]
0x18004bc63  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004bc68  lea     rcx, [rbp+hkey]
0x18004bc6c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004bc71  lea     rcx, [r14+18h]; lpCriticalSection
0x18004bc75  call    cs:__imp_LeaveCriticalSection
0x18004bc7b  mov     eax, esi
0x18004bc7d  add     rsp, 50h
0x18004bc81  pop     r15
0x18004bc83  pop     r14
0x18004bc85  pop     r12
0x18004bc87  pop     rdi
0x18004bc88  pop     rsi
0x18004bc89  pop     rbx
0x18004bc8a  pop     rbp
0x18004bc8b  retn
0x18004bc8c  mov     rdx, [r14+60h]
0x18004bc90  lea     rcx, [rbp+var_8]
0x18004bc94  mov     rdx, [rdx+rbx*8]
0x18004bc98  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x18004bc9d  mov     rbx, [rbp+var_8]
0x18004bca1  test    rbx, rbx
0x18004bca4  jz      loc_18004BC20
0x18004bcaa  xor     edx, edx
0x18004bcac  lea     rcx, [rbp+phkResult]
0x18004bcb0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004bcb5  mov     r12d, 2001Fh
0x18004bcbb  lea     rdx, [rbp+phkResult]; phkResult
0x18004bcbf  mov     ecx, r12d; samDesired
0x18004bcc2  call    cs:__imp_RegOpenCurrentUser
0x18004bcc8  mov     esi, eax
0x18004bcca  mov     r15d, 80070000h
0x18004bcd0  test    eax, eax
0x18004bcd2  jle     short loc_18004BCDA
0x18004bcd4  movzx   esi, ax
0x18004bcd7  or      esi, r15d
0x18004bcda  test    esi, esi
0x18004bcdc  jns     short loc_18004BCF5
0x18004bcde  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004bce5  jb      loc_18004BDF2
0x18004bceb  mov     edx, 1Eh
0x18004bcf0  jmp     loc_18004BDD4
0x18004bcf5  xor     edx, edx
0x18004bcf7  lea     rcx, [rbp+hkey]
0x18004bcfb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004bd00  mov     rcx, [rbp+phkResult]; hKey
0x18004bd04  lea     rax, [rbp+hkey]
0x18004bd08  mov     r9d, r12d; samDesired
0x18004bd0b  mov     [rsp+50h+var_30], rax; phkResult
0x18004bd10  xor     r8d, r8d; ulOptions
0x18004bd13  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Media Foun"...
0x18004bd1a  call    cs:__imp_RegOpenKeyExW
0x18004bd20  mov     esi, eax
0x18004bd22  test    eax, eax
0x18004bd24  jle     short loc_18004BD2C
0x18004bd26  movzx   esi, ax
0x18004bd29  or      esi, r15d
0x18004bd2c  test    esi, esi
0x18004bd2e  jns     short loc_18004BD47
0x18004bd30  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004bd37  jb      loc_18004BDF2
0x18004bd3d  mov     edx, 1Fh
0x18004bd42  jmp     loc_18004BDD4
0x18004bd47  mov     rcx, [rbp+hkey]; hkey
0x18004bd4b  lea     rax, [rbp+arg_10]
0x18004bd4f  mov     [rsp+50h+pcbData], rax; pcbData
0x18004bd54  lea     r8, ValueName; "EffectsDiscoveredToast"
0x18004bd5b  lea     rax, [rbp+Data]
0x18004bd5f  mov     r9d, 10h; dwFlags
0x18004bd65  mov     [rsp+50h+pvData], rax; pvData
0x18004bd6a  xor     edx, edx; lpSubKey
0x18004bd6c  mov     [rsp+50h+var_30], 0; pdwType
0x18004bd75  call    cs:__imp_RegGetValueW
0x18004bd7b  test    eax, eax
0x18004bd7d  mov     eax, [rbx+6Ch]
0x18004bd80  jnz     short loc_18004BD87
0x18004bd82  cmp     eax, [rbp+Data]
0x18004bd85  jbe     short loc_18004BD8A
0x18004bd87  mov     [rbp+Data], eax
0x18004bd8a  mov     rcx, [rbp+hkey]; hKey
0x18004bd8e  lea     rax, [rbp+Data]
0x18004bd92  mov     r9d, 4; dwType
0x18004bd98  lea     rdx, ValueName; "EffectsDiscoveredToast"
0x18004bd9f  mov     dword ptr [rsp+50h+pvData], r9d; cbData
0x18004bda4  xor     r8d, r8d; Reserved
0x18004bda7  mov     [rsp+50h+var_30], rax; lpData
0x18004bdac  call    cs:__imp_RegSetValueExW
0x18004bdb2  mov     esi, eax
0x18004bdb4  test    eax, eax
0x18004bdb6  jle     short loc_18004BDBE
0x18004bdb8  movzx   esi, ax
0x18004bdbb  or      esi, r15d
0x18004bdbe  test    esi, esi
0x18004bdc0  jns     loc_18004BC20
0x18004bdc6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004bdcd  jb      short loc_18004BDF2
0x18004bdcf  mov     edx, 20h ; ' '
0x18004bdd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bddb  lea     r8, WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids
0x18004bde2  mov     r9, r14
0x18004bde5  mov     dword ptr [rsp+50h+var_30], esi
0x18004bde9  mov     rcx, [rcx+10h]
0x18004bded  call    WPP_SF_qD
0x18004bdf2  cmp     cs:byte_18010EC4D, 1
0x18004bdf9  jb      loc_18004BC56
0x18004bdff  mov     rcx, cs:WPP_GLOBAL_Control
0x18004be06  lea     r8, WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids
0x18004be0d  mov     edx, 21h ; '!'
0x18004be12  mov     dword ptr [rsp+50h+var_30], esi
0x18004be16  mov     r9, r14
0x18004be19  mov     rcx, [rcx+0D8h]
0x18004be20  call    WPP_SF_qD
0x18004be25  jmp     loc_18004BC56
```
