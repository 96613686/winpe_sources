# GetDeviceCertExpiryTime(ushort const *,_FILETIME *)

- ea: `0x180005bfc`
- end: `0x180005dbc`
- name: `?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x180004168`

## callees

- `0x180005a38`
- `0x180005bfc`
- `0x180005dc4`
- `0x18000620c`
- `0x180006574`
- `0x180012bac`
- `0x180017368`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d78`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ca4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ca4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d64`
- `CRYPT32!CertFreeCertificateContext` at `0x180005d3d`
- `CRYPT32!CertFreeCertificateContext` at `0x180005d3d`
- `CRYPT32!CertCloseStore` at `0x180005d53`
- `CRYPT32!CertCloseStore` at `0x180005d53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005c53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005c53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005d96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005d96`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetDeviceCertExpiryTime(const unsigned __int16 *a1, struct _FILETIME *a2)
{
  void *v4; // r14
  struct _CERT_CONTEXT *v5; // rdi
  const WCHAR *v6; // rax
  LSTATUS v7; // eax
  int String; // ebx
  unsigned __int16 *v9; // rsi
  HANDLE ProcessHeap; // rax
  BYTE *v11; // rax
  int v12; // r9d
  HANDLE v13; // rax
  HKEY v14; // rcx
  bool v15; // zf
  unsigned int *phkResult; // [rsp+20h] [rbp-20h]
  void *v18; // [rsp+30h] [rbp-10h] BYREF
  struct _CERT_CONTEXT *v19; // [rsp+38h] [rbp-8h] BYREF
  SIZE_T dwBytes; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  v4 = 0;
  v18 = 0;
  v5 = 0;
  v19 = 0;
  LODWORD(dwBytes) = 0;
  hKey = 0;
  v6 = (const WCHAR *)DMGetKnownRegPath(1);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey);
  String = v7;
  if ( v7 > 0 )
    String = (unsigned __int16)v7 | 0x80070000;
  if ( String >= 0 )
  {
    v9 = 0;
    String = ULongLongToULong(0x54u, (unsigned int *)&dwBytes);
    if ( String >= 0 )
    {
      ProcessHeap = GetProcessHeap();
      v11 = (BYTE *)HeapAlloc(ProcessHeap, 8u, (unsigned int)dwBytes);
      v9 = (unsigned __int16 *)v11;
      if ( v11 )
      {
        String = OmaDmRegistryGetString(hKey, a1, L"DMPCertThumbPrint", v11, 0x2Au);
        if ( String >= 0 )
        {
          ImpersonateForCertAccess(a1);
          String = GetInstalledCert(v9, &v18, (const struct _CERT_CONTEXT **)&v19, v12, phkResult);
          v5 = v19;
          v4 = v18;
          if ( String >= 0 )
          {
            a2->dwHighDateTime = v19->pCertInfo->NotAfter.dwHighDateTime;
            a2->dwLowDateTime = v5->pCertInfo->NotAfter.dwLowDateTime;
          }
        }
      }
      else
      {
        String = -2147024882;
      }
    }
    if ( byte_180029A38 )
    {
      DmRevertToSelf();
      byte_180029A38 = 0;
    }
    if ( v5 )
      CertFreeCertificateContext(v5);
    if ( v4 )
      CertCloseStore(v4, 0);
    if ( v9 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v9);
    }
  }
  v14 = hKey;
  v15 = hKey == 0;
  hKey = 0;
  if ( !v15 )
    RegCloseKey(v14);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180005bfc  mov     [rsp-28h+arg_0], rbx
0x180005c01  mov     [rsp-28h+arg_8], rsi
0x180005c06  push    rbp
0x180005c07  push    rdi
0x180005c08  push    r12
0x180005c0a  push    r14
0x180005c0c  push    r15
0x180005c0e  mov     rbp, rsp
0x180005c11  sub     rsp, 40h
0x180005c15  mov     r12, rdx
0x180005c18  mov     r15, rcx
0x180005c1b  xor     r14d, r14d
0x180005c1e  mov     [rbp+var_10], r14
0x180005c22  xor     edi, edi
0x180005c24  mov     [rbp+var_8], rdi
0x180005c28  mov     dword ptr [rbp+dwBytes], edi
0x180005c2b  mov     [rbp+hKey], rdi
0x180005c2f  lea     ecx, [rdi+1]
0x180005c32  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180005c37  lea     rcx, [rbp+hKey]
0x180005c3b  mov     [rsp+40h+phkResult], rcx; phkResult
0x180005c40  mov     r9d, 20019h; samDesired
0x180005c46  xor     r8d, r8d; ulOptions
0x180005c49  mov     rdx, rax; lpSubKey
0x180005c4c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005c53  call    cs:__imp_RegOpenKeyExW
0x180005c5a  nop     dword ptr [rax+rax+00h]
0x180005c5f  mov     ebx, eax
0x180005c61  test    eax, eax
0x180005c63  jle     short loc_180005C6E
0x180005c65  movzx   ebx, ax
0x180005c68  or      ebx, 80070000h
0x180005c6e  test    ebx, ebx
0x180005c70  js      loc_180005D85
0x180005c76  xor     esi, esi
0x180005c78  lea     rdx, [rbp+dwBytes]; unsigned int *
0x180005c7c  lea     ecx, [rsi+54h]; unsigned __int64
0x180005c7f  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180005c84  mov     ebx, eax
0x180005c86  test    eax, eax
0x180005c88  js      loc_180005D20
0x180005c8e  call    cs:__imp_GetProcessHeap
0x180005c95  nop     dword ptr [rax+rax+00h]
0x180005c9a  mov     r8d, dword ptr [rbp+dwBytes]; dwBytes
0x180005c9e  lea     edx, [rsi+8]; dwFlags
0x180005ca1  mov     rcx, rax; hHeap
0x180005ca4  call    cs:__imp_HeapAlloc
0x180005cab  nop     dword ptr [rax+rax+00h]
0x180005cb0  mov     rsi, rax
0x180005cb3  test    rax, rax
0x180005cb6  jnz     short loc_180005CBF
0x180005cb8  mov     ebx, 8007000Eh
0x180005cbd  jmp     short loc_180005D20
0x180005cbf  mov     dword ptr [rsp+40h+phkResult], 2Ah ; '*'; unsigned int *
0x180005cc7  mov     r9, rsi; unsigned __int16 *
0x180005cca  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x180005cd1  mov     rdx, r15; unsigned __int16 *
0x180005cd4  mov     rcx, [rbp+hKey]; HKEY
0x180005cd8  call    ?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x180005cdd  mov     ebx, eax
0x180005cdf  test    eax, eax
0x180005ce1  js      short loc_180005D20
0x180005ce3  mov     rcx, r15; unsigned __int16 *
0x180005ce6  call    ?ImpersonateForCertAccess@@YAJPEBG@Z; ImpersonateForCertAccess(ushort const *)
0x180005ceb  lea     r8, [rbp+var_8]; struct _CERT_CONTEXT **
0x180005cef  lea     rdx, [rbp+var_10]; void **
0x180005cf3  mov     rcx, rsi; unsigned __int16 *
0x180005cf6  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x180005cfb  mov     ebx, eax
0x180005cfd  mov     rdi, [rbp+var_8]
0x180005d01  mov     r14, [rbp+var_10]
0x180005d05  test    eax, eax
0x180005d07  js      short loc_180005D20
0x180005d09  mov     rax, [rdi+18h]
0x180005d0d  mov     ecx, [rax+4Ch]
0x180005d10  mov     [r12+4], ecx
0x180005d15  mov     rax, [rdi+18h]
0x180005d19  mov     ecx, [rax+48h]
0x180005d1c  mov     [r12], ecx
0x180005d20  cmp     cs:byte_180029A38, 0
0x180005d27  jz      short loc_180005D35
0x180005d29  call    ?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180005d2e  mov     cs:byte_180029A38, 0
0x180005d35  test    rdi, rdi
0x180005d38  jz      short loc_180005D49
0x180005d3a  mov     rcx, rdi; pCertContext
0x180005d3d  call    cs:__imp_CertFreeCertificateContext
0x180005d44  nop     dword ptr [rax+rax+00h]
0x180005d49  test    r14, r14
0x180005d4c  jz      short loc_180005D5F
0x180005d4e  xor     edx, edx; dwFlags
0x180005d50  mov     rcx, r14; hCertStore
0x180005d53  call    cs:__imp_CertCloseStore
0x180005d5a  nop     dword ptr [rax+rax+00h]
0x180005d5f  test    rsi, rsi
0x180005d62  jz      short loc_180005D85
0x180005d64  call    cs:__imp_GetProcessHeap
0x180005d6b  nop     dword ptr [rax+rax+00h]
0x180005d70  mov     rcx, rax; hHeap
0x180005d73  mov     r8, rsi; lpMem
0x180005d76  xor     edx, edx; dwFlags
0x180005d78  call    cs:__imp_HeapFree
0x180005d7f  nop     dword ptr [rax+rax+00h]
0x180005d84  nop
0x180005d85  mov     rcx, [rbp+hKey]; hKey
0x180005d89  test    rcx, rcx
0x180005d8c  mov     [rbp+hKey], 0
0x180005d94  jz      short loc_180005DA2
0x180005d96  call    cs:__imp_RegCloseKey
0x180005d9d  nop     dword ptr [rax+rax+00h]
0x180005da2  mov     eax, ebx
0x180005da4  mov     rbx, [rsp+40h+arg_0]
0x180005da9  mov     rsi, [rsp+40h+arg_8]
0x180005dae  add     rsp, 40h
0x180005db2  pop     r15
0x180005db4  pop     r14
0x180005db6  pop     r12
0x180005db8  pop     rdi
0x180005db9  pop     rbp
0x180005dba  retn
```
