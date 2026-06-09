# CInstalledApp::s_CreateInstance(ushort const *,ushort const *,tagMSIINSTALLCONTEXT,_GUID const &,void * *)

- ea: `0x18002cf38`
- end: `0x18002d13d`
- name: `?s_CreateInstance@CInstalledApp@@SAJPEBG0W4tagMSIINSTALLCONTEXT@@AEBU_GUID@@PEAPEAX@Z`
- size: `517`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, LPCWSTR szProduct@<rdx>, enum tagMSIINSTALLCONTEXT@<r8d>, const struct _GUID *@<r9>, void **)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18001a3a4`
- `0x18002d610`
- `0x18002d6a8`
- `0x18002d784`

## callees

- `0x18000b2dc`
- `0x18000dd44`
- `0x18002a058`
- `0x18002cf38`
- `0x18002d28c`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `SHCORE!SHQueryValueExW` at `0x18002d055`
- `SHCORE!SHQueryValueExW` at `0x18002d055`
- `msi!__imp_MsiGetProductInfoW` at `0x18002d09e`
- `msi!__imp_MsiGetProductInfoW` at `0x18002d09e`

## string_xrefs

- `0x18002d041`: `WindowsInstaller`

## pseudocode

```c
__int64 __fastcall CInstalledApp::s_CreateInstance(
        const unsigned __int16 *a1,
        LPCWSTR szProduct,
        enum tagMSIINSTALLCONTEXT a3,
        const struct _GUID *a4,
        void **a5)
{
  signed int v8; // ebx
  CInstalledApp *v9; // rax
  CInstalledApp *v10; // rax
  CInstalledApp *v11; // rdi
  LSTATUS v12; // eax
  unsigned __int64 v13; // rdx
  CInstalledApp *v14; // rax
  CInstalledApp *v15; // rax
  CInstalledApp *v16; // rdi
  int pvData; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v19; // [rsp+34h] [rbp-CCh] BYREF
  DWORD pcbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pdwType; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD pcchValueBuf; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR ValueBuf[264]; // [rsp+50h] [rbp-B0h] BYREF

  *a5 = 0;
  if ( a1 && *a1 )
  {
    v8 = -2147024882;
    v9 = (CInstalledApp *)DirectUI::HAllocAndZero((DirectUI *)0x1B00, (unsigned __int64)szProduct);
    if ( v9 )
    {
      v10 = CInstalledApp::CInstalledApp(v9, a1, szProduct, &WindowName, 0, a3);
      v11 = v10;
      if ( v10 )
      {
        v8 = (**(__int64 (__fastcall ***)(CInstalledApp *, GUID *, void **))v10)(
               v10,
               &GUID_1ffd2211_d3ed_426d_9206_7231b0444d3f,
               a5);
        (*(void (__fastcall **)(CInstalledApp *))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
  }
  else
  {
    v19 = 0;
    hkey = 0;
    v8 = CInstalledApp::s_OpenUninstallRegKey(szProduct, (unsigned int)szProduct, &hkey, &v19);
    if ( v8 >= 0 )
    {
      pvData = 0;
      pcbData = 4;
      pdwType = 0;
      v12 = SHQueryValueExW(hkey, L"WindowsInstaller", 0, &pdwType, &pvData, &pcbData);
      v8 = v12;
      if ( v12 > 0 )
        v8 = (unsigned __int16)v12 | 0x80070000;
      if ( v8 >= 0 )
      {
        v8 = -2147024809;
        if ( pvData == 1 )
        {
          pcchValueBuf = 260;
          MsiGetProductInfoW(szProduct, L"ProductName", ValueBuf, &pcchValueBuf);
          if ( ValueBuf[0] )
          {
            v8 = -2147024882;
            v14 = (CInstalledApp *)DirectUI::HAllocAndZero((DirectUI *)0x1B00, v13);
            if ( v14 )
            {
              v15 = CInstalledApp::CInstalledApp(v14, 0, szProduct, ValueBuf, v19, a3);
              v16 = v15;
              if ( v15 )
              {
                v8 = (**(__int64 (__fastcall ***)(CInstalledApp *, GUID *, void **))v15)(
                       v15,
                       &GUID_1ffd2211_d3ed_426d_9206_7231b0444d3f,
                       a5);
                (*(void (__fastcall **)(CInstalledApp *))(*(_QWORD *)v16 + 16LL))(v16);
              }
            }
          }
        }
      }
    }
    CTSmartObj<HKEY__ *,CAutoHandle_Policy<HKEY__ *>>::Release(&hkey);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002cf38  push    rbp
0x18002cf3a  push    rbx
0x18002cf3b  push    rsi
0x18002cf3c  push    rdi
0x18002cf3d  push    r12
0x18002cf3f  push    r14
0x18002cf41  push    r15
0x18002cf43  lea     rbp, [rsp-170h]
0x18002cf4b  sub     rsp, 270h
0x18002cf52  mov     rax, cs:__security_cookie
0x18002cf59  xor     rax, rsp
0x18002cf5c  mov     [rbp+1A0h+var_40], rax
0x18002cf63  mov     r15, [rbp+1A0h+arg_20]
0x18002cf6a  xor     r12d, r12d
0x18002cf6d  mov     r14d, r8d
0x18002cf70  mov     rdi, rdx
0x18002cf73  mov     rsi, rcx
0x18002cf76  mov     [r15], r12
0x18002cf79  test    rcx, rcx
0x18002cf7c  jz      short loc_18002CFF5
0x18002cf7e  cmp     [rcx], r12w
0x18002cf82  jz      short loc_18002CFF5
0x18002cf84  mov     ecx, 1B00h; this
0x18002cf89  mov     ebx, 8007000Eh
0x18002cf8e  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18002cf93  test    rax, rax
0x18002cf96  jz      loc_18002D11A
0x18002cf9c  mov     dword ptr [rsp+2A0h+pcbData], r14d; enum tagMSIINSTALLCONTEXT
0x18002cfa1  lea     r9, WindowName; unsigned __int16 *
0x18002cfa8  mov     r8, rdi; szProduct
0x18002cfab  mov     dword ptr [rsp+2A0h+pvData], r12d; unsigned int
0x18002cfb0  mov     rdx, rsi; unsigned __int16 *
0x18002cfb3  mov     rcx, rax; this
0x18002cfb6  call    ??0CInstalledApp@@AEAA@PEBG00KW4tagMSIINSTALLCONTEXT@@@Z; CInstalledApp::CInstalledApp(ushort const *,ushort const *,ushort const *,ulong,tagMSIINSTALLCONTEXT)
0x18002cfbb  mov     rdi, rax
0x18002cfbe  test    rax, rax
0x18002cfc1  jz      loc_18002D11A
0x18002cfc7  mov     rax, [rax]
0x18002cfca  lea     rdx, _GUID_1ffd2211_d3ed_426d_9206_7231b0444d3f
0x18002cfd1  mov     r8, r15
0x18002cfd4  mov     rcx, rdi
0x18002cfd7  mov     rax, [rax]
0x18002cfda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfdf  mov     rcx, [rdi]
0x18002cfe2  mov     ebx, eax
0x18002cfe4  mov     rax, [rcx+10h]
0x18002cfe8  mov     rcx, rdi
0x18002cfeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cff0  jmp     loc_18002D11A
0x18002cff5  lea     r9, [rsp+2A0h+var_26C]; unsigned int *
0x18002cffa  mov     [rsp+2A0h+var_26C], r12d
0x18002cfff  lea     r8, [rsp+2A0h+hkey]; HKEY *
0x18002d004  mov     [rsp+2A0h+hkey], r12
0x18002d009  mov     rcx, rdi; unsigned __int16 *
0x18002d00c  call    ?s_OpenUninstallRegKey@CInstalledApp@@CAJPEBGKPEAPEAUHKEY__@@PEAK@Z; CInstalledApp::s_OpenUninstallRegKey(ushort const *,ulong,HKEY__ * *,ulong *)
0x18002d011  mov     ebx, eax
0x18002d013  test    eax, eax
0x18002d015  js      loc_18002D110
0x18002d01b  mov     rcx, [rsp+2A0h+hkey]; hkey
0x18002d020  lea     rax, [rsp+2A0h+var_268]
0x18002d025  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18002d02a  lea     r9, [rsp+2A0h+pdwType]; pdwType
0x18002d02f  lea     rax, [rsp+2A0h+var_270]
0x18002d034  mov     [rsp+2A0h+var_270], r12d
0x18002d039  xor     r8d, r8d; pdwReserved
0x18002d03c  mov     [rsp+2A0h+pvData], rax; pvData
0x18002d041  lea     rdx, aWindowsinstall; "WindowsInstaller"
0x18002d048  mov     [rsp+2A0h+var_268], 4
0x18002d050  mov     [rsp+2A0h+pdwType], r12d
0x18002d055  call    cs:__imp_SHQueryValueExW
0x18002d05b  mov     ebx, eax
0x18002d05d  test    eax, eax
0x18002d05f  jle     short loc_18002D06A
0x18002d061  movzx   ebx, ax
0x18002d064  or      ebx, 80070000h
0x18002d06a  test    ebx, ebx
0x18002d06c  js      loc_18002D110
0x18002d072  cmp     [rsp+2A0h+var_270], 1
0x18002d077  mov     ebx, 80070057h
0x18002d07c  jnz     loc_18002D110
0x18002d082  lea     r9, [rsp+2A0h+pcchValueBuf]; pcchValueBuf
0x18002d087  mov     [rsp+2A0h+pcchValueBuf], 104h
0x18002d08f  lea     r8, [rsp+2A0h+ValueBuf]; lpValueBuf
0x18002d094  mov     rcx, rdi; szProduct
0x18002d097  lea     rdx, szAttribute; "ProductName"
0x18002d09e  call    cs:__imp_MsiGetProductInfoW
0x18002d0a4  cmp     [rsp+2A0h+ValueBuf], r12w
0x18002d0aa  jz      short loc_18002D110
0x18002d0ac  mov     ecx, 1B00h; this
0x18002d0b1  mov     ebx, 8007000Eh
0x18002d0b6  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18002d0bb  test    rax, rax
0x18002d0be  jz      short loc_18002D110
0x18002d0c0  mov     ecx, [rsp+2A0h+var_26C]
0x18002d0c4  lea     r9, [rsp+2A0h+ValueBuf]; unsigned __int16 *
0x18002d0c9  mov     dword ptr [rsp+2A0h+pcbData], r14d; enum tagMSIINSTALLCONTEXT
0x18002d0ce  mov     r8, rdi; szProduct
0x18002d0d1  mov     dword ptr [rsp+2A0h+pvData], ecx; unsigned int
0x18002d0d5  xor     edx, edx; unsigned __int16 *
0x18002d0d7  mov     rcx, rax; this
0x18002d0da  call    ??0CInstalledApp@@AEAA@PEBG00KW4tagMSIINSTALLCONTEXT@@@Z; CInstalledApp::CInstalledApp(ushort const *,ushort const *,ushort const *,ulong,tagMSIINSTALLCONTEXT)
0x18002d0df  mov     rdi, rax
0x18002d0e2  test    rax, rax
0x18002d0e5  jz      short loc_18002D110
0x18002d0e7  mov     rcx, [rax]
0x18002d0ea  lea     rdx, _GUID_1ffd2211_d3ed_426d_9206_7231b0444d3f
0x18002d0f1  mov     r8, r15
0x18002d0f4  mov     rax, [rcx]
0x18002d0f7  mov     rcx, rdi
0x18002d0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0ff  mov     rcx, [rdi]
0x18002d102  mov     ebx, eax
0x18002d104  mov     rax, [rcx+10h]
0x18002d108  mov     rcx, rdi
0x18002d10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d110  lea     rcx, [rsp+2A0h+hkey]
0x18002d115  call    ?Release@?$CTSmartObj@PEAUHKEY__@@V?$CAutoHandle_Policy@PEAUHKEY__@@@@@@QEAAXXZ; CTSmartObj<HKEY__ *,CAutoHandle_Policy<HKEY__ *>>::Release(void)
0x18002d11a  mov     eax, ebx
0x18002d11c  mov     rcx, [rbp+1A0h+var_40]
0x18002d123  xor     rcx, rsp; StackCookie
0x18002d126  call    __security_check_cookie
0x18002d12b  add     rsp, 270h
0x18002d132  pop     r15
0x18002d134  pop     r14
0x18002d136  pop     r12
0x18002d138  pop     rdi
0x18002d139  pop     rsi
0x18002d13a  pop     rbx
0x18002d13b  pop     rbp
0x18002d13c  retn
```
