# _lambda_c175afdfc3660c9c38aa5b32986cf3f1_::operator()

- ea: `0x18000e0d8`
- end: `0x18000e41b`
- name: `_lambda_c175afdfc3660c9c38aa5b32986cf3f1_::operator()`
- size: `835`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callers

- `0x18000d3b8`

## callees

- `0x180004120`
- `0x180005308`
- `0x180005328`
- `0x1800065d4`
- `0x180006608`
- `0x180007274`
- `0x1800072d8`
- `0x18000895c`
- `0x18000e0d8`
- `0x18000edd0`
- `0x18000fbfc`
- `0x18000fd1c`
- `0x180010bfc`
- `0x1800113fc`
- `0x1800119f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e2f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e2f9`

## pseudocode

```c
__int64 __fastcall lambda_c175afdfc3660c9c38aa5b32986cf3f1_::operator()(__int64 a1)
{
  _DWORD *v2; // rax
  NetSetup2::ActiveObject *NetworkInterfaceById; // rax
  const WCHAR *v4; // rsi
  LSTATUS v5; // edi
  const WCHAR *v6; // r8
  __int64 v7; // r8
  DWORD v8; // eax
  _BYTE v10[8]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v11; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+130h] [rbp+30h] BYREF
  HKEY v14; // [rsp+138h] [rbp+38h] BYREF
  HKEY v15; // [rsp+140h] [rbp+40h] BYREF
  __int64 v16; // [rsp+148h] [rbp+48h] BYREF
  int v17; // [rsp+150h] [rbp+50h] BYREF
  void *v18[4]; // [rsp+158h] [rbp+58h] BYREF

  if ( *(_DWORD *)a1 != 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        WPP_f1172f7f51b138cada6e87324e167680_Traceguids,
        "ObjectType == NetSetupObjectTypeInterface");
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
  if ( *(_DWORD *)(a1 + 4) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        WPP_f1172f7f51b138cada6e87324e167680_Traceguids,
        "Reserved == 0");
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
  if ( *(_DWORD *)(a1 + 8) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_f1172f7f51b138cada6e87324e167680_Traceguids,
        "SetValueFlags == 0");
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
  v2 = *(_DWORD **)(a1 + 16);
  if ( *v2 != 4099 && *v2 != 7 && *v2 != 18 && *v2 != 8210 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        WPP_f1172f7f51b138cada6e87324e167680_Traceguids,
        "Value->Type == (0x00000003|0x00001000) || Value->Type == 0x00000007 || Value->Type == 0x00000012 || Value->Type "
        "== (0x00000012|0x00002000)");
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
  v16 = *(_QWORD *)(a1 + 24);
  NetworkInterfaceById = (NetSetup2::ActiveObject *)NetSetup2::details::TransactionBase::GetNetworkInterfaceById(
                                                      &v16,
                                                      v10,
                                                      a1 + 32);
  NetSetup2::NetworkInterface::get_ConfigurationPath(NetworkInterfaceById, (__int64)&v17);
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v11);
  v4 = L"SYSTEM\\CurrentControlSet";
  if ( v17 )
    v4 = L"DEVICES";
  phkResult = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 1u, &phkResult);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        (unsigned int)WPP_f1172f7f51b138cada6e87324e167680_Traceguids,
        (_DWORD)v4,
        v5);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v5);
    throw (Win32Exception *)pExceptionObject;
  }
  RegistryKey::RegistryKey((RegistryKey *)&v15, phkResult);
  v6 = (const WCHAR *)v18;
  if ( v18[3] >= (void *)8 )
    v6 = (const WCHAR *)v18[0];
  RegistryKey::OpenSubKey(&v15, (HKEY)&v14, v6, 2u);
  v7 = *(_QWORD *)(a1 + 16);
  switch ( *(_DWORD *)v7 )
  {
    case 7:
      v8 = 4;
      break;
    case 0x12:
      v8 = 1;
      break;
    case 0x1003:
      v8 = 3;
      break;
    default:
      v8 = 0;
      if ( *(_DWORD *)v7 == 8210 )
        v8 = 7;
      break;
  }
  RegistryKey::SetValue(
    &v14,
    *(const wchar_t **)(a1 + 48),
    *(const unsigned __int8 **)(v7 + 8),
    *(_DWORD *)(v7 + 4),
    v8);
  RegistryKey::~RegistryKey(&v14);
  RegistryKey::~RegistryKey(&v15);
  return std::wstring::_Tidy(v18, 1, 0);
}

```

## disassembly

```asm
0x18000e0d8  push    rbp
0x18000e0da  push    rbx
0x18000e0db  push    rsi
0x18000e0dc  push    rdi
0x18000e0dd  lea     rbp, [rsp-88h]
0x18000e0e5  sub     rsp, 188h
0x18000e0ec  mov     [rsp+1A0h+var_170], 0FFFFFFFFFFFFFFFEh
0x18000e0f5  mov     rax, cs:__security_cookie
0x18000e0fc  xor     rax, rsp
0x18000e0ff  mov     [rbp+0A0h+var_28], rax
0x18000e103  mov     rbx, rcx
0x18000e106  cmp     dword ptr [rcx], 2
0x18000e109  jz      short loc_18000E161
0x18000e10b  lea     rax, WPP_GLOBAL_Control
0x18000e112  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e119  cmp     rcx, rax
0x18000e11c  jz      short loc_18000E140
0x18000e11e  cmp     byte ptr [rcx+19h], 2
0x18000e122  jb      short loc_18000E140
0x18000e124  mov     edx, 23h ; '#'
0x18000e129  lea     r9, aObjecttypeNets; "ObjectType == NetSetupObjectTypeInterfa"...
0x18000e130  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x18000e137  mov     rcx, [rcx+10h]
0x18000e13b  call    WPP_SF_s
0x18000e140  mov     edx, 80070057h; int
0x18000e145  lea     rcx, [rsp+1A0h+pExceptionObject]; this
0x18000e14a  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18000e14f  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000e156  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18000e15b  call    _CxxThrowException_0
0x18000e161  cmp     dword ptr [rcx+4], 0
0x18000e165  jz      short loc_18000E1BD
0x18000e167  lea     rax, WPP_GLOBAL_Control
0x18000e16e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e175  cmp     rcx, rax
0x18000e178  jz      short loc_18000E19C
0x18000e17a  cmp     byte ptr [rcx+19h], 2
0x18000e17e  jb      short loc_18000E19C
0x18000e180  mov     edx, 24h ; '$'
0x18000e185  lea     r9, aReserved0; "Reserved == 0"
0x18000e18c  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x18000e193  mov     rcx, [rcx+10h]
0x18000e197  call    WPP_SF_s
0x18000e19c  mov     edx, 80070057h; int
0x18000e1a1  lea     rcx, [rsp+1A0h+pExceptionObject]; this
0x18000e1a6  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18000e1ab  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000e1b2  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18000e1b7  call    _CxxThrowException_0
0x18000e1bd  cmp     dword ptr [rcx+8], 0
0x18000e1c1  jz      short loc_18000E219
0x18000e1c3  lea     rax, WPP_GLOBAL_Control
0x18000e1ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1d1  cmp     rcx, rax
0x18000e1d4  jz      short loc_18000E1F8
0x18000e1d6  cmp     byte ptr [rcx+19h], 2
0x18000e1da  jb      short loc_18000E1F8
0x18000e1dc  mov     edx, 25h ; '%'
0x18000e1e1  lea     r9, aSetvalueflags0; "SetValueFlags == 0"
0x18000e1e8  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x18000e1ef  mov     rcx, [rcx+10h]
0x18000e1f3  call    WPP_SF_s
0x18000e1f8  mov     edx, 80070057h; int
0x18000e1fd  lea     rcx, [rsp+1A0h+pExceptionObject]; this
0x18000e202  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18000e207  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000e20e  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18000e213  call    _CxxThrowException_0
0x18000e219  mov     rax, [rcx+10h]
0x18000e21d  cmp     dword ptr [rax], 1003h
0x18000e223  jz      short loc_18000E28D
0x18000e225  cmp     dword ptr [rax], 7
0x18000e228  jz      short loc_18000E28D
0x18000e22a  cmp     dword ptr [rax], 12h
0x18000e22d  jz      short loc_18000E28D
0x18000e22f  cmp     dword ptr [rax], 2012h
0x18000e235  jz      short loc_18000E28D
0x18000e237  lea     rax, WPP_GLOBAL_Control
0x18000e23e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e245  cmp     rcx, rax
0x18000e248  jz      short loc_18000E26C
0x18000e24a  cmp     byte ptr [rcx+19h], 2
0x18000e24e  jb      short loc_18000E26C
0x18000e250  mov     edx, 26h ; '&'
0x18000e255  lea     r9, aValueType0x000; "Value->Type == (0x00000003|0x00001000) "...
0x18000e25c  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x18000e263  mov     rcx, [rcx+10h]
0x18000e267  call    WPP_SF_s
0x18000e26c  mov     edx, 80070057h; int
0x18000e271  lea     rcx, [rsp+1A0h+pExceptionObject]; this
0x18000e276  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18000e27b  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000e282  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18000e287  call    _CxxThrowException_0
0x18000e28d  mov     rax, [rcx+18h]
0x18000e291  mov     [rbp+0A0h+var_58], rax
0x18000e295  lea     r8, [rcx+20h]
0x18000e299  lea     rdx, [rsp+1A0h+var_168]
0x18000e29e  lea     rcx, [rbp+0A0h+var_58]
0x18000e2a2  call    ?GetNetworkInterfaceById@TransactionBase@details@NetSetup2@@QEAA?AVNetworkInterface@3@AEBU_GUID@@@Z; NetSetup2::details::TransactionBase::GetNetworkInterfaceById(_GUID const &)
0x18000e2a7  nop
0x18000e2a8  lea     rdx, [rbp+0A0h+var_50]
0x18000e2ac  mov     rcx, rax
0x18000e2af  call    ?get_ConfigurationPath@NetworkInterface@NetSetup2@@QEBA?AUConfigurationPath_Value@Aggregate@2@XZ; NetSetup2::NetworkInterface::get_ConfigurationPath(void)
0x18000e2b4  nop
0x18000e2b5  lea     rcx, [rsp+1A0h+var_160]
0x18000e2ba  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18000e2bf  lea     rsi, aSystemCurrentc; "SYSTEM\\CurrentControlSet"
0x18000e2c6  lea     rax, SubKey; "DEVICES"
0x18000e2cd  cmp     [rbp+0A0h+var_50], 0
0x18000e2d1  cmovnz  rsi, rax
0x18000e2d5  mov     [rbp+0A0h+var_70], 0
0x18000e2dd  lea     rax, [rbp+0A0h+var_70]
0x18000e2e1  mov     [rsp+1A0h+phkResult], rax; phkResult
0x18000e2e6  mov     r9d, 1; samDesired
0x18000e2ec  xor     r8d, r8d; ulOptions
0x18000e2ef  mov     rdx, rsi; lpSubKey
0x18000e2f2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e2f9  call    cs:__imp_RegOpenKeyExW
0x18000e2ff  mov     edi, eax
0x18000e301  test    eax, eax
0x18000e303  jz      short loc_18000E358
0x18000e305  lea     rax, WPP_GLOBAL_Control
0x18000e30c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e313  cmp     rcx, rax
0x18000e316  jz      short loc_18000E33A
0x18000e318  cmp     byte ptr [rcx+19h], 2
0x18000e31c  jb      short loc_18000E33A
0x18000e31e  mov     edx, 27h ; '''
0x18000e323  mov     dword ptr [rsp+1A0h+phkResult], edi
0x18000e327  mov     r9, rsi
0x18000e32a  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x18000e331  mov     rcx, [rcx+10h]
0x18000e335  call    WPP_SF_SD
0x18000e33a  mov     edx, edi; int
0x18000e33c  lea     rcx, [rsp+1A0h+pExceptionObject]; this
0x18000e341  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18000e346  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18000e34d  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18000e352  call    _CxxThrowException_0
0x18000e358  mov     rdx, [rbp+0A0h+var_70]; HKEY
0x18000e35c  lea     rcx, [rbp+0A0h+var_60]; this
0x18000e360  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x18000e365  nop
0x18000e366  lea     r8, [rbp+0A0h+var_48]
0x18000e36a  cmp     [rbp+0A0h+var_30], 8
0x18000e36f  cmovnb  r8, [rbp+0A0h+var_48]
0x18000e374  mov     r9d, 2
0x18000e37a  lea     rdx, [rbp+0A0h+var_68]
0x18000e37e  lea     rcx, [rbp+0A0h+var_60]
0x18000e382  call    ?OpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::OpenSubKey(wchar_t const *,ulong,void *)
0x18000e387  nop
0x18000e388  mov     r8, [rbx+10h]
0x18000e38c  cmp     dword ptr [r8], 7
0x18000e390  jz      short loc_18000E3C1
0x18000e392  cmp     dword ptr [r8], 12h
0x18000e396  jz      short loc_18000E3BA
0x18000e398  cmp     dword ptr [r8], 1003h
0x18000e39f  jz      short loc_18000E3B3
0x18000e3a1  xor     eax, eax
0x18000e3a3  cmp     dword ptr [r8], 2012h
0x18000e3aa  jnz     short loc_18000E3C6
0x18000e3ac  mov     eax, 7
0x18000e3b1  jmp     short loc_18000E3C6
0x18000e3b3  mov     eax, 3
0x18000e3b8  jmp     short loc_18000E3C6
0x18000e3ba  mov     eax, 1
0x18000e3bf  jmp     short loc_18000E3C6
0x18000e3c1  mov     eax, 4
0x18000e3c6  mov     r9d, [r8+4]; unsigned __int64
0x18000e3ca  mov     dword ptr [rsp+1A0h+phkResult], eax; unsigned int
0x18000e3ce  mov     r8, [r8+8]; unsigned __int8 *
0x18000e3d2  mov     rdx, [rbx+30h]; wchar_t *
0x18000e3d6  lea     rcx, [rbp+0A0h+var_68]; this
0x18000e3da  call    ?SetValue@RegistryKey@@QEBAXPEB_WPEBE_KK@Z; RegistryKey::SetValue(wchar_t const *,uchar const *,unsigned __int64,ulong)
0x18000e3df  nop
0x18000e3e0  lea     rcx, [rbp+0A0h+var_68]; this
0x18000e3e4  call    ??1RegistryKey@@QEAA@XZ; RegistryKey::~RegistryKey(void)
0x18000e3e9  nop
0x18000e3ea  lea     rcx, [rbp+0A0h+var_60]; this
0x18000e3ee  call    ??1RegistryKey@@QEAA@XZ; RegistryKey::~RegistryKey(void)
0x18000e3f3  nop
0x18000e3f4  xor     r8d, r8d
0x18000e3f7  mov     dl, 1
0x18000e3f9  lea     rcx, [rbp+0A0h+var_48]
0x18000e3fd  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e402  nop
0x18000e403  mov     rcx, [rbp+0A0h+var_28]
0x18000e407  xor     rcx, rsp; StackCookie
0x18000e40a  call    __security_check_cookie
0x18000e40f  add     rsp, 188h
0x18000e416  pop     rdi
0x18000e417  pop     rsi
0x18000e418  pop     rbx
0x18000e419  pop     rbp
0x18000e41a  retn
```
