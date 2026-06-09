# sub_1800BBCEC

- ea: `0x1800bbcec`
- end: `0x1800bbe96`
- name: `sub_1800BBCEC`
- size: `426`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180060a78`
- `0x1800bc7e0`
- `0x1800bc920`
- `0x1800bca60`
- `0x1800bcd80`

## callees

- `0x180060dc8`
- `0x180068f60`
- `0x1800bbcec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbd79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbe03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbd79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbe03`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bbda0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bbe2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bbda0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bbe2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbd92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbdb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbdc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbe1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbe64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbe76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbd92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbdb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbdc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbe1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbe64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbe76`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800bbdf9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800bbdf9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bbd6f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bbd6f`
- `ntdll!RtlEqualSid` at `0x1800bbe4d`
- `ntdll!RtlEqualSid` at `0x1800bbe4d`

## pseudocode

```c
__int64 __fastcall sub_1800BBCEC(HANDLE *a1)
{
  PSID *v2; // rdi
  DWORD LastError; // ebx
  HLOCAL v4; // rcx
  _BYTE *v6; // rbx
  DWORD v7; // esi
  BOOL v8; // ebx
  HLOCAL hMem; // [rsp+30h] [rbp-79h] BYREF
  DWORD TokenInformationLength; // [rsp+38h] [rbp-71h] BYREF
  HLOCAL v11; // [rsp+40h] [rbp-69h] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-61h] BYREF
  HLOCAL *v13; // [rsp+50h] [rbp-59h]
  HLOCAL *p_hMem; // [rsp+58h] [rbp-51h]
  _BYTE TokenInformation[32]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE pSid[80]; // [rsp+80h] [rbp-29h] BYREF

  TokenInformationLength = 32;
  v2 = (PSID *)TokenInformation;
  v11 = 0;
  v13 = &v11;
  cbSid = 68;
  hMem = 0;
  p_hMem = &hMem;
  if ( !*a1 )
    sub_180060DC8();
  LastError = 122;
  while ( LastError == 122 )
  {
    if ( GetTokenInformation(*a1, TokenIntegrityLevel, v2, TokenInformationLength, &TokenInformationLength) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError != 122 )
        goto LABEL_10;
      if ( v2 != (PSID *)TokenInformation )
        LocalFree(v2);
      v2 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
      v11 = v2;
      if ( !v2 )
      {
LABEL_10:
        v4 = hMem;
LABEL_11:
        LocalFree(v4);
        hMem = 0;
        LocalFree(v11);
        return 1;
      }
    }
  }
  v6 = pSid;
  v7 = 122;
  while ( v7 == 122 )
  {
    if ( CreateWellKnownSid(WinLowLabelSid, 0, v6, &cbSid) )
    {
      v7 = 0;
    }
    else
    {
      v7 = GetLastError();
      if ( v7 != 122 )
        goto LABEL_10;
      if ( v6 != pSid )
        LocalFree(v6);
      v6 = LocalAlloc(0x40u, cbSid);
      hMem = v6;
      if ( !v6 )
      {
        v4 = 0;
        goto LABEL_11;
      }
    }
  }
  v8 = RtlEqualSid(v6, *v2) != 0;
  LocalFree(hMem);
  hMem = 0;
  LocalFree(v11);
  return v8;
}

```

## disassembly

```asm
0x1800bbcec  push    rbp
0x1800bbcee  push    rbx
0x1800bbcef  push    rsi
0x1800bbcf0  push    rdi
0x1800bbcf1  lea     rbp, [rsp-3Fh]
0x1800bbcf6  sub     rsp, 0E8h
0x1800bbcfd  mov     rax, cs:__security_cookie
0x1800bbd04  xor     rax, rsp
0x1800bbd07  mov     [rbp+57h+var_30], rax
0x1800bbd0b  mov     rsi, rcx
0x1800bbd0e  mov     [rbp+57h+TokenInformationLength], 20h ; ' '
0x1800bbd15  lea     rdi, [rbp+57h+TokenInformation]
0x1800bbd19  mov     [rbp+57h+var_C0], 0
0x1800bbd21  lea     rax, [rbp+57h+var_C0]
0x1800bbd25  mov     [rbp+57h+var_B0], rax
0x1800bbd29  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800bbd30  mov     [rbp+57h+hMem], 0
0x1800bbd38  lea     rax, [rbp+57h+hMem]
0x1800bbd3c  mov     [rbp+57h+var_A8], rax
0x1800bbd40  cmp     qword ptr [rcx], 0
0x1800bbd44  jnz     short loc_1800BBD4B
0x1800bbd46  call    sub_180060DC8
0x1800bbd4b  mov     ebx, 7Ah ; 'z'
0x1800bbd50  cmp     ebx, 7Ah ; 'z'
0x1800bbd53  jnz     loc_1800BBDDF
0x1800bbd59  lea     rax, [rbp+57h+TokenInformationLength]
0x1800bbd5d  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x1800bbd62  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800bbd66  mov     r8, rdi; TokenInformation
0x1800bbd69  lea     edx, [rbx-61h]; TokenInformationClass
0x1800bbd6c  mov     rcx, [rsi]; TokenHandle
0x1800bbd6f  call    cs:GetTokenInformation
0x1800bbd75  test    eax, eax
0x1800bbd77  jnz     short loc_1800BBDD8
0x1800bbd79  call    cs:GetLastError
0x1800bbd7f  mov     ebx, eax
0x1800bbd81  cmp     eax, 7Ah ; 'z'
0x1800bbd84  jnz     short loc_1800BBDB2
0x1800bbd86  lea     rax, [rbp+57h+TokenInformation]
0x1800bbd8a  cmp     rdi, rax
0x1800bbd8d  jz      short loc_1800BBD98
0x1800bbd8f  mov     rcx, rdi; hMem
0x1800bbd92  call    cs:LocalFree
0x1800bbd98  mov     edx, [rbp+57h+TokenInformationLength]; uBytes
0x1800bbd9b  mov     ecx, 40h ; '@'; uFlags
0x1800bbda0  call    cs:LocalAlloc
0x1800bbda6  mov     rdi, rax
0x1800bbda9  mov     [rbp+57h+var_C0], rax
0x1800bbdad  test    rax, rax
0x1800bbdb0  jnz     short loc_1800BBD50
0x1800bbdb2  mov     rcx, [rbp+57h+hMem]; hMem
0x1800bbdb6  call    cs:LocalFree
0x1800bbdbc  mov     [rbp+57h+hMem], 0
0x1800bbdc4  mov     rcx, [rbp+57h+var_C0]; hMem
0x1800bbdc8  call    cs:LocalFree
0x1800bbdce  mov     eax, 1
0x1800bbdd3  jmp     loc_1800BBE7E
0x1800bbdd8  xor     ebx, ebx
0x1800bbdda  jmp     loc_1800BBD50
0x1800bbddf  lea     rbx, [rbp+57h+pSid]
0x1800bbde3  mov     esi, 7Ah ; 'z'
0x1800bbde8  cmp     esi, 7Ah ; 'z'
0x1800bbdeb  jnz     short loc_1800BBE47
0x1800bbded  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800bbdf1  mov     r8, rbx; pSid
0x1800bbdf4  xor     edx, edx; DomainSid
0x1800bbdf6  lea     ecx, [rsi-38h]; WellKnownSidType
0x1800bbdf9  call    cs:CreateWellKnownSid
0x1800bbdff  test    eax, eax
0x1800bbe01  jnz     short loc_1800BBE43
0x1800bbe03  call    cs:GetLastError
0x1800bbe09  mov     esi, eax
0x1800bbe0b  cmp     eax, 7Ah ; 'z'
0x1800bbe0e  jnz     short loc_1800BBDB2
0x1800bbe10  lea     rax, [rbp+57h+pSid]
0x1800bbe14  cmp     rbx, rax
0x1800bbe17  jz      short loc_1800BBE22
0x1800bbe19  mov     rcx, rbx; hMem
0x1800bbe1c  call    cs:LocalFree
0x1800bbe22  mov     edx, [rbp+57h+cbSid]; uBytes
0x1800bbe25  mov     ecx, 40h ; '@'; uFlags
0x1800bbe2a  call    cs:LocalAlloc
0x1800bbe30  mov     rbx, rax
0x1800bbe33  mov     [rbp+57h+hMem], rax
0x1800bbe37  test    rax, rax
0x1800bbe3a  jnz     short loc_1800BBDE8
0x1800bbe3c  xor     ecx, ecx
0x1800bbe3e  jmp     loc_1800BBDB6
0x1800bbe43  xor     esi, esi
0x1800bbe45  jmp     short loc_1800BBDE8
0x1800bbe47  mov     rdx, [rdi]; Sid2
0x1800bbe4a  mov     rcx, rbx; Sid1
0x1800bbe4d  call    cs:RtlEqualSid
0x1800bbe53  test    al, al
0x1800bbe55  jz      short loc_1800BBE5E
0x1800bbe57  mov     ebx, 1
0x1800bbe5c  jmp     short loc_1800BBE60
0x1800bbe5e  xor     ebx, ebx
0x1800bbe60  mov     rcx, [rbp+57h+hMem]; hMem
0x1800bbe64  call    cs:LocalFree
0x1800bbe6a  mov     [rbp+57h+hMem], 0
0x1800bbe72  mov     rcx, [rbp+57h+var_C0]; hMem
0x1800bbe76  call    cs:LocalFree
0x1800bbe7c  mov     eax, ebx
0x1800bbe7e  mov     rcx, [rbp+57h+var_30]
0x1800bbe82  xor     rcx, rsp; StackCookie
0x1800bbe85  call    __security_check_cookie
0x1800bbe8a  add     rsp, 0E8h
0x1800bbe91  pop     rdi
0x1800bbe92  pop     rsi
0x1800bbe93  pop     rbx
0x1800bbe94  pop     rbp
0x1800bbe95  retn
```
