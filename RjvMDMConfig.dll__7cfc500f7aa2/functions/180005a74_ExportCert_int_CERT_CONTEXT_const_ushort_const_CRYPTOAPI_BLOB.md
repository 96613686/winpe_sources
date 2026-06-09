# ExportCert(int,_CERT_CONTEXT const *,ushort const *,_CRYPTOAPI_BLOB *)

- ea: `0x180005a74`
- end: `0x180005bf4`
- name: `?ExportCert@@YAJHPEBU_CERT_CONTEXT@@PEBGPEAU_CRYPTOAPI_BLOB@@@Z`
- size: `384`
- prototype: `int(int, const struct _CERT_CONTEXT *, const unsigned __int16 *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800039fc`

## callees

- `0x180003910`
- `0x18000562c`
- `0x180005a74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bc6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005b87`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005b87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b70`
- `CRYPT32!CertOpenStore` at `0x180005aa8`
- `CRYPT32!CertOpenStore` at `0x180005aa8`
- `CRYPT32!PFXExportCertStoreEx` at `0x180005b5b`
- `CRYPT32!PFXExportCertStoreEx` at `0x180005bb6`
- `CRYPT32!PFXExportCertStoreEx` at `0x180005b5b`
- `CRYPT32!PFXExportCertStoreEx` at `0x180005bb6`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180005afe`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180005afe`

## pseudocode

```c
__int64 __fastcall ExportCert(
        __int64 a1,
        const struct _CERT_CONTEXT *a2,
        const unsigned __int16 *a3,
        struct _CRYPTOAPI_BLOB *a4)
{
  HCERTSTORE v6; // rax
  signed int v7; // eax
  signed int v8; // edi
  signed int LastError; // eax
  HCERTSTORE v10; // rcx
  DWORD cbData; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v13; // rax
  signed int v14; // eax
  HCERTSTORE hCertStore; // [rsp+70h] [rbp+18h] BYREF

  hCertStore = 0;
  v6 = CertOpenStore((LPCSTR)2, 0, 0, 0x2280u, 0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hCertStore,
    v6);
  if ( hCertStore )
  {
    v8 = 0;
    if ( CertAddCertificateContextToStore(hCertStore, a2, 3u, 0) )
      goto LABEL_8;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
    {
LABEL_8:
      v10 = hCertStore;
      a4->cbData = 0;
      a4->pbData = 0;
      PFXExportCertStoreEx(v10, a4, szPassword, 0, 0x16u);
      if ( !a4->cbData
        || (cbData = a4->cbData,
            ProcessHeap = GetProcessHeap(),
            v13 = (BYTE *)HeapAlloc(ProcessHeap, 8u, cbData),
            (a4->pbData = v13) == 0)
        || !PFXExportCertStoreEx(hCertStore, a4, szPassword, 0, 0x16u) )
      {
        v14 = GetLastError();
        v8 = v14;
        if ( v14 > 0 )
          v8 = (unsigned __int16)v14 | 0x80070000;
      }
    }
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hCertStore);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005a74  mov     [rsp+hCertStore], r8
0x180005a79  push    rbx
0x180005a7a  push    rsi
0x180005a7b  push    rdi
0x180005a7c  push    r14
0x180005a7e  sub     rsp, 38h
0x180005a82  mov     rbx, rdx
0x180005a85  mov     [rsp+58h+hCertStore], 0
0x180005a8e  xor     edx, edx; dwEncodingType
0x180005a90  mov     [rsp+58h+pvPara], 0; pvPara
0x180005a99  mov     r14, r9
0x180005a9c  xor     r8d, r8d; hCryptProv
0x180005a9f  mov     r9d, 2280h; dwFlags
0x180005aa5  lea     ecx, [rdx+2]; lpszStoreProvider
0x180005aa8  call    cs:__imp_CertOpenStore
0x180005aaf  nop     dword ptr [rax+rax+00h]
0x180005ab4  mov     rdx, rax
0x180005ab7  lea     rcx, [rsp+58h+hCertStore]
0x180005abc  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005ac1  cmp     [rsp+58h+hCertStore], 0
0x180005ac7  jnz     short loc_180005AED
0x180005ac9  call    cs:__imp_GetLastError
0x180005ad0  nop     dword ptr [rax+rax+00h]
0x180005ad5  mov     edi, eax
0x180005ad7  test    eax, eax
0x180005ad9  jle     loc_180005BDD
0x180005adf  movzx   edi, ax
0x180005ae2  or      edi, 80070000h
0x180005ae8  jmp     loc_180005BDD
0x180005aed  mov     rcx, [rsp+58h+hCertStore]; hCertStore
0x180005af2  xor     edi, edi
0x180005af4  xor     r9d, r9d; ppStoreContext
0x180005af7  mov     rdx, rbx; pCertContext
0x180005afa  lea     r8d, [rdi+3]; dwAddDisposition
0x180005afe  call    cs:__imp_CertAddCertificateContextToStore
0x180005b05  nop     dword ptr [rax+rax+00h]
0x180005b0a  mov     esi, 80070000h
0x180005b0f  test    eax, eax
0x180005b11  jnz     short loc_180005B32
0x180005b13  call    cs:__imp_GetLastError
0x180005b1a  nop     dword ptr [rax+rax+00h]
0x180005b1f  mov     edi, eax
0x180005b21  test    eax, eax
0x180005b23  jle     short loc_180005B2A
0x180005b25  movzx   edi, ax
0x180005b28  or      edi, esi
0x180005b2a  test    edi, edi
0x180005b2c  js      loc_180005BDD
0x180005b32  mov     rcx, [rsp+58h+hCertStore]; hStore
0x180005b37  lea     r8, szPassword; "{EE9AA8E2-B182-4063-B3CC-F0B6C5DE6489}"
0x180005b3e  xor     r9d, r9d; pvPara
0x180005b41  mov     dword ptr [r14], 0
0x180005b48  mov     rdx, r14; pPFX
0x180005b4b  mov     qword ptr [r14+8], 0
0x180005b53  mov     dword ptr [rsp+58h+pvPara], 16h; dwFlags
0x180005b5b  call    cs:__imp_PFXExportCertStoreEx
0x180005b62  nop     dword ptr [rax+rax+00h]
0x180005b67  cmp     dword ptr [r14], 0
0x180005b6b  jz      short loc_180005BC6
0x180005b6d  mov     ebx, [r14]
0x180005b70  call    cs:__imp_GetProcessHeap
0x180005b77  nop     dword ptr [rax+rax+00h]
0x180005b7c  mov     r8d, ebx; dwBytes
0x180005b7f  mov     edx, 8; dwFlags
0x180005b84  mov     rcx, rax; hHeap
0x180005b87  call    cs:__imp_HeapAlloc
0x180005b8e  nop     dword ptr [rax+rax+00h]
0x180005b93  mov     [r14+8], rax
0x180005b97  test    rax, rax
0x180005b9a  jz      short loc_180005BC6
0x180005b9c  mov     rcx, [rsp+58h+hCertStore]; hStore
0x180005ba1  lea     r8, szPassword; "{EE9AA8E2-B182-4063-B3CC-F0B6C5DE6489}"
0x180005ba8  xor     r9d, r9d; pvPara
0x180005bab  mov     dword ptr [rsp+58h+pvPara], 16h; dwFlags
0x180005bb3  mov     rdx, r14; pPFX
0x180005bb6  call    cs:__imp_PFXExportCertStoreEx
0x180005bbd  nop     dword ptr [rax+rax+00h]
0x180005bc2  test    eax, eax
0x180005bc4  jnz     short loc_180005BDD
0x180005bc6  call    cs:__imp_GetLastError
0x180005bcd  nop     dword ptr [rax+rax+00h]
0x180005bd2  mov     edi, eax
0x180005bd4  test    eax, eax
0x180005bd6  jle     short loc_180005BDD
0x180005bd8  movzx   edi, ax
0x180005bdb  or      edi, esi
0x180005bdd  lea     rcx, [rsp+58h+hCertStore]
0x180005be2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005be7  mov     eax, edi
0x180005be9  add     rsp, 38h
0x180005bed  pop     r14
0x180005bef  pop     rdi
0x180005bf0  pop     rsi
0x180005bf1  pop     rbx
0x180005bf2  retn
```
