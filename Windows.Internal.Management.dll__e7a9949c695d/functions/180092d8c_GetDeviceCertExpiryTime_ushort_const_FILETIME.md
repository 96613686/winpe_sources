# GetDeviceCertExpiryTime(ushort const *,_FILETIME *)

- ea: `0x180092d8c`
- end: `0x180092f3c`
- name: `?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x180033584`

## callees

- `0x180019ae4`
- `0x18002b664`
- `0x180092d8c`
- `0x180092f44`
- `0x180093398`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetString` at `0x180092e6f`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180092e6f`
- `DMCmnUtils!DmRevertToSelf` at `0x180092ec6`
- `DMCmnUtils!DmRevertToSelf` at `0x180092ec6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180092f04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180092f04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092e41`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092e41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092e31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092ef6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092e31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092ef6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092e0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092f1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092e0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092f1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180092de3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180092de3`
- `CRYPT32!CertCloseStore` at `0x180092eeb`
- `CRYPT32!CertCloseStore` at `0x180092eeb`
- `CRYPT32!CertFreeCertificateContext` at `0x180092edb`
- `CRYPT32!CertFreeCertificateContext` at `0x180092edb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetDeviceCertExpiryTime(unsigned __int16 *a1, struct _FILETIME *a2)
{
  void *v4; // r14
  struct _CERT_CONTEXT *v5; // rdi
  const WCHAR *v6; // rax
  LSTATUS v7; // eax
  signed int String; // ebx
  HKEY v9; // rcx
  unsigned __int16 *v10; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v12; // rax
  int v13; // r9d
  HANDLE v14; // rax
  HKEY v15; // rcx
  void *v17; // [rsp+30h] [rbp-10h] BYREF
  struct _CERT_CONTEXT *v18; // [rsp+38h] [rbp-8h] BYREF
  SIZE_T dwBytes; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  v4 = 0;
  v17 = 0;
  v5 = 0;
  v18 = 0;
  LODWORD(dwBytes) = 0;
  hKey = 0;
  v6 = (const WCHAR *)DMGetKnownRegPath(1);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey);
  String = v7;
  if ( v7 > 0 )
    String = (unsigned __int16)v7 | 0x80070000;
  if ( String >= 0 )
  {
    v10 = 0;
    String = ULongLongToULong(0x54u, (unsigned int *)&dwBytes);
    if ( String >= 0 )
    {
      ProcessHeap = GetProcessHeap();
      v12 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, (unsigned int)dwBytes);
      v10 = v12;
      if ( v12 )
      {
        String = OmaDmRegistryGetString(hKey, a1, L"DMPCertThumbPrint", v12, 0x2Au);
        if ( String >= 0 )
        {
          ImpersonateForCertAccess(a1);
          String = GetInstalledCert(v10, &v17, (const struct _CERT_CONTEXT **)&v18, v13, 0);
          v5 = v18;
          v4 = v17;
          if ( String >= 0 )
          {
            a2->dwHighDateTime = v18->pCertInfo->NotAfter.dwHighDateTime;
            a2->dwLowDateTime = v5->pCertInfo->NotAfter.dwLowDateTime;
          }
        }
      }
      else
      {
        String = -2147024882;
      }
    }
    if ( byte_1800FB484 )
    {
      DmRevertToSelf();
      byte_1800FB484 = 0;
    }
    if ( v5 )
      CertFreeCertificateContext(v5);
    if ( v4 )
      CertCloseStore(v4, 0);
    if ( v10 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v10);
    }
    v15 = hKey;
    hKey = 0;
    if ( v15 )
      RegCloseKey(v15);
  }
  else
  {
    v9 = hKey;
    hKey = 0;
    if ( v9 )
      RegCloseKey(v9);
  }
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180092d8c  mov     [rsp-28h+arg_0], rbx
0x180092d91  mov     [rsp-28h+arg_8], rsi
0x180092d96  push    rbp
0x180092d97  push    rdi
0x180092d98  push    r12
0x180092d9a  push    r14
0x180092d9c  push    r15
0x180092d9e  mov     rbp, rsp
0x180092da1  sub     rsp, 40h
0x180092da5  mov     r12, rdx
0x180092da8  mov     r15, rcx
0x180092dab  xor     r14d, r14d
0x180092dae  mov     [rbp+var_10], r14
0x180092db2  xor     edi, edi
0x180092db4  mov     [rbp+var_8], rdi
0x180092db8  mov     dword ptr [rbp+dwBytes], edi
0x180092dbb  mov     [rbp+hKey], rdi
0x180092dbf  lea     ecx, [rdi+1]
0x180092dc2  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180092dc7  lea     rcx, [rbp+hKey]
0x180092dcb  mov     [rsp+40h+phkResult], rcx; phkResult
0x180092dd0  mov     r9d, 20019h; samDesired
0x180092dd6  xor     r8d, r8d; ulOptions
0x180092dd9  mov     rdx, rax; lpSubKey
0x180092ddc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180092de3  call    cs:__imp_RegOpenKeyExW
0x180092de9  mov     ebx, eax
0x180092deb  test    eax, eax
0x180092ded  jle     short loc_180092DF8
0x180092def  movzx   ebx, ax
0x180092df2  or      ebx, 80070000h
0x180092df8  test    ebx, ebx
0x180092dfa  jns     short loc_180092E19
0x180092dfc  mov     rcx, [rbp+hKey]; hKey
0x180092e00  mov     [rbp+hKey], 0
0x180092e08  test    rcx, rcx
0x180092e0b  jz      short loc_180092E14
0x180092e0d  call    cs:__imp_RegCloseKey
0x180092e13  nop
0x180092e14  jmp     loc_180092F23
0x180092e19  xor     esi, esi
0x180092e1b  lea     rdx, [rbp+dwBytes]; unsigned int *
0x180092e1f  lea     ecx, [rsi+54h]; unsigned __int64
0x180092e22  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180092e27  mov     ebx, eax
0x180092e29  test    eax, eax
0x180092e2b  js      loc_180092EBD
0x180092e31  call    cs:__imp_GetProcessHeap
0x180092e37  mov     r8d, dword ptr [rbp+dwBytes]; dwBytes
0x180092e3b  lea     edx, [rsi+8]; dwFlags
0x180092e3e  mov     rcx, rax; hHeap
0x180092e41  call    cs:__imp_HeapAlloc
0x180092e47  mov     rsi, rax
0x180092e4a  test    rax, rax
0x180092e4d  jnz     short loc_180092E56
0x180092e4f  mov     ebx, 8007000Eh
0x180092e54  jmp     short loc_180092EBD
0x180092e56  mov     dword ptr [rsp+40h+phkResult], 2Ah ; '*'
0x180092e5e  mov     r9, rsi
0x180092e61  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x180092e68  mov     rdx, r15
0x180092e6b  mov     rcx, [rbp+hKey]
0x180092e6f  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x180092e75  mov     ebx, eax
0x180092e77  test    eax, eax
0x180092e79  js      short loc_180092EBD
0x180092e7b  mov     rcx, r15; unsigned __int16 *
0x180092e7e  call    ?ImpersonateForCertAccess@@YAJPEBG@Z; ImpersonateForCertAccess(ushort const *)
0x180092e83  mov     [rsp+40h+phkResult], rdi; unsigned int *
0x180092e88  lea     r8, [rbp+var_8]; struct _CERT_CONTEXT **
0x180092e8c  lea     rdx, [rbp+var_10]; void **
0x180092e90  mov     rcx, rsi; unsigned __int16 *
0x180092e93  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x180092e98  mov     ebx, eax
0x180092e9a  mov     rdi, [rbp+var_8]
0x180092e9e  mov     r14, [rbp+var_10]
0x180092ea2  test    eax, eax
0x180092ea4  js      short loc_180092EBD
0x180092ea6  mov     rax, [rdi+18h]
0x180092eaa  mov     ecx, [rax+4Ch]
0x180092ead  mov     [r12+4], ecx
0x180092eb2  mov     rax, [rdi+18h]
0x180092eb6  mov     ecx, [rax+48h]
0x180092eb9  mov     [r12], ecx
0x180092ebd  cmp     cs:byte_1800FB484, 0
0x180092ec4  jz      short loc_180092ED3
0x180092ec6  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180092ecc  mov     cs:byte_1800FB484, 0
0x180092ed3  test    rdi, rdi
0x180092ed6  jz      short loc_180092EE1
0x180092ed8  mov     rcx, rdi; pCertContext
0x180092edb  call    cs:__imp_CertFreeCertificateContext
0x180092ee1  test    r14, r14
0x180092ee4  jz      short loc_180092EF1
0x180092ee6  xor     edx, edx; dwFlags
0x180092ee8  mov     rcx, r14; hCertStore
0x180092eeb  call    cs:__imp_CertCloseStore
0x180092ef1  test    rsi, rsi
0x180092ef4  jz      short loc_180092F0B
0x180092ef6  call    cs:__imp_GetProcessHeap
0x180092efc  mov     rcx, rax; hHeap
0x180092eff  mov     r8, rsi; lpMem
0x180092f02  xor     edx, edx; dwFlags
0x180092f04  call    cs:__imp_HeapFree
0x180092f0a  nop
0x180092f0b  mov     rcx, [rbp+hKey]; hKey
0x180092f0f  mov     [rbp+hKey], 0
0x180092f17  test    rcx, rcx
0x180092f1a  jz      short loc_180092F23
0x180092f1c  call    cs:__imp_RegCloseKey
0x180092f22  nop
0x180092f23  mov     eax, ebx
0x180092f25  mov     rbx, [rsp+40h+arg_0]
0x180092f2a  mov     rsi, [rsp+40h+arg_8]
0x180092f2f  add     rsp, 40h
0x180092f33  pop     r15
0x180092f35  pop     r14
0x180092f37  pop     r12
0x180092f39  pop     rdi
0x180092f3a  pop     rbp
0x180092f3b  retn
```
