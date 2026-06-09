# WsImpersonateAndGetLogonId

- ea: `0x180002a60`
- end: `0x1800031be`
- name: `WsImpersonateAndGetLogonId`
- size: `1886`
- prototype: `__int64 __fastcall(PLUID DestinationLuid)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800012a0`
- `0x180001710`
- `0x1800024f0`
- `0x180002700`
- `0x1800038d0`
- `0x18002a06c`

## callees

- `0x180002a60`
- `0x18001e420`
- `0x18002ecc0`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180002b75`
- `ntdll!RtlCopyLuid` at `0x180002b75`
- `ntdll!NtOpenThreadToken` at `0x180002ad5`
- `ntdll!NtOpenThreadToken` at `0x180002ad5`
- `ntdll!RtlNtStatusToDosError` at `0x180002d45`
- `ntdll!RtlNtStatusToDosError` at `0x180002edc`
- `ntdll!RtlNtStatusToDosError` at `0x180002d45`
- `ntdll!RtlNtStatusToDosError` at `0x180002edc`
- `ntdll!NtClose` at `0x180002b80`
- `ntdll!NtClose` at `0x180002b80`
- `ntdll!NtQueryInformationToken` at `0x180002b50`
- `ntdll!NtQueryInformationToken` at `0x180002b50`
- `RPCRT4!RpcImpersonateClient` at `0x180002aa3`
- `RPCRT4!RpcImpersonateClient` at `0x180002aa3`
- `RPCRT4!RpcRevertToSelf` at `0x180002af5`
- `RPCRT4!RpcRevertToSelf` at `0x180002af5`

## pseudocode

```c
__int64 __fastcall WsImpersonateAndGetLogonId(PLUID DestinationLuid)
{
  RPC_STATUS v2; // eax
  int v3; // r8d
  int v4; // eax
  int v5; // edi
  unsigned int v6; // ebx
  RPC_STATUS v7; // eax
  int v8; // r8d
  int v10; // eax
  int v11; // edi
  ULONG v12; // eax
  ULONG v13; // eax
  void *TokenHandle; // [rsp+30h] [rbp-68h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-60h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v17; // [rsp+70h] [rbp-28h]

  TokenHandle = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v17 = 0;
  ReturnLength = 0;
  v2 = RpcImpersonateClient(0);
  if ( !v2 )
  {
    v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
    v5 = v4;
    if ( !v4 )
      goto LABEL_8;
    if ( v4 == -2147483611 )
    {
      v6 = 0;
LABEL_5:
      v7 = RpcRevertToSelf();
      if ( v7 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
            WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v8, (unsigned int)"unknown", 0, v7);
        }
        __fastfail(7u);
      }
      return v6;
    }
    if ( v4 <= -1073741531 )
    {
      if ( v4 != -1073741531 )
      {
        switch ( v4 )
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
            goto LABEL_61;
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
            goto LABEL_57;
        }
        goto LABEL_5;
      }
LABEL_51:
      v6 = 2234;
      goto LABEL_7;
    }
    if ( v4 > -1073741495 )
    {
      switch ( v4 )
      {
        case -1073741433:
LABEL_61:
          v6 = 2226;
          goto LABEL_7;
        case -1073741421:
          v6 = 2239;
          goto LABEL_5;
        case -1073741261:
          v6 = 2453;
          goto LABEL_5;
      }
    }
    else
    {
      switch ( v4 )
      {
        case -1073741495:
          v6 = 2403;
          goto LABEL_5;
        case -1073741529:
          goto LABEL_51;
        case -1073741518:
          v6 = 2210;
          goto LABEL_5;
        case -1073741517:
          v6 = 2457;
          goto LABEL_5;
        case -1073741516:
          v6 = 2249;
          goto LABEL_5;
      }
    }
LABEL_57:
    v12 = RtlNtStatusToDosError(v4);
    v6 = 2140;
    if ( v12 != v5 )
      v6 = v12;
LABEL_7:
    if ( v5 < 0 )
      goto LABEL_5;
LABEL_8:
    v10 = NtQueryInformationToken(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
    v11 = v10;
    if ( !v10 )
    {
      v6 = 0;
LABEL_12:
      RtlCopyLuid(DestinationLuid, (PLUID)TokenInformation + 1);
      goto LABEL_13;
    }
    if ( v10 == -2147483611 )
    {
      v6 = 0;
LABEL_13:
      NtClose(TokenHandle);
      goto LABEL_5;
    }
    if ( v10 <= -1073741531 )
    {
      if ( v10 != -1073741531 )
      {
        switch ( v10 )
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
            goto LABEL_102;
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
            goto LABEL_98;
        }
        goto LABEL_13;
      }
LABEL_92:
      v6 = 2234;
      goto LABEL_14;
    }
    if ( v10 > -1073741495 )
    {
      switch ( v10 )
      {
        case -1073741433:
LABEL_102:
          v6 = 2226;
          goto LABEL_14;
        case -1073741421:
          v6 = 2239;
          goto LABEL_13;
        case -1073741261:
          v6 = 2453;
          goto LABEL_13;
      }
    }
    else
    {
      switch ( v10 )
      {
        case -1073741495:
          v6 = 2403;
          goto LABEL_13;
        case -1073741529:
          goto LABEL_92;
        case -1073741518:
          v6 = 2210;
          goto LABEL_13;
        case -1073741517:
          v6 = 2457;
          goto LABEL_13;
        case -1073741516:
          v6 = 2249;
          goto LABEL_13;
      }
    }
LABEL_98:
    v13 = RtlNtStatusToDosError(v10);
    v6 = 2140;
    if ( v13 != v11 )
      v6 = v13;
LABEL_14:
    if ( v11 < 0 )
      goto LABEL_13;
    goto LABEL_12;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v3, (unsigned int)"unknown", 0, v2);
  }
  return 5;
}

```

## disassembly

```asm
0x180002a60  push    rbx
0x180002a62  push    rbp
0x180002a63  push    rsi
0x180002a64  sub     rsp, 80h
0x180002a6b  mov     rax, cs:__security_cookie
0x180002a72  xor     rax, rsp
0x180002a75  mov     [rsp+98h+var_20], rax
0x180002a7a  xorps   xmm0, xmm0
0x180002a7d  mov     rsi, rcx
0x180002a80  xor     ebp, ebp
0x180002a82  xor     eax, eax
0x180002a84  xor     ecx, ecx; BindingHandle
0x180002a86  mov     [rsp+98h+TokenHandle], rbp
0x180002a8b  movups  [rsp+98h+TokenInformation], xmm0
0x180002a90  mov     [rsp+98h+var_28], rax
0x180002a95  movups  [rsp+98h+var_48], xmm0
0x180002a9a  mov     [rsp+98h+var_60], ebp
0x180002a9e  movups  [rsp+98h+var_38], xmm0
0x180002aa3  call    cs:__imp_RpcImpersonateClient
0x180002aa9  test    eax, eax
0x180002aab  jnz     loc_180002B91
0x180002ab1  mov     [rsp+98h+arg_8], rdi
0x180002ab9  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x180002abe  mov     r8b, 1; OpenAsSelf
0x180002ac1  mov     [rsp+98h+arg_10], r14
0x180002ac9  mov     edx, 8; DesiredAccess
0x180002ace  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180002ad5  call    cs:__imp_NtOpenThreadToken
0x180002adb  lea     r14, __ImageBase
0x180002ae2  mov     edi, eax
0x180002ae4  test    eax, eax
0x180002ae6  jz      short loc_180002B31
0x180002ae8  cmp     eax, 80000025h
0x180002aed  jnz     loc_180002BD7
0x180002af3  mov     ebx, ebp
0x180002af5  call    cs:__imp_RpcRevertToSelf
0x180002afb  mov     r14, [rsp+98h+arg_10]
0x180002b03  mov     rdi, [rsp+98h+arg_8]
0x180002b0b  test    eax, eax
0x180002b0d  jnz     loc_180002F05
0x180002b13  mov     eax, ebx
0x180002b15  mov     rcx, [rsp+98h+var_20]
0x180002b1a  xor     rcx, rsp; StackCookie
0x180002b1d  call    __security_check_cookie
0x180002b22  add     rsp, 80h
0x180002b29  pop     rsi
0x180002b2a  pop     rbp
0x180002b2b  pop     rbx
0x180002b2c  retn
0x180002b2d  test    edi, edi
0x180002b2f  js      short loc_180002AF5
0x180002b31  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x180002b36  lea     rax, [rsp+98h+var_60]
0x180002b3b  mov     r9d, 38h ; '8'; TokenInformationLength
0x180002b41  mov     [rsp+98h+ReturnLength], rax; ReturnLength
0x180002b46  lea     r8, [rsp+98h+TokenInformation]; TokenInformation
0x180002b4b  mov     edx, 0Ah; TokenInformationClass
0x180002b50  call    cs:__imp_NtQueryInformationToken
0x180002b56  mov     edi, eax
0x180002b58  test    eax, eax
0x180002b5a  jz      short loc_180002B6B
0x180002b5c  cmp     eax, 80000025h
0x180002b61  jnz     loc_180002D6E
0x180002b67  mov     ebx, ebp
0x180002b69  jmp     short loc_180002B7B
0x180002b6b  mov     ebx, ebp
0x180002b6d  lea     rdx, [rsp+98h+TokenInformation+8]; SourceLuid
0x180002b72  mov     rcx, rsi; DestinationLuid
0x180002b75  call    cs:__imp_RtlCopyLuid
0x180002b7b  mov     rcx, [rsp+98h+TokenHandle]; Handle
0x180002b80  call    cs:__imp_NtClose
0x180002b86  jmp     loc_180002AF5
0x180002b8b  test    edi, edi
0x180002b8d  js      short loc_180002B7B
0x180002b8f  jmp     short loc_180002B6D
0x180002b91  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180002b98  lea     rdx, WPP_GLOBAL_Control
0x180002b9f  cmp     rcx, rdx
0x180002ba2  jz      short loc_180002BCD
0x180002ba4  test    byte ptr [rcx+1Ch], 4
0x180002ba8  jz      short loc_180002BCD
0x180002baa  cmp     byte ptr [rcx+19h], 1
0x180002bae  jb      short loc_180002BCD
0x180002bb0  mov     rcx, [rcx+10h]
0x180002bb4  lea     r9, aUnknown; "unknown"
0x180002bbb  mov     [rsp+98h+var_70], eax
0x180002bbf  mov     edx, 0Ah
0x180002bc4  mov     dword ptr [rsp+98h+ReturnLength], ebp
0x180002bc8  call    WPP_SF_sdL
0x180002bcd  mov     eax, 5
0x180002bd2  jmp     loc_180002B15
0x180002bd7  cmp     edi, 0C0000125h
0x180002bdd  jg      loc_180002CC5
0x180002be3  jz      loc_180002D0D
0x180002be9  add     eax, 3FFFFFDDh; switch 230 cases
0x180002bee  cmp     eax, 0E5h
0x180002bf3  ja      def_180002C0F; jumptable 0000000180002C0F default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180002bf9  cdqe
0x180002bfb  movzx   eax, ds:(byte_180002FA0 - 180000000h)[r14+rax]
0x180002c04  mov     ecx, ds:(jpt_180002C0F - 180000000h)[r14+rax*4]
0x180002c0c  add     rcx, r14
0x180002c0f  jmp     rcx; switch jump
0x180002c11  mov     ebx, 84Bh; jumptable 0000000180002C0F case -1073741789
0x180002c16  jmp     loc_180002AF5
0x180002c1b  mov     ebx, 961h; jumptable 0000000180002C0F case -1073741561
0x180002c20  jmp     loc_180002AF5
0x180002c25  mov     ebx, 964h; jumptable 0000000180002C0F case -1073741560
0x180002c2a  jmp     loc_180002AF5
0x180002c2f  mov     ebx, 8C1h; jumptable 0000000180002C0F case -1073741713
0x180002c34  jmp     loc_180002AF5
0x180002c39  mov     ebx, 8C0h; jumptable 0000000180002C0F case -1073741712
0x180002c3e  jmp     loc_180002AF5
0x180002c43  mov     ebx, 8C2h; jumptable 0000000180002C0F case -1073741711
0x180002c48  jmp     loc_180002AF5
0x180002c4d  mov     ebx, 836h; jumptable 0000000180002C0F case -1073741573
0x180002c52  jmp     loc_180002AF5
0x180002c57  mov     ebx, 8AFh; jumptable 0000000180002C0F case -1073741723
0x180002c5c  jmp     loc_180002AF5
0x180002c61  mov     ebx, 8C7h; jumptable 0000000180002C0F case -1073741596
0x180002c66  jmp     loc_180002AF5
0x180002c6b  mov     ebx, 89Ah; jumptable 0000000180002C0F case -1073741726
0x180002c70  jmp     loc_180002AF5
0x180002c75  mov     ebx, 8B3h; jumptable 0000000180002C0F case -1073741603
0x180002c7a  jmp     loc_180002AF5
0x180002c7f  mov     ebx, 8BCh; jumptable 0000000180002C0F case -1073741721
0x180002c84  jmp     loc_180002AF5
0x180002c89  mov     ebx, 8BDh; jumptable 0000000180002C0F case -1073741720
0x180002c8e  jmp     loc_180002AF5
0x180002c93  mov     ebx, 8ACh; jumptable 0000000180002C0F cases -1073741722,-1073741709
0x180002c98  jmp     loc_180002AF5
0x180002c9d  mov     ebx, 8B0h; jumptable 0000000180002C0F case -1073741725
0x180002ca2  jmp     loc_180002AF5
0x180002ca7  mov     ebx, 8ADh; jumptable 0000000180002C0F case -1073741724
0x180002cac  jmp     loc_180002AF5
0x180002cb1  mov     ebx, 5; jumptable 0000000180002C0F case -1073741727
0x180002cb6  jmp     loc_180002AF5
0x180002cbb  mov     ebx, 8C5h; jumptable 0000000180002C0F case -1073741716
0x180002cc0  jmp     loc_180002AF5
0x180002cc5  cmp     edi, 0C0000149h
0x180002ccb  jg      short loc_180002D21
0x180002ccd  jz      short loc_180002D17
0x180002ccf  cmp     edi, 0C0000127h
0x180002cd5  jz      short loc_180002D0D
0x180002cd7  cmp     edi, 0C0000132h
0x180002cdd  jz      short loc_180002D03
0x180002cdf  cmp     edi, 0C0000133h
0x180002ce5  jz      short loc_180002CF9
0x180002ce7  cmp     edi, 0C0000134h
0x180002ced  jnz     short def_180002C0F; jumptable 0000000180002C0F default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180002cef  mov     ebx, 8C9h
0x180002cf4  jmp     loc_180002AF5
0x180002cf9  mov     ebx, 999h
0x180002cfe  jmp     loc_180002AF5
0x180002d03  mov     ebx, 8A2h
0x180002d08  jmp     loc_180002AF5
0x180002d0d  mov     ebx, 8BAh
0x180002d12  jmp     loc_180002B2D
0x180002d17  mov     ebx, 963h
0x180002d1c  jmp     loc_180002AF5
0x180002d21  cmp     edi, 0C0000187h
0x180002d27  jz      short loc_180002D64; jumptable 0000000180002C0F cases -1073741604,-1073741602
0x180002d29  cmp     edi, 0C0000193h
0x180002d2f  jz      short loc_180002D5A
0x180002d31  cmp     edi, 0C0000233h
0x180002d37  jnz     short def_180002C0F; jumptable 0000000180002C0F default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180002d39  mov     ebx, 995h
0x180002d3e  jmp     loc_180002AF5
0x180002d43  mov     ecx, edi; jumptable 0000000180002C0F default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180002d45  call    cs:__imp_RtlNtStatusToDosError
0x180002d4b  cmp     eax, edi
0x180002d4d  mov     ebx, 85Ch
0x180002d52  cmovnz  ebx, eax
0x180002d55  jmp     loc_180002B2D
0x180002d5a  mov     ebx, 8BFh
0x180002d5f  jmp     loc_180002AF5
0x180002d64  mov     ebx, 8B2h; jumptable 0000000180002C0F cases -1073741604,-1073741602
0x180002d69  jmp     loc_180002B2D
0x180002d6e  cmp     edi, 0C0000125h
0x180002d74  jg      loc_180002E5C
0x180002d7a  jz      loc_180002EA4
0x180002d80  add     eax, 3FFFFFDDh; switch 230 cases
0x180002d85  cmp     eax, 0E5h
0x180002d8a  ja      def_180002DA6; jumptable 0000000180002DA6 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180002d90  cdqe
0x180002d92  movzx   eax, ds:(byte_1800030D8 - 180000000h)[r14+rax]
0x180002d9b  mov     ecx, ds:(jpt_180002DA6 - 180000000h)[r14+rax*4]
0x180002da3  add     rcx, r14
0x180002da6  jmp     rcx; switch jump
0x180002da8  mov     ebx, 84Bh; jumptable 0000000180002DA6 case -1073741789
0x180002dad  jmp     loc_180002B7B
0x180002db2  mov     ebx, 961h; jumptable 0000000180002DA6 case -1073741561
0x180002db7  jmp     loc_180002B7B
0x180002dbc  mov     ebx, 964h; jumptable 0000000180002DA6 case -1073741560
0x180002dc1  jmp     loc_180002B7B
0x180002dc6  mov     ebx, 8C1h; jumptable 0000000180002DA6 case -1073741713
0x180002dcb  jmp     loc_180002B7B
0x180002dd0  mov     ebx, 8C0h; jumptable 0000000180002DA6 case -1073741712
0x180002dd5  jmp     loc_180002B7B
0x180002dda  mov     ebx, 8C2h; jumptable 0000000180002DA6 case -1073741711
0x180002ddf  jmp     loc_180002B7B
0x180002de4  mov     ebx, 836h; jumptable 0000000180002DA6 case -1073741573
0x180002de9  jmp     loc_180002B7B
0x180002dee  mov     ebx, 8AFh; jumptable 0000000180002DA6 case -1073741723
0x180002df3  jmp     loc_180002B7B
0x180002df8  mov     ebx, 8C7h; jumptable 0000000180002DA6 case -1073741596
0x180002dfd  jmp     loc_180002B7B
0x180002e02  mov     ebx, 89Ah; jumptable 0000000180002DA6 case -1073741726
0x180002e07  jmp     loc_180002B7B
0x180002e0c  mov     ebx, 8B3h; jumptable 0000000180002DA6 case -1073741603
0x180002e11  jmp     loc_180002B7B
0x180002e16  mov     ebx, 8BCh; jumptable 0000000180002DA6 case -1073741721
0x180002e1b  jmp     loc_180002B7B
0x180002e20  mov     ebx, 8BDh; jumptable 0000000180002DA6 case -1073741720
0x180002e25  jmp     loc_180002B7B
0x180002e2a  mov     ebx, 8ACh; jumptable 0000000180002DA6 cases -1073741722,-1073741709
0x180002e2f  jmp     loc_180002B7B
0x180002e34  mov     ebx, 8B0h; jumptable 0000000180002DA6 case -1073741725
0x180002e39  jmp     loc_180002B7B
0x180002e3e  mov     ebx, 8ADh; jumptable 0000000180002DA6 case -1073741724
0x180002e43  jmp     loc_180002B7B
0x180002e48  mov     ebx, 5; jumptable 0000000180002DA6 case -1073741727
0x180002e4d  jmp     loc_180002B7B
0x180002e52  mov     ebx, 8C5h; jumptable 0000000180002DA6 case -1073741716
0x180002e57  jmp     loc_180002B7B
0x180002e5c  cmp     edi, 0C0000149h
0x180002e62  jg      short loc_180002EB8
0x180002e64  jz      short loc_180002EAE
0x180002e66  cmp     edi, 0C0000127h
0x180002e6c  jz      short loc_180002EA4
0x180002e6e  cmp     edi, 0C0000132h
0x180002e74  jz      short loc_180002E9A
0x180002e76  cmp     edi, 0C0000133h
0x180002e7c  jz      short loc_180002E90
0x180002e7e  cmp     edi, 0C0000134h
0x180002e84  jnz     short def_180002DA6; jumptable 0000000180002DA6 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180002e86  mov     ebx, 8C9h
0x180002e8b  jmp     loc_180002B7B
0x180002e90  mov     ebx, 999h
0x180002e95  jmp     loc_180002B7B
0x180002e9a  mov     ebx, 8A2h
0x180002e9f  jmp     loc_180002B7B
0x180002ea4  mov     ebx, 8BAh
0x180002ea9  jmp     loc_180002B8B
0x180002eae  mov     ebx, 963h
0x180002eb3  jmp     loc_180002B7B
0x180002eb8  cmp     edi, 0C0000187h
0x180002ebe  jz      short loc_180002EFB; jumptable 0000000180002DA6 cases -1073741604,-1073741602
0x180002ec0  cmp     edi, 0C0000193h
0x180002ec6  jz      short loc_180002EF1
0x180002ec8  cmp     edi, 0C0000233h
0x180002ece  jnz     short def_180002DA6; jumptable 0000000180002DA6 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180002ed0  mov     ebx, 995h
0x180002ed5  jmp     loc_180002B7B
0x180002eda  mov     ecx, edi; jumptable 0000000180002DA6 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180002edc  call    cs:__imp_RtlNtStatusToDosError
0x180002ee2  cmp     eax, edi
0x180002ee4  mov     ebx, 85Ch
0x180002ee9  cmovnz  ebx, eax
0x180002eec  jmp     loc_180002B8B
0x180002ef1  mov     ebx, 8BFh
0x180002ef6  jmp     loc_180002B7B
0x180002efb  mov     ebx, 8B2h; jumptable 0000000180002DA6 cases -1073741604,-1073741602
0x180002f00  jmp     loc_180002B8B
0x180002f05  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180002f0c  lea     rdx, WPP_GLOBAL_Control
0x180002f13  cmp     rcx, rdx
0x180002f16  jz      short loc_180002F41
0x180002f18  test    byte ptr [rcx+1Ch], 4
0x180002f1c  jz      short loc_180002F41
0x180002f1e  cmp     byte ptr [rcx+19h], 1
0x180002f22  jb      short loc_180002F41
0x180002f24  mov     rcx, [rcx+10h]
0x180002f28  lea     r9, aUnknown; "unknown"
0x180002f2f  mov     [rsp+98h+var_70], eax
0x180002f33  mov     edx, 0Bh
0x180002f38  mov     dword ptr [rsp+98h+ReturnLength], ebp
0x180002f3c  call    WPP_SF_sdL
0x180002f41  mov     ecx, 7
0x180002f46  int     29h; Win8: RtlFailFast(ecx)
0x180002f48  jmp     loc_180002B13
```
