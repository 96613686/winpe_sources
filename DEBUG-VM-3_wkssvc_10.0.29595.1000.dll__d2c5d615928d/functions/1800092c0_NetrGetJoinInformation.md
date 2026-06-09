# NetrGetJoinInformation

- ea: `0x1800092c0`
- end: `0x1800099ae`
- name: `NetrGetJoinInformation`
- size: `1774`
- prototype: `__int64 __fastcall(PCWSTR SourceString, LPVOID *Buffer)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800092c0`
- `0x18002ecc0`
- `0x180033159`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009341`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009356`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000936b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009341`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009356`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000936b`
- `ntdll!RtlNtStatusToDosError` at `0x1800097f5`
- `ntdll!RtlNtStatusToDosError` at `0x1800097f5`
- `ntdll!RtlAdjustPrivilege` at `0x180009418`
- `ntdll!RtlAdjustPrivilege` at `0x180009418`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180009475`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180009475`
- `ntdll!RtlInitUnicodeString` at `0x1800093e2`
- `ntdll!RtlInitUnicodeString` at `0x1800093f3`
- `ntdll!RtlInitUnicodeString` at `0x180009404`
- `ntdll!RtlInitUnicodeString` at `0x18000961e`
- `ntdll!RtlInitUnicodeString` at `0x1800093e2`
- `ntdll!RtlInitUnicodeString` at `0x1800093f3`
- `ntdll!RtlInitUnicodeString` at `0x180009404`
- `ntdll!RtlInitUnicodeString` at `0x18000961e`
- `RPCRT4!RpcStringFreeW` at `0x180009380`
- `RPCRT4!RpcStringFreeW` at `0x180009390`
- `RPCRT4!RpcStringFreeW` at `0x180009380`
- `RPCRT4!RpcStringFreeW` at `0x180009390`
- `RPCRT4!RpcStringBindingParseW` at `0x18000932a`
- `RPCRT4!RpcStringBindingParseW` at `0x18000932a`
- `RPCRT4!RpcImpersonateClient` at `0x180009420`
- `RPCRT4!RpcImpersonateClient` at `0x1800094a3`
- `RPCRT4!RpcImpersonateClient` at `0x180009420`
- `RPCRT4!RpcImpersonateClient` at `0x1800094a3`
- `RPCRT4!RpcBindingServerFromClient` at `0x1800092f3`
- `RPCRT4!RpcBindingServerFromClient` at `0x1800092f3`
- `RPCRT4!RpcBindingFree` at `0x1800093a0`
- `RPCRT4!RpcBindingFree` at `0x1800093a0`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180009307`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180009307`
- `RPCRT4!RpcRevertToSelf` at `0x18000947d`
- `RPCRT4!RpcRevertToSelf` at `0x18000959d`
- `RPCRT4!RpcRevertToSelf` at `0x18000947d`
- `RPCRT4!RpcRevertToSelf` at `0x18000959d`
- `netutils!NetApiBufferAllocate` at `0x1800095c9`
- `netutils!NetApiBufferAllocate` at `0x1800095c9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000950c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000950c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180009525`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180009525`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180009531`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180009531`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180009597`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180009597`

## pseudocode

```c
__int64 __fastcall NetrGetJoinInformation(PCWSTR SourceString, LPVOID *Buffer, _DWORD *a3)
{
  DWORD v6; // ebx
  PSECURITY_DESCRIPTOR v7; // rbx
  NTSTATUS v8; // ebx
  RPC_STATUS v9; // eax
  int v10; // r8d
  struct _UNICODE_STRING *p_DestinationString; // rcx
  int InformationPolicy; // esi
  RPC_WSTR v13; // rdx
  unsigned __int16 v14; // cx
  unsigned int v15; // eax
  int v16; // eax
  RPC_STATUS v17; // eax
  int v18; // r8d
  const void *v20; // r14
  unsigned int v21; // esi
  ULONG v22; // eax
  unsigned __int8 GenerateOnClose[8]; // [rsp+60h] [rbp-59h] BYREF
  RPC_WSTR StringBinding; // [rsp+68h] [rbp-51h] BYREF
  RPC_BINDING_HANDLE ServerBinding; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-41h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-31h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+B8h] [rbp-1h] BYREF
  struct _UNICODE_STRING ObjectTypeName; // [rsp+C8h] [rbp+Fh] BYREF
  RPC_WSTR Protseq; // [rsp+138h] [rbp+7Fh] BYREF

  ServerBinding = 0;
  StringBinding = 0;
  Protseq = 0;
  v6 = RpcBindingServerFromClient(0, &ServerBinding);
  if ( !v6 )
  {
    v6 = RpcBindingToStringBindingW(ServerBinding, &StringBinding);
    if ( !v6 )
    {
      v6 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
      if ( !v6 && (unsigned int)_o__wcsicmp(L"ncacn_nb_tcp", Protseq) && (unsigned int)_o__wcsicmp(L"ncacn_np", Protseq) )
      {
        _o__wcsicmp(L"ncalrpc", Protseq);
        v6 = 1703;
      }
    }
  }
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( ServerBinding )
    RpcBindingFree(&ServerBinding);
  if ( v6 )
    return v6;
  v7 = NetApiSd;
  LOBYTE(Protseq) = 0;
  LODWORD(StringBinding) = 0;
  GenerateOnClose[0] = 0;
  DestinationString = 0;
  LODWORD(ServerBinding) = 0;
  ObjectTypeName = 0;
  ObjectName = 0;
  RtlInitUnicodeString(&DestinationString, L"Workstation");
  RtlInitUnicodeString(&ObjectTypeName, L"NetAPI");
  RtlInitUnicodeString(&ObjectName, L"-");
  RtlAdjustPrivilege(0x15u, 1u, 0, (PBOOLEAN)&Protseq);
  if ( RpcImpersonateClient(0) )
    return 5;
  v8 = NtAccessCheckAndAuditAlarm(
         &DestinationString,
         0,
         &ObjectTypeName,
         &ObjectName,
         v7,
         2u,
         &WsNetApiMapping,
         0,
         (PACCESS_MASK)&StringBinding,
         (PNTSTATUS)&ServerBinding,
         GenerateOnClose);
  RpcRevertToSelf();
  if ( v8 < 0 || (_DWORD)ServerBinding )
    return 5;
  if ( Buffer )
  {
    *Buffer = 0;
    v9 = RpcImpersonateClient(0);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v10, (unsigned int)"unknown", 0, v9);
      }
      return 5;
    }
    Protseq = 0;
    StringBinding = 0;
    DestinationString = 0;
    memset(&ObjectAttributes, 0, 44);
    if ( a3 )
    {
      p_DestinationString = 0;
      if ( SourceString )
      {
        RtlInitUnicodeString(&DestinationString, SourceString);
        p_DestinationString = &DestinationString;
      }
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      InformationPolicy = LsaOpenPolicy(
                            (PLSA_UNICODE_STRING)p_DestinationString,
                            &ObjectAttributes,
                            0x2000000u,
                            (PLSA_HANDLE)&Protseq);
      if ( InformationPolicy >= 0 )
      {
        InformationPolicy = LsaQueryInformationPolicy(Protseq, PolicyDnsDomainInformation, (PVOID *)&StringBinding);
        LsaClose(Protseq);
        Protseq = 0;
      }
      if ( !InformationPolicy || InformationPolicy == -2147483611 )
      {
        v6 = 0;
        goto LABEL_27;
      }
      if ( InformationPolicy <= -1073741531 )
      {
        if ( InformationPolicy != -1073741531 )
        {
          switch ( InformationPolicy )
          {
            case -1073741789:
              v6 = 2123;
              break;
            case -1073741727:
              v6 = 5;
              break;
            case -1073741726:
              v6 = 2202;
              break;
            case -1073741725:
              v6 = 2224;
              break;
            case -1073741724:
              v6 = 2221;
              break;
            case -1073741723:
              v6 = 2223;
              break;
            case -1073741722:
            case -1073741709:
              v6 = 2220;
              break;
            case -1073741721:
              v6 = 2236;
              break;
            case -1073741720:
              v6 = 2237;
              break;
            case -1073741716:
              v6 = 2245;
              break;
            case -1073741713:
              v6 = 2241;
              break;
            case -1073741712:
              v6 = 2240;
              break;
            case -1073741711:
              v6 = 2242;
              break;
            case -1073741604:
            case -1073741602:
              goto LABEL_90;
            case -1073741603:
              v6 = 2227;
              break;
            case -1073741596:
              v6 = 2247;
              break;
            case -1073741573:
              v6 = 2102;
              break;
            case -1073741561:
              v6 = 2401;
              break;
            case -1073741560:
              v6 = 2404;
              break;
            default:
              goto LABEL_87;
          }
          goto LABEL_35;
        }
        goto LABEL_81;
      }
      if ( InformationPolicy > -1073741495 )
      {
        switch ( InformationPolicy )
        {
          case -1073741433:
LABEL_90:
            v6 = 2226;
            goto LABEL_35;
          case -1073741421:
            v6 = 2239;
            goto LABEL_35;
          case -1073741261:
            v6 = 2453;
            goto LABEL_35;
        }
      }
      else
      {
        switch ( InformationPolicy )
        {
          case -1073741495:
            v6 = 2403;
            goto LABEL_35;
          case -1073741529:
LABEL_81:
            v6 = 2234;
            goto LABEL_35;
          case -1073741518:
            v6 = 2210;
            goto LABEL_35;
          case -1073741517:
            v6 = 2457;
            goto LABEL_35;
          case -1073741516:
            v6 = 2249;
            goto LABEL_35;
        }
      }
LABEL_87:
      v22 = RtlNtStatusToDosError(InformationPolicy);
      v6 = v22;
      if ( v22 == InformationPolicy )
      {
        v6 = 2140;
      }
      else if ( !v22 )
      {
LABEL_27:
        v13 = StringBinding;
        if ( *((_QWORD *)StringBinding + 8) )
        {
          if ( !*StringBinding )
          {
            *a3 = 1;
            goto LABEL_33;
          }
          *a3 = 3;
        }
        else
        {
          v14 = *StringBinding;
          *a3 = (*StringBinding != 0) + 1;
          if ( !v14 )
            goto LABEL_33;
        }
        v15 = *v13;
        if ( (_WORD)v15 )
        {
          v16 = (v15 >> 1) + 1;
          if ( v16 )
          {
            v20 = (const void *)*((_QWORD *)v13 + 1);
            v21 = 2 * v16;
            v6 = NetApiBufferAllocate(2 * v16, Buffer);
            if ( !v6 )
              memcpy_0(*Buffer, v20, v21);
            v13 = StringBinding;
          }
          else
          {
            v6 = 534;
          }
          goto LABEL_34;
        }
LABEL_33:
        *Buffer = 0;
LABEL_34:
        LsaFreeMemory(v13);
      }
    }
    else
    {
      v6 = 87;
    }
LABEL_35:
    v17 = RpcRevertToSelf();
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
          WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v18, (unsigned int)"unknown", 0, v17);
      }
      __fastfail(7u);
    }
    return v6;
  }
  return 87;
}

```

## disassembly

```asm
0x1800092c0  push    rbp
0x1800092c2  push    rbx
0x1800092c3  push    rsi
0x1800092c4  push    rdi
0x1800092c5  push    r14
0x1800092c7  push    r15
0x1800092c9  lea     rbp, [rsp-2Fh]
0x1800092ce  sub     rsp, 0E8h
0x1800092d5  xor     r15d, r15d
0x1800092d8  mov     rdi, rdx
0x1800092db  mov     rsi, rcx
0x1800092de  mov     [rbp+57h+ServerBinding], r15
0x1800092e2  lea     rdx, [rbp+57h+ServerBinding]; ServerBinding
0x1800092e6  mov     [rbp+57h+StringBinding], r15
0x1800092ea  xor     ecx, ecx; ClientBinding
0x1800092ec  mov     [rbp+57h+Protseq], r15
0x1800092f0  mov     r14, r8
0x1800092f3  call    cs:__imp_RpcBindingServerFromClient
0x1800092f9  mov     ebx, eax
0x1800092fb  test    eax, eax
0x1800092fd  jnz     short loc_180009376
0x1800092ff  mov     rcx, [rbp+57h+ServerBinding]; Binding
0x180009303  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x180009307  call    cs:__imp_RpcBindingToStringBindingW
0x18000930d  mov     ebx, eax
0x18000930f  test    eax, eax
0x180009311  jnz     short loc_180009376
0x180009313  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x180009317  lea     r8, [rbp+57h+Protseq]; Protseq
0x18000931b  mov     [rsp+110h+NetworkOptions], r15; NetworkOptions
0x180009320  xor     r9d, r9d; NetworkAddr
0x180009323  xor     edx, edx; ObjUuid
0x180009325  mov     [rsp+110h+Endpoint], r15; Endpoint
0x18000932a  call    cs:__imp_RpcStringBindingParseW
0x180009330  mov     ebx, eax
0x180009332  test    eax, eax
0x180009334  jnz     short loc_180009376
0x180009336  mov     rdx, [rbp+57h+Protseq]
0x18000933a  lea     rcx, aNcacnNbTcp; "ncacn_nb_tcp"
0x180009341  call    cs:__imp__o__wcsicmp
0x180009347  test    eax, eax
0x180009349  jz      short loc_180009376
0x18000934b  mov     rdx, [rbp+57h+Protseq]
0x18000934f  lea     rcx, Protseq; "ncacn_np"
0x180009356  call    cs:__imp__o__wcsicmp
0x18000935c  test    eax, eax
0x18000935e  jz      short loc_180009376
0x180009360  mov     rdx, [rbp+57h+Protseq]
0x180009364  lea     rcx, String2; "ncalrpc"
0x18000936b  call    cs:__imp__o__wcsicmp
0x180009371  mov     ebx, 6A7h
0x180009376  cmp     [rbp+57h+StringBinding], r15
0x18000937a  jz      short loc_180009386
0x18000937c  lea     rcx, [rbp+57h+StringBinding]; String
0x180009380  call    cs:__imp_RpcStringFreeW
0x180009386  cmp     [rbp+57h+Protseq], r15
0x18000938a  jz      short loc_180009396
0x18000938c  lea     rcx, [rbp+57h+Protseq]; String
0x180009390  call    cs:__imp_RpcStringFreeW
0x180009396  cmp     [rbp+57h+ServerBinding], r15
0x18000939a  jz      short loc_1800093A6
0x18000939c  lea     rcx, [rbp+57h+ServerBinding]; Binding
0x1800093a0  call    cs:__imp_RpcBindingFree
0x1800093a6  test    ebx, ebx
0x1800093a8  jnz     loc_1800095AB
0x1800093ae  mov     rbx, cs:NetApiSd
0x1800093b5  lea     rdx, SourceName; "Workstation"
0x1800093bc  xorps   xmm0, xmm0
0x1800093bf  mov     byte ptr [rbp+57h+Protseq], r15b
0x1800093c3  xorps   xmm1, xmm1
0x1800093c6  mov     dword ptr [rbp+57h+StringBinding], r15d
0x1800093ca  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800093ce  mov     [rbp+57h+var_B0], r15b
0x1800093d2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800093d6  mov     dword ptr [rbp+57h+ServerBinding], r15d
0x1800093da  movups  xmmword ptr [rbp+57h+ObjectTypeName.Length], xmm1
0x1800093de  movups  xmmword ptr [rbp+57h+ObjectName.Length], xmm0
0x1800093e2  call    cs:__imp_RtlInitUnicodeString
0x1800093e8  lea     rdx, aNetapi; "NetAPI"
0x1800093ef  lea     rcx, [rbp+57h+ObjectTypeName]; DestinationString
0x1800093f3  call    cs:__imp_RtlInitUnicodeString
0x1800093f9  lea     rdx, asc_18003AB90; "-"
0x180009400  lea     rcx, [rbp+57h+ObjectName]; DestinationString
0x180009404  call    cs:__imp_RtlInitUnicodeString
0x18000940a  lea     r9, [rbp+57h+Protseq]; OldValue
0x18000940e  xor     r8d, r8d; ForThread
0x180009411  mov     dl, 1; NewValue
0x180009413  mov     ecx, 15h; Privilege
0x180009418  call    cs:__imp_RtlAdjustPrivilege
0x18000941e  xor     ecx, ecx; BindingHandle
0x180009420  call    cs:__imp_RpcImpersonateClient
0x180009426  test    eax, eax
0x180009428  jnz     loc_180009610
0x18000942e  lea     rax, [rbp+57h+var_B0]
0x180009432  xor     edx, edx; HandleId
0x180009434  mov     [rsp+110h+GenerateOnClose], rax; GenerateOnClose
0x180009439  lea     r9, [rbp+57h+ObjectName]; ObjectName
0x18000943d  lea     rax, [rbp+57h+ServerBinding]
0x180009441  mov     [rsp+110h+AccessStatus], rax; AccessStatus
0x180009446  lea     r8, [rbp+57h+ObjectTypeName]; ObjectTypeName
0x18000944a  lea     rax, [rbp+57h+StringBinding]
0x18000944e  mov     [rsp+110h+GrantedAccess], rax; GrantedAccess
0x180009453  lea     rcx, [rbp+57h+DestinationString]; SubsystemName
0x180009457  mov     [rsp+110h+ObjectCreation], r15b; ObjectCreation
0x18000945c  lea     rax, WsNetApiMapping
0x180009463  mov     [rsp+110h+GenericMapping], rax; GenericMapping
0x180009468  mov     dword ptr [rsp+110h+NetworkOptions], 2; DesiredAccess
0x180009470  mov     [rsp+110h+Endpoint], rbx; SecurityDescriptor
0x180009475  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x18000947b  mov     ebx, eax
0x18000947d  call    cs:__imp_RpcRevertToSelf
0x180009483  test    ebx, ebx
0x180009485  js      loc_180009610
0x18000948b  cmp     dword ptr [rbp+57h+ServerBinding], r15d
0x18000948f  jnz     loc_180009610
0x180009495  test    rdi, rdi
0x180009498  jz      loc_1800095FB
0x18000949e  xor     ecx, ecx; BindingHandle
0x1800094a0  mov     [rdi], r15
0x1800094a3  call    cs:__imp_RpcImpersonateClient
0x1800094a9  test    eax, eax
0x1800094ab  jnz     loc_18000963A
0x1800094b1  xorps   xmm0, xmm0
0x1800094b4  mov     [rbp+57h+Protseq], r15
0x1800094b8  xor     eax, eax
0x1800094ba  mov     [rbp+57h+StringBinding], r15
0x1800094be  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800094c2  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800094c6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800094ca  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800094ce  test    r14, r14
0x1800094d1  jz      loc_180009823
0x1800094d7  mov     rcx, r15; SystemName
0x1800094da  test    rsi, rsi
0x1800094dd  jnz     loc_180009617
0x1800094e3  xorps   xmm0, xmm0
0x1800094e6  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800094ed  lea     r9, [rbp+57h+Protseq]; PolicyHandle
0x1800094f1  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1800094f5  mov     r8d, 2000000h; DesiredAccess
0x1800094fb  mov     [rbp+57h+ObjectAttributes.Attributes], r15d
0x1800094ff  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180009503  mov     [rbp+57h+ObjectAttributes.ObjectName], r15
0x180009507  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000950c  call    cs:__imp_LsaOpenPolicy
0x180009512  mov     esi, eax
0x180009514  test    eax, eax
0x180009516  js      short loc_18000953B
0x180009518  mov     rcx, [rbp+57h+Protseq]; PolicyHandle
0x18000951c  lea     r8, [rbp+57h+StringBinding]; Buffer
0x180009520  mov     edx, 0Ch; InformationClass
0x180009525  call    cs:__imp_LsaQueryInformationPolicy
0x18000952b  mov     rcx, [rbp+57h+Protseq]; ObjectHandle
0x18000952f  mov     esi, eax
0x180009531  call    cs:__imp_LsaClose
0x180009537  mov     [rbp+57h+Protseq], r15
0x18000953b  test    esi, esi
0x18000953d  jz      short loc_18000954B
0x18000953f  cmp     esi, 80000025h
0x180009545  jnz     loc_180009681
0x18000954b  mov     ebx, r15d
0x18000954e  mov     rdx, [rbp+57h+StringBinding]
0x180009552  cmp     [rdx+40h], r15
0x180009556  jnz     loc_1800095E9
0x18000955c  movzx   ecx, word ptr [rdx]
0x18000955f  mov     eax, r15d
0x180009562  test    cx, cx
0x180009565  setnz   al
0x180009568  inc     eax
0x18000956a  mov     [r14], eax
0x18000956d  test    cx, cx
0x180009570  jz      short loc_180009591
0x180009572  movzx   eax, word ptr [rdx]
0x180009575  test    ax, ax
0x180009578  jz      short loc_180009591
0x18000957a  shr     eax, 1
0x18000957c  inc     eax
0x18000957e  cmp     eax, 1
0x180009581  jnb     short loc_1800095BD
0x180009583  mov     ebx, 216h
0x180009588  jmp     short loc_180009594
0x18000958a  mov     dword ptr [r14], 1
0x180009591  mov     [rdi], r15
0x180009594  mov     rcx, rdx; Buffer
0x180009597  call    cs:__imp_LsaFreeMemory
0x18000959d  call    cs:__imp_RpcRevertToSelf
0x1800095a3  test    eax, eax
0x1800095a5  jnz     loc_18000982D
0x1800095ab  mov     eax, ebx
0x1800095ad  add     rsp, 0E8h
0x1800095b4  pop     r15
0x1800095b6  pop     r14
0x1800095b8  pop     rdi
0x1800095b9  pop     rsi
0x1800095ba  pop     rbx
0x1800095bb  pop     rbp
0x1800095bc  retn
0x1800095bd  mov     r14, [rdx+8]
0x1800095c1  lea     esi, [rax+rax]
0x1800095c4  mov     ecx, esi; ByteCount
0x1800095c6  mov     rdx, rdi; Buffer
0x1800095c9  call    cs:__imp_NetApiBufferAllocate
0x1800095cf  mov     ebx, eax
0x1800095d1  test    eax, eax
0x1800095d3  jnz     short loc_1800095E3
0x1800095d5  mov     rcx, [rdi]; void *
0x1800095d8  mov     rdx, r14; Src
0x1800095db  mov     r8d, esi; Size
0x1800095de  call    memcpy_0
0x1800095e3  mov     rdx, [rbp+57h+StringBinding]
0x1800095e7  jmp     short loc_180009594
0x1800095e9  cmp     [rdx], r15w
0x1800095ed  jz      short loc_18000958A
0x1800095ef  mov     dword ptr [r14], 3
0x1800095f6  jmp     loc_180009572
0x1800095fb  mov     eax, 57h ; 'W'
0x180009600  add     rsp, 0E8h
0x180009607  pop     r15
0x180009609  pop     r14
0x18000960b  pop     rdi
0x18000960c  pop     rsi
0x18000960d  pop     rbx
0x18000960e  pop     rbp
0x18000960f  retn
0x180009610  mov     eax, 5
0x180009615  jmp     short loc_1800095AD
0x180009617  mov     rdx, rsi; SourceString
0x18000961a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000961e  call    cs:__imp_RtlInitUnicodeString
0x180009624  lea     rcx, [rbp+57h+DestinationString]
0x180009628  jmp     loc_1800094E3
0x18000962d  test    eax, eax
0x18000962f  jz      loc_18000954E
0x180009635  jmp     loc_18000959D
0x18000963a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180009641  lea     rdx, WPP_GLOBAL_Control
0x180009648  cmp     rcx, rdx
0x18000964b  jz      short loc_180009677
0x18000964d  test    byte ptr [rcx+1Ch], 4
0x180009651  jz      short loc_180009677
0x180009653  cmp     byte ptr [rcx+19h], 1
0x180009657  jb      short loc_180009677
0x180009659  mov     rcx, [rcx+10h]
0x18000965d  lea     r9, aUnknown; "unknown"
0x180009664  mov     dword ptr [rsp+110h+NetworkOptions], eax
0x180009668  mov     edx, 0Ah
0x18000966d  mov     dword ptr [rsp+110h+Endpoint], r15d
0x180009672  call    WPP_SF_sdL
0x180009677  mov     ebx, 5
0x18000967c  jmp     loc_1800095AB
0x180009681  cmp     esi, 0C0000125h
0x180009687  jg      loc_180009775
0x18000968d  jz      loc_1800097BD
0x180009693  lea     eax, [rsi+3FFFFFDDh]; switch 230 cases
0x180009699  cmp     eax, 0E5h
0x18000969e  ja      def_1800096BF; jumptable 00000001800096BF default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x1800096a4  lea     rdx, __ImageBase
0x1800096ab  cdqe
0x1800096ad  movzx   eax, ds:(byte_1800098C8 - 180000000h)[rdx+rax]
0x1800096b5  mov     ecx, ds:(jpt_1800096BF - 180000000h)[rdx+rax*4]
0x1800096bc  add     rcx, rdx
0x1800096bf  jmp     rcx; switch jump
0x1800096c1  mov     ebx, 84Bh; jumptable 00000001800096BF case -1073741789
0x1800096c6  jmp     loc_18000959D
0x1800096cb  mov     ebx, 961h; jumptable 00000001800096BF case -1073741561
0x1800096d0  jmp     loc_18000959D
0x1800096d5  mov     ebx, 964h; jumptable 00000001800096BF case -1073741560
0x1800096da  jmp     loc_18000959D
0x1800096df  mov     ebx, 8C1h; jumptable 00000001800096BF case -1073741713
0x1800096e4  jmp     loc_18000959D
0x1800096e9  mov     ebx, 8C0h; jumptable 00000001800096BF case -1073741712
0x1800096ee  jmp     loc_18000959D
0x1800096f3  mov     ebx, 8C2h; jumptable 00000001800096BF case -1073741711
0x1800096f8  jmp     loc_18000959D
0x1800096fd  mov     ebx, 836h; jumptable 00000001800096BF case -1073741573
0x180009702  jmp     loc_18000959D
0x180009707  mov     ebx, 8AFh; jumptable 00000001800096BF case -1073741723
0x18000970c  jmp     loc_18000959D
0x180009711  mov     ebx, 8C7h; jumptable 00000001800096BF case -1073741596
0x180009716  jmp     loc_18000959D
0x18000971b  mov     ebx, 89Ah; jumptable 00000001800096BF case -1073741726
0x180009720  jmp     loc_18000959D
0x180009725  mov     ebx, 8B3h; jumptable 00000001800096BF case -1073741603
0x18000972a  jmp     loc_18000959D
0x18000972f  mov     ebx, 8BCh; jumptable 00000001800096BF case -1073741721
0x180009734  jmp     loc_18000959D
0x180009739  mov     ebx, 8BDh; jumptable 00000001800096BF case -1073741720
0x18000973e  jmp     loc_18000959D
0x180009743  mov     ebx, 8ACh; jumptable 00000001800096BF cases -1073741722,-1073741709
0x180009748  jmp     loc_18000959D
0x18000974d  mov     ebx, 8B0h; jumptable 00000001800096BF case -1073741725
0x180009752  jmp     loc_18000959D
0x180009757  mov     ebx, 8ADh; jumptable 00000001800096BF case -1073741724
0x18000975c  jmp     loc_18000959D
0x180009761  mov     ebx, 5; jumptable 00000001800096BF case -1073741727
0x180009766  jmp     loc_18000959D
0x18000976b  mov     ebx, 8C5h; jumptable 00000001800096BF case -1073741716
0x180009770  jmp     loc_18000959D
0x180009775  cmp     esi, 0C0000149h
0x18000977b  jg      short loc_1800097D1
  ... truncated ...
```
