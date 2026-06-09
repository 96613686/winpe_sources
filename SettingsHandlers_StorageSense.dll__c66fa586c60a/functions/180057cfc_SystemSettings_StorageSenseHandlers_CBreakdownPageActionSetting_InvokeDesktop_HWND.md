# SystemSettings::StorageSenseHandlers::CBreakdownPageActionSetting::InvokeDesktop(HWND__ *)

- ea: `0x180057cfc`
- end: `0x180058007`
- name: `?InvokeDesktop@CBreakdownPageActionSetting@StorageSenseHandlers@SystemSettings@@AEAAJPEAUHWND__@@@Z`
- size: `779`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CBreakdownPageActionSetting *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800579e0`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x18000e6cc`
- `0x180057cfc`
- `0x18005c60c`
- `0x1800b48f4`
- `0x1800b4994`
- `0x1800c12d0`
- `0x1800c15d4`

## import_xrefs

- `ext-ms-win-storage-sense-l1-1-0!GetStorageExecutionInfo` at `0x180057e01`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageExecutionInfo` at `0x180057e01`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180057ef4`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180057ef4`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180057f9d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180057f9d`

## string_xrefs

- `0x180057d35`: `shell32.dll,Control_RunDLL sysdm.cpl,,4`
- `0x180057d3c`: `rundll32.exe`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::CBreakdownPageActionSetting::InvokeDesktop(
        SystemSettings::StorageSenseHandlers::CBreakdownPageActionSetting *this,
        HWND a2,
        const unsigned __int16 *a3)
{
  int v3; // eax
  struct _ITEMIDLIST *v5; // r9
  WCHAR *v6; // rdx
  const GUID *v7; // rcx
  unsigned int *v8; // r8
  __int64 v9; // rcx
  int v10; // eax
  HRESULT StorageExecutionInfo; // edi
  __int64 v12; // rcx
  const unsigned __int16 *v13; // rdx
  HRESULT v14; // eax
  SystemSettings::StorageSenseHandlers::ExecutionHelpers *v15; // rcx
  const unsigned __int16 *v16; // r8
  int pszPath; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v19; // [rsp+28h] [rbp-D8h]
  PWSTR ppszPath; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h]
  __int64 v22; // [rsp+40h] [rbp-C0h]
  int v23[2]; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v24[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR sourceString[260]; // [rsp+58h] [rbp-A8h] BYREF
  char v26; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  v3 = *((_DWORD *)this + 66);
  switch ( v3 )
  {
    case 5:
      v5 = (struct _ITEMIDLIST *)L"shell32.dll,Control_RunDLL sysdm.cpl,,4";
      v6 = (WCHAR *)L"rundll32.exe";
LABEL_20:
      v14 = SystemSettings::StorageSenseHandlers::ExecutionHelpers::LaunchOnDesktop(this, (HWND)v6, a3, v5, 0, v19);
      goto LABEL_21;
    case 12:
      ppszPath = 0;
      v21 = 0;
      v22 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
      v7 = &FOLDERID_OneDrive;
LABEL_26:
      v21 = -1;
      v22 = -1;
      StorageExecutionInfo = SHGetKnownFolderPath(v7, 0, 0, &ppszPath);
      if ( StorageExecutionInfo >= 0 )
        StorageExecutionInfo = SystemSettings::StorageSenseHandlers::ExecutionHelpers::LaunchOnDesktop(
                                 v15,
                                 (HWND)ppszPath,
                                 v16,
                                 0,
                                 0,
                                 v19);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
      return (unsigned int)StorageExecutionInfo;
    case 10:
      memset_0(v24, 0, 0x418u);
      v8 = (unsigned int *)*((_QWORD *)this + 34);
      *(_QWORD *)v23 = 0;
      v10 = SystemSettings::StorageSenseHandlers::CStorSvcHandler::Get(v9, 2, *v8, v8[1], v23);
      StorageExecutionInfo = v10;
      if ( v10 >= 0 )
      {
        wcscpy((wchar_t *)v24, L"И");
        StorageExecutionInfo = GetStorageExecutionInfo(*(_QWORD *)v23, 12, v24);
        SystemSettings::StorageSenseHandlers::CStorSvcHandler::ClearHandleInUseState(
          v12,
          2,
          **((unsigned int **)this + 34),
          *(unsigned int *)(*((_QWORD *)this + 34) + 4LL));
        if ( StorageExecutionInfo >= 0 )
        {
          if ( v24[1] == 1 )
          {
            v5 = (struct _ITEMIDLIST *)&v26;
            v6 = sourceString;
            goto LABEL_20;
          }
          if ( v24[1] == 2 )
          {
            v14 = SystemSettings::StorageSenseHandlers::ExecutionHelpers::LaunchUri(sourceString, v13);
LABEL_21:
            StorageExecutionInfo = v14;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x81D,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\breakdownpages.cpp",
          (const char *)(unsigned int)v10,
          pszPath);
      }
      break;
    case 11:
      ppszPath = 0;
      v21 = 0;
      v22 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
      v7 = &FOLDERID_LocalDocuments;
      goto LABEL_26;
    case 7:
      ppszPath = 0;
      v21 = 0;
      v22 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
      v7 = &FOLDERID_LocalPictures;
      goto LABEL_26;
    case 9:
      memset_0(v24, 0, 0x208u);
      StorageExecutionInfo = SHGetFolderPathW(0, 14, 0, 0, (LPWSTR)v24);
      if ( StorageExecutionInfo >= 0 )
      {
        v5 = 0;
        v6 = (WCHAR *)v24;
        goto LABEL_20;
      }
      break;
    case 8:
      ppszPath = 0;
      v21 = 0;
      v22 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
      v7 = &FOLDERID_LocalMusic;
      goto LABEL_26;
    case 14:
      ppszPath = 0;
      v21 = 0;
      v22 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
      v7 = &FOLDERID_Desktop;
      goto LABEL_26;
    default:
      if ( v3 == 15 || (StorageExecutionInfo = -2147024809, v3 == 24) )
        StorageExecutionInfo = -2147467263;
      break;
  }
  return (unsigned int)StorageExecutionInfo;
}

```

## disassembly

```asm
0x180057cfc  mov     [rsp-8+arg_8], rsi
0x180057d01  mov     [rsp-8+arg_10], rdi
0x180057d06  push    rbp
0x180057d07  lea     rbp, [rsp-380h]
0x180057d0f  sub     rsp, 480h
0x180057d16  mov     rax, cs:__security_cookie
0x180057d1d  xor     rax, rsp
0x180057d20  mov     [rbp+380h+var_10], rax
0x180057d27  mov     eax, [rcx+108h]
0x180057d2d  mov     rsi, rcx
0x180057d30  cmp     eax, 5
0x180057d33  jnz     short loc_180057D48
0x180057d35  lea     r9, aShell32DllCont; "shell32.dll,Control_RunDLL sysdm.cpl,,4"
0x180057d3c  lea     rdx, aRundll32Exe; "rundll32.exe"
0x180057d43  jmp     loc_180057F0C
0x180057d48  cmp     eax, 0Ch
0x180057d4b  jnz     short loc_180057D7E
0x180057d4d  lea     rcx, [rsp+480h+ppszPath]
0x180057d52  mov     [rsp+480h+ppszPath], 0
0x180057d5b  mov     [rsp+480h+var_448], 0
0x180057d64  mov     [rsp+480h+var_440], 0
0x180057d6d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180057d72  lea     rcx, FOLDERID_OneDrive
0x180057d79  jmp     loc_180057F85
0x180057d7e  cmp     eax, 0Ah
0x180057d81  jnz     loc_180057E5B
0x180057d87  xor     edx, edx; Val
0x180057d89  lea     rcx, [rsp+480h+var_430]; void *
0x180057d8e  mov     r8d, 418h; Size
0x180057d94  call    memset_0
0x180057d99  mov     r8, [rsi+110h]
0x180057da0  lea     rax, [rsp+480h+var_438]
0x180057da5  mov     qword ptr [rsp+480h+var_438], 0
0x180057dae  mov     edx, 2
0x180057db3  mov     [rsp+480h+pszPath], rax; int
0x180057db8  mov     r9d, [r8+4]
0x180057dbc  mov     r8d, [r8]
0x180057dbf  call    ?Get@CStorSvcHandler@StorageSenseHandlers@SystemSettings@@QEAAJW4_STORAGE_SELECTVOL_FLAGS@@W4_STORAGE_DEVICE_TYPE@@KPEAPEAX@Z; SystemSettings::StorageSenseHandlers::CStorSvcHandler::Get(_STORAGE_SELECTVOL_FLAGS,_STORAGE_DEVICE_TYPE,ulong,void * *)
0x180057dc4  mov     edi, eax
0x180057dc6  test    eax, eax
0x180057dc8  jns     short loc_180057DEA
0x180057dca  mov     rcx, [rbp+388h]; this
0x180057dd1  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\coresettinghandlers"...
0x180057dd8  mov     r9d, eax; char *
0x180057ddb  mov     edx, 81Dh; void *
0x180057de0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057de5  jmp     loc_180057FE1
0x180057dea  mov     rcx, qword ptr [rsp+480h+var_438]
0x180057def  lea     r8, [rsp+480h+var_430]
0x180057df4  mov     edx, 0Ch
0x180057df9  mov     dword ptr [rsp+480h+var_430], 418h
0x180057e01  call    cs:__imp_GetStorageExecutionInfo
0x180057e07  mov     r8, [rsi+110h]
0x180057e0e  mov     edx, 2
0x180057e13  mov     edi, eax
0x180057e15  mov     r9d, [r8+4]
0x180057e19  mov     r8d, [r8]
0x180057e1c  call    ?ClearHandleInUseState@CStorSvcHandler@StorageSenseHandlers@SystemSettings@@QEAAJW4_STORAGE_SELECTVOL_FLAGS@@W4_STORAGE_DEVICE_TYPE@@K@Z; SystemSettings::StorageSenseHandlers::CStorSvcHandler::ClearHandleInUseState(_STORAGE_SELECTVOL_FLAGS,_STORAGE_DEVICE_TYPE,ulong)
0x180057e21  test    edi, edi
0x180057e23  js      loc_180057FE1
0x180057e29  cmp     dword ptr [rsp+480h+var_430+4], 1
0x180057e2e  jnz     short loc_180057E41
0x180057e30  lea     r9, [rbp+380h+var_220]
0x180057e37  lea     rdx, [rsp+480h+sourceString]
0x180057e3c  jmp     loc_180057F0C
0x180057e41  cmp     dword ptr [rsp+480h+var_430+4], 2
0x180057e46  jnz     loc_180057FE1
0x180057e4c  lea     rcx, [rsp+480h+sourceString]; sourceString
0x180057e51  call    ?LaunchUri@ExecutionHelpers@StorageSenseHandlers@SystemSettings@@YAJPEBG@Z; SystemSettings::StorageSenseHandlers::ExecutionHelpers::LaunchUri(ushort const *)
0x180057e56  jmp     loc_180057F1A
0x180057e5b  cmp     eax, 0Bh
0x180057e5e  jnz     short loc_180057E91
0x180057e60  lea     rcx, [rsp+480h+ppszPath]
0x180057e65  mov     [rsp+480h+ppszPath], 0
0x180057e6e  mov     [rsp+480h+var_448], 0
0x180057e77  mov     [rsp+480h+var_440], 0
0x180057e80  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180057e85  lea     rcx, FOLDERID_LocalDocuments
0x180057e8c  jmp     loc_180057F85
0x180057e91  cmp     eax, 7
0x180057e94  jnz     short loc_180057EC7
0x180057e96  lea     rcx, [rsp+480h+ppszPath]
0x180057e9b  mov     [rsp+480h+ppszPath], 0
0x180057ea4  mov     [rsp+480h+var_448], 0
0x180057ead  mov     [rsp+480h+var_440], 0
0x180057eb6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180057ebb  lea     rcx, FOLDERID_LocalPictures
0x180057ec2  jmp     loc_180057F85
0x180057ec7  cmp     eax, 9
0x180057eca  jnz     short loc_180057F21
0x180057ecc  xor     edx, edx; Val
0x180057ece  lea     rcx, [rsp+480h+var_430]; void *
0x180057ed3  mov     r8d, 208h; Size
0x180057ed9  call    memset_0
0x180057ede  xor     r9d, r9d; dwFlags
0x180057ee1  lea     rax, [rsp+480h+var_430]
0x180057ee6  xor     r8d, r8d; hToken
0x180057ee9  mov     [rsp+480h+pszPath], rax; pszPath
0x180057eee  xor     ecx, ecx; hwnd
0x180057ef0  lea     edx, [r9+0Eh]; csidl
0x180057ef4  call    cs:__imp_SHGetFolderPathW
0x180057efa  mov     edi, eax
0x180057efc  test    eax, eax
0x180057efe  js      loc_180057FE1
0x180057f04  xor     r9d, r9d; struct _ITEMIDLIST *
0x180057f07  lea     rdx, [rsp+480h+var_430]; HWND
0x180057f0c  mov     [rsp+480h+pszPath], 0; unsigned __int16 *
0x180057f15  call    ?LaunchOnDesktop@ExecutionHelpers@StorageSenseHandlers@SystemSettings@@YAJPEAUHWND__@@PEBGPEFAU_ITEMIDLIST@@11@Z; SystemSettings::StorageSenseHandlers::ExecutionHelpers::LaunchOnDesktop(HWND__ *,ushort const *,_ITEMIDLIST *,ushort const *,ushort const *)
0x180057f1a  mov     edi, eax
0x180057f1c  jmp     loc_180057FE1
0x180057f21  cmp     eax, 8
0x180057f24  jnz     short loc_180057F54
0x180057f26  lea     rcx, [rsp+480h+ppszPath]
0x180057f2b  mov     [rsp+480h+ppszPath], 0
0x180057f34  mov     [rsp+480h+var_448], 0
0x180057f3d  mov     [rsp+480h+var_440], 0
0x180057f46  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180057f4b  lea     rcx, FOLDERID_LocalMusic
0x180057f52  jmp     short loc_180057F85
0x180057f54  cmp     eax, 0Eh
0x180057f57  jnz     short loc_180057FCD
0x180057f59  lea     rcx, [rsp+480h+ppszPath]
0x180057f5e  mov     [rsp+480h+ppszPath], 0
0x180057f67  mov     [rsp+480h+var_448], 0
0x180057f70  mov     [rsp+480h+var_440], 0
0x180057f79  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180057f7e  lea     rcx, FOLDERID_Desktop; rfid
0x180057f85  or      rax, 0FFFFFFFFFFFFFFFFh
0x180057f89  lea     r9, [rsp+480h+ppszPath]; ppszPath
0x180057f8e  xor     r8d, r8d; hToken
0x180057f91  mov     [rsp+480h+var_448], rax
0x180057f96  xor     edx, edx; dwFlags
0x180057f98  mov     [rsp+480h+var_440], rax
0x180057f9d  call    cs:__imp_SHGetKnownFolderPath
0x180057fa3  mov     edi, eax
0x180057fa5  test    eax, eax
0x180057fa7  js      short loc_180057FC1
0x180057fa9  mov     rdx, [rsp+480h+ppszPath]; HWND
0x180057fae  xor     r9d, r9d; struct _ITEMIDLIST *
0x180057fb1  mov     [rsp+480h+pszPath], 0; unsigned __int16 *
0x180057fba  call    ?LaunchOnDesktop@ExecutionHelpers@StorageSenseHandlers@SystemSettings@@YAJPEAUHWND__@@PEBGPEFAU_ITEMIDLIST@@11@Z; SystemSettings::StorageSenseHandlers::ExecutionHelpers::LaunchOnDesktop(HWND__ *,ushort const *,_ITEMIDLIST *,ushort const *,ushort const *)
0x180057fbf  mov     edi, eax
0x180057fc1  lea     rcx, [rsp+480h+ppszPath]
0x180057fc6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180057fcb  jmp     short loc_180057FE1
0x180057fcd  cmp     eax, 0Fh
0x180057fd0  jz      short loc_180057FDC
0x180057fd2  mov     edi, 80070057h
0x180057fd7  cmp     eax, 18h
0x180057fda  jnz     short loc_180057FE1
0x180057fdc  mov     edi, 80004001h
0x180057fe1  mov     eax, edi
0x180057fe3  mov     rcx, [rbp+380h+var_10]
0x180057fea  xor     rcx, rsp; StackCookie
0x180057fed  call    __security_check_cookie
0x180057ff2  lea     r11, [rsp+480h+var_s0]
0x180057ffa  mov     rsi, [r11+18h]
0x180057ffe  mov     rdi, [r11+20h]
0x180058002  mov     rsp, r11
0x180058005  pop     rbp
0x180058006  retn
```
