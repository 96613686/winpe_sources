# WSManHttpListenerRequest::GetClientTokenFromCredSSPCredentials(WSManHttpListenerConnection *,AutoHandle &)

- ea: `0x18005ad14`
- end: `0x18005b247`
- name: `?GetClientTokenFromCredSSPCredentials@WSManHttpListenerRequest@@AEAAKPEAVWSManHttpListenerConnection@@AEAVAutoHandle@@@Z`
- size: `1331`
- prototype: `unsigned int(WSManHttpListenerRequest *__hidden this, struct WSManHttpListenerConnection *, struct AutoHandle *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005936c`

## callees

- `0x180013760`
- `0x18002aee0`
- `0x180033c90`
- `0x18005ad14`
- `0x1800621e0`
- `0x1800973c0`
- `0x1801123a8`
- `0x18011a6d4`
- `0x1801ba1b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b036`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b09a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b1ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b036`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b09a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b1ba`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005b022`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005b022`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18005b02c`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18005b02c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005b18c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005b18c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005b15c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005b168`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005b15c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005b168`
- `ntdll!NtAllocateLocallyUniqueId` at `0x18005af35`
- `ntdll!NtAllocateLocallyUniqueId` at `0x18005af35`
- `ntdll!RtlInitString` at `0x18005af19`
- `ntdll!RtlInitString` at `0x18005af46`
- `ntdll!RtlInitString` at `0x18005af19`
- `ntdll!RtlInitString` at `0x18005af46`
- `ntdll!RtlNtStatusToDosError` at `0x18005af03`
- `ntdll!RtlNtStatusToDosError` at `0x18005af65`
- `ntdll!RtlNtStatusToDosError` at `0x18005af03`
- `ntdll!RtlNtStatusToDosError` at `0x18005af65`
- `SspiCli!LsaLogonUser` at `0x18005afd6`
- `SspiCli!LsaLogonUser` at `0x18005afd6`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18005af59`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18005af59`
- `SspiCli!LsaConnectUntrusted` at `0x18005aef7`
- `SspiCli!LsaConnectUntrusted` at `0x18005aef7`
- `SspiCli!QueryContextAttributesW` at `0x18005add6`
- `SspiCli!QueryContextAttributesW` at `0x18005ae6d`
- `SspiCli!QueryContextAttributesW` at `0x18005add6`
- `SspiCli!QueryContextAttributesW` at `0x18005ae6d`
- `SspiCli!LsaFreeReturnBuffer` at `0x18005b206`
- `SspiCli!LsaFreeReturnBuffer` at `0x18005b206`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18005b210`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18005b210`
- `SspiCli!GetUserNameExW` at `0x18005b08c`
- `SspiCli!GetUserNameExW` at `0x18005b0ef`
- `SspiCli!GetUserNameExW` at `0x18005b08c`
- `SspiCli!GetUserNameExW` at `0x18005b0ef`

## pseudocode

```c
ULONG __fastcall WSManHttpListenerRequest::GetClientTokenFromCredSSPCredentials(
        ULONG *this,
        struct WSManHttpListenerConnection *a2,
        void **a3)
{
  PVOID *v6; // rdi
  __int64 v7; // rax
  ULONG v8; // eax
  unsigned int ContextAttributesW; // eax
  ULONG v10; // esi
  CHeap *v12; // rcx
  SIZE_T v13; // rdx
  CHeap *v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  int v18; // eax
  LPWSTR *v19; // rbx
  __int64 v20; // rax
  BOOL v21; // eax
  DWORD LastError; // eax
  __int64 v23; // rax
  __int64 v24; // rax
  DWORD v25; // eax
  HANDLE CurrentProcess; // rax
  void *v27; // rdi
  void *v28; // rbx
  HANDLE v29; // rax
  DWORD v30; // eax
  __int64 v31; // rax
  _BYTE *v32; // rcx
  ULONG nSize; // [rsp+70h] [rbp-90h] BYREF
  ULONG AuthenticationPackage; // [rsp+74h] [rbp-8Ch] BYREF
  ULONG pBuffer[2]; // [rsp+78h] [rbp-88h] BYREF
  PVOID AuthenticationInformation; // [rsp+80h] [rbp-80h]
  void *LsaHandle; // [rsp+88h] [rbp-78h] BYREF
  int SubStatus; // [rsp+90h] [rbp-70h] BYREF
  ULONG ProfileBufferLength; // [rsp+94h] [rbp-6Ch] BYREF
  PVOID Buffer; // [rsp+98h] [rbp-68h] BYREF
  struct _LUID LogonId; // [rsp+A0h] [rbp-60h] BYREF
  struct _STRING v42; // [rsp+A8h] [rbp-58h] BYREF
  _STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  LUID LocallyUniqueId[2]; // [rsp+C8h] [rbp-38h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+D8h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 419, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
  v6 = (PVOID *)(this + 106);
  if ( !*((_QWORD *)this + 53) )
  {
    this[108] = 1024;
    v7 = WSManMemory::Alloc(1024, 0, 0);
    AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(this + 106, v7);
  }
  if ( !*v6 )
    return 14;
  v8 = this[108];
  AuthenticationInformation = *v6;
  pBuffer[1] = 0;
  pBuffer[0] = v8;
  ContextAttributesW = QueryContextAttributesW((PCtxtHandle)a2 + 5, 0x80000080, pBuffer);
  v10 = ContextAttributesW;
  if ( ContextAttributesW )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        420,
        &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
        ContextAttributesW);
    return v10;
  }
  if ( this[108] >= pBuffer[0] )
  {
LABEL_19:
    SubStatus = 0;
    Buffer = 0;
    ProfileBufferLength = 0;
    DestinationString = 0;
    AuthenticationPackage = 0;
    v42 = 0;
    LogonId = 0;
    *(_OWORD *)&LocallyUniqueId[0].LowPart = 0;
    LsaHandle = 0;
    memset(&Quotas, 0, sizeof(Quotas));
    nSize = 513;
    v17 = LsaConnectUntrusted(&LsaHandle);
    if ( v17 < 0 )
      return RtlNtStatusToDosError(v17);
    RtlInitString(&DestinationString, "WSMAN-CredSSP");
    qmemcpy(LocallyUniqueId, "WSMAN", 5);
    NtAllocateLocallyUniqueId(&LocallyUniqueId[1]);
    RtlInitString(&v42, "Negotiate");
    v18 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&v42, &AuthenticationPackage);
    if ( v18 < 0
      || (v18 = LsaLogonUser(
                  LsaHandle,
                  (PLSA_STRING)&DestinationString,
                  NetworkCleartext,
                  AuthenticationPackage,
                  AuthenticationInformation,
                  pBuffer[0],
                  0,
                  (PTOKEN_SOURCE)LocallyUniqueId,
                  &Buffer,
                  &ProfileBufferLength,
                  &LogonId,
                  a3,
                  &Quotas,
                  &SubStatus),
          v18 < 0) )
    {
      v10 = RtlNtStatusToDosError(v18);
LABEL_50:
      v31 = pBuffer[0];
      v32 = AuthenticationInformation;
      if ( pBuffer[0] )
      {
        do
        {
          *v32++ = 0;
          --v31;
        }
        while ( v31 );
      }
      if ( Buffer )
        LsaFreeReturnBuffer(Buffer);
      LsaDeregisterLogonProcess(LsaHandle);
      return v10;
    }
    v19 = (LPWSTR *)((char *)a2 + 184);
    if ( !*((_QWORD *)a2 + 23) )
    {
      v20 = WSManMemory::Alloc(1026, 0, 0);
      AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=((char *)a2 + 184, v20);
      if ( !*v19 )
      {
        v10 = 14;
        goto LABEL_50;
      }
    }
    if ( *a3 )
      v21 = ImpersonateLoggedOnUser(*a3);
    else
      v21 = ImpersonateSelf(SecurityImpersonation);
    if ( !v21 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 422, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, LastError);
      goto LABEL_50;
    }
    v10 = 0;
    if ( !GetUserNameExW(NameSamCompatible, *v19, &nSize) )
    {
      v10 = GetLastError();
      if ( v10 != 122 )
      {
LABEL_49:
        CSecurity::RevertToSelf();
        goto LABEL_50;
      }
      v23 = 2LL * nSize;
      if ( !is_mul_ok(nSize, 2u) )
        v23 = -1;
      v24 = WSManMemory::Alloc(v23, 0, 0);
      AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=((char *)a2 + 184, v24);
      if ( !*v19 )
      {
        v10 = 14;
        goto LABEL_49;
      }
      if ( !GetUserNameExW(NameSamCompatible, *v19, &nSize) )
      {
        v25 = GetLastError();
        v10 = v25;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 423, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v25);
        goto LABEL_49;
      }
    }
    AutoHandle::operator=((char *)a2 + 280, 0);
    if ( *a3 )
    {
      CurrentProcess = GetCurrentProcess();
      v27 = *a3;
      v28 = CurrentProcess;
      v29 = GetCurrentProcess();
      if ( !DuplicateHandle(v29, v27, v28, (LPHANDLE)a2 + 35, 0, 0, 2u) )
      {
        v10 = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          v30 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 424, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v30);
        }
      }
    }
    goto LABEL_49;
  }
  v12 = (CHeap *)*v6;
  v13 = pBuffer[0];
  this[108] = pBuffer[0];
  v14 = WSManMemory::ReAlloc(v12, v13);
  if ( !v14 )
    return 14;
  pBuffer[0] = this[108];
  *v6 = v14;
  AuthenticationInformation = v14;
  v15 = QueryContextAttributesW((PCtxtHandle)a2 + 5, 0x80000080, pBuffer);
  v16 = v15;
  if ( !v15 )
    goto LABEL_19;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 421, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v15);
  return v16;
}

```

## disassembly

```asm
0x18005ad14  mov     [rsp-8+arg_18], rbx
0x18005ad19  push    rbp
0x18005ad1a  push    rsi
0x18005ad1b  push    rdi
0x18005ad1c  push    r12
0x18005ad1e  push    r13
0x18005ad20  push    r14
0x18005ad22  push    r15
0x18005ad24  lea     rbp, [rsp-10h]
0x18005ad29  sub     rsp, 110h
0x18005ad30  mov     rax, cs:__security_cookie
0x18005ad37  xor     rax, rsp
0x18005ad3a  mov     [rbp+40h+var_38], rax
0x18005ad3e  mov     r15, r8
0x18005ad41  mov     r13, rdx
0x18005ad44  mov     rbx, rcx
0x18005ad47  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ad4e  lea     rax, WPP_GLOBAL_Control
0x18005ad55  mov     esi, 400h
0x18005ad5a  cmp     rcx, rax
0x18005ad5d  jz      short loc_18005AD7C
0x18005ad5f  test    [rcx+1Ch], esi
0x18005ad62  jz      short loc_18005AD7C
0x18005ad64  mov     rcx, [rcx+10h]
0x18005ad68  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005ad6f  mov     edx, 1A3h
0x18005ad74  mov     r9, rbx
0x18005ad77  call    WPP_SF_q
0x18005ad7c  lea     rdi, [rbx+1A8h]
0x18005ad83  xor     r12d, r12d
0x18005ad86  cmp     [rdi], r12
0x18005ad89  jnz     short loc_18005ADA9
0x18005ad8b  xor     r8d, r8d
0x18005ad8e  mov     [rbx+1B0h], esi
0x18005ad94  xor     edx, edx
0x18005ad96  mov     rcx, rsi
0x18005ad99  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18005ad9e  mov     rdx, rax
0x18005ada1  mov     rcx, rdi
0x18005ada4  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x18005ada9  mov     rcx, [rdi]
0x18005adac  test    rcx, rcx
0x18005adaf  jz      loc_18005B21B
0x18005adb5  mov     eax, [rbx+1B0h]
0x18005adbb  lea     r8, [rsp+140h+pBuffer]; pBuffer
0x18005adc0  mov     [rbp+40h+var_C0], rcx
0x18005adc4  mov     edx, 80000080h; ulAttribute
0x18005adc9  lea     rcx, [r13+50h]; phContext
0x18005adcd  mov     [rsp+140h+var_C4], r12d
0x18005add2  mov     [rsp+140h+pBuffer], eax
0x18005add6  call    cs:__imp_QueryContextAttributesW
0x18005addc  mov     esi, eax
0x18005adde  test    eax, eax
0x18005ade0  jz      short loc_18005AE1D
0x18005ade2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ade9  lea     rdx, WPP_GLOBAL_Control
0x18005adf0  cmp     rcx, rdx
0x18005adf3  jz      short loc_18005AE16
0x18005adf5  test    dword ptr [rcx+1Ch], 200h
0x18005adfc  jz      short loc_18005AE16
0x18005adfe  mov     rcx, [rcx+10h]
0x18005ae02  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005ae09  mov     edx, 1A4h
0x18005ae0e  mov     r9d, eax
0x18005ae11  call    WPP_SF_d
0x18005ae16  mov     eax, esi
0x18005ae18  jmp     loc_18005B220
0x18005ae1d  mov     eax, [rsp+140h+pBuffer]
0x18005ae21  cmp     [rbx+1B0h], eax
0x18005ae27  jnb     loc_18005AEB4
0x18005ae2d  mov     rcx, [rdi]
0x18005ae30  mov     edx, eax
0x18005ae32  xor     r9d, r9d
0x18005ae35  mov     [rbx+1B0h], edx
0x18005ae3b  xor     r8d, r8d
0x18005ae3e  call    ?ReAlloc@WSManMemory@@SAPEAXPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::ReAlloc(void *,unsigned __int64,int,_NitsFaultMode)
0x18005ae43  test    rax, rax
0x18005ae46  jz      loc_18005B21B
0x18005ae4c  mov     r8d, [rbx+1B0h]
0x18005ae53  lea     rcx, [r13+50h]; phContext
0x18005ae57  mov     [rsp+140h+pBuffer], r8d
0x18005ae5c  mov     edx, 80000080h; ulAttribute
0x18005ae61  lea     r8, [rsp+140h+pBuffer]; pBuffer
0x18005ae66  mov     [rdi], rax
0x18005ae69  mov     [rbp+40h+var_C0], rax
0x18005ae6d  call    cs:__imp_QueryContextAttributesW
0x18005ae73  mov     ebx, eax
0x18005ae75  test    eax, eax
0x18005ae77  jz      short loc_18005AEB4
0x18005ae79  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ae80  lea     rdx, WPP_GLOBAL_Control
0x18005ae87  cmp     rcx, rdx
0x18005ae8a  jz      short loc_18005AEAD
0x18005ae8c  test    dword ptr [rcx+1Ch], 200h
0x18005ae93  jz      short loc_18005AEAD
0x18005ae95  mov     rcx, [rcx+10h]
0x18005ae99  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005aea0  mov     edx, 1A5h
0x18005aea5  mov     r9d, eax
0x18005aea8  call    WPP_SF_d
0x18005aead  mov     eax, ebx
0x18005aeaf  jmp     loc_18005B220
0x18005aeb4  xorps   xmm1, xmm1
0x18005aeb7  mov     [rbp+40h+var_B0], r12d
0x18005aebb  xorps   xmm0, xmm0
0x18005aebe  mov     [rbp+40h+Buffer], r12
0x18005aec2  lea     rcx, [rbp+40h+LsaHandle]; LsaHandle
0x18005aec6  mov     [rbp+40h+var_AC], r12d
0x18005aeca  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x18005aece  mov     [rsp+140h+AuthenticationPackage], r12d
0x18005aed3  movups  xmmword ptr [rbp+40h+var_98.Length], xmm1
0x18005aed7  mov     qword ptr [rbp+40h+var_A0.LowPart], r12
0x18005aedb  movups  xmmword ptr [rbp+40h+LocallyUniqueId.LowPart], xmm0
0x18005aedf  mov     [rbp+40h+LsaHandle], r12
0x18005aee3  movups  xmmword ptr [rbp+40h+var_68.PagedPoolLimit], xmm1
0x18005aee7  mov     [rsp+140h+nSize], 201h
0x18005aeef  movups  xmmword ptr [rbp+40h+var_68.MinimumWorkingSetSize], xmm1
0x18005aef3  movups  xmmword ptr [rbp+40h+var_68.PagefileLimit], xmm1
0x18005aef7  call    cs:__imp_LsaConnectUntrusted
0x18005aefd  test    eax, eax
0x18005aeff  jns     short loc_18005AF0E
0x18005af01  mov     ecx, eax; Status
0x18005af03  call    cs:__imp_RtlNtStatusToDosError
0x18005af09  jmp     loc_18005B220
0x18005af0e  lea     rdx, SourceString; "WSMAN-CredSSP"
0x18005af15  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x18005af19  call    cs:__imp_RtlInitString
0x18005af1f  mov     eax, dword ptr cs:aWsman_1; "WSMAN"
0x18005af25  lea     rcx, [rbp+40h+LocallyUniqueId.LowPart+8]; LocallyUniqueId
0x18005af29  mov     [rbp+40h+LocallyUniqueId.LowPart], eax
0x18005af2c  mov     al, byte ptr cs:aWsman_1+4; "N"
0x18005af32  mov     byte ptr [rbp+40h+LocallyUniqueId.HighPart], al
0x18005af35  call    cs:__imp_NtAllocateLocallyUniqueId
0x18005af3b  lea     rdx, aNegotiate_1; "Negotiate"
0x18005af42  lea     rcx, [rbp+40h+var_98]; DestinationString
0x18005af46  call    cs:__imp_RtlInitString
0x18005af4c  mov     rcx, [rbp+40h+LsaHandle]; LsaHandle
0x18005af50  lea     r8, [rsp+140h+AuthenticationPackage]; AuthenticationPackage
0x18005af55  lea     rdx, [rbp+40h+var_98]; PackageName
0x18005af59  call    cs:__imp_LsaLookupAuthenticationPackage
0x18005af5f  test    eax, eax
0x18005af61  jns     short loc_18005AF72
0x18005af63  mov     ecx, eax; Status
0x18005af65  call    cs:__imp_RtlNtStatusToDosError
0x18005af6b  mov     esi, eax
0x18005af6d  jmp     loc_18005B1E4
0x18005af72  mov     r9d, [rsp+140h+AuthenticationPackage]; AuthenticationPackage
0x18005af77  lea     rax, [rbp+40h+var_B0]
0x18005af7b  mov     rcx, [rbp+40h+LsaHandle]; LsaHandle
0x18005af7f  lea     rdx, [rbp+40h+DestinationString]; OriginName
0x18005af83  mov     [rsp+140h+SubStatus], rax; SubStatus
0x18005af88  mov     r8d, 8; LogonType
0x18005af8e  lea     rax, [rbp+40h+var_68]
0x18005af92  mov     [rsp+140h+Quotas], rax; Quotas
0x18005af97  lea     rax, [rbp+40h+var_A0]
0x18005af9b  mov     [rsp+140h+Token], r15; Token
0x18005afa0  mov     [rsp+140h+LogonId], rax; LogonId
0x18005afa5  lea     rax, [rbp+40h+var_AC]
0x18005afa9  mov     [rsp+140h+ProfileBufferLength], rax; ProfileBufferLength
0x18005afae  lea     rax, [rbp+40h+Buffer]
0x18005afb2  mov     [rsp+140h+ProfileBuffer], rax; ProfileBuffer
0x18005afb7  lea     rax, [rbp+40h+LocallyUniqueId]
0x18005afbb  mov     [rsp+140h+SourceContext], rax; SourceContext
0x18005afc0  mov     eax, [rsp+140h+pBuffer]
0x18005afc4  mov     [rsp+140h+LocalGroups], r12; LocalGroups
0x18005afc9  mov     [rsp+140h+AuthenticationInformationLength], eax; AuthenticationInformationLength
0x18005afcd  mov     rax, [rbp+40h+var_C0]
0x18005afd1  mov     [rsp+140h+AuthenticationInformation], rax; AuthenticationInformation
0x18005afd6  call    cs:__imp_LsaLogonUser
0x18005afdc  test    eax, eax
0x18005afde  js      short loc_18005AF63
0x18005afe0  lea     rbx, [r13+0B8h]
0x18005afe7  cmp     [rbx], r12
0x18005afea  jnz     short loc_18005B015
0x18005afec  xor     r8d, r8d
0x18005afef  xor     edx, edx
0x18005aff1  mov     ecx, 402h
0x18005aff6  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18005affb  mov     rdx, rax
0x18005affe  mov     rcx, rbx
0x18005b001  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x18005b006  cmp     [rbx], r12
0x18005b009  jnz     short loc_18005B015
0x18005b00b  mov     esi, 0Eh
0x18005b010  jmp     loc_18005B1E4
0x18005b015  mov     rcx, [r15]; hToken
0x18005b018  mov     edi, 2
0x18005b01d  test    rcx, rcx
0x18005b020  jz      short loc_18005B02A
0x18005b022  call    cs:__imp_ImpersonateLoggedOnUser
0x18005b028  jmp     short loc_18005B032
0x18005b02a  mov     ecx, edi; ImpersonationLevel
0x18005b02c  call    cs:__imp_ImpersonateSelf
0x18005b032  test    eax, eax
0x18005b034  jnz     short loc_18005B07F
0x18005b036  call    cs:__imp_GetLastError
0x18005b03c  mov     esi, eax
0x18005b03e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b045  lea     rdx, WPP_GLOBAL_Control
0x18005b04c  cmp     rcx, rdx
0x18005b04f  jz      loc_18005B1E4
0x18005b055  test    dword ptr [rcx+1Ch], 200h
0x18005b05c  jz      loc_18005B1E4
0x18005b062  mov     rcx, [rcx+10h]
0x18005b066  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005b06d  mov     edx, 1A6h
0x18005b072  mov     r9d, eax
0x18005b075  call    WPP_SF_d
0x18005b07a  jmp     loc_18005B1E4
0x18005b07f  mov     rdx, [rbx]; lpNameBuffer
0x18005b082  lea     r8, [rsp+140h+nSize]; nSize
0x18005b087  mov     ecx, edi; NameFormat
0x18005b089  mov     esi, r12d
0x18005b08c  call    cs:__imp_GetUserNameExW
0x18005b092  test    al, al
0x18005b094  jnz     loc_18005B142
0x18005b09a  call    cs:__imp_GetLastError
0x18005b0a0  mov     esi, eax
0x18005b0a2  cmp     eax, 7Ah ; 'z'
0x18005b0a5  jnz     loc_18005B1DF
0x18005b0ab  mov     ecx, [rsp+140h+nSize]
0x18005b0af  mov     rax, rdi
0x18005b0b2  mul     rcx
0x18005b0b5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005b0bc  cmovb   rax, rcx
0x18005b0c0  xor     r8d, r8d
0x18005b0c3  mov     rcx, rax
0x18005b0c6  xor     edx, edx
0x18005b0c8  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18005b0cd  mov     rdx, rax
0x18005b0d0  mov     rcx, rbx
0x18005b0d3  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x18005b0d8  mov     rdx, [rbx]; lpNameBuffer
0x18005b0db  test    rdx, rdx
0x18005b0de  jnz     short loc_18005B0E8
0x18005b0e0  lea     esi, [rdx+0Eh]
0x18005b0e3  jmp     loc_18005B1DF
0x18005b0e8  lea     r8, [rsp+140h+nSize]; nSize
0x18005b0ed  mov     ecx, edi; NameFormat
0x18005b0ef  call    cs:__imp_GetUserNameExW
0x18005b0f5  test    al, al
0x18005b0f7  jnz     short loc_18005B142
0x18005b0f9  call    cs:__imp_GetLastError
0x18005b0ff  mov     esi, eax
0x18005b101  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b108  lea     rdx, WPP_GLOBAL_Control
0x18005b10f  cmp     rcx, rdx
0x18005b112  jz      loc_18005B1DF
0x18005b118  test    dword ptr [rcx+1Ch], 200h
0x18005b11f  jz      loc_18005B1DF
0x18005b125  mov     rcx, [rcx+10h]
0x18005b129  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005b130  mov     edx, 1A7h
0x18005b135  mov     r9d, eax
0x18005b138  call    WPP_SF_d
0x18005b13d  jmp     loc_18005B1DF
0x18005b142  lea     r14, [r13+118h]
0x18005b149  xor     edx, edx
0x18005b14b  mov     rcx, r14
0x18005b14e  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x18005b153  cmp     [r15], r12
0x18005b156  jz      loc_18005B1DF
0x18005b15c  call    cs:__imp_GetCurrentProcess
0x18005b162  mov     rdi, [r15]
0x18005b165  mov     rbx, rax
0x18005b168  call    cs:__imp_GetCurrentProcess
0x18005b16e  mov     dword ptr [rsp+140h+LocalGroups], 2; dwOptions
0x18005b176  mov     r9, r14; lpTargetHandle
0x18005b179  mov     rcx, rax; hSourceProcessHandle
0x18005b17c  mov     [rsp+140h+AuthenticationInformationLength], r12d; bInheritHandle
0x18005b181  mov     r8, rbx; hTargetProcessHandle
0x18005b184  mov     dword ptr [rsp+140h+AuthenticationInformation], r12d; dwDesiredAccess
0x18005b189  mov     rdx, rdi; hSourceHandle
0x18005b18c  call    cs:__imp_DuplicateHandle
0x18005b192  test    eax, eax
0x18005b194  jnz     short loc_18005B1DF
0x18005b196  call    cs:__imp_GetLastError
0x18005b19c  mov     esi, eax
0x18005b19e  mov     rax, cs:WPP_GLOBAL_Control
0x18005b1a5  lea     rdx, WPP_GLOBAL_Control
0x18005b1ac  cmp     rax, rdx
0x18005b1af  jz      short loc_18005B1DF
0x18005b1b1  test    dword ptr [rax+1Ch], 200h
0x18005b1b8  jz      short loc_18005B1DF
0x18005b1ba  call    cs:__imp_GetLastError
0x18005b1c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b1c7  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005b1ce  mov     edx, 1A8h
0x18005b1d3  mov     r9d, eax
0x18005b1d6  mov     rcx, [rcx+10h]
0x18005b1da  call    WPP_SF_d
0x18005b1df  call    ?RevertToSelf@CSecurity@@SAHXZ; CSecurity::RevertToSelf(void)
0x18005b1e4  mov     eax, [rsp+140h+pBuffer]
0x18005b1e8  mov     rcx, [rbp+40h+var_C0]
0x18005b1ec  test    rax, rax
0x18005b1ef  jz      short loc_18005B1FD
0x18005b1f1  mov     [rcx], r12b
0x18005b1f4  inc     rcx
0x18005b1f7  sub     rax, 1
0x18005b1fb  jnz     short loc_18005B1F1
  ... truncated ...
```
