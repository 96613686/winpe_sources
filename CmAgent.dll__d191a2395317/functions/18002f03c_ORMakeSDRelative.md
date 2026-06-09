# ORMakeSDRelative

- ea: `0x18002f03c`
- end: `0x18002f11c`
- name: `ORMakeSDRelative`
- size: `224`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c768`
- `0x180030e5c`

## callees

- `0x180002b28`
- `0x180002b34`
- `0x18002f03c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f0eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f0eb`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18002f091`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18002f0db`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18002f091`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18002f0db`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18002f06b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18002f06b`

## pseudocode

```c
__int64 __fastcall ORMakeSDRelative(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor, _QWORD *a2)
{
  DWORD LastError; // edi
  void *v5; // rax
  PSECURITY_DESCRIPTOR v6; // rbx
  WORD pControl; // [rsp+48h] [rbp+10h] BYREF
  DWORD dwBufferLength; // [rsp+50h] [rbp+18h] BYREF
  DWORD dwRevision; // [rsp+58h] [rbp+20h] BYREF

  dwBufferLength = 0;
  dwRevision = 0;
  pControl = 0;
  GetSecurityDescriptorControl(pAbsoluteSecurityDescriptor, &pControl, &dwRevision);
  if ( (pControl & 0x8000u) != 0 )
  {
    v6 = pAbsoluteSecurityDescriptor;
    goto LABEL_11;
  }
  MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, 0, &dwBufferLength);
  if ( GetLastError() != 122 )
  {
    LastError = 1359;
LABEL_9:
    v6 = 0;
    goto LABEL_12;
  }
  v5 = o__aligned_malloc_0(dwBufferLength, 0x10u);
  v6 = v5;
  if ( !v5 )
  {
    LastError = 8;
    goto LABEL_9;
  }
  if ( MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, v5, &dwBufferLength) )
  {
LABEL_11:
    LastError = 0;
    goto LABEL_12;
  }
  LastError = GetLastError();
  if ( LastError )
  {
    aligned_free(v6);
    goto LABEL_9;
  }
LABEL_12:
  *a2 = v6;
  return LastError;
}

```

## disassembly

```asm
0x18002f03c  push    rbx
0x18002f03e  push    rsi
0x18002f03f  push    rdi
0x18002f040  sub     rsp, 20h
0x18002f044  mov     rsi, rdx
0x18002f047  mov     [rsp+38h+dwBufferLength], 0
0x18002f04f  xor     eax, eax
0x18002f051  mov     [rsp+38h+dwRevision], 0
0x18002f059  lea     rdx, [rsp+38h+pControl]; pControl
0x18002f05e  mov     [rsp+38h+pControl], ax
0x18002f063  lea     r8, [rsp+38h+dwRevision]; lpdwRevision
0x18002f068  mov     rdi, rcx
0x18002f06b  call    cs:__imp_GetSecurityDescriptorControl
0x18002f072  nop     dword ptr [rax+rax+00h]
0x18002f077  mov     eax, 8000h
0x18002f07c  test    [rsp+38h+pControl], ax
0x18002f081  jnz     loc_18002F109
0x18002f087  lea     r8, [rsp+38h+dwBufferLength]; lpdwBufferLength
0x18002f08c  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x18002f08e  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x18002f091  call    cs:__imp_MakeSelfRelativeSD
0x18002f098  nop     dword ptr [rax+rax+00h]
0x18002f09d  call    cs:__imp_GetLastError
0x18002f0a4  nop     dword ptr [rax+rax+00h]
0x18002f0a9  cmp     eax, 7Ah ; 'z'
0x18002f0ac  jz      short loc_18002F0B5
0x18002f0ae  mov     edi, 54Fh
0x18002f0b3  jmp     short loc_18002F105
0x18002f0b5  mov     ecx, [rsp+38h+dwBufferLength]; Size
0x18002f0b9  mov     edx, 10h; Alignment
0x18002f0be  call    _o__aligned_malloc_0
0x18002f0c3  mov     rbx, rax
0x18002f0c6  test    rax, rax
0x18002f0c9  jnz     short loc_18002F0D0
0x18002f0cb  lea     edi, [rax+8]
0x18002f0ce  jmp     short loc_18002F105
0x18002f0d0  lea     r8, [rsp+38h+dwBufferLength]; lpdwBufferLength
0x18002f0d5  mov     rdx, rbx; pSelfRelativeSecurityDescriptor
0x18002f0d8  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x18002f0db  call    cs:__imp_MakeSelfRelativeSD
0x18002f0e2  nop     dword ptr [rax+rax+00h]
0x18002f0e7  test    eax, eax
0x18002f0e9  jnz     short loc_18002F10C
0x18002f0eb  call    cs:__imp_GetLastError
0x18002f0f2  nop     dword ptr [rax+rax+00h]
0x18002f0f7  mov     edi, eax
0x18002f0f9  test    eax, eax
0x18002f0fb  jz      short loc_18002F10E
0x18002f0fd  mov     rcx, rbx; Block
0x18002f100  call    _aligned_free
0x18002f105  xor     ebx, ebx
0x18002f107  jmp     short loc_18002F10E
0x18002f109  mov     rbx, rdi
0x18002f10c  xor     edi, edi
0x18002f10e  mov     [rsi], rbx
0x18002f111  mov     eax, edi
0x18002f113  add     rsp, 20h
0x18002f117  pop     rdi
0x18002f118  pop     rsi
0x18002f119  pop     rbx
0x18002f11a  retn
```
