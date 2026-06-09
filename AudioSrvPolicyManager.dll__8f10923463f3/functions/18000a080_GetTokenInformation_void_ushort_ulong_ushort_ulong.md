# GetTokenInformation(void *,ushort * *,ulong *,ushort * *,ulong *)

- ea: `0x18000a080`
- end: `0x18000a37e`
- name: `?GetTokenInformation@@YAKPEAXPEAPEAGPEAK12@Z`
- size: `766`
- prototype: `unsigned int __usercall@<eax>(HANDLE TokenHandle@<rcx>, unsigned __int16 **@<rdx>, unsigned int *@<r8>, unsigned __int16 **@<r9>, unsigned int *)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003c70`
- `0x180009a30`
- `0x180009e60`
- `0x18001dcd0`
- `0x18001edd0`
- `0x180044800`

## callees

- `0x18000a080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a19f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a19f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a359`
- `ntdll!RtlGetAppContainerParent` at `0x18000a2cb`
- `ntdll!RtlGetAppContainerParent` at `0x18000a2cb`
- `ntdll!RtlFreeSid` at `0x18000a2ed`
- `ntdll!RtlFreeSid` at `0x18000a2ed`
- `ntdll!RtlGetAppContainerSidType` at `0x18000a2a8`
- `ntdll!RtlGetAppContainerSidType` at `0x18000a2a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a1b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a25b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a1b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a25b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a13e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a148`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a151`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a15a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a13e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a148`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a151`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a15a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a101`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a18e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a1de`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a234`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a285`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a323`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a101`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a18e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a1de`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a234`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a285`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a323`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a1ef`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a2e1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a34b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a1ef`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a2e1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a34b`

## pseudocode

```c
__int64 __fastcall GetTokenInformation(
        HANDLE TokenHandle,
        HLOCAL *a2,
        unsigned int *a3,
        HLOCAL *a4,
        unsigned int *TokenInformation)
{
  DWORD LastError; // edi
  PSID *v10; // r14
  void **v11; // r15
  void *v13; // rcx
  void *v14; // rcx
  BOOL v15; // edi
  HLOCAL v16; // [rsp+30h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-18h] BYREF
  PSID Sid[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+98h] [rbp+48h] BYREF
  int v20; // [rsp+A8h] [rbp+58h] BYREF

  LastError = 0;
  TokenInformationLength = 0;
  hMem = 0;
  v16 = 0;
  v10 = 0;
  v11 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a2 )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
      goto LABEL_17;
    LastError = GetLastError();
    if ( LastError != 122 )
      goto LABEL_15;
    v10 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( !v10 )
      goto LABEL_35;
    if ( !GetTokenInformation(TokenHandle, TokenUser, v10, TokenInformationLength, &TokenInformationLength)
      || !ConvertSidToStringSidW(*v10, (LPWSTR *)&hMem) )
    {
      goto LABEL_38;
    }
    LastError = 0;
  }
  if ( a3 )
  {
    TokenInformationLength = 4;
    if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, a3, 4u, &TokenInformationLength) )
      goto LABEL_38;
  }
  if ( TokenInformation )
  {
    TokenInformationLength = 4;
    if ( !GetTokenInformation(TokenHandle, TokenSessionId, TokenInformation, 4u, &TokenInformationLength) )
      goto LABEL_38;
  }
  if ( a4 )
  {
    TokenInformationLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
    {
      LastError = GetLastError();
      if ( LastError != 122 )
        goto LABEL_15;
      v11 = (void **)LocalAlloc(0x40u, TokenInformationLength);
      if ( v11 )
      {
        if ( GetTokenInformation(
               TokenHandle,
               TokenAppContainerSid,
               v11,
               TokenInformationLength,
               &TokenInformationLength) )
        {
          v13 = *v11;
          LastError = 0;
          if ( !*v11 )
            goto LABEL_10;
          v20 = 0;
          if ( (int)RtlGetAppContainerSidType(v13, &v20) >= 0 )
          {
            v14 = *v11;
            if ( v20 == 1 )
            {
              Sid[0] = 0;
              if ( (int)RtlGetAppContainerParent(v14, Sid) >= 0 )
              {
                v15 = ConvertSidToStringSidW(Sid[0], (LPWSTR *)&v16);
                RtlFreeSid(Sid[0]);
                if ( v15 )
                {
                  LastError = 0;
                  goto LABEL_10;
                }
              }
            }
            else if ( ConvertSidToStringSidW(v14, (LPWSTR *)&v16) )
            {
              goto LABEL_10;
            }
          }
        }
LABEL_38:
        LastError = GetLastError();
        goto LABEL_15;
      }
LABEL_35:
      LastError = 14;
      goto LABEL_15;
    }
LABEL_17:
    LastError = 1337;
    goto LABEL_15;
  }
LABEL_10:
  if ( a2 )
    *a2 = hMem;
  if ( a4 )
    *a4 = v16;
  hMem = 0;
  v16 = 0;
LABEL_15:
  LocalFree(hMem);
  LocalFree(v16);
  LocalFree(v10);
  LocalFree(v11);
  return LastError;
}

```

## disassembly

```asm
0x18000a080  mov     [rsp-38h+arg_0], rbx
0x18000a085  push    rbp
0x18000a086  push    rsi
0x18000a087  push    rdi
0x18000a088  push    r12
0x18000a08a  push    r13
0x18000a08c  push    r14
0x18000a08e  push    r15
0x18000a090  mov     rbp, rsp
0x18000a093  sub     rsp, 50h
0x18000a097  xor     edi, edi
0x18000a099  mov     rsi, r9
0x18000a09c  mov     [rbp+TokenInformationLength], edi
0x18000a09f  mov     r12, r8
0x18000a0a2  mov     [rbp+hMem], rdi
0x18000a0a6  mov     rbx, rdx
0x18000a0a9  mov     [rbp+var_20], rdi
0x18000a0ad  mov     r13, rcx
0x18000a0b0  mov     r14d, edi
0x18000a0b3  mov     r15d, edi
0x18000a0b6  test    rdx, rdx
0x18000a0b9  jnz     loc_18000A212
0x18000a0bf  test    rsi, rsi
0x18000a0c2  jnz     loc_18000A20A
0x18000a0c8  test    rbx, rbx
0x18000a0cb  jnz     loc_18000A17A
0x18000a0d1  test    r12, r12
0x18000a0d4  jnz     loc_18000A302
0x18000a0da  mov     r8, [rbp+TokenInformation]; TokenInformation
0x18000a0de  test    r8, r8
0x18000a0e1  jz      short loc_18000A10F
0x18000a0e3  lea     rax, [rbp+TokenInformationLength]
0x18000a0e7  mov     [rbp+TokenInformationLength], 4
0x18000a0ee  mov     edx, 0Ch; TokenInformationClass
0x18000a0f3  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18000a0f8  mov     r9d, 4; TokenInformationLength
0x18000a0fe  mov     rcx, r13; TokenHandle
0x18000a101  call    cs:__imp_GetTokenInformation
0x18000a107  test    eax, eax
0x18000a109  jz      loc_18000A1FD
0x18000a10f  test    rsi, rsi
0x18000a112  jnz     loc_18000A21A
0x18000a118  test    rbx, rbx
0x18000a11b  jnz     loc_18000A366
0x18000a121  test    rsi, rsi
0x18000a124  jnz     loc_18000A372
0x18000a12a  mov     [rbp+hMem], 0
0x18000a132  mov     [rbp+var_20], 0
0x18000a13a  mov     rcx, [rbp+hMem]; hMem
0x18000a13e  call    cs:__imp_LocalFree
0x18000a144  mov     rcx, [rbp+var_20]; hMem
0x18000a148  call    cs:__imp_LocalFree
0x18000a14e  mov     rcx, r14; hMem
0x18000a151  call    cs:__imp_LocalFree
0x18000a157  mov     rcx, r15; hMem
0x18000a15a  call    cs:__imp_LocalFree
0x18000a160  mov     rbx, [rsp+50h+arg_0]
0x18000a168  mov     eax, edi
0x18000a16a  add     rsp, 50h
0x18000a16e  pop     r15
0x18000a170  pop     r14
0x18000a172  pop     r13
0x18000a174  pop     r12
0x18000a176  pop     rdi
0x18000a177  pop     rsi
0x18000a178  pop     rbp
0x18000a179  retn
0x18000a17a  lea     rax, [rbp+TokenInformationLength]
0x18000a17e  xor     r9d, r9d; TokenInformationLength
0x18000a181  xor     r8d, r8d; TokenInformation
0x18000a184  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18000a189  mov     edx, 1; TokenInformationClass
0x18000a18e  call    cs:__imp_GetTokenInformation
0x18000a194  test    eax, eax
0x18000a196  jz      short loc_18000A19F
0x18000a198  mov     edi, 539h
0x18000a19d  jmp     short loc_18000A13A
0x18000a19f  call    cs:__imp_GetLastError
0x18000a1a5  mov     edi, eax
0x18000a1a7  cmp     eax, 7Ah ; 'z'
0x18000a1aa  jnz     short loc_18000A13A
0x18000a1ac  mov     edx, [rbp+TokenInformationLength]; uBytes
0x18000a1af  mov     ecx, 40h ; '@'; uFlags
0x18000a1b4  call    cs:__imp_LocalAlloc
0x18000a1ba  mov     r14, rax
0x18000a1bd  test    rax, rax
0x18000a1c0  jz      loc_18000A336
0x18000a1c6  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18000a1ca  lea     rax, [rbp+TokenInformationLength]
0x18000a1ce  mov     r8, r14; TokenInformation
0x18000a1d1  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18000a1d6  mov     edx, 1; TokenInformationClass
0x18000a1db  mov     rcx, r13; TokenHandle
0x18000a1de  call    cs:__imp_GetTokenInformation
0x18000a1e4  test    eax, eax
0x18000a1e6  jz      short loc_18000A1FD
0x18000a1e8  mov     rcx, [r14]; Sid
0x18000a1eb  lea     rdx, [rbp+hMem]; StringSid
0x18000a1ef  call    cs:__imp_ConvertSidToStringSidW
0x18000a1f5  test    eax, eax
0x18000a1f7  jnz     loc_18000A340
0x18000a1fd  call    cs:__imp_GetLastError
0x18000a203  mov     edi, eax
0x18000a205  jmp     loc_18000A13A
0x18000a20a  mov     [r9], rdi
0x18000a20d  jmp     loc_18000A0C8
0x18000a212  mov     [rdx], rdi
0x18000a215  jmp     loc_18000A0BF
0x18000a21a  lea     rax, [rbp+TokenInformationLength]
0x18000a21e  mov     [rbp+TokenInformationLength], edi
0x18000a221  xor     r9d, r9d; TokenInformationLength
0x18000a224  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18000a229  xor     r8d, r8d; TokenInformation
0x18000a22c  mov     edx, 1Fh; TokenInformationClass
0x18000a231  mov     rcx, r13; TokenHandle
0x18000a234  call    cs:__imp_GetTokenInformation
0x18000a23a  test    eax, eax
0x18000a23c  jnz     loc_18000A198
0x18000a242  call    cs:__imp_GetLastError
0x18000a248  mov     edi, eax
0x18000a24a  cmp     eax, 7Ah ; 'z'
0x18000a24d  jnz     loc_18000A13A
0x18000a253  mov     edx, [rbp+TokenInformationLength]; uBytes
0x18000a256  mov     ecx, 40h ; '@'; uFlags
0x18000a25b  call    cs:__imp_LocalAlloc
0x18000a261  mov     r15, rax
0x18000a264  test    rax, rax
0x18000a267  jz      loc_18000A336
0x18000a26d  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18000a271  lea     rax, [rbp+TokenInformationLength]
0x18000a275  mov     r8, r15; TokenInformation
0x18000a278  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18000a27d  mov     edx, 1Fh; TokenInformationClass
0x18000a282  mov     rcx, r13; TokenHandle
0x18000a285  call    cs:__imp_GetTokenInformation
0x18000a28b  test    eax, eax
0x18000a28d  jz      loc_18000A1FD
0x18000a293  mov     rcx, [r15]
0x18000a296  xor     edi, edi
0x18000a298  test    rcx, rcx
0x18000a29b  jz      loc_18000A118
0x18000a2a1  lea     rdx, [rbp+arg_18]
0x18000a2a5  mov     [rbp+arg_18], edi
0x18000a2a8  call    cs:__imp_RtlGetAppContainerSidType
0x18000a2ae  test    eax, eax
0x18000a2b0  js      loc_18000A1FD
0x18000a2b6  cmp     [rbp+arg_18], 1
0x18000a2ba  mov     rcx, [r15]; Sid
0x18000a2bd  jnz     loc_18000A347
0x18000a2c3  lea     rdx, [rbp+Sid]
0x18000a2c7  mov     [rbp+Sid], rdi
0x18000a2cb  call    cs:__imp_RtlGetAppContainerParent
0x18000a2d1  test    eax, eax
0x18000a2d3  js      loc_18000A1FD
0x18000a2d9  mov     rcx, [rbp+Sid]; Sid
0x18000a2dd  lea     rdx, [rbp+var_20]; StringSid
0x18000a2e1  call    cs:__imp_ConvertSidToStringSidW
0x18000a2e7  mov     rcx, [rbp+Sid]; Sid
0x18000a2eb  mov     edi, eax
0x18000a2ed  call    cs:__imp_RtlFreeSid
0x18000a2f3  test    edi, edi
0x18000a2f5  jz      loc_18000A1FD
0x18000a2fb  xor     edi, edi
0x18000a2fd  jmp     loc_18000A118
0x18000a302  lea     rax, [rbp+TokenInformationLength]
0x18000a306  mov     [rbp+TokenInformationLength], 4
0x18000a30d  mov     r9d, 4; TokenInformationLength
0x18000a313  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18000a318  mov     r8, r12; TokenInformation
0x18000a31b  mov     edx, 1Dh; TokenInformationClass
0x18000a320  mov     rcx, r13; TokenHandle
0x18000a323  call    cs:__imp_GetTokenInformation
0x18000a329  test    eax, eax
0x18000a32b  jnz     loc_18000A0DA
0x18000a331  jmp     loc_18000A1FD
0x18000a336  mov     edi, 0Eh
0x18000a33b  jmp     loc_18000A13A
0x18000a340  xor     edi, edi
0x18000a342  jmp     loc_18000A0D1
0x18000a347  lea     rdx, [rbp+var_20]; StringSid
0x18000a34b  call    cs:__imp_ConvertSidToStringSidW
0x18000a351  test    eax, eax
0x18000a353  jnz     loc_18000A118
0x18000a359  call    cs:__imp_GetLastError
0x18000a35f  mov     edi, eax
0x18000a361  jmp     loc_18000A13A
0x18000a366  mov     rax, [rbp+hMem]
0x18000a36a  mov     [rbx], rax
0x18000a36d  jmp     loc_18000A121
0x18000a372  mov     rax, [rbp+var_20]
0x18000a376  mov     [rsi], rax
0x18000a379  jmp     loc_18000A12A
```
