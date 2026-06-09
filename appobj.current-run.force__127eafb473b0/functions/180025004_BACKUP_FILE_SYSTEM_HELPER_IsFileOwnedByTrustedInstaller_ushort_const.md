# BACKUP_FILE_SYSTEM_HELPER::IsFileOwnedByTrustedInstaller(ushort const *)

- ea: `0x180025004`
- end: `0x18002514f`
- name: `?IsFileOwnedByTrustedInstaller@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBG@Z`
- size: `331`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180024854`

## callees

- `0x180001fb0`
- `0x180025004`
- `0x180033954`
- `0x180034cbe`
- `0x180034cca`
- `0x180034d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002507e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800250ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002507e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800250ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002511d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002511d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800250f2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800250f2`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180025074`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800250c4`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180025074`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800250c4`

## pseudocode

```c
__int64 __fastcall BACKUP_FILE_SYSTEM_HELPER::IsFileOwnedByTrustedInstaller(LPCWSTR lpFileName)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  _BYTE *v4; // rbx
  DWORD nLengthNeeded; // [rsp+30h] [rbp-59h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+38h] [rbp-51h] BYREF
  _BYTE v8[32]; // [rsp+40h] [rbp-49h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-29h]
  DWORD nLength; // [rsp+68h] [rbp-21h]
  __int16 v11; // [rsp+6Ch] [rbp-1Dh]
  _BYTE pSecurityDescriptor[64]; // [rsp+70h] [rbp-19h] BYREF

  memset_0(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  nLength = 64;
  SecurityDescriptor = pSecurityDescriptor;
  v11 = 256;
  nLengthNeeded = 0;
  StringSecurityDescriptor = 0;
  if ( GetFileSecurityW(lpFileName, 1u, pSecurityDescriptor, 0x40u, &nLengthNeeded) )
  {
    v4 = pSecurityDescriptor;
LABEL_8:
    if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v4, 1u, 1u, &StringSecurityDescriptor, 0) )
    {
      v3 = wcscmp_0(StringSecurityDescriptor, L"O:S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464") != 0;
      goto LABEL_10;
    }
    goto LABEL_6;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError != 122 )
    goto LABEL_3;
  BUFFER::Resize((BUFFER *)v8, nLengthNeeded);
  v4 = SecurityDescriptor;
  if ( GetFileSecurityW(lpFileName, 1u, SecurityDescriptor, nLength, &nLengthNeeded) )
    goto LABEL_8;
LABEL_6:
  LastError = GetLastError();
  v3 = LastError;
LABEL_3:
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
LABEL_10:
  if ( StringSecurityDescriptor )
  {
    LocalFree(StringSecurityDescriptor);
    StringSecurityDescriptor = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v8);
  return v3;
}

```

## disassembly

```asm
0x180025004  push    rbp
0x180025006  push    rbx
0x180025007  push    rdi
0x180025008  push    r14
0x18002500a  lea     rbp, [rsp-3Fh]
0x18002500f  sub     rsp, 0C8h
0x180025016  mov     rax, cs:__security_cookie
0x18002501d  xor     rax, rsp
0x180025020  mov     [rbp+57h+var_30], rax
0x180025024  mov     rdi, rcx
0x180025027  mov     ebx, 40h ; '@'
0x18002502c  mov     r8d, ebx; Size
0x18002502f  lea     rcx, [rbp+57h+pSecurityDescriptor]; void *
0x180025033  xor     edx, edx; Val
0x180025035  call    memset_0
0x18002503a  lea     rax, [rbp+57h+pSecurityDescriptor]
0x18002503e  mov     [rbp+57h+nLength], ebx
0x180025041  mov     [rbp+57h+SecurityDescriptor], rax
0x180025045  lea     r14d, [rbx-3Fh]
0x180025049  lea     rax, [rbp+57h+nLengthNeeded]
0x18002504d  mov     [rbp+57h+var_74], 100h
0x180025053  mov     r9d, ebx; nLength
0x180025056  mov     [rsp+0E0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18002505b  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18002505f  mov     [rbp+57h+nLengthNeeded], 0
0x180025066  mov     edx, r14d; RequestedInformation
0x180025069  mov     [rbp+57h+StringSecurityDescriptor], 0
0x180025071  mov     rcx, rdi; lpFileName
0x180025074  call    cs:__imp_GetFileSecurityW
0x18002507a  test    eax, eax
0x18002507c  jnz     short loc_1800250D8
0x18002507e  call    cs:__imp_GetLastError
0x180025084  mov     ebx, eax
0x180025086  cmp     eax, 7Ah ; 'z'
0x180025089  jz      short loc_18002509E
0x18002508b  test    eax, eax
0x18002508d  jle     loc_180025114
0x180025093  movzx   ebx, ax
0x180025096  or      ebx, 80070000h
0x18002509c  jmp     short loc_180025114
0x18002509e  mov     edx, [rbp+57h+nLengthNeeded]; unsigned int
0x1800250a1  lea     rcx, [rbp+57h+var_A0]; this
0x1800250a5  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800250aa  mov     rbx, [rbp+57h+SecurityDescriptor]
0x1800250ae  lea     rax, [rbp+57h+nLengthNeeded]
0x1800250b2  mov     r9d, [rbp+57h+nLength]; nLength
0x1800250b6  mov     r8, rbx; pSecurityDescriptor
0x1800250b9  mov     edx, r14d; RequestedInformation
0x1800250bc  mov     [rsp+0E0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800250c1  mov     rcx, rdi; lpFileName
0x1800250c4  call    cs:__imp_GetFileSecurityW
0x1800250ca  test    eax, eax
0x1800250cc  jnz     short loc_1800250DC
0x1800250ce  call    cs:__imp_GetLastError
0x1800250d4  mov     ebx, eax
0x1800250d6  jmp     short loc_18002508B
0x1800250d8  lea     rbx, [rbp+57h+pSecurityDescriptor]
0x1800250dc  lea     r9, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800250e0  mov     [rsp+0E0h+lpnLengthNeeded], 0; StringSecurityDescriptorLen
0x1800250e9  mov     r8d, r14d; SecurityInformation
0x1800250ec  mov     edx, r14d; RequestedStringSDRevision
0x1800250ef  mov     rcx, rbx; SecurityDescriptor
0x1800250f2  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800250f8  test    eax, eax
0x1800250fa  jz      short loc_1800250CE
0x1800250fc  mov     rcx, [rbp+57h+StringSecurityDescriptor]; String1
0x180025100  lea     rdx, aOS158095600888; "O:S-1-5-80-956008885-3418522649-1831038"...
0x180025107  xor     ebx, ebx
0x180025109  call    wcscmp_0
0x18002510e  test    eax, eax
0x180025110  cmovnz  ebx, r14d
0x180025114  mov     rcx, [rbp+57h+StringSecurityDescriptor]; hMem
0x180025118  test    rcx, rcx
0x18002511b  jz      short loc_18002512B
0x18002511d  call    cs:__imp_LocalFree
0x180025123  mov     [rbp+57h+StringSecurityDescriptor], 0
0x18002512b  lea     rcx, [rbp+57h+var_A0]; this
0x18002512f  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180025134  mov     eax, ebx
0x180025136  mov     rcx, [rbp+57h+var_30]
0x18002513a  xor     rcx, rsp; StackCookie
0x18002513d  call    __security_check_cookie
0x180025142  add     rsp, 0C8h
0x180025149  pop     r14
0x18002514b  pop     rdi
0x18002514c  pop     rbx
0x18002514d  pop     rbp
0x18002514e  retn
```
