# GetDeviceCertExpiryTime(ushort const *,_FILETIME *)

- ea: `0x140011eb4`
- end: `0x14001204d`
- name: `?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z`
- size: `409`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x140007f34`

## callees

- `0x140007724`
- `0x14000b288`
- `0x140011eb4`
- `0x140012054`
- `0x140012458`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011f49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012009`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011f49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012009`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140011f59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140011f59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012017`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012017`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001202e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001202e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011f0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011f0b`
- `DMCmnUtils!DmRevertToSelf` at `0x140011fd9`
- `DMCmnUtils!DmRevertToSelf` at `0x140011fd9`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x140011f87`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x140011f87`
- `CRYPT32!CertFreeCertificateContext` at `0x140011fee`
- `CRYPT32!CertFreeCertificateContext` at `0x140011fee`
- `CRYPT32!CertCloseStore` at `0x140011ffe`
- `CRYPT32!CertCloseStore` at `0x140011ffe`

## pseudocode

```c
__int64 __fastcall GetDeviceCertExpiryTime(const unsigned __int16 *a1, struct _FILETIME *a2)
{
  struct _CERT_CONTEXT *v2; // rdi
  void *v4; // r14
  const WCHAR *v6; // rax
  LSTATUS v7; // eax
  signed int String; // ebx
  HKEY v9; // rcx
  unsigned __int16 *v10; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v12; // rax
  int v13; // r9d
  int InstalledCert; // eax
  HANDLE v15; // rax
  unsigned int *phkResult; // [rsp+20h] [rbp-20h]
  void *v18; // [rsp+30h] [rbp-10h] BYREF
  struct _CERT_CONTEXT *v19; // [rsp+38h] [rbp-8h] BYREF
  SIZE_T dwBytes; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  v2 = 0;
  v4 = 0;
  v19 = 0;
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
          InstalledCert = GetInstalledCert(v10, &v18, (const struct _CERT_CONTEXT **)&v19, v13, phkResult);
          v2 = v19;
          String = InstalledCert;
          v4 = v18;
          if ( InstalledCert >= 0 )
          {
            a2->dwHighDateTime = v19->pCertInfo->NotAfter.dwHighDateTime;
            a2->dwLowDateTime = v2->pCertInfo->NotAfter.dwLowDateTime;
          }
        }
      }
      else
      {
        String = -2147024882;
      }
    }
    if ( byte_140024704 )
    {
      DmRevertToSelf();
      byte_140024704 = 0;
    }
    if ( v2 )
      CertFreeCertificateContext(v2);
    if ( v4 )
      CertCloseStore(v4, 0);
    if ( v10 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v10);
    }
    v9 = hKey;
    hKey = 0;
  }
  else
  {
    v9 = hKey;
    hKey = 0;
  }
  if ( v9 )
    RegCloseKey(v9);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x140011eb4  mov     [rsp-28h+arg_0], rbx
0x140011eb9  mov     [rsp-28h+arg_8], rsi
0x140011ebe  push    rbp
0x140011ebf  push    rdi
0x140011ec0  push    r12
0x140011ec2  push    r14
0x140011ec4  push    r15
0x140011ec6  mov     rbp, rsp
0x140011ec9  sub     rsp, 40h
0x140011ecd  xor     edi, edi
0x140011ecf  mov     r15, rcx
0x140011ed2  xor     r14d, r14d
0x140011ed5  mov     [rbp+var_8], rdi
0x140011ed9  mov     r12, rdx
0x140011edc  mov     [rbp+var_10], r14
0x140011ee0  mov     dword ptr [rbp+dwBytes], edi
0x140011ee3  lea     ecx, [rdi+1]
0x140011ee6  mov     [rbp+hKey], rdi
0x140011eea  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x140011eef  lea     rcx, [rbp+hKey]
0x140011ef3  mov     r9d, 20019h; samDesired
0x140011ef9  mov     [rsp+40h+phkResult], rcx; phkResult
0x140011efe  xor     r8d, r8d; ulOptions
0x140011f01  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140011f08  mov     rdx, rax; lpSubKey
0x140011f0b  call    cs:__imp_RegOpenKeyExW
0x140011f11  mov     ebx, eax
0x140011f13  test    eax, eax
0x140011f15  jle     short loc_140011F20
0x140011f17  movzx   ebx, ax
0x140011f1a  or      ebx, 80070000h
0x140011f20  test    ebx, ebx
0x140011f22  jns     short loc_140011F31
0x140011f24  mov     rcx, [rbp+hKey]
0x140011f28  mov     [rbp+hKey], rdi
0x140011f2c  jmp     loc_140012029
0x140011f31  xor     esi, esi
0x140011f33  lea     rdx, [rbp+dwBytes]; unsigned int *
0x140011f37  lea     ecx, [rsi+54h]; unsigned __int64
0x140011f3a  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140011f3f  mov     ebx, eax
0x140011f41  test    eax, eax
0x140011f43  js      loc_140011FD0
0x140011f49  call    cs:__imp_GetProcessHeap
0x140011f4f  mov     r8d, dword ptr [rbp+dwBytes]; dwBytes
0x140011f53  lea     edx, [rsi+8]; dwFlags
0x140011f56  mov     rcx, rax; hHeap
0x140011f59  call    cs:__imp_HeapAlloc
0x140011f5f  mov     rsi, rax
0x140011f62  test    rax, rax
0x140011f65  jnz     short loc_140011F6E
0x140011f67  mov     ebx, 8007000Eh
0x140011f6c  jmp     short loc_140011FD0
0x140011f6e  mov     rcx, [rbp+hKey]
0x140011f72  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x140011f79  mov     r9, rsi
0x140011f7c  mov     dword ptr [rsp+40h+phkResult], 2Ah ; '*'; unsigned int *
0x140011f84  mov     rdx, r15
0x140011f87  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x140011f8d  mov     ebx, eax
0x140011f8f  test    eax, eax
0x140011f91  js      short loc_140011FD0
0x140011f93  mov     rcx, r15; unsigned __int16 *
0x140011f96  call    ?ImpersonateForCertAccess@@YAJPEBG@Z; ImpersonateForCertAccess(ushort const *)
0x140011f9b  lea     r8, [rbp+var_8]; struct _CERT_CONTEXT **
0x140011f9f  mov     rcx, rsi; unsigned __int16 *
0x140011fa2  lea     rdx, [rbp+var_10]; void **
0x140011fa6  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x140011fab  mov     rdi, [rbp+var_8]
0x140011faf  mov     ebx, eax
0x140011fb1  mov     r14, [rbp+var_10]
0x140011fb5  test    eax, eax
0x140011fb7  js      short loc_140011FD0
0x140011fb9  mov     rax, [rdi+18h]
0x140011fbd  mov     ecx, [rax+4Ch]
0x140011fc0  mov     [r12+4], ecx
0x140011fc5  mov     rax, [rdi+18h]
0x140011fc9  mov     ecx, [rax+48h]
0x140011fcc  mov     [r12], ecx
0x140011fd0  cmp     cs:byte_140024704, 0
0x140011fd7  jz      short loc_140011FE6
0x140011fd9  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x140011fdf  mov     cs:byte_140024704, 0
0x140011fe6  test    rdi, rdi
0x140011fe9  jz      short loc_140011FF4
0x140011feb  mov     rcx, rdi; pCertContext
0x140011fee  call    cs:__imp_CertFreeCertificateContext
0x140011ff4  test    r14, r14
0x140011ff7  jz      short loc_140012004
0x140011ff9  xor     edx, edx; dwFlags
0x140011ffb  mov     rcx, r14; hCertStore
0x140011ffe  call    cs:__imp_CertCloseStore
0x140012004  test    rsi, rsi
0x140012007  jz      short loc_14001201D
0x140012009  call    cs:__imp_GetProcessHeap
0x14001200f  mov     r8, rsi; lpMem
0x140012012  xor     edx, edx; dwFlags
0x140012014  mov     rcx, rax; hHeap
0x140012017  call    cs:__imp_HeapFree
0x14001201d  mov     rcx, [rbp+hKey]; hKey
0x140012021  mov     [rbp+hKey], 0
0x140012029  test    rcx, rcx
0x14001202c  jz      short loc_140012034
0x14001202e  call    cs:__imp_RegCloseKey
0x140012034  mov     rsi, [rsp+40h+arg_8]
0x140012039  mov     eax, ebx
0x14001203b  mov     rbx, [rsp+40h+arg_0]
0x140012040  add     rsp, 40h
0x140012044  pop     r15
0x140012046  pop     r14
0x140012048  pop     r12
0x14001204a  pop     rdi
0x14001204b  pop     rbp
0x14001204c  retn
```
