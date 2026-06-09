# AslGetSessionId

- ea: `0x18003cbcc`
- end: `0x18003cc7d`
- name: `AslGetSessionId`
- size: `177`
- prototype: `__int64 __fastcall(PVOID TokenInformation)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180043410`
- `0x180046468`

## callees

- `0x18000f114`
- `0x18003cbcc`

## import_xrefs

- `ntdll!ZwQueryInformationToken` at `0x18003cc43`
- `ntdll!ZwQueryInformationToken` at `0x18003cc43`
- `ntdll!ZwClose` at `0x18003cc6a`
- `ntdll!ZwClose` at `0x18003cc6a`
- `ntdll!ZwOpenProcessToken` at `0x18003cbf7`
- `ntdll!ZwOpenProcessToken` at `0x18003cbf7`

## string_xrefs

- `0x18003cc03`: `NtOpenProcessToken failed [%x]`
- `0x18003cc4f`: `NtQueryInformationToken failed [%x]`

## pseudocode

```c
__int64 __fastcall AslGetSessionId(PVOID TokenInformation)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 v5; // r8
  PULONG ResultLength; // [rsp+20h] [rbp-18h]
  ULONG v8; // [rsp+48h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  TokenHandle = 0;
  v2 = ZwOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x20008u, &TokenHandle);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = "NtOpenProcessToken failed [%x]";
    v5 = 416;
LABEL_3:
    LODWORD(ResultLength) = v2;
    AslLogCallPrintf(1, "AslGetSessionId", v5, v4, ResultLength);
    goto LABEL_7;
  }
  v2 = ZwQueryInformationToken(TokenHandle, TokenSessionId, TokenInformation, 4u, &v8);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = "NtQueryInformationToken failed [%x]";
    v5 = 426;
    goto LABEL_3;
  }
  v3 = 0;
LABEL_7:
  if ( TokenHandle )
    ZwClose(TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x18003cbcc  mov     rax, rsp
0x18003cbcf  mov     [rax+8], rbx
0x18003cbd3  push    rdi
0x18003cbd4  sub     rsp, 30h
0x18003cbd8  mov     rdi, rcx
0x18003cbdb  mov     dword ptr [rax+10h], 0
0x18003cbe2  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18003cbe6  mov     qword ptr [rax+18h], 0
0x18003cbee  lea     r8, [rax+18h]; TokenHandle
0x18003cbf2  mov     edx, 20008h; DesiredAccess
0x18003cbf7  call    cs:__imp_ZwOpenProcessToken
0x18003cbfd  mov     ebx, eax
0x18003cbff  test    eax, eax
0x18003cc01  jns     short loc_18003CC27
0x18003cc03  lea     r9, aNtopenprocesst; "NtOpenProcessToken failed [%x]"
0x18003cc0a  mov     r8d, 1A0h
0x18003cc10  lea     rdx, aAslgetsessioni; "AslGetSessionId"
0x18003cc17  mov     dword ptr [rsp+38h+ResultLength], eax
0x18003cc1b  mov     ecx, 1
0x18003cc20  call    AslLogCallPrintf
0x18003cc25  jmp     short loc_18003CC60
0x18003cc27  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18003cc2c  lea     rax, [rsp+38h+arg_8]
0x18003cc31  mov     r9d, 4; Length
0x18003cc37  mov     [rsp+38h+ResultLength], rax; ResultLength
0x18003cc3c  mov     r8, rdi; TokenInformation
0x18003cc3f  lea     edx, [r9+8]; TokenInformationClass
0x18003cc43  call    cs:__imp_ZwQueryInformationToken
0x18003cc49  mov     ebx, eax
0x18003cc4b  test    eax, eax
0x18003cc4d  jns     short loc_18003CC5E
0x18003cc4f  lea     r9, aNtqueryinforma_2; "NtQueryInformationToken failed [%x]"
0x18003cc56  mov     r8d, 1AAh
0x18003cc5c  jmp     short loc_18003CC10
0x18003cc5e  xor     ebx, ebx
0x18003cc60  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x18003cc65  test    rcx, rcx
0x18003cc68  jz      short loc_18003CC70
0x18003cc6a  call    cs:__imp_ZwClose
0x18003cc70  mov     eax, ebx
0x18003cc72  mov     rbx, [rsp+38h+arg_0]
0x18003cc77  add     rsp, 30h
0x18003cc7b  pop     rdi
0x18003cc7c  retn
```
