# CabUtils::IsFileMicrosoftSigned(ushort const *)

- ea: `0x18003e60c`
- end: `0x18003e7a7`
- name: `?IsFileMicrosoftSigned@CabUtils@@SAJPEBG@Z`
- size: `411`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180040220`

## callees

- `0x18000a6e0`
- `0x18000b2b4`
- `0x18001206c`
- `0x18001208c`
- `0x180019ecc`
- `0x18003e190`
- `0x18003e4a0`
- `0x18003e60c`
- `0x18003e7b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003e659`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003e659`
- `WINTRUST!WinVerifyTrust` at `0x18003e774`
- `WINTRUST!WinVerifyTrust` at `0x18003e774`

## string_xrefs

- `0x18003e671`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003e6d6`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003e6ee`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003e74c`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`

## pseudocode

```c
__int64 __fastcall CabUtils::IsFileMicrosoftSigned(const unsigned __int16 *a1)
{
  const char *v2; // r9
  unsigned int LastError; // ebx
  int WinTrustDataForFileInCatalog; // eax
  int IsMicrosoftSigned; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  HANDLE v9[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _WINTRUST_DATA pWVTData; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v11; // [rsp+A0h] [rbp-60h]
  _WINTRUST_DATA v12; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v13; // [rsp+100h] [rbp+0h]
  GUID pgActionID; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v9[0] = CreateFileW(a1, 0x120089u, 1u, 0, 3u, 4u, 0);
  if ( v9[0] == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1EC,
                  (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
                  v2);
  }
  else
  {
    memset_0(&pWVTData, 0, 0x58u);
    pgActionID = 0;
    if ( (int)CabUtils::GetWinTrustDataFromFile(v9[0], a1, &pWVTData, &pgActionID) >= 0
      || (WinTrustDataForFileInCatalog = CabUtils::GetWinTrustDataForFileInCatalog(v9[0], a1, &pWVTData, &pgActionID),
          LastError = WinTrustDataForFileInCatalog,
          WinTrustDataForFileInCatalog >= 0) )
    {
      v12 = pWVTData;
      v13 = v11;
      IsMicrosoftSigned = CabUtils::IsMicrosoftSigned(&v12);
      LastError = IsMicrosoftSigned;
      if ( IsMicrosoftSigned < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1FB,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
          (const char *)(unsigned int)IsMicrosoftSigned,
          dwCreationDisposition);
      pWVTData.dwStateAction = 2;
      WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, &pWVTData);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x209,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
        (const char *)(unsigned int)WinTrustDataForFileInCatalog,
        dwCreationDisposition);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F1,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
        (const char *)LastError,
        dwCreationDispositiona);
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v9);
  return LastError;
}

```

## disassembly

```asm
0x18003e60c  mov     [rsp-8+arg_8], rbx
0x18003e611  mov     [rsp-8+arg_10], rdi
0x18003e616  push    rbp
0x18003e617  lea     rbp, [rsp-30h]
0x18003e61c  sub     rsp, 130h
0x18003e623  mov     rax, cs:__security_cookie
0x18003e62a  xor     rax, rsp
0x18003e62d  mov     [rbp+30h+var_10], rax
0x18003e631  xor     r9d, r9d; lpSecurityAttributes
0x18003e634  mov     [rsp+130h+hTemplateFile], 0; hTemplateFile
0x18003e63d  mov     [rsp+130h+dwFlagsAndAttributes], 4; dwFlagsAndAttributes
0x18003e645  mov     edx, 120089h; dwDesiredAccess
0x18003e64a  mov     rdi, rcx
0x18003e64d  mov     [rsp+130h+dwCreationDisposition], 3; int
0x18003e655  lea     r8d, [r9+1]; dwShareMode
0x18003e659  call    cs:__imp_CreateFileW
0x18003e65f  mov     [rsp+130h+var_F0], rax
0x18003e664  mov     rbx, rax
0x18003e667  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003e66b  jnz     short loc_18003E689
0x18003e66d  mov     rcx, [rbp+38h]; this
0x18003e671  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003e678  mov     edx, 1ECh; void *
0x18003e67d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e682  mov     ebx, eax
0x18003e684  jmp     loc_18003E77A
0x18003e689  xor     edx, edx; Val
0x18003e68b  lea     rcx, [rsp+130h+pWVTData]; void *
0x18003e690  lea     r8d, [rdx+58h]; Size
0x18003e694  call    memset_0
0x18003e699  xorps   xmm0, xmm0
0x18003e69c  lea     r9, [rbp+30h+pgActionID]; struct _GUID *
0x18003e6a0  lea     r8, [rsp+130h+pWVTData]; struct _WINTRUST_DATA *
0x18003e6a5  mov     rdx, rdi; unsigned __int16 *
0x18003e6a8  mov     rcx, rbx; void *
0x18003e6ab  movups  xmmword ptr [rbp+30h+pgActionID.Data1], xmm0
0x18003e6af  call    ?GetWinTrustDataFromFile@CabUtils@@CAJPEAXPEBGPEAU_WINTRUST_DATA@@PEAU_GUID@@@Z; CabUtils::GetWinTrustDataFromFile(void *,ushort const *,_WINTRUST_DATA *,_GUID *)
0x18003e6b4  test    eax, eax
0x18003e6b6  jns     short loc_18003E704
0x18003e6b8  lea     r9, [rbp+30h+pgActionID]; struct _GUID *
0x18003e6bc  mov     rdx, rdi; unsigned __int16 *
0x18003e6bf  lea     r8, [rsp+130h+pWVTData]; struct _WINTRUST_DATA *
0x18003e6c4  mov     rcx, rbx; hFile
0x18003e6c7  call    ?GetWinTrustDataForFileInCatalog@CabUtils@@CAJPEAXPEBGPEAU_WINTRUST_DATA@@PEAU_GUID@@@Z; CabUtils::GetWinTrustDataForFileInCatalog(void *,ushort const *,_WINTRUST_DATA *,_GUID *)
0x18003e6cc  mov     ebx, eax
0x18003e6ce  test    eax, eax
0x18003e6d0  jns     short loc_18003E704
0x18003e6d2  mov     rcx, [rbp+38h]; this
0x18003e6d6  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003e6dd  mov     r9d, eax; char *
0x18003e6e0  mov     edx, 209h; void *
0x18003e6e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e6ea  mov     rcx, [rbp+38h]; this
0x18003e6ee  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003e6f5  mov     r9d, ebx; char *
0x18003e6f8  mov     edx, 1F1h; void *
0x18003e6fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e702  jmp     short loc_18003E77A
0x18003e704  movaps  xmm0, [rsp+130h+pWVTData]
0x18003e709  lea     rcx, [rbp+30h+var_80]; struct _WINTRUST_DATA
0x18003e70d  movaps  xmm1, [rsp+130h+var_D0]
0x18003e712  movaps  xmmword ptr [rbp+30h+var_80.cbStruct], xmm0
0x18003e716  movaps  xmm0, [rsp+130h+var_C0]
0x18003e71b  movaps  xmmword ptr [rbp+30h+var_80.pSIPClientData], xmm1
0x18003e71f  movaps  xmm1, [rbp+30h+var_B0]
0x18003e723  movaps  xmmword ptr [rbp+30h+var_80.dwUnionChoice], xmm0
0x18003e727  movaps  xmm0, [rbp+30h+var_A0]
0x18003e72b  movaps  xmmword ptr [rbp+30h+var_80.dwStateAction], xmm1
0x18003e72f  movsd   xmm1, [rbp+30h+var_90]
0x18003e734  movaps  xmmword ptr [rbp+30h+var_80.pwszURLReference], xmm0
0x18003e738  movsd   [rbp+30h+var_30], xmm1
0x18003e73d  call    ?IsMicrosoftSigned@CabUtils@@CAJU_WINTRUST_DATA@@@Z; CabUtils::IsMicrosoftSigned(_WINTRUST_DATA)
0x18003e742  mov     ebx, eax
0x18003e744  test    eax, eax
0x18003e746  jns     short loc_18003E760
0x18003e748  mov     rcx, [rbp+38h]; this
0x18003e74c  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003e753  mov     r9d, eax; char *
0x18003e756  mov     edx, 1FBh; void *
0x18003e75b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e760  lea     r8, [rsp+130h+pWVTData]; pWVTData
0x18003e765  mov     dword ptr [rbp+30h+var_B0], 2
0x18003e76c  lea     rdx, [rbp+30h+pgActionID]; pgActionID
0x18003e770  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x18003e774  call    cs:__imp_WinVerifyTrust
0x18003e77a  lea     rcx, [rsp+130h+var_F0]
0x18003e77f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003e784  mov     eax, ebx
0x18003e786  mov     rcx, [rbp+30h+var_10]
0x18003e78a  xor     rcx, rsp; StackCookie
0x18003e78d  call    __security_check_cookie
0x18003e792  lea     r11, [rsp+130h+var_s0]
0x18003e79a  mov     rbx, [r11+18h]
0x18003e79e  mov     rdi, [r11+20h]
0x18003e7a2  mov     rsp, r11
0x18003e7a5  pop     rbp
0x18003e7a6  retn
```
