# CSettingsManager::DownloadSettingsStrings(ushort const *,ushort const *)

- ea: `0x1801c4de0`
- end: `0x1801c5142`
- name: `?DownloadSettingsStrings@CSettingsManager@@QEAAJPEBG0@Z`
- size: `866`
- prototype: `__int64 __fastcall(CSettingsManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801a8178`

## callees

- `0x180009dd0`
- `0x180009dfc`
- `0x180041d1c`
- `0x180041f54`
- `0x1801ba0c4`
- `0x1801c4de0`
- `0x1801c57dc`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801c4fa0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801c4fe1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801c5029`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801c5085`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801c4fa0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801c4fe1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801c5029`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801c5085`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801c50c5`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801c50de`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801c50fc`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801c50c5`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801c50de`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801c50fc`
- `XmlLite!CreateXmlReader` at `0x1801c4e93`
- `XmlLite!CreateXmlReader` at `0x1801c4e93`

## pseudocode

```c
__int64 __fastcall CSettingsManager::DownloadSettingsStrings(
        CSettingsManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HRESULT v4; // ebx
  __int64 v5; // rbx
  char v6; // si
  char v7; // di
  int v8; // eax
  CSettingsManager *v9; // rcx
  CSettingsManager *v10; // rcx
  CSettingsManager *v11; // rcx
  int v13; // [rsp+40h] [rbp-40h] BYREF
  int v14; // [rsp+44h] [rbp-3Ch] BYREF
  void *ppvObject; // [rsp+48h] [rbp-38h] BYREF
  LPCWCH lpString1; // [rsp+50h] [rbp-30h] BYREF
  __int64 v17; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v18[4]; // [rsp+60h] [rbp-20h] BYREF
  int v19; // [rsp+C8h] [rbp+48h] BYREF

  v17 = 0;
  memset(v18, 0, 24);
  v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         v18,
         L"?setlang=%s&cc=%s",
         a2,
         a3);
  if ( v4 < 0 )
    goto LABEL_31;
  v5 = *((_QWORD *)this + 2);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  v4 = CConnectedSearchTransport::_HttpRequest(v5, 7, L"GET", v18[0], 0, 0, 0, &v17);
  if ( v4 < 0 )
    goto LABEL_31;
  ppvObject = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
  v4 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v4 < 0 )
    goto LABEL_30;
  v4 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v17);
  if ( v4 < 0 )
    goto LABEL_30;
  v6 = 0;
  v7 = 0;
  while ( v4 >= 0 && !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 200LL))(ppvObject) )
  {
    v19 = 0;
    lpString1 = 0;
    v14 = 0;
    v13 = 0;
    v8 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v19);
    v4 = v8;
    if ( v8 == 1 )
    {
      v4 = 0;
      break;
    }
    if ( v8 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(void *, LPCWCH *, int *))(*(_QWORD *)ppvObject + 112LL))(
             ppvObject,
             &lpString1,
             &v14);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 192LL))(ppvObject, &v13);
        if ( v4 >= 0 )
        {
          if ( v19 == 1 )
          {
            if ( v13 )
            {
              if ( v13 == 1 )
              {
                if ( CompareStringOrdinal(lpString1, -1, L"termsOfUse", -1, 0) == 2 )
                {
                  v4 = CSettingsManager::SaveSettingsStrings(
                         v9,
                         (struct IXmlReader *)ppvObject,
                         0,
                         L"ConnectedSearchTOUUrl");
                }
                else if ( CompareStringOrdinal(lpString1, -1, L"impressum", -1, 0) == 2 )
                {
                  v4 = CSettingsManager::SaveSettingsStrings(
                         v10,
                         (struct IXmlReader *)ppvObject,
                         L"ConnectedSearchImpressumTitle",
                         L"ConnectedSearchImpressumUrl");
                  v6 = 1;
                }
                else if ( CompareStringOrdinal(lpString1, -1, L"icp", -1, 0) == 2 )
                {
                  v4 = CSettingsManager::SaveSettingsStrings(
                         v11,
                         (struct IXmlReader *)ppvObject,
                         L"ConnectedSearchICPTitle",
                         0);
                  v7 = 1;
                }
              }
            }
            else
            {
LABEL_23:
              if ( CompareStringOrdinal(lpString1, -1, L"settings", -1, 0) != 2 )
                v4 = -2147467259;
            }
          }
          else if ( v19 == 15 && v13 == 1 )
          {
            goto LABEL_23;
          }
        }
      }
    }
  }
  if ( !v6 )
  {
    RegDeleteKeyValueW(
      HKEY_CURRENT_USER,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ConnectedSearch",
      L"ConnectedSearchImpressumTitle");
    RegDeleteKeyValueW(
      HKEY_CURRENT_USER,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ConnectedSearch",
      L"ConnectedSearchImpressumUrl");
  }
  if ( !v7 )
    RegDeleteKeyValueW(
      HKEY_CURRENT_USER,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ConnectedSearch",
      L"ConnectedSearchICPTitle");
LABEL_30:
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
LABEL_31:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v18);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1801c4de0  mov     [rsp-28h+arg_0], rbx
0x1801c4de5  mov     [rsp-28h+arg_8], rsi
0x1801c4dea  push    rbp
0x1801c4deb  push    rdi
0x1801c4dec  push    r12
0x1801c4dee  push    r14
0x1801c4df0  push    r15
0x1801c4df2  mov     rbp, rsp
0x1801c4df5  sub     rsp, 80h
0x1801c4dfc  xor     r14d, r14d
0x1801c4dff  mov     r9, r8
0x1801c4e02  mov     r8, rdx
0x1801c4e05  mov     [rbp+var_28], r14
0x1801c4e09  mov     rdi, rcx
0x1801c4e0c  mov     [rbp+var_20], r14
0x1801c4e10  lea     rdx, aSetlangSCcS; "?setlang=%s&cc=%s"
0x1801c4e17  mov     [rbp+var_18], r14
0x1801c4e1b  lea     rcx, [rbp+var_20]
0x1801c4e1f  mov     [rbp+var_10], r14
0x1801c4e23  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1801c4e28  mov     ebx, eax
0x1801c4e2a  test    eax, eax
0x1801c4e2c  js      loc_1801C5111
0x1801c4e32  mov     rbx, [rdi+10h]
0x1801c4e36  lea     rcx, [rbp+var_28]
0x1801c4e3a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c4e3f  mov     r9, [rbp+var_20]
0x1801c4e43  lea     rax, [rbp+var_28]
0x1801c4e47  mov     [rsp+80h+var_48], rax
0x1801c4e4c  lea     r8, aGet; "GET"
0x1801c4e53  mov     [rsp+80h+var_50], r14
0x1801c4e58  lea     edx, [r14+7]
0x1801c4e5c  mov     [rsp+80h+var_58], r14d
0x1801c4e61  mov     rcx, rbx
0x1801c4e64  mov     qword ptr [rsp+80h+bIgnoreCase], r14
0x1801c4e69  call    ?_HttpRequest@CConnectedSearchTransport@@AEAAJW4HttpEndpoint@1@PEBG11W4HttpRequestFlags@@1PEAPEAUIStream@@@Z; CConnectedSearchTransport::_HttpRequest(CConnectedSearchTransport::HttpEndpoint,ushort const *,ushort const *,ushort const *,HttpRequestFlags,ushort const *,IStream * *)
0x1801c4e6e  mov     ebx, eax
0x1801c4e70  test    eax, eax
0x1801c4e72  js      loc_1801C5111
0x1801c4e78  lea     rcx, [rbp+ppvObject]
0x1801c4e7c  mov     [rbp+ppvObject], r14
0x1801c4e80  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801c4e85  xor     r8d, r8d; pMalloc
0x1801c4e88  lea     rdx, [rbp+ppvObject]; ppvObject
0x1801c4e8c  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1801c4e93  call    cs:__imp_CreateXmlReader
0x1801c4e9a  nop     dword ptr [rax+rax+00h]
0x1801c4e9f  mov     ebx, eax
0x1801c4ea1  test    eax, eax
0x1801c4ea3  js      loc_1801C5108
0x1801c4ea9  mov     rcx, [rbp+ppvObject]
0x1801c4ead  mov     rdx, [rbp+var_28]
0x1801c4eb1  mov     rax, [rcx]
0x1801c4eb4  mov     rax, [rax+18h]
0x1801c4eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4ebd  mov     ebx, eax
0x1801c4ebf  test    eax, eax
0x1801c4ec1  js      loc_1801C5108
0x1801c4ec7  mov     sil, r14b
0x1801c4eca  mov     dil, r14b
0x1801c4ecd  or      r15d, 0FFFFFFFFh
0x1801c4ed1  mov     r12d, 80004005h
0x1801c4ed7  test    ebx, ebx
0x1801c4ed9  js      loc_1801C50A5
0x1801c4edf  mov     rcx, [rbp+ppvObject]
0x1801c4ee3  mov     rax, [rcx]
0x1801c4ee6  mov     rax, [rax+0C8h]
0x1801c4eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4ef2  test    eax, eax
0x1801c4ef4  jnz     loc_1801C50A5
0x1801c4efa  mov     rcx, [rbp+ppvObject]
0x1801c4efe  lea     rdx, [rbp+arg_18]
0x1801c4f02  mov     [rbp+arg_18], r14d
0x1801c4f06  mov     [rbp+lpString1], r14
0x1801c4f0a  mov     [rbp+var_3C], r14d
0x1801c4f0e  mov     [rbp+var_40], r14d
0x1801c4f12  mov     rax, [rcx]
0x1801c4f15  mov     rax, [rax+30h]
0x1801c4f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4f1e  mov     ebx, eax
0x1801c4f20  cmp     eax, 1
0x1801c4f23  jz      loc_1801C50A2
0x1801c4f29  test    eax, eax
0x1801c4f2b  js      short loc_1801C4ED7
0x1801c4f2d  mov     rcx, [rbp+ppvObject]
0x1801c4f31  lea     r8, [rbp+var_3C]
0x1801c4f35  lea     rdx, [rbp+lpString1]
0x1801c4f39  mov     rax, [rcx]
0x1801c4f3c  mov     rax, [rax+70h]
0x1801c4f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4f45  mov     ebx, eax
0x1801c4f47  test    eax, eax
0x1801c4f49  js      short loc_1801C4ED7
0x1801c4f4b  mov     rcx, [rbp+ppvObject]
0x1801c4f4f  lea     rdx, [rbp+var_40]
0x1801c4f53  mov     rax, [rcx]
0x1801c4f56  mov     rax, [rax+0C0h]
0x1801c4f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4f62  mov     ebx, eax
0x1801c4f64  test    eax, eax
0x1801c4f66  js      loc_1801C4ED7
0x1801c4f6c  cmp     [rbp+arg_18], 1
0x1801c4f70  jnz     loc_1801C505B
0x1801c4f76  mov     eax, [rbp+var_40]
0x1801c4f79  test    eax, eax
0x1801c4f7b  jz      loc_1801C506F
0x1801c4f81  cmp     eax, 1
0x1801c4f84  jnz     loc_1801C4ED7
0x1801c4f8a  mov     rcx, [rbp+lpString1]; lpString1
0x1801c4f8e  lea     r8, aTermsofuse; "termsOfUse"
0x1801c4f95  mov     r9d, r15d; cchCount2
0x1801c4f98  mov     [rsp+80h+bIgnoreCase], r14d; bIgnoreCase
0x1801c4f9d  mov     edx, r15d; cchCount1
0x1801c4fa0  call    cs:__imp_CompareStringOrdinal
0x1801c4fa7  nop     dword ptr [rax+rax+00h]
0x1801c4fac  cmp     eax, 2
0x1801c4faf  jnz     short loc_1801C4FCB
0x1801c4fb1  mov     rdx, [rbp+ppvObject]; struct IXmlReader *
0x1801c4fb5  lea     r9, aConnectedsearc_11; "ConnectedSearchTOUUrl"
0x1801c4fbc  xor     r8d, r8d; unsigned __int16 *
0x1801c4fbf  call    ?SaveSettingsStrings@CSettingsManager@@QEAAJPEAUIXmlReader@@PEBG1@Z; CSettingsManager::SaveSettingsStrings(IXmlReader *,ushort const *,ushort const *)
0x1801c4fc4  mov     ebx, eax
0x1801c4fc6  jmp     loc_1801C4ED7
0x1801c4fcb  mov     rcx, [rbp+lpString1]; lpString1
0x1801c4fcf  lea     r8, aImpressum; "impressum"
0x1801c4fd6  mov     r9d, r15d; cchCount2
0x1801c4fd9  mov     [rsp+80h+bIgnoreCase], r14d; bIgnoreCase
0x1801c4fde  mov     edx, r15d; cchCount1
0x1801c4fe1  call    cs:__imp_CompareStringOrdinal
0x1801c4fe8  nop     dword ptr [rax+rax+00h]
0x1801c4fed  cmp     eax, 2
0x1801c4ff0  jnz     short loc_1801C5013
0x1801c4ff2  mov     rdx, [rbp+ppvObject]; struct IXmlReader *
0x1801c4ff6  lea     r9, aConnectedsearc_9; "ConnectedSearchImpressumUrl"
0x1801c4ffd  lea     r8, aConnectedsearc_7; "ConnectedSearchImpressumTitle"
0x1801c5004  call    ?SaveSettingsStrings@CSettingsManager@@QEAAJPEAUIXmlReader@@PEBG1@Z; CSettingsManager::SaveSettingsStrings(IXmlReader *,ushort const *,ushort const *)
0x1801c5009  mov     ebx, eax
0x1801c500b  mov     sil, 1
0x1801c500e  jmp     loc_1801C4ED7
0x1801c5013  mov     rcx, [rbp+lpString1]; lpString1
0x1801c5017  lea     r8, aIcp; "icp"
0x1801c501e  mov     r9d, r15d; cchCount2
0x1801c5021  mov     [rsp+80h+bIgnoreCase], r14d; bIgnoreCase
0x1801c5026  mov     edx, r15d; cchCount1
0x1801c5029  call    cs:__imp_CompareStringOrdinal
0x1801c5030  nop     dword ptr [rax+rax+00h]
0x1801c5035  cmp     eax, 2
0x1801c5038  jnz     loc_1801C4ED7
0x1801c503e  mov     rdx, [rbp+ppvObject]; struct IXmlReader *
0x1801c5042  lea     r8, aConnectedsearc_10; "ConnectedSearchICPTitle"
0x1801c5049  xor     r9d, r9d; unsigned __int16 *
0x1801c504c  call    ?SaveSettingsStrings@CSettingsManager@@QEAAJPEAUIXmlReader@@PEBG1@Z; CSettingsManager::SaveSettingsStrings(IXmlReader *,ushort const *,ushort const *)
0x1801c5051  mov     ebx, eax
0x1801c5053  mov     dil, 1
0x1801c5056  jmp     loc_1801C4ED7
0x1801c505b  cmp     [rbp+arg_18], 0Fh
0x1801c505f  jnz     loc_1801C4ED7
0x1801c5065  cmp     [rbp+var_40], 1
0x1801c5069  jnz     loc_1801C4ED7
0x1801c506f  mov     rcx, [rbp+lpString1]; lpString1
0x1801c5073  lea     r8, aSettings; "settings"
0x1801c507a  mov     r9d, r15d; cchCount2
0x1801c507d  mov     [rsp+80h+bIgnoreCase], r14d; bIgnoreCase
0x1801c5082  mov     edx, r15d; cchCount1
0x1801c5085  call    cs:__imp_CompareStringOrdinal
0x1801c508c  nop     dword ptr [rax+rax+00h]
0x1801c5091  cmp     eax, 2
0x1801c5094  jz      loc_1801C4ED7
0x1801c509a  mov     ebx, r12d
0x1801c509d  jmp     loc_1801C4ED7
0x1801c50a2  mov     ebx, r14d
0x1801c50a5  lea     r15, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1801c50ac  mov     r12, 0FFFFFFFF80000001h
0x1801c50b3  test    sil, sil
0x1801c50b6  jnz     short loc_1801C50EA
0x1801c50b8  lea     r8, aConnectedsearc_7; "ConnectedSearchImpressumTitle"
0x1801c50bf  mov     rdx, r15; lpSubKey
0x1801c50c2  mov     rcx, r12; hKey
0x1801c50c5  call    cs:__imp_RegDeleteKeyValueW
0x1801c50cc  nop     dword ptr [rax+rax+00h]
0x1801c50d1  lea     r8, aConnectedsearc_9; "ConnectedSearchImpressumUrl"
0x1801c50d8  mov     rdx, r15; lpSubKey
0x1801c50db  mov     rcx, r12; hKey
0x1801c50de  call    cs:__imp_RegDeleteKeyValueW
0x1801c50e5  nop     dword ptr [rax+rax+00h]
0x1801c50ea  test    dil, dil
0x1801c50ed  jnz     short loc_1801C5108
0x1801c50ef  lea     r8, aConnectedsearc_10; "ConnectedSearchICPTitle"
0x1801c50f6  mov     rdx, r15; lpSubKey
0x1801c50f9  mov     rcx, r12; hKey
0x1801c50fc  call    cs:__imp_RegDeleteKeyValueW
0x1801c5103  nop     dword ptr [rax+rax+00h]
0x1801c5108  lea     rcx, [rbp+ppvObject]
0x1801c510c  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801c5111  lea     rcx, [rbp+var_20]
0x1801c5115  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801c511a  lea     rcx, [rbp+var_28]
0x1801c511e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c5123  lea     r11, [rsp+80h+var_s0]
0x1801c512b  mov     eax, ebx
0x1801c512d  mov     rbx, [r11+30h]
0x1801c5131  mov     rsi, [r11+38h]
0x1801c5135  mov     rsp, r11
0x1801c5138  pop     r15
0x1801c513a  pop     r14
0x1801c513c  pop     r12
0x1801c513e  pop     rdi
0x1801c513f  pop     rbp
0x1801c5140  retn
```
