# ConfigUpdate::DeleteSSLConfiguration(void)

- ea: `0x1801979ec`
- end: `0x180197ca7`
- name: `?DeleteSSLConfiguration@ConfigUpdate@@AEAAXXZ`
- size: `699`
- prototype: `void __fastcall(ConfigUpdate *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18019a8ac`

## callees

- `0x180008920`
- `0x180013760`
- `0x1800621e0`
- `0x1801123a8`
- `0x18011a6d4`
- `0x1801979ec`
- `0x1801ba152`
- `0x1801ba1b0`

## import_xrefs

- `HTTPAPI!HttpTerminate` at `0x180197c57`
- `HTTPAPI!HttpTerminate` at `0x180197c57`
- `HTTPAPI!HttpInitialize` at `0x180197a5c`
- `HTTPAPI!HttpInitialize` at `0x180197a5c`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180197ae8`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180197b52`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180197ae8`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180197b52`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x180197bad`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x180197bad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ConfigUpdate::DeleteSSLConfiguration(ConfigUpdate *this)
{
  ULONG v1; // eax
  ULONG v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  ULONG v5; // eax
  __int64 v6; // rax
  __int64 *v7; // rsi
  ULONG v8; // eax
  __int64 v9; // rax
  ULONG v10; // eax
  ULONG pReturnLength; // [rsp+40h] [rbp-79h] BYREF
  PVOID pOutput; // [rsp+48h] [rbp-71h] BYREF
  __int128 pInput; // [rsp+50h] [rbp-69h] BYREF
  __int64 v14; // [rsp+60h] [rbp-59h]
  __int64 pConfigInformation; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v16[88]; // [rsp+78h] [rbp-41h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, &WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids, this);
  LODWORD(pOutput) = 1;
  v1 = HttpInitialize((HTTPAPI_VERSION)1, 2u, 0);
  v2 = v1;
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v4 = 187;
      goto LABEL_33;
    }
    return;
  }
  pReturnLength = 0;
  pInput = 0;
  LODWORD(pInput) = 1;
  v14 = 0;
  while ( v2 != 259 )
  {
    v5 = HttpQueryServiceConfiguration(0, HttpServiceConfigSSLCertInfo, &pInput, 0x18u, 0, 0, &pReturnLength, 0);
    if ( v5 != 122 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 188, &WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids, v5);
      break;
    }
    pOutput = 0;
    v6 = WSManMemory::Alloc(pReturnLength, 0, 0);
    AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(&pOutput, v6);
    v7 = (__int64 *)pOutput;
    if ( !pOutput )
      goto LABEL_25;
    v8 = HttpQueryServiceConfiguration(
           0,
           HttpServiceConfigSSLCertInfo,
           &pInput,
           0x18u,
           pOutput,
           pReturnLength,
           &pReturnLength,
           0);
    v2 = v8;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, &WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids, v8);
LABEL_25:
      AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&pOutput);
      break;
    }
    v9 = v7[3] - WSMAN_SSLCONFIG_GUID;
    if ( !v9 )
      v9 = v7[4] - *((_QWORD *)&WSMAN_SSLCONFIG_GUID + 1);
    if ( !v9 )
    {
      memset_0(v16, 0, 0x50u);
      pConfigInformation = *v7;
      v10 = HttpDeleteServiceConfiguration(0, HttpServiceConfigSSLCertInfo, &pConfigInformation, 0x58u, 0);
      v2 = v10;
      if ( !v10 )
        goto LABEL_21;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, &WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids, v10);
    }
    LODWORD(v14) = v14 + 1;
LABEL_21:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&pOutput);
  }
  v1 = HttpTerminate(2u, 0);
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      v4 = 191;
LABEL_33:
      WPP_SF_d(v3[2], v4, &WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids, v1);
    }
  }
}

```

## disassembly

```asm
0x1801979ec  push    rbp
0x1801979ee  push    rbx
0x1801979ef  push    rsi
0x1801979f0  push    r12
0x1801979f2  push    r13
0x1801979f4  push    r15
0x1801979f6  lea     rbp, [rsp-2Fh]
0x1801979fb  sub     rsp, 0E8h
0x180197a02  mov     rax, cs:__security_cookie
0x180197a09  xor     rax, rsp
0x180197a0c  mov     [rbp+57h+var_40], rax
0x180197a10  mov     r9, rcx
0x180197a13  lea     r15, WPP_GLOBAL_Control
0x180197a1a  lea     r13, WPP_61dbeec22f33346d309c612f1570c2b1_Traceguids
0x180197a21  mov     rcx, cs:WPP_GLOBAL_Control
0x180197a28  cmp     rcx, r15
0x180197a2b  jz      short loc_180197A47
0x180197a2d  test    dword ptr [rcx+1Ch], 200000h
0x180197a34  jz      short loc_180197A47
0x180197a36  mov     edx, 0BAh
0x180197a3b  mov     r8, r13
0x180197a3e  mov     rcx, [rcx+10h]
0x180197a42  call    WPP_SF_q
0x180197a47  mov     r12d, 1
0x180197a4d  mov     dword ptr [rbp+57h+var_C8], r12d
0x180197a51  xor     r8d, r8d; pReserved
0x180197a54  lea     edx, [r12+1]; Flags
0x180197a59  mov     ecx, r12d; Version
0x180197a5c  call    cs:__imp_HttpInitialize
0x180197a62  mov     ebx, eax
0x180197a64  test    eax, eax
0x180197a66  jz      short loc_180197A8F
0x180197a68  mov     rcx, cs:WPP_GLOBAL_Control
0x180197a6f  cmp     rcx, r15
0x180197a72  jz      loc_180197C8A
0x180197a78  test    dword ptr [rcx+1Ch], 200h
0x180197a7f  jz      loc_180197C8A
0x180197a85  mov     edx, 0BBh
0x180197a8a  jmp     loc_180197C7B
0x180197a8f  mov     [rbp+57h+var_D0], 0
0x180197a96  xorps   xmm0, xmm0
0x180197a99  xor     eax, eax
0x180197a9b  movups  [rbp+57h+pInput], xmm0
0x180197a9f  mov     [rbp+57h+var_B0], rax
0x180197aa3  mov     dword ptr [rbp+57h+pInput], r12d
0x180197aa7  mov     dword ptr [rbp+57h+var_B0], eax
0x180197aaa  cmp     ebx, 103h
0x180197ab0  jz      loc_180197C52
0x180197ab6  mov     [rsp+110h+pOverlapped], 0; pOverlapped
0x180197abf  lea     rax, [rbp+57h+var_D0]
0x180197ac3  mov     [rsp+110h+pReturnLength], rax; pReturnLength
0x180197ac8  mov     [rsp+110h+OutputLength], 0; OutputLength
0x180197ad0  mov     [rsp+110h+pOutput], 0; pOutput
0x180197ad9  mov     r9d, 18h; InputLength
0x180197adf  lea     r8, [rbp+57h+pInput]; pInput
0x180197ae3  mov     edx, r12d; ConfigId
0x180197ae6  xor     ecx, ecx; ServiceHandle
0x180197ae8  call    cs:__imp_HttpQueryServiceConfiguration
0x180197aee  cmp     eax, 7Ah ; 'z'
0x180197af1  jnz     loc_180197C29
0x180197af7  mov     [rbp+57h+var_C8], 0
0x180197aff  mov     ecx, [rbp+57h+var_D0]
0x180197b02  xor     r8d, r8d
0x180197b05  xor     edx, edx
0x180197b07  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180197b0c  mov     rdx, rax
0x180197b0f  lea     rcx, [rbp+57h+var_C8]
0x180197b13  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x180197b18  mov     rsi, [rbp+57h+var_C8]
0x180197b1c  test    rsi, rsi
0x180197b1f  jz      loc_180197C1E
0x180197b25  mov     eax, [rbp+57h+var_D0]
0x180197b28  mov     [rsp+110h+pOverlapped], 0; pOverlapped
0x180197b31  lea     rcx, [rbp+57h+var_D0]
0x180197b35  mov     [rsp+110h+pReturnLength], rcx; pReturnLength
0x180197b3a  mov     [rsp+110h+OutputLength], eax; OutputLength
0x180197b3e  mov     [rsp+110h+pOutput], rsi; pOutput
0x180197b43  mov     r9d, 18h; InputLength
0x180197b49  lea     r8, [rbp+57h+pInput]; pInput
0x180197b4d  mov     edx, r12d; ConfigId
0x180197b50  xor     ecx, ecx; ServiceHandle
0x180197b52  call    cs:__imp_HttpQueryServiceConfiguration
0x180197b58  mov     ebx, eax
0x180197b5a  test    eax, eax
0x180197b5c  jnz     loc_180197BF4
0x180197b62  mov     rax, [rsi+18h]
0x180197b66  sub     rax, qword ptr cs:WSMAN_SSLCONFIG_GUID
0x180197b6d  jnz     short loc_180197B7A
0x180197b6f  mov     rax, [rsi+20h]
0x180197b73  sub     rax, qword ptr cs:WSMAN_SSLCONFIG_GUID+8
0x180197b7a  test    rax, rax
0x180197b7d  jnz     short loc_180197BE2
0x180197b7f  xor     edx, edx; Val
0x180197b81  lea     r8d, [rax+50h]; Size
0x180197b85  lea     rcx, [rbp+57h+var_98]; void *
0x180197b89  call    memset_0
0x180197b8e  mov     rax, [rsi]
0x180197b91  mov     [rbp+57h+pConfigInformation], rax
0x180197b95  mov     [rsp+110h+pOutput], 0; pOverlapped
0x180197b9e  mov     r9d, 58h ; 'X'; ConfigInformationLength
0x180197ba4  lea     r8, [rbp+57h+pConfigInformation]; pConfigInformation
0x180197ba8  mov     edx, r12d; ConfigId
0x180197bab  xor     ecx, ecx; ServiceHandle
0x180197bad  call    cs:__imp_HttpDeleteServiceConfiguration
0x180197bb3  mov     ebx, eax
0x180197bb5  test    eax, eax
0x180197bb7  jz      short loc_180197BE6
0x180197bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180197bc0  cmp     rcx, r15
0x180197bc3  jz      short loc_180197BE2
0x180197bc5  test    dword ptr [rcx+1Ch], 200h
0x180197bcc  jz      short loc_180197BE2
0x180197bce  mov     edx, 0BEh
0x180197bd3  mov     r9d, eax
0x180197bd6  mov     r8, r13
0x180197bd9  mov     rcx, [rcx+10h]
0x180197bdd  call    WPP_SF_d
0x180197be2  add     dword ptr [rbp+57h+var_B0], r12d
0x180197be6  lea     rcx, [rbp+57h+var_C8]
0x180197bea  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180197bef  jmp     loc_180197AAA
0x180197bf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180197bfb  cmp     rcx, r15
0x180197bfe  jz      short loc_180197C1E
0x180197c00  test    dword ptr [rcx+1Ch], 200h
0x180197c07  jz      short loc_180197C1E
0x180197c09  mov     edx, 0BDh
0x180197c0e  mov     r9d, eax
0x180197c11  mov     r8, r13
0x180197c14  mov     rcx, [rcx+10h]
0x180197c18  call    WPP_SF_d
0x180197c1d  nop
0x180197c1e  lea     rcx, [rbp+57h+var_C8]
0x180197c22  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180197c27  jmp     short loc_180197C52
0x180197c29  mov     rcx, cs:WPP_GLOBAL_Control
0x180197c30  cmp     rcx, r15
0x180197c33  jz      short loc_180197C52
0x180197c35  test    dword ptr [rcx+1Ch], 200h
0x180197c3c  jz      short loc_180197C52
0x180197c3e  mov     edx, 0BCh
0x180197c43  mov     r9d, eax
0x180197c46  mov     r8, r13
0x180197c49  mov     rcx, [rcx+10h]
0x180197c4d  call    WPP_SF_d
0x180197c52  xor     edx, edx; pReserved
0x180197c54  lea     ecx, [rdx+2]; Flags
0x180197c57  call    cs:__imp_HttpTerminate
0x180197c5d  test    eax, eax
0x180197c5f  jz      short loc_180197C8A
0x180197c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180197c68  cmp     rcx, r15
0x180197c6b  jz      short loc_180197C8A
0x180197c6d  test    dword ptr [rcx+1Ch], 400000h
0x180197c74  jz      short loc_180197C8A
0x180197c76  mov     edx, 0BFh
0x180197c7b  mov     r9d, eax
0x180197c7e  mov     r8, r13
0x180197c81  mov     rcx, [rcx+10h]
0x180197c85  call    WPP_SF_d
0x180197c8a  mov     rcx, [rbp+57h+var_40]
0x180197c8e  xor     rcx, rsp; StackCookie
0x180197c91  call    __security_check_cookie
0x180197c96  add     rsp, 0E8h
0x180197c9d  pop     r15
0x180197c9f  pop     r13
0x180197ca1  pop     r12
0x180197ca3  pop     rsi
0x180197ca4  pop     rbx
0x180197ca5  pop     rbp
0x180197ca6  retn
```
