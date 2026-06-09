# BaseRegSaveKeyInternal

- ea: `0x180060dc0`
- end: `0x180061001`
- name: `BaseRegSaveKeyInternal`
- size: `577`
- prototype: `ULONG __fastcall(HANDLE KeyHandle, __int16 *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800362a0`
- `0x18004e7d0`

## callees

- `0x180060dc0`
- `0x1800610e0`

## import_xrefs

- `ntdll!NtClose` at `0x180060fb0`
- `ntdll!NtClose` at `0x180060fd0`
- `ntdll!NtClose` at `0x180060fb0`
- `ntdll!NtClose` at `0x180060fd0`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180060e61`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180060e61`
- `ntdll!NtCreateFile` at `0x180060f2e`
- `ntdll!NtCreateFile` at `0x180060f2e`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180060e7e`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180060e7e`
- `ntdll!RtlReleaseRelativeName` at `0x180060f3a`
- `ntdll!RtlReleaseRelativeName` at `0x180060f3a`
- `ntdll!NtSaveKey` at `0x180060fc4`
- `ntdll!NtSaveKey` at `0x180060fc4`
- `ntdll!NtSaveMergedKeys` at `0x180060fa0`
- `ntdll!NtSaveMergedKeys` at `0x180060fa0`
- `ntdll!RtlFreeHeap` at `0x180060f52`
- `ntdll!RtlFreeHeap` at `0x180060f52`
- `ntdll!RtlNtStatusToDosError` at `0x180060fd8`
- `ntdll!RtlNtStatusToDosError` at `0x180060fd8`

## pseudocode

```c
ULONG __fastcall BaseRegSaveKeyInternal(HANDLE KeyHandle, __int16 *a2, __int64 a3)
{
  __int16 v6; // ax
  void *v7; // rcx
  PWSTR Buffer; // r14
  HANDLE ContainingDirectory; // rax
  int UserAndMachineClass; // ebx
  __int64 v11; // rcx
  __int64 v12; // r8
  HANDLE v13; // r14
  HANDLE v14; // rdi
  void *v15; // rcx
  HANDLE HighPrecedenceKeyHandle; // [rsp+60h] [rbp-49h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+68h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-31h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+88h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-1h] BYREF
  HANDLE FileHandle; // [rsp+110h] [rbp+67h] BYREF
  HANDLE LowPrecedenceKeyHandle; // [rsp+128h] [rbp+7Fh] BYREF

  FileHandle = 0;
  NtName = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( KeyHandle )
  {
    if ( a2 )
    {
      if ( *((_QWORD *)a2 + 1) )
      {
        v6 = *a2;
        if ( (*a2 & 1) == 0 )
        {
          if ( v6 )
            *a2 = v6 - 2;
          if ( !a3 || (v7 = *(void **)(a3 + 8)) != 0 && RtlValidRelativeSecurityDescriptor(v7, *(_DWORD *)(a3 + 16), 0) )
          {
            if ( RtlDosPathNameToRelativeNtPathName_U(*((PCWSTR *)a2 + 1), &NtName, 0, &RelativeName) )
            {
              Buffer = NtName.Buffer;
              if ( RelativeName.RelativeName.Length )
              {
                NtName = RelativeName.RelativeName;
                ContainingDirectory = RelativeName.ContainingDirectory;
              }
              else
              {
                ContainingDirectory = 0;
                RelativeName.ContainingDirectory = 0;
              }
              ObjectAttributes.RootDirectory = ContainingDirectory;
              ObjectAttributes.ObjectName = &NtName;
              ObjectAttributes.Length = 48;
              ObjectAttributes.Attributes = 64;
              if ( a3 )
                ObjectAttributes.SecurityDescriptor = *(PVOID *)(a3 + 8);
              else
                ObjectAttributes.SecurityDescriptor = 0;
              ObjectAttributes.SecurityQualityOfService = 0;
              UserAndMachineClass = NtCreateFile(
                                      &FileHandle,
                                      0x40100000u,
                                      &ObjectAttributes,
                                      &IoStatusBlock,
                                      0,
                                      0x80u,
                                      1u,
                                      2u,
                                      0x4020u,
                                      0,
                                      0);
              RtlReleaseRelativeName(&RelativeName);
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
              if ( UserAndMachineClass < 0 )
                return RtlNtStatusToDosError(UserAndMachineClass);
              if ( ((unsigned __int8)KeyHandle & 2) != 0 )
              {
                LowPrecedenceKeyHandle = 0;
                HighPrecedenceKeyHandle = 0;
                UserAndMachineClass = BaseRegGetUserAndMachineClass(
                                        v11,
                                        KeyHandle,
                                        v12,
                                        &LowPrecedenceKeyHandle,
                                        &HighPrecedenceKeyHandle);
                if ( UserAndMachineClass < 0 )
                {
LABEL_27:
                  NtClose(FileHandle);
                  return RtlNtStatusToDosError(UserAndMachineClass);
                }
                v13 = LowPrecedenceKeyHandle;
                if ( LowPrecedenceKeyHandle )
                {
                  v14 = HighPrecedenceKeyHandle;
                  if ( HighPrecedenceKeyHandle )
                  {
                    UserAndMachineClass = NtSaveMergedKeys(HighPrecedenceKeyHandle, LowPrecedenceKeyHandle, FileHandle);
                    if ( v14 == KeyHandle )
                      v15 = v13;
                    else
                      v15 = v14;
                    NtClose(v15);
                    goto LABEL_27;
                  }
                }
              }
              UserAndMachineClass = NtSaveKey(KeyHandle, FileHandle);
              goto LABEL_27;
            }
          }
        }
      }
    }
  }
  return 87;
}

```

## disassembly

```asm
0x180060dc0  mov     [rsp-8+arg_8], rbx
0x180060dc5  mov     [rsp-8+arg_10], rsi
0x180060dca  push    rbp
0x180060dcb  push    rdi
0x180060dcc  push    r12
0x180060dce  push    r14
0x180060dd0  push    r15
0x180060dd2  lea     rbp, [rsp-37h]
0x180060dd7  sub     rsp, 0E0h
0x180060dde  xorps   xmm0, xmm0
0x180060de1  xor     r15d, r15d
0x180060de4  xorps   xmm1, xmm1
0x180060de7  mov     [rbp+57h+FileHandle], r15
0x180060deb  xor     eax, eax
0x180060ded  mov     rdi, r8
0x180060df0  mov     rbx, rdx
0x180060df3  mov     rsi, rcx
0x180060df6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180060dfa  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180060dfe  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x180060e02  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm1
0x180060e06  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm1
0x180060e0a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180060e0e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180060e12  test    rcx, rcx
0x180060e15  jz      loc_180060FE0
0x180060e1b  test    rdx, rdx
0x180060e1e  jz      loc_180060FE0
0x180060e24  cmp     [rdx+8], r15
0x180060e28  jz      loc_180060FE0
0x180060e2e  movzx   eax, word ptr [rdx]
0x180060e31  test    al, 1
0x180060e33  jnz     loc_180060FE0
0x180060e39  lea     r12d, [r15+2]
0x180060e3d  test    ax, ax
0x180060e40  jz      short loc_180060E49
0x180060e42  sub     ax, r12w
0x180060e46  mov     [rdx], ax
0x180060e49  test    rdi, rdi
0x180060e4c  jz      short loc_180060E6F
0x180060e4e  mov     rcx, [r8+8]; SecurityDescriptorInput
0x180060e52  test    rcx, rcx
0x180060e55  jz      loc_180060FE0
0x180060e5b  mov     edx, [rdi+10h]; SecurityDescriptorLength
0x180060e5e  xor     r8d, r8d; RequiredInformation
0x180060e61  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x180060e67  test    al, al
0x180060e69  jz      loc_180060FE0
0x180060e6f  mov     rcx, [rbx+8]; DosName
0x180060e73  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x180060e77  xor     r8d, r8d; PartName
0x180060e7a  lea     rdx, [rbp+57h+NtName]; NtName
0x180060e7e  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180060e84  test    al, al
0x180060e86  jz      loc_180060FE0
0x180060e8c  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x180060e90  mov     r14, [rbp+57h+NtName.Buffer]
0x180060e94  test    ax, ax
0x180060e97  jz      short loc_180060EB9
0x180060e99  mov     [rbp+57h+NtName.Length], ax
0x180060e9d  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x180060ea0  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x180060ea3  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x180060ea7  mov     word ptr [rbp+57h+NtName+6], ax
0x180060eab  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x180060eaf  mov     [rbp+57h+NtName.Buffer], rax
0x180060eb3  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x180060eb7  jmp     short loc_180060EC0
0x180060eb9  mov     rax, r15
0x180060ebc  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x180060ec0  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180060ec4  lea     rax, [rbp+57h+NtName]
0x180060ec8  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180060ecc  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180060ed3  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180060eda  test    rdi, rdi
0x180060edd  jz      short loc_180060EE9
0x180060edf  mov     rax, [rdi+8]
0x180060ee3  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x180060ee7  jmp     short loc_180060EED
0x180060ee9  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r15
0x180060eed  mov     [rsp+100h+EaLength], r15d; EaLength
0x180060ef2  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180060ef6  mov     [rsp+100h+EaBuffer], r15; EaBuffer
0x180060efb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180060eff  mov     [rsp+100h+CreateOptions], 4020h; CreateOptions
0x180060f07  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180060f0b  mov     [rsp+100h+CreateDisposition], r12d; CreateDisposition
0x180060f10  mov     edx, 40100000h; DesiredAccess
0x180060f15  mov     [rsp+100h+ShareAccess], 1; ShareAccess
0x180060f1d  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x180060f25  mov     [rsp+100h+AllocationSize], r15; AllocationSize
0x180060f2a  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r15
0x180060f2e  call    cs:__imp_NtCreateFile
0x180060f34  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x180060f38  mov     ebx, eax
0x180060f3a  call    cs:__imp_RtlReleaseRelativeName
0x180060f40  mov     rcx, gs:60h
0x180060f49  mov     r8, r14; P
0x180060f4c  xor     edx, edx; Flags
0x180060f4e  mov     rcx, [rcx+30h]; HeapHandle
0x180060f52  call    cs:__imp_RtlFreeHeap
0x180060f58  test    ebx, ebx
0x180060f5a  js      short loc_180060FD6
0x180060f5c  test    r12b, sil
0x180060f5f  jz      short loc_180060FBD
0x180060f61  lea     rax, [rbp+57h+HighPrecedenceKeyHandle]
0x180060f65  mov     [rbp+57h+LowPrecedenceKeyHandle], r15
0x180060f69  lea     r9, [rbp+57h+LowPrecedenceKeyHandle]
0x180060f6d  mov     [rsp+100h+AllocationSize], rax
0x180060f72  mov     rdx, rsi
0x180060f75  mov     [rbp+57h+HighPrecedenceKeyHandle], r15
0x180060f79  call    BaseRegGetUserAndMachineClass
0x180060f7e  mov     ebx, eax
0x180060f80  test    eax, eax
0x180060f82  js      short loc_180060FCC
0x180060f84  mov     r14, [rbp+57h+LowPrecedenceKeyHandle]
0x180060f88  test    r14, r14
0x180060f8b  jz      short loc_180060FBD
0x180060f8d  mov     rdi, [rbp+57h+HighPrecedenceKeyHandle]
0x180060f91  test    rdi, rdi
0x180060f94  jz      short loc_180060FBD
0x180060f96  mov     r8, [rbp+57h+FileHandle]; FileHandle
0x180060f9a  mov     rdx, r14; LowPrecedenceKeyHandle
0x180060f9d  mov     rcx, rdi; HighPrecedenceKeyHandle
0x180060fa0  call    cs:__imp_NtSaveMergedKeys
0x180060fa6  mov     ebx, eax
0x180060fa8  cmp     rdi, rsi
0x180060fab  jz      short loc_180060FB8
0x180060fad  mov     rcx, rdi; Handle
0x180060fb0  call    cs:__imp_NtClose
0x180060fb6  jmp     short loc_180060FCC
0x180060fb8  mov     rcx, r14
0x180060fbb  jmp     short loc_180060FB0
0x180060fbd  mov     rdx, [rbp+57h+FileHandle]; FileHandle
0x180060fc1  mov     rcx, rsi; KeyHandle
0x180060fc4  call    cs:__imp_NtSaveKey
0x180060fca  mov     ebx, eax
0x180060fcc  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180060fd0  call    cs:__imp_NtClose
0x180060fd6  mov     ecx, ebx; Status
0x180060fd8  call    cs:__imp_RtlNtStatusToDosError
0x180060fde  jmp     short loc_180060FE5
0x180060fe0  mov     eax, 57h ; 'W'
0x180060fe5  lea     r11, [rsp+100h+var_20]
0x180060fed  mov     rbx, [r11+38h]
0x180060ff1  mov     rsi, [r11+40h]
0x180060ff5  mov     rsp, r11
0x180060ff8  pop     r15
0x180060ffa  pop     r14
0x180060ffc  pop     r12
0x180060ffe  pop     rdi
0x180060fff  pop     rbp
0x180061000  retn
```
