# GetDeviceCertExpiryTime(ushort const *,_FILETIME *)

- ea: `0x1400516ec`
- end: `0x140051874`
- name: `?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x14002c1b0`

## callees

- `0x1400516ec`
- `0x14005187c`
- `0x140051c68`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetString` at `0x1400517b4`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x1400517b4`
- `DMCmnUtils!DmRevertToSelf` at `0x140051800`
- `DMCmnUtils!DmRevertToSelf` at `0x140051800`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14005171c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14005171c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005183e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005183e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140051786`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140051786`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140051774`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140051830`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140051774`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140051830`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005174e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005174e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051855`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051855`
- `CRYPT32!CertFreeCertificateContext` at `0x140051815`
- `CRYPT32!CertFreeCertificateContext` at `0x140051815`
- `CRYPT32!CertCloseStore` at `0x140051825`
- `CRYPT32!CertCloseStore` at `0x140051825`

## pseudocode

```c
__int64 __fastcall GetDeviceCertExpiryTime(unsigned __int16 *a1, struct _FILETIME *a2)
{
  struct _CERT_CONTEXT *v2; // rdi
  void *v3; // r14
  char IsStateSeparationEnabled; // al
  LSTATUS v7; // eax
  signed int String; // ebx
  HKEY v9; // rcx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rsi
  int v13; // r9d
  int InstalledCert; // eax
  HANDLE v15; // rax
  unsigned int *phkResult; // [rsp+20h] [rbp-20h]
  struct _CERT_CONTEXT *v18; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+40h] BYREF
  void *v20; // [rsp+88h] [rbp+48h] BYREF

  v2 = 0;
  v3 = 0;
  v20 = 0;
  v18 = 0;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)off_14005EF50 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         0,
         0x20019u,
         &hKey);
  String = v7;
  if ( v7 > 0 )
    String = (unsigned __int16)v7 | 0x80070000;
  if ( String >= 0 )
  {
    ProcessHeap = GetProcessHeap();
    v11 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x54u);
    v12 = v11;
    if ( v11 )
    {
      String = OmaDmRegistryGetString(hKey, a1, L"DMPCertThumbPrint", v11, 0x2Au);
      if ( String >= 0 )
      {
        ImpersonateForCertAccess(a1);
        InstalledCert = GetInstalledCert(v12, &v20, (const struct _CERT_CONTEXT **)&v18, v13, phkResult);
        v2 = v18;
        String = InstalledCert;
        v3 = v20;
        if ( InstalledCert >= 0 )
          *a2 = v18->pCertInfo->NotAfter;
      }
    }
    else
    {
      String = -2147024882;
    }
    if ( byte_14007E5F8 )
    {
      DmRevertToSelf();
      byte_14007E5F8 = 0;
    }
    if ( v2 )
      CertFreeCertificateContext(v2);
    if ( v3 )
      CertCloseStore(v3, 0);
    if ( v12 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v12);
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
0x1400516ec  mov     [rsp-28h+arg_0], rbx
0x1400516f1  mov     [rsp-28h+arg_8], rsi
0x1400516f6  push    rbp
0x1400516f7  push    rdi
0x1400516f8  push    r12
0x1400516fa  push    r14
0x1400516fc  push    r15
0x1400516fe  mov     rbp, rsp
0x140051701  sub     rsp, 40h
0x140051705  xor     edi, edi
0x140051707  xor     r14d, r14d
0x14005170a  mov     [rbp+arg_18], r14
0x14005170e  mov     r15, rdx
0x140051711  mov     [rbp+var_10], rdi
0x140051715  mov     r12, rcx
0x140051718  mov     [rbp+hKey], rdi
0x14005171c  call    cs:__imp_RtlIsStateSeparationEnabled
0x140051722  lea     rcx, off_14005EF50; "Software\\Microsoft\\Enrollments"
0x140051729  mov     r9d, 20019h; samDesired
0x14005172f  neg     al
0x140051731  lea     rax, [rbp+hKey]
0x140051735  sbb     rdx, rdx
0x140051738  mov     [rsp+40h+phkResult], rax; phkResult
0x14005173d  and     edx, 8
0x140051740  xor     r8d, r8d; ulOptions
0x140051743  mov     rdx, [rdx+rcx]; lpSubKey
0x140051747  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005174e  call    cs:__imp_RegOpenKeyExW
0x140051754  mov     ebx, eax
0x140051756  test    eax, eax
0x140051758  jle     short loc_140051763
0x14005175a  movzx   ebx, ax
0x14005175d  or      ebx, 80070000h
0x140051763  test    ebx, ebx
0x140051765  jns     short loc_140051774
0x140051767  mov     rcx, [rbp+hKey]
0x14005176b  mov     [rbp+hKey], rdi
0x14005176f  jmp     loc_140051850
0x140051774  call    cs:__imp_GetProcessHeap
0x14005177a  mov     edx, 8; dwFlags
0x14005177f  mov     rcx, rax; hHeap
0x140051782  lea     r8d, [rdx+4Ch]; dwBytes
0x140051786  call    cs:__imp_HeapAlloc
0x14005178c  mov     rsi, rax
0x14005178f  test    rax, rax
0x140051792  jnz     short loc_14005179B
0x140051794  mov     ebx, 8007000Eh
0x140051799  jmp     short loc_1400517F7
0x14005179b  mov     rcx, [rbp+hKey]
0x14005179f  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x1400517a6  mov     r9, rsi
0x1400517a9  mov     dword ptr [rsp+40h+phkResult], 2Ah ; '*'; unsigned int *
0x1400517b1  mov     rdx, r12
0x1400517b4  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x1400517ba  mov     ebx, eax
0x1400517bc  test    eax, eax
0x1400517be  js      short loc_1400517F7
0x1400517c0  mov     rcx, r12; unsigned __int16 *
0x1400517c3  call    ?ImpersonateForCertAccess@@YAJPEBG@Z; ImpersonateForCertAccess(ushort const *)
0x1400517c8  lea     r8, [rbp+var_10]; struct _CERT_CONTEXT **
0x1400517cc  mov     rcx, rsi; unsigned __int16 *
0x1400517cf  lea     rdx, [rbp+arg_18]; void **
0x1400517d3  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x1400517d8  mov     rdi, [rbp+var_10]
0x1400517dc  mov     ebx, eax
0x1400517de  mov     r14, [rbp+arg_18]
0x1400517e2  test    eax, eax
0x1400517e4  js      short loc_1400517F7
0x1400517e6  mov     rcx, [rdi+18h]
0x1400517ea  mov     eax, [rcx+4Ch]
0x1400517ed  mov     [r15+4], eax
0x1400517f1  mov     eax, [rcx+48h]
0x1400517f4  mov     [r15], eax
0x1400517f7  cmp     cs:byte_14007E5F8, 0
0x1400517fe  jz      short loc_14005180D
0x140051800  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x140051806  mov     cs:byte_14007E5F8, 0
0x14005180d  test    rdi, rdi
0x140051810  jz      short loc_14005181B
0x140051812  mov     rcx, rdi; pCertContext
0x140051815  call    cs:__imp_CertFreeCertificateContext
0x14005181b  test    r14, r14
0x14005181e  jz      short loc_14005182B
0x140051820  xor     edx, edx; dwFlags
0x140051822  mov     rcx, r14; hCertStore
0x140051825  call    cs:__imp_CertCloseStore
0x14005182b  test    rsi, rsi
0x14005182e  jz      short loc_140051844
0x140051830  call    cs:__imp_GetProcessHeap
0x140051836  mov     r8, rsi; lpMem
0x140051839  xor     edx, edx; dwFlags
0x14005183b  mov     rcx, rax; hHeap
0x14005183e  call    cs:__imp_HeapFree
0x140051844  mov     rcx, [rbp+hKey]; hKey
0x140051848  mov     [rbp+hKey], 0
0x140051850  test    rcx, rcx
0x140051853  jz      short loc_14005185B
0x140051855  call    cs:__imp_RegCloseKey
0x14005185b  mov     rsi, [rsp+40h+arg_8]
0x140051860  mov     eax, ebx
0x140051862  mov     rbx, [rsp+40h+arg_0]
0x140051867  add     rsp, 40h
0x14005186b  pop     r15
0x14005186d  pop     r14
0x14005186f  pop     r12
0x140051871  pop     rdi
0x140051872  pop     rbp
0x140051873  retn
```
