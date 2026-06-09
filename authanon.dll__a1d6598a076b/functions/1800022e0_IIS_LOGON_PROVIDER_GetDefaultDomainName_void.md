# IIS_LOGON_PROVIDER::GetDefaultDomainName(void)

- ea: `0x1800022e0`
- end: `0x180002522`
- name: `?GetDefaultDomainName@IIS_LOGON_PROVIDER@@AEAAJXZ`
- size: `578`
- prototype: `__int64 __fastcall(wchar_t *Destination)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000570c`

## callees

- `0x1800022e0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000241f`
- `msvcrt!wcsncpy_s` at `0x18000241f`
- `ntdll!RtlNtStatusToDosError` at `0x180002377`
- `ntdll!RtlNtStatusToDosError` at `0x1800023ea`
- `ntdll!RtlNtStatusToDosError` at `0x180002489`
- `ntdll!RtlNtStatusToDosError` at `0x180002377`
- `ntdll!RtlNtStatusToDosError` at `0x1800023ea`
- `ntdll!RtlNtStatusToDosError` at `0x180002489`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800024cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800024cd`
- `iisutil!PuDbgPrint` at `0x18000236f`
- `iisutil!PuDbgPrint` at `0x1800023e2`
- `iisutil!PuDbgPrint` at `0x180002481`
- `iisutil!PuDbgPrint` at `0x18000236f`
- `iisutil!PuDbgPrint` at `0x1800023e2`
- `iisutil!PuDbgPrint` at `0x180002481`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800024e4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800024f7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800024e4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800024f7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000232f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000232f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800023a2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180002441`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800023a2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180002441`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000250a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000250a`

## string_xrefs

- `0x18000235d`: `cannot open lsa policy, error %08lX\n`
- `0x180002356`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x1800023c9`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180002468`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::GetDefaultDomainName(wchar_t *Destination)
{
  NTSTATUS v2; // eax
  NTSTATUS v3; // ebx
  signed int v4; // eax
  unsigned int v5; // ebx
  NTSTATUS v6; // eax
  NTSTATUS v7; // ebx
  signed int v8; // eax
  NTSTATUS v9; // eax
  NTSTATUS v10; // ebx
  signed int v11; // eax
  PVOID v13; // [rsp+30h] [rbp-40h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF
  DWORD nSize; // [rsp+98h] [rbp+28h] BYREF
  PVOID PolicyHandle; // [rsp+A0h] [rbp+30h] BYREF
  PVOID Buffer; // [rsp+A8h] [rbp+38h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  nSize = 0;
  PolicyHandle = 0;
  Buffer = 0;
  v13 = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 0x20801u, &PolicyHandle);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
    v7 = v6;
    if ( v6 >= 0 )
    {
      if ( wcsncpy_s(Destination, 0x100u, *((const wchar_t **)Buffer + 1), 0xFFFFFFFFFFFFFFFFuLL) == 80 )
      {
        v5 = -2147024774;
      }
      else
      {
        v9 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &v13);
        v10 = v9;
        if ( v9 >= 0 )
        {
          v5 = 0;
          if ( *((_QWORD *)v13 + 2) )
          {
            *((_DWORD *)Destination + 640) = 1;
            nSize = 1024;
            GetComputerNameExW(ComputerNameDnsDomain, Destination + 256, &nSize);
          }
          else
          {
            *((_DWORD *)Destination + 640) = 0;
          }
        }
        else
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
              380,
              "IIS_LOGON_PROVIDER::GetDefaultDomainName",
              "cannot query lsa policy info, error %08lX\n",
              v9);
          v11 = RtlNtStatusToDosError(v10);
          v5 = v11;
          if ( v11 > 0 )
            v5 = (unsigned __int16)v11 | 0x80070000;
        }
      }
    }
    else
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
          347,
          "IIS_LOGON_PROVIDER::GetDefaultDomainName",
          "cannot query lsa policy info, error %08lX\n",
          v6);
      v8 = RtlNtStatusToDosError(v7);
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
    }
  }
  else
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
  }
  if ( Buffer )
  {
    LsaFreeMemory(Buffer);
    Buffer = 0;
  }
  if ( v13 )
  {
    LsaFreeMemory(v13);
    v13 = 0;
  }
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v5;
}

```

## disassembly

```asm
0x1800022e0  mov     [rsp-18h+arg_0], rbx
0x1800022e5  push    rbp
0x1800022e6  push    rsi
0x1800022e7  push    rdi
0x1800022e8  mov     rbp, rsp
0x1800022eb  sub     rsp, 70h
0x1800022ef  xor     esi, esi
0x1800022f1  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800022f9  mov     rdi, rcx
0x1800022fc  mov     qword ptr [rbp+ObjectAttributes.Attributes], rsi
0x180002300  xorps   xmm0, xmm0
0x180002303  mov     [rbp+nSize], esi
0x180002306  xor     ecx, ecx; SystemName
0x180002308  mov     [rbp+PolicyHandle], rsi
0x18000230c  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180002310  mov     [rbp+Buffer], rsi
0x180002314  mov     r8d, 20801h; DesiredAccess
0x18000231a  mov     [rbp+var_40], rsi
0x18000231e  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180002322  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180002326  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x18000232a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000232f  call    cs:__imp_LsaOpenPolicy
0x180002335  mov     ebx, eax
0x180002337  test    eax, eax
0x180002339  jns     short loc_180002395
0x18000233b  test    byte ptr cs:g_dwDebugFlags, 3
0x180002342  jz      short loc_180002375
0x180002344  mov     rcx, cs:g_pDebug
0x18000234b  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x180002352  mov     [rsp+70h+var_48], eax
0x180002356  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000235d  lea     rax, aCannotOpenLsaP; "cannot open lsa policy, error %08lX\n"
0x180002364  mov     r8d, 140h
0x18000236a  mov     [rsp+70h+var_50], rax
0x18000236f  call    cs:__imp_PuDbgPrint
0x180002375  mov     ecx, ebx; Status
0x180002377  call    cs:__imp_RtlNtStatusToDosError
0x18000237d  mov     ebx, eax
0x18000237f  test    eax, eax
0x180002381  jle     short loc_18000238C
0x180002383  movzx   ebx, ax
0x180002386  or      ebx, 80070000h
0x18000238c  mov     [rbp+PolicyHandle], rsi
0x180002390  jmp     loc_1800024DB
0x180002395  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180002399  lea     r8, [rbp+Buffer]; Buffer
0x18000239d  mov     edx, 5; InformationClass
0x1800023a2  call    cs:__imp_LsaQueryInformationPolicy
0x1800023a8  mov     ebx, eax
0x1800023aa  test    eax, eax
0x1800023ac  jns     short loc_180002408
0x1800023ae  test    byte ptr cs:g_dwDebugFlags, 3
0x1800023b5  jz      short loc_1800023E8
0x1800023b7  mov     rcx, cs:g_pDebug
0x1800023be  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x1800023c5  mov     [rsp+70h+var_48], eax
0x1800023c9  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800023d0  lea     rax, aCannotQueryLsa; "cannot query lsa policy info, error %08"...
0x1800023d7  mov     r8d, 15Bh
0x1800023dd  mov     [rsp+70h+var_50], rax
0x1800023e2  call    cs:__imp_PuDbgPrint
0x1800023e8  mov     ecx, ebx; Status
0x1800023ea  call    cs:__imp_RtlNtStatusToDosError
0x1800023f0  mov     ebx, eax
0x1800023f2  test    eax, eax
0x1800023f4  jle     loc_1800024DB
0x1800023fa  movzx   ebx, ax
0x1800023fd  or      ebx, 80070000h
0x180002403  jmp     loc_1800024DB
0x180002408  mov     r8, [rbp+Buffer]
0x18000240c  mov     r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180002413  mov     edx, 100h; SizeInWords
0x180002418  mov     rcx, rdi; Destination
0x18000241b  mov     r8, [r8+8]; Source
0x18000241f  call    cs:__imp_wcsncpy_s
0x180002425  cmp     eax, 50h ; 'P'
0x180002428  jnz     short loc_180002434
0x18000242a  mov     ebx, 8007007Ah
0x18000242f  jmp     loc_1800024DB
0x180002434  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180002438  lea     r8, [rbp+var_40]; Buffer
0x18000243c  mov     edx, 3; InformationClass
0x180002441  call    cs:__imp_LsaQueryInformationPolicy
0x180002447  mov     ebx, eax
0x180002449  test    eax, eax
0x18000244b  jns     short loc_1800024A0
0x18000244d  test    byte ptr cs:g_dwDebugFlags, 3
0x180002454  jz      short loc_180002487
0x180002456  mov     rcx, cs:g_pDebug
0x18000245d  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x180002464  mov     [rsp+70h+var_48], eax
0x180002468  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000246f  lea     rax, aCannotQueryLsa; "cannot query lsa policy info, error %08"...
0x180002476  mov     r8d, 17Ch
0x18000247c  mov     [rsp+70h+var_50], rax
0x180002481  call    cs:__imp_PuDbgPrint
0x180002487  mov     ecx, ebx; Status
0x180002489  call    cs:__imp_RtlNtStatusToDosError
0x18000248f  mov     ebx, eax
0x180002491  test    eax, eax
0x180002493  jle     short loc_1800024DB
0x180002495  movzx   ebx, ax
0x180002498  or      ebx, 80070000h
0x18000249e  jmp     short loc_1800024DB
0x1800024a0  mov     rax, [rbp+var_40]
0x1800024a4  mov     ebx, esi
0x1800024a6  cmp     [rax+10h], rbx
0x1800024aa  jz      short loc_1800024D5
0x1800024ac  lea     rdx, [rdi+200h]; lpBuffer
0x1800024b3  mov     dword ptr [rdi+0A00h], 1
0x1800024bd  lea     r8, [rbp+nSize]; nSize
0x1800024c1  mov     [rbp+nSize], 400h
0x1800024c8  mov     ecx, 2; NameType
0x1800024cd  call    cs:__imp_GetComputerNameExW
0x1800024d3  jmp     short loc_1800024DB
0x1800024d5  mov     [rdi+0A00h], esi
0x1800024db  mov     rcx, [rbp+Buffer]; Buffer
0x1800024df  test    rcx, rcx
0x1800024e2  jz      short loc_1800024EE
0x1800024e4  call    cs:__imp_LsaFreeMemory
0x1800024ea  mov     [rbp+Buffer], rsi
0x1800024ee  mov     rcx, [rbp+var_40]; Buffer
0x1800024f2  test    rcx, rcx
0x1800024f5  jz      short loc_180002501
0x1800024f7  call    cs:__imp_LsaFreeMemory
0x1800024fd  mov     [rbp+var_40], rsi
0x180002501  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180002505  test    rcx, rcx
0x180002508  jz      short loc_180002510
0x18000250a  call    cs:__imp_LsaClose
0x180002510  mov     eax, ebx
0x180002512  mov     rbx, [rsp+70h+arg_0]
0x18000251a  add     rsp, 70h
0x18000251e  pop     rdi
0x18000251f  pop     rsi
0x180002520  pop     rbp
0x180002521  retn
```
