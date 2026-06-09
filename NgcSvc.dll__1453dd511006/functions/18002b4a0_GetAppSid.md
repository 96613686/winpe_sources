# GetAppSid

- ea: `0x18002b4a0`
- end: `0x18002b5c9`
- name: `GetAppSid`
- size: `297`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800aabc0`

## callees

- `0x18002b4a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5ac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b4da`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b516`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b4da`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b516`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b545`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b5c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b545`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b5c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b4ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b4ea`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002b528`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002b528`

## pseudocode

```c
__int64 __fastcall GetAppSid(HANDLE TokenHandle, LPWSTR *a2)
{
  PSID *v4; // rbx
  unsigned int v5; // edi
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+20h] BYREF

  StringSid = 0;
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 122 )
    {
      v4 = 0;
      if ( LastError <= 0 )
        goto LABEL_11;
      goto LABEL_10;
    }
  }
  v4 = (PSID *)LocalAlloc(0, TokenInformationLength);
  if ( v4 )
  {
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, v4, TokenInformationLength, &TokenInformationLength) )
    {
      if ( ConvertSidToStringSidW(*v4, &StringSid) )
      {
        v5 = 0;
        *a2 = StringSid;
        StringSid = 0;
LABEL_6:
        LocalFree(v4);
        return v5;
      }
      GetLastError();
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        goto LABEL_10;
    }
    else
    {
      GetLastError();
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
LABEL_10:
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v5 = -2146893810;
  }
LABEL_11:
  if ( StringSid )
    LocalFree(StringSid);
  if ( v4 )
    goto LABEL_6;
  return v5;
}

```

## disassembly

```asm
0x18002b4a0  mov     [rsp+arg_0], rbx
0x18002b4a5  mov     [rsp+arg_8], rbp
0x18002b4aa  push    rsi
0x18002b4ab  push    rdi
0x18002b4ac  push    r14
0x18002b4ae  sub     rsp, 30h
0x18002b4b2  mov     rsi, rdx
0x18002b4b5  lea     rax, [rsp+48h+TokenInformationLength]
0x18002b4ba  xor     r14d, r14d
0x18002b4bd  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002b4c2  mov     edx, 1Fh; TokenInformationClass
0x18002b4c7  mov     [rsp+48h+StringSid], r14
0x18002b4cc  xor     r9d, r9d; TokenInformationLength
0x18002b4cf  mov     [rsp+48h+TokenInformationLength], r14d
0x18002b4d4  xor     r8d, r8d; TokenInformation
0x18002b4d7  mov     rbp, rcx
0x18002b4da  call    cs:__imp_GetTokenInformation
0x18002b4e0  test    eax, eax
0x18002b4e2  jz      short loc_18002B560
0x18002b4e4  mov     edx, [rsp+48h+TokenInformationLength]; uBytes
0x18002b4e8  xor     ecx, ecx; uFlags
0x18002b4ea  call    cs:__imp_LocalAlloc
0x18002b4f0  mov     rbx, rax
0x18002b4f3  test    rax, rax
0x18002b4f6  jz      loc_18002B5BA
0x18002b4fc  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18002b501  lea     rax, [rsp+48h+TokenInformationLength]
0x18002b506  mov     r8, rbx; TokenInformation
0x18002b509  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002b50e  mov     edx, 1Fh; TokenInformationClass
0x18002b513  mov     rcx, rbp; TokenHandle
0x18002b516  call    cs:__imp_GetTokenInformation
0x18002b51c  test    eax, eax
0x18002b51e  jz      short loc_18002B592
0x18002b520  mov     rcx, [rbx]; Sid
0x18002b523  lea     rdx, [rsp+48h+StringSid]; StringSid
0x18002b528  call    cs:__imp_ConvertSidToStringSidW
0x18002b52e  test    eax, eax
0x18002b530  jz      short loc_18002B5A6
0x18002b532  mov     rax, [rsp+48h+StringSid]
0x18002b537  mov     edi, r14d
0x18002b53a  mov     [rsi], rax
0x18002b53d  mov     [rsp+48h+StringSid], r14
0x18002b542  mov     rcx, rbx; hMem
0x18002b545  call    cs:__imp_LocalFree
0x18002b54b  mov     rbx, [rsp+48h+arg_0]
0x18002b550  mov     eax, edi
0x18002b552  mov     rbp, [rsp+48h+arg_8]
0x18002b557  add     rsp, 30h
0x18002b55b  pop     r14
0x18002b55d  pop     rdi
0x18002b55e  pop     rsi
0x18002b55f  retn
0x18002b560  call    cs:__imp_GetLastError
0x18002b566  mov     edi, eax
0x18002b568  cmp     eax, 7Ah ; 'z'
0x18002b56b  jz      loc_18002B4E4
0x18002b571  mov     rbx, r14
0x18002b574  test    eax, eax
0x18002b576  jle     short loc_18002B581
0x18002b578  movzx   edi, ax
0x18002b57b  or      edi, 80070000h
0x18002b581  mov     rcx, [rsp+48h+StringSid]; hMem
0x18002b586  test    rcx, rcx
0x18002b589  jnz     short loc_18002B5C1
0x18002b58b  test    rbx, rbx
0x18002b58e  jnz     short loc_18002B542
0x18002b590  jmp     short loc_18002B54B
0x18002b592  call    cs:__imp_GetLastError
0x18002b598  call    cs:__imp_GetLastError
0x18002b59e  mov     edi, eax
0x18002b5a0  test    eax, eax
0x18002b5a2  jle     short loc_18002B581
0x18002b5a4  jmp     short loc_18002B578
0x18002b5a6  call    cs:__imp_GetLastError
0x18002b5ac  call    cs:__imp_GetLastError
0x18002b5b2  mov     edi, eax
0x18002b5b4  test    eax, eax
0x18002b5b6  jle     short loc_18002B581
0x18002b5b8  jmp     short loc_18002B578
0x18002b5ba  mov     edi, 8009000Eh
0x18002b5bf  jmp     short loc_18002B581
0x18002b5c1  call    cs:__imp_LocalFree
0x18002b5c7  jmp     short loc_18002B58B
```
