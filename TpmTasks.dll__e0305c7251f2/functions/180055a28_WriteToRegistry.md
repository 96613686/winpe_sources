# WriteToRegistry

- ea: `0x180055a28`
- end: `0x180055b21`
- name: `WriteToRegistry`
- size: `249`
- prototype: `__int64 __fastcall(unsigned int, DWORD cbData)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180055894`

## callees

- `0x18000e48c`
- `0x18001a450`
- `0x180055870`
- `0x180055a28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180055a96`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180055a96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180055ad7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180055ad7`

## pseudocode

```c
__int64 __fastcall WriteToRegistry(const BYTE *a1, DWORD cbData)
{
  unsigned int v4; // ebx
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-58h]
  HKEY *p_hKey; // [rsp+50h] [rbp-28h] BYREF
  HKEY v12; // [rsp+58h] [rbp-20h] BYREF
  char v13; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HKEY hKey; // [rsp+90h] [rbp+18h] BYREF

  p_hKey = &hKey;
  v12 = 0;
  hKey = 0;
  v13 = 1;
  v4 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SecureBoot",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &v12,
         0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v4 )
  {
    v5 = (const char *)v4;
    v6 = 65;
  }
  else
  {
    v7 = RegSetValueExW(hKey, L"EncodedUEFI", 0, 3u, a1, cbData);
    if ( !v7 )
    {
      v8 = 0;
      goto LABEL_7;
    }
    v5 = (const char *)v7;
    v6 = 72;
  }
  v8 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v6,
         (unsigned int)"onecore\\base\\secureboot\\uefiencoding\\encoder\\securebootencodeuefi.cpp",
         v5,
         dwOptions);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v8;
}

```

## disassembly

```asm
0x180055a28  mov     r11, rsp
0x180055a2b  mov     [r11+8], rbx
0x180055a2f  mov     [r11+10h], rsi
0x180055a33  push    rdi
0x180055a34  sub     rsp, 70h
0x180055a38  mov     qword ptr [r11-38h], 0
0x180055a40  lea     rax, [r11+18h]
0x180055a44  mov     [r11-28h], rax
0x180055a48  mov     edi, edx
0x180055a4a  lea     rax, [r11-20h]
0x180055a4e  mov     qword ptr [r11-20h], 0
0x180055a56  mov     [r11-40h], rax
0x180055a5a  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180055a61  mov     qword ptr [r11-48h], 0
0x180055a69  mov     rsi, rcx
0x180055a6c  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180055a74  xor     r9d, r9d; lpClass
0x180055a77  xor     r8d, r8d; Reserved
0x180055a7a  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180055a82  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180055a89  mov     qword ptr [r11+18h], 0
0x180055a91  mov     [rsp+78h+var_18], 1
0x180055a96  call    cs:__imp_RegCreateKeyExW
0x180055a9c  lea     rcx, [rsp+78h+var_28]
0x180055aa1  mov     ebx, eax
0x180055aa3  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180055aa8  test    ebx, ebx
0x180055aaa  jz      short loc_180055AB6
0x180055aac  mov     r9d, ebx
0x180055aaf  mov     edx, 41h ; 'A'
0x180055ab4  jmp     short loc_180055AE9
0x180055ab6  mov     rcx, [rsp+78h+hKey]; hKey
0x180055abe  lea     rdx, aEncodeduefi; "EncodedUEFI"
0x180055ac5  mov     [rsp+78h+samDesired], edi; cbData
0x180055ac9  mov     r9d, 3; dwType
0x180055acf  xor     r8d, r8d; Reserved
0x180055ad2  mov     qword ptr [rsp+78h+dwOptions], rsi; unsigned int
0x180055ad7  call    cs:__imp_RegSetValueExW
0x180055add  test    eax, eax
0x180055adf  jz      short loc_180055AFE
0x180055ae1  mov     r9d, eax; char *
0x180055ae4  mov     edx, 48h ; 'H'; void *
0x180055ae9  mov     rcx, [rsp+78h]; this
0x180055aee  lea     r8, aOnecoreBaseSec_2; "onecore\\base\\secureboot\\uefiencoding"...
0x180055af5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180055afa  mov     ebx, eax
0x180055afc  jmp     short loc_180055B00
0x180055afe  xor     ebx, ebx
0x180055b00  lea     rcx, [rsp+78h+hKey]
0x180055b08  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180055b0d  lea     r11, [rsp+78h+var_8]
0x180055b12  mov     eax, ebx
0x180055b14  mov     rbx, [r11+10h]
0x180055b18  mov     rsi, [r11+18h]
0x180055b1c  mov     rsp, r11
0x180055b1f  pop     rdi
0x180055b20  retn
```
