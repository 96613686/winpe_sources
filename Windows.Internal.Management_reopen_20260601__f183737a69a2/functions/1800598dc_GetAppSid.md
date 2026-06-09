# GetAppSid

- ea: `0x1800598dc`
- end: `0x180059a03`
- name: `GetAppSid`
- size: `295`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004adbc`

## callees

- `0x1800598dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059937`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180059914`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005998f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180059914`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005998f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005995a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005995a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800599d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800599e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800599d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800599e4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800599a7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800599a7`

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
0x1800598dc  mov     rax, rsp
0x1800598df  mov     [rax+8], rbx
0x1800598e3  mov     [rax+10h], rsi
0x1800598e7  push    rdi
0x1800598e8  sub     rsp, 30h
0x1800598ec  xor     r9d, r9d; TokenInformationLength
0x1800598ef  mov     qword ptr [rax+20h], 0
0x1800598f7  mov     dword ptr [rax+18h], 0
0x1800598fe  lea     rax, [rax+18h]
0x180059902  mov     rsi, rdx
0x180059905  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18005990a  xor     r8d, r8d; TokenInformation
0x18005990d  mov     rbx, rcx
0x180059910  lea     edx, [r9+1Fh]; TokenInformationClass
0x180059914  call    cs:__imp_GetTokenInformation
0x18005991b  nop     dword ptr [rax+rax+00h]
0x180059920  test    eax, eax
0x180059922  jnz     short loc_180059954
0x180059924  call    cs:__imp_GetLastError
0x18005992b  nop     dword ptr [rax+rax+00h]
0x180059930  cmp     eax, 7Ah ; 'z'
0x180059933  jz      short loc_180059954
0x180059935  xor     edi, edi
0x180059937  call    cs:__imp_GetLastError
0x18005993e  nop     dword ptr [rax+rax+00h]
0x180059943  mov     ebx, eax
0x180059945  test    eax, eax
0x180059947  jle     short loc_1800599C6
0x180059949  movzx   ebx, ax
0x18005994c  or      ebx, 80070000h
0x180059952  jmp     short loc_1800599C6
0x180059954  mov     edx, dword ptr [rsp+38h+uBytes]; uBytes
0x180059958  xor     ecx, ecx; uFlags
0x18005995a  call    cs:__imp_LocalAlloc
0x180059961  nop     dword ptr [rax+rax+00h]
0x180059966  mov     rdi, rax
0x180059969  test    rax, rax
0x18005996c  jnz     short loc_180059975
0x18005996e  mov     ebx, 8009000Eh
0x180059973  jmp     short loc_1800599C6
0x180059975  mov     r9d, dword ptr [rsp+38h+uBytes]; TokenInformationLength
0x18005997a  lea     rax, [rsp+38h+uBytes]
0x18005997f  mov     r8, rdi; TokenInformation
0x180059982  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180059987  mov     edx, 1Fh; TokenInformationClass
0x18005998c  mov     rcx, rbx; TokenHandle
0x18005998f  call    cs:__imp_GetTokenInformation
0x180059996  nop     dword ptr [rax+rax+00h]
0x18005999b  test    eax, eax
0x18005999d  jz      short loc_180059937
0x18005999f  mov     rcx, [rdi]; Sid
0x1800599a2  lea     rdx, [rsp+38h+StringSid]; StringSid
0x1800599a7  call    cs:__imp_ConvertSidToStringSidW
0x1800599ae  nop     dword ptr [rax+rax+00h]
0x1800599b3  test    eax, eax
0x1800599b5  jz      short loc_180059937
0x1800599b7  mov     rax, [rsp+38h+StringSid]
0x1800599bc  xor     ebx, ebx
0x1800599be  mov     [rsi], rax
0x1800599c1  mov     [rsp+38h+StringSid], rbx
0x1800599c6  mov     rcx, [rsp+38h+StringSid]; hMem
0x1800599cb  test    rcx, rcx
0x1800599ce  jz      short loc_1800599DC
0x1800599d0  call    cs:__imp_LocalFree
0x1800599d7  nop     dword ptr [rax+rax+00h]
0x1800599dc  test    rdi, rdi
0x1800599df  jz      short loc_1800599F0
0x1800599e1  mov     rcx, rdi; hMem
0x1800599e4  call    cs:__imp_LocalFree
0x1800599eb  nop     dword ptr [rax+rax+00h]
0x1800599f0  mov     rsi, [rsp+38h+arg_8]
0x1800599f5  mov     eax, ebx
0x1800599f7  mov     rbx, [rsp+38h+arg_0]
0x1800599fc  add     rsp, 30h
0x180059a00  pop     rdi
0x180059a01  retn
```
