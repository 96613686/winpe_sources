# IIS_LOGON_PROVIDER::GetDefaultDomainName(void)

- ea: `0x18000551c`
- end: `0x180005719`
- name: `?GetDefaultDomainName@IIS_LOGON_PROVIDER@@AEAAJXZ`
- size: `509`
- prototype: `__int64 __fastcall(wchar_t *Destination)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002480`

## callees

- `0x18000551c`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180005658`
- `msvcrt!wcsncpy_s` at `0x180005658`
- `ntdll!RtlNtStatusToDosError` at `0x1800055b3`
- `ntdll!RtlNtStatusToDosError` at `0x180005626`
- `ntdll!RtlNtStatusToDosError` at `0x1800055b3`
- `ntdll!RtlNtStatusToDosError` at `0x180005626`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800056c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800056c4`
- `iisutil!PuDbgPrint` at `0x1800055ab`
- `iisutil!PuDbgPrint` at `0x18000561e`
- `iisutil!PuDbgPrint` at `0x1800055ab`
- `iisutil!PuDbgPrint` at `0x18000561e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800055de`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180005677`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800055de`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180005677`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800056db`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800056ee`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800056db`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800056ee`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180005701`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180005701`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000556b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000556b`

## string_xrefs

- `0x180005599`: `cannot open lsa policy, error %08lX\n`
- `0x180005592`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180005612`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`

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
0x18000551c  mov     [rsp-18h+arg_0], rbx
0x180005521  push    rbp
0x180005522  push    rsi
0x180005523  push    rdi
0x180005524  mov     rbp, rsp
0x180005527  sub     rsp, 70h
0x18000552b  xor     esi, esi
0x18000552d  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180005535  mov     rdi, rcx
0x180005538  mov     qword ptr [rbp+ObjectAttributes.Attributes], rsi
0x18000553c  xorps   xmm0, xmm0
0x18000553f  mov     [rbp+nSize], esi
0x180005542  xor     ecx, ecx; SystemName
0x180005544  mov     [rbp+PolicyHandle], rsi
0x180005548  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18000554c  mov     [rbp+Buffer], rsi
0x180005550  mov     r8d, 20801h; DesiredAccess
0x180005556  mov     [rbp+var_40], rsi
0x18000555a  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18000555e  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180005562  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x180005566  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000556b  call    cs:__imp_LsaOpenPolicy
0x180005571  mov     ebx, eax
0x180005573  test    eax, eax
0x180005575  jns     short loc_1800055D1
0x180005577  test    byte ptr cs:g_dwDebugFlags, 3
0x18000557e  jz      short loc_1800055B1
0x180005580  mov     rcx, cs:g_pDebug
0x180005587  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x18000558e  mov     [rsp+70h+var_48], eax
0x180005592  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005599  lea     rax, aCannotOpenLsaP; "cannot open lsa policy, error %08lX\n"
0x1800055a0  mov     r8d, 140h
0x1800055a6  mov     [rsp+70h+var_50], rax
0x1800055ab  call    cs:__imp_PuDbgPrint
0x1800055b1  mov     ecx, ebx; Status
0x1800055b3  call    cs:__imp_RtlNtStatusToDosError
0x1800055b9  mov     ebx, eax
0x1800055bb  test    eax, eax
0x1800055bd  jle     short loc_1800055C8
0x1800055bf  movzx   ebx, ax
0x1800055c2  or      ebx, 80070000h
0x1800055c8  mov     [rbp+PolicyHandle], rsi
0x1800055cc  jmp     loc_1800056D2
0x1800055d1  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800055d5  lea     r8, [rbp+Buffer]; Buffer
0x1800055d9  mov     edx, 5; InformationClass
0x1800055de  call    cs:__imp_LsaQueryInformationPolicy
0x1800055e4  mov     ebx, eax
0x1800055e6  test    eax, eax
0x1800055e8  jns     short loc_180005644
0x1800055ea  test    byte ptr cs:g_dwDebugFlags, 3
0x1800055f1  jz      short loc_180005624
0x1800055f3  mov     r8d, 15Bh
0x1800055f9  mov     rcx, cs:g_pDebug
0x180005600  lea     rax, aCannotQueryLsa; "cannot query lsa policy info, error %08"...
0x180005607  mov     [rsp+70h+var_48], ebx
0x18000560b  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x180005612  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005619  mov     [rsp+70h+var_50], rax
0x18000561e  call    cs:__imp_PuDbgPrint
0x180005624  mov     ecx, ebx; Status
0x180005626  call    cs:__imp_RtlNtStatusToDosError
0x18000562c  mov     ebx, eax
0x18000562e  test    eax, eax
0x180005630  jle     loc_1800056D2
0x180005636  movzx   ebx, ax
0x180005639  or      ebx, 80070000h
0x18000563f  jmp     loc_1800056D2
0x180005644  mov     r8, [rbp+Buffer]
0x180005648  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000564c  mov     edx, 100h; SizeInWords
0x180005651  mov     rcx, rdi; Destination
0x180005654  mov     r8, [r8+8]; Source
0x180005658  call    cs:__imp_wcsncpy_s
0x18000565e  cmp     eax, 50h ; 'P'
0x180005661  jnz     short loc_18000566A
0x180005663  mov     ebx, 8007007Ah
0x180005668  jmp     short loc_1800056D2
0x18000566a  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18000566e  lea     r8, [rbp+var_40]; Buffer
0x180005672  mov     edx, 3; InformationClass
0x180005677  call    cs:__imp_LsaQueryInformationPolicy
0x18000567d  mov     ebx, eax
0x18000567f  test    eax, eax
0x180005681  jns     short loc_180005697
0x180005683  test    byte ptr cs:g_dwDebugFlags, 3
0x18000568a  jz      short loc_180005624
0x18000568c  mov     r8d, 17Ch
0x180005692  jmp     loc_1800055F9
0x180005697  mov     rax, [rbp+var_40]
0x18000569b  mov     ebx, esi
0x18000569d  cmp     [rax+10h], rsi
0x1800056a1  jz      short loc_1800056CC
0x1800056a3  lea     rdx, [rdi+200h]; lpBuffer
0x1800056aa  mov     dword ptr [rdi+0A00h], 1
0x1800056b4  lea     r8, [rbp+nSize]; nSize
0x1800056b8  mov     [rbp+nSize], 400h
0x1800056bf  mov     ecx, 2; NameType
0x1800056c4  call    cs:__imp_GetComputerNameExW
0x1800056ca  jmp     short loc_1800056D2
0x1800056cc  mov     [rdi+0A00h], esi
0x1800056d2  mov     rcx, [rbp+Buffer]; Buffer
0x1800056d6  test    rcx, rcx
0x1800056d9  jz      short loc_1800056E5
0x1800056db  call    cs:__imp_LsaFreeMemory
0x1800056e1  mov     [rbp+Buffer], rsi
0x1800056e5  mov     rcx, [rbp+var_40]; Buffer
0x1800056e9  test    rcx, rcx
0x1800056ec  jz      short loc_1800056F8
0x1800056ee  call    cs:__imp_LsaFreeMemory
0x1800056f4  mov     [rbp+var_40], rsi
0x1800056f8  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800056fc  test    rcx, rcx
0x1800056ff  jz      short loc_180005707
0x180005701  call    cs:__imp_LsaClose
0x180005707  mov     eax, ebx
0x180005709  mov     rbx, [rsp+70h+arg_0]
0x180005711  add     rsp, 70h
0x180005715  pop     rdi
0x180005716  pop     rsi
0x180005717  pop     rbp
0x180005718  retn
```
