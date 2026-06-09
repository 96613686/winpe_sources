# ParseBrokerEventParameters(_BR_EVENT_PARAMETERS *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,_WNF_STATE_NAME &)

- ea: `0x180039fa0`
- end: `0x18003a26c`
- name: `?ParseBrokerEventParameters@@YAJPEAU_BR_EVENT_PARAMETERS@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEAU_WNF_STATE_NAME@@@Z`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c580`

## callees

- `0x18000498c`
- `0x18000659c`
- `0x180039fa0`
- `0x180051420`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18003a01c`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18003a0be`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18003a147`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18003a01c`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18003a0be`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18003a147`

## string_xrefs

- `0x18003a234`: `Invalid broker event parameters Parameter=%u, cParameters=%d.`
- `0x18003a19f`: `ParseBrokerEventParameters`
- `0x18003a24a`: `ParseBrokerEventParameters`
- `0x18003a213`: `Invalid  parameter RegistrationXml==null.`
- `0x18003a090`: `RegistrationXml`
- `0x18003a1d1`: `RegistrationXml`

## pseudocode

```c
__int64 __fastcall ParseBrokerEventParameters(unsigned __int16 *a1, char **a2, char **a3, _QWORD *a4)
{
  unsigned int v8; // ebp
  __int64 v9; // rbx
  int v10; // eax
  __int64 v11; // r8
  _WORD *v12; // r9
  unsigned __int64 v13; // rdx
  char *v14; // rsi
  __int64 v15; // rbx
  char **v16; // rcx
  int v17; // eax
  __int64 v18; // rax
  char *v19; // r9
  unsigned int v20; // edx
  int v22; // eax
  LPCWCH lpString2; // [rsp+20h] [rbp-78h]
  LPCWCH lpString2a; // [rsp+20h] [rbp-78h]
  LPCWCH lpString2b; // [rsp+20h] [rbp-78h]

  if ( !a1 )
  {
    v22 = 0;
LABEL_42:
    LogSmsRouterError(
      "ParseBrokerEventParameters",
      0x4Cu,
      -2147024809,
      "Invalid broker event parameters Parameter=%u, cParameters=%d.",
      a1,
      v22);
    return 2147942487LL;
  }
  if ( !*a1 )
  {
    v22 = *a1;
    goto LABEL_42;
  }
  v8 = 0;
  do
  {
    v9 = 32LL * v8;
    v10 = CompareStringEx(&LocaleName, 1u, *(LPCWCH *)(v9 + *((_QWORD *)a1 + 1)), -1, L"RegistrationName", -1, 0, 0, 0);
    v11 = *((_QWORD *)a1 + 1);
    if ( v10 == 2 )
    {
      if ( *(_DWORD *)(v9 + v11 + 8) != 2 )
      {
        LODWORD(lpString2) = *(_DWORD *)(v9 + v11 + 8);
        LogSmsRouterError(
          "ParseBrokerEventParameters",
          0x66u,
          -2147024809,
          "Invalid parameters type=%d for parameterName=%S.",
          lpString2,
          L"RegistrationName");
        return 2147942487LL;
      }
      v12 = *(_WORD **)(v9 + v11 + 16);
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      if ( v13 <= (unsigned __int64)a2[3] )
      {
        if ( (unsigned __int64)a2[3] <= 7 )
          v14 = (char *)a2;
        else
          v14 = *a2;
        a2[2] = (char *)v13;
LABEL_13:
        v15 = 2 * v13;
        memmove_0(v14, v12, 2 * v13);
        *(_WORD *)&v14[v15] = 0;
        goto LABEL_30;
      }
      v16 = a2;
LABEL_25:
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v16,
        v13,
        v11,
        v12);
      goto LABEL_30;
    }
    v17 = CompareStringEx(&LocaleName, 1u, *(LPCWCH *)(v9 + v11), -1, L"RegistrationXml", -1, 0, 0, 0);
    v11 = *((_QWORD *)a1 + 1);
    if ( v17 == 2 )
    {
      if ( *(_DWORD *)(v9 + v11 + 8) != 2 )
      {
        LODWORD(lpString2a) = *(_DWORD *)(v9 + v11 + 8);
        LogSmsRouterError(
          "ParseBrokerEventParameters",
          0x76u,
          -2147024809,
          "Invalid parameters type=%d for parameterName=%S.",
          lpString2a,
          L"RegistrationXml");
        return 2147942487LL;
      }
      v12 = *(_WORD **)(v9 + v11 + 16);
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      if ( v13 <= (unsigned __int64)a3[3] )
      {
        if ( (unsigned __int64)a3[3] <= 7 )
          v14 = (char *)a3;
        else
          v14 = *a3;
        a3[2] = (char *)v13;
        goto LABEL_13;
      }
      v16 = a3;
      goto LABEL_25;
    }
    if ( CompareStringEx(&LocaleName, 1u, *(LPCWCH *)(v9 + v11), -1, L"RegistrationWnf", -1, 0, 0, 0) == 2 )
    {
      v18 = *((_QWORD *)a1 + 1);
      if ( *(_DWORD *)(v9 + v18 + 8) != 4 || *(_WORD *)(v9 + v18 + 16) != 8 )
      {
        LODWORD(lpString2b) = *(_DWORD *)(v9 + v18 + 8);
        LogSmsRouterError(
          "ParseBrokerEventParameters",
          0x87u,
          -2147024809,
          "Invalid parameters type=%d for parameterName=%S.",
          lpString2b,
          L"RegistrationWnf");
        return 2147942487LL;
      }
      *a4 = **(_QWORD **)(v9 + v18 + 24);
    }
LABEL_30:
    ++v8;
  }
  while ( v8 < *a1 );
  if ( !a2[2] )
  {
    v19 = "Invalid  parameter RegistrationName==null.";
    v20 = 149;
LABEL_33:
    LogSmsRouterError("ParseBrokerEventParameters", v20, -2147024809, v19);
    return 2147942487LL;
  }
  if ( !a3[2] )
  {
    v19 = "Invalid  parameter RegistrationXml==null.";
    v20 = 156;
    goto LABEL_33;
  }
  return 0;
}

```

## disassembly

```asm
0x180039fa0  push    rbx
0x180039fa2  push    rbp
0x180039fa3  push    rsi
0x180039fa4  push    rdi
0x180039fa5  push    r12
0x180039fa7  push    r13
0x180039fa9  push    r14
0x180039fab  push    r15
0x180039fad  sub     rsp, 58h
0x180039fb1  xor     r13d, r13d
0x180039fb4  mov     r12, r9
0x180039fb7  mov     r14, r8
0x180039fba  mov     r15, rdx
0x180039fbd  mov     rdi, rcx
0x180039fc0  test    rcx, rcx
0x180039fc3  jz      loc_18003A22D
0x180039fc9  cmp     r13w, [rcx]
0x180039fcd  jz      loc_18003A228
0x180039fd3  mov     ebp, r13d
0x180039fd6  jnb     loc_18003A188
0x180039fdc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180039fe0  mov     r8, [rdi+8]
0x180039fe4  lea     rax, aRegistrationna_0; "RegistrationName"
0x180039feb  mov     [rsp+98h+lParam], r13; lParam
0x180039ff0  lea     rcx, LocaleName; lpLocaleName
0x180039ff7  mov     [rsp+98h+lpReserved], r13; lpReserved
0x180039ffc  mov     r9d, esi; cchCount1
0x180039fff  mov     [rsp+98h+lpVersionInformation], r13; lpVersionInformation
0x18003a004  mov     edx, 1; dwCmpFlags
0x18003a009  mov     ebx, ebp
0x18003a00b  shl     rbx, 5
0x18003a00f  mov     [rsp+98h+cchCount2], esi; cchCount2
0x18003a013  mov     [rsp+98h+lpString2], rax; lpString2
0x18003a018  mov     r8, [rbx+r8]; lpString1
0x18003a01c  call    cs:__imp_CompareStringEx
0x18003a022  mov     r8, [rdi+8]
0x18003a026  cmp     eax, 2
0x18003a029  jnz     short loc_18003A08C
0x18003a02b  mov     eax, [rbx+r8+8]
0x18003a030  cmp     eax, 2
0x18003a033  jnz     loc_18003A1B3
0x18003a039  mov     r9, [rbx+r8+10h]
0x18003a03e  mov     rdx, rsi
0x18003a041  inc     rdx
0x18003a044  cmp     [r9+rdx*2], r13w
0x18003a049  jnz     short loc_18003A041
0x18003a04b  cmp     rdx, [r15+18h]
0x18003a04f  ja      short loc_18003A084
0x18003a051  cmp     qword ptr [r15+18h], 7
0x18003a056  jbe     short loc_18003A05D
0x18003a058  mov     rsi, [r15]
0x18003a05b  jmp     short loc_18003A060
0x18003a05d  mov     rsi, r15
0x18003a060  mov     [r15+10h], rdx
0x18003a064  lea     rbx, [rdx+rdx]
0x18003a068  mov     rcx, rsi; void *
0x18003a06b  mov     r8, rbx; Size
0x18003a06e  mov     rdx, r9; Src
0x18003a071  call    memmove_0
0x18003a076  mov     [rbx+rsi], r13w
0x18003a07b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003a07f  jmp     loc_18003A17B
0x18003a084  mov     rcx, r15
0x18003a087  jmp     loc_18003A10E
0x18003a08c  mov     r8, [rbx+r8]; lpString1
0x18003a090  lea     rax, aRegistrationxm; "RegistrationXml"
0x18003a097  mov     [rsp+98h+lParam], r13; lParam
0x18003a09c  lea     rcx, LocaleName; lpLocaleName
0x18003a0a3  mov     [rsp+98h+lpReserved], r13; lpReserved
0x18003a0a8  mov     r9d, esi; cchCount1
0x18003a0ab  mov     [rsp+98h+lpVersionInformation], r13; lpVersionInformation
0x18003a0b0  mov     edx, 1; dwCmpFlags
0x18003a0b5  mov     [rsp+98h+cchCount2], esi; cchCount2
0x18003a0b9  mov     [rsp+98h+lpString2], rax; lpString2
0x18003a0be  call    cs:__imp_CompareStringEx
0x18003a0c4  mov     r8, [rdi+8]
0x18003a0c8  cmp     eax, 2
0x18003a0cb  jnz     short loc_18003A115
0x18003a0cd  mov     eax, [rbx+r8+8]
0x18003a0d2  cmp     eax, 2
0x18003a0d5  jnz     loc_18003A1D1
0x18003a0db  mov     r9, [rbx+r8+10h]
0x18003a0e0  mov     rdx, rsi
0x18003a0e3  inc     rdx
0x18003a0e6  cmp     [r9+rdx*2], r13w
0x18003a0eb  jnz     short loc_18003A0E3
0x18003a0ed  cmp     rdx, [r14+18h]
0x18003a0f1  ja      short loc_18003A10B
0x18003a0f3  cmp     qword ptr [r14+18h], 7
0x18003a0f8  jbe     short loc_18003A0FF
0x18003a0fa  mov     rsi, [r14]
0x18003a0fd  jmp     short loc_18003A102
0x18003a0ff  mov     rsi, r14
0x18003a102  mov     [r14+10h], rdx
0x18003a106  jmp     loc_18003A064
0x18003a10b  mov     rcx, r14
0x18003a10e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18003a113  jmp     short loc_18003A17B
0x18003a115  mov     r8, [rbx+r8]; lpString1
0x18003a119  lea     rax, aRegistrationwn; "RegistrationWnf"
0x18003a120  mov     [rsp+98h+lParam], r13; lParam
0x18003a125  lea     rcx, LocaleName; lpLocaleName
0x18003a12c  mov     [rsp+98h+lpReserved], r13; lpReserved
0x18003a131  mov     r9d, esi; cchCount1
0x18003a134  mov     [rsp+98h+lpVersionInformation], r13; lpVersionInformation
0x18003a139  mov     edx, 1; dwCmpFlags
0x18003a13e  mov     [rsp+98h+cchCount2], esi; cchCount2
0x18003a142  mov     [rsp+98h+lpString2], rax; lpString2
0x18003a147  call    cs:__imp_CompareStringEx
0x18003a14d  cmp     eax, 2
0x18003a150  jnz     short loc_18003A17B
0x18003a152  mov     rax, [rdi+8]
0x18003a156  mov     ecx, [rbx+rax+8]
0x18003a15a  cmp     ecx, 4
0x18003a15d  jnz     loc_18003A1EF
0x18003a163  cmp     word ptr [rbx+rax+10h], 8
0x18003a169  jnz     loc_18003A1EF
0x18003a16f  mov     rax, [rbx+rax+18h]
0x18003a174  mov     rcx, [rax]
0x18003a177  mov     [r12], rcx
0x18003a17b  movzx   eax, word ptr [rdi]
0x18003a17e  inc     ebp
0x18003a180  cmp     ebp, eax
0x18003a182  jb      loc_180039FE0
0x18003a188  cmp     [r15+10h], r13
0x18003a18c  jnz     short loc_18003A20D
0x18003a18e  lea     r9, aInvalidParamet_0; "Invalid  parameter RegistrationName==nu"...
0x18003a195  mov     edx, 95h; unsigned int
0x18003a19a  mov     ebx, 80070057h
0x18003a19f  lea     rcx, aParsebrokereve; "ParseBrokerEventParameters"
0x18003a1a6  mov     r8d, ebx; int
0x18003a1a9  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003a1ae  jmp     loc_18003A259
0x18003a1b3  lea     rcx, aRegistrationna_0; "RegistrationName"
0x18003a1ba  mov     edx, 66h ; 'f'
0x18003a1bf  mov     qword ptr [rsp+98h+cchCount2], rcx
0x18003a1c4  lea     r9, aInvalidParamet; "Invalid parameters type=%d for paramete"...
0x18003a1cb  mov     dword ptr [rsp+98h+lpString2], eax
0x18003a1cf  jmp     short loc_18003A245
0x18003a1d1  lea     rcx, aRegistrationxm; "RegistrationXml"
0x18003a1d8  mov     edx, 76h ; 'v'
0x18003a1dd  mov     qword ptr [rsp+98h+cchCount2], rcx
0x18003a1e2  lea     r9, aInvalidParamet; "Invalid parameters type=%d for paramete"...
0x18003a1e9  mov     dword ptr [rsp+98h+lpString2], eax
0x18003a1ed  jmp     short loc_18003A245
0x18003a1ef  lea     rax, aRegistrationwn; "RegistrationWnf"
0x18003a1f6  mov     edx, 87h
0x18003a1fb  mov     qword ptr [rsp+98h+cchCount2], rax
0x18003a200  lea     r9, aInvalidParamet; "Invalid parameters type=%d for paramete"...
0x18003a207  mov     dword ptr [rsp+98h+lpString2], ecx
0x18003a20b  jmp     short loc_18003A245
0x18003a20d  cmp     [r14+10h], r13
0x18003a211  jnz     short loc_18003A224
0x18003a213  lea     r9, aInvalidParamet_1; "Invalid  parameter RegistrationXml==nul"...
0x18003a21a  mov     edx, 9Ch
0x18003a21f  jmp     loc_18003A19A
0x18003a224  xor     eax, eax
0x18003a226  jmp     short loc_18003A25B
0x18003a228  movzx   eax, word ptr [rcx]
0x18003a22b  jmp     short loc_18003A230
0x18003a22d  mov     eax, r13d
0x18003a230  mov     [rsp+98h+cchCount2], eax
0x18003a234  lea     r9, aInvalidBrokerE; "Invalid broker event parameters Paramet"...
0x18003a23b  mov     [rsp+98h+lpString2], rdi
0x18003a240  mov     edx, 4Ch ; 'L'; unsigned int
0x18003a245  mov     ebx, 80070057h
0x18003a24a  lea     rcx, aParsebrokereve; "ParseBrokerEventParameters"
0x18003a251  mov     r8d, ebx; int
0x18003a254  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003a259  mov     eax, ebx
0x18003a25b  add     rsp, 58h
0x18003a25f  pop     r15
0x18003a261  pop     r14
0x18003a263  pop     r13
0x18003a265  pop     r12
0x18003a267  pop     rdi
0x18003a268  pop     rsi
0x18003a269  pop     rbp
0x18003a26a  pop     rbx
0x18003a26b  retn
```
