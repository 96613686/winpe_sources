# GetDeviceCertExpiryTime(ushort const *,_FILETIME *)

- ea: `0x1800954f0`
- end: `0x1800956e3`
- name: `?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z`
- size: `499`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800323e8`

## callees

- `0x1800184c0`
- `0x18002a028`
- `0x1800954f0`
- `0x1800956ec`
- `0x180095bb8`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetString` at `0x1800955eb`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x1800955eb`
- `DMCmnUtils!DmRevertToSelf` at `0x180095648`
- `DMCmnUtils!DmRevertToSelf` at `0x180095648`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800955b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800955b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800955a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009568a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800955a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009568a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009569e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009569e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095577`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800956bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095577`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800956bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095547`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095547`
- `CRYPT32!CertCloseStore` at `0x180095679`
- `CRYPT32!CertCloseStore` at `0x180095679`
- `CRYPT32!CertFreeCertificateContext` at `0x180095663`
- `CRYPT32!CertFreeCertificateContext` at `0x180095663`

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
    if ( byte_1800FF444 )
    {
      DmRevertToSelf();
      byte_1800FF444 = 0;
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
0x1800954f0  mov     [rsp-28h+arg_0], rbx
0x1800954f5  mov     [rsp-28h+arg_8], rsi
0x1800954fa  push    rbp
0x1800954fb  push    rdi
0x1800954fc  push    r12
0x1800954fe  push    r14
0x180095500  push    r15
0x180095502  mov     rbp, rsp
0x180095505  sub     rsp, 40h
0x180095509  mov     r12, rdx
0x18009550c  mov     r15, rcx
0x18009550f  xor     r14d, r14d
0x180095512  mov     [rbp+var_10], r14
0x180095516  xor     edi, edi
0x180095518  mov     [rbp+var_8], rdi
0x18009551c  mov     dword ptr [rbp+dwBytes], edi
0x18009551f  mov     [rbp+hKey], rdi
0x180095523  lea     ecx, [rdi+1]
0x180095526  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18009552b  lea     rcx, [rbp+hKey]
0x18009552f  mov     [rsp+40h+phkResult], rcx; phkResult
0x180095534  mov     r9d, 20019h; samDesired
0x18009553a  xor     r8d, r8d; ulOptions
0x18009553d  mov     rdx, rax; lpSubKey
0x180095540  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180095547  call    cs:__imp_RegOpenKeyExW
0x18009554e  nop     dword ptr [rax+rax+00h]
0x180095553  mov     ebx, eax
0x180095555  test    eax, eax
0x180095557  jle     short loc_180095562
0x180095559  movzx   ebx, ax
0x18009555c  or      ebx, 80070000h
0x180095562  test    ebx, ebx
0x180095564  jns     short loc_180095589
0x180095566  mov     rcx, [rbp+hKey]; hKey
0x18009556a  mov     [rbp+hKey], 0
0x180095572  test    rcx, rcx
0x180095575  jz      short loc_180095584
0x180095577  call    cs:__imp_RegCloseKey
0x18009557e  nop     dword ptr [rax+rax+00h]
0x180095583  nop
0x180095584  jmp     loc_1800956C9
0x180095589  xor     esi, esi
0x18009558b  lea     rdx, [rbp+dwBytes]; unsigned int *
0x18009558f  lea     ecx, [rsi+54h]; unsigned __int64
0x180095592  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180095597  mov     ebx, eax
0x180095599  test    eax, eax
0x18009559b  js      loc_18009563F
0x1800955a1  call    cs:__imp_GetProcessHeap
0x1800955a8  nop     dword ptr [rax+rax+00h]
0x1800955ad  mov     r8d, dword ptr [rbp+dwBytes]; dwBytes
0x1800955b1  lea     edx, [rsi+8]; dwFlags
0x1800955b4  mov     rcx, rax; hHeap
0x1800955b7  call    cs:__imp_HeapAlloc
0x1800955be  nop     dword ptr [rax+rax+00h]
0x1800955c3  mov     rsi, rax
0x1800955c6  test    rax, rax
0x1800955c9  jnz     short loc_1800955D2
0x1800955cb  mov     ebx, 8007000Eh
0x1800955d0  jmp     short loc_18009563F
0x1800955d2  mov     dword ptr [rsp+40h+phkResult], 2Ah ; '*'
0x1800955da  mov     r9, rsi
0x1800955dd  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x1800955e4  mov     rdx, r15
0x1800955e7  mov     rcx, [rbp+hKey]
0x1800955eb  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x1800955f2  nop     dword ptr [rax+rax+00h]
0x1800955f7  mov     ebx, eax
0x1800955f9  test    eax, eax
0x1800955fb  js      short loc_18009563F
0x1800955fd  mov     rcx, r15; unsigned __int16 *
0x180095600  call    ?ImpersonateForCertAccess@@YAJPEBG@Z; ImpersonateForCertAccess(ushort const *)
0x180095605  mov     [rsp+40h+phkResult], rdi; unsigned int *
0x18009560a  lea     r8, [rbp+var_8]; struct _CERT_CONTEXT **
0x18009560e  lea     rdx, [rbp+var_10]; void **
0x180095612  mov     rcx, rsi; unsigned __int16 *
0x180095615  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x18009561a  mov     ebx, eax
0x18009561c  mov     rdi, [rbp+var_8]
0x180095620  mov     r14, [rbp+var_10]
0x180095624  test    eax, eax
0x180095626  js      short loc_18009563F
0x180095628  mov     rax, [rdi+18h]
0x18009562c  mov     ecx, [rax+4Ch]
0x18009562f  mov     [r12+4], ecx
0x180095634  mov     rax, [rdi+18h]
0x180095638  mov     ecx, [rax+48h]
0x18009563b  mov     [r12], ecx
0x18009563f  cmp     cs:byte_1800FF444, 0
0x180095646  jz      short loc_18009565B
0x180095648  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18009564f  nop     dword ptr [rax+rax+00h]
0x180095654  mov     cs:byte_1800FF444, 0
0x18009565b  test    rdi, rdi
0x18009565e  jz      short loc_18009566F
0x180095660  mov     rcx, rdi; pCertContext
0x180095663  call    cs:__imp_CertFreeCertificateContext
0x18009566a  nop     dword ptr [rax+rax+00h]
0x18009566f  test    r14, r14
0x180095672  jz      short loc_180095685
0x180095674  xor     edx, edx; dwFlags
0x180095676  mov     rcx, r14; hCertStore
0x180095679  call    cs:__imp_CertCloseStore
0x180095680  nop     dword ptr [rax+rax+00h]
0x180095685  test    rsi, rsi
0x180095688  jz      short loc_1800956AB
0x18009568a  call    cs:__imp_GetProcessHeap
0x180095691  nop     dword ptr [rax+rax+00h]
0x180095696  mov     rcx, rax; hHeap
0x180095699  mov     r8, rsi; lpMem
0x18009569c  xor     edx, edx; dwFlags
0x18009569e  call    cs:__imp_HeapFree
0x1800956a5  nop     dword ptr [rax+rax+00h]
0x1800956aa  nop
0x1800956ab  mov     rcx, [rbp+hKey]; hKey
0x1800956af  mov     [rbp+hKey], 0
0x1800956b7  test    rcx, rcx
0x1800956ba  jz      short loc_1800956C9
0x1800956bc  call    cs:__imp_RegCloseKey
0x1800956c3  nop     dword ptr [rax+rax+00h]
0x1800956c8  nop
0x1800956c9  mov     eax, ebx
0x1800956cb  mov     rbx, [rsp+40h+arg_0]
0x1800956d0  mov     rsi, [rsp+40h+arg_8]
0x1800956d5  add     rsp, 40h
0x1800956d9  pop     r15
0x1800956db  pop     r14
0x1800956dd  pop     r12
0x1800956df  pop     rdi
0x1800956e0  pop     rbp
0x1800956e1  retn
```
