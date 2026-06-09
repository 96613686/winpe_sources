# BACKUP_FILE_SYSTEM_HELPER::CreateBackupStorageDirectoryTransacted(void *)

- ea: `0x180023474`
- end: `0x1800235d3`
- name: `?CreateBackupStorageDirectoryTransacted@BACKUP_FILE_SYSTEM_HELPER@@CAJPEAX@Z`
- size: `351`
- prototype: `__int64 __fastcall(HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023208`

## callees

- `0x180001fb0`
- `0x180023474`
- `0x180024480`
- `0x180033bc4`
- `0x180034d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002357a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002357a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023598`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023598`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x180023570`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x180023570`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180023543`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180023543`

## pseudocode

```c
__int64 __fastcall BACKUP_FILE_SYSTEM_HELPER::CreateBackupStorageDirectoryTransacted(HANDLE hTransaction)
{
  signed int AppcmdBackupStoragePath; // ebx
  signed int LastError; // eax
  ULONG SecurityDescriptorSize; // [rsp+20h] [rbp-49h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+28h] [rbp-41h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v8[4]; // [rsp+48h] [rbp-21h] BYREF
  LPCWSTR lpNewDirectory; // [rsp+68h] [rbp-1h]
  int v10; // [rsp+70h] [rbp+7h]
  __int16 v11; // [rsp+74h] [rbp+Bh]
  int v12; // [rsp+78h] [rbp+Fh]
  _QWORD v13[4]; // [rsp+80h] [rbp+17h] BYREF
  unsigned __int16 *v14; // [rsp+A0h] [rbp+37h]
  int v15; // [rsp+A8h] [rbp+3Fh]
  __int16 v16; // [rsp+ACh] [rbp+43h]
  int v17; // [rsp+B0h] [rbp+47h]

  v13[0] = 0;
  v14 = (unsigned __int16 *)v13;
  v16 = 256;
  lpNewDirectory = (LPCWSTR)v8;
  v15 = 32;
  v17 = 0;
  v8[0] = 0;
  v10 = 32;
  v11 = 256;
  v12 = 0;
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( hTransaction == (HANDLE)-1LL )
  {
    AppcmdBackupStoragePath = -2147024809;
  }
  else
  {
    AppcmdBackupStoragePath = BACKUP_FILE_SYSTEM_HELPER::GetAppcmdBackupStoragePath((struct STRU *)v13);
    if ( AppcmdBackupStoragePath >= 0 )
    {
      AppcmdBackupStoragePath = MakePathCanonicalizationProof(v14, (struct STRU *)v8);
      if ( AppcmdBackupStoragePath >= 0 )
      {
        if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
                L"O:BAG:BAD:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)",
                1u,
                &SecurityDescriptor,
                &SecurityDescriptorSize)
          || (SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor,
              SecurityAttributes.nLength = 24,
              SecurityAttributes.bInheritHandle = 0,
              !CreateDirectoryTransactedW(0, lpNewDirectory, &SecurityAttributes, hTransaction)) )
        {
          LastError = GetLastError();
          AppcmdBackupStoragePath = LastError;
          if ( LastError > 0 )
            AppcmdBackupStoragePath = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
  }
  BUFFER::~BUFFER((BUFFER *)v8);
  BUFFER::~BUFFER((BUFFER *)v13);
  return (unsigned int)AppcmdBackupStoragePath;
}

```

## disassembly

```asm
0x180023474  mov     [rsp-8+arg_8], rbx
0x180023479  mov     [rsp-8+arg_10], rdi
0x18002347e  push    rbp
0x18002347f  lea     rbp, [rsp-57h]
0x180023484  sub     rsp, 0C0h
0x18002348b  mov     rax, cs:__security_cookie
0x180023492  xor     rax, rsp
0x180023495  mov     [rbp+57h+var_8], rax
0x180023499  lea     rax, [rbp+57h+var_40]
0x18002349d  mov     [rbp+57h+var_40], 0
0x1800234a5  mov     [rbp+57h+var_20], rax
0x1800234a9  mov     rdi, rcx
0x1800234ac  lea     rax, [rbp+57h+var_78]
0x1800234b0  mov     [rbp+57h+var_14], 100h
0x1800234b6  mov     ecx, 20h ; ' '
0x1800234bb  mov     [rbp+57h+lpNewDirectory], rax
0x1800234bf  xor     eax, eax
0x1800234c1  mov     [rbp+57h+var_18], ecx
0x1800234c4  mov     [rbp+57h+var_10], 0
0x1800234cb  xorps   xmm0, xmm0
0x1800234ce  mov     [rbp+57h+var_78], 0
0x1800234d6  mov     [rbp+57h+var_50], ecx
0x1800234d9  mov     [rbp+57h+var_4C], 100h
0x1800234df  mov     [rbp+57h+var_48], 0
0x1800234e6  mov     [rbp+57h+SecurityDescriptor], 0
0x1800234ee  mov     [rbp+57h+SecurityDescriptorSize], 0
0x1800234f5  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x1800234f9  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x1800234fd  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180023501  jnz     short loc_18002350D
0x180023503  mov     ebx, 80070057h
0x180023508  jmp     loc_18002359E
0x18002350d  lea     rcx, [rbp+57h+var_40]; this
0x180023511  call    ?GetAppcmdBackupStoragePath@BACKUP_FILE_SYSTEM_HELPER@@CAJPEAVSTRU@@@Z; BACKUP_FILE_SYSTEM_HELPER::GetAppcmdBackupStoragePath(STRU *)
0x180023516  mov     ebx, eax
0x180023518  test    eax, eax
0x18002351a  js      short loc_18002358F
0x18002351c  mov     rcx, [rbp+57h+var_20]; unsigned __int16 *
0x180023520  lea     rdx, [rbp+57h+var_78]; this
0x180023524  call    ?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180023529  mov     ebx, eax
0x18002352b  test    eax, eax
0x18002352d  js      short loc_18002358F
0x18002352f  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180023533  mov     edx, 1; StringSDRevision
0x180023538  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18002353c  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:PAI(A;OICI;FA;;;SY)(A;OICI;FA"...
0x180023543  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180023549  test    eax, eax
0x18002354b  jz      short loc_18002357A
0x18002354d  mov     rax, [rbp+57h+SecurityDescriptor]
0x180023551  lea     r8, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x180023555  mov     rdx, [rbp+57h+lpNewDirectory]; lpNewDirectory
0x180023559  mov     r9, rdi; hTransaction
0x18002355c  xor     ecx, ecx; lpTemplateDirectory
0x18002355e  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x180023562  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x180023569  mov     [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x180023570  call    cs:__imp_CreateDirectoryTransactedW
0x180023576  test    eax, eax
0x180023578  jnz     short loc_18002358F
0x18002357a  call    cs:__imp_GetLastError
0x180023580  mov     ebx, eax
0x180023582  test    eax, eax
0x180023584  jle     short loc_18002358F
0x180023586  movzx   ebx, ax
0x180023589  or      ebx, 80070000h
0x18002358f  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180023593  test    rcx, rcx
0x180023596  jz      short loc_18002359E
0x180023598  call    cs:__imp_LocalFree
0x18002359e  lea     rcx, [rbp+57h+var_78]; this
0x1800235a2  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800235a7  lea     rcx, [rbp+57h+var_40]; this
0x1800235ab  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800235b0  mov     eax, ebx
0x1800235b2  mov     rcx, [rbp+57h+var_8]
0x1800235b6  xor     rcx, rsp; StackCookie
0x1800235b9  call    __security_check_cookie
0x1800235be  lea     r11, [rsp+0C0h+var_s0]
0x1800235c6  mov     rbx, [r11+18h]
0x1800235ca  mov     rdi, [r11+20h]
0x1800235ce  mov     rsp, r11
0x1800235d1  pop     rbp
0x1800235d2  retn
```
