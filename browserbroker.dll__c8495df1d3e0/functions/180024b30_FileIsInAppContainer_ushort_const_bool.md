# FileIsInAppContainer(ushort const *,bool *)

- ea: `0x180024b30`
- end: `0x180024c52`
- name: `?FileIsInAppContainer@@YAJPEBGPEA_N@Z`
- size: `290`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001c9b0`
- `0x18001df80`

## callees

- `0x180024b30`
- `0x180024c58`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024c3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024bac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024bac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024bc1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024bc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024c36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024c36`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024b6e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024b6e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180024c16`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180024c16`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180024b9e`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180024be7`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180024b9e`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180024be7`

## pseudocode

```c
__int64 __fastcall FileIsInAppContainer(const unsigned __int16 *a1, bool *a2)
{
  unsigned int v3; // esi
  HANDLE FileW; // rdi
  HLOCAL v5; // rbx
  PACL pDacl; // [rsp+40h] [rbp-10h] BYREF
  DWORD nLengthNeeded; // [rsp+88h] [rbp+38h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+90h] [rbp+40h] BYREF
  WINBOOL bDaclPresent; // [rsp+98h] [rbp+48h] BYREF

  *a2 = 0;
  v3 = -2147467259;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    nLengthNeeded = 0;
    if ( !GetKernelObjectSecurity(FileW, 4u, 0, 0, &nLengthNeeded) && GetLastError() == 122 )
    {
      v5 = LocalAlloc(0x40u, nLengthNeeded);
      if ( v5 )
      {
        if ( GetKernelObjectSecurity(FileW, 4u, v5, nLengthNeeded, &nLengthNeeded) )
        {
          pDacl = 0;
          bDaclPresent = 0;
          bDaclDefaulted = 0;
          if ( GetSecurityDescriptorDacl(v5, &bDaclPresent, &pDacl, &bDaclDefaulted) )
          {
            if ( pDacl )
            {
              *a2 = _DaclHasAllowAceForAppContainer(pDacl);
              v3 = 0;
            }
          }
        }
        LocalFree(v5);
      }
    }
    CloseHandle(FileW);
  }
  return v3;
}

```

## disassembly

```asm
0x180024b30  push    rbp
0x180024b32  push    rbx
0x180024b33  push    rsi
0x180024b34  push    rdi
0x180024b35  push    r14
0x180024b37  mov     rbp, rsp
0x180024b3a  sub     rsp, 50h
0x180024b3e  xor     r9d, r9d; lpSecurityAttributes
0x180024b41  mov     byte ptr [rdx], 0
0x180024b44  mov     r14, rdx
0x180024b47  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x180024b50  mov     [rsp+50h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180024b58  mov     edx, 80000000h; dwDesiredAccess
0x180024b5d  mov     esi, 80004005h
0x180024b62  mov     [rsp+50h+dwCreationDisposition], 3; dwCreationDisposition
0x180024b6a  lea     r8d, [r9+1]; dwShareMode
0x180024b6e  call    cs:__imp_CreateFileW
0x180024b74  mov     rdi, rax
0x180024b77  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024b7b  jz      loc_180024C45
0x180024b81  xor     r9d, r9d; nLength
0x180024b84  mov     [rbp+nLengthNeeded], 0
0x180024b8b  lea     rax, [rbp+nLengthNeeded]
0x180024b8f  xor     r8d, r8d; pSecurityDescriptor
0x180024b92  mov     rcx, rdi; Handle
0x180024b95  mov     qword ptr [rsp+50h+dwCreationDisposition], rax; lpnLengthNeeded
0x180024b9a  lea     edx, [r9+4]; RequestedInformation
0x180024b9e  call    cs:__imp_GetKernelObjectSecurity
0x180024ba4  test    eax, eax
0x180024ba6  jnz     loc_180024C3C
0x180024bac  call    cs:__imp_GetLastError
0x180024bb2  cmp     eax, 7Ah ; 'z'
0x180024bb5  jnz     loc_180024C3C
0x180024bbb  mov     edx, [rbp+nLengthNeeded]; uBytes
0x180024bbe  lea     ecx, [rax-3Ah]; uFlags
0x180024bc1  call    cs:__imp_LocalAlloc
0x180024bc7  mov     rbx, rax
0x180024bca  test    rax, rax
0x180024bcd  jz      short loc_180024C3C
0x180024bcf  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180024bd3  lea     rax, [rbp+nLengthNeeded]
0x180024bd7  mov     r8, rbx; pSecurityDescriptor
0x180024bda  mov     qword ptr [rsp+50h+dwCreationDisposition], rax; lpnLengthNeeded
0x180024bdf  mov     edx, 4; RequestedInformation
0x180024be4  mov     rcx, rdi; Handle
0x180024be7  call    cs:__imp_GetKernelObjectSecurity
0x180024bed  test    eax, eax
0x180024bef  jz      short loc_180024C33
0x180024bf1  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180024bf5  mov     [rbp+pDacl], 0
0x180024bfd  lea     r8, [rbp+pDacl]; pDacl
0x180024c01  mov     [rbp+bDaclPresent], 0
0x180024c08  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180024c0c  mov     [rbp+bDaclDefaulted], 0
0x180024c13  mov     rcx, rbx; pSecurityDescriptor
0x180024c16  call    cs:__imp_GetSecurityDescriptorDacl
0x180024c1c  test    eax, eax
0x180024c1e  jz      short loc_180024C33
0x180024c20  mov     rcx, [rbp+pDacl]; pAcl
0x180024c24  test    rcx, rcx
0x180024c27  jz      short loc_180024C33
0x180024c29  call    ?_DaclHasAllowAceForAppContainer@@YA_NPEAU_ACL@@@Z; _DaclHasAllowAceForAppContainer(_ACL *)
0x180024c2e  mov     [r14], al
0x180024c31  xor     esi, esi
0x180024c33  mov     rcx, rbx; hMem
0x180024c36  call    cs:__imp_LocalFree
0x180024c3c  mov     rcx, rdi; hObject
0x180024c3f  call    cs:__imp_CloseHandle
0x180024c45  mov     eax, esi
0x180024c47  add     rsp, 50h
0x180024c4b  pop     r14
0x180024c4d  pop     rdi
0x180024c4e  pop     rsi
0x180024c4f  pop     rbx
0x180024c50  pop     rbp
0x180024c51  retn
```
