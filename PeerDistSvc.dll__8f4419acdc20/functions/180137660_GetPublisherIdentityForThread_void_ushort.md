# GetPublisherIdentityForThread(void *,ushort * *)

- ea: `0x180137660`
- end: `0x180137711`
- name: `?GetPublisherIdentityForThread@@YAKPEAXPEAPEAG@Z`
- size: `177`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180137470`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x18013753c`
- `0x180137660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013769b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801376e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013769b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801376e9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180137691`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801376df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180137691`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801376df`

## pseudocode

```c
__int64 __fastcall GetPublisherIdentityForThread(HANDLE TokenHandle, unsigned __int16 **a2)
{
  PSID *v3; // rdi
  DWORD LastError; // ebx
  DWORD PublisherIdentityForSid; // eax
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  v3 = 0;
  LastError = 160;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v3 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
      if ( v3 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
          PublisherIdentityForSid = GetPublisherIdentityForSid(*v3, a2);
        else
          PublisherIdentityForSid = GetLastError();
        LastError = PublisherIdentityForSid;
      }
      else
      {
        LastError = 8;
      }
    }
  }
  operator delete(v3);
  return LastError;
}

```

## disassembly

```asm
0x180137660  push    rbx
0x180137662  push    rbp
0x180137663  push    rsi
0x180137664  push    rdi
0x180137665  sub     rsp, 38h
0x180137669  mov     rsi, rdx
0x18013766c  mov     [rsp+58h+TokenInformationLength], 0
0x180137674  lea     rax, [rsp+58h+TokenInformationLength]
0x180137679  xor     edi, edi
0x18013767b  xor     r9d, r9d; TokenInformationLength
0x18013767e  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180137683  xor     r8d, r8d; TokenInformation
0x180137686  mov     rbp, rcx
0x180137689  mov     ebx, 0A0h
0x18013768e  lea     edx, [rdi+1]; TokenInformationClass
0x180137691  call    cs:__imp_GetTokenInformation
0x180137697  test    eax, eax
0x180137699  jnz     short loc_1801376FE
0x18013769b  call    cs:__imp_GetLastError
0x1801376a1  mov     ebx, eax
0x1801376a3  cmp     eax, 7Ah ; 'z'
0x1801376a6  jnz     short loc_1801376FE
0x1801376a8  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x1801376ac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801376b3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801376b8  mov     rdi, rax
0x1801376bb  test    rax, rax
0x1801376be  jnz     short loc_1801376C5
0x1801376c0  lea     ebx, [rax+8]
0x1801376c3  jmp     short loc_1801376FE
0x1801376c5  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1801376ca  lea     rax, [rsp+58h+TokenInformationLength]
0x1801376cf  mov     r8, rdi; TokenInformation
0x1801376d2  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1801376d7  mov     edx, 1; TokenInformationClass
0x1801376dc  mov     rcx, rbp; TokenHandle
0x1801376df  call    cs:__imp_GetTokenInformation
0x1801376e5  test    eax, eax
0x1801376e7  jnz     short loc_1801376F1
0x1801376e9  call    cs:__imp_GetLastError
0x1801376ef  jmp     short loc_1801376FC
0x1801376f1  mov     rcx, [rdi]; pSid
0x1801376f4  mov     rdx, rsi; unsigned __int16 **
0x1801376f7  call    ?GetPublisherIdentityForSid@@YAKPEAXPEAPEAG@Z; GetPublisherIdentityForSid(void *,ushort * *)
0x1801376fc  mov     ebx, eax
0x1801376fe  mov     rcx, rdi; Block
0x180137701  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180137706  mov     eax, ebx
0x180137708  add     rsp, 38h
0x18013770c  pop     rdi
0x18013770d  pop     rsi
0x18013770e  pop     rbp
0x18013770f  pop     rbx
0x180137710  retn
```
