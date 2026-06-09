# CUpdateManager::IsHostDomainJoined(int *)

- ea: `0x14003754c`
- end: `0x1400377b1`
- name: `?IsHostDomainJoined@CUpdateManager@@IEAAJPEAH@Z`
- size: `613`
- prototype: `__int64 __fastcall(CUpdateManager *__hidden this, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14003851c`

## callees

- `0x14003754c`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!LsaOpenPolicy` at `0x140037617`
- `ADVAPI32!LsaOpenPolicy` at `0x140037617`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1400376de`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1400376de`
- `ADVAPI32!LsaFreeMemory` at `0x140037783`
- `ADVAPI32!LsaFreeMemory` at `0x140037783`
- `ADVAPI32!LsaClose` at `0x14003778d`
- `ADVAPI32!LsaClose` at `0x14003778d`
- `KERNEL32!GetComputerNameW` at `0x1400375bb`
- `KERNEL32!GetComputerNameW` at `0x1400375bb`
- `KERNEL32!GetLastError` at `0x1400375c5`
- `KERNEL32!GetLastError` at `0x1400375c5`
- `KERNEL32!IsDebuggerPresent` at `0x14003766a`
- `KERNEL32!IsDebuggerPresent` at `0x14003772d`
- `KERNEL32!IsDebuggerPresent` at `0x14003766a`
- `KERNEL32!IsDebuggerPresent` at `0x14003772d`

## string_xrefs

- `0x140037647`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x14003770a`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x140037585`: `CUpdateManager::IsHostDomainJoined - Enter.\n`
- `0x14003763d`: `CUpdateManager::IsHostDomainJoined`
- `0x140037700`: `CUpdateManager::IsHostDomainJoined`
- `0x14003775d`: `CUpdateManager::IsHostDomainJoined - %s is domain joined.\n`
- `0x140037771`: `CUpdateManager::IsHostDomainJoined - %s is NOT domain joined.\n`

## pseudocode

```c
__int64 __fastcall CUpdateManager::IsHostDomainJoined(CUpdateManager *this, int *a2)
{
  signed int LastError; // eax
  signed int v4; // ebx
  NTSTATUS v5; // eax
  __int64 v6; // r9
  __int64 v7; // r8
  NTSTATUS v8; // eax
  DWORD nSize; // [rsp+40h] [rbp-59h] BYREF
  PVOID v11; // [rsp+48h] [rbp-51h] BYREF
  PVOID PolicyHandle; // [rsp+50h] [rbp-49h] BYREF
  struct _LSA_UNICODE_STRING SystemName; // [rsp+58h] [rbp-41h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-31h] BYREF
  WCHAR Buffer[8]; // [rsp+98h] [rbp-1h] BYREF
  __int128 v16; // [rsp+A8h] [rbp+Fh]

  PolicyHandle = 0;
  v11 = 0;
  nSize = 16;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  SystemName = 0;
  *(_OWORD *)Buffer = 0;
  v16 = 0;
  DEBUGMSG(L"CUpdateManager::IsHostDomainJoined - Enter.\n");
  if ( GetComputerNameW(Buffer, &nSize) )
  {
    SystemName.Buffer = Buffer;
    SystemName.Length = 2 * nSize;
    SystemName.MaximumLength = 32;
    v5 = LsaOpenPolicy(&SystemName, &ObjectAttributes, 0x80000001, &PolicyHandle);
    v4 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        0x80Au,
        L"CUpdateManager::IsHostDomainJoined",
        L"CBRAEx",
        L"status == ((NTSTATUS)0x00000000L)",
        v4);
      if ( IsDebuggerPresent() )
      {
        v6 = 2058;
LABEL_12:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
          v6,
          L"CUpdateManager::IsHostDomainJoined",
          L"CBRAEx",
          L"status == ((NTSTATUS)0x00000000L)",
          v4);
        goto LABEL_24;
      }
      v7 = 2058;
    }
    else
    {
      v8 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &v11);
      v4 = v8;
      if ( !v8 )
      {
        v4 = 0;
        if ( *((_QWORD *)v11 + 2) )
        {
          DEBUGMSG(L"CUpdateManager::IsHostDomainJoined - %s is domain joined.\n", Buffer);
          *a2 = 1;
        }
        else
        {
          DEBUGMSG(L"CUpdateManager::IsHostDomainJoined - %s is NOT domain joined.\n", Buffer);
          *a2 = 0;
        }
        goto LABEL_24;
      }
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        0x80Du,
        L"CUpdateManager::IsHostDomainJoined",
        L"CBRAEx",
        L"status == ((NTSTATUS)0x00000000L)",
        v4);
      if ( IsDebuggerPresent() )
      {
        v6 = 2061;
        goto LABEL_12;
      }
      v7 = 2061;
    }
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
      v7,
      L"CUpdateManager::IsHostDomainJoined",
      L"CBRAEx",
      L"status == ((NTSTATUS)0x00000000L)",
      v4);
    goto LABEL_24;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
    v4 = -2147467259;
LABEL_24:
  LsaFreeMemory(v11);
  LsaClose(PolicyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14003754c  push    rbp
0x14003754e  push    rbx
0x14003754f  push    rsi
0x140037550  push    rdi
0x140037551  push    r14
0x140037553  push    r15
0x140037555  lea     rbp, [rsp-2Fh]
0x14003755a  sub     rsp, 0C8h
0x140037561  mov     rax, cs:__security_cookie
0x140037568  xor     rax, rsp
0x14003756b  mov     [rbp+57h+var_38], rax
0x14003756f  xorps   xmm0, xmm0
0x140037572  mov     [rbp+57h+PolicyHandle], 0
0x14003757a  xorps   xmm1, xmm1
0x14003757d  mov     [rbp+57h+var_A8], 0
0x140037585  lea     rcx, aCupdatemanager_20; "CUpdateManager::IsHostDomainJoined - En"...
0x14003758c  mov     [rbp+57h+nSize], 10h
0x140037593  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140037597  mov     rdi, rdx
0x14003759a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14003759e  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400375a2  movups  xmmword ptr [rbp+57h+SystemName.Length], xmm0
0x1400375a6  movups  xmmword ptr [rbp+57h+Buffer], xmm1
0x1400375aa  movups  [rbp+57h+var_48], xmm1
0x1400375ae  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400375b3  lea     rdx, [rbp+57h+nSize]; nSize
0x1400375b7  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x1400375bb  call    cs:__imp_GetComputerNameW
0x1400375c1  test    eax, eax
0x1400375c3  jnz     short loc_1400375E9
0x1400375c5  call    cs:__imp_GetLastError
0x1400375cb  mov     ebx, eax
0x1400375cd  test    eax, eax
0x1400375cf  jle     short loc_1400375DA
0x1400375d1  movzx   ebx, ax
0x1400375d4  or      ebx, 80070000h
0x1400375da  test    ebx, ebx
0x1400375dc  mov     eax, 80004005h
0x1400375e1  cmovns  ebx, eax
0x1400375e4  jmp     loc_14003777F
0x1400375e9  lea     rax, [rbp+57h+Buffer]
0x1400375ed  mov     r8d, 80000001h; DesiredAccess
0x1400375f3  mov     [rbp+57h+SystemName.Buffer], rax
0x1400375f7  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x1400375fb  movzx   eax, word ptr [rbp+57h+nSize]
0x1400375ff  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140037603  add     ax, ax
0x140037606  lea     rcx, [rbp+57h+SystemName]; SystemName
0x14003760a  mov     [rbp+57h+SystemName.Length], ax
0x14003760e  mov     eax, 20h ; ' '
0x140037613  mov     [rbp+57h+SystemName.MaximumLength], ax
0x140037617  call    cs:__imp_LsaOpenPolicy
0x14003761d  mov     ebx, eax
0x14003761f  test    eax, eax
0x140037621  jz      loc_1400376D1
0x140037627  jle     short loc_140037632
0x140037629  movzx   ebx, ax
0x14003762c  or      ebx, 80070000h
0x140037632  lea     r15, aCbraex; "CBRAEx"
0x140037639  mov     [rsp+0F0h+var_C8], ebx; int
0x14003763d  lea     rsi, aCupdatemanager_77; "CUpdateManager::IsHostDomainJoined"
0x140037644  mov     r9, r15; unsigned __int16 *
0x140037647  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x14003764e  mov     r8, rsi; unsigned __int16 *
0x140037651  lea     r14, aStatusNtstatus_0; "status == ((NTSTATUS)0x00000000L)"
0x140037658  mov     rcx, rdi; unsigned __int16 *
0x14003765b  mov     edx, 80Ah; unsigned int
0x140037660  mov     [rsp+0F0h+var_D0], r14; unsigned __int16 *
0x140037665  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003766a  call    cs:__imp_IsDebuggerPresent
0x140037670  test    eax, eax
0x140037672  jz      short loc_1400376A6
0x140037674  mov     r9d, 80Ah
0x14003767a  mov     [rsp+0F0h+var_B8], ebx
0x14003767e  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140037685  mov     [rsp+0F0h+var_C0], r14
0x14003768a  mov     r8, rdi
0x14003768d  mov     qword ptr [rsp+0F0h+var_C8], r15
0x140037692  mov     ecx, 2; unsigned __int8
0x140037697  mov     [rsp+0F0h+var_D0], rsi
0x14003769c  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400376a1  jmp     loc_14003777F
0x1400376a6  mov     r8d, 80Ah
0x1400376ac  mov     dword ptr [rsp+0F0h+var_C0], ebx
0x1400376b0  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400376b7  mov     qword ptr [rsp+0F0h+var_C8], r14
0x1400376bc  mov     r9, rsi
0x1400376bf  mov     rdx, rdi
0x1400376c2  mov     [rsp+0F0h+var_D0], r15
0x1400376c7  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400376cc  jmp     loc_14003777F
0x1400376d1  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x1400376d5  lea     r8, [rbp+57h+var_A8]; Buffer
0x1400376d9  mov     edx, 0Ch; InformationClass
0x1400376de  call    cs:__imp_LsaQueryInformationPolicy
0x1400376e4  mov     ebx, eax
0x1400376e6  test    eax, eax
0x1400376e8  jz      short loc_14003774D
0x1400376ea  jle     short loc_1400376F5
0x1400376ec  movzx   ebx, ax
0x1400376ef  or      ebx, 80070000h
0x1400376f5  lea     r15, aCbraex; "CBRAEx"
0x1400376fc  mov     [rsp+0F0h+var_C8], ebx; int
0x140037700  lea     rsi, aCupdatemanager_77; "CUpdateManager::IsHostDomainJoined"
0x140037707  mov     r9, r15; unsigned __int16 *
0x14003770a  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140037711  mov     r8, rsi; unsigned __int16 *
0x140037714  lea     r14, aStatusNtstatus_0; "status == ((NTSTATUS)0x00000000L)"
0x14003771b  mov     rcx, rdi; unsigned __int16 *
0x14003771e  mov     edx, 80Dh; unsigned int
0x140037723  mov     [rsp+0F0h+var_D0], r14; unsigned __int16 *
0x140037728  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003772d  call    cs:__imp_IsDebuggerPresent
0x140037733  test    eax, eax
0x140037735  jz      short loc_140037742
0x140037737  mov     r9d, 80Dh
0x14003773d  jmp     loc_14003767A
0x140037742  mov     r8d, 80Dh
0x140037748  jmp     loc_1400376AC
0x14003774d  mov     rax, [rbp+57h+var_A8]
0x140037751  lea     rdx, [rbp+57h+Buffer]
0x140037755  xor     ebx, ebx
0x140037757  cmp     [rax+10h], rbx
0x14003775b  jz      short loc_140037771
0x14003775d  lea     rcx, aCupdatemanager_35; "CUpdateManager::IsHostDomainJoined - %s"...
0x140037764  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140037769  mov     dword ptr [rdi], 1
0x14003776f  jmp     short loc_14003777F
0x140037771  lea     rcx, aCupdatemanager_27; "CUpdateManager::IsHostDomainJoined - %s"...
0x140037778  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14003777d  mov     [rdi], ebx
0x14003777f  mov     rcx, [rbp+57h+var_A8]; Buffer
0x140037783  call    cs:__imp_LsaFreeMemory
0x140037789  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x14003778d  call    cs:__imp_LsaClose
0x140037793  mov     eax, ebx
0x140037795  mov     rcx, [rbp+57h+var_38]
0x140037799  xor     rcx, rsp; StackCookie
0x14003779c  call    __security_check_cookie
0x1400377a1  add     rsp, 0C8h
0x1400377a8  pop     r15
0x1400377aa  pop     r14
0x1400377ac  pop     rdi
0x1400377ad  pop     rsi
0x1400377ae  pop     rbx
0x1400377af  pop     rbp
0x1400377b0  retn
```
