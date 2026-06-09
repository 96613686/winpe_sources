# GetCachedFulfillmentData(ushort const *,HSTRING__ * *)

- ea: `0x1800daa98`
- end: `0x1800dacc4`
- name: `?GetCachedFulfillmentData@@YAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `556`
- prototype: `__int64 __fastcall(LPCWSTR lpValue, HSTRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800818d4`

## callees

- `0x1800101f4`
- `0x180012794`
- `0x18001c414`
- `0x180043320`
- `0x1800d5cc4`
- `0x1800d5db4`
- `0x1800d5eb4`
- `0x1800daa98`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800daca8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800daca8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800daaf2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800dab6c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800daaf2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800dab6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dabb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dac04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dac80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dac95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dabb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dac04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dac80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dac95`

## string_xrefs

- `0x1800daabb`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State\CategoryCache`
- `0x1800dab2f`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State\CategoryCache`
- `0x1800dac56`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`
- `0x1800dac49`: `GetCachedFulfillmentData`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetCachedFulfillmentData(LPCWSTR lpValue, HSTRING *a2)
{
  const WCHAR *RegistryLocation; // rax
  LSTATUS ValueW; // eax
  void *v6; // rcx
  signed int NamedValue; // ebx
  const WCHAR *v8; // rax
  unsigned __int16 *v9; // rdi
  LSTATUS v10; // eax
  HSTRING v11; // rax
  struct Windows::Data::Json::IJsonObject *v13; // [rsp+50h] [rbp-10h] BYREF
  HSTRING string; // [rsp+58h] [rbp-8h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+38h] BYREF
  PVOID hMem; // [rsp+A0h] [rbp+40h] BYREF
  struct Windows::Data::Json::IJsonObject *v17; // [rsp+A8h] [rbp+48h] BYREF

  *a2 = 0;
  pcbData = 0;
  RegistryLocation = (const WCHAR *)_InitOnceAndGetRegistryLocation(
                                      &qword_1802CAE68,
                                      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State\\CategoryCache");
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, RegistryLocation, lpValue, 2u, 0, 0, &pcbData);
  NamedValue = ValueW;
  if ( ValueW > 0 )
    NamedValue = (unsigned __int16)ValueW | 0x80070000;
  if ( NamedValue >= 0 )
  {
    hMem = 0;
    NamedValue = CTLocalAllocPolicy::Alloc(v6, 0x40u, pcbData, &hMem);
    if ( NamedValue >= 0 )
    {
      v8 = (const WCHAR *)_InitOnceAndGetRegistryLocation(
                            &qword_1802CAE68,
                            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State\\CategoryCache");
      v9 = (unsigned __int16 *)hMem;
      v10 = RegGetValueW(HKEY_LOCAL_MACHINE, v8, lpValue, 2u, 0, hMem, &pcbData);
      NamedValue = v10;
      if ( v10 > 0 )
        NamedValue = (unsigned __int16)v10 | 0x80070000;
      if ( NamedValue >= 0 )
      {
        v13 = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v13);
        NamedValue = Json_Parse(v9, &v13);
        if ( NamedValue >= 0 )
        {
          hMem = 0;
          WindowsDeleteString(0);
          hMem = 0;
          NamedValue = Json_GetNamedValue(v13, L"FulfillmentData", (HSTRING *)&hMem);
          if ( NamedValue >= 0 )
          {
            v17 = 0;
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v17);
            NamedValue = Json_Parse((HSTRING)hMem, &v17);
            if ( NamedValue >= 0 )
            {
              string = 0;
              WindowsDeleteString(0);
              string = 0;
              if ( (int)Json_GetNamedValue(v17, L"Placeholder", &string) < 0 )
              {
                v11 = (HSTRING)hMem;
                hMem = 0;
                *a2 = v11;
                NamedValue = 0;
              }
              else
              {
                LogMessage(
                  2u,
                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
                  0x257u,
                  "GetCachedFulfillmentData",
                  -1,
                  L"Fulfillment data found for %s is placeholder data, returning ERROR_FILE_NOT_FOUND",
                  0,
                  0,
                  lpValue);
                NamedValue = -2147024894;
              }
              WindowsDeleteString(string);
            }
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v17);
          }
          WindowsDeleteString((HSTRING)hMem);
        }
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v13);
      }
      LocalFree(v9);
    }
  }
  return (unsigned int)NamedValue;
}

```

## disassembly

```asm
0x1800daa98  mov     [rsp-28h+arg_0], rbx
0x1800daa9d  push    rbp
0x1800daa9e  push    rsi
0x1800daa9f  push    rdi
0x1800daaa0  push    r14
0x1800daaa2  push    r15
0x1800daaa4  mov     rbp, rsp
0x1800daaa7  sub     rsp, 60h
0x1800daaab  mov     r14, rdx
0x1800daaae  mov     rsi, rcx
0x1800daab1  xor     r15d, r15d
0x1800daab4  mov     [rdx], r15
0x1800daab7  mov     [rbp+arg_8], r15d
0x1800daabb  lea     rdx, aSoftwareMicros_18; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800daac2  lea     rcx, qword_1802CAE68
0x1800daac9  call    ?_InitOnceAndGetRegistryLocation@@YAPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; _InitOnceAndGetRegistryLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x1800daace  lea     rcx, [rbp+arg_8]
0x1800daad2  mov     [rsp+60h+pcbData], rcx; pcbData
0x1800daad7  mov     [rsp+60h+pvData], r15; pvData
0x1800daadc  mov     [rsp+60h+pdwType], r15; pdwType
0x1800daae1  lea     r9d, [r15+2]; dwFlags
0x1800daae5  mov     r8, rsi; lpValue
0x1800daae8  mov     rdx, rax; lpSubKey
0x1800daaeb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800daaf2  call    cs:__imp_RegGetValueW
0x1800daaf8  mov     ebx, eax
0x1800daafa  test    eax, eax
0x1800daafc  jle     short loc_1800DAB07
0x1800daafe  movzx   ebx, ax
0x1800dab01  or      ebx, 80070000h
0x1800dab07  test    ebx, ebx
0x1800dab09  js      loc_1800DACAE
0x1800dab0f  mov     [rbp+hMem], r15
0x1800dab13  mov     r8d, [rbp+arg_8]; unsigned __int64
0x1800dab17  lea     r9, [rbp+hMem]; void **
0x1800dab1b  mov     edx, 40h ; '@'; unsigned int
0x1800dab20  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800dab25  mov     ebx, eax
0x1800dab27  test    eax, eax
0x1800dab29  js      loc_1800DACAE
0x1800dab2f  lea     rdx, aSoftwareMicros_18; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800dab36  lea     rcx, qword_1802CAE68
0x1800dab3d  call    ?_InitOnceAndGetRegistryLocation@@YAPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; _InitOnceAndGetRegistryLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x1800dab42  lea     rdx, [rbp+arg_8]
0x1800dab46  mov     [rsp+60h+pcbData], rdx; pcbData
0x1800dab4b  mov     rdi, [rbp+hMem]
0x1800dab4f  mov     [rsp+60h+pvData], rdi; pvData
0x1800dab54  mov     [rsp+60h+pdwType], r15; pdwType
0x1800dab59  mov     r9d, 2; dwFlags
0x1800dab5f  mov     r8, rsi; lpValue
0x1800dab62  mov     rdx, rax; lpSubKey
0x1800dab65  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800dab6c  call    cs:__imp_RegGetValueW
0x1800dab72  mov     ebx, eax
0x1800dab74  test    eax, eax
0x1800dab76  jle     short loc_1800DAB81
0x1800dab78  movzx   ebx, ax
0x1800dab7b  or      ebx, 80070000h
0x1800dab81  test    ebx, ebx
0x1800dab83  js      loc_1800DACA5
0x1800dab89  mov     [rbp+var_10], r15
0x1800dab8d  lea     rcx, [rbp+var_10]
0x1800dab91  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800dab96  lea     rdx, [rbp+var_10]; struct Windows::Data::Json::IJsonObject **
0x1800dab9a  mov     rcx, rdi; unsigned __int16 *
0x1800dab9d  call    ?Json_Parse@@YAJPEBGPEAPEAUIJsonObject@Json@Data@Windows@@@Z; Json_Parse(ushort const *,Windows::Data::Json::IJsonObject * *)
0x1800daba2  mov     ebx, eax
0x1800daba4  test    eax, eax
0x1800daba6  js      loc_1800DAC9C
0x1800dabac  mov     [rbp+hMem], r15
0x1800dabb0  xor     ecx, ecx; string
0x1800dabb2  call    cs:__imp_WindowsDeleteString
0x1800dabb8  mov     [rbp+hMem], r15
0x1800dabbc  lea     r8, [rbp+hMem]; HSTRING *
0x1800dabc0  lea     rdx, aFulfillmentdat; "FulfillmentData"
0x1800dabc7  mov     rcx, [rbp+var_10]; struct Windows::Data::Json::IJsonObject *
0x1800dabcb  call    ?Json_GetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAPEAUHSTRING__@@@Z; Json_GetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,HSTRING__ * *)
0x1800dabd0  mov     ebx, eax
0x1800dabd2  test    eax, eax
0x1800dabd4  js      loc_1800DAC91
0x1800dabda  mov     [rbp+arg_18], r15
0x1800dabde  lea     rcx, [rbp+arg_18]
0x1800dabe2  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800dabe7  lea     rdx, [rbp+arg_18]; struct Windows::Data::Json::IJsonObject **
0x1800dabeb  mov     rcx, [rbp+hMem]; HSTRING
0x1800dabef  call    ?Json_Parse@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@Windows@@@Z; Json_Parse(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x1800dabf4  mov     ebx, eax
0x1800dabf6  test    eax, eax
0x1800dabf8  js      loc_1800DAC87
0x1800dabfe  mov     [rbp+string], r15
0x1800dac02  xor     ecx, ecx; string
0x1800dac04  call    cs:__imp_WindowsDeleteString
0x1800dac0a  mov     [rbp+string], r15
0x1800dac0e  lea     r8, [rbp+string]; HSTRING *
0x1800dac12  lea     rdx, aPlaceholder; "Placeholder"
0x1800dac19  mov     rcx, [rbp+arg_18]; struct Windows::Data::Json::IJsonObject *
0x1800dac1d  call    ?Json_GetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAPEAUHSTRING__@@@Z; Json_GetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,HSTRING__ * *)
0x1800dac22  test    eax, eax
0x1800dac24  js      short loc_1800DAC6E
0x1800dac26  mov     [rsp+60h+var_20], rsi
0x1800dac2b  mov     [rsp+60h+var_28], r15; unsigned __int16 *
0x1800dac30  mov     [rsp+60h+pcbData], r15; char *
0x1800dac35  lea     rax, aFulfillmentDat; "Fulfillment data found for %s is placeh"...
0x1800dac3c  mov     [rsp+60h+pvData], rax; unsigned __int16 *
0x1800dac41  mov     dword ptr [rsp+60h+pdwType], 0FFFFFFFFh; int
0x1800dac49  lea     r9, aGetcachedfulfi_0; "GetCachedFulfillmentData"
0x1800dac50  mov     r8d, 257h; unsigned int
0x1800dac56  lea     rdx, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\installs"...
0x1800dac5d  mov     ecx, 2; unsigned int
0x1800dac62  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800dac67  mov     ebx, 80070002h
0x1800dac6c  jmp     short loc_1800DAC7C
0x1800dac6e  mov     rax, [rbp+hMem]
0x1800dac72  mov     [rbp+hMem], r15
0x1800dac76  mov     [r14], rax
0x1800dac79  mov     ebx, r15d
0x1800dac7c  mov     rcx, [rbp+string]; string
0x1800dac80  call    cs:__imp_WindowsDeleteString
0x1800dac86  nop
0x1800dac87  lea     rcx, [rbp+arg_18]
0x1800dac8b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800dac90  nop
0x1800dac91  mov     rcx, [rbp+hMem]; string
0x1800dac95  call    cs:__imp_WindowsDeleteString
0x1800dac9b  nop
0x1800dac9c  lea     rcx, [rbp+var_10]
0x1800daca0  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800daca5  mov     rcx, rdi; hMem
0x1800daca8  call    cs:__imp_LocalFree
0x1800dacae  mov     eax, ebx
0x1800dacb0  mov     rbx, [rsp+60h+arg_0]
0x1800dacb8  add     rsp, 60h
0x1800dacbc  pop     r15
0x1800dacbe  pop     r14
0x1800dacc0  pop     rdi
0x1800dacc1  pop     rsi
0x1800dacc2  pop     rbp
0x1800dacc3  retn
```
