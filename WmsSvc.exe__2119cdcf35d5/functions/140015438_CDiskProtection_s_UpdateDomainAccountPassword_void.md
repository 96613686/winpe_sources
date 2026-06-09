# CDiskProtection::s_UpdateDomainAccountPassword(void)

- ea: `0x140015438`
- end: `0x14001586d`
- name: `?s_UpdateDomainAccountPassword@CDiskProtection@@SAJXZ`
- size: `1077`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140009778`
- `0x140033ca0`
- `0x140035ec0`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x140014210`
- `0x140015438`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!LsaOpenPolicy` at `0x140015502`
- `ADVAPI32!LsaOpenPolicy` at `0x140015502`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1400155c9`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1400155c9`
- `ADVAPI32!LsaFreeMemory` at `0x14001583b`
- `ADVAPI32!LsaFreeMemory` at `0x14001583b`
- `ADVAPI32!LsaClose` at `0x140015845`
- `ADVAPI32!LsaClose` at `0x140015845`
- `KERNEL32!GetComputerNameW` at `0x1400154a6`
- `KERNEL32!GetComputerNameW` at `0x1400154a6`
- `KERNEL32!GetLastError` at `0x1400154b0`
- `KERNEL32!GetLastError` at `0x1400154b0`
- `KERNEL32!IsDebuggerPresent` at `0x140015555`
- `KERNEL32!IsDebuggerPresent` at `0x140015618`
- `KERNEL32!IsDebuggerPresent` at `0x1400156af`
- `KERNEL32!IsDebuggerPresent` at `0x140015779`
- `KERNEL32!IsDebuggerPresent` at `0x140015555`
- `KERNEL32!IsDebuggerPresent` at `0x140015618`
- `KERNEL32!IsDebuggerPresent` at `0x1400156af`
- `KERNEL32!IsDebuggerPresent` at `0x140015779`

## string_xrefs

- `0x14001546c`: `CDiskProtection::s_UpdateDomainAccountPassword\n`
- `0x140015528`: `CDiskProtection::s_UpdateDomainAccountPassword`
- `0x1400155eb`: `CDiskProtection::s_UpdateDomainAccountPassword`
- `0x140015676`: `CDiskProtection::s_UpdateDomainAccountPassword`
- `0x140015740`: `CDiskProtection::s_UpdateDomainAccountPassword`
- `0x1400157f0`: `CDiskProtection::s_UpdateDomainAccountPassword - %s is part of domain %s, attempting to reset domain account password.\n`
- `0x140015823`: `CDiskProtection::s_UpdateDomainAccountPassword - %s is not part of a domain, exiting gracefully.\n`
- `0x14001580e`: `CDiskProtection::s_UpdateDomainAccountPassword - Attempt to reset domain account password succeeded.\n`
- `0x1400157b6`: `CDiskProtection::s_UpdateDomainAccountPassword - Attempt to reset domain account password failed, hr = 0x%08X.\n`

## pseudocode

```c
__int64 CDiskProtection::s_UpdateDomainAccountPassword(void)
{
  unsigned __int16 *v0; // rdi
  signed int LastError; // eax
  signed int v2; // ebx
  NTSTATUS v3; // eax
  __int64 v4; // r9
  __int64 v5; // r8
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  unsigned __int64 v8; // rsi
  unsigned __int16 *v9; // rdx
  __int64 v10; // rcx
  unsigned __int16 *v11; // r8
  unsigned __int16 *v12; // rcx
  DWORD nSize; // [rsp+40h] [rbp-69h] BYREF
  PVOID v15; // [rsp+48h] [rbp-61h] BYREF
  PVOID PolicyHandle; // [rsp+50h] [rbp-59h] BYREF
  _LSA_UNICODE_STRING SystemName; // [rsp+58h] [rbp-51h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-41h] BYREF
  WCHAR Buffer[8]; // [rsp+98h] [rbp-11h] BYREF
  __int128 v20; // [rsp+A8h] [rbp-1h]

  nSize = 16;
  PolicyHandle = 0;
  v15 = 0;
  v0 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  SystemName = 0;
  *(_OWORD *)Buffer = 0;
  v20 = 0;
  DEBUGMSG(L"CDiskProtection::s_UpdateDomainAccountPassword\n");
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 >= 0 )
      v2 = -2147467259;
    goto LABEL_40;
  }
  SystemName.Buffer = Buffer;
  SystemName.Length = 2 * nSize;
  SystemName.MaximumLength = 32;
  v3 = LsaOpenPolicy(&SystemName, &ObjectAttributes, 0x80000001, &PolicyHandle);
  v2 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x137Du,
      L"CDiskProtection::s_UpdateDomainAccountPassword",
      L"CBRAEx",
      L"status == ((NTSTATUS)0x00000000L)",
      v2);
    if ( IsDebuggerPresent() )
    {
      v4 = 4989;
LABEL_12:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v4,
        L"CDiskProtection::s_UpdateDomainAccountPassword",
        L"CBRAEx",
        L"status == ((NTSTATUS)0x00000000L)",
        v2);
      goto LABEL_40;
    }
    v5 = 4989;
    goto LABEL_14;
  }
  v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &v15);
  v2 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x1380u,
      L"CDiskProtection::s_UpdateDomainAccountPassword",
      L"CBRAEx",
      L"status == ((NTSTATUS)0x00000000L)",
      v2);
    if ( IsDebuggerPresent() )
    {
      v4 = 4992;
      goto LABEL_12;
    }
    v5 = 4992;
LABEL_14:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v5,
      L"CDiskProtection::s_UpdateDomainAccountPassword",
      L"CBRAEx",
      L"status == ((NTSTATUS)0x00000000L)",
      v2);
    goto LABEL_40;
  }
  if ( !*((_QWORD *)v15 + 2) )
  {
    v2 = 0;
    DEBUGMSG(
      L"CDiskProtection::s_UpdateDomainAccountPassword - %s is not part of a domain, exiting gracefully.\n",
      Buffer);
    goto LABEL_40;
  }
  v7 = *(unsigned __int16 *)v15 >> 1;
  v8 = v7 + 1;
  v0 = (unsigned __int16 *)operator new(saturated_mul(v8, 2u));
  if ( v0 )
  {
    v9 = v0;
    v10 = v7;
    v11 = (unsigned __int16 *)*((_QWORD *)v15 + 1);
    do
    {
      if ( !v10 )
        break;
      if ( !*v11 )
        break;
      *v9++ = *v11++;
      --v10;
      --v8;
    }
    while ( v8 );
    v12 = v9 - 1;
    v2 = v8 == 0 ? 0x8007007A : 0;
    if ( v8 )
      v12 = v9;
    *v12 = 0;
    if ( v8 )
    {
      DEBUGMSG(
        L"CDiskProtection::s_UpdateDomainAccountPassword - %s is part of domain %s, attempting to reset domain account password.\n",
        Buffer,
        v0);
      v2 = CDiskProtection::s_ResetServer(v0, Buffer);
      if ( v2 >= 0 )
      {
        DEBUGMSG(L"CDiskProtection::s_UpdateDomainAccountPassword - Attempt to reset domain account password succeeded.\n");
        goto LABEL_40;
      }
    }
    else
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        0x138Du,
        L"CDiskProtection::s_UpdateDomainAccountPassword",
        L"CHRA",
        L"hr",
        -2147024774);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          5005,
          L"CDiskProtection::s_UpdateDomainAccountPassword",
          L"CHRA",
          L"hr",
          v8 == 0 ? 0x8007007A : 0);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          5005,
          L"CDiskProtection::s_UpdateDomainAccountPassword",
          L"CHRA",
          L"hr",
          v8 == 0 ? 0x8007007A : 0);
    }
    DEBUGMSG(
      L"CDiskProtection::s_UpdateDomainAccountPassword - Attempt to reset domain account password failed, hr = 0x%08X.\n",
      (unsigned int)v2);
  }
  else
  {
    v2 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x138Au,
      L"CDiskProtection::s_UpdateDomainAccountPassword",
      L"CPR",
      L"pszDomainName",
      -2147024882);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        5002,
        L"CDiskProtection::s_UpdateDomainAccountPassword",
        L"CPR",
        L"pszDomainName",
        -2147024882);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        5002,
        L"CDiskProtection::s_UpdateDomainAccountPassword",
        L"CPR",
        L"pszDomainName",
        -2147024882);
  }
LABEL_40:
  operator delete(v0);
  LsaFreeMemory(v15);
  LsaClose(PolicyHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140015438  push    rbp
0x14001543a  push    rbx
0x14001543b  push    rsi
0x14001543c  push    rdi
0x14001543d  push    r12
0x14001543f  push    r13
0x140015441  push    r14
0x140015443  push    r15
0x140015445  lea     rbp, [rsp-1Fh]
0x14001544a  sub     rsp, 0C8h
0x140015451  mov     rax, cs:__security_cookie
0x140015458  xor     rax, rsp
0x14001545b  mov     [rbp+57h+var_48], rax
0x14001545f  xorps   xmm0, xmm0
0x140015462  mov     [rbp+57h+nSize], 10h
0x140015469  xor     r13d, r13d
0x14001546c  lea     rcx, aCdiskprotectio_84; "CDiskProtection::s_UpdateDomainAccountP"...
0x140015473  xorps   xmm1, xmm1
0x140015476  mov     [rbp+57h+PolicyHandle], r13
0x14001547a  mov     [rbp+57h+var_B8], r13
0x14001547e  mov     edi, r13d
0x140015481  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140015485  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140015489  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001548d  movups  xmmword ptr [rbp+57h+SystemName.Length], xmm0
0x140015491  movups  xmmword ptr [rbp+57h+Buffer], xmm1
0x140015495  movups  [rbp+57h+var_58], xmm1
0x140015499  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14001549e  lea     rdx, [rbp+57h+nSize]; nSize
0x1400154a2  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x1400154a6  call    cs:__imp_GetComputerNameW
0x1400154ac  test    eax, eax
0x1400154ae  jnz     short loc_1400154D4
0x1400154b0  call    cs:__imp_GetLastError
0x1400154b6  mov     ebx, eax
0x1400154b8  test    eax, eax
0x1400154ba  jle     short loc_1400154C5
0x1400154bc  movzx   ebx, ax
0x1400154bf  or      ebx, 80070000h
0x1400154c5  test    ebx, ebx
0x1400154c7  mov     eax, 80004005h
0x1400154cc  cmovns  ebx, eax
0x1400154cf  jmp     loc_14001582F
0x1400154d4  lea     rax, [rbp+57h+Buffer]
0x1400154d8  mov     r8d, 80000001h; DesiredAccess
0x1400154de  mov     [rbp+57h+SystemName.Buffer], rax
0x1400154e2  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x1400154e6  movzx   eax, word ptr [rbp+57h+nSize]
0x1400154ea  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400154ee  add     ax, ax
0x1400154f1  lea     rcx, [rbp+57h+SystemName]; SystemName
0x1400154f5  mov     [rbp+57h+SystemName.Length], ax
0x1400154f9  mov     eax, 20h ; ' '
0x1400154fe  mov     [rbp+57h+SystemName.MaximumLength], ax
0x140015502  call    cs:__imp_LsaOpenPolicy
0x140015508  mov     ebx, eax
0x14001550a  test    eax, eax
0x14001550c  jz      loc_1400155BC
0x140015512  jle     short loc_14001551D
0x140015514  movzx   ebx, ax
0x140015517  or      ebx, 80070000h
0x14001551d  lea     r12, aCbraex; "CBRAEx"
0x140015524  mov     [rsp+100h+var_D8], ebx; int
0x140015528  lea     r14, aCdiskprotectio_86; "CDiskProtection::s_UpdateDomainAccountP"...
0x14001552f  mov     r9, r12; unsigned __int16 *
0x140015532  lea     rsi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140015539  mov     r8, r14; unsigned __int16 *
0x14001553c  lea     r15, aStatusNtstatus_0; "status == ((NTSTATUS)0x00000000L)"
0x140015543  mov     rcx, rsi; unsigned __int16 *
0x140015546  mov     edx, 137Dh; unsigned int
0x14001554b  mov     [rsp+100h+var_E0], r15; unsigned __int16 *
0x140015550  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140015555  call    cs:__imp_IsDebuggerPresent
0x14001555b  test    eax, eax
0x14001555d  jz      short loc_140015591
0x14001555f  mov     r9d, 137Dh
0x140015565  mov     [rsp+100h+var_C8], ebx
0x140015569  mov     [rsp+100h+var_D0], r15
0x14001556e  mov     qword ptr [rsp+100h+var_D8], r12
0x140015573  mov     r8, rsi
0x140015576  mov     [rsp+100h+var_E0], r14
0x14001557b  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140015582  mov     ecx, 2; unsigned __int8
0x140015587  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14001558c  jmp     loc_14001582F
0x140015591  mov     r8d, 137Dh
0x140015597  mov     dword ptr [rsp+100h+var_D0], ebx
0x14001559b  mov     qword ptr [rsp+100h+var_D8], r15
0x1400155a0  mov     [rsp+100h+var_E0], r12
0x1400155a5  mov     r9, r14
0x1400155a8  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400155af  mov     rdx, rsi
0x1400155b2  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400155b7  jmp     loc_14001582F
0x1400155bc  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x1400155c0  lea     r8, [rbp+57h+var_B8]; Buffer
0x1400155c4  mov     edx, 0Ch; InformationClass
0x1400155c9  call    cs:__imp_LsaQueryInformationPolicy
0x1400155cf  mov     ebx, eax
0x1400155d1  test    eax, eax
0x1400155d3  jz      short loc_140015638
0x1400155d5  jle     short loc_1400155E0
0x1400155d7  movzx   ebx, ax
0x1400155da  or      ebx, 80070000h
0x1400155e0  lea     r12, aCbraex; "CBRAEx"
0x1400155e7  mov     [rsp+100h+var_D8], ebx; int
0x1400155eb  lea     r14, aCdiskprotectio_86; "CDiskProtection::s_UpdateDomainAccountP"...
0x1400155f2  mov     r9, r12; unsigned __int16 *
0x1400155f5  lea     rsi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x1400155fc  mov     r8, r14; unsigned __int16 *
0x1400155ff  lea     r15, aStatusNtstatus_0; "status == ((NTSTATUS)0x00000000L)"
0x140015606  mov     rcx, rsi; unsigned __int16 *
0x140015609  mov     edx, 1380h; unsigned int
0x14001560e  mov     [rsp+100h+var_E0], r15; unsigned __int16 *
0x140015613  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140015618  call    cs:__imp_IsDebuggerPresent
0x14001561e  test    eax, eax
0x140015620  jz      short loc_14001562D
0x140015622  mov     r9d, 1380h
0x140015628  jmp     loc_140015565
0x14001562d  mov     r8d, 1380h
0x140015633  jmp     loc_140015597
0x140015638  mov     rax, [rbp+57h+var_B8]
0x14001563c  cmp     [rax+10h], r13
0x140015640  jz      loc_14001581C
0x140015646  movzx   ebx, word ptr [rax]
0x140015649  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140015650  shr     ebx, 1
0x140015652  mov     eax, 2
0x140015657  lea     esi, [rbx+1]
0x14001565a  mul     rsi
0x14001565d  cmovb   rax, rcx
0x140015661  mov     rcx, rax; Size
0x140015664  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015669  mov     rdi, rax
0x14001566c  test    rax, rax
0x14001566f  jnz     short loc_1400156EC
0x140015671  mov     ebx, 8007000Eh
0x140015676  lea     r14, aCdiskprotectio_86; "CDiskProtection::s_UpdateDomainAccountP"...
0x14001567d  mov     r15d, 138Ah
0x140015683  mov     [rsp+100h+var_D8], ebx; int
0x140015687  lea     rsi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14001568e  mov     r8, r14; unsigned __int16 *
0x140015691  lea     r12, aPszdomainname; "pszDomainName"
0x140015698  mov     edx, r15d; unsigned int
0x14001569b  mov     rcx, rsi; unsigned __int16 *
0x14001569e  mov     [rsp+100h+var_E0], r12; unsigned __int16 *
0x1400156a3  lea     r9, aCpr; "CPR"
0x1400156aa  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400156af  call    cs:__imp_IsDebuggerPresent
0x1400156b5  test    eax, eax
0x1400156b7  lea     rax, aCpr; "CPR"
0x1400156be  jz      short loc_1400156D6
0x1400156c0  mov     [rsp+100h+var_C8], ebx
0x1400156c4  mov     r9d, r15d
0x1400156c7  mov     [rsp+100h+var_D0], r12
0x1400156cc  mov     qword ptr [rsp+100h+var_D8], rax
0x1400156d1  jmp     loc_140015573
0x1400156d6  mov     dword ptr [rsp+100h+var_D0], ebx
0x1400156da  mov     r8d, r15d
0x1400156dd  mov     qword ptr [rsp+100h+var_D8], r12
0x1400156e2  mov     [rsp+100h+var_E0], rax
0x1400156e7  jmp     loc_1400155A5
0x1400156ec  mov     rax, [rbp+57h+var_B8]
0x1400156f0  mov     rdx, rdi
0x1400156f3  mov     ecx, ebx
0x1400156f5  mov     r8, [rax+8]
0x1400156f9  test    rcx, rcx
0x1400156fc  jz      short loc_14001571B
0x1400156fe  movzx   eax, word ptr [r8]
0x140015702  test    ax, ax
0x140015705  jz      short loc_14001571B
0x140015707  mov     [rdx], ax
0x14001570a  add     r8, 2
0x14001570e  add     rdx, 2
0x140015712  dec     rcx
0x140015715  sub     rsi, 1
0x140015719  jnz     short loc_1400156F9
0x14001571b  mov     rax, rsi
0x14001571e  lea     rcx, [rdx-2]
0x140015722  neg     rax
0x140015725  sbb     ebx, ebx
0x140015727  not     ebx
0x140015729  and     ebx, 8007007Ah
0x14001572f  test    rsi, rsi
0x140015732  cmovnz  rcx, rdx
0x140015736  mov     [rcx], r13w
0x14001573a  jnz     loc_1400157E9
0x140015740  lea     r14, aCdiskprotectio_86; "CDiskProtection::s_UpdateDomainAccountP"...
0x140015747  mov     [rsp+100h+var_D8], ebx; int
0x14001574b  mov     r15d, 138Dh
0x140015751  lea     rsi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140015758  lea     r12, aHr; "hr"
0x14001575f  mov     r8, r14; unsigned __int16 *
0x140015762  mov     edx, r15d; unsigned int
0x140015765  mov     [rsp+100h+var_E0], r12; unsigned __int16 *
0x14001576a  mov     rcx, rsi; unsigned __int16 *
0x14001576d  lea     r9, aChra; "CHRA"
0x140015774  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140015779  call    cs:__imp_IsDebuggerPresent
0x14001577f  test    eax, eax
0x140015781  lea     rax, aChra; "CHRA"
0x140015788  jz      short loc_1400157C4
0x14001578a  mov     [rsp+100h+var_C8], ebx
0x14001578e  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140015795  mov     [rsp+100h+var_D0], r12
0x14001579a  mov     r9d, r15d
0x14001579d  mov     qword ptr [rsp+100h+var_D8], rax
0x1400157a2  mov     r8, rsi
0x1400157a5  mov     ecx, 2; unsigned __int8
0x1400157aa  mov     [rsp+100h+var_E0], r14
0x1400157af  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400157b4  mov     edx, ebx
0x1400157b6  lea     rcx, aCdiskprotectio_58; "CDiskProtection::s_UpdateDomainAccountP"...
0x1400157bd  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400157c2  jmp     short loc_14001582F
0x1400157c4  mov     dword ptr [rsp+100h+var_D0], ebx
0x1400157c8  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400157cf  mov     qword ptr [rsp+100h+var_D8], r12
0x1400157d4  mov     r9, r14
0x1400157d7  mov     r8d, r15d
0x1400157da  mov     [rsp+100h+var_E0], rax
0x1400157df  mov     rdx, rsi
0x1400157e2  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400157e7  jmp     short loc_1400157B4
0x1400157e9  mov     r8, rdi
0x1400157ec  lea     rdx, [rbp+57h+Buffer]
0x1400157f0  lea     rcx, aCdiskprotectio_24; "CDiskProtection::s_UpdateDomainAccountP"...
0x1400157f7  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400157fc  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x140015800  mov     rcx, rdi; unsigned __int16 *
0x140015803  call    ?s_ResetServer@CDiskProtection@@KAJPEBG0@Z; CDiskProtection::s_ResetServer(ushort const *,ushort const *)
0x140015808  mov     ebx, eax
0x14001580a  test    eax, eax
0x14001580c  js      short loc_1400157B4
0x14001580e  lea     rcx, aCdiskprotectio_102; "CDiskProtection::s_UpdateDomainAccountP"...
0x140015815  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14001581a  jmp     short loc_14001582F
0x14001581c  lea     rdx, [rbp+57h+Buffer]
0x140015820  mov     ebx, r13d
0x140015823  lea     rcx, aCdiskprotectio_73; "CDiskProtection::s_UpdateDomainAccountP"...
0x14001582a  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14001582f  mov     rcx, rdi; Block
0x140015832  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140015837  mov     rcx, [rbp+57h+var_B8]; Buffer
0x14001583b  call    cs:__imp_LsaFreeMemory
0x140015841  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x140015845  call    cs:__imp_LsaClose
0x14001584b  mov     eax, ebx
0x14001584d  mov     rcx, [rbp+57h+var_48]
0x140015851  xor     rcx, rsp; StackCookie
0x140015854  call    __security_check_cookie
0x140015859  add     rsp, 0C8h
0x140015860  pop     r15
0x140015862  pop     r14
0x140015864  pop     r13
0x140015866  pop     r12
0x140015868  pop     rdi
0x140015869  pop     rsi
0x14001586a  pop     rbx
0x14001586b  pop     rbp
0x14001586c  retn
```
