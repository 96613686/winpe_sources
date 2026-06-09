# CSyncTrayIconManager::_OnTrayMenu(HWND__ *)

- ea: `0x180023314`
- end: `0x180023542`
- name: `?_OnTrayMenu@CSyncTrayIconManager@@AEAAXPEAUHWND__@@@Z`
- size: `558`
- prototype: `void __fastcall(CSyncTrayIconManager *this, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005490`

## callees

- `0x180004c70`
- `0x180009600`
- `0x1800096d0`
- `0x180023314`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002340f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023468`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800234a4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002340f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023468`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800234a4`
- `USER32!PostMessageW` at `0x1800233bb`
- `USER32!PostMessageW` at `0x1800233bb`
- `USER32!GetCursorPos` at `0x180023335`
- `USER32!GetCursorPos` at `0x180023335`
- `USER32!LoadMenuW` at `0x180023347`
- `USER32!LoadMenuW` at `0x180023347`
- `USER32!GetSubMenu` at `0x18002335e`
- `USER32!GetSubMenu` at `0x18002335e`
- `USER32!SetForegroundWindow` at `0x180023373`
- `USER32!SetForegroundWindow` at `0x180023373`
- `USER32!TrackPopupMenu` at `0x18002339f`
- `USER32!TrackPopupMenu` at `0x18002339f`
- `USER32!DestroyMenu` at `0x1800233aa`
- `USER32!DestroyMenu` at `0x180023528`
- `USER32!DestroyMenu` at `0x180023531`
- `USER32!DestroyMenu` at `0x1800233aa`
- `USER32!DestroyMenu` at `0x180023528`
- `USER32!DestroyMenu` at `0x180023531`

## pseudocode

```c
void __fastcall CSyncTrayIconManager::_OnTrayMenu(CSyncTrayIconManager *this, HWND a2)
{
  HMENU MenuW; // rax
  HMENU v4; // rsi
  HMENU SubMenu; // rdi
  BOOL v6; // ebx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  void *v11; // rcx
  const wchar_t *v12; // r8
  struct tagPOINT Point; // [rsp+70h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+40h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+88h] [rbp+48h] BYREF

  Point = 0;
  GetCursorPos(&Point);
  MenuW = LoadMenuW(g_hmodThisDll, (LPCWSTR)0x17C);
  v4 = MenuW;
  if ( MenuW )
  {
    SubMenu = GetSubMenu(MenuW, 0);
    if ( !SubMenu )
    {
LABEL_21:
      DestroyMenu(v4);
      return;
    }
    SetForegroundWindow(a2);
    v6 = TrackPopupMenu(SubMenu, 0x182u, Point.x, Point.y, 0, a2, 0);
    DestroyMenu(SubMenu);
    PostMessageW(a2, 0, 0, 0);
    v7 = v6 - 1;
    if ( !v7 )
    {
      lpCriticalSection = 0;
      if ( (int)CHandlerCache::s_GetInstance((struct CHandlerCache **)&lpCriticalSection, 1) >= 0 )
        CHandlerCache::SynchronizeAll(lpCriticalSection, 0);
      goto LABEL_20;
    }
    v8 = v7 - 1;
    if ( !v8 )
    {
      lpCriticalSection = 0;
      if ( (int)CHandlerCache::s_GetInstance((struct CHandlerCache **)&lpCriticalSection, 1) >= 0 )
        CHandlerCache::CancelAll(lpCriticalSection);
      goto LABEL_20;
    }
    v9 = v8 - 3;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 != 5 )
          goto LABEL_20;
        ppv = 0;
        if ( CoCreateInstance(&CLSID_OpenControlPanel, 0, 1u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, &ppv) < 0 )
          goto LABEL_20;
        (*(void (__fastcall **)(LPVOID, const unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
          ppv,
          L"Microsoft.SyncCenter",
          0,
          0);
        v11 = ppv;
        goto LABEL_15;
      }
      lpCriticalSection = 0;
      if ( CoCreateInstance(
             &CLSID_OpenControlPanel,
             0,
             1u,
             &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1,
             (LPVOID *)&lpCriticalSection) >= 0 )
      {
        v12 = L"::{BC48B32F-5910-47F5-8570-5074A8A5636A}";
LABEL_14:
        ((void (__fastcall *)(LPCRITICAL_SECTION, const unsigned __int16 *, const wchar_t *, _QWORD))lpCriticalSection->DebugInfo->ProcessLocksList.Blink)(
          lpCriticalSection,
          L"Microsoft.SyncCenter",
          v12,
          0);
        v11 = lpCriticalSection;
LABEL_15:
        (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
    else
    {
      lpCriticalSection = 0;
      if ( CoCreateInstance(
             &CLSID_OpenControlPanel,
             0,
             1u,
             &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1,
             (LPVOID *)&lpCriticalSection) >= 0 )
      {
        v12 = L"::{E413D040-6788-4C22-957E-175D1C513A34}";
        goto LABEL_14;
      }
    }
LABEL_20:
    DestroyMenu(SubMenu);
    goto LABEL_21;
  }
}

```

## disassembly

```asm
0x180023314  mov     qword ptr [rsp-28h+Point.x], rcx
0x180023319  push    rbp
0x18002331a  push    rbx
0x18002331b  push    rsi
0x18002331c  push    rdi
0x18002331d  push    r14
0x18002331f  mov     rbp, rsp
0x180023322  sub     rsp, 40h
0x180023326  lea     rcx, [rbp+Point]; lpPoint
0x18002332a  mov     qword ptr [rbp+Point.x], 0
0x180023332  mov     r14, rdx
0x180023335  call    cs:__imp_GetCursorPos
0x18002333b  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180023342  mov     edx, 17Ch; lpMenuName
0x180023347  call    cs:__imp_LoadMenuW
0x18002334d  mov     rsi, rax
0x180023350  test    rax, rax
0x180023353  jz      loc_180023537
0x180023359  xor     edx, edx; nPos
0x18002335b  mov     rcx, rax; hMenu
0x18002335e  call    cs:__imp_GetSubMenu
0x180023364  mov     rdi, rax
0x180023367  test    rax, rax
0x18002336a  jz      loc_18002352E
0x180023370  mov     rcx, r14; hWnd
0x180023373  call    cs:__imp_SetForegroundWindow
0x180023379  mov     r9d, [rbp+Point.y]; y
0x18002337d  mov     edx, 182h; uFlags
0x180023382  mov     r8d, [rbp+Point.x]; x
0x180023386  mov     rcx, rdi; hMenu
0x180023389  mov     [rsp+40h+prcRect], 0; prcRect
0x180023392  mov     [rsp+40h+hWnd], r14; hWnd
0x180023397  mov     [rsp+40h+nReserved], 0; nReserved
0x18002339f  call    cs:__imp_TrackPopupMenu
0x1800233a5  mov     rcx, rdi; hMenu
0x1800233a8  mov     ebx, eax
0x1800233aa  call    cs:__imp_DestroyMenu
0x1800233b0  xor     r9d, r9d; lParam
0x1800233b3  xor     r8d, r8d; wParam
0x1800233b6  xor     edx, edx; Msg
0x1800233b8  mov     rcx, r14; hWnd
0x1800233bb  call    cs:__imp_PostMessageW
0x1800233c1  sub     ebx, 1
0x1800233c4  jz      loc_180023503
0x1800233ca  sub     ebx, 1
0x1800233cd  jz      loc_1800234E1
0x1800233d3  sub     ebx, 3
0x1800233d6  jz      loc_18002347F
0x1800233dc  sub     ebx, 1
0x1800233df  jz      short loc_180023443
0x1800233e1  cmp     ebx, 5
0x1800233e4  jnz     loc_180023525
0x1800233ea  lea     rax, [rbp+ppv]
0x1800233ee  mov     [rbp+ppv], 0
0x1800233f6  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x1800233fd  mov     qword ptr [rsp+40h+nReserved], rax; ppv
0x180023402  xor     edx, edx; pUnkOuter
0x180023404  lea     r8d, [rbx-4]; dwClsContext
0x180023408  lea     rcx, CLSID_OpenControlPanel; rclsid
0x18002340f  call    cs:__imp_CoCreateInstance
0x180023415  test    eax, eax
0x180023417  js      loc_180023525
0x18002341d  mov     rcx, [rbp+ppv]
0x180023421  lea     rdx, aMicrosoftSyncc; "Microsoft.SyncCenter"
0x180023428  xor     r9d, r9d
0x18002342b  xor     r8d, r8d
0x18002342e  mov     rax, [rcx]
0x180023431  mov     rax, [rax+18h]
0x180023435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002343a  mov     rcx, [rbp+ppv]
0x18002343e  jmp     loc_1800234D3
0x180023443  xor     edx, edx; pUnkOuter
0x180023445  mov     [rbp+lpCriticalSection], 0
0x18002344d  lea     rax, [rbp+lpCriticalSection]
0x180023451  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x180023458  mov     qword ptr [rsp+40h+nReserved], rax; ppv
0x18002345d  lea     rcx, CLSID_OpenControlPanel; rclsid
0x180023464  lea     r8d, [rdx+1]; dwClsContext
0x180023468  call    cs:__imp_CoCreateInstance
0x18002346e  test    eax, eax
0x180023470  js      loc_180023525
0x180023476  lea     r8, aBc48b32f591047; "::{BC48B32F-5910-47F5-8570-5074A8A5636A"...
0x18002347d  jmp     short loc_1800234B5
0x18002347f  xor     edx, edx; pUnkOuter
0x180023481  mov     [rbp+lpCriticalSection], 0
0x180023489  lea     rax, [rbp+lpCriticalSection]
0x18002348d  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x180023494  mov     qword ptr [rsp+40h+nReserved], rax; ppv
0x180023499  lea     rcx, CLSID_OpenControlPanel; rclsid
0x1800234a0  lea     r8d, [rdx+1]; dwClsContext
0x1800234a4  call    cs:__imp_CoCreateInstance
0x1800234aa  test    eax, eax
0x1800234ac  js      short loc_180023525
0x1800234ae  lea     r8, aE413d04067884c; "::{E413D040-6788-4C22-957E-175D1C513A34"...
0x1800234b5  mov     rcx, [rbp+lpCriticalSection]
0x1800234b9  lea     rdx, aMicrosoftSyncc; "Microsoft.SyncCenter"
0x1800234c0  xor     r9d, r9d
0x1800234c3  mov     rax, [rcx]
0x1800234c6  mov     rax, [rax+18h]
0x1800234ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234cf  mov     rcx, [rbp+lpCriticalSection]
0x1800234d3  mov     rax, [rcx]
0x1800234d6  mov     rax, [rax+10h]
0x1800234da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234df  jmp     short loc_180023525
0x1800234e1  mov     dl, 1; bool
0x1800234e3  mov     [rbp+lpCriticalSection], 0
0x1800234eb  lea     rcx, [rbp+lpCriticalSection]; struct CHandlerCache **
0x1800234ef  call    ?s_GetInstance@CHandlerCache@@SAJPEAPEAV1@_N@Z; CHandlerCache::s_GetInstance(CHandlerCache * *,bool)
0x1800234f4  test    eax, eax
0x1800234f6  js      short loc_180023525
0x1800234f8  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800234fc  call    ?CancelAll@CHandlerCache@@QEAAJXZ; CHandlerCache::CancelAll(void)
0x180023501  jmp     short loc_180023525
0x180023503  mov     dl, 1; bool
0x180023505  mov     [rbp+lpCriticalSection], 0
0x18002350d  lea     rcx, [rbp+lpCriticalSection]; struct CHandlerCache **
0x180023511  call    ?s_GetInstance@CHandlerCache@@SAJPEAPEAV1@_N@Z; CHandlerCache::s_GetInstance(CHandlerCache * *,bool)
0x180023516  test    eax, eax
0x180023518  js      short loc_180023525
0x18002351a  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18002351e  xor     edx, edx; pData
0x180023520  call    ?SynchronizeAll@CHandlerCache@@QEAAJPEAUHWND__@@@Z; CHandlerCache::SynchronizeAll(HWND__ *)
0x180023525  mov     rcx, rdi; hMenu
0x180023528  call    cs:__imp_DestroyMenu
0x18002352e  mov     rcx, rsi; hMenu
0x180023531  call    cs:__imp_DestroyMenu
0x180023537  add     rsp, 40h
0x18002353b  pop     r14
0x18002353d  pop     rdi
0x18002353e  pop     rsi
0x18002353f  pop     rbx
0x180023540  pop     rbp
0x180023541  retn
```
