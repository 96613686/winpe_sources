# IcpGetContainerHelper(unsigned __int64 *,char const *,char const *,ulong,ulong,int)

- ea: `0x1800048a4`
- end: `0x180004e1f`
- name: `?IcpGetContainerHelper@@YAJPEA_KPEBD1KKH@Z`
- size: `1403`
- prototype: `int(unsigned __int64 *, const char *, const char *, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000522c`
- `0x1800053bc`

## callees

- `0x180004870`
- `0x1800048a4`
- `0x180007234`
- `0x1800083de`
- `0x180008410`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180004935`
- `KERNEL32!EnterCriticalSection` at `0x180004935`
- `KERNEL32!LeaveCriticalSection` at `0x180004df4`
- `KERNEL32!LeaveCriticalSection` at `0x180004df4`
- `KERNEL32!GetVersionExA` at `0x180004c08`
- `KERNEL32!GetVersionExA` at `0x180004c08`
- `ADVAPI32!FreeSid` at `0x180004db1`
- `ADVAPI32!FreeSid` at `0x180004dc1`
- `ADVAPI32!FreeSid` at `0x180004db1`
- `ADVAPI32!FreeSid` at `0x180004dc1`
- `ADVAPI32!CryptSetProvParam` at `0x180004d81`
- `ADVAPI32!CryptSetProvParam` at `0x180004d81`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180004d64`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180004d64`
- `ADVAPI32!AddAccessAllowedAce` at `0x180004d33`
- `ADVAPI32!AddAccessAllowedAce` at `0x180004d4d`
- `ADVAPI32!AddAccessAllowedAce` at `0x180004d33`
- `ADVAPI32!AddAccessAllowedAce` at `0x180004d4d`
- `ADVAPI32!InitializeAcl` at `0x180004d08`
- `ADVAPI32!InitializeAcl` at `0x180004d08`
- `ADVAPI32!GetLengthSid` at `0x180004ccb`
- `ADVAPI32!GetLengthSid` at `0x180004cd8`
- `ADVAPI32!GetLengthSid` at `0x180004ccb`
- `ADVAPI32!GetLengthSid` at `0x180004cd8`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180004c7a`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180004cb8`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180004c7a`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180004cb8`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180004c34`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180004c34`
- `ADVAPI32!CryptReleaseContext` at `0x180004dd7`
- `ADVAPI32!CryptReleaseContext` at `0x180004dd7`
- `ADVAPI32!CryptAcquireContextA` at `0x180004966`
- `ADVAPI32!CryptAcquireContextA` at `0x180004a2d`
- `ADVAPI32!CryptAcquireContextA` at `0x180004b85`
- `ADVAPI32!CryptAcquireContextA` at `0x180004966`
- `ADVAPI32!CryptAcquireContextA` at `0x180004a2d`
- `ADVAPI32!CryptAcquireContextA` at `0x180004b85`
- `ole32!CoTaskMemFree` at `0x180004da1`
- `ole32!CoTaskMemFree` at `0x180004da1`
- `ole32!CoTaskMemAlloc` at `0x180004ce5`
- `ole32!CoTaskMemAlloc` at `0x180004ce5`

## string_xrefs

- `0x180004994`: `IcpGetContainerHelper. CryptAcquireContext(advapi32.dll) with CRYPT_VERIFYCONTEXT failed err=0x%x\n`
- `0x180004a6e`: `IcpGetContainerHelper. CryptAcquireContext(advapi32.dll) failed err=0x%x.toast.\n`
- `0x180004b51`: `CryptAcquireContext(%p,%p,%p,%d,%d) returned NTE_BAD_KEYSET, so lets create a keyset now...\n`
- `0x180004bb0`: `IcpGetContainerHelper. CryptAcquireContext(advapi32.dll) failed err=0x%x.\n`

## pseudocode

```c
__int64 __fastcall IcpGetContainerHelper(
        unsigned __int64 *a1,
        const char *a2,
        const char *a3,
        __int64 a4,
        DWORD dwFlags,
        int a6)
{
  struct _ACL *v9; // rdi
  int LastError; // ebx
  int v11; // eax
  unsigned int v12; // r8d
  int v13; // ebx
  DWORD LengthSid; // ebx
  DWORD v15; // ebx
  struct _ACL *v16; // rax
  HCRYPTPROV phProv; // [rsp+60h] [rbp-A0h] BYREF
  LPCSTR szContainer; // [rsp+68h] [rbp-98h]
  PSID v19; // [rsp+70h] [rbp-90h] BYREF
  PSID pSid; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 *v21; // [rsp+80h] [rbp-80h]
  _OWORD pSecurityDescriptor[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v23; // [rsp+A8h] [rbp-58h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B0h] [rbp-50h] BYREF
  struct _OSVERSIONINFOA VersionInformation; // [rsp+C0h] [rbp-40h] BYREF

  szContainer = a2;
  v21 = a1;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v23 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  if ( !dword_18000FC34 )
  {
    *a1 = 1984918096;
    return 0;
  }
  phProv = 0;
  pSid = 0;
  v9 = 0;
  v19 = 0;
  EnterCriticalSection(&IcpGlobals);
  if ( !a2 )
  {
    if ( !CryptAcquireContextA(&phProv, 0, "Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
    {
      LastError = IcpGetLastError();
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "inetsrv\\iis\\mb\\crypto\\contain.cxx",
          0x239u,
          "IcpGetContainerHelper",
          "IcpGetContainerHelper. CryptAcquireContext(advapi32.dll) with CRYPT_VERIFYCONTEXT failed err=0x%x\n",
          LastError);
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "inetsrv\\iis\\mb\\crypto\\contain.cxx",
            0x23Au,
            "IcpGetContainerHelper",
            "args for CryptAcquireContext(%p,%p,%p,%d,%d)\n",
            (char)&phProv);
      }
      goto LABEL_41;
    }
LABEL_39:
    *v21 = phProv;
    LastError = 0;
    if ( v9 )
      goto LABEL_40;
LABEL_41:
    if ( v19 )
      FreeSid(v19);
    if ( pSid )
      FreeSid(pSid);
    if ( phProv )
    {
      if ( LastError < 0 )
        CryptReleaseContext(phProv, 0);
    }
    goto LABEL_49;
  }
  if ( !CryptAcquireContextA(&phProv, a2, "Microsoft Base Cryptographic Provider v1.0", 1u, dwFlags) )
  {
    v11 = IcpGetLastError();
    LastError = v11;
    if ( v11 < 0 )
    {
      if ( v11 == -2146893802 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "inetsrv\\iis\\mb\\crypto\\contain.cxx",
            0x26Bu,
            "IcpGetContainerHelper",
            "CryptAcquireContext(%p,%p,%p,%d,%d) returned NTE_BAD_KEYSET, so lets create a keyset now...\n",
            (char)&phProv);
        if ( CryptAcquireContextA(&phProv, szContainer, "Microsoft Base Cryptographic Provider v1.0", 1u, dwFlags | 8)
          || (LastError = IcpGetLastError(), LastError >= 0) )
        {
          VersionInformation.dwOSVersionInfoSize = 148;
          v13 = 0;
          if ( GetVersionExA(&VersionInformation) )
            LOBYTE(v13) = VersionInformation.dwPlatformId == 2;
          if ( a6 && v13 )
          {
            if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
              || !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid)
              || !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v19) )
            {
              LastError = IcpGetLastError();
              goto LABEL_41;
            }
            LengthSid = GetLengthSid(v19);
            v15 = GetLengthSid(pSid) + 28 + LengthSid;
            v16 = (struct _ACL *)CoTaskMemAlloc(v15);
            v9 = v16;
            if ( !v16 )
            {
              LastError = -2147024888;
              goto LABEL_41;
            }
            if ( !InitializeAcl(v16, v15, 2u)
              || !AddAccessAllowedAce(v9, 2u, 0xF003Fu, pSid)
              || !AddAccessAllowedAce(v9, 2u, 0xF003Fu, v19)
              || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v9, 0)
              || !CryptSetProvParam(phProv, 8u, (const BYTE *)pSecurityDescriptor, 4u) )
            {
              LastError = IcpGetLastError();
LABEL_40:
              CoTaskMemFree(v9);
              goto LABEL_41;
            }
          }
          goto LABEL_39;
        }
        if ( (g_dwDebugFlags & 3) == 0
          || (PuDbgPrint(
                (struct _DEBUG_PRINTS *)g_pDebug,
                "inetsrv\\iis\\mb\\crypto\\contain.cxx",
                0x282u,
                "IcpGetContainerHelper",
                "IcpGetContainerHelper. CryptAcquireContext(advapi32.dll) failed err=0x%x.\n",
                LastError),
              (g_dwDebugFlags & 3) == 0) )
        {
LABEL_15:
          phProv = 0;
          goto LABEL_41;
        }
        v12 = 643;
      }
      else
      {
        if ( (g_dwDebugFlags & 3) == 0 )
          goto LABEL_15;
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "inetsrv\\iis\\mb\\crypto\\contain.cxx",
          0x263u,
          "IcpGetContainerHelper",
          "IcpGetContainerHelper. CryptAcquireContext(advapi32.dll) failed err=0x%x.toast.\n",
          v11);
        if ( (g_dwDebugFlags & 3) == 0 )
          goto LABEL_15;
        v12 = 612;
      }
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "inetsrv\\iis\\mb\\crypto\\contain.cxx",
        v12,
        "IcpGetContainerHelper",
        "args for CryptAcquireContext(%p,%p,%p,%d,%d)\n",
        (char)&phProv);
      goto LABEL_15;
    }
  }
  LastError = 0;
  *v21 = phProv;
LABEL_49:
  LeaveCriticalSection(&IcpGlobals);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800048a4  mov     [rsp-8+arg_10], rbx
0x1800048a9  push    rbp
0x1800048aa  push    rsi
0x1800048ab  push    rdi
0x1800048ac  push    r12
0x1800048ae  push    r13
0x1800048b0  lea     rbp, [rsp-70h]
0x1800048b5  sub     rsp, 170h
0x1800048bc  mov     rax, cs:__security_cookie
0x1800048c3  xor     rax, rsp
0x1800048c6  mov     [rbp+90h+var_30], rax
0x1800048ca  xorps   xmm0, xmm0
0x1800048cd  mov     [rsp+190h+szContainer], rdx
0x1800048d2  mov     rbx, rdx
0x1800048d5  mov     [rbp+90h+var_110], rcx
0x1800048d9  mov     rdi, rcx
0x1800048dc  mov     word ptr [rbp+90h+pIdentifierAuthority.Value+4], 500h
0x1800048e2  xor     eax, eax
0x1800048e4  lea     rcx, [rbp+90h+VersionInformation]; void *
0x1800048e8  xor     esi, esi
0x1800048ea  mov     [rbp+90h+var_E8], rax
0x1800048ee  xor     edx, edx; Val
0x1800048f0  mov     dword ptr [rbp+90h+pIdentifierAuthority.Value], esi
0x1800048f3  mov     r8d, 94h; Size
0x1800048f9  movups  [rbp+90h+pSecurityDescriptor], xmm0
0x1800048fd  movups  [rbp+90h+var_F8], xmm0
0x180004901  call    memset_0
0x180004906  cmp     cs:dword_18000FC34, esi
0x18000490c  jnz     short loc_18000491C
0x18000490e  mov     qword ptr [rdi], 764F7250h
0x180004915  xor     eax, eax
0x180004917  jmp     loc_180004DFC
0x18000491c  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x180004923  mov     [rsp+190h+phProv], rsi
0x180004928  mov     [rsp+190h+var_118], rsi
0x18000492d  mov     rdi, rsi
0x180004930  mov     [rsp+190h+var_120], rsi
0x180004935  call    cs:__imp_EnterCriticalSection
0x18000493b  lea     r13, szProvider; "Microsoft Base Cryptographic Provider v"...
0x180004942  mov     r12d, 1
0x180004948  lea     rcx, [rsp+190h+phProv]; phProv
0x18000494d  mov     r9d, r12d; dwProvType
0x180004950  mov     r8, r13; szProvider
0x180004953  test    rbx, rbx
0x180004956  jnz     loc_180004A20
0x18000495c  xor     edx, edx; szContainer
0x18000495e  mov     [rsp+190h+dwFlags], 0F0000000h; dwFlags
0x180004966  call    cs:__imp_CryptAcquireContextA
0x18000496c  test    eax, eax
0x18000496e  jnz     loc_180004D8B
0x180004974  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180004979  mov     ebx, eax
0x18000497b  mov     sil, 3
0x18000497e  mov     eax, cs:g_dwDebugFlags
0x180004984  test    sil, al
0x180004987  jz      loc_180004DA7
0x18000498d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180004994  lea     rax, aIcpgetcontaine; "IcpGetContainerHelper. CryptAcquireCont"...
0x18000499b  mov     [rsp+190h+nSubAuthority3], ebx; char
0x18000499f  lea     r9, aIcpgetcontaine_2; "IcpGetContainerHelper"
0x1800049a6  mov     r8d, 239h; unsigned int
0x1800049ac  mov     qword ptr [rsp+190h+dwFlags], rax; char *
0x1800049b1  lea     rdx, aInetsrvIisMbCr; "inetsrv\\iis\\mb\\crypto\\contain.cxx"
0x1800049b8  call    PuDbgPrint
0x1800049bd  mov     eax, cs:g_dwDebugFlags
0x1800049c3  test    sil, al
0x1800049c6  jz      loc_180004DA7
0x1800049cc  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800049d3  lea     rax, [rsp+190h+phProv]
0x1800049d8  mov     [rsp+190h+nSubAuthority7], 0F0000000h
0x1800049e0  lea     r9, aIcpgetcontaine_2; "IcpGetContainerHelper"
0x1800049e7  mov     [rsp+190h+nSubAuthority6], r12d
0x1800049ec  lea     rdx, aInetsrvIisMbCr; "inetsrv\\iis\\mb\\crypto\\contain.cxx"
0x1800049f3  mov     qword ptr [rsp+190h+nSubAuthority5], r13
0x1800049f8  xor     esi, esi
0x1800049fa  mov     qword ptr [rsp+190h+nSubAuthority4], rsi
0x1800049ff  mov     r8d, 23Ah; unsigned int
0x180004a05  mov     qword ptr [rsp+190h+nSubAuthority3], rax; char
0x180004a0a  lea     rax, aArgsForCryptac; "args for CryptAcquireContext(%p,%p,%p,%"...
0x180004a11  mov     qword ptr [rsp+190h+dwFlags], rax; char *
0x180004a16  call    PuDbgPrint
0x180004a1b  jmp     loc_180004DA7
0x180004a20  mov     eax, [rbp+90h+arg_20]
0x180004a26  mov     rdx, rbx; szContainer
0x180004a29  mov     [rsp+190h+dwFlags], eax; dwFlags
0x180004a2d  call    cs:__imp_CryptAcquireContextA
0x180004a33  test    eax, eax
0x180004a35  jnz     loc_180004DDF
0x180004a3b  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180004a40  mov     ebx, eax
0x180004a42  test    eax, eax
0x180004a44  jns     loc_180004DDF
0x180004a4a  mov     sil, 3
0x180004a4d  cmp     eax, 80090016h
0x180004a52  jz      loc_180004B05
0x180004a58  mov     eax, cs:g_dwDebugFlags
0x180004a5e  test    sil, al
0x180004a61  jz      loc_180004AF9
0x180004a67  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180004a6e  lea     rax, aIcpgetcontaine_0; "IcpGetContainerHelper. CryptAcquireCont"...
0x180004a75  mov     [rsp+190h+nSubAuthority3], ebx; char
0x180004a79  lea     r9, aIcpgetcontaine_2; "IcpGetContainerHelper"
0x180004a80  mov     r8d, 263h; unsigned int
0x180004a86  mov     qword ptr [rsp+190h+dwFlags], rax; char *
0x180004a8b  lea     rdx, aInetsrvIisMbCr; "inetsrv\\iis\\mb\\crypto\\contain.cxx"
0x180004a92  call    PuDbgPrint
0x180004a97  mov     eax, cs:g_dwDebugFlags
0x180004a9d  test    sil, al
0x180004aa0  jz      short loc_180004AF9
0x180004aa2  mov     eax, [rbp+90h+arg_20]
0x180004aa8  mov     r8d, 264h; unsigned int
0x180004aae  or      eax, 8
0x180004ab1  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180004ab8  lea     r9, aIcpgetcontaine_2; "IcpGetContainerHelper"
0x180004abf  mov     [rsp+190h+nSubAuthority7], eax
0x180004ac3  lea     rdx, aInetsrvIisMbCr; "inetsrv\\iis\\mb\\crypto\\contain.cxx"
0x180004aca  mov     rax, [rsp+190h+szContainer]
0x180004acf  mov     [rsp+190h+nSubAuthority6], r12d
0x180004ad4  mov     qword ptr [rsp+190h+nSubAuthority5], r13
0x180004ad9  mov     qword ptr [rsp+190h+nSubAuthority4], rax
0x180004ade  lea     rax, [rsp+190h+phProv]
0x180004ae3  mov     qword ptr [rsp+190h+nSubAuthority3], rax; char
0x180004ae8  lea     rax, aArgsForCryptac; "args for CryptAcquireContext(%p,%p,%p,%"...
0x180004aef  mov     qword ptr [rsp+190h+dwFlags], rax; char *
0x180004af4  call    PuDbgPrint
0x180004af9  xor     esi, esi
0x180004afb  mov     [rsp+190h+phProv], rsi
0x180004b00  jmp     loc_180004DA7
0x180004b05  test    byte ptr cs:g_dwDebugFlags, sil
0x180004b0c  jz      short loc_180004B62
0x180004b0e  mov     eax, [rbp+90h+arg_20]
0x180004b14  lea     r9, aIcpgetcontaine_2; "IcpGetContainerHelper"
0x180004b1b  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180004b22  lea     rdx, aInetsrvIisMbCr; "inetsrv\\iis\\mb\\crypto\\contain.cxx"
0x180004b29  mov     [rsp+190h+nSubAuthority7], eax
0x180004b2d  mov     r8d, 26Bh; unsigned int
0x180004b33  mov     rax, [rsp+190h+szContainer]
0x180004b38  mov     [rsp+190h+nSubAuthority6], r12d
0x180004b3d  mov     qword ptr [rsp+190h+nSubAuthority5], r13
0x180004b42  mov     qword ptr [rsp+190h+nSubAuthority4], rax
0x180004b47  lea     rax, [rsp+190h+phProv]
0x180004b4c  mov     qword ptr [rsp+190h+nSubAuthority3], rax; char
0x180004b51  lea     rax, aCryptacquireco; "CryptAcquireContext(%p,%p,%p,%d,%d) ret"...
0x180004b58  mov     qword ptr [rsp+190h+dwFlags], rax; char *
0x180004b5d  call    PuDbgPrint
0x180004b62  mov     eax, [rbp+90h+arg_20]
0x180004b68  lea     rcx, [rsp+190h+phProv]; phProv
0x180004b6d  mov     rdx, [rsp+190h+szContainer]; szContainer
0x180004b72  or      eax, 8
0x180004b75  mov     r9d, r12d; dwProvType
0x180004b78  mov     [rbp+90h+arg_20], eax
0x180004b7e  mov     r8, r13; szProvider
0x180004b81  mov     [rsp+190h+dwFlags], eax; dwFlags
0x180004b85  call    cs:__imp_CryptAcquireContextA
0x180004b8b  test    eax, eax
0x180004b8d  jnz     short loc_180004BF9
0x180004b8f  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180004b94  mov     ebx, eax
0x180004b96  test    eax, eax
0x180004b98  jns     short loc_180004BF9
0x180004b9a  mov     eax, cs:g_dwDebugFlags
0x180004ba0  test    sil, al
0x180004ba3  jz      loc_180004AF9
0x180004ba9  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180004bb0  lea     rax, aIcpgetcontaine_1; "IcpGetContainerHelper. CryptAcquireCont"...
0x180004bb7  mov     [rsp+190h+nSubAuthority3], ebx; char
0x180004bbb  lea     r9, aIcpgetcontaine_2; "IcpGetContainerHelper"
0x180004bc2  mov     r8d, 282h; unsigned int
0x180004bc8  mov     qword ptr [rsp+190h+dwFlags], rax; char *
0x180004bcd  lea     rdx, aInetsrvIisMbCr; "inetsrv\\iis\\mb\\crypto\\contain.cxx"
0x180004bd4  call    PuDbgPrint
0x180004bd9  mov     eax, cs:g_dwDebugFlags
0x180004bdf  test    sil, al
0x180004be2  jz      loc_180004AF9
0x180004be8  mov     eax, [rbp+90h+arg_20]
0x180004bee  mov     r8d, 283h
0x180004bf4  jmp     loc_180004AB1
0x180004bf9  xor     esi, esi
0x180004bfb  mov     [rbp+90h+VersionInformation.dwOSVersionInfoSize], 94h
0x180004c02  lea     rcx, [rbp+90h+VersionInformation]; lpVersionInformation
0x180004c06  mov     ebx, esi
0x180004c08  call    cs:__imp_GetVersionExA
0x180004c0e  test    eax, eax
0x180004c10  jz      short loc_180004C19
0x180004c12  cmp     [rbp+90h+VersionInformation.dwPlatformId], 2
0x180004c16  setz    bl
0x180004c19  cmp     [rbp+90h+arg_28], esi
0x180004c1f  jz      loc_180004D8B
0x180004c25  test    ebx, ebx
0x180004c27  jz      loc_180004D8B
0x180004c2d  mov     edx, r12d; dwRevision
0x180004c30  lea     rcx, [rbp+90h+pSecurityDescriptor]; pSecurityDescriptor
0x180004c34  call    cs:__imp_InitializeSecurityDescriptor
0x180004c3a  test    eax, eax
0x180004c3c  jnz     short loc_180004C4A
0x180004c3e  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180004c43  mov     ebx, eax
0x180004c45  jmp     loc_180004DA7
0x180004c4a  lea     rax, [rsp+190h+var_118]
0x180004c4f  xor     r9d, r9d; nSubAuthority1
0x180004c52  mov     [rsp+190h+pSid], rax; pSid
0x180004c57  lea     rcx, [rbp+90h+pIdentifierAuthority]; pIdentifierAuthority
0x180004c5b  mov     [rsp+190h+nSubAuthority7], esi; nSubAuthority7
0x180004c5f  mov     dl, r12b; nSubAuthorityCount
0x180004c62  mov     [rsp+190h+nSubAuthority6], esi; nSubAuthority6
0x180004c66  mov     [rsp+190h+nSubAuthority5], esi; nSubAuthority5
0x180004c6a  lea     r8d, [r9+12h]; nSubAuthority0
0x180004c6e  mov     [rsp+190h+nSubAuthority4], esi; nSubAuthority4
0x180004c72  mov     [rsp+190h+nSubAuthority3], esi; nSubAuthority3
0x180004c76  mov     [rsp+190h+dwFlags], esi; nSubAuthority2
0x180004c7a  call    cs:__imp_AllocateAndInitializeSid
0x180004c80  test    eax, eax
0x180004c82  jz      short loc_180004C3E
0x180004c84  lea     rax, [rsp+190h+var_120]
0x180004c89  mov     r9d, 220h; nSubAuthority1
0x180004c8f  mov     [rsp+190h+pSid], rax; pSid
0x180004c94  lea     rcx, [rbp+90h+pIdentifierAuthority]; pIdentifierAuthority
0x180004c98  mov     [rsp+190h+nSubAuthority7], esi; nSubAuthority7
0x180004c9c  mov     r8d, 20h ; ' '; nSubAuthority0
0x180004ca2  mov     [rsp+190h+nSubAuthority6], esi; nSubAuthority6
0x180004ca6  mov     dl, 2; nSubAuthorityCount
0x180004ca8  mov     [rsp+190h+nSubAuthority5], esi; nSubAuthority5
0x180004cac  mov     [rsp+190h+nSubAuthority4], esi; nSubAuthority4
0x180004cb0  mov     [rsp+190h+nSubAuthority3], esi; nSubAuthority3
0x180004cb4  mov     [rsp+190h+dwFlags], esi; nSubAuthority2
0x180004cb8  call    cs:__imp_AllocateAndInitializeSid
0x180004cbe  test    eax, eax
0x180004cc0  jz      loc_180004C3E
0x180004cc6  mov     rcx, [rsp+190h+var_120]; pSid
0x180004ccb  call    cs:__imp_GetLengthSid
0x180004cd1  mov     rcx, [rsp+190h+var_118]; pSid
0x180004cd6  mov     ebx, eax
0x180004cd8  call    cs:__imp_GetLengthSid
0x180004cde  add     eax, 1Ch
0x180004ce1  add     ebx, eax
0x180004ce3  mov     ecx, ebx; cb
0x180004ce5  call    cs:__imp_CoTaskMemAlloc
0x180004ceb  mov     rdi, rax
0x180004cee  test    rax, rax
0x180004cf1  jnz     short loc_180004CFD
0x180004cf3  mov     ebx, 80070008h
0x180004cf8  jmp     loc_180004DA7
0x180004cfd  mov     r8d, 2; dwAclRevision
0x180004d03  mov     edx, ebx; nAclLength
0x180004d05  mov     rcx, rdi; pAcl
0x180004d08  call    cs:__imp_InitializeAcl
0x180004d0e  test    eax, eax
0x180004d10  jnz     short loc_180004D1E
0x180004d12  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180004d17  mov     ebx, eax
0x180004d19  jmp     loc_180004D9E
0x180004d1e  mov     r9, [rsp+190h+var_118]; pSid
0x180004d23  mov     ebx, 0F003Fh
0x180004d28  mov     r8d, ebx; AccessMask
0x180004d2b  mov     edx, 2; dwAceRevision
0x180004d30  mov     rcx, rdi; pAcl
0x180004d33  call    cs:__imp_AddAccessAllowedAce
0x180004d39  test    eax, eax
0x180004d3b  jz      short loc_180004D12
0x180004d3d  mov     r9, [rsp+190h+var_120]; pSid
0x180004d42  mov     r8d, ebx; AccessMask
0x180004d45  mov     edx, 2; dwAceRevision
0x180004d4a  mov     rcx, rdi; pAcl
0x180004d4d  call    cs:__imp_AddAccessAllowedAce
0x180004d53  test    eax, eax
0x180004d55  jz      short loc_180004D12
0x180004d57  xor     r9d, r9d; bDaclDefaulted
0x180004d5a  lea     rcx, [rbp+90h+pSecurityDescriptor]; pSecurityDescriptor
0x180004d5e  mov     r8, rdi; pDacl
0x180004d61  mov     edx, r12d; bDaclPresent
0x180004d64  call    cs:__imp_SetSecurityDescriptorDacl
0x180004d6a  test    eax, eax
0x180004d6c  jz      short loc_180004D12
0x180004d6e  mov     rcx, [rsp+190h+phProv]; hProv
0x180004d73  lea     r8, [rbp+90h+pSecurityDescriptor]; pbData
0x180004d77  mov     r9d, 4; dwFlags
0x180004d7d  lea     edx, [r9+4]; dwParam
0x180004d81  call    cs:__imp_CryptSetProvParam
0x180004d87  test    eax, eax
0x180004d89  jz      short loc_180004D12
0x180004d8b  mov     rcx, [rbp+90h+var_110]
0x180004d8f  mov     rax, [rsp+190h+phProv]
0x180004d94  mov     [rcx], rax
0x180004d97  mov     ebx, esi
0x180004d99  test    rdi, rdi
0x180004d9c  jz      short loc_180004DA7
0x180004d9e  mov     rcx, rdi; pv
0x180004da1  call    cs:__imp_CoTaskMemFree
0x180004da7  mov     rcx, [rsp+190h+var_120]; pSid
0x180004dac  test    rcx, rcx
0x180004daf  jz      short loc_180004DB7
0x180004db1  call    cs:__imp_FreeSid
0x180004db7  mov     rcx, [rsp+190h+var_118]; pSid
0x180004dbc  test    rcx, rcx
0x180004dbf  jz      short loc_180004DC7
0x180004dc1  call    cs:__imp_FreeSid
0x180004dc7  mov     rcx, [rsp+190h+phProv]; hProv
0x180004dcc  test    rcx, rcx
0x180004dcf  jz      short loc_180004DED
0x180004dd1  test    ebx, ebx
  ... truncated ...
```
