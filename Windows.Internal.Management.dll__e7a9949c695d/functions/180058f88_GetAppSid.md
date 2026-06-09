# GetAppSid

- ea: `0x180058f88`
- end: `0x18005907e`
- name: `GetAppSid`
- size: `246`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004abc0`

## callees

- `0x180058f88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058fd7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180058fc0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180059023`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180058fc0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180059023`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058ff4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058ff4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059058`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059066`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059058`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059066`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180059035`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180059035`

## pseudocode

```c
__int64 __fastcall GetAppSid(HANDLE TokenHandle, LPWSTR *a2)
{
  PSID *v4; // rdi
  signed int LastError; // eax
  unsigned int v6; // ebx
  SIZE_T uBytes; // [rsp+50h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp+20h] BYREF

  StringSid = 0;
  LODWORD(uBytes) = 0;
  if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, (PDWORD)&uBytes) || GetLastError() == 122 )
  {
    v4 = (PSID *)LocalAlloc(0, (unsigned int)uBytes);
    if ( !v4 )
    {
      v6 = -2146893810;
      goto LABEL_11;
    }
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, v4, uBytes, (PDWORD)&uBytes)
      && ConvertSidToStringSidW(*v4, &StringSid) )
    {
      v6 = 0;
      *a2 = StringSid;
      StringSid = 0;
      goto LABEL_11;
    }
  }
  else
  {
    v4 = 0;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_11:
  if ( StringSid )
    LocalFree(StringSid);
  if ( v4 )
    LocalFree(v4);
  return v6;
}

```

## disassembly

```asm
0x180058f88  mov     rax, rsp
0x180058f8b  mov     [rax+8], rbx
0x180058f8f  mov     [rax+10h], rsi
0x180058f93  push    rdi
0x180058f94  sub     rsp, 30h
0x180058f98  xor     r9d, r9d; TokenInformationLength
0x180058f9b  mov     qword ptr [rax+20h], 0
0x180058fa3  mov     dword ptr [rax+18h], 0
0x180058faa  lea     rax, [rax+18h]
0x180058fae  mov     rsi, rdx
0x180058fb1  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180058fb6  xor     r8d, r8d; TokenInformation
0x180058fb9  mov     rbx, rcx
0x180058fbc  lea     edx, [r9+1Fh]; TokenInformationClass
0x180058fc0  call    cs:__imp_GetTokenInformation
0x180058fc6  test    eax, eax
0x180058fc8  jnz     short loc_180058FEE
0x180058fca  call    cs:__imp_GetLastError
0x180058fd0  cmp     eax, 7Ah ; 'z'
0x180058fd3  jz      short loc_180058FEE
0x180058fd5  xor     edi, edi
0x180058fd7  call    cs:__imp_GetLastError
0x180058fdd  mov     ebx, eax
0x180058fdf  test    eax, eax
0x180058fe1  jle     short loc_18005904E
0x180058fe3  movzx   ebx, ax
0x180058fe6  or      ebx, 80070000h
0x180058fec  jmp     short loc_18005904E
0x180058fee  mov     edx, dword ptr [rsp+38h+uBytes]; uBytes
0x180058ff2  xor     ecx, ecx; uFlags
0x180058ff4  call    cs:__imp_LocalAlloc
0x180058ffa  mov     rdi, rax
0x180058ffd  test    rax, rax
0x180059000  jnz     short loc_180059009
0x180059002  mov     ebx, 8009000Eh
0x180059007  jmp     short loc_18005904E
0x180059009  mov     r9d, dword ptr [rsp+38h+uBytes]; TokenInformationLength
0x18005900e  lea     rax, [rsp+38h+uBytes]
0x180059013  mov     r8, rdi; TokenInformation
0x180059016  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18005901b  mov     edx, 1Fh; TokenInformationClass
0x180059020  mov     rcx, rbx; TokenHandle
0x180059023  call    cs:__imp_GetTokenInformation
0x180059029  test    eax, eax
0x18005902b  jz      short loc_180058FD7
0x18005902d  mov     rcx, [rdi]; Sid
0x180059030  lea     rdx, [rsp+38h+StringSid]; StringSid
0x180059035  call    cs:__imp_ConvertSidToStringSidW
0x18005903b  test    eax, eax
0x18005903d  jz      short loc_180058FD7
0x18005903f  mov     rax, [rsp+38h+StringSid]
0x180059044  xor     ebx, ebx
0x180059046  mov     [rsi], rax
0x180059049  mov     [rsp+38h+StringSid], rbx
0x18005904e  mov     rcx, [rsp+38h+StringSid]; hMem
0x180059053  test    rcx, rcx
0x180059056  jz      short loc_18005905E
0x180059058  call    cs:__imp_LocalFree
0x18005905e  test    rdi, rdi
0x180059061  jz      short loc_18005906C
0x180059063  mov     rcx, rdi; hMem
0x180059066  call    cs:__imp_LocalFree
0x18005906c  mov     rsi, [rsp+38h+arg_8]
0x180059071  mov     eax, ebx
0x180059073  mov     rbx, [rsp+38h+arg_0]
0x180059078  add     rsp, 30h
0x18005907c  pop     rdi
0x18005907d  retn
```
