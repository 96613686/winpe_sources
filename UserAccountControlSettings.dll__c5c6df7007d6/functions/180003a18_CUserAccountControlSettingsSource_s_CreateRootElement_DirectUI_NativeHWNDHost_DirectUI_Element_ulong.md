# CUserAccountControlSettingsSource::s_CreateRootElement(DirectUI::NativeHWNDHost * *,DirectUI::Element * *,ulong *)

- ea: `0x180003a18`
- end: `0x180003da3`
- name: `?s_CreateRootElement@CUserAccountControlSettingsSource@@CAJPEAPEAVNativeHWNDHost@DirectUI@@PEAPEAVElement@3@PEAK@Z`
- size: `907`
- prototype: `__int64 __fastcall(struct DirectUI::NativeHWNDHost **, struct DirectUI::Element **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000377c`

## callees

- `0x1800039c4`
- `0x180003a18`
- `0x1800090a0`
- `0x18000b2dc`
- `0x18000b710`
- `0x18000c010`

## import_xrefs

- `SHELL32!__imp_SetWindowRelaunchProperties` at `0x180003d64`
- `SHELL32!__imp_SetWindowRelaunchProperties` at `0x180003d64`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003c17`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003c17`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003be0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003be0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180003a72`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180003a72`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180003b47`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180003b47`
- `GDI32!GetDeviceCaps` at `0x180003a99`
- `GDI32!GetDeviceCaps` at `0x180003aa9`
- `GDI32!GetDeviceCaps` at `0x180003a99`
- `GDI32!GetDeviceCaps` at `0x180003aa9`
- `KERNEL32!MulDiv` at `0x180003ad2`
- `KERNEL32!MulDiv` at `0x180003ae7`
- `KERNEL32!MulDiv` at `0x180003ad2`
- `KERNEL32!MulDiv` at `0x180003ae7`
- `USER32!ReleaseDC` at `0x180003ab6`
- `USER32!ReleaseDC` at `0x180003ab6`
- `USER32!GetDC` at `0x180003a83`
- `USER32!GetDC` at `0x180003a83`
- `USER32!SystemParametersInfoW` at `0x180003b02`
- `USER32!SystemParametersInfoW` at `0x180003b02`
- `USER32!GetAncestor` at `0x180003ce1`
- `USER32!GetAncestor` at `0x180003ce1`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180003bca`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180003bca`
- `DUI70!?Create@NativeHWNDHost@DirectUI@@SAJPEBG0PEAUHWND__@@PEAUHICON__@@HHHHHHPEAUHINSTANCE__@@IPEAPEAV12@@Z` at `0x180003bb2`
- `DUI70!?Create@NativeHWNDHost@DirectUI@@SAJPEBG0PEAUHWND__@@PEAUHICON__@@HHHHHHPEAUHINSTANCE__@@IPEAPEAV12@@Z` at `0x180003bb2`
- `DUI70!?Create@HWNDElement@DirectUI@@SAJPEAUHWND__@@_NIPEAVElement@2@PEAKPEAPEAV42@@Z` at `0x180003c3c`
- `DUI70!?Create@HWNDElement@DirectUI@@SAJPEAUHWND__@@_NIPEAVElement@2@PEAKPEAPEAV42@@Z` at `0x180003c3c`
- `DUI70!?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z` at `0x180003c54`
- `DUI70!?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z` at `0x180003c54`
- `DUI70!?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z` at `0x180003c63`
- `DUI70!?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z` at `0x180003c63`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x180003c7b`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x180003c7b`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x180003c8b`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x180003c8b`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180003c99`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180003c99`
- `DUI70!?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z` at `0x180003ca9`
- `DUI70!?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z` at `0x180003ca9`
- `DUI70!?Destroy@NativeHWNDHost@DirectUI@@QEAAXXZ` at `0x180003d71`
- `DUI70!?Destroy@NativeHWNDHost@DirectUI@@QEAAXXZ` at `0x180003d71`

## string_xrefs

- `0x180003bd6`: `imageres.dll`
- `0x180003d3b`: `@%SystemRoot%\system32\shell32.dll,-4161`
- `0x180003d47`: `%SystemRoot%\system32\shell32.dll,-22`
- `0x180003d53`: `%SystemRoot%\system32\control.exe`

## pseudocode

```c
__int64 __fastcall CUserAccountControlSettingsSource::s_CreateRootElement(
        struct DirectUI::NativeHWNDHost **a1,
        struct DirectUI::Element **a2,
        unsigned int *a3)
{
  int v3; // r14d
  HINSTANCE v7; // rcx
  HDC DC; // rax
  HDC v9; // rbx
  int DeviceCaps; // edi
  int v11; // esi
  int v12; // edi
  int v13; // esi
  int v14; // ebx
  int v15; // edi
  int v16; // esi
  LANGID ThreadUILanguage; // ax
  int v18; // eax
  int v19; // ebx
  HWND HWND; // rdi
  HMODULE Library; // rax
  HINSTANCE v22; // rbx
  struct DirectUI::Element *v23; // rcx
  struct DirectUI::NativeHWNDHost *v24; // rax
  HWND v25; // rax
  HWND Ancestor; // rdi
  unsigned int (__fastcall *v27)(HWND, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64, unsigned __int64, unsigned __int64), _QWORD, struct DirectUI::Element *); // rax
  struct DirectUI::Element *v28; // rsi
  __int64 v30; // [rsp+28h] [rbp-D8h]
  struct DirectUI::Element *v31; // [rsp+70h] [rbp-90h] BYREF
  struct DirectUI::NativeHWNDHost *v32; // [rsp+78h] [rbp-88h] BYREF
  struct DirectUI::Layout *v33; // [rsp+80h] [rbp-80h] BYREF
  __int128 pvParam; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Buffer[128]; // [rsp+A0h] [rbp-60h] BYREF

  v3 = 0;
  *a1 = 0;
  *a2 = 0;
  v7 = g_hinst;
  *a3 = 0;
  if ( !LoadStringW(v7, 0x46u, Buffer, 128) )
    Buffer[0] = 0;
  DC = GetDC(0);
  v9 = DC;
  if ( DC )
  {
    DeviceCaps = GetDeviceCaps(DC, 88);
    v11 = GetDeviceCaps(v9, 90);
    ReleaseDC(0, v9);
  }
  else
  {
    DeviceCaps = 96;
    v11 = 96;
  }
  v12 = MulDiv(760, DeviceCaps, 96);
  v13 = MulDiv(560, v11, 96);
  pvParam = 0;
  if ( SystemParametersInfoW(0x30u, 0, &pvParam, 0) )
  {
    v14 = DWORD2(pvParam) - pvParam;
    if ( v12 <= DWORD2(pvParam) - (int)pvParam )
      v14 = v12;
    v15 = HIDWORD(pvParam) - DWORD1(pvParam);
    if ( v13 <= HIDWORD(pvParam) - DWORD1(pvParam) )
      v15 = v13;
    v16 = (DWORD2(pvParam) - (int)pvParam - v14) / 2;
    v3 = (HIDWORD(pvParam) - DWORD1(pvParam) - v15) / 2;
  }
  else
  {
    v14 = v12;
    v15 = v13;
    v16 = 0;
  }
  ThreadUILanguage = GetThreadUILanguage();
  v18 = IsBiDiLocale(ThreadUILanguage);
  v32 = 0;
  v19 = DirectUI::NativeHWNDHost::Create(
          0,
          Buffer,
          0,
          0,
          v16,
          v3,
          v14,
          v15,
          v18 != 0 ? 4194560 : 256,
          349110272,
          0,
          0x10u,
          &v32);
  if ( v19 >= 0 )
  {
    HWND = DirectUI::NativeHWNDHost::GetHWND(v32);
    Library = LoadLibraryExW(L"imageres.dll", 0, 2u);
    v22 = Library;
    if ( Library )
    {
      CUserAccountControlSettingsSource::s_ApplyShieldIconToWindow(Library, HWND, 1, 1u);
      CUserAccountControlSettingsSource::s_ApplyShieldIconToWindow(v22, HWND, 0, 0);
      FreeLibrary(v22);
    }
    v31 = 0;
    v19 = DirectUI::HWNDElement::Create(HWND, 0, 0, 0, a3, &v31);
    if ( v19 < 0 || (v33 = 0, DirectUI::FillLayout::Create(&v33), v19 = DirectUI::Element::SetLayout(v31, v33), v19 < 0) )
    {
      DirectUI::NativeHWNDHost::Destroy(v32);
    }
    else
    {
      DirectUI::Element::SetAccessible(v31, 1);
      DirectUI::Element::SetAccRole(v31, 10);
      DirectUI::Element::SetVisible(v31, 1);
      DirectUI::NativeHWNDHost::Host(v32, v31);
      v23 = v31;
      v24 = v32;
      *a2 = v31;
      *a1 = v24;
      v25 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v23 + 360LL))(v23);
      if ( v25 )
      {
        Ancestor = GetAncestor(v25, 2u);
        if ( Ancestor )
        {
          v27 = (unsigned int (__fastcall *)(HWND, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64, unsigned __int64, unsigned __int64), _QWORD, struct DirectUI::Element *))qword_180015270;
          v28 = v31;
          if ( qword_180015270 == -1 )
          {
            GetProcFromComCtl32(&qword_180015270, 410);
            v27 = (unsigned int (__fastcall *)(HWND, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64, unsigned __int64, unsigned __int64), _QWORD, struct DirectUI::Element *))qword_180015270;
          }
          if ( v27 && v27(Ancestor, CUserAccountControlSettingsSource::s_SubclassWndProc, 0, v28) )
          {
            LODWORD(v30) = 0;
            SetWindowRelaunchProperties(
              Ancestor,
              L"Microsoft.Windows.ControlPanel",
              L"%SystemRoot%\\system32\\control.exe",
              L"%SystemRoot%\\system32\\shell32.dll,-22",
              L"@%SystemRoot%\\system32\\shell32.dll,-4161",
              v30);
          }
        }
      }
    }
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180003a18  mov     [rsp-8+arg_18], rbx
0x180003a1d  push    rbp
0x180003a1e  push    rsi
0x180003a1f  push    rdi
0x180003a20  push    r12
0x180003a22  push    r13
0x180003a24  push    r14
0x180003a26  push    r15
0x180003a28  lea     rbp, [rsp-0B0h]
0x180003a30  sub     rsp, 1B0h
0x180003a37  mov     rax, cs:__security_cookie
0x180003a3e  xor     rax, rsp
0x180003a41  mov     [rbp+0E0h+var_40], rax
0x180003a48  xor     r14d, r14d
0x180003a4b  mov     r15, r8
0x180003a4e  mov     [rcx], r14
0x180003a51  mov     r13, rdx
0x180003a54  mov     [rdx], r14
0x180003a57  mov     r12, rcx
0x180003a5a  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180003a61  mov     r9d, 80h; cchBufferMax
0x180003a67  mov     [r8], r14d
0x180003a6a  lea     edx, [r14+46h]; uID
0x180003a6e  lea     r8, [rbp+0E0h+Buffer]; lpBuffer
0x180003a72  call    cs:__imp_LoadStringW
0x180003a78  test    eax, eax
0x180003a7a  jnz     short loc_180003A81
0x180003a7c  mov     [rbp+0E0h+Buffer], r14w
0x180003a81  xor     ecx, ecx; hWnd
0x180003a83  call    cs:__imp_GetDC
0x180003a89  mov     rbx, rax
0x180003a8c  test    rax, rax
0x180003a8f  jz      short loc_180003ABE
0x180003a91  mov     edx, 58h ; 'X'; index
0x180003a96  mov     rcx, rax; hdc
0x180003a99  call    cs:__imp_GetDeviceCaps
0x180003a9f  mov     edx, 5Ah ; 'Z'; index
0x180003aa4  mov     rcx, rbx; hdc
0x180003aa7  mov     edi, eax
0x180003aa9  call    cs:__imp_GetDeviceCaps
0x180003aaf  mov     rdx, rbx; hDC
0x180003ab2  xor     ecx, ecx; hWnd
0x180003ab4  mov     esi, eax
0x180003ab6  call    cs:__imp_ReleaseDC
0x180003abc  jmp     short loc_180003AC5
0x180003abe  mov     edi, 60h ; '`'
0x180003ac3  mov     esi, edi
0x180003ac5  mov     r8d, 60h ; '`'; nDenominator
0x180003acb  mov     edx, edi; nNumerator
0x180003acd  mov     ecx, 2F8h; nNumber
0x180003ad2  call    cs:__imp_MulDiv
0x180003ad8  mov     r8d, 60h ; '`'; nDenominator
0x180003ade  mov     edx, esi; nNumerator
0x180003ae0  mov     ecx, 230h; nNumber
0x180003ae5  mov     edi, eax
0x180003ae7  call    cs:__imp_MulDiv
0x180003aed  xor     edx, edx; uiParam
0x180003aef  lea     r8, [rbp+0E0h+pvParam]; pvParam
0x180003af3  xorps   xmm0, xmm0
0x180003af6  xor     r9d, r9d; fWinIni
0x180003af9  mov     esi, eax
0x180003afb  movups  [rbp+0E0h+pvParam], xmm0
0x180003aff  lea     ecx, [rdx+30h]; uiAction
0x180003b02  call    cs:__imp_SystemParametersInfoW
0x180003b08  mov     r8d, 2
0x180003b0e  test    eax, eax
0x180003b10  jz      short loc_180003B41
0x180003b12  mov     eax, dword ptr [rbp+0E0h+pvParam+8]
0x180003b15  sub     eax, dword ptr [rbp+0E0h+pvParam]
0x180003b18  mov     ecx, dword ptr [rbp+0E0h+pvParam+0Ch]
0x180003b1b  cmp     edi, eax
0x180003b1d  mov     ebx, eax
0x180003b1f  cmovle  ebx, edi
0x180003b22  sub     ecx, dword ptr [rbp+0E0h+pvParam+4]
0x180003b25  cmp     esi, ecx
0x180003b27  mov     edi, ecx
0x180003b29  cmovle  edi, esi
0x180003b2c  sub     eax, ebx
0x180003b2e  cdq
0x180003b2f  sub     ecx, edi
0x180003b31  idiv    r8d
0x180003b34  mov     esi, eax
0x180003b36  mov     eax, ecx
0x180003b38  cdq
0x180003b39  idiv    r8d
0x180003b3c  mov     r14d, eax
0x180003b3f  jmp     short loc_180003B47
0x180003b41  mov     ebx, edi
0x180003b43  mov     edi, esi
0x180003b45  xor     esi, esi
0x180003b47  call    cs:__imp_GetThreadUILanguage
0x180003b4d  movzx   ecx, ax; unsigned int
0x180003b50  call    ?IsBiDiLocale@@YAHK@Z; IsBiDiLocale(ulong)
0x180003b55  neg     eax
0x180003b57  mov     [rsp+1E0h+var_168], 0
0x180003b60  lea     rax, [rsp+1E0h+var_168]
0x180003b65  mov     [rsp+1E0h+var_180], rax
0x180003b6a  lea     rdx, [rbp+0E0h+Buffer]
0x180003b6e  mov     [rsp+1E0h+var_188], 10h
0x180003b76  sbb     ecx, ecx
0x180003b78  mov     [rsp+1E0h+var_190], 0
0x180003b81  and     ecx, 400000h
0x180003b87  mov     [rsp+1E0h+var_198], 14CF0000h
0x180003b8f  add     ecx, 100h
0x180003b95  mov     [rsp+1E0h+var_1A0], ecx
0x180003b99  xor     r9d, r9d
0x180003b9c  mov     [rsp+1E0h+var_1A8], edi
0x180003ba0  xor     r8d, r8d
0x180003ba3  mov     [rsp+1E0h+var_1B0], ebx
0x180003ba7  xor     ecx, ecx
0x180003ba9  mov     dword ptr [rsp+1E0h+var_1B8], r14d
0x180003bae  mov     dword ptr [rsp+1E0h+var_1C0], esi
0x180003bb2  call    cs:__imp_?Create@NativeHWNDHost@DirectUI@@SAJPEBG0PEAUHWND__@@PEAUHICON__@@HHHHHHPEAUHINSTANCE__@@IPEAPEAV12@@Z; DirectUI::NativeHWNDHost::Create(ushort const *,ushort const *,HWND__ *,HICON__ *,int,int,int,int,int,int,HINSTANCE__ *,uint,DirectUI::NativeHWNDHost * *)
0x180003bb8  xor     r14d, r14d
0x180003bbb  mov     ebx, eax
0x180003bbd  test    eax, eax
0x180003bbf  js      loc_180003D77
0x180003bc5  mov     rcx, [rsp+1E0h+var_168]
0x180003bca  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x180003bd0  xor     edx, edx; hFile
0x180003bd2  lea     r8d, [r14+2]; dwFlags
0x180003bd6  lea     rcx, LibFileName; "imageres.dll"
0x180003bdd  mov     rdi, rax
0x180003be0  call    cs:__imp_LoadLibraryExW
0x180003be6  lea     esi, [r14+1]
0x180003bea  mov     rbx, rax
0x180003bed  test    rax, rax
0x180003bf0  jz      short loc_180003C1D
0x180003bf2  mov     r9d, esi; unsigned __int64
0x180003bf5  mov     r8d, esi; int
0x180003bf8  mov     rdx, rdi; HWND
0x180003bfb  mov     rcx, rax; HINSTANCE
0x180003bfe  call    ?s_ApplyShieldIconToWindow@CUserAccountControlSettingsSource@@CAXPEAUHINSTANCE__@@PEAUHWND__@@H_K@Z; CUserAccountControlSettingsSource::s_ApplyShieldIconToWindow(HINSTANCE__ *,HWND__ *,int,unsigned __int64)
0x180003c03  xor     r9d, r9d; unsigned __int64
0x180003c06  xor     r8d, r8d; int
0x180003c09  mov     rdx, rdi; HWND
0x180003c0c  mov     rcx, rbx; HINSTANCE
0x180003c0f  call    ?s_ApplyShieldIconToWindow@CUserAccountControlSettingsSource@@CAXPEAUHINSTANCE__@@PEAUHWND__@@H_K@Z; CUserAccountControlSettingsSource::s_ApplyShieldIconToWindow(HINSTANCE__ *,HWND__ *,int,unsigned __int64)
0x180003c14  mov     rcx, rbx; hLibModule
0x180003c17  call    cs:__imp_FreeLibrary
0x180003c1d  lea     rax, [rsp+1E0h+var_170]
0x180003c22  mov     [rsp+1E0h+var_170], r14
0x180003c27  mov     [rsp+1E0h+var_1B8], rax
0x180003c2c  xor     r9d, r9d
0x180003c2f  xor     r8d, r8d
0x180003c32  mov     [rsp+1E0h+var_1C0], r15
0x180003c37  xor     edx, edx
0x180003c39  mov     rcx, rdi
0x180003c3c  call    cs:__imp_?Create@HWNDElement@DirectUI@@SAJPEAUHWND__@@_NIPEAVElement@2@PEAKPEAPEAV42@@Z; DirectUI::HWNDElement::Create(HWND__ *,bool,uint,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180003c42  mov     ebx, eax
0x180003c44  test    eax, eax
0x180003c46  js      loc_180003D6C
0x180003c4c  lea     rcx, [rbp+0E0h+var_160]
0x180003c50  mov     [rbp+0E0h+var_160], r14
0x180003c54  call    cs:__imp_?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z; DirectUI::FillLayout::Create(DirectUI::Layout * *)
0x180003c5a  mov     rdx, [rbp+0E0h+var_160]
0x180003c5e  mov     rcx, [rsp+1E0h+var_170]
0x180003c63  call    cs:__imp_?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z; DirectUI::Element::SetLayout(DirectUI::Layout *)
0x180003c69  mov     ebx, eax
0x180003c6b  test    eax, eax
0x180003c6d  js      loc_180003D6C
0x180003c73  mov     rcx, [rsp+1E0h+var_170]
0x180003c78  mov     dl, sil
0x180003c7b  call    cs:__imp_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetAccessible(bool)
0x180003c81  mov     rcx, [rsp+1E0h+var_170]
0x180003c86  mov     edx, 0Ah
0x180003c8b  call    cs:__imp_?SetAccRole@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAccRole(int)
0x180003c91  mov     rcx, [rsp+1E0h+var_170]
0x180003c96  mov     dl, sil
0x180003c99  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180003c9f  mov     rdx, [rsp+1E0h+var_170]
0x180003ca4  mov     rcx, [rsp+1E0h+var_168]
0x180003ca9  call    cs:__imp_?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z; DirectUI::NativeHWNDHost::Host(DirectUI::Element *)
0x180003caf  mov     rcx, [rsp+1E0h+var_170]
0x180003cb4  mov     rax, [rsp+1E0h+var_168]
0x180003cb9  mov     [r13+0], rcx
0x180003cbd  mov     [r12], rax
0x180003cc1  mov     rax, [rcx]
0x180003cc4  mov     rax, [rax+168h]
0x180003ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cd0  test    rax, rax
0x180003cd3  jz      loc_180003D77
0x180003cd9  mov     edx, 2; gaFlags
0x180003cde  mov     rcx, rax; hwnd
0x180003ce1  call    cs:__imp_GetAncestor
0x180003ce7  mov     rdi, rax
0x180003cea  test    rax, rax
0x180003ced  jz      loc_180003D77
0x180003cf3  mov     rax, cs:qword_180015270
0x180003cfa  mov     rsi, [rsp+1E0h+var_170]
0x180003cff  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003d03  jnz     short loc_180003D1D
0x180003d05  mov     edx, 19Ah
0x180003d0a  lea     rcx, qword_180015270
0x180003d11  call    _GetProcFromComCtl32
0x180003d16  mov     rax, cs:qword_180015270
0x180003d1d  test    rax, rax
0x180003d20  jz      short loc_180003D77
0x180003d22  mov     r9, rsi
0x180003d25  lea     rdx, ?s_SubclassWndProc@CUserAccountControlSettingsSource@@CA_JPEAUHWND__@@I_K_J11@Z; CUserAccountControlSettingsSource::s_SubclassWndProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x180003d2c  xor     r8d, r8d
0x180003d2f  mov     rcx, rdi
0x180003d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d37  test    eax, eax
0x180003d39  jz      short loc_180003D77
0x180003d3b  lea     rax, aSystemrootSyst_0; "@%SystemRoot%\\system32\\shell32.dll,-4"...
0x180003d42  mov     dword ptr [rsp+1E0h+var_1B8], r14d
0x180003d47  lea     r9, aSystemrootSyst; "%SystemRoot%\\system32\\shell32.dll,-22"
0x180003d4e  mov     [rsp+1E0h+var_1C0], rax
0x180003d53  lea     r8, aSystemrootSyst_1; "%SystemRoot%\\system32\\control.exe"
0x180003d5a  mov     rcx, rdi
0x180003d5d  lea     rdx, aMicrosoftWindo; "Microsoft.Windows.ControlPanel"
0x180003d64  call    cs:__imp_SetWindowRelaunchProperties
0x180003d6a  jmp     short loc_180003D77
0x180003d6c  mov     rcx, [rsp+1E0h+var_168]
0x180003d71  call    cs:__imp_?Destroy@NativeHWNDHost@DirectUI@@QEAAXXZ; DirectUI::NativeHWNDHost::Destroy(void)
0x180003d77  mov     eax, ebx
0x180003d79  mov     rcx, [rbp+0E0h+var_40]
0x180003d80  xor     rcx, rsp; StackCookie
0x180003d83  call    __security_check_cookie
0x180003d88  mov     rbx, [rsp+1E0h+arg_18]
0x180003d90  add     rsp, 1B0h
0x180003d97  pop     r15
0x180003d99  pop     r14
0x180003d9b  pop     r13
0x180003d9d  pop     r12
0x180003d9f  pop     rdi
0x180003da0  pop     rsi
0x180003da1  pop     rbp
0x180003da2  retn
```
