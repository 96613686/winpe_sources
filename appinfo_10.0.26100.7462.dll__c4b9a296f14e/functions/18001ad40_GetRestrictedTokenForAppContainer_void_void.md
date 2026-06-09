# GetRestrictedTokenForAppContainer(void *,void * *)

- ea: `0x18001ad40`
- end: `0x18001af4b`
- name: `?GetRestrictedTokenForAppContainer@@YAJPEAXPEAPEAX@Z`
- size: `523`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800291e0`

## callees

- `0x18001ad40`
- `0x18001b494`
- `0x18001bc9c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x18001aec8`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x18001aec8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ad74`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ade7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ad74`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ade7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aef8`

## pseudocode

```c
signed int __fastcall GetRestrictedTokenForAppContainer(HANDLE ExistingTokenHandle, PHANDLE NewTokenHandle)
{
  unsigned int *v3; // rbx
  signed int result; // eax
  unsigned int v6; // edi
  unsigned __int64 v7; // rax
  struct _LUID_AND_ATTRIBUTES *v8; // rax
  DWORD v9; // r9d
  unsigned int v10; // edx
  struct _LUID_AND_ATTRIBUTES *PrivilegesToDelete; // rdi
  struct _LUID_AND_ATTRIBUTES *v12; // r8
  _DWORD *v13; // rcx
  DWORD v14; // eax
  unsigned int LastError; // esi
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  v3 = 0;
  if ( GetTokenInformation(ExistingTokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength) )
    goto LABEL_12;
  result = GetLastError();
  if ( result != 122 )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0xC0070000;
    return result;
  }
  v3 = (unsigned int *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v3 )
    return -1073741801;
  if ( GetTokenInformation(ExistingTokenHandle, TokenPrivileges, v3, TokenInformationLength, &TokenInformationLength) )
  {
LABEL_12:
    v7 = 12LL * *v3;
    if ( !is_mul_ok(*v3, 0xCu) )
      v7 = -1;
    v8 = (struct _LUID_AND_ATTRIBUTES *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
    v9 = 0;
    v10 = 0;
    PrivilegesToDelete = v8;
    if ( *v3 )
    {
      v12 = v8;
      v13 = v3 + 1;
      do
      {
        if ( *v13 != 23 && *v13 != 33 || v13[1] )
        {
          ++v9;
          v14 = v13[2];
          v12->Luid = *(LUID *)v13;
          v12->Attributes = v14;
          ++v12;
        }
        ++v10;
        v13 += 3;
      }
      while ( v10 < *v3 );
    }
    if ( CreateRestrictedToken(ExistingTokenHandle, 0, 0, 0, v9, PrivilegesToDelete, 0, 0, NewTokenHandle) )
    {
      if ( PrivilegesToDelete )
        operator delete(PrivilegesToDelete);
      LastError = 0;
    }
    else
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      else
        LastError = GetLastError();
      if ( PrivilegesToDelete )
        operator delete(PrivilegesToDelete);
    }
    operator delete(v3);
    return LastError;
  }
  else
  {
    if ( (int)GetLastError() > 0 )
      v6 = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      v6 = GetLastError();
    operator delete(v3);
    return v6;
  }
}

```

## disassembly

```asm
0x18001ad40  mov     rax, rsp
0x18001ad43  mov     [rax+8], rbx
0x18001ad47  mov     [rax+10h], rbp
0x18001ad4b  mov     [rax+20h], rsi
0x18001ad4f  push    rdi
0x18001ad50  sub     rsp, 50h
0x18001ad54  and     dword ptr [rax+18h], 0
0x18001ad58  lea     rax, [rax+18h]
0x18001ad5c  mov     rbp, rdx
0x18001ad5f  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18001ad64  xor     ebx, ebx
0x18001ad66  xor     r9d, r9d; TokenInformationLength
0x18001ad69  xor     r8d, r8d; TokenInformation
0x18001ad6c  mov     rsi, rcx
0x18001ad6f  lea     edi, [rbx+3]
0x18001ad72  mov     edx, edi; TokenInformationClass
0x18001ad74  call    cs:__imp_GetTokenInformation
0x18001ad7b  nop     dword ptr [rax+rax+00h]
0x18001ad80  test    eax, eax
0x18001ad82  jnz     loc_18001AE3B
0x18001ad88  call    cs:__imp_GetLastError
0x18001ad8f  nop     dword ptr [rax+rax+00h]
0x18001ad94  cmp     eax, 7Ah ; 'z'
0x18001ad97  jz      short loc_18001ADAE
0x18001ad99  test    eax, eax
0x18001ad9b  jle     loc_18001AF35
0x18001ada1  movzx   eax, ax
0x18001ada4  or      eax, 0C0070000h
0x18001ada9  jmp     loc_18001AF35
0x18001adae  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x18001adb2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001adb9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001adbe  mov     rbx, rax
0x18001adc1  test    rax, rax
0x18001adc4  jnz     short loc_18001ADD0
0x18001adc6  mov     eax, 0C0000017h
0x18001adcb  jmp     loc_18001AF35
0x18001add0  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18001add5  lea     rax, [rsp+58h+TokenInformationLength]
0x18001adda  mov     r8, rbx; TokenInformation
0x18001addd  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18001ade2  mov     edx, edi; TokenInformationClass
0x18001ade4  mov     rcx, rsi; TokenHandle
0x18001ade7  call    cs:__imp_GetTokenInformation
0x18001adee  nop     dword ptr [rax+rax+00h]
0x18001adf3  test    eax, eax
0x18001adf5  jnz     short loc_18001AE3B
0x18001adf7  call    cs:__imp_GetLastError
0x18001adfe  nop     dword ptr [rax+rax+00h]
0x18001ae03  test    eax, eax
0x18001ae05  jg      short loc_18001AE17
0x18001ae07  call    cs:__imp_GetLastError
0x18001ae0e  nop     dword ptr [rax+rax+00h]
0x18001ae13  mov     edi, eax
0x18001ae15  jmp     short loc_18001AE2C
0x18001ae17  call    cs:__imp_GetLastError
0x18001ae1e  nop     dword ptr [rax+rax+00h]
0x18001ae23  movzx   edi, ax
0x18001ae26  or      edi, 0C0070000h
0x18001ae2c  mov     rcx, rbx; Block
0x18001ae2f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ae34  mov     eax, edi
0x18001ae36  jmp     loc_18001AF35
0x18001ae3b  mov     ecx, [rbx]
0x18001ae3d  mov     eax, 0Ch
0x18001ae42  mul     rcx
0x18001ae45  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001ae4c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ae53  cmovo   rax, rcx
0x18001ae57  mov     rcx, rax; unsigned __int64
0x18001ae5a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001ae5f  xor     r9d, r9d
0x18001ae62  xor     edx, edx
0x18001ae64  mov     rdi, rax
0x18001ae67  cmp     [rbx], edx
0x18001ae69  jbe     short loc_18001AEA3
0x18001ae6b  mov     r8, rax
0x18001ae6e  lea     rcx, [rbx+4]
0x18001ae72  cmp     dword ptr [rcx], 17h
0x18001ae75  jz      short loc_18001AE7C
0x18001ae77  cmp     dword ptr [rcx], 21h ; '!'
0x18001ae7a  jnz     short loc_18001AE82
0x18001ae7c  cmp     dword ptr [rcx+4], 0
0x18001ae80  jz      short loc_18001AE99
0x18001ae82  movsd   xmm0, qword ptr [rcx]
0x18001ae86  inc     r9d
0x18001ae89  mov     eax, [rcx+8]
0x18001ae8c  movsd   qword ptr [r8], xmm0
0x18001ae91  mov     [r8+8], eax
0x18001ae95  add     r8, 0Ch
0x18001ae99  inc     edx
0x18001ae9b  add     rcx, 0Ch
0x18001ae9f  cmp     edx, [rbx]
0x18001aea1  jb      short loc_18001AE72
0x18001aea3  mov     [rsp+58h+NewTokenHandle], rbp; NewTokenHandle
0x18001aea8  xor     r8d, r8d; DisableSidCount
0x18001aeab  and     [rsp+58h+var_20], 0
0x18001aeb1  xor     edx, edx; Flags
0x18001aeb3  and     [rsp+58h+var_28], 0
0x18001aeb8  mov     rcx, rsi; ExistingTokenHandle
0x18001aebb  mov     [rsp+58h+PrivilegesToDelete], rdi; PrivilegesToDelete
0x18001aec0  mov     dword ptr [rsp+58h+ReturnLength], r9d; DeletePrivilegeCount
0x18001aec5  xor     r9d, r9d; SidsToDisable
0x18001aec8  call    cs:__imp_CreateRestrictedToken
0x18001aecf  nop     dword ptr [rax+rax+00h]
0x18001aed4  test    eax, eax
0x18001aed6  jnz     short loc_18001AF1C
0x18001aed8  call    cs:__imp_GetLastError
0x18001aedf  nop     dword ptr [rax+rax+00h]
0x18001aee4  test    eax, eax
0x18001aee6  jg      short loc_18001AEF8
0x18001aee8  call    cs:__imp_GetLastError
0x18001aeef  nop     dword ptr [rax+rax+00h]
0x18001aef4  mov     esi, eax
0x18001aef6  jmp     short loc_18001AF0D
0x18001aef8  call    cs:__imp_GetLastError
0x18001aeff  nop     dword ptr [rax+rax+00h]
0x18001af04  movzx   esi, ax
0x18001af07  or      esi, 0C0070000h
0x18001af0d  test    rdi, rdi
0x18001af10  jz      short loc_18001AF2B
0x18001af12  mov     rcx, rdi; Block
0x18001af15  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001af1a  jmp     short loc_18001AF2B
0x18001af1c  test    rdi, rdi
0x18001af1f  jz      short loc_18001AF29
0x18001af21  mov     rcx, rdi; Block
0x18001af24  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001af29  xor     esi, esi
0x18001af2b  mov     rcx, rbx; Block
0x18001af2e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001af33  mov     eax, esi
0x18001af35  mov     rbx, [rsp+58h+arg_0]
0x18001af3a  mov     rbp, [rsp+58h+arg_8]
0x18001af3f  mov     rsi, [rsp+58h+arg_18]
0x18001af44  add     rsp, 50h
0x18001af48  pop     rdi
0x18001af49  retn
```
