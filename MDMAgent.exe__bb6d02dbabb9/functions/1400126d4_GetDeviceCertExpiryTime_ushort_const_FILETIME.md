# GetDeviceCertExpiryTime(ushort const *,_FILETIME *)

- ea: `0x1400126d4`
- end: `0x1400128aa`
- name: `?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x14000829c`

## callees

- `0x1400079f8`
- `0x14000b784`
- `0x1400126d4`
- `0x1400128b0`
- `0x140012d20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001276f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012853`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001276f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012853`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012785`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012785`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012867`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012867`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012884`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012884`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001272b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001272b`
- `DMCmnUtils!DmRevertToSelf` at `0x140012811`
- `DMCmnUtils!DmRevertToSelf` at `0x140012811`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x1400127b9`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x1400127b9`
- `CRYPT32!CertFreeCertificateContext` at `0x14001282c`
- `CRYPT32!CertFreeCertificateContext` at `0x14001282c`
- `CRYPT32!CertCloseStore` at `0x140012842`
- `CRYPT32!CertCloseStore` at `0x140012842`

## pseudocode

```c
__int64 __fastcall GetDeviceCertExpiryTime(unsigned __int16 *a1, struct _FILETIME *a2)
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
    if ( byte_140025804 )
    {
      DmRevertToSelf();
      byte_140025804 = 0;
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
0x1400126d4  mov     [rsp-28h+arg_0], rbx
0x1400126d9  mov     [rsp-28h+arg_8], rsi
0x1400126de  push    rbp
0x1400126df  push    rdi
0x1400126e0  push    r12
0x1400126e2  push    r14
0x1400126e4  push    r15
0x1400126e6  mov     rbp, rsp
0x1400126e9  sub     rsp, 40h
0x1400126ed  xor     edi, edi
0x1400126ef  mov     r15, rcx
0x1400126f2  xor     r14d, r14d
0x1400126f5  mov     [rbp+var_8], rdi
0x1400126f9  mov     r12, rdx
0x1400126fc  mov     [rbp+var_10], r14
0x140012700  mov     dword ptr [rbp+dwBytes], edi
0x140012703  lea     ecx, [rdi+1]
0x140012706  mov     [rbp+hKey], rdi
0x14001270a  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x14001270f  lea     rcx, [rbp+hKey]
0x140012713  mov     r9d, 20019h; samDesired
0x140012719  mov     [rsp+40h+phkResult], rcx; phkResult
0x14001271e  xor     r8d, r8d; ulOptions
0x140012721  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012728  mov     rdx, rax; lpSubKey
0x14001272b  call    cs:__imp_RegOpenKeyExW
0x140012732  nop     dword ptr [rax+rax+00h]
0x140012737  mov     ebx, eax
0x140012739  test    eax, eax
0x14001273b  jle     short loc_140012746
0x14001273d  movzx   ebx, ax
0x140012740  or      ebx, 80070000h
0x140012746  test    ebx, ebx
0x140012748  jns     short loc_140012757
0x14001274a  mov     rcx, [rbp+hKey]
0x14001274e  mov     [rbp+hKey], rdi
0x140012752  jmp     loc_14001287F
0x140012757  xor     esi, esi
0x140012759  lea     rdx, [rbp+dwBytes]; unsigned int *
0x14001275d  lea     ecx, [rsi+54h]; unsigned __int64
0x140012760  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140012765  mov     ebx, eax
0x140012767  test    eax, eax
0x140012769  js      loc_140012808
0x14001276f  call    cs:__imp_GetProcessHeap
0x140012776  nop     dword ptr [rax+rax+00h]
0x14001277b  mov     r8d, dword ptr [rbp+dwBytes]; dwBytes
0x14001277f  lea     edx, [rsi+8]; dwFlags
0x140012782  mov     rcx, rax; hHeap
0x140012785  call    cs:__imp_HeapAlloc
0x14001278c  nop     dword ptr [rax+rax+00h]
0x140012791  mov     rsi, rax
0x140012794  test    rax, rax
0x140012797  jnz     short loc_1400127A0
0x140012799  mov     ebx, 8007000Eh
0x14001279e  jmp     short loc_140012808
0x1400127a0  mov     rcx, [rbp+hKey]
0x1400127a4  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x1400127ab  mov     r9, rsi
0x1400127ae  mov     dword ptr [rsp+40h+phkResult], 2Ah ; '*'; unsigned int *
0x1400127b6  mov     rdx, r15
0x1400127b9  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x1400127c0  nop     dword ptr [rax+rax+00h]
0x1400127c5  mov     ebx, eax
0x1400127c7  test    eax, eax
0x1400127c9  js      short loc_140012808
0x1400127cb  mov     rcx, r15; unsigned __int16 *
0x1400127ce  call    ?ImpersonateForCertAccess@@YAJPEBG@Z; ImpersonateForCertAccess(ushort const *)
0x1400127d3  lea     r8, [rbp+var_8]; struct _CERT_CONTEXT **
0x1400127d7  mov     rcx, rsi; unsigned __int16 *
0x1400127da  lea     rdx, [rbp+var_10]; void **
0x1400127de  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x1400127e3  mov     rdi, [rbp+var_8]
0x1400127e7  mov     ebx, eax
0x1400127e9  mov     r14, [rbp+var_10]
0x1400127ed  test    eax, eax
0x1400127ef  js      short loc_140012808
0x1400127f1  mov     rax, [rdi+18h]
0x1400127f5  mov     ecx, [rax+4Ch]
0x1400127f8  mov     [r12+4], ecx
0x1400127fd  mov     rax, [rdi+18h]
0x140012801  mov     ecx, [rax+48h]
0x140012804  mov     [r12], ecx
0x140012808  cmp     cs:byte_140025804, 0
0x14001280f  jz      short loc_140012824
0x140012811  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x140012818  nop     dword ptr [rax+rax+00h]
0x14001281d  mov     cs:byte_140025804, 0
0x140012824  test    rdi, rdi
0x140012827  jz      short loc_140012838
0x140012829  mov     rcx, rdi; pCertContext
0x14001282c  call    cs:__imp_CertFreeCertificateContext
0x140012833  nop     dword ptr [rax+rax+00h]
0x140012838  test    r14, r14
0x14001283b  jz      short loc_14001284E
0x14001283d  xor     edx, edx; dwFlags
0x14001283f  mov     rcx, r14; hCertStore
0x140012842  call    cs:__imp_CertCloseStore
0x140012849  nop     dword ptr [rax+rax+00h]
0x14001284e  test    rsi, rsi
0x140012851  jz      short loc_140012873
0x140012853  call    cs:__imp_GetProcessHeap
0x14001285a  nop     dword ptr [rax+rax+00h]
0x14001285f  mov     r8, rsi; lpMem
0x140012862  xor     edx, edx; dwFlags
0x140012864  mov     rcx, rax; hHeap
0x140012867  call    cs:__imp_HeapFree
0x14001286e  nop     dword ptr [rax+rax+00h]
0x140012873  mov     rcx, [rbp+hKey]; hKey
0x140012877  mov     [rbp+hKey], 0
0x14001287f  test    rcx, rcx
0x140012882  jz      short loc_140012890
0x140012884  call    cs:__imp_RegCloseKey
0x14001288b  nop     dword ptr [rax+rax+00h]
0x140012890  mov     rsi, [rsp+40h+arg_8]
0x140012895  mov     eax, ebx
0x140012897  mov     rbx, [rsp+40h+arg_0]
0x14001289c  add     rsp, 40h
0x1400128a0  pop     r15
0x1400128a2  pop     r14
0x1400128a4  pop     r12
0x1400128a6  pop     rdi
0x1400128a7  pop     rbp
0x1400128a8  retn
```
