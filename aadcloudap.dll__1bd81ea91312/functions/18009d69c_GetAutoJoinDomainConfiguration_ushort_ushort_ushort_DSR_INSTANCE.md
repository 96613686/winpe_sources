# GetAutoJoinDomainConfiguration(ushort * *,ushort * *,ushort * *,_DSR_INSTANCE *)

- ea: `0x18009d69c`
- end: `0x18009da32`
- name: `?GetAutoJoinDomainConfiguration@@YAJPEAPEAG00PEAW4_DSR_INSTANCE@@@Z`
- size: `918`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, enum _DSR_INSTANCE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180092f6c`

## callees

- `0x18001d208`
- `0x180085cc4`
- `0x180087618`
- `0x180087764`
- `0x18008aa28`
- `0x18008aa64`
- `0x18008aa9c`
- `0x18009d3a8`
- `0x18009d69c`
- `0x18009e138`
- `0x18009e4ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18009d949`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18009d949`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009d8d5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009d935`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009d9e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009d9f1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009d9fa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009da03`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009d8d5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009d935`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009d9e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009d9f1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009d9fa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009da03`

## string_xrefs

- `0x18009d96f`: `CopyStringSafeW`
- `0x18009d9a6`: `CopyStringSafeW`
- `0x18009d837`: `WriteDsRegDiscAdrsAndEntDrsFailureEvent: failed with error code: 0x%08x.`
- `0x18009d708`: `GetAutoJoinDomainConfiguration`
- `0x18009d739`: `GetAutoJoinDomainConfiguration`
- `0x18009d784`: `GetAutoJoinDomainConfiguration`
- `0x18009d876`: `GetAutoJoinDomainConfiguration`
- `0x18009d8b6`: `GetAutoJoinDomainConfiguration`
- `0x18009d976`: `GetAutoJoinDomainConfiguration`
- `0x18009d9ad`: `GetAutoJoinDomainConfiguration`
- `0x18009da0c`: `GetAutoJoinDomainConfiguration`
- `0x18009d7bc`: `%s: Read registration values from AD. tenantName: %s; tenantID: %s; enterpriseDrs: %s.`
- `0x18009d712`: `%s: Read tenant values from registry, name: %s, ID: %s.`
- `0x18009d740`: `%s: Found Enterprise DRS values from registry, name: %s`

## pseudocode

```c
__int64 __fastcall GetAutoJoinDomainConfiguration(
        unsigned __int16 **a1,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        enum _DSR_INSTANCE *a4)
{
  unsigned __int16 *v6; // r15
  int AadTenantDetailsFromRegistry; // eax
  unsigned __int16 *v8; // rsi
  unsigned __int16 *v9; // rdi
  int EnterpriseDrsDetailsFromRegistry; // eax
  unsigned __int16 *v11; // r14
  int v12; // ebx
  int RegistrationDetailsFromAD; // eax
  const WCHAR *v14; // r8
  unsigned int v15; // eax
  __int64 v16; // r9
  int v17; // eax
  int v18; // eax
  char v19; // dl
  __int16 v20; // r8
  int v21; // r9d
  int v22; // eax
  wchar_t v24; // [rsp+20h] [rbp-28h]
  long double v25; // [rsp+28h] [rbp-20h]
  unsigned __int16 *Source[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 *v27; // [rsp+90h] [rbp+48h] BYREF
  void *Block; // [rsp+98h] [rbp+50h] BYREF
  unsigned __int16 *v29; // [rsp+A0h] [rbp+58h] BYREF
  int v30; // [rsp+A8h] [rbp+60h] BYREF
  int v31; // [rsp+ACh] [rbp+64h]

  v31 = HIDWORD(a4);
  v29 = 0;
  v30 = 0;
  v6 = 0;
  v27 = 0;
  Source[0] = 0;
  Block = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  AadTenantDetailsFromRegistry = GetAadTenantDetailsFromRegistry(&v27, (unsigned __int16 **)&Block);
  v8 = v27;
  v9 = (unsigned __int16 *)Block;
  if ( AadTenantDetailsFromRegistry >= 0 && AadTenantDetailsFromRegistry != 1 )
    Logger::TraceInformation(
      L"%s: Read tenant values from registry, name: %s, ID: %s.",
      L"GetAutoJoinDomainConfiguration",
      Block,
      v27);
  EnterpriseDrsDetailsFromRegistry = GetEnterpriseDrsDetailsFromRegistry(Source);
  v11 = Source[0];
  v12 = EnterpriseDrsDetailsFromRegistry;
  if ( EnterpriseDrsDetailsFromRegistry < 0 || EnterpriseDrsDetailsFromRegistry == 1 )
    v12 = 0;
  else
    Logger::TraceInformation(
      L"%s: Found Enterprise DRS values from registry, name: %s",
      L"GetAutoJoinDomainConfiguration",
      Source[0]);
  if ( (!v9 || !*v9 || !v8 || !*v8) && (!v11 || !*v11) )
  {
    RegistrationDetailsFromAD = GetRegistrationDetailsFromAD(&v27, (unsigned __int16 **)&Block, Source);
    v12 = RegistrationDetailsFromAD;
    if ( RegistrationDetailsFromAD < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"GetAutoJoinDomainConfiguration",
        L"GetRegistrationDetailsFromAD",
        (unsigned int)RegistrationDetailsFromAD);
      v11 = Source[0];
LABEL_20:
      v8 = v27;
      v9 = (unsigned __int16 *)Block;
      goto LABEL_55;
    }
    v8 = v27;
    v9 = (unsigned __int16 *)Block;
    v11 = Source[0];
    v24 = (wchar_t)Source[0];
    Logger::TraceInformation(
      L"%s: Read registration values from AD. tenantName: %s; tenantID: %s; enterpriseDrs: %s.",
      L"GetAutoJoinDomainConfiguration",
      Block,
      v27);
  }
  if ( v9 || v8 )
  {
    if ( v11 )
    {
      v12 = -2145648611;
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
      {
        v14 = &base;
        if ( v9 )
          v14 = v9;
        v15 = McTemplateU0zz_EventWriteTransfer(
                &UserDeviceRegistrationEventProvider_Context,
                DsRegAdrsAndEnterpriseDrsDiscoveredFailureEvent,
                v14,
                v11);
        if ( v15 )
          Logger::TraceError(L"WriteDsRegDiscAdrsAndEntDrsFailureEvent: failed with error code: 0x%08x.", v15);
      }
      goto LABEL_55;
    }
    if ( v9 )
    {
      v12 = StringStartsOrEndsWithOneOf(v9, L" ", &v30);
      if ( v12 < 0 )
      {
        v16 = (unsigned int)v12;
LABEL_33:
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"GetAutoJoinDomainConfiguration",
          L"StringStartsOrEndsWithChar",
          v16);
        goto LABEL_55;
      }
      if ( v30 )
      {
        v17 = StringTrimChars(v9, L" ", &v29);
        v12 = v17;
        if ( v17 < 0 )
        {
LABEL_36:
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"GetAutoJoinDomainConfiguration",
            L"StringTrimChars",
            (unsigned int)v17);
          v6 = v29;
          goto LABEL_55;
        }
        free(v9);
        v9 = v29;
        v29 = 0;
        Block = v9;
      }
    }
    if ( v8 )
    {
      v18 = StringStartsOrEndsWithOneOf(v8, L" \"{}\n\r\t", &v30);
      v12 = v18;
      if ( v18 < 0 )
      {
        v16 = (unsigned int)v18;
        goto LABEL_33;
      }
      if ( v30 )
      {
        v17 = StringTrimChars(v8, L" \"{}\n\r\t", &v29);
        v12 = v17;
        if ( v17 < 0 )
          goto LABEL_36;
        free(v8);
        v8 = v29;
        v6 = 0;
        v27 = v29;
      }
      o((wchar_t)v8, v19, v20, v21, v24, v25);
    }
  }
  if ( v11 )
  {
    v22 = CopyStringSafeW(L"383a3889-5bc9-47a3-846c-2b70f0b7fe0e", &v27);
    v12 = v22;
    if ( v22 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"GetAutoJoinDomainConfiguration",
        L"CopyStringSafeW",
        (unsigned int)v22);
      v8 = v27;
      goto LABEL_55;
    }
    v12 = CopyStringSafeW(v11, (unsigned __int16 **)&Block);
    if ( v12 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"GetAutoJoinDomainConfiguration",
        L"CopyStringSafeW",
        (unsigned int)v12);
      goto LABEL_20;
    }
    v8 = v27;
    v9 = (unsigned __int16 *)Block;
  }
  if ( a2 )
  {
    *a2 = v9;
    v9 = 0;
  }
  if ( a3 )
  {
    *a3 = v11;
    v11 = 0;
  }
LABEL_55:
  free(v8);
  free(v9);
  free(v11);
  free(v6);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"GetAutoJoinDomainConfiguration", (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18009d69c  mov     qword ptr [rsp-40h+arg_18], r9
0x18009d6a1  mov     [rsp-40h+arg_0], rcx
0x18009d6a6  push    rbp
0x18009d6a7  push    rbx
0x18009d6a8  push    rsi
0x18009d6a9  push    rdi
0x18009d6aa  push    r12
0x18009d6ac  push    r13
0x18009d6ae  push    r14
0x18009d6b0  push    r15
0x18009d6b2  mov     rbp, rsp
0x18009d6b5  sub     rsp, 48h
0x18009d6b9  xor     eax, eax
0x18009d6bb  mov     r12, r8
0x18009d6be  mov     [rbp+arg_10], rax
0x18009d6c2  mov     r13, rdx
0x18009d6c5  mov     [rbp+arg_18], eax
0x18009d6c8  mov     r15d, eax
0x18009d6cb  mov     [rbp+arg_0], rax
0x18009d6cf  mov     [rbp+Source], rax
0x18009d6d3  mov     [rbp+Block], rax
0x18009d6d7  test    rdx, rdx
0x18009d6da  jz      short loc_18009D6DF
0x18009d6dc  mov     [rdx], rax
0x18009d6df  test    r12, r12
0x18009d6e2  jz      short loc_18009D6E7
0x18009d6e4  mov     [r8], rax
0x18009d6e7  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18009d6eb  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x18009d6ef  call    ?GetAadTenantDetailsFromRegistry@@YAJPEAPEAG0@Z; GetAadTenantDetailsFromRegistry(ushort * *,ushort * *)
0x18009d6f4  mov     rsi, [rbp+arg_0]
0x18009d6f8  mov     rdi, [rbp+Block]
0x18009d6fc  test    eax, eax
0x18009d6fe  js      short loc_18009D71E
0x18009d700  cmp     eax, 1
0x18009d703  jz      short loc_18009D71E
0x18009d705  mov     r9, rsi
0x18009d708  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18009d70f  mov     r8, rdi
0x18009d712  lea     rcx, aSReadTenantVal; "%s: Read tenant values from registry, n"...
0x18009d719  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009d71e  lea     rcx, [rbp+Source]; unsigned __int16 **
0x18009d722  call    ?GetEnterpriseDrsDetailsFromRegistry@@YAJPEAPEAG@Z; GetEnterpriseDrsDetailsFromRegistry(ushort * *)
0x18009d727  mov     r14, [rbp+Source]
0x18009d72b  mov     ebx, eax
0x18009d72d  test    eax, eax
0x18009d72f  js      short loc_18009D750
0x18009d731  cmp     eax, 1
0x18009d734  jz      short loc_18009D750
0x18009d736  mov     r8, r14
0x18009d739  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18009d740  lea     rcx, aSFoundEnterpri; "%s: Found Enterprise DRS values from re"...
0x18009d747  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009d74c  xor     eax, eax
0x18009d74e  jmp     short loc_18009D754
0x18009d750  xor     eax, eax
0x18009d752  mov     ebx, eax
0x18009d754  test    rdi, rdi
0x18009d757  jz      short loc_18009D768
0x18009d759  cmp     [rdi], ax
0x18009d75c  jz      short loc_18009D768
0x18009d75e  test    rsi, rsi
0x18009d761  jz      short loc_18009D768
0x18009d763  cmp     [rsi], ax
0x18009d766  jnz     short loc_18009D7DD
0x18009d768  test    r14, r14
0x18009d76b  jz      short loc_18009D773
0x18009d76d  cmp     [r14], ax
0x18009d771  jnz     short loc_18009D7DD
0x18009d773  lea     r8, [rbp+Source]; unsigned __int16 **
0x18009d777  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18009d77b  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x18009d77f  call    ?GetRegistrationDetailsFromAD@@YAJPEAPEAG00@Z; GetRegistrationDetailsFromAD(ushort * *,ushort * *,ushort * *)
0x18009d784  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18009d78b  mov     ebx, eax
0x18009d78d  test    eax, eax
0x18009d78f  jns     short loc_18009D7B8
0x18009d791  mov     r9d, eax
0x18009d794  lea     r8, aGetregistratio; "GetRegistrationDetailsFromAD"
0x18009d79b  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009d7a2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009d7a7  mov     r14, [rbp+Source]
0x18009d7ab  mov     rsi, [rbp+arg_0]
0x18009d7af  mov     rdi, [rbp+Block]
0x18009d7b3  jmp     loc_18009D9E5
0x18009d7b8  mov     rsi, [rbp+arg_0]
0x18009d7bc  lea     rcx, aSReadRegistrat; "%s: Read registration values from AD. t"...
0x18009d7c3  mov     rdi, [rbp+Block]
0x18009d7c7  mov     r9, rsi
0x18009d7ca  mov     r14, [rbp+Source]
0x18009d7ce  mov     r8, rdi
0x18009d7d1  mov     [rsp+48h+var_28], r14
0x18009d7d6  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009d7db  xor     eax, eax
0x18009d7dd  test    rdi, rdi
0x18009d7e0  jnz     short loc_18009D7EB
0x18009d7e2  test    rsi, rsi
0x18009d7e5  jz      loc_18009D951
0x18009d7eb  test    r14, r14
0x18009d7ee  jz      short loc_18009D848
0x18009d7f0  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18009d7f7  mov     ebx, 801C001Dh
0x18009d7fc  jz      loc_18009D9E5
0x18009d802  lea     r8, base
0x18009d809  test    r14, r14
0x18009d80c  mov     r9, r8
0x18009d80f  lea     rdx, DsRegAdrsAndEnterpriseDrsDiscoveredFailureEvent
0x18009d816  cmovnz  r9, r14
0x18009d81a  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18009d821  test    rdi, rdi
0x18009d824  cmovnz  r8, rdi
0x18009d828  call    McTemplateU0zz_EventWriteTransfer
0x18009d82d  test    eax, eax
0x18009d82f  jz      loc_18009D9E5
0x18009d835  mov     edx, eax
0x18009d837  lea     rcx, aWritedsregdisc; "WriteDsRegDiscAdrsAndEntDrsFailureEvent"...
0x18009d83e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009d843  jmp     loc_18009D9E5
0x18009d848  test    rdi, rdi
0x18009d84b  jz      loc_18009D8E9
0x18009d851  lea     r8, [rbp+arg_18]; int *
0x18009d855  mov     rcx, rdi; unsigned __int16 *
0x18009d858  lea     rdx, asc_1800BC308; " "
0x18009d85f  call    ?StringStartsOrEndsWithOneOf@@YAJPEBG0PEAH@Z; StringStartsOrEndsWithOneOf(ushort const *,ushort const *,int *)
0x18009d864  mov     ebx, eax
0x18009d866  xor     eax, eax
0x18009d868  test    ebx, ebx
0x18009d86a  jns     short loc_18009D88E
0x18009d86c  mov     r9d, ebx
0x18009d86f  lea     r8, aStringstartsor; "StringStartsOrEndsWithChar"
0x18009d876  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18009d87d  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009d884  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009d889  jmp     loc_18009D9E5
0x18009d88e  cmp     [rbp+arg_18], eax
0x18009d891  jz      short loc_18009D8E9
0x18009d893  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x18009d897  mov     rcx, rdi; unsigned __int16 *
0x18009d89a  lea     rdx, asc_1800BC308; " "
0x18009d8a1  call    ?StringTrimChars@@YAJPEBG0PEAPEAG@Z; StringTrimChars(ushort const *,ushort const *,ushort * *)
0x18009d8a6  mov     ebx, eax
0x18009d8a8  test    eax, eax
0x18009d8aa  jns     short loc_18009D8D2
0x18009d8ac  mov     r9d, eax
0x18009d8af  lea     r8, aStringtrimchar; "StringTrimChars"
0x18009d8b6  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18009d8bd  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009d8c4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009d8c9  mov     r15, [rbp+arg_10]
0x18009d8cd  jmp     loc_18009D9E5
0x18009d8d2  mov     rcx, rdi; Block
0x18009d8d5  call    cs:__imp_free
0x18009d8db  mov     rdi, [rbp+arg_10]
0x18009d8df  xor     eax, eax
0x18009d8e1  mov     [rbp+arg_10], rax
0x18009d8e5  mov     [rbp+Block], rdi
0x18009d8e9  test    rsi, rsi
0x18009d8ec  jz      short loc_18009D951
0x18009d8ee  lea     r8, [rbp+arg_18]; int *
0x18009d8f2  mov     rcx, rsi; unsigned __int16 *
0x18009d8f5  lea     rdx, asc_1800D0E40; " \"{}\n\r\t"
0x18009d8fc  call    ?StringStartsOrEndsWithOneOf@@YAJPEBG0PEAH@Z; StringStartsOrEndsWithOneOf(ushort const *,ushort const *,int *)
0x18009d901  mov     ebx, eax
0x18009d903  test    eax, eax
0x18009d905  jns     short loc_18009D90F
0x18009d907  mov     r9d, eax
0x18009d90a  jmp     loc_18009D86F
0x18009d90f  cmp     [rbp+arg_18], 0
0x18009d913  jz      short loc_18009D946
0x18009d915  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x18009d919  mov     rcx, rsi; unsigned __int16 *
0x18009d91c  lea     rdx, asc_1800D0E40; " \"{}\n\r\t"
0x18009d923  call    ?StringTrimChars@@YAJPEBG0PEAPEAG@Z; StringTrimChars(ushort const *,ushort const *,ushort * *)
0x18009d928  mov     ebx, eax
0x18009d92a  test    eax, eax
0x18009d92c  js      loc_18009D8AC
0x18009d932  mov     rcx, rsi; Block
0x18009d935  call    cs:__imp_free
0x18009d93b  mov     rsi, [rbp+arg_10]
0x18009d93f  xor     r15d, r15d
0x18009d942  mov     [rbp+arg_0], rsi
0x18009d946  mov     rcx, rsi
0x18009d949  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18009d94f  xor     eax, eax
0x18009d951  test    r14, r14
0x18009d954  jz      short loc_18009D9CD
0x18009d956  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x18009d95a  lea     rcx, a383a38895bc947; "383a3889-5bc9-47a3-846c-2b70f0b7fe0e"
0x18009d961  call    ?CopyStringSafeW@@YAJPEBGPEAPEAG@Z; CopyStringSafeW(ushort const *,ushort * *)
0x18009d966  mov     ebx, eax
0x18009d968  test    eax, eax
0x18009d96a  jns     short loc_18009D98F
0x18009d96c  mov     r9d, eax
0x18009d96f  lea     r8, aCopystringsafe; "CopyStringSafeW"
0x18009d976  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18009d97d  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009d984  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009d989  mov     rsi, [rbp+arg_0]
0x18009d98d  jmp     short loc_18009D9E5
0x18009d98f  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18009d993  mov     rcx, r14; Source
0x18009d996  call    ?CopyStringSafeW@@YAJPEBGPEAPEAG@Z; CopyStringSafeW(ushort const *,ushort * *)
0x18009d99b  mov     ebx, eax
0x18009d99d  xor     eax, eax
0x18009d99f  test    ebx, ebx
0x18009d9a1  jns     short loc_18009D9C5
0x18009d9a3  mov     r9d, ebx
0x18009d9a6  lea     r8, aCopystringsafe; "CopyStringSafeW"
0x18009d9ad  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18009d9b4  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009d9bb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009d9c0  jmp     loc_18009D7AB
0x18009d9c5  mov     rsi, [rbp+arg_0]
0x18009d9c9  mov     rdi, [rbp+Block]
0x18009d9cd  test    r13, r13
0x18009d9d0  jz      short loc_18009D9D9
0x18009d9d2  mov     [r13+0], rdi
0x18009d9d6  mov     rdi, rax
0x18009d9d9  test    r12, r12
0x18009d9dc  jz      short loc_18009D9E5
0x18009d9de  mov     [r12], r14
0x18009d9e2  mov     r14, rax
0x18009d9e5  mov     rcx, rsi; Block
0x18009d9e8  call    cs:__imp_free
0x18009d9ee  mov     rcx, rdi; Block
0x18009d9f1  call    cs:__imp_free
0x18009d9f7  mov     rcx, r14; Block
0x18009d9fa  call    cs:__imp_free
0x18009da00  mov     rcx, r15; Block
0x18009da03  call    cs:__imp_free
0x18009da09  mov     r8d, ebx
0x18009da0c  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18009da13  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18009da1a  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009da1f  mov     eax, ebx
0x18009da21  add     rsp, 48h
0x18009da25  pop     r15
0x18009da27  pop     r14
0x18009da29  pop     r13
0x18009da2b  pop     r12
0x18009da2d  pop     rdi
0x18009da2e  pop     rsi
0x18009da2f  pop     rbx
0x18009da30  pop     rbp
0x18009da31  retn
```
