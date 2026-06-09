# CInstalledApp::s_CreateInstance(ulong,ushort const *,_GUID const &,void * *)

- ea: `0x18002cce8`
- end: `0x18002cf31`
- name: `?s_CreateInstance@CInstalledApp@@SAJKPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `585`
- prototype: `__int64 __fastcall(unsigned int, LPCWSTR szProduct, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002d610`
- `0x18002da98`

## callees

- `0x18000b2dc`
- `0x18000dd44`
- `0x18001d668`
- `0x180029da8`
- `0x18002a058`
- `0x18002cce8`
- `0x18002d1dc`
- `0x180044db4`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `SHCORE!SHQueryValueExW` at `0x18002cd7b`
- `SHCORE!SHQueryValueExW` at `0x18002cd7b`
- `msi!__imp_MsiGetProductInfoW` at `0x18002cdc2`
- `msi!__imp_MsiGetProductInfoW` at `0x18002cdc2`

## string_xrefs

- `0x18002ce68`: `UninstallString`
- `0x18002cd65`: `WindowsInstaller`

## pseudocode

```c
__int64 __fastcall CInstalledApp::s_CreateInstance(
        unsigned int a1,
        LPCWSTR szProduct,
        const struct _GUID *a3,
        void **a4)
{
  int v7; // r14d
  HKEY v8; // rbx
  LSTATUS v9; // eax
  bool v10; // sf
  unsigned __int64 v11; // rdx
  CInstalledApp *v12; // rax
  CInstalledApp *v13; // rax
  CInstalledApp *v14; // rbx
  const unsigned __int16 *v15; // rsi
  unsigned __int64 v16; // rdx
  const unsigned __int16 *v17; // rdi
  CInstalledApp *v18; // rax
  CInstalledApp *v19; // rax
  CInstalledApp *v20; // rbx
  int pvData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD pdwType; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pcchValueBuf[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *LocalizedStringFromRegistry; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueBuf[264]; // [rsp+60h] [rbp-A0h] BYREF

  *a4 = 0;
  hkey = 0;
  v7 = CInstalledApp::s_OpenUninstallRegKey(a1, szProduct, (unsigned int)a3, &hkey);
  if ( v7 >= 0 )
  {
    v8 = hkey;
    pvData = 0;
    pcbData = 4;
    pdwType = 0;
    v9 = SHQueryValueExW(hkey, L"WindowsInstaller", 0, &pdwType, &pvData, &pcbData);
    v10 = v9 < 0;
    if ( v9 > 0 )
      v10 = 1;
    if ( v10 || pvData != 1 )
    {
      v7 = -2147024809;
      LocalizedStringFromRegistry = GetLocalizedStringFromRegistry(v8, L"DisplayName");
      v15 = LocalizedStringFromRegistry;
      if ( LocalizedStringFromRegistry )
      {
        *(_QWORD *)pcchValueBuf = GetLocalizedStringFromRegistry(v8, L"UninstallString");
        v17 = *(const unsigned __int16 **)pcchValueBuf;
        if ( *(_QWORD *)pcchValueBuf )
        {
          v7 = -2147024882;
          v18 = (CInstalledApp *)DirectUI::HAllocAndZero((DirectUI *)0x1B00, v16);
          if ( v18 )
          {
            v19 = CInstalledApp::CInstalledApp(v18, v8, szProduct, v15, v17, a1);
            v20 = v19;
            if ( v19 )
            {
              v7 = (**(__int64 (__fastcall ***)(CInstalledApp *, GUID *, void **))v19)(
                     v19,
                     &GUID_1ffd2211_d3ed_426d_9206_7231b0444d3f,
                     a4);
              (*(void (__fastcall **)(CInstalledApp *))(*(_QWORD *)v20 + 16LL))(v20);
            }
          }
        }
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(pcchValueBuf);
      }
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&LocalizedStringFromRegistry);
    }
    else
    {
      pcchValueBuf[0] = 260;
      v7 = -2147024809;
      MsiGetProductInfoW(szProduct, L"ProductName", ValueBuf, pcchValueBuf);
      if ( ValueBuf[0] )
      {
        v7 = -2147024882;
        v12 = (CInstalledApp *)DirectUI::HAllocAndZero((DirectUI *)0x1B00, v11);
        if ( v12 )
        {
          v13 = CInstalledApp::CInstalledApp(v12, 0, szProduct, ValueBuf, a1, MSIINSTALLCONTEXT_FIRSTVISIBLE);
          v14 = v13;
          if ( v13 )
          {
            v7 = (**(__int64 (__fastcall ***)(CInstalledApp *, GUID *, void **))v13)(
                   v13,
                   &GUID_1ffd2211_d3ed_426d_9206_7231b0444d3f,
                   a4);
            (*(void (__fastcall **)(CInstalledApp *))(*(_QWORD *)v14 + 16LL))(v14);
          }
        }
      }
    }
  }
  CTSmartObj<HKEY__ *,CAutoHandle_Policy<HKEY__ *>>::Release(&hkey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002cce8  mov     [rsp-8+arg_10], rbx
0x18002cced  push    rbp
0x18002ccee  push    rsi
0x18002ccef  push    rdi
0x18002ccf0  push    r12
0x18002ccf2  push    r13
0x18002ccf4  push    r14
0x18002ccf6  push    r15
0x18002ccf8  lea     rbp, [rsp-180h]
0x18002cd00  sub     rsp, 280h
0x18002cd07  mov     rax, cs:__security_cookie
0x18002cd0e  xor     rax, rsp
0x18002cd11  mov     [rbp+1B0h+var_40], rax
0x18002cd18  xor     edi, edi
0x18002cd1a  mov     r13, r9
0x18002cd1d  mov     [r9], rdi
0x18002cd20  mov     r15, rdx
0x18002cd23  lea     r9, [rsp+2B0h+hkey]; HKEY *
0x18002cd28  mov     [rsp+2B0h+hkey], rdi
0x18002cd2d  mov     r12d, ecx
0x18002cd30  call    ?s_OpenUninstallRegKey@CInstalledApp@@CAJKPEBGKPEAPEAUHKEY__@@@Z; CInstalledApp::s_OpenUninstallRegKey(ulong,ushort const *,ulong,HKEY__ * *)
0x18002cd35  mov     r14d, eax
0x18002cd38  test    eax, eax
0x18002cd3a  js      loc_18002CEFA
0x18002cd40  mov     rbx, [rsp+2B0h+hkey]
0x18002cd45  lea     rax, [rsp+2B0h+var_27C]
0x18002cd4a  mov     [rsp+2B0h+pcbData], rax; pcbData
0x18002cd4f  lea     r9, [rsp+2B0h+pdwType]; pdwType
0x18002cd54  lea     rax, [rsp+2B0h+var_280]
0x18002cd59  mov     [rsp+2B0h+var_280], edi
0x18002cd5d  xor     r8d, r8d; pdwReserved
0x18002cd60  mov     [rsp+2B0h+pvData], rax; pvData
0x18002cd65  lea     rdx, aWindowsinstall; "WindowsInstaller"
0x18002cd6c  mov     [rsp+2B0h+var_27C], 4
0x18002cd74  mov     rcx, rbx; hkey
0x18002cd77  mov     [rsp+2B0h+pdwType], edi
0x18002cd7b  call    cs:__imp_SHQueryValueExW
0x18002cd81  test    eax, eax
0x18002cd83  jle     short loc_18002CD8F
0x18002cd85  movzx   eax, ax
0x18002cd88  or      eax, 80070000h
0x18002cd8d  test    eax, eax
0x18002cd8f  js      loc_18002CE42
0x18002cd95  cmp     [rsp+2B0h+var_280], 1
0x18002cd9a  jnz     loc_18002CE42
0x18002cda0  lea     r9, [rsp+2B0h+pcchValueBuf]; pcchValueBuf
0x18002cda5  mov     [rsp+2B0h+pcchValueBuf], 104h
0x18002cdad  lea     r8, [rsp+2B0h+ValueBuf]; lpValueBuf
0x18002cdb2  mov     rcx, r15; szProduct
0x18002cdb5  lea     rdx, szAttribute; "ProductName"
0x18002cdbc  mov     r14d, 80070057h
0x18002cdc2  call    cs:__imp_MsiGetProductInfoW
0x18002cdc8  cmp     [rsp+2B0h+ValueBuf], di
0x18002cdcd  jz      loc_18002CEFA
0x18002cdd3  mov     ecx, 1B00h; this
0x18002cdd8  mov     r14d, 8007000Eh
0x18002cdde  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18002cde3  test    rax, rax
0x18002cde6  jz      loc_18002CEFA
0x18002cdec  mov     dword ptr [rsp+2B0h+pcbData], edi; enum tagMSIINSTALLCONTEXT
0x18002cdf0  lea     r9, [rsp+2B0h+ValueBuf]; unsigned __int16 *
0x18002cdf5  mov     r8, r15; szProduct
0x18002cdf8  mov     dword ptr [rsp+2B0h+pvData], r12d; unsigned int
0x18002cdfd  xor     edx, edx; unsigned __int16 *
0x18002cdff  mov     rcx, rax; this
0x18002ce02  call    ??0CInstalledApp@@AEAA@PEBG00KW4tagMSIINSTALLCONTEXT@@@Z; CInstalledApp::CInstalledApp(ushort const *,ushort const *,ushort const *,ulong,tagMSIINSTALLCONTEXT)
0x18002ce07  mov     rbx, rax
0x18002ce0a  test    rax, rax
0x18002ce0d  jz      loc_18002CEFA
0x18002ce13  mov     rcx, [rax]
0x18002ce16  lea     rdx, _GUID_1ffd2211_d3ed_426d_9206_7231b0444d3f
0x18002ce1d  mov     r8, r13
0x18002ce20  mov     rax, [rcx]
0x18002ce23  mov     rcx, rbx
0x18002ce26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce2b  mov     rcx, [rbx]
0x18002ce2e  mov     r14d, eax
0x18002ce31  mov     rax, [rcx+10h]
0x18002ce35  mov     rcx, rbx
0x18002ce38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce3d  jmp     loc_18002CEFA
0x18002ce42  lea     rdx, aDisplayname; "DisplayName"
0x18002ce49  mov     rcx, rbx; hkey
0x18002ce4c  mov     r14d, 80070057h
0x18002ce52  call    ?GetLocalizedStringFromRegistry@@YAPEAGPEAUHKEY__@@PEBG@Z; GetLocalizedStringFromRegistry(HKEY__ *,ushort const *)
0x18002ce57  mov     [rsp+2B0h+var_260], rax
0x18002ce5c  mov     rsi, rax
0x18002ce5f  test    rax, rax
0x18002ce62  jz      loc_18002CEF0
0x18002ce68  lea     rdx, aUninstallstrin; "UninstallString"
0x18002ce6f  mov     rcx, rbx; hkey
0x18002ce72  call    ?GetLocalizedStringFromRegistry@@YAPEAGPEAUHKEY__@@PEBG@Z; GetLocalizedStringFromRegistry(HKEY__ *,ushort const *)
0x18002ce77  mov     qword ptr [rsp+2B0h+pcchValueBuf], rax
0x18002ce7c  mov     rdi, rax
0x18002ce7f  test    rax, rax
0x18002ce82  jz      short loc_18002CEE6
0x18002ce84  mov     ecx, 1B00h; this
0x18002ce89  mov     r14d, 8007000Eh
0x18002ce8f  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18002ce94  test    rax, rax
0x18002ce97  jz      short loc_18002CEE6
0x18002ce99  mov     dword ptr [rsp+2B0h+pcbData], r12d; DWORD
0x18002ce9e  mov     r9, rsi; unsigned __int16 *
0x18002cea1  mov     r8, r15; unsigned __int16 *
0x18002cea4  mov     [rsp+2B0h+pvData], rdi; unsigned __int16 *
0x18002cea9  mov     rdx, rbx; HKEY
0x18002ceac  mov     rcx, rax; this
0x18002ceaf  call    ??0CInstalledApp@@AEAA@PEAUHKEY__@@PEBG11K@Z; CInstalledApp::CInstalledApp(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x18002ceb4  mov     rbx, rax
0x18002ceb7  test    rax, rax
0x18002ceba  jz      short loc_18002CEE6
0x18002cebc  mov     rcx, [rax]
0x18002cebf  lea     rdx, _GUID_1ffd2211_d3ed_426d_9206_7231b0444d3f
0x18002cec6  mov     r8, r13
0x18002cec9  mov     rax, [rcx]
0x18002cecc  mov     rcx, rbx
0x18002cecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ced4  mov     rcx, [rbx]
0x18002ced7  mov     r14d, eax
0x18002ceda  mov     rax, [rcx+10h]
0x18002cede  mov     rcx, rbx
0x18002cee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cee6  lea     rcx, [rsp+2B0h+pcchValueBuf]
0x18002ceeb  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18002cef0  lea     rcx, [rsp+2B0h+var_260]
0x18002cef5  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18002cefa  lea     rcx, [rsp+2B0h+hkey]
0x18002ceff  call    ?Release@?$CTSmartObj@PEAUHKEY__@@V?$CAutoHandle_Policy@PEAUHKEY__@@@@@@QEAAXXZ; CTSmartObj<HKEY__ *,CAutoHandle_Policy<HKEY__ *>>::Release(void)
0x18002cf04  mov     eax, r14d
0x18002cf07  mov     rcx, [rbp+1B0h+var_40]
0x18002cf0e  xor     rcx, rsp; StackCookie
0x18002cf11  call    __security_check_cookie
0x18002cf16  mov     rbx, [rsp+2B0h+arg_10]
0x18002cf1e  add     rsp, 280h
0x18002cf25  pop     r15
0x18002cf27  pop     r14
0x18002cf29  pop     r13
0x18002cf2b  pop     r12
0x18002cf2d  pop     rdi
0x18002cf2e  pop     rsi
0x18002cf2f  pop     rbp
0x18002cf30  retn
```
