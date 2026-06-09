# RoutingRegistryHelper::RemoveAppletIdGroupRegKeys(ushort const *,_GUID)

- ea: `0x18003a878`
- end: `0x18003aa21`
- name: `?RemoveAppletIdGroupRegKeys@RoutingRegistryHelper@@SAJPEBGU_GUID@@@Z`
- size: `425`
- prototype: `__int64 __fastcall(const unsigned __int16 *, GUID *rguid)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003bc1c`
- `0x1800407ec`
- `0x180040b50`

## callees

- `0x1800049a0`
- `0x180005858`
- `0x18000d4ec`
- `0x180013274`
- `0x180038e30`
- `0x18003a878`
- `0x18003aa28`
- `0x18007d804`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003a941`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003a941`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a9ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a9ec`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003a986`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003a986`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18003a9a7`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18003a9a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RoutingRegistryHelper::RemoveAppletIdGroupRegKeys(WCHAR *a1, GUID *rguid)
{
  unsigned int v4; // edx
  int AppletIdGroupAssetDataPath; // ebx
  int v6; // eax
  LSTATUS v7; // eax
  const WCHAR *v8; // rcx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v11; // [rsp+38h] [rbp-C8h] BYREF
  __m128i si128; // [rsp+48h] [rbp-B8h]
  OLECHAR sz[40]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+B0h] [rbp-50h] BYREF

  v11 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v11) = 0;
  memset_0(SubKey, 0, 0x208u);
  memset_0(sz, 0, 0x4Eu);
  hKey = 0;
  if ( a1 )
  {
    hKey = 0;
    v6 = NfcRegOpenKeyEx((const struct NfcRegistryLocation *)&qword_1800A1C18, v4, 0x2001Fu, &hKey);
    AppletIdGroupAssetDataPath = v6;
    if ( v6 > 0 )
      AppletIdGroupAssetDataPath = (unsigned __int16)v6 | 0x80070000;
    if ( AppletIdGroupAssetDataPath >= 0 )
    {
      if ( StringFromGUID2(rguid, sz, 39) )
      {
        AppletIdGroupAssetDataPath = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", a1, sz);
        if ( AppletIdGroupAssetDataPath >= 0 )
        {
          v7 = RegDeleteTreeW(hKey, SubKey);
          AppletIdGroupAssetDataPath = v7;
          if ( v7 > 0 )
            AppletIdGroupAssetDataPath = (unsigned __int16)v7 | 0x80070000;
          if ( AppletIdGroupAssetDataPath >= 0 )
          {
            RegDeleteKeyW(hKey, a1);
            AppletIdGroupAssetDataPath = RoutingRegistryHelper::GetAppletIdGroupAssetDataPath(a1, rguid, (__int64)&v11);
            if ( AppletIdGroupAssetDataPath >= 0 )
            {
              AppletIdGroupAssetDataPath = 0;
              v8 = (const WCHAR *)&v11;
              if ( si128.m128i_i64[1] > 7uLL )
                v8 = (const WCHAR *)v11;
              wil::RemoveDirectoryRecursiveNoThrow(v8, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
            }
          }
        }
      }
      else
      {
        AppletIdGroupAssetDataPath = -2147467259;
      }
    }
  }
  else
  {
    AppletIdGroupAssetDataPath = -2147467261;
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(&v11);
  return (unsigned int)AppletIdGroupAssetDataPath;
}

```

## disassembly

```asm
0x18003a878  mov     [rsp-8+arg_10], rbx
0x18003a87d  push    rbp
0x18003a87e  push    rsi
0x18003a87f  push    rdi
0x18003a880  lea     rbp, [rsp-1D0h]
0x18003a888  sub     rsp, 2D0h
0x18003a88f  mov     rax, cs:__security_cookie
0x18003a896  xor     rax, rsp
0x18003a899  mov     [rbp+1E0h+var_20], rax
0x18003a8a0  mov     rsi, rdx
0x18003a8a3  mov     rdi, rcx
0x18003a8a6  xorps   xmm0, xmm0
0x18003a8a9  movups  [rsp+2E0h+var_2A8], xmm0
0x18003a8ae  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003a8b6  movdqu  [rsp+2E0h+var_298], xmm1
0x18003a8bc  xor     eax, eax
0x18003a8be  mov     word ptr [rsp+2E0h+var_2A8], ax
0x18003a8c3  xor     edx, edx; Val
0x18003a8c5  mov     r8d, 208h; Size
0x18003a8cb  lea     rcx, [rbp+1E0h+SubKey]; void *
0x18003a8cf  call    memset_0
0x18003a8d4  xor     edx, edx; Val
0x18003a8d6  lea     r8d, [rdx+4Eh]; Size
0x18003a8da  lea     rcx, [rsp+2E0h+sz]; void *
0x18003a8df  call    memset_0
0x18003a8e4  mov     [rsp+2E0h+hKey], 0
0x18003a8ed  test    rdi, rdi
0x18003a8f0  jnz     short loc_18003A8FC
0x18003a8f2  mov     ebx, 80004003h
0x18003a8f7  jmp     loc_18003A9E2
0x18003a8fc  mov     [rsp+2E0h+hKey], 0
0x18003a905  lea     r9, [rsp+2E0h+hKey]; HKEY *
0x18003a90a  mov     r8d, 2001Fh; unsigned int
0x18003a910  lea     rcx, qword_1800A1C18; struct NfcRegistryLocation *
0x18003a917  call    ?NfcRegOpenKeyEx@@YAJAEBUNfcRegistryLocation@@KKPEAPEAUHKEY__@@@Z; NfcRegOpenKeyEx(NfcRegistryLocation const &,ulong,ulong,HKEY__ * *)
0x18003a91c  mov     ebx, eax
0x18003a91e  test    eax, eax
0x18003a920  jle     short loc_18003A92B
0x18003a922  movzx   ebx, ax
0x18003a925  or      ebx, 80070000h
0x18003a92b  test    ebx, ebx
0x18003a92d  js      loc_18003A9E2
0x18003a933  mov     r8d, 27h ; '''; cchMax
0x18003a939  lea     rdx, [rsp+2E0h+sz]; lpsz
0x18003a93e  mov     rcx, rsi; rguid
0x18003a941  call    cs:__imp_StringFromGUID2
0x18003a947  test    eax, eax
0x18003a949  jnz     short loc_18003A955
0x18003a94b  mov     ebx, 80004005h
0x18003a950  jmp     loc_18003A9E2
0x18003a955  lea     rax, [rsp+2E0h+sz]
0x18003a95a  mov     [rsp+2E0h+var_2C0], rax
0x18003a95f  mov     r9, rdi
0x18003a962  lea     r8, aSS; "%s\\%s"
0x18003a969  mov     edx, 104h; unsigned __int64
0x18003a96e  lea     rcx, [rbp+1E0h+SubKey]; unsigned __int16 *
0x18003a972  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a977  mov     ebx, eax
0x18003a979  test    eax, eax
0x18003a97b  js      short loc_18003A9E2
0x18003a97d  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x18003a981  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18003a986  call    cs:__imp_RegDeleteTreeW
0x18003a98c  mov     ebx, eax
0x18003a98e  test    eax, eax
0x18003a990  jle     short loc_18003A99B
0x18003a992  movzx   ebx, ax
0x18003a995  or      ebx, 80070000h
0x18003a99b  test    ebx, ebx
0x18003a99d  js      short loc_18003A9E2
0x18003a99f  mov     rdx, rdi; lpSubKey
0x18003a9a2  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18003a9a7  call    cs:__imp_RegDeleteKeyW
0x18003a9ad  lea     r8, [rsp+2E0h+var_2A8]
0x18003a9b2  mov     rdx, rsi; rguid
0x18003a9b5  mov     rcx, rdi; void *
0x18003a9b8  call    ?GetAppletIdGroupAssetDataPath@RoutingRegistryHelper@@CAJPEBGAEBU_GUID@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RoutingRegistryHelper::GetAppletIdGroupAssetDataPath(ushort const *,_GUID const &,std::wstring *)
0x18003a9bd  mov     ebx, eax
0x18003a9bf  test    eax, eax
0x18003a9c1  js      short loc_18003A9E2
0x18003a9c3  xor     ebx, ebx
0x18003a9c5  lea     rcx, [rsp+2E0h+var_2A8]
0x18003a9ca  cmp     qword ptr [rsp+2E0h+var_298+8], 7
0x18003a9d0  cmova   rcx, qword ptr [rsp+2E0h+var_2A8]
0x18003a9d6  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003a9da  xor     edx, edx
0x18003a9dc  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18003a9e1  nop
0x18003a9e2  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18003a9e7  test    rcx, rcx
0x18003a9ea  jz      short loc_18003A9F3
0x18003a9ec  call    cs:__imp_RegCloseKey
0x18003a9f2  nop
0x18003a9f3  lea     rcx, [rsp+2E0h+var_2A8]
0x18003a9f8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a9fd  mov     eax, ebx
0x18003a9ff  mov     rcx, [rbp+1E0h+var_20]
0x18003aa06  xor     rcx, rsp; StackCookie
0x18003aa09  call    __security_check_cookie
0x18003aa0e  mov     rbx, [rsp+2E0h+arg_10]
0x18003aa16  add     rsp, 2D0h
0x18003aa1d  pop     rdi
0x18003aa1e  pop     rsi
0x18003aa1f  pop     rbp
0x18003aa20  retn
```
