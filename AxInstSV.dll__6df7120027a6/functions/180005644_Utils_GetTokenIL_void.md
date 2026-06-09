# Utils::GetTokenIL(void *)

- ea: `0x180005644`
- end: `0x1800056d7`
- name: `?GetTokenIL@Utils@@SAKPEAX@Z`
- size: `147`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005934`

## callees

- `0x180005644`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000567f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000567f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800056bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800056bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005672`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800056a5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005672`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800056a5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800056b4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800056b4`

## pseudocode

```c
__int64 __fastcall Utils::GetTokenIL(HANDLE TokenHandle)
{
  DWORD v1; // edi
  PSID *v3; // rbx
  SIZE_T uBytes; // [rsp+48h] [rbp+10h] BYREF

  LODWORD(uBytes) = 0;
  v1 = 0;
  GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, (PDWORD)&uBytes);
  v3 = (PSID *)LocalAlloc(0x40u, (unsigned int)uBytes);
  if ( v3 )
  {
    if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v3, uBytes, (PDWORD)&uBytes) )
      v1 = *GetSidSubAuthority(*v3, 0);
    LocalFree(v3);
  }
  return v1;
}

```

## disassembly

```asm
0x180005644  mov     rax, rsp
0x180005647  mov     [rax+8], rbx
0x18000564b  mov     [rax+18h], rsi
0x18000564f  push    rdi
0x180005650  sub     rsp, 30h
0x180005654  mov     dword ptr [rax+10h], 0
0x18000565b  lea     rax, [rax+10h]
0x18000565f  xor     edi, edi
0x180005661  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180005666  xor     r9d, r9d; TokenInformationLength
0x180005669  xor     r8d, r8d; TokenInformation
0x18000566c  mov     rsi, rcx
0x18000566f  lea     edx, [rdi+19h]; TokenInformationClass
0x180005672  call    cs:__imp_GetTokenInformation
0x180005678  mov     edx, dword ptr [rsp+38h+uBytes]; uBytes
0x18000567c  lea     ecx, [rdi+40h]; uFlags
0x18000567f  call    cs:__imp_LocalAlloc
0x180005685  mov     rbx, rax
0x180005688  test    rax, rax
0x18000568b  jz      short loc_1800056C5
0x18000568d  mov     r9d, dword ptr [rsp+38h+uBytes]; TokenInformationLength
0x180005692  lea     rax, [rsp+38h+uBytes]
0x180005697  mov     r8, rbx; TokenInformation
0x18000569a  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18000569f  lea     edx, [rdi+19h]; TokenInformationClass
0x1800056a2  mov     rcx, rsi; TokenHandle
0x1800056a5  call    cs:__imp_GetTokenInformation
0x1800056ab  test    eax, eax
0x1800056ad  jz      short loc_1800056BC
0x1800056af  mov     rcx, [rbx]; pSid
0x1800056b2  xor     edx, edx; nSubAuthority
0x1800056b4  call    cs:__imp_GetSidSubAuthority
0x1800056ba  mov     edi, [rax]
0x1800056bc  mov     rcx, rbx; hMem
0x1800056bf  call    cs:__imp_LocalFree
0x1800056c5  mov     rbx, [rsp+38h+arg_0]
0x1800056ca  mov     eax, edi
0x1800056cc  mov     rsi, [rsp+38h+arg_10]
0x1800056d1  add     rsp, 30h
0x1800056d5  pop     rdi
0x1800056d6  retn
```
