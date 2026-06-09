# IIS_LOGON_PROVIDER::GetDefaultDomainName(void)

- ea: `0x18000428c`
- end: `0x180004489`
- name: `?GetDefaultDomainName@IIS_LOGON_PROVIDER@@AEAAJXZ`
- size: `509`
- prototype: `__int64 __fastcall(wchar_t *Destination)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002820`

## callees

- `0x18000428c`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800043c8`
- `msvcrt!wcsncpy_s` at `0x1800043c8`
- `ntdll!RtlNtStatusToDosError` at `0x180004323`
- `ntdll!RtlNtStatusToDosError` at `0x180004396`
- `ntdll!RtlNtStatusToDosError` at `0x180004323`
- `ntdll!RtlNtStatusToDosError` at `0x180004396`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180004434`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180004434`
- `iisutil!PuDbgPrint` at `0x18000431b`
- `iisutil!PuDbgPrint` at `0x18000438e`
- `iisutil!PuDbgPrint` at `0x18000431b`
- `iisutil!PuDbgPrint` at `0x18000438e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180004471`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180004471`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800042db`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800042db`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18000434e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800043e7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18000434e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800043e7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000444b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000445e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000444b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000445e`

## string_xrefs

- `0x180004309`: `cannot open lsa policy, error %08lX\n`
- `0x180004302`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180004382`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::GetDefaultDomainName(wchar_t *Destination)
{
  NTSTATUS v2; // eax
  NTSTATUS v3; // ebx
  signed int v4; // eax
  unsigned int v5; // ebx
  int v6; // ebx
  __int64 v7; // r8
  signed int v8; // eax
  PVOID v10; // [rsp+30h] [rbp-40h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF
  DWORD nSize; // [rsp+98h] [rbp+28h] BYREF
  PVOID PolicyHandle; // [rsp+A0h] [rbp+30h] BYREF
  PVOID Buffer; // [rsp+A8h] [rbp+38h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  nSize = 0;
  PolicyHandle = 0;
  Buffer = 0;
  v10 = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 0x20801u, &PolicyHandle);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
        320,
        "IIS_LOGON_PROVIDER::GetDefaultDomainName",
        "cannot open lsa policy, error %08lX\n",
        v2);
    v4 = RtlNtStatusToDosError(v3);
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    PolicyHandle = 0;
    goto LABEL_21;
  }
  v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
  if ( v6 >= 0 )
  {
    if ( wcsncpy_s(Destination, 0x100u, *((const wchar_t **)Buffer + 1), 0xFFFFFFFFFFFFFFFFuLL) == 80 )
    {
      v5 = -2147024774;
      goto LABEL_21;
    }
    v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &v10);
    if ( v6 >= 0 )
    {
      v5 = 0;
      if ( *((_QWORD *)v10 + 2) )
      {
        *((_DWORD *)Destination + 640) = 1;
        nSize = 1024;
        GetComputerNameExW(ComputerNameDnsDomain, Destination + 256, &nSize);
      }
      else
      {
        *((_DWORD *)Destination + 640) = 0;
      }
      goto LABEL_21;
    }
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_11;
    v7 = 380;
  }
  else
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_11;
    v7 = 347;
  }
  PuDbgPrint(
    g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
    v7,
    "IIS_LOGON_PROVIDER::GetDefaultDomainName",
    "cannot query lsa policy info, error %08lX\n",
    v6);
LABEL_11:
  v8 = RtlNtStatusToDosError(v6);
  v5 = v8;
  if ( v8 > 0 )
    v5 = (unsigned __int16)v8 | 0x80070000;
LABEL_21:
  if ( Buffer )
  {
    LsaFreeMemory(Buffer);
    Buffer = 0;
  }
  if ( v10 )
  {
    LsaFreeMemory(v10);
    v10 = 0;
  }
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v5;
}

```

## disassembly

```asm
0x18000428c  mov     [rsp-18h+arg_0], rbx
0x180004291  push    rbp
0x180004292  push    rsi
0x180004293  push    rdi
0x180004294  mov     rbp, rsp
0x180004297  sub     rsp, 70h
0x18000429b  xor     esi, esi
0x18000429d  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800042a5  mov     rdi, rcx
0x1800042a8  mov     qword ptr [rbp+ObjectAttributes.Attributes], rsi
0x1800042ac  xorps   xmm0, xmm0
0x1800042af  mov     [rbp+nSize], esi
0x1800042b2  xor     ecx, ecx; SystemName
0x1800042b4  mov     [rbp+PolicyHandle], rsi
0x1800042b8  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800042bc  mov     [rbp+Buffer], rsi
0x1800042c0  mov     r8d, 20801h; DesiredAccess
0x1800042c6  mov     [rbp+var_40], rsi
0x1800042ca  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800042ce  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x1800042d2  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x1800042d6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800042db  call    cs:__imp_LsaOpenPolicy
0x1800042e1  mov     ebx, eax
0x1800042e3  test    eax, eax
0x1800042e5  jns     short loc_180004341
0x1800042e7  test    byte ptr cs:g_dwDebugFlags, 3
0x1800042ee  jz      short loc_180004321
0x1800042f0  mov     rcx, cs:g_pDebug
0x1800042f7  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x1800042fe  mov     [rsp+70h+var_48], eax
0x180004302  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004309  lea     rax, aCannotOpenLsaP; "cannot open lsa policy, error %08lX\n"
0x180004310  mov     r8d, 140h
0x180004316  mov     [rsp+70h+var_50], rax
0x18000431b  call    cs:__imp_PuDbgPrint
0x180004321  mov     ecx, ebx; Status
0x180004323  call    cs:__imp_RtlNtStatusToDosError
0x180004329  mov     ebx, eax
0x18000432b  test    eax, eax
0x18000432d  jle     short loc_180004338
0x18000432f  movzx   ebx, ax
0x180004332  or      ebx, 80070000h
0x180004338  mov     [rbp+PolicyHandle], rsi
0x18000433c  jmp     loc_180004442
0x180004341  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180004345  lea     r8, [rbp+Buffer]; Buffer
0x180004349  mov     edx, 5; InformationClass
0x18000434e  call    cs:__imp_LsaQueryInformationPolicy
0x180004354  mov     ebx, eax
0x180004356  test    eax, eax
0x180004358  jns     short loc_1800043B4
0x18000435a  test    byte ptr cs:g_dwDebugFlags, 3
0x180004361  jz      short loc_180004394
0x180004363  mov     r8d, 15Bh
0x180004369  mov     rcx, cs:g_pDebug
0x180004370  lea     rax, aCannotQueryLsa; "cannot query lsa policy info, error %08"...
0x180004377  mov     [rsp+70h+var_48], ebx
0x18000437b  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x180004382  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004389  mov     [rsp+70h+var_50], rax
0x18000438e  call    cs:__imp_PuDbgPrint
0x180004394  mov     ecx, ebx; Status
0x180004396  call    cs:__imp_RtlNtStatusToDosError
0x18000439c  mov     ebx, eax
0x18000439e  test    eax, eax
0x1800043a0  jle     loc_180004442
0x1800043a6  movzx   ebx, ax
0x1800043a9  or      ebx, 80070000h
0x1800043af  jmp     loc_180004442
0x1800043b4  mov     r8, [rbp+Buffer]
0x1800043b8  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800043bc  mov     edx, 100h; SizeInWords
0x1800043c1  mov     rcx, rdi; Destination
0x1800043c4  mov     r8, [r8+8]; Source
0x1800043c8  call    cs:__imp_wcsncpy_s
0x1800043ce  cmp     eax, 50h ; 'P'
0x1800043d1  jnz     short loc_1800043DA
0x1800043d3  mov     ebx, 8007007Ah
0x1800043d8  jmp     short loc_180004442
0x1800043da  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800043de  lea     r8, [rbp+var_40]; Buffer
0x1800043e2  mov     edx, 3; InformationClass
0x1800043e7  call    cs:__imp_LsaQueryInformationPolicy
0x1800043ed  mov     ebx, eax
0x1800043ef  test    eax, eax
0x1800043f1  jns     short loc_180004407
0x1800043f3  test    byte ptr cs:g_dwDebugFlags, 3
0x1800043fa  jz      short loc_180004394
0x1800043fc  mov     r8d, 17Ch
0x180004402  jmp     loc_180004369
0x180004407  mov     rax, [rbp+var_40]
0x18000440b  mov     ebx, esi
0x18000440d  cmp     [rax+10h], rsi
0x180004411  jz      short loc_18000443C
0x180004413  lea     rdx, [rdi+200h]; lpBuffer
0x18000441a  mov     dword ptr [rdi+0A00h], 1
0x180004424  lea     r8, [rbp+nSize]; nSize
0x180004428  mov     [rbp+nSize], 400h
0x18000442f  mov     ecx, 2; NameType
0x180004434  call    cs:__imp_GetComputerNameExW
0x18000443a  jmp     short loc_180004442
0x18000443c  mov     [rdi+0A00h], esi
0x180004442  mov     rcx, [rbp+Buffer]; Buffer
0x180004446  test    rcx, rcx
0x180004449  jz      short loc_180004455
0x18000444b  call    cs:__imp_LsaFreeMemory
0x180004451  mov     [rbp+Buffer], rsi
0x180004455  mov     rcx, [rbp+var_40]; Buffer
0x180004459  test    rcx, rcx
0x18000445c  jz      short loc_180004468
0x18000445e  call    cs:__imp_LsaFreeMemory
0x180004464  mov     [rbp+var_40], rsi
0x180004468  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18000446c  test    rcx, rcx
0x18000446f  jz      short loc_180004477
0x180004471  call    cs:__imp_LsaClose
0x180004477  mov     eax, ebx
0x180004479  mov     rbx, [rsp+70h+arg_0]
0x180004481  add     rsp, 70h
0x180004485  pop     rdi
0x180004486  pop     rsi
0x180004487  pop     rbp
0x180004488  retn
```
