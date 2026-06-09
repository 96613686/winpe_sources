# OSIntegration::DEH::CSearchIndexerDeploymentExtension::_MarkPackageUninstalled(ushort const *,ushort const *)

- ea: `0x1800eb2e8`
- end: `0x1800eb4a3`
- name: `?_MarkPackageUninstalled@CSearchIndexerDeploymentExtension@DEH@OSIntegration@@AEAAXPEBG0@Z`
- size: `443`
- prototype: `void __fastcall(OSIntegration::DEH::CSearchIndexerDeploymentExtension *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180058170`

## callees

- `0x180015590`
- `0x18003d814`
- `0x18003d8f4`
- `0x1800af1bc`
- `0x1800af1fc`
- `0x1800da940`
- `0x1800eb2e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eb46d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eb46d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800eb3fb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800eb3fb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800eb323`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800eb323`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800eb44c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800eb44c`

## string_xrefs

- `0x1800eb391`: `SOFTWARE\Microsoft\Windows Search\UninstalledStoreApps`
- `0x1800eb43d`: `SOFTWARE\Microsoft\Windows Search\UninstalledStoreApps`

## pseudocode

```c
void __fastcall OSIntegration::DEH::CSearchIndexerDeploymentExtension::_MarkPackageUninstalled(
        OSIntegration::DEH::CSearchIndexerDeploymentExtension *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  Common *lpSecurityDescriptor; // rdi
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rax
  unsigned __int16 *v10; // rax
  WCHAR *v11; // rbx
  void *v12; // rdx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-48h] BYREF
  void *TokenHandle; // [rsp+A0h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+20h] BYREF

  TokenHandle = this;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GRGX;;;SY)(A;;GRGX;;;BA)(A;;GRGX;;;BU)(A;;GA;;;S-1-5-80-117416528-2204451360-1913602512-1355018040-1234992034)",
         1u,
         &SecurityAttributes.lpSecurityDescriptor,
         0) )
  {
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    lpSecurityDescriptor = (Common *)SecurityAttributes.lpSecurityDescriptor;
    v8 = v6 + v5 + 57;
    v9 = 2 * v8;
    if ( !is_mul_ok(v8, 2u) )
      v9 = -1;
    v10 = (unsigned __int16 *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( v10 )
    {
      if ( StringCchPrintfW(
             v10,
             v8,
             L"%s\\%s\\%s",
             L"SOFTWARE\\Microsoft\\Windows Search\\UninstalledStoreApps",
             a2,
             a3) >= 0 )
      {
        hKey = 0;
        if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0, 0, 0x20019u, &SecurityAttributes, &hKey, 0) )
        {
          TokenHandle = 0;
          if ( (int)Common::AutoNoImpersonateDuringScope::DropImpersonation(&TokenHandle) >= 0 )
            RegSetKeyValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows Search\\UninstalledStoreApps",
              L"CheckOnStartup",
              4u,
              &unk_1801DE78C,
              4u);
          Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
          RegCloseKey(hKey);
        }
      }
    }
    operator delete(v11, (const struct std::nothrow_t *)2);
    Common::AutoHandleFreeHLocal(lpSecurityDescriptor, v12);
  }
}

```

## disassembly

```asm
0x1800eb2e8  mov     r11, rsp
0x1800eb2eb  mov     [r11+10h], rbx
0x1800eb2ef  mov     [r11+8], rcx
0x1800eb2f3  push    rbp
0x1800eb2f4  push    rsi
0x1800eb2f5  push    rdi
0x1800eb2f6  push    r14
0x1800eb2f8  push    r15
0x1800eb2fa  sub     rsp, 70h
0x1800eb2fe  xor     eax, eax
0x1800eb300  lea     rcx, StringSecurityDescriptor; "D:(A;;GRGX;;;SY)(A;;GRGX;;;BA)(A;;GRGX;"...
0x1800eb307  xorps   xmm0, xmm0
0x1800eb30a  mov     rsi, r8
0x1800eb30d  mov     rbp, rdx
0x1800eb310  lea     r8, [r11-40h]; SecurityDescriptor
0x1800eb314  movups  xmmword ptr [rsp+98h+SecurityAttributes.nLength], xmm0
0x1800eb319  lea     edx, [rax+1]; StringSDRevision
0x1800eb31c  mov     [r11-38h], rax
0x1800eb320  xor     r9d, r9d; SecurityDescriptorSize
0x1800eb323  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800eb32a  nop     dword ptr [rax+rax+00h]
0x1800eb32f  xor     r15d, r15d
0x1800eb332  test    eax, eax
0x1800eb334  jz      loc_1800EB48E
0x1800eb33a  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800eb33e  mov     rax, r8
0x1800eb341  inc     rax
0x1800eb344  cmp     [rsi+rax*2], r15w
0x1800eb349  jnz     short loc_1800EB341
0x1800eb34b  mov     rcx, r8
0x1800eb34e  inc     rcx
0x1800eb351  cmp     [rbp+rcx*2+0], r15w
0x1800eb357  jnz     short loc_1800EB34E
0x1800eb359  mov     rdi, [rsp+98h+SecurityAttributes.lpSecurityDescriptor]
0x1800eb35e  lea     r14, [rax+39h]
0x1800eb362  add     r14, rcx
0x1800eb365  mov     eax, 2
0x1800eb36a  mul     r14
0x1800eb36d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800eb374  cmovb   rax, r8
0x1800eb378  mov     rcx, rax; unsigned __int64
0x1800eb37b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800eb380  mov     rbx, rax
0x1800eb383  test    rax, rax
0x1800eb386  jz      loc_1800EB479
0x1800eb38c  mov     qword ptr [rsp+98h+samDesired], rsi
0x1800eb391  lea     r9, aSoftwareMicros_26; "SOFTWARE\\Microsoft\\Windows Search\\Un"...
0x1800eb398  lea     r8, aSSS; "%s\\%s\\%s"
0x1800eb39f  mov     qword ptr [rsp+98h+dwOptions], rbp
0x1800eb3a4  mov     rdx, r14; unsigned __int64
0x1800eb3a7  mov     rcx, rax; unsigned __int16 *
0x1800eb3aa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800eb3af  test    eax, eax
0x1800eb3b1  js      loc_1800EB479
0x1800eb3b7  mov     [rsp+98h+lpdwDisposition], r15; lpdwDisposition
0x1800eb3bc  lea     rax, [rsp+98h+hKey]
0x1800eb3c4  mov     [rsp+98h+phkResult], rax; phkResult
0x1800eb3c9  mov     rsi, 0FFFFFFFF80000002h
0x1800eb3d0  lea     rax, [rsp+98h+SecurityAttributes]
0x1800eb3d5  mov     [rsp+98h+hKey], r15
0x1800eb3dd  mov     [rsp+98h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800eb3e2  xor     r9d, r9d; lpClass
0x1800eb3e5  mov     [rsp+98h+samDesired], 20019h; samDesired
0x1800eb3ed  xor     r8d, r8d; Reserved
0x1800eb3f0  mov     rdx, rbx; lpSubKey
0x1800eb3f3  mov     [rsp+98h+dwOptions], r15d; dwOptions
0x1800eb3f8  mov     rcx, rsi; hKey
0x1800eb3fb  call    cs:__imp_RegCreateKeyExW
0x1800eb402  nop     dword ptr [rax+rax+00h]
0x1800eb407  test    eax, eax
0x1800eb409  jnz     short loc_1800EB479
0x1800eb40b  lea     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x1800eb413  mov     [rsp+98h+TokenHandle], r15
0x1800eb41b  call    ?DropImpersonation@AutoNoImpersonateDuringScope@Common@@QEAAJXZ; Common::AutoNoImpersonateDuringScope::DropImpersonation(void)
0x1800eb420  test    eax, eax
0x1800eb422  js      short loc_1800EB458
0x1800eb424  mov     r9d, 4; dwType
0x1800eb42a  lea     rax, unk_1801DE78C
0x1800eb431  mov     [rsp+98h+samDesired], r9d; cbData
0x1800eb436  lea     r8, aCheckonstartup; "CheckOnStartup"
0x1800eb43d  lea     rdx, aSoftwareMicros_26; "SOFTWARE\\Microsoft\\Windows Search\\Un"...
0x1800eb444  mov     qword ptr [rsp+98h+dwOptions], rax; lpData
0x1800eb449  mov     rcx, rsi; hKey
0x1800eb44c  call    cs:__imp_RegSetKeyValueW
0x1800eb453  nop     dword ptr [rax+rax+00h]
0x1800eb458  lea     rcx, [rsp+98h+TokenHandle]; this
0x1800eb460  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x1800eb465  mov     rcx, [rsp+98h+hKey]; hKey
0x1800eb46d  call    cs:__imp_RegCloseKey
0x1800eb474  nop     dword ptr [rax+rax+00h]
0x1800eb479  mov     edx, 2; struct std::nothrow_t *
0x1800eb47e  mov     rcx, rbx; void *
0x1800eb481  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eb486  mov     rcx, rdi; this
0x1800eb489  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x1800eb48e  mov     rbx, [rsp+98h+arg_8]
0x1800eb496  add     rsp, 70h
0x1800eb49a  pop     r15
0x1800eb49c  pop     r14
0x1800eb49e  pop     rdi
0x1800eb49f  pop     rsi
0x1800eb4a0  pop     rbp
0x1800eb4a1  retn
```
