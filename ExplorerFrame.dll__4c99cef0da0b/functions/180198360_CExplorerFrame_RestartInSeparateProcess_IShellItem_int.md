# CExplorerFrame::RestartInSeparateProcess(IShellItem *,int)

- ea: `0x180198360`
- end: `0x1801988b5`
- name: `?RestartInSeparateProcess@CExplorerFrame@@UEAAJPEAUIShellItem@@H@Z`
- size: `1365`
- prototype: `int(CExplorerFrame *__hidden this, struct IShellItem *, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800218ac`
- `0x18002f35c`
- `0x1800340a0`
- `0x180037240`
- `0x18003d368`
- `0x1800749f0`
- `0x1800ebd30`
- `0x1800ee720`
- `0x180103e1c`
- `0x18010a500`
- `0x18012fda4`
- `0x18013c048`
- `0x18013f7d0`
- `0x180198360`
- `0x180210010`

## import_xrefs

- `SHCORE!GetDpiForMonitor` at `0x180198536`
- `SHCORE!GetDpiForMonitor` at `0x180198536`
- `SHELL32!SHGetIDListFromObject` at `0x1801985c9`
- `SHELL32!SHGetIDListFromObject` at `0x1801985c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019868a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801986d8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180198703`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019872e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180198759`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019868a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801986d8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180198703`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019872e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180198759`
- `KERNEL32!MulDiv` at `0x18019854c`
- `KERNEL32!MulDiv` at `0x180198564`
- `KERNEL32!MulDiv` at `0x18019857c`
- `KERNEL32!MulDiv` at `0x180198594`
- `KERNEL32!MulDiv` at `0x18019854c`
- `KERNEL32!MulDiv` at `0x180198564`
- `KERNEL32!MulDiv` at `0x18019857c`
- `KERNEL32!MulDiv` at `0x180198594`
- `USER32!GetDC` at `0x1801984f3`
- `USER32!GetDC` at `0x1801984f3`
- `USER32!GetWindowRect` at `0x180198497`
- `USER32!GetWindowRect` at `0x180198497`
- `USER32!PtInRect` at `0x1801984c8`
- `USER32!PtInRect` at `0x1801984c8`
- `USER32!GetForegroundWindow` at `0x1801983fe`
- `USER32!GetForegroundWindow` at `0x180198418`
- `USER32!GetForegroundWindow` at `0x1801983fe`
- `USER32!GetForegroundWindow` at `0x180198418`
- `USER32!IsChild` at `0x18019840e`
- `USER32!IsChild` at `0x18019840e`
- `USER32!PostMessageW` at `0x18019881f`
- `USER32!PostMessageW` at `0x18019881f`
- `USER32!MonitorFromWindow` at `0x1801984df`
- `USER32!MonitorFromWindow` at `0x1801984df`
- `USER32!MonitorFromRect` at `0x1801985a6`
- `USER32!MonitorFromRect` at `0x1801985a6`
- `USER32!GetWindowPlacement` at `0x18019844f`
- `USER32!GetWindowPlacement` at `0x18019844f`
- `USER32!GetPhysicalCursorPos` at `0x1801984b2`
- `USER32!GetPhysicalCursorPos` at `0x1801984b2`
- `GDI32!GetDeviceCaps` at `0x18019850a`
- `GDI32!GetDeviceCaps` at `0x18019850a`

## string_xrefs

- `0x1801986e6`: `ms-settings:windowsupdate-uninstallupdates`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CExplorerFrame::RestartInSeparateProcess(CExplorerFrame *this, IUnknown *a2, int a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // edi
  HWND ForegroundWindow; // rax
  bool v10; // bl
  HMONITOR v11; // rbx
  HDC DC; // rax
  int DeviceCaps; // r15d
  HRESULT v14; // eax
  HRESULT (__stdcall *Release)(IShellItem *, SIGDN, LPWSTR *); // rbx
  __int64 v17; // rdx
  __int64 v18; // rdx
  char v19; // r14
  __int64 v20; // r8
  __int64 v21; // rdx
  const wchar_t *v22; // rbx
  unsigned int v23; // r15d
  __int64 v24; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-79h]
  int bIgnoreCasea; // [rsp+20h] [rbp-79h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-79h]
  struct tagPOINT Point; // [rsp+30h] [rbp-69h] BYREF
  int nNumerator; // [rsp+38h] [rbp-61h] BYREF
  LPVOID v30; // [rsp+40h] [rbp-59h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-51h] BYREF
  LPCWCH lpString1; // [rsp+50h] [rbp-49h] BYREF
  __int64 v33; // [rsp+58h] [rbp-41h]
  __int64 v34; // [rsp+60h] [rbp-39h]
  int v35; // [rsp+68h] [rbp-31h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp-29h] BYREF
  RECT rc; // [rsp+80h] [rbp-19h] BYREF
  WINDOWPLACEMENT wndpl; // [rsp+90h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  if ( *((_BYTE *)this + 337) )
    return 0;
  v30 = 0;
  Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&v30);
  v6 = IECreateInstance(&CLSID_ExplorerLauncher, &v30);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13DB,
      (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
LABEL_26:
    Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&v30);
    return v7;
  }
  v8 = 1;
  ForegroundWindow = GetForegroundWindow();
  v10 = IsChild(*((HWND *)this - 21), ForegroundWindow) || *((HWND *)this - 21) == GetForegroundWindow();
  memset(&wndpl, 0, sizeof(wndpl));
  wndpl.length = 44;
  if ( GetWindowPlacement(*((HWND *)this - 21), &wndpl) )
  {
    switch ( wndpl.showCmd )
    {
      case 1u:
        v8 = v10 ? 1 : 4;
        break;
      case 2u:
        v8 = v10 ? 2 : 7;
        break;
      case 3u:
        v8 = 3;
        break;
    }
  }
  Rect = 0;
  GetWindowRect(*((HWND *)this - 21), &Rect);
  if ( a3 )
  {
    Point = 0;
    if ( GetPhysicalCursorPos(&Point) )
    {
      if ( PtInRect(&Rect, Point) )
      {
        v11 = MonitorFromWindow(*((HWND *)this - 21), 0);
        if ( v11 )
        {
          DC = GetDC(0);
          if ( DC )
          {
            DeviceCaps = GetDeviceCaps(DC, 88);
            if ( DeviceCaps )
            {
              nNumerator = 0;
              v35 = 0;
              if ( (int)GetDpiForMonitor(v11, 0, &nNumerator, &v35) >= 0 )
              {
                rc.left = Point.x + MulDiv(Rect.left - Point.x, nNumerator, DeviceCaps);
                rc.top = Point.y + MulDiv(Rect.top - Point.y, nNumerator, DeviceCaps);
                rc.right = Point.x + MulDiv(Rect.right - Point.x, nNumerator, DeviceCaps);
                rc.bottom = Point.y + MulDiv(Rect.bottom - Point.y, nNumerator, DeviceCaps);
                if ( MonitorFromRect(&rc, 0) == v11 )
                  Rect = rc;
              }
            }
          }
        }
      }
    }
  }
  ppidl = 0;
  v14 = SHGetIDListFromObject(a2, &ppidl);
  v7 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x141E,
      (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
      (const char *)(unsigned int)v14,
      bIgnoreCase);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppidl);
    goto LABEL_26;
  }
  *((_BYTE *)this + 337) = 1;
  lpString1 = 0;
  v33 = 0;
  v34 = 0;
  Release = (HRESULT (__stdcall *)(IShellItem *, SIGDN, LPWSTR *))a2->lpVtbl[1].Release;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
  v33 = -1;
  v34 = -1;
  if ( ((int (__fastcall *)(IUnknown *, __int64, LPCWCH *))Release)(a2, 2147581953LL, &lpString1) < 0 )
    goto LABEL_42;
  LOBYTE(v17) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::GetImpl'::`2'::impl,
    v17,
    0);
  if ( CompareStringOrdinal(lpString1, -1, L"::{BB06C0E4-D293-4F75-8A90-CB05B6477EEE}", -1, 1) == 2 )
  {
    v19 = 1;
    LOBYTE(v18) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::GetImpl'::`2'::impl,
      v18,
      0);
    LOBYTE(v20) = 1;
    LOBYTE(v21) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::GetImpl'::`2'::impl,
      v21,
      v20);
    v22 = L"ms-settings:about";
  }
  else
  {
    v19 = 0;
    v22 = 0;
  }
  if ( CompareStringOrdinal(lpString1, -1, L"::{D450A8A1-9568-45C7-9C0E-B4F9FB4537BD}", -1, 1) == 2 )
  {
    v19 = 1;
    v22 = L"ms-settings:windowsupdate-uninstallupdates";
  }
  if ( CompareStringOrdinal(lpString1, -1, L"::{17CD9488-1228-4B2F-88CE-4298E93E0966}", -1, 1) == 2 )
  {
    v19 = 1;
    v22 = L"ms-settings:defaultapps";
  }
  if ( CompareStringOrdinal(lpString1, -1, L"::{BD84B380-8CA2-1069-AB1D-08000948F534}", -1, 1) == 2 )
  {
    v19 = 1;
    v22 = L"ms-settings:fonts";
  }
  if ( CompareStringOrdinal(lpString1, -1, L"::{A8A91A66-3A7D-4424-8D24-04E180695C7A}", -1, 1) == 2 )
  {
    v19 = 1;
    v22 = L"ms-settings:devices";
  }
  else
  {
    v23 = 0;
    if ( !v22 )
      goto LABEL_41;
  }
  v23 = LaunchRedirectedControlPanelEntryPoint(v22, 2);
LABEL_41:
  if ( !v19 )
  {
LABEL_42:
    bIgnoreCasea = v8;
    v23 = (*(__int64 (__fastcall **)(LPVOID, LPITEMIDLIST, __int64, struct tagRECT *))(*(_QWORD *)v30 + 32LL))(
            v30,
            ppidl,
            1,
            &Rect);
  }
  if ( (v23 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1469,
      (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
      (const char *)v23,
      bIgnoreCasea);
    *((_BYTE *)this + 337) = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1472,
      (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
      (const char *)v23,
      bIgnoreCaseb);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppidl);
    Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&v30);
    return v23;
  }
  PostMessageW(*((HWND *)this - 21), 0x10u, 0, 0);
  v24 = *((_QWORD *)this + 98);
  if ( v24 )
  {
    if ( (unsigned __int8)tip2::details::shared_data<0,0,0>::is_running(v24 + 8) )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerUptimeTest,_tip_FileExplorerUptimeTest>>::operator->(
                              (char *)this + 784,
                              &Point)
               + 274LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerUptimeTest,_tip_FileExplorerUptimeTest>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerUptimeTest,_tip_FileExplorerUptimeTest>>(&Point);
      tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerUptimeTest,_tip_FileExplorerUptimeTest>>::complete((char *)this + 784);
    }
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppidl);
  Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&v30);
  return 0;
}

```

## disassembly

```asm
0x180198360  mov     [rsp-8+arg_10], rbx
0x180198365  mov     [rsp-8+arg_18], rsi
0x18019836a  push    rbp
0x18019836b  push    rdi
0x18019836c  push    r13
0x18019836e  push    r14
0x180198370  push    r15
0x180198372  lea     rbp, [rsp-37h]
0x180198377  sub     rsp, 0D0h
0x18019837e  mov     rax, cs:__security_cookie
0x180198385  xor     rax, rsp
0x180198388  mov     [rbp+57h+var_30], rax
0x18019838c  mov     r15d, r8d
0x18019838f  mov     r14, rdx
0x180198392  mov     rsi, rcx
0x180198395  cmp     byte ptr [rcx+151h], 0
0x18019839c  jnz     loc_18019888B
0x1801983a2  mov     [rbp+57h+var_B0], 0
0x1801983aa  lea     rcx, [rbp+57h+var_B0]
0x1801983ae  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x1801983b3  lea     rax, [rbp+57h+var_B0]
0x1801983b7  mov     qword ptr [rsp+0F0h+bIgnoreCase], rax; int
0x1801983bc  lea     r9, _GUID_9b25c299_03b6_4a14_827d_095485d0c022
0x1801983c3  mov     r13d, 1
0x1801983c9  mov     r8d, r13d
0x1801983cc  lea     rcx, CLSID_ExplorerLauncher; rclsid
0x1801983d3  call    IECreateInstance
0x1801983d8  mov     ebx, eax
0x1801983da  test    eax, eax
0x1801983dc  jns     short loc_1801983FB
0x1801983de  mov     rcx, [rbp+5Fh]; this
0x1801983e2  mov     r9d, eax; char *
0x1801983e5  lea     r8, aShellExplorerf_10; "shell\\explorerframe\\explorerframep.cp"...
0x1801983ec  mov     edx, 13DBh; void *
0x1801983f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801983f6  jmp     loc_1801985F8
0x1801983fb  mov     edi, r13d
0x1801983fe  call    cs:__imp_GetForegroundWindow
0x180198404  mov     rdx, rax; hWnd
0x180198407  mov     rcx, [rsi-0A8h]; hWndParent
0x18019840e  call    cs:__imp_IsChild
0x180198414  test    eax, eax
0x180198416  jnz     short loc_18019842B
0x180198418  call    cs:__imp_GetForegroundWindow
0x18019841e  cmp     [rsi-0A8h], rax
0x180198425  jz      short loc_18019842B
0x180198427  xor     bl, bl
0x180198429  jmp     short loc_18019842E
0x18019842b  mov     bl, r13b
0x18019842e  xorps   xmm0, xmm0
0x180198431  movups  xmmword ptr [rbp+57h+wndpl.length], xmm0
0x180198435  movups  xmmword ptr [rbp+57h+wndpl.ptMinPosition.y], xmm0
0x180198439  movups  xmmword ptr [rbp+57h+wndpl.rcNormalPosition.left], xmm0
0x18019843d  mov     [rbp+57h+wndpl.length], 2Ch ; ','
0x180198444  lea     rdx, [rbp+57h+wndpl]; lpwndpl
0x180198448  mov     rcx, [rsi-0A8h]; hWnd
0x18019844f  call    cs:__imp_GetWindowPlacement
0x180198455  test    eax, eax
0x180198457  jz      short loc_180198485
0x180198459  mov     eax, [rbp+57h+wndpl.showCmd]
0x18019845c  sub     eax, edi
0x18019845e  jz      short loc_18019847B
0x180198460  sub     eax, edi
0x180198462  jz      short loc_18019846F
0x180198464  cmp     eax, edi
0x180198466  jnz     short loc_180198485
0x180198468  mov     edi, 3
0x18019846d  jmp     short loc_180198485
0x18019846f  neg     bl
0x180198471  sbb     edi, edi
0x180198473  and     edi, 0FFFFFFFBh
0x180198476  add     edi, 7
0x180198479  jmp     short loc_180198485
0x18019847b  neg     bl
0x18019847d  sbb     edi, edi
0x18019847f  and     edi, 0FFFFFFFDh
0x180198482  add     edi, 4
0x180198485  xorps   xmm0, xmm0
0x180198488  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18019848c  lea     rdx, [rbp+57h+Rect]; lpRect
0x180198490  mov     rcx, [rsi-0A8h]; hWnd
0x180198497  call    cs:__imp_GetWindowRect
0x18019849d  test    r15d, r15d
0x1801984a0  jz      loc_1801985BA
0x1801984a6  mov     qword ptr [rbp+57h+Point.x], 0
0x1801984ae  lea     rcx, [rbp+57h+Point]; lpPoint
0x1801984b2  call    cs:__imp_GetPhysicalCursorPos
0x1801984b8  test    eax, eax
0x1801984ba  jz      loc_1801985BA
0x1801984c0  mov     rdx, qword ptr [rbp+57h+Point.x]; pt
0x1801984c4  lea     rcx, [rbp+57h+Rect]; lprc
0x1801984c8  call    cs:__imp_PtInRect
0x1801984ce  test    eax, eax
0x1801984d0  jz      loc_1801985BA
0x1801984d6  xor     edx, edx; dwFlags
0x1801984d8  mov     rcx, [rsi-0A8h]; hwnd
0x1801984df  call    cs:__imp_MonitorFromWindow
0x1801984e5  mov     rbx, rax
0x1801984e8  test    rax, rax
0x1801984eb  jz      loc_1801985BA
0x1801984f1  xor     ecx, ecx; hWnd
0x1801984f3  call    cs:__imp_GetDC
0x1801984f9  test    rax, rax
0x1801984fc  jz      loc_1801985BA
0x180198502  mov     edx, 58h ; 'X'; index
0x180198507  mov     rcx, rax; hdc
0x18019850a  call    cs:__imp_GetDeviceCaps
0x180198510  mov     r15d, eax
0x180198513  test    eax, eax
0x180198515  jz      loc_1801985BA
0x18019851b  mov     [rbp+57h+nNumerator], 0
0x180198522  mov     [rbp+57h+var_88], 0
0x180198529  lea     r9, [rbp+57h+var_88]
0x18019852d  lea     r8, [rbp+57h+nNumerator]
0x180198531  xor     edx, edx
0x180198533  mov     rcx, rbx
0x180198536  call    cs:__imp_GetDpiForMonitor
0x18019853c  test    eax, eax
0x18019853e  js      short loc_1801985BA
0x180198540  mov     ecx, [rbp+57h+Rect.left]
0x180198543  sub     ecx, [rbp+57h+Point.x]; nNumber
0x180198546  mov     r8d, r15d; nDenominator
0x180198549  mov     edx, [rbp+57h+nNumerator]; nNumerator
0x18019854c  call    cs:__imp_MulDiv
0x180198552  add     eax, [rbp+57h+Point.x]
0x180198555  mov     [rbp+57h+rc.left], eax
0x180198558  mov     ecx, [rbp+57h+Rect.top]
0x18019855b  sub     ecx, [rbp+57h+Point.y]; nNumber
0x18019855e  mov     r8d, r15d; nDenominator
0x180198561  mov     edx, [rbp+57h+nNumerator]; nNumerator
0x180198564  call    cs:__imp_MulDiv
0x18019856a  add     eax, [rbp+57h+Point.y]
0x18019856d  mov     [rbp+57h+rc.top], eax
0x180198570  mov     ecx, [rbp+57h+Rect.right]
0x180198573  sub     ecx, [rbp+57h+Point.x]; nNumber
0x180198576  mov     r8d, r15d; nDenominator
0x180198579  mov     edx, [rbp+57h+nNumerator]; nNumerator
0x18019857c  call    cs:__imp_MulDiv
0x180198582  add     eax, [rbp+57h+Point.x]
0x180198585  mov     [rbp+57h+rc.right], eax
0x180198588  mov     ecx, [rbp+57h+Rect.bottom]
0x18019858b  sub     ecx, [rbp+57h+Point.y]; nNumber
0x18019858e  mov     r8d, r15d; nDenominator
0x180198591  mov     edx, [rbp+57h+nNumerator]; nNumerator
0x180198594  call    cs:__imp_MulDiv
0x18019859a  add     eax, [rbp+57h+Point.y]
0x18019859d  mov     [rbp+57h+rc.bottom], eax
0x1801985a0  xor     edx, edx; dwFlags
0x1801985a2  lea     rcx, [rbp+57h+rc]; lprc
0x1801985a6  call    cs:__imp_MonitorFromRect
0x1801985ac  cmp     rax, rbx
0x1801985af  jnz     short loc_1801985BA
0x1801985b1  movaps  xmm0, xmmword ptr [rbp+57h+rc.left]
0x1801985b5  movdqa  xmmword ptr [rbp+57h+Rect.left], xmm0
0x1801985ba  mov     [rbp+57h+ppidl], 0
0x1801985c2  lea     rdx, [rbp+57h+ppidl]; ppidl
0x1801985c6  mov     rcx, r14; punk
0x1801985c9  call    cs:__imp_SHGetIDListFromObject
0x1801985cf  mov     ebx, eax
0x1801985d1  test    eax, eax
0x1801985d3  jns     short loc_180198608
0x1801985d5  mov     rcx, [rbp+5Fh]; this
0x1801985d9  mov     r9d, eax; char *
0x1801985dc  lea     r8, aShellExplorerf_10; "shell\\explorerframe\\explorerframep.cp"...
0x1801985e3  mov     edx, 141Eh; void *
0x1801985e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801985ed  nop
0x1801985ee  lea     rcx, [rbp+57h+ppidl]
0x1801985f2  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1801985f7  nop
0x1801985f8  lea     rcx, [rbp+57h+var_B0]
0x1801985fc  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x180198601  mov     eax, ebx
0x180198603  jmp     loc_18019888D
0x180198608  mov     [rsi+151h], r13b
0x18019860f  mov     [rbp+57h+lpString1], 0
0x180198617  mov     [rbp+57h+var_98], 0
0x18019861f  mov     [rbp+57h+var_90], 0
0x180198627  mov     rax, [r14]
0x18019862a  mov     rbx, [rax+28h]
0x18019862e  lea     rcx, [rbp+57h+lpString1]
0x180198632  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180198637  or      r15, 0FFFFFFFFFFFFFFFFh
0x18019863b  mov     [rbp+57h+var_98], r15
0x18019863f  mov     [rbp+57h+var_90], r15
0x180198643  lea     r8, [rbp+57h+lpString1]
0x180198647  mov     edx, 80018001h
0x18019864c  mov     rcx, r14
0x18019864f  mov     rax, rbx
0x180198652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198657  test    eax, eax
0x180198659  js      loc_18019878D
0x18019865f  xor     r8d, r8d
0x180198662  mov     dl, r13b
0x180198665  lea     rbx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel> `wil::Feature<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::GetImpl(void)'::`2'::impl
0x18019866c  mov     rcx, rbx
0x18019866f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180198674  mov     [rsp+0F0h+bIgnoreCase], r13d; bIgnoreCase
0x180198679  mov     r9d, r15d; cchCount2
0x18019867c  lea     r8, aBb06c0e4D2934f; "::{BB06C0E4-D293-4F75-8A90-CB05B6477EEE"...
0x180198683  mov     edx, r15d; cchCount1
0x180198686  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18019868a  call    cs:__imp_CompareStringOrdinal
0x180198690  cmp     eax, 2
0x180198693  jnz     short loc_1801986BD
0x180198695  mov     r14b, r13b
0x180198698  xor     r8d, r8d
0x18019869b  mov     dl, r13b
0x18019869e  mov     rcx, rbx
0x1801986a1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1801986a6  mov     r8b, r13b
0x1801986a9  mov     dl, r13b
0x1801986ac  mov     rcx, rbx
0x1801986af  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1801986b4  lea     rbx, aMsSettingsAbou; "ms-settings:about"
0x1801986bb  jmp     short loc_1801986C2
0x1801986bd  xor     r14b, r14b
0x1801986c0  xor     ebx, ebx
0x1801986c2  mov     [rsp+0F0h+bIgnoreCase], r13d; bIgnoreCase
0x1801986c7  mov     r9d, r15d; cchCount2
0x1801986ca  lea     r8, aD450a8a1956845; "::{D450A8A1-9568-45C7-9C0E-B4F9FB4537BD"...
0x1801986d1  mov     edx, r15d; cchCount1
0x1801986d4  mov     rcx, [rbp+57h+lpString1]; lpString1
0x1801986d8  call    cs:__imp_CompareStringOrdinal
0x1801986de  cmp     eax, 2
0x1801986e1  jnz     short loc_1801986ED
0x1801986e3  mov     r14b, r13b
0x1801986e6  lea     rbx, aMsSettingsWind; "ms-settings:windowsupdate-uninstallupda"...
0x1801986ed  mov     [rsp+0F0h+bIgnoreCase], r13d; bIgnoreCase
0x1801986f2  mov     r9d, r15d; cchCount2
0x1801986f5  lea     r8, a17cd948812284b; "::{17CD9488-1228-4B2F-88CE-4298E93E0966"...
0x1801986fc  mov     edx, r15d; cchCount1
0x1801986ff  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180198703  call    cs:__imp_CompareStringOrdinal
0x180198709  cmp     eax, 2
0x18019870c  jnz     short loc_180198718
0x18019870e  mov     r14b, r13b
0x180198711  lea     rbx, aMsSettingsDefa; "ms-settings:defaultapps"
0x180198718  mov     [rsp+0F0h+bIgnoreCase], r13d; bIgnoreCase
0x18019871d  mov     r9d, r15d; cchCount2
0x180198720  lea     r8, aBd84b3808ca210; "::{BD84B380-8CA2-1069-AB1D-08000948F534"...
0x180198727  mov     edx, r15d; cchCount1
0x18019872a  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18019872e  call    cs:__imp_CompareStringOrdinal
0x180198734  cmp     eax, 2
0x180198737  jnz     short loc_180198743
0x180198739  mov     r14b, r13b
0x18019873c  lea     rbx, aMsSettingsFont; "ms-settings:fonts"
0x180198743  mov     [rsp+0F0h+bIgnoreCase], r13d; bIgnoreCase
0x180198748  mov     r9d, r15d; cchCount2
0x18019874b  lea     r8, aA8a91a663a7d44; "::{A8A91A66-3A7D-4424-8D24-04E180695C7A"...
0x180198752  mov     edx, r15d; cchCount1
0x180198755  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180198759  call    cs:__imp_CompareStringOrdinal
0x18019875f  cmp     eax, 2
0x180198762  jnz     short loc_180198770
0x180198764  mov     r14b, r13b
0x180198767  lea     rbx, aMsSettingsDevi; "ms-settings:devices"
0x18019876e  jmp     short loc_180198778
0x180198770  xor     r15d, r15d
0x180198773  test    rbx, rbx
0x180198776  jz      short loc_180198788
0x180198778  mov     edx, 2
0x18019877d  mov     rcx, rbx
0x180198780  call    ?LaunchRedirectedControlPanelEntryPoint@@YAJPEBGW4CPLENTRYPOINT@@@Z; LaunchRedirectedControlPanelEntryPoint(ushort const *,CPLENTRYPOINT)
0x180198785  mov     r15d, eax
0x180198788  test    r14b, r14b
0x18019878b  jnz     short loc_1801987AF
0x18019878d  mov     rcx, [rbp+57h+var_B0]
0x180198791  mov     rax, [rcx]
0x180198794  mov     [rsp+0F0h+bIgnoreCase], edi; int
0x180198798  lea     r9, [rbp+57h+Rect]
0x18019879c  mov     r8d, r13d
0x18019879f  mov     rdx, [rbp+57h+ppidl]
0x1801987a3  mov     rax, [rax+20h]
0x1801987a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801987ac  mov     r15d, eax
0x1801987af  mov     rcx, [rbp+5Fh]; this
0x1801987b3  test    r15d, r15d
0x1801987b6  jns     short loc_18019880E
0x1801987b8  mov     r9d, r15d; char *
0x1801987bb  lea     r8, aShellExplorerf_10; "shell\\explorerframe\\explorerframep.cp"...
0x1801987c2  mov     edx, 1469h; void *
0x1801987c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801987cc  mov     byte ptr [rsi+151h], 0
0x1801987d3  mov     rcx, [rbp+5Fh]; this
0x1801987d7  mov     r9d, r15d; char *
0x1801987da  lea     r8, aShellExplorerf_10; "shell\\explorerframe\\explorerframep.cp"...
0x1801987e1  mov     edx, 1472h; void *
0x1801987e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801987eb  nop
0x1801987ec  lea     rcx, [rbp+57h+lpString1]
0x1801987f0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801987f5  nop
0x1801987f6  lea     rcx, [rbp+57h+ppidl]
0x1801987fa  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1801987ff  nop
0x180198800  lea     rcx, [rbp+57h+var_B0]
0x180198804  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x180198809  mov     eax, r15d
  ... truncated ...
```
