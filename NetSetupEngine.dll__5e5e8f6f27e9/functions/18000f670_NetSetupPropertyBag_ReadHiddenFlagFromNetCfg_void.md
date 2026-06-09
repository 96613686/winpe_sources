# NetSetupPropertyBag::ReadHiddenFlagFromNetCfg(void)

- ea: `0x18000f670`
- end: `0x18000fd67`
- name: `?ReadHiddenFlagFromNetCfg@NetSetupPropertyBag@@AEBA?AV?$shared_ptr@VProperty@NetSetup2@@@std@@XZ`
- size: `1783`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180006070`

## callees

- `0x1800074a0`
- `0x180008280`
- `0x18000f670`
- `0x18000fd70`
- `0x18000ffb0`
- `0x180010440`
- `0x180012830`
- `0x1800505ec`
- `0x18005097c`
- `0x180052620`
- `0x180052698`
- `0x18005b034`
- `0x1800646b8`
- `0x180064704`
- `0x180065035`
- `0x1800679d0`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f91e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f91e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f852`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f852`
- `api-ms-win-devices-config-l1-1-0!CM_Locate_DevNodeW` at `0x18000f76e`
- `api-ms-win-devices-config-l1-1-0!CM_Locate_DevNodeW` at `0x18000f7e1`
- `api-ms-win-devices-config-l1-1-0!CM_Locate_DevNodeW` at `0x18000f76e`
- `api-ms-win-devices-config-l1-1-0!CM_Locate_DevNodeW` at `0x18000f7e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
_QWORD *__fastcall NetSetupPropertyBag::ReadHiddenFlagFromNetCfg(__int64 a1, _QWORD *a2)
{
  __int64 v4; // r9
  _DWORD *v5; // rcx
  __int64 String; // rax
  WCHAR *v7; // rsi
  CONFIGRET DevNodeW; // eax
  unsigned int v9; // r14d
  char v10; // si
  __int64 v11; // rax
  CONFIGRET v12; // esi
  LSTATUS Value; // eax
  __int64 v14; // r8
  signed int v15; // ebx
  char ValueDword; // r14
  _DWORD *v17; // rax
  _DWORD *v18; // rbx
  volatile signed __int32 *v19; // rsi
  volatile signed __int32 *v20; // rsi
  _QWORD *result; // rax
  volatile signed __int32 *v22; // rsi
  volatile signed __int32 *v23; // rsi
  int v24; // eax
  int v25; // eax
  _QWORD *v26; // rax
  HKEY hKey; // [rsp+40h] [rbp-4B8h] BYREF
  int v28; // [rsp+48h] [rbp-4B0h]
  _QWORD *v29; // [rsp+50h] [rbp-4A8h]
  __int64 v30; // [rsp+58h] [rbp-4A0h]
  void *Block[3]; // [rsp+60h] [rbp-498h] BYREF
  unsigned __int64 v32; // [rsp+78h] [rbp-480h]
  __int64 v33; // [rsp+80h] [rbp-478h]
  char *v34; // [rsp+88h] [rbp-470h]
  _BYTE v35[208]; // [rsp+90h] [rbp-468h] BYREF
  _BYTE v36[208]; // [rsp+160h] [rbp-398h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+230h] [rbp-2C8h] BYREF
  _BYTE v38[208]; // [rsp+300h] [rbp-1F8h] BYREF
  _BYTE v39[208]; // [rsp+3D0h] [rbp-128h] BYREF
  __int64 v40; // [rsp+4A0h] [rbp-58h] BYREF
  std::_Ref_count_base *v41; // [rsp+4A8h] [rbp-50h]
  __int64 v42; // [rsp+4B0h] [rbp-48h] BYREF
  std::_Ref_count_base *v43; // [rsp+4B8h] [rbp-40h]
  DEVNODE pdnDevInst[2]; // [rsp+4C0h] [rbp-38h] BYREF
  DEVNODE v45; // [rsp+4C8h] [rbp-30h] BYREF
  __int64 v46; // [rsp+4D0h] [rbp-28h]

  v33 = -2;
  try
  {
    v30 = a1;
    v29 = a2;
    v28 = 0;
    if ( *(_DWORD *)(a1 + 16) == 2 )
    {
      NetSetupPropertyBag::Get((RTL_SRWLOCK *)a1, &v42, (__int128 *)&NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber);
      v4 = *(unsigned int *)(v42 + 20);
      if ( (_DWORD)v4 != 7 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_5c29e29b0d073899e3087936fa39f4e7_Traceguids, v4);
        HResultException::HResultException((HResultException *)v35, -2147023267);
        throw (HResultException *)v35;
      }
      v5 = *(_DWORD **)(v42 + 24);
      if ( *(_QWORD *)(v42 + 32) - (_QWORD)v5 != 4 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_5c29e29b0d073899e3087936fa39f4e7_Traceguids);
        HResultException::HResultException((HResultException *)v36, -2147024883);
        throw (HResultException *)v36;
      }
      if ( *v5 )
      {
        *a2 = 0;
        a2[1] = 0;
        if ( v43 )
          std::_Ref_count_base::_Decref(v43);
        result = a2;
      }
      else
      {
        NetSetupPropertyBag::Get((RTL_SRWLOCK *)a1, &v40, &NETSETUPPKEY_Interface_PnpInstance);
        if ( v40 && *(_DWORD *)(v40 + 20) )
        {
          String = NetSetup2::Property::GetString(v40, Block);
          v7 = (WCHAR *)String;
          if ( *(_QWORD *)(String + 24) >= 8u )
            v7 = *(WCHAR **)String;
          pdnDevInst[0] = 0;
          DevNodeW = CM_Locate_DevNodeW(pdnDevInst, v7, 1u);
          v9 = DevNodeW;
          if ( DevNodeW == 13 )
          {
            v10 = 1;
          }
          else
          {
            if ( DevNodeW )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  10,
                  (unsigned int)WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids,
                  (_DWORD)v7,
                  DevNodeW);
              v24 = My_CM_MapCrToWin32Err(v9);
              if ( v24 > 0 )
                v24 = (unsigned __int16)v24 | 0x80070000;
              HResultException::HResultException((HResultException *)pExceptionObject, v24);
              throw (HResultException *)pExceptionObject;
            }
            v10 = 0;
          }
          if ( v32 >= 8 )
            operator delete(Block[0]);
          if ( v10 )
          {
            *a2 = 0;
            a2[1] = 0;
            if ( v41 )
              std::_Ref_count_base::_Decref(v41);
            if ( v43 )
              std::_Ref_count_base::_Decref(v43);
            result = a2;
          }
          else
          {
            v11 = NetSetup2::Property::GetString(v40, Block);
            if ( *(_QWORD *)(v11 + 24) >= 8u )
              v11 = *(_QWORD *)v11;
            v45 = -1;
            v46 = v11;
            v12 = CM_Locate_DevNodeW(&v45, (DEVINSTID_W)v11, 1u);
            if ( v12 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  41,
                  (unsigned int)WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids,
                  v46,
                  v12);
              v25 = My_CM_MapCrToWin32Err(v12);
              if ( v25 > 0 )
                v25 = (unsigned __int16)v25 | 0x80070000;
              HResultException::HResultException((HResultException *)v38, v25);
              throw (HResultException *)v38;
            }
            if ( v32 >= 8 )
              operator delete(Block[0]);
            NetSetupDevice::OpenDeviceKey((__int64)&v45, (HKEY)&hKey, 1u, *(char **)(a1 + 40), 0, 1u, 1u);
            v28 = 8;
            Value = RegQueryValueExW(hKey, L"Characteristics", 0, 0, 0, 0);
            v15 = Value;
            if ( Value == 2 )
            {
              *a2 = 0;
              a2[1] = 0;
              if ( hKey )
                RegCloseKey(hKey);
              if ( v41 )
                std::_Ref_count_base::_Decref(v41);
              if ( v43 )
                std::_Ref_count_base::_Decref(v43);
              result = a2;
            }
            else
            {
              if ( Value )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    19,
                    (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
                    (unsigned int)L"Characteristics",
                    Value);
                Win32Exception::Win32Exception((Win32Exception *)v39, v15);
                throw (Win32Exception *)v39;
              }
              ValueDword = RegistryKey::GetValueDword(&hKey, L"Characteristics", v14, 0);
              v17 = operator new(0x40u);
              v18 = v17;
              *(_QWORD *)pdnDevInst = v17;
              if ( v17 )
              {
                v17[2] = 1;
                v17[3] = 1;
                *(_QWORD *)v17 = &std::_Ref_count_obj<NetSetup2::Property>::`vftable';
                v34 = (char *)(v17 + 4);
                *((_OWORD *)v17 + 1) = NETSETUPPKEY_Driver_HideInUi;
                v17[8] = 20;
                *((_QWORD *)v17 + 5) = 0;
                *((_QWORD *)v17 + 6) = 0;
                *((_QWORD *)v17 + 7) = 0;
                v17[9] = 17;
                std::vector<unsigned char>::resize(v17 + 10, 1);
                **((_BYTE **)v18 + 5) = (ValueDword & 8) != 0;
              }
              else
              {
                v18 = 0;
              }
              a2[1] = v18;
              *a2 = v18 + 4;
              if ( hKey )
                RegCloseKey(hKey);
              v19 = (volatile signed __int32 *)v41;
              if ( v41 )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
                  if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
                }
              }
              v20 = (volatile signed __int32 *)v43;
              if ( v43 )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
                  if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
                }
              }
              result = a2;
            }
          }
        }
        else
        {
          *a2 = 0;
          a2[1] = 0;
          v22 = (volatile signed __int32 *)v41;
          if ( v41 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
              if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
            }
          }
          v23 = (volatile signed __int32 *)v43;
          if ( v43 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
              if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
            }
          }
          result = a2;
        }
      }
    }
    else
    {
      *a2 = 0;
      a2[1] = 0;
      result = a2;
    }
  }
  catch ( ... )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_D_guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_44aef15b60a63ec0e0e715ba4b6cc043_Traceguids,
        *(_DWORD *)(v30 + 16),
        v30 + 20);
    v26 = v29;
    *v29 = 0;
    v26[1] = 0;
    return v29;
  }
  return result;
}

```

## disassembly

```asm
0x18000f670  mov     r11, rsp
0x18000f673  push    rdi
0x18000f674  push    r14
0x18000f676  push    r15
0x18000f678  sub     rsp, 4E0h
0x18000f67f  mov     qword ptr [r11-478h], 0FFFFFFFFFFFFFFFEh
0x18000f68a  mov     [r11+18h], rbx
0x18000f68e  mov     [r11+20h], rsi
0x18000f692  mov     rax, cs:__security_cookie
0x18000f699  xor     rax, rsp
0x18000f69c  mov     [rsp+4F8h+var_20], rax
0x18000f6a4  mov     rdi, rdx
0x18000f6a7  mov     rbx, rcx
0x18000f6aa  mov     [rsp+4F8h+var_4A0], rcx
0x18000f6af  mov     [rsp+4F8h+var_4A8], rdx
0x18000f6b4  xor     r15d, r15d
0x18000f6b7  mov     [rsp+4F8h+var_4B0], r15d
0x18000f6bc  cmp     dword ptr [rcx+10h], 2
0x18000f6c0  jnz     loc_18000FA90
0x18000f6c6  lea     r8, NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber
0x18000f6cd  lea     rdx, [r11-48h]
0x18000f6d1  call    ?Get@NetSetupPropertyBag@@AEBA?AV?$shared_ptr@VProperty@NetSetup2@@@std@@AEBU_NETSETUPPROPKEY@@@Z; NetSetupPropertyBag::Get(_NETSETUPPROPKEY const &)
0x18000f6d6  nop
0x18000f6d7  mov     rax, [rsp+4F8h+var_48]
0x18000f6df  mov     r9d, [rax+14h]
0x18000f6e3  cmp     r9d, 7
0x18000f6e7  jnz     loc_18000FBA3
0x18000f6ed  mov     rcx, [rax+18h]
0x18000f6f1  mov     r9, [rax+20h]
0x18000f6f5  sub     r9, rcx
0x18000f6f8  cmp     r9, 4
0x18000f6fc  jnz     loc_18000FBF7
0x18000f702  cmp     [rcx], r15d
0x18000f705  ja      loc_18000FA9F
0x18000f70b  lea     r8, NETSETUPPKEY_Interface_PnpInstance
0x18000f712  lea     rdx, [rsp+4F8h+var_58]
0x18000f71a  mov     rcx, rbx
0x18000f71d  call    ?Get@NetSetupPropertyBag@@AEBA?AV?$shared_ptr@VProperty@NetSetup2@@@std@@AEBU_NETSETUPPROPKEY@@@Z; NetSetupPropertyBag::Get(_NETSETUPPROPKEY const &)
0x18000f722  nop
0x18000f723  mov     rcx, [rsp+4F8h+var_58]
0x18000f72b  test    rcx, rcx
0x18000f72e  jz      loc_18000F9DA
0x18000f734  cmp     [rcx+14h], r15d
0x18000f738  jz      loc_18000F9DA
0x18000f73e  lea     rdx, [rsp+4F8h+Block]
0x18000f743  call    ?GetString@Property@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::Property::GetString(void)
0x18000f748  mov     rsi, rax
0x18000f74b  cmp     qword ptr [rax+18h], 8
0x18000f750  jb      short loc_18000F755
0x18000f752  mov     rsi, [rax]
0x18000f755  mov     [rsp+4F8h+pdnDevInst], r15d
0x18000f75d  mov     r8d, 1; ulFlags
0x18000f763  mov     rdx, rsi; pDeviceID
0x18000f766  lea     rcx, [rsp+4F8h+pdnDevInst]; pdnDevInst
0x18000f76e  call    cs:__imp_CM_Locate_DevNodeW
0x18000f774  mov     r14d, eax
0x18000f777  cmp     eax, 0Dh
0x18000f77a  jz      loc_18000FC9C
0x18000f780  test    eax, eax
0x18000f782  jnz     loc_18000FC4C
0x18000f788  xor     sil, sil
0x18000f78b  cmp     [rsp+4F8h+var_480], 8
0x18000f791  jnb     loc_18000FA72
0x18000f797  test    sil, sil
0x18000f79a  jnz     loc_18000FAC1
0x18000f7a0  lea     rdx, [rsp+4F8h+Block]
0x18000f7a5  mov     rcx, [rsp+4F8h+var_58]
0x18000f7ad  call    ?GetString@Property@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::Property::GetString(void)
0x18000f7b2  nop
0x18000f7b3  cmp     qword ptr [rax+18h], 8
0x18000f7b8  jb      short loc_18000F7BD
0x18000f7ba  mov     rax, [rax]
0x18000f7bd  mov     [rsp+4F8h+var_30], 0FFFFFFFFh
0x18000f7c8  mov     [rsp+4F8h+var_28], rax
0x18000f7d0  mov     r8d, 1; ulFlags
0x18000f7d6  mov     rdx, rax; pDeviceID
0x18000f7d9  lea     rcx, [rsp+4F8h+var_30]; pdnDevInst
0x18000f7e1  call    cs:__imp_CM_Locate_DevNodeW
0x18000f7e7  mov     esi, eax
0x18000f7e9  test    eax, eax
0x18000f7eb  jnz     loc_18000FCA4
0x18000f7f1  cmp     [rsp+4F8h+var_480], 8
0x18000f7f7  jnb     loc_18000FA81
0x18000f7fd  mov     [rsp+4F8h+var_4C8], 1
0x18000f805  mov     dword ptr [rsp+4F8h+lpcbData], 1
0x18000f80d  mov     byte ptr [rsp+4F8h+lpData], 0
0x18000f812  mov     r9, [rbx+28h]
0x18000f816  mov     r8d, 1
0x18000f81c  lea     rdx, [rsp+4F8h+hKey]
0x18000f821  lea     rcx, [rsp+4F8h+var_30]
0x18000f829  call    ?OpenDeviceKey@NetSetupDevice@@AEAA?AVRegistryKey@@KPEAXW4DeviceKeyFailPolicy@1@KK@Z; NetSetupDevice::OpenDeviceKey(ulong,void *,NetSetupDevice::DeviceKeyFailPolicy,ulong,ulong)
0x18000f82e  mov     [rsp+4F8h+var_4B0], 8
0x18000f836  mov     [rsp+4F8h+lpcbData], r15; lpcbData
0x18000f83b  mov     [rsp+4F8h+lpData], r15; lpData
0x18000f840  xor     r9d, r9d; lpType
0x18000f843  xor     r8d, r8d; lpReserved
0x18000f846  lea     rdx, aCharacteristic; "Characteristics"
0x18000f84d  mov     rcx, [rsp+4F8h+hKey]; hKey
0x18000f852  call    cs:__imp_RegQueryValueExW
0x18000f858  mov     ebx, eax
0x18000f85a  cmp     eax, 2
0x18000f85d  jz      loc_18000FAF6
0x18000f863  test    eax, eax
0x18000f865  jnz     loc_18000FCF8
0x18000f86b  xor     r9d, r9d
0x18000f86e  lea     rdx, aCharacteristic; "Characteristics"
0x18000f875  lea     rcx, [rsp+4F8h+hKey]
0x18000f87a  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18000f87f  mov     r14d, eax
0x18000f882  mov     ecx, 40h ; '@'; Size
0x18000f887  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f88c  mov     rbx, rax
0x18000f88f  mov     qword ptr [rsp+4F8h+pdnDevInst], rax
0x18000f897  test    rax, rax
0x18000f89a  jz      loc_18000FD55
0x18000f8a0  and     r14d, 8
0x18000f8a4  mov     dword ptr [rax+8], 1
0x18000f8ab  mov     dword ptr [rax+0Ch], 1
0x18000f8b2  lea     rax, ??_7?$_Ref_count_obj@VProperty@NetSetup2@@@std@@6B@; const std::_Ref_count_obj<NetSetup2::Property>::`vftable'
0x18000f8b9  mov     [rbx], rax
0x18000f8bc  lea     rcx, [rbx+10h]
0x18000f8c0  mov     [rsp+4F8h+var_470], rcx
0x18000f8c8  movups  xmm0, cs:NETSETUPPKEY_Driver_HideInUi
0x18000f8cf  movups  xmmword ptr [rcx], xmm0
0x18000f8d2  mov     eax, cs:dword_1800999C8
0x18000f8d8  mov     [rcx+10h], eax
0x18000f8db  lea     rsi, [rcx+18h]
0x18000f8df  mov     [rsi], r15
0x18000f8e2  mov     [rsi+8], r15
0x18000f8e6  mov     [rsi+10h], r15
0x18000f8ea  mov     dword ptr [rcx+14h], 11h
0x18000f8f1  mov     edx, 1
0x18000f8f6  mov     rcx, rsi
0x18000f8f9  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18000f8fe  test    r14d, r14d
0x18000f901  setnz   cl
0x18000f904  mov     rax, [rsi]
0x18000f907  mov     [rax], cl
0x18000f909  mov     [rdi+8], rbx
0x18000f90d  lea     rax, [rbx+10h]
0x18000f911  mov     [rdi], rax
0x18000f914  mov     rcx, [rsp+4F8h+hKey]; hKey
0x18000f919  test    rcx, rcx
0x18000f91c  jz      short loc_18000F925
0x18000f91e  call    cs:__imp_RegCloseKey
0x18000f924  nop
0x18000f925  mov     rsi, [rsp+4F8h+var_50]
0x18000f92d  mov     ebx, 0FFFFFFFFh
0x18000f932  test    rsi, rsi
0x18000f935  jz      short loc_18000F96D
0x18000f937  mov     eax, ebx
0x18000f939  lock xadd [rsi+8], eax
0x18000f93e  cmp     eax, 1
0x18000f941  jnz     short loc_18000F96D
0x18000f943  mov     rax, [rsi]
0x18000f946  mov     rcx, rsi
0x18000f949  mov     rax, [rax]
0x18000f94c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f951  mov     eax, ebx
0x18000f953  lock xadd [rsi+0Ch], eax
0x18000f958  cmp     eax, 1
0x18000f95b  jnz     short loc_18000F96D
0x18000f95d  mov     rax, [rsi]
0x18000f960  mov     rcx, rsi
0x18000f963  mov     rax, [rax+8]
0x18000f967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f96c  nop
0x18000f96d  mov     rsi, [rsp+4F8h+var_40]
0x18000f975  test    rsi, rsi
0x18000f978  jz      short loc_18000F9AE
0x18000f97a  mov     eax, ebx
0x18000f97c  lock xadd [rsi+8], eax
0x18000f981  cmp     eax, 1
0x18000f984  jnz     short loc_18000F9AE
0x18000f986  mov     rax, [rsi]
0x18000f989  mov     rcx, rsi
0x18000f98c  mov     rax, [rax]
0x18000f98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f994  lock xadd [rsi+0Ch], ebx
0x18000f999  cmp     ebx, 1
0x18000f99c  jnz     short loc_18000F9AE
0x18000f99e  mov     rax, [rsi]
0x18000f9a1  mov     rcx, rsi
0x18000f9a4  mov     rax, [rax+8]
0x18000f9a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9ad  nop
0x18000f9ae  mov     rax, rdi
0x18000f9b1  mov     rcx, [rsp+4F8h+var_20]
0x18000f9b9  xor     rcx, rsp; StackCookie
0x18000f9bc  call    __security_check_cookie
0x18000f9c1  lea     r11, [rsp+4F8h+var_18]
0x18000f9c9  mov     rbx, [r11+30h]
0x18000f9cd  mov     rsi, [r11+38h]
0x18000f9d1  mov     rsp, r11
0x18000f9d4  pop     r15
0x18000f9d6  pop     r14
0x18000f9d8  pop     rdi
0x18000f9d9  retn
0x18000f9da  mov     [rdi], r15
0x18000f9dd  mov     [rdi+8], r15
0x18000f9e1  mov     rsi, [rsp+4F8h+var_50]
0x18000f9e9  mov     ebx, 0FFFFFFFFh
0x18000f9ee  test    rsi, rsi
0x18000f9f1  jz      short loc_18000FA29
0x18000f9f3  mov     eax, ebx
0x18000f9f5  lock xadd [rsi+8], eax
0x18000f9fa  cmp     eax, 1
0x18000f9fd  jnz     short loc_18000FA29
0x18000f9ff  mov     rax, [rsi]
0x18000fa02  mov     rcx, rsi
0x18000fa05  mov     rax, [rax]
0x18000fa08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa0d  mov     eax, ebx
0x18000fa0f  lock xadd [rsi+0Ch], eax
0x18000fa14  cmp     eax, 1
0x18000fa17  jnz     short loc_18000FA29
0x18000fa19  mov     rax, [rsi]
0x18000fa1c  mov     rcx, rsi
0x18000fa1f  mov     rax, [rax+8]
0x18000fa23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa28  nop
0x18000fa29  mov     rsi, [rsp+4F8h+var_40]
0x18000fa31  test    rsi, rsi
0x18000fa34  jz      short loc_18000FA6A
0x18000fa36  mov     eax, ebx
0x18000fa38  lock xadd [rsi+8], eax
0x18000fa3d  cmp     eax, 1
0x18000fa40  jnz     short loc_18000FA6A
0x18000fa42  mov     rax, [rsi]
0x18000fa45  mov     rcx, rsi
0x18000fa48  mov     rax, [rax]
0x18000fa4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa50  lock xadd [rsi+0Ch], ebx
0x18000fa55  cmp     ebx, 1
0x18000fa58  jnz     short loc_18000FA6A
0x18000fa5a  mov     rax, [rsi]
0x18000fa5d  mov     rcx, rsi
0x18000fa60  mov     rax, [rax+8]
0x18000fa64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa69  nop
0x18000fa6a  mov     rax, rdi
0x18000fa6d  jmp     loc_18000F9B1
0x18000fa72  mov     rcx, [rsp+4F8h+Block]; Block
0x18000fa77  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fa7c  jmp     loc_18000F797
0x18000fa81  mov     rcx, [rsp+4F8h+Block]; Block
0x18000fa86  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fa8b  jmp     loc_18000F7FD
0x18000fa90  mov     [rdx], r15
0x18000fa93  mov     [rdx+8], r15
0x18000fa97  mov     rax, rdi
0x18000fa9a  jmp     loc_18000F9B1
0x18000fa9f  mov     [rdi], r15
0x18000faa2  mov     [rdi+8], r15
0x18000faa6  mov     rcx, [rsp+4F8h+var_40]; this
0x18000faae  test    rcx, rcx
0x18000fab1  jz      short loc_18000FAB9
0x18000fab3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fab8  nop
0x18000fab9  mov     rax, rdi
0x18000fabc  jmp     loc_18000F9B1
0x18000fac1  mov     [rdi], r15
0x18000fac4  mov     [rdi+8], r15
0x18000fac8  mov     rcx, [rsp+4F8h+var_50]; this
0x18000fad0  test    rcx, rcx
0x18000fad3  jz      short loc_18000FADB
0x18000fad5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fada  nop
0x18000fadb  mov     rcx, [rsp+4F8h+var_40]; this
0x18000fae3  test    rcx, rcx
0x18000fae6  jz      short loc_18000FAEE
0x18000fae8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000faed  nop
0x18000faee  mov     rax, rdi
0x18000faf1  jmp     loc_18000F9B1
0x18000faf6  mov     [rdi], r15
0x18000faf9  mov     [rdi+8], r15
0x18000fafd  mov     rcx, [rsp+4F8h+hKey]; hKey
0x18000fb02  test    rcx, rcx
0x18000fb05  jz      short loc_18000FB0E
0x18000fb07  call    cs:__imp_RegCloseKey
0x18000fb0d  nop
0x18000fb0e  mov     rcx, [rsp+4F8h+var_50]; this
0x18000fb16  test    rcx, rcx
0x18000fb19  jz      short loc_18000FB21
0x18000fb1b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fb20  nop
0x18000fb21  mov     rcx, [rsp+4F8h+var_40]; this
0x18000fb29  test    rcx, rcx
0x18000fb2c  jz      short loc_18000FB34
0x18000fb2e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fb33  nop
0x18000fb34  mov     rax, rdi
0x18000fb37  jmp     loc_18000F9B1
0x18000fb3c  mov     ecx, r14d; unsigned int
0x18000fb3f  call    ?My_CM_MapCrToWin32Err@@YAKKK@Z; My_CM_MapCrToWin32Err(ulong,ulong)
0x18000fb44  test    eax, eax
0x18000fb46  jg      loc_18000FC8F
0x18000fb4c  mov     edx, eax; int
0x18000fb4e  lea     rcx, [rsp+4F8h+pExceptionObject]; this
  ... truncated ...
```
