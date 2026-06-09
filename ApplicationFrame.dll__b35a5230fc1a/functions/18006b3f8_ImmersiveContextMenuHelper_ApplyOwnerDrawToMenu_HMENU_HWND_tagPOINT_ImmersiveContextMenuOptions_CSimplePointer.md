# ImmersiveContextMenuHelper::ApplyOwnerDrawToMenu(HMENU__ *,HWND__ *,tagPOINT *,ImmersiveContextMenuOptions,CSimplePointerArrayNewMem<ContextMenuRenderingData,CSimpleArrayStandardCompareHelper<ContextMenuRenderingData *>> &)

- ea: `0x18006b3f8`
- end: `0x18006b7ef`
- name: `?ApplyOwnerDrawToMenu@ImmersiveContextMenuHelper@@YAJPEAUHMENU__@@PEAUHWND__@@PEAUtagPOINT@@W4ImmersiveContextMenuOptions@@AEAV?$CSimplePointerArrayNewMem@UContextMenuRenderingData@@V?$CSimpleArrayStandardCompareHelper@PEAUContextMenuRenderingData@@@@@@@Z`
- size: `1015`
- prototype: `__int64 __fastcall(int, int, int, int, HANDLE hData)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003f930`
- `0x18006b3f8`
- `0x18006ba70`

## callees

- `0x18001e260`
- `0x1800206e8`
- `0x180041ec0`
- `0x180043c30`
- `0x1800446fc`
- `0x18005e99c`
- `0x180067c88`
- `0x18006b3f8`
- `0x18006b7f8`
- `0x18006b984`
- `0x18006ba70`
- `0x18006bc2c`
- `0x18006bd5c`
- `0x18006bf78`
- `0x18006bfec`
- `0x18006c078`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x18006b4c6`
- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x18006b4c6`
- `ext-ms-win-ntuser-window-l1-1-4!GetMessageExtraInfo` at `0x18006b479`
- `ext-ms-win-ntuser-window-l1-1-4!GetMessageExtraInfo` at `0x18006b479`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18006b502`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18006b502`
- `USER32!GetMenuItemInfoW` at `0x18006b566`
- `USER32!GetMenuItemInfoW` at `0x18006b566`
- `USER32!GetCurrentInputMessageSource` at `0x18006b468`
- `USER32!GetCurrentInputMessageSource` at `0x18006b468`
- `USER32!SetMenuItemInfoW` at `0x18006b707`
- `USER32!SetMenuItemInfoW` at `0x18006b707`

## pseudocode

```c
__int64 __fastcall ImmersiveContextMenuHelper::ApplyOwnerDrawToMenu(
        HMENU a1,
        HWND a2,
        HWND a3,
        unsigned int a4,
        _QWORD *hData)
{
  INPUT_MESSAGE_DEVICE_TYPE deviceType; // esi
  signed int Error; // ebx
  HWND v10; // r8
  _DWORD *v11; // rdi
  unsigned int v12; // r9d
  struct ContextMenuRenderingData *ContextMenuDataForItem; // rax
  HWND v14; // rsi
  __int64 v15; // rdx
  unsigned int v16; // edx
  HWND *v17; // rdx
  HWND dwItemData; // rdx
  unsigned int v19; // ecx
  struct ContextMenuRenderingData *v21; // [rsp+20h] [rbp-E0h]
  char v22; // [rsp+40h] [rbp-C0h]
  INPUT_MESSAGE_SOURCE inputMessageSource; // [rsp+48h] [rbp-B8h] BYREF
  int pvParam; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+54h] [rbp-ACh]
  HWND v26; // [rsp+58h] [rbp-A8h] BYREF
  int v27[4]; // [rsp+60h] [rbp-A0h]
  tagMENUITEMINFOW mii; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpString[4]; // [rsp+C0h] [rbp-40h] BYREF
  MENUITEMINFOW v30; // [rsp+E0h] [rbp-20h] BYREF
  tagMENUITEMINFOW v31; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v32[528]; // [rsp+180h] [rbp+80h] BYREF

  deviceType = IMDT_UNAVAILABLE;
  *(_QWORD *)v27 = a3;
  v25 = a4 & 2;
  if ( (a4 & 2) == 0 )
  {
    Error = 1;
    if ( !ImmersiveContextMenuHelper::CanApplyOwnerDrawToMenu(a1, (HMENU)a2, a3) )
      return (unsigned int)Error;
  }
  if ( (a4 & 4) == 0
    && (inputMessageSource = 0, GetCurrentInputMessageSource(&inputMessageSource))
    && inputMessageSource.deviceType == IMDT_TOUCH
    || (v22 = 0, (GetMessageExtraInfo() & 0xFF515780LL) == 0xFF515780LL) )
  {
    v22 = 1;
  }
  memset(lpString, 0, 24);
  Error = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            (__int64)lpString,
            L"ImmersiveContextMenuArray_%lu",
            0xFFFFFFFFLL);
  if ( Error >= 0 )
    Error = !SetPropW(a2, lpString[0], hData) ? 0x80004005 : 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)lpString);
  byte_180091FF1 = ImmersiveContextMenuHelper::ShouldUseDarkTheme(a4);
  pvParam = 0;
  SystemParametersInfoW(0x100Au, 0, &pvParam, 0);
  v11 = 0;
  while ( 1 )
  {
    inputMessageSource.deviceType = deviceType;
    if ( Error < 0 )
      break;
    memset_0(&mii, 0, sizeof(mii));
    mii.cbSize = 80;
    mii.fMask = 495;
    memset_0(v32, 0, 0x208u);
    mii.cch = 260;
    mii.dwTypeData = (LPWSTR)v32;
    if ( GetMenuItemInfoW(a1, deviceType, 1, &mii) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_42;
    }
    ContextMenuDataForItem = ImmersiveContextMenuHelper::GetContextMenuDataForItem(
                               a2,
                               (HWND)mii.dwItemData,
                               mii.wID,
                               v12);
    v11 = ContextMenuDataForItem;
    if ( (mii.fType & 0x100) != 0 && mii.dwItemData )
      goto LABEL_38;
    if ( !ContextMenuDataForItem || v22 != ((*((_DWORD *)ContextMenuDataForItem + 14) & 4) != 0) )
    {
      v26 = 0;
      v31 = mii;
      Error = ImmersiveContextMenuHelper::_GetRenderingDataForMenuItem(
                a4 & 1,
                (unsigned int)&v31,
                (unsigned int)v32,
                v27[0],
                (__int64)hData,
                (__int64)ContextMenuDataForItem,
                a4,
                (unsigned int)&v26);
      if ( Error >= 0 )
      {
        v14 = v26;
        *((_DWORD *)v26 + 18) = pvParam;
        v15 = hData[1];
        if ( v15 == hData[3] )
        {
          Error = CTSimpleArray<unsigned short *,4294967294,CTPolicyCoTaskMem<unsigned short *>,CSimpleArrayStandardCompareHelper<unsigned short *>,CSimpleArrayStandardMergeHelper<unsigned short *>>::_EnsureCapacity(
                    hData,
                    v15 + 1);
          if ( Error < 0 )
          {
            if ( v14 )
              ContextMenuRenderingData::`scalar deleting destructor'((ContextMenuRenderingData *)v14, v16);
            goto LABEL_37;
          }
        }
        v17 = (HWND *)(*hData + 8 * hData[1]++);
        if ( v17 )
          *v17 = v14;
        memset_0(&v30, 0, sizeof(v30));
        dwItemData = (HWND)mii.dwItemData;
        v30.hbmpChecked = mii.hbmpChecked;
        v30.hbmpUnchecked = mii.hbmpUnchecked;
        v30.cbSize = 80;
        v30.fMask = 392;
        v30.hbmpItem = 0;
        v30.fType = mii.fType | 0x100;
        if ( !mii.dwItemData )
        {
          v30.fMask = 424;
          dwItemData = v14;
          v30.dwItemData = (ULONG_PTR)v14;
        }
        Error = ImmersiveContextMenuHelper::StoreContextMenuDataForItem(a2, dwItemData, mii.wID, (unsigned int)v14, v21);
        if ( Error >= 0 )
        {
          if ( SetMenuItemInfoW(a1, inputMessageSource.deviceType, 1, &v30) )
          {
            Error = 0;
LABEL_31:
            if ( mii.hSubMenu )
            {
              if ( v25 )
                ImmersiveContextMenuHelper::HandleMergedMenus(
                  (ImmersiveContextMenuHelper *)mii.hSubMenu,
                  (HMENU)a2,
                  v10);
              else
                ImmersiveContextMenuHelper::ApplyOwnerDrawToMenu((int)mii.hSubMenu, (int)a2, v27[0], a4 | 0x10, hData);
            }
          }
          else
          {
            Error = ResultFromKnownLastError();
            if ( Error >= 0 )
              goto LABEL_31;
          }
        }
        v11 = v14;
        *((_QWORD *)v14 + 10) = hData;
        if ( v22 )
          *((_DWORD *)v14 + 14) |= 4u;
LABEL_37:
        deviceType = inputMessageSource.deviceType;
      }
LABEL_38:
      if ( !v11 )
        goto LABEL_42;
    }
    v19 = v11[14] | 1;
    if ( deviceType )
      v19 = v11[14] & 0xFFFFFFFE;
    v11[14] = v19 & 0xFFFFFFFD;
LABEL_42:
    ++deviceType;
  }
  if ( Error == -2147023440 && hData[1] )
  {
    Error = 0;
    if ( v11 )
      v11[14] |= 2u;
    if ( (a4 & 0x10) == 0 )
      ImmersiveContextMenuHelper::OverrideBackgroundColor(a1, a2, a4);
  }
  else
  {
    ImmersiveContextMenuHelper::RemoveOwnerDrawFromMenu(a1, (HMENU)a2, v10);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18006b3f8  push    rbp
0x18006b3fa  push    rbx
0x18006b3fb  push    rsi
0x18006b3fc  push    rdi
0x18006b3fd  push    r12
0x18006b3ff  push    r13
0x18006b401  push    r14
0x18006b403  push    r15
0x18006b405  lea     rbp, [rsp-2A8h]
0x18006b40d  sub     rsp, 3A8h
0x18006b414  mov     rax, cs:__security_cookie
0x18006b41b  xor     rax, rsp
0x18006b41e  mov     [rbp+2E0h+var_50], rax
0x18006b425  mov     r14, [rbp+2E0h+hData]
0x18006b42c  mov     eax, r9d
0x18006b42f  xor     esi, esi
0x18006b431  mov     qword ptr [rsp+3E0h+var_380], r8
0x18006b436  and     eax, 2
0x18006b439  mov     r12d, r9d
0x18006b43c  mov     [rsp+3E0h+var_38C], eax
0x18006b440  mov     r15, rdx
0x18006b443  mov     r13, rcx
0x18006b446  jnz     short loc_18006B458
0x18006b448  lea     ebx, [rsi+1]
0x18006b44b  call    ?CanApplyOwnerDrawToMenu@ImmersiveContextMenuHelper@@YA_NPEAUHMENU__@@PEAUHWND__@@@Z; ImmersiveContextMenuHelper::CanApplyOwnerDrawToMenu(HMENU__ *,HWND__ *)
0x18006b450  test    al, al
0x18006b452  jz      loc_18006B7CA
0x18006b458  test    r12b, 4
0x18006b45c  jnz     short loc_18006B479
0x18006b45e  lea     rcx, [rsp+3E0h+inputMessageSource]; inputMessageSource
0x18006b463  mov     qword ptr [rsp+3E0h+inputMessageSource.deviceType], rsi
0x18006b468  call    cs:__imp_GetCurrentInputMessageSource
0x18006b46e  test    eax, eax
0x18006b470  jz      short loc_18006B479
0x18006b472  cmp     [rsp+3E0h+inputMessageSource.deviceType], 4
0x18006b477  jz      short loc_18006B491
0x18006b479  call    cs:__imp_GetMessageExtraInfo
0x18006b47f  mov     ecx, 0FF515780h
0x18006b484  mov     [rsp+3E0h+var_3A0], sil
0x18006b489  and     rax, rcx
0x18006b48c  cmp     rax, rcx
0x18006b48f  jnz     short loc_18006B496
0x18006b491  mov     [rsp+3E0h+var_3A0], 1
0x18006b496  or      r8d, 0FFFFFFFFh
0x18006b49a  mov     [rbp+2E0h+lpString], rsi
0x18006b49e  lea     rdx, aImmersiveconte; "ImmersiveContextMenuArray_%lu"
0x18006b4a5  mov     [rbp+2E0h+var_318], rsi
0x18006b4a9  lea     rcx, [rbp+2E0h+lpString]
0x18006b4ad  mov     [rbp+2E0h+var_310], rsi
0x18006b4b1  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18006b4b6  mov     ebx, eax
0x18006b4b8  test    eax, eax
0x18006b4ba  js      short loc_18006B4D8
0x18006b4bc  mov     rdx, [rbp+2E0h+lpString]; lpString
0x18006b4c0  mov     r8, r14; hData
0x18006b4c3  mov     rcx, r15; hWnd
0x18006b4c6  call    cs:__imp_SetPropW
0x18006b4cc  neg     eax
0x18006b4ce  sbb     ebx, ebx
0x18006b4d0  not     ebx
0x18006b4d2  and     ebx, 80004005h
0x18006b4d8  lea     rcx, [rbp+2E0h+lpString]
0x18006b4dc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006b4e1  mov     ecx, r12d
0x18006b4e4  call    ?ShouldUseDarkTheme@ImmersiveContextMenuHelper@@YA_NW4ImmersiveContextMenuOptions@@@Z; ImmersiveContextMenuHelper::ShouldUseDarkTheme(ImmersiveContextMenuOptions)
0x18006b4e9  xor     r9d, r9d; fWinIni
0x18006b4ec  mov     cs:byte_180091FF1, al
0x18006b4f2  lea     r8, [rsp+3E0h+pvParam]; pvParam
0x18006b4f7  mov     [rsp+3E0h+pvParam], esi
0x18006b4fb  xor     edx, edx; uiParam
0x18006b4fd  mov     ecx, 100Ah; uiAction
0x18006b502  call    cs:__imp_SystemParametersInfoW
0x18006b508  mov     rdi, rsi
0x18006b50b  jmp     loc_18006B783
0x18006b510  xor     edx, edx; Val
0x18006b512  lea     rcx, [rsp+3E0h+mii]; void *
0x18006b517  lea     r8d, [rdx+50h]; Size
0x18006b51b  call    memset_0
0x18006b520  xor     edx, edx; Val
0x18006b522  mov     [rsp+3E0h+mii.cbSize], 50h ; 'P'
0x18006b52a  mov     r8d, 208h; Size
0x18006b530  mov     [rsp+3E0h+mii.fMask], 1EFh
0x18006b538  lea     rcx, [rbp+2E0h+var_260]; void *
0x18006b53f  call    memset_0
0x18006b544  lea     rax, [rbp+2E0h+var_260]
0x18006b54b  mov     [rbp+2E0h+mii.cch], 104h
0x18006b552  lea     r9, [rsp+3E0h+mii]; lpmii
0x18006b557  mov     [rbp+2E0h+mii.dwTypeData], rax
0x18006b55b  mov     r8d, 1; fByPosition
0x18006b561  mov     edx, esi; item
0x18006b563  mov     rcx, r13; hmenu
0x18006b566  call    cs:__imp_GetMenuItemInfoW
0x18006b56c  test    eax, eax
0x18006b56e  jz      short loc_18006B574
0x18006b570  xor     ebx, ebx
0x18006b572  jmp     short loc_18006B583
0x18006b574  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006b579  mov     ebx, eax
0x18006b57b  test    eax, eax
0x18006b57d  js      loc_18006B781
0x18006b583  mov     r8d, [rbp+2E0h+mii.wID]; unsigned __int64
0x18006b587  mov     rcx, r15; hWnd
0x18006b58a  mov     rdx, [rbp+2E0h+mii.dwItemData]; HWND
0x18006b58e  call    ?GetContextMenuDataForItem@ImmersiveContextMenuHelper@@YAPEAUContextMenuRenderingData@@PEAUHWND__@@_KI@Z; ImmersiveContextMenuHelper::GetContextMenuDataForItem(HWND__ *,unsigned __int64,uint)
0x18006b593  test    [rsp+3E0h+mii.fType], 100h
0x18006b59b  mov     rdi, rax
0x18006b59e  jz      short loc_18006B5AB
0x18006b5a0  cmp     [rbp+2E0h+mii.dwItemData], 0
0x18006b5a5  jnz     loc_18006B766
0x18006b5ab  test    rdi, rdi
0x18006b5ae  jz      short loc_18006B5C3
0x18006b5b0  mov     ecx, [rax+38h]
0x18006b5b3  shr     ecx, 2
0x18006b5b6  and     ecx, 1
0x18006b5b9  cmp     [rsp+3E0h+var_3A0], cl
0x18006b5bd  jz      loc_18006B76B
0x18006b5c3  movaps  xmm0, xmmword ptr [rsp+3E0h+mii.cbSize]
0x18006b5c8  lea     rax, [rsp+3E0h+var_388]
0x18006b5cd  movaps  xmm1, xmmword ptr [rbp+2E0h+mii.wID]
0x18006b5d1  lea     r8, [rbp+2E0h+var_260]
0x18006b5d8  movaps  xmm2, xmmword ptr [rbp+2E0h+mii.hbmpChecked]
0x18006b5dc  lea     rdx, [rbp+2E0h+var_2B0]
0x18006b5e0  movaps  xmm3, xmmword ptr [rbp+2E0h+mii.dwItemData]
0x18006b5e4  mov     ecx, r12d
0x18006b5e7  movaps  xmm4, xmmword ptr [rbp+2E0h+mii.cch]
0x18006b5eb  and     ecx, 1
0x18006b5ee  mov     r9, qword ptr [rsp+3E0h+var_380]
0x18006b5f3  mov     [rsp+3E0h+var_3A8], rax
0x18006b5f8  mov     [rsp+3E0h+var_3B0], r12d
0x18006b5fd  mov     [rsp+3E0h+var_3B8], rdi
0x18006b602  mov     [rsp+3E0h+var_3C0], r14; struct ContextMenuRenderingData *
0x18006b607  mov     [rsp+3E0h+var_388], 0
0x18006b610  movaps  [rbp+2E0h+var_2B0], xmm0
0x18006b614  movaps  [rbp+2E0h+var_2A0], xmm1
0x18006b618  movaps  [rbp+2E0h+var_290], xmm2
0x18006b61c  movaps  [rbp+2E0h+var_280], xmm3
0x18006b620  movaps  [rbp+2E0h+var_270], xmm4
0x18006b624  call    ?_GetRenderingDataForMenuItem@ImmersiveContextMenuHelper@@YAJW4ScaleType@DPIToPPIHelpers@@UtagMENUITEMINFOW@@PEBGPEAUtagPOINT@@AEAV?$CSimplePointerArrayNewMem@UContextMenuRenderingData@@V?$CSimpleArrayStandardCompareHelper@PEAUContextMenuRenderingData@@@@@@PEAUContextMenuRenderingData@@W4ImmersiveContextMenuOptions@@PEAPEAU7@@Z; ImmersiveContextMenuHelper::_GetRenderingDataForMenuItem(DPIToPPIHelpers::ScaleType,tagMENUITEMINFOW,ushort const *,tagPOINT *,CSimplePointerArrayNewMem<ContextMenuRenderingData,CSimpleArrayStandardCompareHelper<ContextMenuRenderingData *>> &,ContextMenuRenderingData *,ImmersiveContextMenuOptions,ContextMenuRenderingData * *)
0x18006b629  mov     ebx, eax
0x18006b62b  test    eax, eax
0x18006b62d  js      loc_18006B766
0x18006b633  mov     rsi, [rsp+3E0h+var_388]
0x18006b638  mov     eax, [rsp+3E0h+pvParam]
0x18006b63c  mov     [rsi+48h], eax
0x18006b63f  mov     rdx, [r14+8]
0x18006b643  cmp     rdx, [r14+18h]
0x18006b647  jnz     short loc_18006B670
0x18006b649  inc     rdx
0x18006b64c  mov     rcx, r14
0x18006b64f  call    ?_EnsureCapacity@?$CTSimpleArray@PEAG$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAG@@V?$CSimpleArrayStandardCompareHelper@PEAG@@V?$CSimpleArrayStandardMergeHelper@PEAG@@@@QEAAJ_K0@Z; CTSimpleArray<ushort *,4294967294,CTPolicyCoTaskMem<ushort *>,CSimpleArrayStandardCompareHelper<ushort *>,CSimpleArrayStandardMergeHelper<ushort *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18006b654  mov     ebx, eax
0x18006b656  test    eax, eax
0x18006b658  jns     short loc_18006B670
0x18006b65a  test    rsi, rsi
0x18006b65d  jz      loc_18006B762
0x18006b663  mov     rcx, rsi; this
0x18006b666  call    ??_GContextMenuRenderingData@@QEAAPEAXI@Z; ContextMenuRenderingData::`scalar deleting destructor'(uint)
0x18006b66b  jmp     loc_18006B762
0x18006b670  inc     qword ptr [r14+8]
0x18006b674  mov     rdx, [r14+8]
0x18006b678  mov     rax, [r14]
0x18006b67b  dec     rdx
0x18006b67e  lea     rdx, [rax+rdx*8]
0x18006b682  test    rdx, rdx
0x18006b685  jz      short loc_18006B68A
0x18006b687  mov     [rdx], rsi
0x18006b68a  mov     ebx, 50h ; 'P'
0x18006b68f  lea     rcx, [rbp+2E0h+var_300]; void *
0x18006b693  mov     r8d, ebx; Size
0x18006b696  xor     edx, edx; Val
0x18006b698  call    memset_0
0x18006b69d  mov     rax, [rbp+2E0h+mii.hbmpChecked]
0x18006b6a1  mov     r9, rsi; unsigned int
0x18006b6a4  mov     rdx, [rbp+2E0h+mii.dwItemData]
0x18006b6a8  mov     rcx, r15; hWnd
0x18006b6ab  mov     r8d, [rbp+2E0h+mii.wID]; unsigned __int64
0x18006b6af  mov     [rbp+2E0h+var_300.hbmpChecked], rax
0x18006b6b3  mov     rax, [rbp+2E0h+mii.hbmpUnchecked]
0x18006b6b7  mov     [rbp+2E0h+var_300.hbmpUnchecked], rax
0x18006b6bb  mov     eax, [rsp+3E0h+mii.fType]
0x18006b6bf  bts     eax, 8
0x18006b6c3  mov     [rbp+2E0h+var_300.cbSize], ebx
0x18006b6c6  mov     [rbp+2E0h+var_300.fMask], 188h
0x18006b6cd  mov     [rbp+2E0h+var_300.hbmpItem], 0
0x18006b6d5  mov     [rbp+2E0h+var_300.fType], eax
0x18006b6d8  test    rdx, rdx
0x18006b6db  jnz     short loc_18006B6EB
0x18006b6dd  mov     [rbp+2E0h+var_300.fMask], 1A8h
0x18006b6e4  mov     rdx, rsi; HWND
0x18006b6e7  mov     [rbp+2E0h+var_300.dwItemData], rsi
0x18006b6eb  call    ?StoreContextMenuDataForItem@ImmersiveContextMenuHelper@@YAJPEAUHWND__@@_KIPEAUContextMenuRenderingData@@@Z; ImmersiveContextMenuHelper::StoreContextMenuDataForItem(HWND__ *,unsigned __int64,uint,ContextMenuRenderingData *)
0x18006b6f0  mov     ebx, eax
0x18006b6f2  test    eax, eax
0x18006b6f4  js      short loc_18006B750
0x18006b6f6  mov     edx, [rsp+3E0h+inputMessageSource.deviceType]; item
0x18006b6fa  lea     r9, [rbp+2E0h+var_300]; lpmii
0x18006b6fe  mov     r8d, 1; fByPositon
0x18006b704  mov     rcx, r13; hmenu
0x18006b707  call    cs:__imp_SetMenuItemInfoW
0x18006b70d  test    eax, eax
0x18006b70f  jz      short loc_18006B715
0x18006b711  xor     ebx, ebx
0x18006b713  jmp     short loc_18006B720
0x18006b715  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006b71a  mov     ebx, eax
0x18006b71c  test    eax, eax
0x18006b71e  js      short loc_18006B750
0x18006b720  mov     rcx, [rbp+2E0h+mii.hSubMenu]; int
0x18006b724  test    rcx, rcx
0x18006b727  jz      short loc_18006B750
0x18006b729  cmp     [rsp+3E0h+var_38C], 0
0x18006b72e  mov     rdx, r15; int
0x18006b731  jz      short loc_18006B73A
0x18006b733  call    ?HandleMergedMenus@ImmersiveContextMenuHelper@@YAXPEAUHMENU__@@PEAUHWND__@@@Z; ImmersiveContextMenuHelper::HandleMergedMenus(HMENU__ *,HWND__ *)
0x18006b738  jmp     short loc_18006B750
0x18006b73a  mov     r8, qword ptr [rsp+3E0h+var_380]; int
0x18006b73f  mov     r9d, r12d
0x18006b742  or      r9d, 10h; int
0x18006b746  mov     [rsp+3E0h+var_3C0], r14; hData
0x18006b74b  call    ?ApplyOwnerDrawToMenu@ImmersiveContextMenuHelper@@YAJPEAUHMENU__@@PEAUHWND__@@PEAUtagPOINT@@W4ImmersiveContextMenuOptions@@AEAV?$CSimplePointerArrayNewMem@UContextMenuRenderingData@@V?$CSimpleArrayStandardCompareHelper@PEAUContextMenuRenderingData@@@@@@@Z; ImmersiveContextMenuHelper::ApplyOwnerDrawToMenu(HMENU__ *,HWND__ *,tagPOINT *,ImmersiveContextMenuOptions,CSimplePointerArrayNewMem<ContextMenuRenderingData,CSimpleArrayStandardCompareHelper<ContextMenuRenderingData *>> &)
0x18006b750  cmp     [rsp+3E0h+var_3A0], 0
0x18006b755  mov     rdi, rsi
0x18006b758  mov     [rsi+50h], r14
0x18006b75c  jz      short loc_18006B762
0x18006b75e  or      dword ptr [rsi+38h], 4
0x18006b762  mov     esi, [rsp+3E0h+inputMessageSource.deviceType]
0x18006b766  test    rdi, rdi
0x18006b769  jz      short loc_18006B781
0x18006b76b  mov     ecx, [rdi+38h]
0x18006b76e  mov     eax, ecx
0x18006b770  and     eax, 0FFFFFFFEh
0x18006b773  or      ecx, 1
0x18006b776  test    esi, esi
0x18006b778  cmovnz  ecx, eax
0x18006b77b  and     ecx, 0FFFFFFFDh
0x18006b77e  mov     [rdi+38h], ecx
0x18006b781  inc     esi
0x18006b783  mov     [rsp+3E0h+inputMessageSource.deviceType], esi
0x18006b787  test    ebx, ebx
0x18006b789  jns     loc_18006B510
0x18006b78f  cmp     ebx, 800705B0h
0x18006b795  jnz     short loc_18006B7BF
0x18006b797  cmp     qword ptr [r14+8], 0
0x18006b79c  jbe     short loc_18006B7BF
0x18006b79e  xor     ebx, ebx
0x18006b7a0  test    rdi, rdi
0x18006b7a3  jz      short loc_18006B7A9
0x18006b7a5  or      dword ptr [rdi+38h], 2
0x18006b7a9  test    r12b, 10h
0x18006b7ad  jnz     short loc_18006B7CA
0x18006b7af  mov     r8d, r12d
0x18006b7b2  mov     rdx, r15
0x18006b7b5  mov     rcx, r13
0x18006b7b8  call    ?OverrideBackgroundColor@ImmersiveContextMenuHelper@@YAJPEAUHMENU__@@PEAUHWND__@@W4ImmersiveContextMenuOptions@@@Z; ImmersiveContextMenuHelper::OverrideBackgroundColor(HMENU__ *,HWND__ *,ImmersiveContextMenuOptions)
0x18006b7bd  jmp     short loc_18006B7CA
0x18006b7bf  mov     rdx, r15; hWnd
0x18006b7c2  mov     rcx, r13; this
0x18006b7c5  call    ?RemoveOwnerDrawFromMenu@ImmersiveContextMenuHelper@@YAXPEAUHMENU__@@PEAUHWND__@@@Z; ImmersiveContextMenuHelper::RemoveOwnerDrawFromMenu(HMENU__ *,HWND__ *)
0x18006b7ca  mov     eax, ebx
0x18006b7cc  mov     rcx, [rbp+2E0h+var_50]
0x18006b7d3  xor     rcx, rsp; StackCookie
0x18006b7d6  call    __security_check_cookie
0x18006b7db  add     rsp, 3A8h
0x18006b7e2  pop     r15
0x18006b7e4  pop     r14
0x18006b7e6  pop     r13
0x18006b7e8  pop     r12
0x18006b7ea  pop     rdi
0x18006b7eb  pop     rsi
0x18006b7ec  pop     rbx
0x18006b7ed  pop     rbp
0x18006b7ee  retn
```
