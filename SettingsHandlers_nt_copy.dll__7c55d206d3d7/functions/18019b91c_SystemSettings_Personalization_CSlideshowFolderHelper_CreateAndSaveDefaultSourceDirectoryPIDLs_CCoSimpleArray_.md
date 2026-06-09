# SystemSettings::Personalization::CSlideshowFolderHelper::_CreateAndSaveDefaultSourceDirectoryPIDLs(CCoSimpleArray<SystemSettings::Personalization::INDEX_PIDL_PAIR *,4294967294,CSimpleArrayStandardCompareHelper<SystemSettings::Personalization::INDEX_PIDL_PAIR *>> *)

- ea: `0x18019b91c`
- end: `0x18019baef`
- name: `?_CreateAndSaveDefaultSourceDirectoryPIDLs@CSlideshowFolderHelper@Personalization@SystemSettings@@AEAAJPEAV?$CCoSimpleArray@PEAUINDEX_PIDL_PAIR@Personalization@SystemSettings@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@PEAUINDEX_PIDL_PAIR@Personalization@SystemSettings@@@@@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::CSlideshowFolderHelper *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18019a800`

## callees

- `0x1800234f8`
- `0x18004e8d4`
- `0x180144ab8`
- `0x18019b91c`
- `0x18019c0bc`
- `0x18019c198`
- `0x1801cc7d8`
- `0x1802205e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019b9ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019bad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019b9ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019bad5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18019b97f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18019b97f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019bac4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019bac4`
- `SHELL32!SHGetKnownFolderIDList` at `0x18019ba3f`
- `SHELL32!SHGetKnownFolderIDList` at `0x18019ba93`
- `SHELL32!SHGetKnownFolderIDList` at `0x18019ba3f`
- `SHELL32!SHGetKnownFolderIDList` at `0x18019ba93`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::Personalization::CSlideshowFolderHelper::_CreateAndSaveDefaultSourceDirectoryPIDLs(
        SystemSettings::Personalization::CSlideshowFolderHelper *this,
        __int64 a2)
{
  const WCHAR *v4; // rax
  LSTATUS v5; // eax
  int v6; // ebx
  const unsigned __int16 *v7; // rax
  SystemSettings::DataModel *v8; // rax
  unsigned __int16 **v9; // r8
  const unsigned __int16 *v10; // rcx
  unsigned int v11; // esi
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+40h] BYREF
  LPITEMIDLIST ppidl; // [rsp+98h] [rbp+48h] BYREF

  hKey = 0;
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 536);
  v5 = RegCreateKeyExW(HKEY_CURRENT_USER, v4, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
    v7 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 568);
    v6 = SHRegSetBOOL(hKey, 0, v7, 1);
    pv = 0;
    CoTaskMemFree(0);
    v8 = (SystemSettings::DataModel *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 632);
    if ( (int)SystemSettings::DataModel::GetCurrentProcessDefaultSettingsIdentifier(
                v8,
                (const unsigned __int16 *)&pv,
                v9) >= 0 )
      ClearLastVisitedFolder(v10, (const unsigned __int16 *)pv);
    if ( v6 >= 0 )
    {
      v6 = SystemSettings::Personalization::CSlideshowFolderHelper::_RemoveSourceDirectoriesFromRegistry(this, hKey);
      if ( v6 >= 0 )
      {
        v11 = 0;
        if ( (unsigned int)IsOS_OS_ANYSERVER()
          || (ppidl = 0, SHGetKnownFolderIDList(&FOLDERID_SkyDrivePictures, 0x1000u, 0, &ppidl) < 0)
          || (v6 = SystemSettings::Personalization::CSlideshowFolderHelper::_SaveDefaultSourceDirectoryPIDLs(
                     this,
                     hKey,
                     &ppidl,
                     1,
                     a2),
              v11 = 1,
              v6 >= 0) )
        {
          if ( v11 < *((_DWORD *)this + 190) )
          {
            ppidl = 0;
            v6 = SHGetKnownFolderIDList(&FOLDERID_PicturesLibrary, 0, 0, &ppidl);
            if ( v6 >= 0 )
              v6 = SystemSettings::Personalization::CSlideshowFolderHelper::_SaveDefaultSourceDirectoryPIDLs(
                     this,
                     hKey,
                     &ppidl,
                     v11 + 1,
                     a2);
          }
        }
      }
    }
    RegCloseKey(hKey);
    CoTaskMemFree(pv);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18019b91c  push    rbp
0x18019b91e  push    rbx
0x18019b91f  push    rsi
0x18019b920  push    rdi
0x18019b921  push    r14
0x18019b923  mov     rbp, rsp
0x18019b926  sub     rsp, 50h
0x18019b92a  mov     r14, rdx
0x18019b92d  mov     rdi, rcx
0x18019b930  mov     [rbp+hKey], 0
0x18019b938  add     rcx, 218h
0x18019b93f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18019b944  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x18019b94d  lea     rcx, [rbp+hKey]
0x18019b951  mov     [rsp+50h+phkResult], rcx; phkResult
0x18019b956  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18019b95f  mov     [rsp+50h+samDesired], 20006h; samDesired
0x18019b967  mov     [rsp+50h+dwOptions], 0; dwOptions
0x18019b96f  xor     r9d, r9d; lpClass
0x18019b972  xor     r8d, r8d; Reserved
0x18019b975  mov     rdx, rax; lpSubKey
0x18019b978  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18019b97f  call    cs:__imp_RegCreateKeyExW
0x18019b986  nop     dword ptr [rax+rax+00h]
0x18019b98b  mov     ebx, eax
0x18019b98d  test    eax, eax
0x18019b98f  jle     short loc_18019B99A
0x18019b991  movzx   ebx, ax
0x18019b994  or      ebx, 80070000h
0x18019b99a  test    ebx, ebx
0x18019b99c  js      loc_18019BAE1
0x18019b9a2  lea     rcx, [rdi+238h]
0x18019b9a9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18019b9ae  mov     r9d, 1; int
0x18019b9b4  mov     r8, rax; unsigned __int16 *
0x18019b9b7  xor     edx, edx; unsigned __int16 *
0x18019b9b9  mov     rcx, [rbp+hKey]; HKEY
0x18019b9bd  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18019b9c2  mov     ebx, eax
0x18019b9c4  mov     [rbp+pv], 0
0x18019b9cc  xor     ecx, ecx; pv
0x18019b9ce  call    cs:__imp_CoTaskMemFree
0x18019b9d5  nop     dword ptr [rax+rax+00h]
0x18019b9da  lea     rcx, [rdi+278h]
0x18019b9e1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18019b9e6  lea     rdx, [rbp+pv]; unsigned __int16 *
0x18019b9ea  mov     rcx, rax; this
0x18019b9ed  call    ?GetCurrentProcessDefaultSettingsIdentifier@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z; SystemSettings::DataModel::GetCurrentProcessDefaultSettingsIdentifier(ushort const *,ushort * *)
0x18019b9f2  test    eax, eax
0x18019b9f4  js      short loc_18019B9FF
0x18019b9f6  mov     rdx, [rbp+pv]; unsigned __int16 *
0x18019b9fa  call    ?ClearLastVisitedFolder@@YAJPEBG0@Z; ClearLastVisitedFolder(ushort const *,ushort const *)
0x18019b9ff  test    ebx, ebx
0x18019ba01  js      loc_18019BAC0
0x18019ba07  mov     rdx, [rbp+hKey]; HKEY
0x18019ba0b  mov     rcx, rdi; this
0x18019ba0e  call    ?_RemoveSourceDirectoriesFromRegistry@CSlideshowFolderHelper@Personalization@SystemSettings@@AEAAJPEAUHKEY__@@@Z; SystemSettings::Personalization::CSlideshowFolderHelper::_RemoveSourceDirectoriesFromRegistry(HKEY__ *)
0x18019ba13  mov     ebx, eax
0x18019ba15  test    eax, eax
0x18019ba17  js      loc_18019BAC0
0x18019ba1d  xor     esi, esi
0x18019ba1f  call    ?IsOS_OS_ANYSERVER@@YAHXZ; IsOS_OS_ANYSERVER(void)
0x18019ba24  test    eax, eax
0x18019ba26  jnz     short loc_18019BA73
0x18019ba28  mov     [rbp+ppidl], rsi
0x18019ba2c  lea     r9, [rbp+ppidl]; ppidl
0x18019ba30  xor     r8d, r8d; hToken
0x18019ba33  mov     edx, 1000h; dwFlags
0x18019ba38  lea     rcx, FOLDERID_SkyDrivePictures; rfid
0x18019ba3f  call    cs:__imp_SHGetKnownFolderIDList
0x18019ba46  nop     dword ptr [rax+rax+00h]
0x18019ba4b  test    eax, eax
0x18019ba4d  js      short loc_18019BA73
0x18019ba4f  mov     qword ptr [rsp+50h+dwOptions], r14
0x18019ba54  lea     r9d, [rsi+1]
0x18019ba58  lea     r8, [rbp+ppidl]
0x18019ba5c  mov     rdx, [rbp+hKey]
0x18019ba60  mov     rcx, rdi
0x18019ba63  call    ?_SaveDefaultSourceDirectoryPIDLs@CSlideshowFolderHelper@Personalization@SystemSettings@@AEAAJPEAUHKEY__@@PEAPEFAU_ITEMIDLIST@@IPEAV?$CCoSimpleArray@PEAUINDEX_PIDL_PAIR@Personalization@SystemSettings@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@PEAUINDEX_PIDL_PAIR@Personalization@SystemSettings@@@@@@@Z; SystemSettings::Personalization::CSlideshowFolderHelper::_SaveDefaultSourceDirectoryPIDLs(HKEY__ *,_ITEMIDLIST * *,uint,CCoSimpleArray<SystemSettings::Personalization::INDEX_PIDL_PAIR *,4294967294,CSimpleArrayStandardCompareHelper<SystemSettings::Personalization::INDEX_PIDL_PAIR *>> *)
0x18019ba68  mov     ebx, eax
0x18019ba6a  mov     esi, 1
0x18019ba6f  test    eax, eax
0x18019ba71  js      short loc_18019BAC0
0x18019ba73  cmp     esi, [rdi+2F8h]
0x18019ba79  jnb     short loc_18019BAC0
0x18019ba7b  mov     [rbp+ppidl], 0
0x18019ba83  lea     r9, [rbp+ppidl]; ppidl
0x18019ba87  xor     r8d, r8d; hToken
0x18019ba8a  xor     edx, edx; dwFlags
0x18019ba8c  lea     rcx, FOLDERID_PicturesLibrary; rfid
0x18019ba93  call    cs:__imp_SHGetKnownFolderIDList
0x18019ba9a  nop     dword ptr [rax+rax+00h]
0x18019ba9f  mov     ebx, eax
0x18019baa1  test    eax, eax
0x18019baa3  js      short loc_18019BAC0
0x18019baa5  lea     r9d, [rsi+1]
0x18019baa9  mov     qword ptr [rsp+50h+dwOptions], r14
0x18019baae  lea     r8, [rbp+ppidl]
0x18019bab2  mov     rdx, [rbp+hKey]
0x18019bab6  mov     rcx, rdi
0x18019bab9  call    ?_SaveDefaultSourceDirectoryPIDLs@CSlideshowFolderHelper@Personalization@SystemSettings@@AEAAJPEAUHKEY__@@PEAPEFAU_ITEMIDLIST@@IPEAV?$CCoSimpleArray@PEAUINDEX_PIDL_PAIR@Personalization@SystemSettings@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@PEAUINDEX_PIDL_PAIR@Personalization@SystemSettings@@@@@@@Z; SystemSettings::Personalization::CSlideshowFolderHelper::_SaveDefaultSourceDirectoryPIDLs(HKEY__ *,_ITEMIDLIST * *,uint,CCoSimpleArray<SystemSettings::Personalization::INDEX_PIDL_PAIR *,4294967294,CSimpleArrayStandardCompareHelper<SystemSettings::Personalization::INDEX_PIDL_PAIR *>> *)
0x18019babe  mov     ebx, eax
0x18019bac0  mov     rcx, [rbp+hKey]; hKey
0x18019bac4  call    cs:__imp_RegCloseKey
0x18019bacb  nop     dword ptr [rax+rax+00h]
0x18019bad0  nop
0x18019bad1  mov     rcx, [rbp+pv]; pv
0x18019bad5  call    cs:__imp_CoTaskMemFree
0x18019badc  nop     dword ptr [rax+rax+00h]
0x18019bae1  mov     eax, ebx
0x18019bae3  add     rsp, 50h
0x18019bae7  pop     r14
0x18019bae9  pop     rdi
0x18019baea  pop     rsi
0x18019baeb  pop     rbx
0x18019baec  pop     rbp
0x18019baed  retn
```
