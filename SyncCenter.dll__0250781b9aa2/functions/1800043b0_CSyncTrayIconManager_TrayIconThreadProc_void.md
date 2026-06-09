# CSyncTrayIconManager::_TrayIconThreadProc(void)

- ea: `0x1800043b0`
- end: `0x1800045d8`
- name: `?_TrayIconThreadProc@CSyncTrayIconManager@@AEAAXXZ`
- size: `552`
- prototype: `void __fastcall(CSyncTrayIconManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000b330`

## callees

- `0x1800043b0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180004496`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180004496`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800043c3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800043c3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800045b9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800045b9`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180004467`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180004467`
- `USER32!TranslateMessage` at `0x18000454c`
- `USER32!TranslateMessage` at `0x18000454c`
- `USER32!GetMessageW` at `0x18000453d`
- `USER32!GetMessageW` at `0x18000456a`
- `USER32!GetMessageW` at `0x18000453d`
- `USER32!GetMessageW` at `0x18000456a`
- `USER32!CreateWindowExW` at `0x18000450c`
- `USER32!CreateWindowExW` at `0x18000450c`
- `USER32!RegisterClassExW` at `0x18000444c`
- `USER32!RegisterClassExW` at `0x18000444c`
- `USER32!UnregisterClassW` at `0x1800045b3`
- `USER32!UnregisterClassW` at `0x1800045b3`
- `USER32!DispatchMessageW` at `0x180004557`
- `USER32!DispatchMessageW` at `0x180004557`

## pseudocode

```c
void __fastcall CSyncTrayIconManager::_TrayIconThreadProc(CSyncTrayIconManager *this)
{
  int v2; // eax
  __int32 v3; // edi
  LANGID UserDefaultUILanguage; // ax
  DWORD v5; // ecx
  HWND Window; // rax
  __int64 v7; // rcx
  tagMSG Msg; // [rsp+60h] [rbp-88h] BYREF
  WNDCLASSEXW v9; // [rsp+90h] [rbp-58h] BYREF
  int LCData; // [rsp+F8h] [rbp+10h] BYREF

  if ( CoInitializeEx(0, 6u) >= 0 )
  {
    v9.lpfnWndProc = (WNDPROC)CSyncTrayIconManager::s_TrayIconWindowProc;
    v9.hInstance = g_hmodThisDll;
    *(_QWORD *)&v9.cbSize = 80;
    *(_QWORD *)&v9.cbClsExtra = 0;
    memset(&v9.hIcon, 0, 32);
    v9.hIconSm = 0;
    v9.lpszClassName = L"SyncMgrTrayIconClass";
    RegisterClassExW(&v9);
    v2 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
    if ( `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi == -1 )
    {
      v3 = 0;
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      `IsBiDiLocalizedSystemEx'::`2'::s_langID = UserDefaultUILanguage;
      if ( UserDefaultUILanguage )
      {
        LCData = 0;
        if ( GetLocaleInfoW(UserDefaultUILanguage, 0x20000070u, (LPWSTR)&LCData, 2) > 0 )
          LOBYTE(v3) = LCData == 1;
      }
      _InterlockedExchange(&`IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi, v3);
      v2 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
    }
    v5 = 0;
    if ( v2 == 1 )
      v5 = 0x400000;
    Window = CreateWindowExW(
               v5,
               L"SyncMgrTrayIconClass",
               L"SyncMgrTrayIconWindow",
               0x80000000,
               0,
               0,
               0,
               0,
               HWND_MESSAGE,
               0,
               g_hmodThisDll,
               this);
    *((_QWORD *)this + 3) = Window;
    if ( Window )
    {
      memset(&Msg, 0, sizeof(Msg));
      while ( GetMessageW(&Msg, 0, 0, 0) > 0 )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
    }
    v7 = *((_QWORD *)this + 7);
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v7 + 72LL))(v7, *((unsigned int *)this + 8), 1);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 16LL))(*((_QWORD *)this + 7));
      *((_QWORD *)this + 7) = 0;
      *((_DWORD *)this + 8) = 0;
    }
    UnregisterClassW(L"SyncMgrTrayIconClass", g_hmodThisDll);
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x1800043b0  push    rbx
0x1800043b2  sub     rsp, 0E0h
0x1800043b9  mov     rbx, rcx
0x1800043bc  mov     edx, 6; dwCoInit
0x1800043c1  xor     ecx, ecx; pvReserved
0x1800043c3  call    cs:__imp_CoInitializeEx
0x1800043c9  test    eax, eax
0x1800043cb  js      loc_1800045CF
0x1800043d1  lea     rax, ?s_TrayIconWindowProc@CSyncTrayIconManager@@CA_JPEAUHWND__@@I_K_J@Z; CSyncTrayIconManager::s_TrayIconWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800043d8  mov     [rsp+0E8h+arg_0], rbp
0x1800043e0  mov     [rsp+0E8h+var_58.lpfnWndProc], rax
0x1800043e8  lea     rbp, szClass; "SyncMgrTrayIconClass"
0x1800043ef  mov     rax, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hmodThisDll
0x1800043f6  lea     rcx, [rsp+0E8h+var_58]; WNDCLASSEXW *
0x1800043fe  xorps   xmm0, xmm0
0x180004401  mov     [rsp+0E8h+arg_10], rsi
0x180004409  xor     esi, esi
0x18000440b  mov     [rsp+0E8h+var_58.hInstance], rax
0x180004413  xorps   xmm1, xmm1
0x180004416  mov     qword ptr [rsp+0E8h+var_58.cbSize], 50h ; 'P'
0x180004422  mov     qword ptr [rsp+0E8h+var_58.cbClsExtra], rsi
0x18000442a  movdqa  xmmword ptr [rsp+0E8h+var_58.hIcon], xmm0
0x180004433  movdqa  xmmword ptr [rsp+0E8h+var_58.hbrBackground], xmm1
0x18000443c  mov     [rsp+0E8h+var_58.hIconSm], rsi
0x180004444  mov     [rsp+0E8h+var_58.lpszClassName], rbp
0x18000444c  call    cs:__imp_RegisterClassExW
0x180004452  mov     eax, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x180004458  cmp     eax, 0FFFFFFFFh
0x18000445b  jnz     short loc_1800044C0
0x18000445d  mov     [rsp+0E8h+arg_18], rdi
0x180004465  mov     edi, esi
0x180004467  call    cs:__imp_GetUserDefaultUILanguage
0x18000446d  mov     cs:?s_langID@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4GA, ax; ushort `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_langID
0x180004474  test    ax, ax
0x180004477  jz      short loc_1800044AC
0x180004479  movzx   ecx, ax; Locale
0x18000447c  lea     r8, [rsp+0E8h+LCData]; lpLCData
0x180004484  mov     r9d, 2; cchData
0x18000448a  mov     [rsp+0E8h+LCData], esi
0x180004491  mov     edx, 20000070h; LCType
0x180004496  call    cs:__imp_GetLocaleInfoW
0x18000449c  test    eax, eax
0x18000449e  jle     short loc_1800044AC
0x1800044a0  cmp     [rsp+0E8h+LCData], 1
0x1800044a8  setz    dil
0x1800044ac  xchg    edi, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x1800044b2  mov     rdi, [rsp+0E8h+arg_18]
0x1800044ba  mov     eax, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x1800044c0  mov     [rsp+0E8h+lpParam], rbx; lpParam
0x1800044c5  lea     r8, szWindow; "SyncMgrTrayIconWindow"
0x1800044cc  cmp     eax, 1
0x1800044cf  mov     ecx, esi
0x1800044d1  mov     rax, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hmodThisDll
0x1800044d8  mov     edx, 400000h
0x1800044dd  mov     [rsp+0E8h+hInstance], rax; hInstance
0x1800044e2  cmovz   ecx, edx; dwExStyle
0x1800044e5  mov     [rsp+0E8h+hMenu], rsi; hMenu
0x1800044ea  mov     r9d, 80000000h; dwStyle
0x1800044f0  mov     [rsp+0E8h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x1800044f9  mov     rdx, rbp; lpClassName
0x1800044fc  mov     [rsp+0E8h+nHeight], esi; nHeight
0x180004500  mov     [rsp+0E8h+nWidth], esi; nWidth
0x180004504  mov     [rsp+0E8h+Y], esi; Y
0x180004508  mov     [rsp+0E8h+X], esi; X
0x18000450c  call    cs:__imp_CreateWindowExW
0x180004512  mov     [rbx+18h], rax
0x180004516  test    rax, rax
0x180004519  jz      short loc_180004574
0x18000451b  xorps   xmm0, xmm0
0x18000451e  lea     rcx, [rsp+0E8h+Msg]; lpMsg
0x180004523  xor     r9d, r9d; wMsgFilterMax
0x180004526  xor     r8d, r8d; wMsgFilterMin
0x180004529  xor     edx, edx; hWnd
0x18000452b  movups  xmmword ptr [rsp+0E8h+Msg.hwnd], xmm0
0x180004530  movups  xmmword ptr [rsp+0E8h+Msg.wParam], xmm0
0x180004535  movups  xmmword ptr [rsp+0E8h+Msg.time], xmm0
0x18000453d  call    cs:__imp_GetMessageW
0x180004543  test    eax, eax
0x180004545  jle     short loc_180004574
0x180004547  lea     rcx, [rsp+0E8h+Msg]; lpMsg
0x18000454c  call    cs:__imp_TranslateMessage
0x180004552  lea     rcx, [rsp+0E8h+Msg]; lpMsg
0x180004557  call    cs:__imp_DispatchMessageW
0x18000455d  xor     r9d, r9d; wMsgFilterMax
0x180004560  lea     rcx, [rsp+0E8h+Msg]; lpMsg
0x180004565  xor     r8d, r8d; wMsgFilterMin
0x180004568  xor     edx, edx; hWnd
0x18000456a  call    cs:__imp_GetMessageW
0x180004570  test    eax, eax
0x180004572  jg      short loc_180004547
0x180004574  mov     rcx, [rbx+38h]
0x180004578  test    rcx, rcx
0x18000457b  jz      short loc_1800045A9
0x18000457d  mov     rax, [rcx]
0x180004580  mov     r8d, 1
0x180004586  mov     edx, [rbx+20h]
0x180004589  mov     rax, [rax+48h]
0x18000458d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004592  mov     rcx, [rbx+38h]
0x180004596  mov     rax, [rcx]
0x180004599  mov     rax, [rax+10h]
0x18000459d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045a2  mov     [rbx+38h], rsi
0x1800045a6  mov     [rbx+20h], esi
0x1800045a9  mov     rdx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; hInstance
0x1800045b0  mov     rcx, rbp; lpClassName
0x1800045b3  call    cs:__imp_UnregisterClassW
0x1800045b9  call    cs:__imp_CoUninitialize
0x1800045bf  mov     rsi, [rsp+0E8h+arg_10]
0x1800045c7  mov     rbp, [rsp+0E8h+arg_0]
0x1800045cf  add     rsp, 0E0h
0x1800045d6  pop     rbx
0x1800045d7  retn
```
