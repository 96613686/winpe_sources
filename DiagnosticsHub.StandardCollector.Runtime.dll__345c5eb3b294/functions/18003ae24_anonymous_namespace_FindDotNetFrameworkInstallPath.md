# _anonymous_namespace_::FindDotNetFrameworkInstallPath

- ea: `0x18003ae24`
- end: `0x18003b264`
- name: `_anonymous_namespace_::FindDotNetFrameworkInstallPath`
- size: `1088`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003b61c`

## callees

- `0x1800020bc`
- `0x180002604`
- `0x18000288c`
- `0x180031490`
- `0x18003ae24`
- `0x18003cac8`
- `0x18003d864`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18003aecd`
- `KERNEL32!LoadLibraryExW` at `0x18003aecd`
- `KERNEL32!GetLastError` at `0x18003aef0`
- `KERNEL32!GetLastError` at `0x18003aefc`
- `KERNEL32!GetLastError` at `0x18003aef0`
- `KERNEL32!GetLastError` at `0x18003aefc`
- `KERNEL32!GetProcAddress` at `0x18003aee2`
- `KERNEL32!GetProcAddress` at `0x18003aee2`
- `OLEAUT32!__imp_SysAllocString` at `0x18003b06a`
- `OLEAUT32!__imp_SysAllocString` at `0x18003b06a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b0b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b0bb`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b0b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b0bb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18003b0a5`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18003b0a5`
- `api-ms-win-crt-string-l1-1-0!wcstok_s` at `0x18003b094`
- `api-ms-win-crt-string-l1-1-0!wcstok_s` at `0x18003b094`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003ae66`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003ae7d`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003b0f5`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003ae66`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003ae7d`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003b0f5`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x18003b09d`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x18003b09d`

## string_xrefs

- `0x18003aec6`: `mscoree.dll`
- `0x18003aed8`: `CLRCreateInstance`
- `0x18003b1dc`: `Unexpected Win32 error loading mscoree function CLRCreateInstance. Error: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall anonymous_namespace_::FindDotNetFrameworkInstallPath(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // eax
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v7; // rbx
  FARPROC ProcAddress; // r14
  DWORD LastError; // edi
  HMODULE Library; // rax
  int v11; // esi
  signed int v12; // edi
  __int64 v13; // r9
  __int64 v14; // rcx
  int v15; // eax
  wchar_t *v16; // rax
  OLECHAR *v17; // rbx
  wchar_t *v18; // rax
  int v19; // edi
  unsigned int v20; // eax
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *Context; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  int v29; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  __int16 v31; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR psz[31]; // [rsp+72h] [rbp-8Eh] BYREF
  wchar_t String[264]; // [rsp+B0h] [rbp-50h] BYREF

  v4 = wcslen(&word_180055D48);
  ATL::CSimpleStringT<unsigned short,0>::SetString(a1, &word_180055D48, v4);
  v5 = wcslen(&word_180055D48);
  ATL::CSimpleStringT<unsigned short,0>::SetString(a2, &word_180055D48, v5);
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v7 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
  v22 = v7;
  ProcAddress = 0;
  LastError = 0;
  Library = LoadLibraryExW(L"mscoree.dll", 0, 0x800u);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "CLRCreateInstance");
    if ( !ProcAddress )
      LastError = GetLastError();
    v11 = LastError;
  }
  else
  {
    LastError = GetLastError();
    v11 = LastError;
  }
  if ( LastError || !ProcAddress )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
      L"Unexpected Win32 error loading mscoree function CLRCreateInstance. Error: %d",
      (unsigned int)v11);
    v12 = (unsigned __int16)v11 | 0x80070000;
    if ( v11 <= 0 )
      v12 = v11;
  }
  else
  {
    v30 = 0;
    v12 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(&CLSID_CLRMetaHost, &IID_ICLRMetaHost, &v30);
    if ( v12 >= 0 )
    {
      v27 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 40LL))(v30, &v27);
      if ( v12 >= 0 )
      {
        v26 = 0;
        v25 = 0;
        if ( (*(int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v27 + 24LL))(v27, 1, &v26, &v25) >= 0 )
        {
          do
          {
            if ( v25 != 1 )
              break;
            v13 = v26;
            v14 = 0;
            v24 = 0;
            if ( v26 )
            {
              v15 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v26)(
                      v26,
                      &GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891,
                      &v24);
              v13 = v26;
              if ( v15 >= 0 )
              {
                v14 = v24;
              }
              else
              {
                v14 = 0;
                v24 = 0;
              }
            }
            if ( v13 )
            {
              v26 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
              v14 = v24;
            }
            if ( v14 )
            {
              v28 = 32;
              if ( (*(int (__fastcall **)(__int64, __int16 *, int *))(*(_QWORD *)v14 + 24LL))(v14, &v31, &v28) >= 0
                && ((v31 - 86) & 0xFFDF) == 0 )
              {
                v16 = SysAllocString(psz);
                v17 = v16;
                if ( !v16 )
                  ATL::AtlThrowImpl(-2147024882);
                Context = 0;
                v18 = wcstok_s(v16, L".", &Context);
                v19 = _wtoi(v18);
                if ( *_errno() == 34 )
                {
                  SysFreeString(v17);
                }
                else
                {
                  SysFreeString(v17);
                  if ( v19 >= 4 )
                  {
                    v29 = 261;
                    if ( (*(int (__fastcall **)(__int64, wchar_t *, int *))(*(_QWORD *)v24 + 32LL))(v24, String, &v29) >= 0 )
                    {
                      v20 = wcslen(String);
                      ATL::CSimpleStringT<unsigned short,0>::SetString(&v22, String, v20);
                    }
                  }
                }
              }
              if ( v24 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            }
          }
          while ( (*(int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v27 + 24LL))(
                    v27,
                    1,
                    &v26,
                    &v25) >= 0 );
          v7 = v22;
        }
        if ( *(_DWORD *)(v7 - 16) )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
            a1,
            &v22);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(a1);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
            a2,
            &v22);
          v12 = 0;
        }
        else
        {
          v12 = -2147023728;
        }
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 - 24 + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 - 24) + 8LL))(*(_QWORD *)(v7 - 24));
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003ae24  mov     [rsp-8+arg_10], rbx
0x18003ae29  mov     [rsp-8+arg_18], rsi
0x18003ae2e  push    rbp
0x18003ae2f  push    rdi
0x18003ae30  push    r12
0x18003ae32  push    r14
0x18003ae34  push    r15
0x18003ae36  lea     rbp, [rsp-1D0h]
0x18003ae3e  sub     rsp, 2D0h
0x18003ae45  mov     rax, cs:__security_cookie
0x18003ae4c  xor     rax, rsp
0x18003ae4f  mov     [rbp+1F0h+var_30], rax
0x18003ae56  mov     r12, rdx
0x18003ae59  mov     r15, rcx
0x18003ae5c  lea     rbx, word_180055D48
0x18003ae63  mov     rcx, rbx; String
0x18003ae66  call    cs:__imp_wcslen
0x18003ae6c  mov     r8d, eax
0x18003ae6f  mov     rdx, rbx
0x18003ae72  mov     rcx, r15
0x18003ae75  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003ae7a  mov     rcx, rbx; String
0x18003ae7d  call    cs:__imp_wcslen
0x18003ae83  mov     r8d, eax
0x18003ae86  mov     rdx, rbx
0x18003ae89  mov     rcx, r12
0x18003ae8c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003ae91  nop
0x18003ae92  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18003ae97  mov     rcx, rax
0x18003ae9a  test    rax, rax
0x18003ae9d  jz      loc_18003B259
0x18003aea3  mov     rax, [rax]
0x18003aea6  mov     rax, [rax+18h]
0x18003aeaa  call    cs:__guard_dispatch_icall_fptr
0x18003aeb0  lea     rbx, [rax+18h]
0x18003aeb4  mov     [rsp+2F0h+var_2C0], rbx
0x18003aeb9  xor     r14d, r14d
0x18003aebc  xor     edi, edi
0x18003aebe  xor     edx, edx; hFile
0x18003aec0  mov     r8d, 800h; dwFlags
0x18003aec6  lea     rcx, aMscoreeDll; "mscoree.dll"
0x18003aecd  call    cs:__imp_LoadLibraryExW
0x18003aed3  test    rax, rax
0x18003aed6  jz      short loc_18003AEFC
0x18003aed8  lea     rdx, aClrcreateinsta; "CLRCreateInstance"
0x18003aedf  mov     rcx, rax; hModule
0x18003aee2  call    cs:__imp_GetProcAddress
0x18003aee8  mov     r14, rax
0x18003aeeb  test    rax, rax
0x18003aeee  jnz     short loc_18003AEF8
0x18003aef0  call    cs:__imp_GetLastError
0x18003aef6  mov     edi, eax
0x18003aef8  mov     esi, edi
0x18003aefa  jmp     short loc_18003AF06
0x18003aefc  call    cs:__imp_GetLastError
0x18003af02  mov     edi, eax
0x18003af04  mov     esi, eax
0x18003af06  test    edi, edi
0x18003af08  jnz     loc_18003B1CB
0x18003af0e  test    r14, r14
0x18003af11  jz      loc_18003B1CB
0x18003af17  mov     [rsp+2F0h+var_288], 0
0x18003af20  lea     r8, [rsp+2F0h+var_288]
0x18003af25  lea     rdx, IID_ICLRMetaHost
0x18003af2c  lea     rcx, CLSID_CLRMetaHost
0x18003af33  mov     rax, r14
0x18003af36  call    cs:__guard_dispatch_icall_fptr
0x18003af3c  mov     edi, eax
0x18003af3e  test    eax, eax
0x18003af40  js      loc_18003B1B1
0x18003af46  mov     [rsp+2F0h+var_298], 0
0x18003af4f  mov     rcx, [rsp+2F0h+var_288]
0x18003af54  mov     rax, [rcx]
0x18003af57  lea     rdx, [rsp+2F0h+var_298]
0x18003af5c  mov     rax, [rax+28h]
0x18003af60  call    cs:__guard_dispatch_icall_fptr
0x18003af66  mov     edi, eax
0x18003af68  test    eax, eax
0x18003af6a  js      loc_18003B199
0x18003af70  mov     [rsp+2F0h+var_2A0], 0
0x18003af79  mov     [rsp+2F0h+var_2A8], 0
0x18003af81  mov     rcx, [rsp+2F0h+var_298]
0x18003af86  mov     rax, [rcx]
0x18003af89  lea     r9, [rsp+2F0h+var_2A8]
0x18003af8e  lea     r8, [rsp+2F0h+var_2A0]
0x18003af93  mov     esi, 1
0x18003af98  mov     edx, esi
0x18003af9a  mov     rax, [rax+18h]
0x18003af9e  call    cs:__guard_dispatch_icall_fptr
0x18003afa4  test    eax, eax
0x18003afa6  js      loc_18003B150
0x18003afac  cmp     [rsp+2F0h+var_2A8], esi
0x18003afb0  jnz     loc_18003B14B
0x18003afb6  mov     r9, [rsp+2F0h+var_2A0]
0x18003afbb  xor     ecx, ecx
0x18003afbd  mov     [rsp+2F0h+var_2B0], rcx
0x18003afc2  test    r9, r9
0x18003afc5  jz      short loc_18003AFF9
0x18003afc7  mov     rax, [r9]
0x18003afca  lea     r8, [rsp+2F0h+var_2B0]
0x18003afcf  lea     rdx, _GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891
0x18003afd6  mov     rcx, r9
0x18003afd9  mov     rax, [rax]
0x18003afdc  call    cs:__guard_dispatch_icall_fptr
0x18003afe2  mov     r9, [rsp+2F0h+var_2A0]
0x18003afe7  test    eax, eax
0x18003afe9  jns     short loc_18003AFF4
0x18003afeb  xor     ecx, ecx
0x18003afed  mov     [rsp+2F0h+var_2B0], rcx
0x18003aff2  jmp     short loc_18003AFF9
0x18003aff4  mov     rcx, [rsp+2F0h+var_2B0]
0x18003aff9  test    r9, r9
0x18003affc  jz      short loc_18003B01C
0x18003affe  mov     [rsp+2F0h+var_2A0], 0
0x18003b007  mov     rax, [r9]
0x18003b00a  mov     rcx, r9
0x18003b00d  mov     rax, [rax+10h]
0x18003b011  call    cs:__guard_dispatch_icall_fptr
0x18003b017  mov     rcx, [rsp+2F0h+var_2B0]
0x18003b01c  test    rcx, rcx
0x18003b01f  jnz     short loc_18003B026
0x18003b021  jmp     loc_18003B125
0x18003b026  mov     [rsp+2F0h+var_290], 20h ; ' '
0x18003b02e  mov     rax, [rcx]
0x18003b031  lea     r8, [rsp+2F0h+var_290]
0x18003b036  lea     rdx, [rsp+2F0h+var_280]
0x18003b03b  mov     rax, [rax+18h]
0x18003b03f  call    cs:__guard_dispatch_icall_fptr
0x18003b045  test    eax, eax
0x18003b047  jns     short loc_18003B04E
0x18003b049  jmp     loc_18003B10D
0x18003b04e  movzx   eax, [rsp+2F0h+var_280]
0x18003b053  sub     ax, 56h ; 'V'
0x18003b057  mov     ecx, 0FFDFh
0x18003b05c  test    cx, ax
0x18003b05f  jnz     loc_18003B10D
0x18003b065  lea     rcx, [rsp+2F0h+psz]; psz
0x18003b06a  call    cs:__imp_SysAllocString
0x18003b070  mov     rbx, rax
0x18003b073  test    rax, rax
0x18003b076  jz      loc_18003B24E
0x18003b07c  mov     [rsp+2F0h+Context], 0
0x18003b085  lea     r8, [rsp+2F0h+Context]; Context
0x18003b08a  lea     rdx, Delimiter; "."
0x18003b091  mov     rcx, rax; String
0x18003b094  call    cs:__imp_wcstok_s
0x18003b09a  mov     rcx, rax; String
0x18003b09d  call    cs:__imp__wtoi
0x18003b0a3  mov     edi, eax
0x18003b0a5  call    cs:__imp__errno
0x18003b0ab  mov     rcx, rbx; bstrString
0x18003b0ae  cmp     dword ptr [rax], 22h ; '"'
0x18003b0b1  jnz     short loc_18003B0BB
0x18003b0b3  call    cs:__imp_SysFreeString
0x18003b0b9  jmp     short loc_18003B10D
0x18003b0bb  call    cs:__imp_SysFreeString
0x18003b0c1  cmp     edi, 4
0x18003b0c4  jge     short loc_18003B0C8
0x18003b0c6  jmp     short loc_18003B10D
0x18003b0c8  mov     [rsp+2F0h+var_28C], 105h
0x18003b0d0  mov     rcx, [rsp+2F0h+var_2B0]
0x18003b0d5  mov     rax, [rcx]
0x18003b0d8  lea     r8, [rsp+2F0h+var_28C]
0x18003b0dd  lea     rdx, [rbp+1F0h+String]
0x18003b0e1  mov     rax, [rax+20h]
0x18003b0e5  call    cs:__guard_dispatch_icall_fptr
0x18003b0eb  test    eax, eax
0x18003b0ed  jns     short loc_18003B0F1
0x18003b0ef  jmp     short loc_18003B10D
0x18003b0f1  lea     rcx, [rbp+1F0h+String]; String
0x18003b0f5  call    cs:__imp_wcslen
0x18003b0fb  mov     r8d, eax
0x18003b0fe  lea     rdx, [rbp+1F0h+String]
0x18003b102  lea     rcx, [rsp+2F0h+var_2C0]
0x18003b107  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003b10c  nop
0x18003b10d  mov     rcx, [rsp+2F0h+var_2B0]
0x18003b112  test    rcx, rcx
0x18003b115  jz      short loc_18003B125
0x18003b117  mov     rax, [rcx]
0x18003b11a  mov     rax, [rax+10h]
0x18003b11e  call    cs:__guard_dispatch_icall_fptr
0x18003b124  nop
0x18003b125  mov     rcx, [rsp+2F0h+var_298]
0x18003b12a  mov     rax, [rcx]
0x18003b12d  lea     r9, [rsp+2F0h+var_2A8]
0x18003b132  lea     r8, [rsp+2F0h+var_2A0]
0x18003b137  mov     edx, esi
0x18003b139  mov     rax, [rax+18h]
0x18003b13d  call    cs:__guard_dispatch_icall_fptr
0x18003b143  test    eax, eax
0x18003b145  jns     loc_18003AFAC
0x18003b14b  mov     rbx, [rsp+2F0h+var_2C0]
0x18003b150  cmp     dword ptr [rbx-10h], 0
0x18003b154  jnz     short loc_18003B15D
0x18003b156  mov     edi, 80070490h
0x18003b15b  jmp     short loc_18003B181
0x18003b15d  lea     rdx, [rsp+2F0h+var_2C0]
0x18003b162  mov     rcx, r15
0x18003b165  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18003b16a  mov     rcx, r15
0x18003b16d  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x18003b172  lea     rdx, [rsp+2F0h+var_2C0]
0x18003b177  mov     rcx, r12
0x18003b17a  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18003b17f  xor     edi, edi
0x18003b181  mov     rcx, [rsp+2F0h+var_2A0]
0x18003b186  test    rcx, rcx
0x18003b189  jz      short loc_18003B199
0x18003b18b  mov     rax, [rcx]
0x18003b18e  mov     rax, [rax+10h]
0x18003b192  call    cs:__guard_dispatch_icall_fptr
0x18003b198  nop
0x18003b199  mov     rcx, [rsp+2F0h+var_298]
0x18003b19e  test    rcx, rcx
0x18003b1a1  jz      short loc_18003B1B1
0x18003b1a3  mov     rax, [rcx]
0x18003b1a6  mov     rax, [rax+10h]
0x18003b1aa  call    cs:__guard_dispatch_icall_fptr
0x18003b1b0  nop
0x18003b1b1  mov     rcx, [rsp+2F0h+var_288]
0x18003b1b6  test    rcx, rcx
0x18003b1b9  jz      short loc_18003B1C9
0x18003b1bb  mov     rax, [rcx]
0x18003b1be  mov     rax, [rax+10h]
0x18003b1c2  call    cs:__guard_dispatch_icall_fptr
0x18003b1c8  nop
0x18003b1c9  jmp     short loc_18003B1FD
0x18003b1cb  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003b1d2  add     rcx, 0A8h; this
0x18003b1d9  mov     r9d, esi
0x18003b1dc  lea     r8, aUnexpectedWin3; "Unexpected Win32 error loading mscoree "...
0x18003b1e3  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003b1ea  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003b1ef  movzx   edi, si
0x18003b1f2  or      edi, 80070000h
0x18003b1f8  test    esi, esi
0x18003b1fa  cmovle  edi, esi
0x18003b1fd  lea     rdx, [rbx-18h]
0x18003b201  or      ecx, 0FFFFFFFFh
0x18003b204  lock xadd [rdx+10h], ecx
0x18003b209  sub     ecx, 1
0x18003b20c  jg      short loc_18003B221
0x18003b20e  lfence
0x18003b211  mov     rcx, [rdx]
0x18003b214  mov     r8, [rcx]
0x18003b217  mov     rax, [r8+8]
0x18003b21b  call    cs:__guard_dispatch_icall_fptr
0x18003b221  mov     eax, edi
0x18003b223  mov     rcx, [rbp+1F0h+var_30]
0x18003b22a  xor     rcx, rsp; StackCookie
0x18003b22d  call    __security_check_cookie
0x18003b232  lea     r11, [rsp+2F0h+var_20]
0x18003b23a  mov     rbx, [r11+40h]
0x18003b23e  mov     rsi, [r11+48h]
0x18003b242  mov     rsp, r11
0x18003b245  pop     r15
0x18003b247  pop     r14
0x18003b249  pop     r12
0x18003b24b  pop     rdi
0x18003b24c  pop     rbp
0x18003b24d  retn
0x18003b24e  mov     ecx, 8007000Eh; int
0x18003b253  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003b259  mov     ecx, 80004005h; int
0x18003b25e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
