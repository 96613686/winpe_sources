# LocationCallerInfoHelper::GetAppContainerSid(ATL::CAccessToken const &,ATL::CSid &)

- ea: `0x18005affc`
- end: `0x18005b141`
- name: `?GetAppContainerSid@LocationCallerInfoHelper@@SAJAEBVCAccessToken@ATL@@AEAVCSid@3@@Z`
- size: `325`
- prototype: `static int(const struct ATL::CAccessToken *, struct ATL::CSid *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017c0c`
- `0x18001de04`

## callees

- `0x18001e858`
- `0x18001eb88`
- `0x18005affc`
- `0x1800a98c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0fe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005b056`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005b0bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005b056`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005b0bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b08a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b08a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b0f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b11c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b0f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b11c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LocationCallerInfoHelper::GetAppContainerSid(HANDLE *a1, struct ATL::CSid *a2)
{
  DWORD LastError; // eax
  unsigned int v6; // ebx
  struct _SID **v7; // rbx
  const unsigned __int16 *v8; // r8
  signed int v9; // eax
  unsigned int v10; // edi
  signed int v11; // eax
  DWORD TokenInformationLength; // [rsp+38h] [rbp-20h] BYREF

  if ( ATL::CSid::IsValid(a2) )
    return 2147942487LL;
  TokenInformationLength = 0;
  if ( GetTokenInformation(a1[1], TokenAppContainerSid, 0, 0, &TokenInformationLength) )
  {
LABEL_17:
    v6 = -2147418113;
    goto LABEL_18;
  }
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( LastError )
    {
      v11 = GetLastError();
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      goto LABEL_18;
    }
    goto LABEL_17;
  }
  if ( TokenInformationLength == 8 )
  {
    v6 = -2147023728;
LABEL_18:
    LocalFree(0);
    return v6;
  }
  v7 = (struct _SID **)LocalAlloc(0, TokenInformationLength);
  if ( !v7 )
  {
    v6 = -2147024882;
    goto LABEL_18;
  }
  if ( GetTokenInformation(a1[1], TokenAppContainerSid, v7, TokenInformationLength, &TokenInformationLength) )
  {
    ATL::CSid::LoadAccount(a2, *v7, v8);
    v10 = 0;
  }
  else
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
  }
  LocalFree(v7);
  return v10;
}

```

## disassembly

```asm
0x18005affc  mov     [rsp+arg_10], rbx
0x18005b001  mov     [rsp+arg_18], rsi
0x18005b006  push    rdi
0x18005b007  sub     rsp, 50h
0x18005b00b  mov     rax, cs:__security_cookie
0x18005b012  xor     rax, rsp
0x18005b015  mov     [rsp+58h+var_18], rax
0x18005b01a  mov     rdi, rdx
0x18005b01d  mov     rsi, rcx
0x18005b020  mov     rcx, rdx; this
0x18005b023  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x18005b028  test    al, al
0x18005b02a  jz      short loc_18005B036
0x18005b02c  mov     eax, 80070057h
0x18005b031  jmp     loc_18005B124
0x18005b036  mov     [rsp+58h+TokenInformationLength], 0
0x18005b03e  lea     rax, [rsp+58h+TokenInformationLength]
0x18005b043  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18005b048  xor     r9d, r9d; TokenInformationLength
0x18005b04b  xor     r8d, r8d; TokenInformation
0x18005b04e  lea     edx, [r9+1Fh]; TokenInformationClass
0x18005b052  mov     rcx, [rsi+8]; TokenHandle
0x18005b056  call    cs:__imp_GetTokenInformation
0x18005b05c  test    eax, eax
0x18005b05e  jnz     loc_18005B115
0x18005b064  call    cs:__imp_GetLastError
0x18005b06a  cmp     eax, 7Ah ; 'z'
0x18005b06d  jnz     loc_18005B0FA
0x18005b073  cmp     [rsp+58h+TokenInformationLength], 8
0x18005b078  jnz     short loc_18005B084
0x18005b07a  mov     ebx, 80070490h
0x18005b07f  jmp     loc_18005B11A
0x18005b084  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x18005b088  xor     ecx, ecx; uFlags
0x18005b08a  call    cs:__imp_LocalAlloc
0x18005b090  mov     rbx, rax
0x18005b093  mov     [rsp+58h+var_28], rax
0x18005b098  test    rax, rax
0x18005b09b  jnz     short loc_18005B0A4
0x18005b09d  mov     ebx, 8007000Eh
0x18005b0a2  jmp     short loc_18005B11A
0x18005b0a4  lea     rax, [rsp+58h+TokenInformationLength]
0x18005b0a9  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18005b0ae  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18005b0b3  mov     r8, rbx; TokenInformation
0x18005b0b6  mov     edx, 1Fh; TokenInformationClass
0x18005b0bb  mov     rcx, [rsi+8]; TokenHandle
0x18005b0bf  call    cs:__imp_GetTokenInformation
0x18005b0c5  test    eax, eax
0x18005b0c7  jnz     short loc_18005B0E0
0x18005b0c9  call    cs:__imp_GetLastError
0x18005b0cf  mov     edi, eax
0x18005b0d1  test    eax, eax
0x18005b0d3  jle     short loc_18005B0ED
0x18005b0d5  movzx   edi, ax
0x18005b0d8  or      edi, 80070000h
0x18005b0de  jmp     short loc_18005B0ED
0x18005b0e0  mov     rdx, [rbx]; struct _SID *
0x18005b0e3  mov     rcx, rdi; this
0x18005b0e6  call    ?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z; ATL::CSid::LoadAccount(_SID const *,ushort const *)
0x18005b0eb  xor     edi, edi
0x18005b0ed  mov     rcx, rbx; hMem
0x18005b0f0  call    cs:__imp_LocalFree
0x18005b0f6  mov     eax, edi
0x18005b0f8  jmp     short loc_18005B124
0x18005b0fa  test    eax, eax
0x18005b0fc  jz      short loc_18005B115
0x18005b0fe  call    cs:__imp_GetLastError
0x18005b104  mov     ebx, eax
0x18005b106  test    eax, eax
0x18005b108  jle     short loc_18005B11A
0x18005b10a  movzx   ebx, ax
0x18005b10d  or      ebx, 80070000h
0x18005b113  jmp     short loc_18005B11A
0x18005b115  mov     ebx, 8000FFFFh
0x18005b11a  xor     ecx, ecx; hMem
0x18005b11c  call    cs:__imp_LocalFree
0x18005b122  mov     eax, ebx
0x18005b124  mov     rcx, [rsp+58h+var_18]
0x18005b129  xor     rcx, rsp; StackCookie
0x18005b12c  call    __security_check_cookie
0x18005b131  mov     rbx, [rsp+58h+arg_10]
0x18005b136  mov     rsi, [rsp+58h+arg_18]
0x18005b13b  add     rsp, 50h
0x18005b13f  pop     rdi
0x18005b140  retn
```
