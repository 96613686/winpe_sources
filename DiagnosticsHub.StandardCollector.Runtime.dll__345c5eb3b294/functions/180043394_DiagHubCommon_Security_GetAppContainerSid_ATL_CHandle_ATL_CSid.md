# DiagHubCommon::Security::GetAppContainerSid(ATL::CHandle &,ATL::CSid &)

- ea: `0x180043394`
- end: `0x18004352d`
- name: `?GetAppContainerSid@Security@DiagHubCommon@@SAJAEAVCHandle@ATL@@AEAVCSid@4@@Z`
- size: `409`
- prototype: `__int64 __fastcall(struct ATL::CHandle *, struct ATL::CSid *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002eb3c`

## callees

- `0x180031284`
- `0x18003153c`
- `0x1800315c8`
- `0x1800316c4`
- `0x180043394`
- `0x180049b50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180043406`
- `KERNEL32!GetLastError` at `0x180043466`
- `KERNEL32!GetLastError` at `0x180043471`
- `KERNEL32!GetLastError` at `0x1800434c9`
- `KERNEL32!GetLastError` at `0x180043406`
- `KERNEL32!GetLastError` at `0x180043466`
- `KERNEL32!GetLastError` at `0x180043471`
- `KERNEL32!GetLastError` at `0x1800434c9`
- `ADVAPI32!GetTokenInformation` at `0x1800433fc`
- `ADVAPI32!GetTokenInformation` at `0x180043460`
- `ADVAPI32!GetTokenInformation` at `0x1800434bf`
- `ADVAPI32!GetTokenInformation` at `0x1800433fc`
- `ADVAPI32!GetTokenInformation` at `0x180043460`
- `ADVAPI32!GetTokenInformation` at `0x1800434bf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180043506`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180043506`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18004348e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18004348e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DiagHubCommon::Security::GetAppContainerSid(HANDLE *a1, struct ATL::CSid *a2)
{
  __int64 v4; // rax
  DWORD LastError; // eax
  int v6; // ecx
  __int64 result; // rax
  signed int v8; // ecx
  const struct _SID **v9; // rbx
  unsigned int v10; // edi
  const unsigned __int16 *v11; // r8
  signed int v12; // eax
  __int64 v13; // rax
  _BYTE v14[128]; // [rsp+30h] [rbp-59h] BYREF
  DWORD TokenInformationLength; // [rsp+B0h] [rbp+27h] BYREF
  int TokenInformation; // [rsp+B4h] [rbp+2Bh] BYREF
  DWORD ReturnLength[2]; // [rsp+B8h] [rbp+2Fh] BYREF

  v4 = ATL::CSid::CSid((ATL::CSid *)v14);
  ATL::CSid::operator=(a2, v4);
  ATL::CSid::~CSid((ATL::CSid *)v14);
  TokenInformation = 0;
  if ( GetTokenInformation(*a1, TokenIsAppContainer, &TokenInformation, 4u, ReturnLength) )
  {
    result = TokenInformation == 0;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError == 87 || LastError == 1 )
      return 1;
    result = (unsigned __int16)LastError | 0x80070000;
    if ( v6 <= 0 )
      result = (unsigned int)v6;
  }
  if ( (int)result < 0 )
  {
    _mm_lfence();
    return result;
  }
  if ( (_DWORD)result == 1 )
    return 1;
  GetTokenInformation(*a1, TokenAppContainerSid, 0, 0, &TokenInformationLength);
  if ( GetLastError() == 122 )
  {
    v9 = (const struct _SID **)malloc(TokenInformationLength);
    *(_QWORD *)ReturnLength = v9;
    if ( v9 )
    {
      if ( GetTokenInformation(*a1, TokenAppContainerSid, v9, TokenInformationLength, &TokenInformationLength) )
      {
        v13 = ATL::CSid::CSid((ATL::CSid *)v14, *v9, v11);
        ATL::CSid::operator=(a2, v13);
        ATL::CSid::~CSid((ATL::CSid *)v14);
        v10 = 0;
      }
      else
      {
        v12 = GetLastError();
        v10 = (unsigned __int16)v12 | 0x80070000;
        if ( v12 <= 0 )
          v10 = v12;
      }
    }
    else
    {
      v10 = -2147024882;
    }
    free(v9);
    return v10;
  }
  else
  {
    v8 = GetLastError();
    result = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x180043394  mov     [rsp-8+arg_10], rbx
0x180043399  push    rbp
0x18004339a  push    rsi
0x18004339b  push    rdi
0x18004339c  lea     rbp, [rsp-47h]
0x1800433a1  sub     rsp, 0D0h
0x1800433a8  mov     rax, cs:__security_cookie
0x1800433af  xor     rax, rsp
0x1800433b2  mov     [rbp+57h+var_20], rax
0x1800433b6  mov     rsi, rdx
0x1800433b9  mov     rdi, rcx
0x1800433bc  lea     rcx, [rbp+57h+var_B0]; this
0x1800433c0  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x1800433c5  nop
0x1800433c6  mov     rdx, rax
0x1800433c9  mov     rcx, rsi
0x1800433cc  call    ??4CSid@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSid::operator=(ATL::CSid const &)
0x1800433d1  nop
0x1800433d2  lea     rcx, [rbp+57h+var_B0]; this
0x1800433d6  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1800433db  mov     [rbp+57h+TokenInformation], 0
0x1800433e2  lea     rax, [rbp+57h+var_28]
0x1800433e6  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800433eb  mov     r9d, 4; TokenInformationLength
0x1800433f1  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800433f5  lea     edx, [r9+19h]; TokenInformationClass
0x1800433f9  mov     rcx, [rdi]; TokenHandle
0x1800433fc  call    cs:__imp_GetTokenInformation
0x180043402  test    eax, eax
0x180043404  jnz     short loc_180043427
0x180043406  call    cs:__imp_GetLastError
0x18004340c  mov     ecx, eax
0x18004340e  cmp     eax, 57h ; 'W'
0x180043411  jz      short loc_180043440
0x180043413  cmp     eax, 1
0x180043416  jz      short loc_180043440
0x180043418  movzx   eax, cx
0x18004341b  or      eax, 80070000h
0x180043420  test    ecx, ecx
0x180043422  cmovle  eax, ecx
0x180043425  jmp     short loc_18004342F
0x180043427  xor     eax, eax
0x180043429  cmp     [rbp+57h+TokenInformation], eax
0x18004342c  setz    al
0x18004342f  test    eax, eax
0x180043431  jns     short loc_18004343B
0x180043433  lfence
0x180043436  jmp     loc_18004350E
0x18004343b  cmp     eax, 1
0x18004343e  jnz     short loc_18004344A
0x180043440  mov     eax, 1
0x180043445  jmp     loc_18004350E
0x18004344a  lea     rax, [rbp+57h+TokenInformationLength]
0x18004344e  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180043453  xor     r9d, r9d; TokenInformationLength
0x180043456  xor     r8d, r8d; TokenInformation
0x180043459  lea     edx, [r9+1Fh]; TokenInformationClass
0x18004345d  mov     rcx, [rdi]; TokenHandle
0x180043460  call    cs:__imp_GetTokenInformation
0x180043466  call    cs:__imp_GetLastError
0x18004346c  cmp     eax, 7Ah ; 'z'
0x18004346f  jz      short loc_18004348B
0x180043471  call    cs:__imp_GetLastError
0x180043477  mov     ecx, eax
0x180043479  movzx   eax, ax
0x18004347c  or      eax, 80070000h
0x180043481  test    ecx, ecx
0x180043483  cmovle  eax, ecx
0x180043486  jmp     loc_18004350E
0x18004348b  mov     ecx, [rbp+57h+TokenInformationLength]; Size
0x18004348e  call    cs:__imp_malloc
0x180043494  mov     rbx, rax
0x180043497  mov     qword ptr [rbp+57h+var_28], rax
0x18004349b  test    rax, rax
0x18004349e  jnz     short loc_1800434A7
0x1800434a0  mov     edi, 8007000Eh
0x1800434a5  jmp     short loc_180043503
0x1800434a7  lea     rax, [rbp+57h+TokenInformationLength]
0x1800434ab  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800434b0  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800434b4  mov     r8, rbx; TokenInformation
0x1800434b7  mov     edx, 1Fh; TokenInformationClass
0x1800434bc  mov     rcx, [rdi]; TokenHandle
0x1800434bf  call    cs:__imp_GetTokenInformation
0x1800434c5  test    eax, eax
0x1800434c7  jnz     short loc_1800434DF
0x1800434c9  call    cs:__imp_GetLastError
0x1800434cf  movzx   edi, ax
0x1800434d2  or      edi, 80070000h
0x1800434d8  test    eax, eax
0x1800434da  cmovle  edi, eax
0x1800434dd  jmp     short loc_180043503
0x1800434df  mov     rdx, [rbx]; struct _SID *
0x1800434e2  lea     rcx, [rbp+57h+var_B0]; this
0x1800434e6  call    ??0CSid@ATL@@QEAA@PEBU_SID@@PEBG@Z; ATL::CSid::CSid(_SID const *,ushort const *)
0x1800434eb  nop
0x1800434ec  mov     rdx, rax
0x1800434ef  mov     rcx, rsi
0x1800434f2  call    ??4CSid@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSid::operator=(ATL::CSid const &)
0x1800434f7  nop
0x1800434f8  lea     rcx, [rbp+57h+var_B0]; this
0x1800434fc  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180043501  xor     edi, edi
0x180043503  mov     rcx, rbx; Block
0x180043506  call    cs:__imp_free
0x18004350c  mov     eax, edi
0x18004350e  mov     rcx, [rbp+57h+var_20]
0x180043512  xor     rcx, rsp; StackCookie
0x180043515  call    __security_check_cookie
0x18004351a  mov     rbx, [rsp+0E0h+arg_10]
0x180043522  add     rsp, 0D0h
0x180043529  pop     rdi
0x18004352a  pop     rsi
0x18004352b  pop     rbp
0x18004352c  retn
```
