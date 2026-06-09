# BaseRegSaveKeyInternal

- ea: `0x18006d834`
- end: `0x18006dab6`
- name: `BaseRegSaveKeyInternal`
- size: `642`
- prototype: `ULONG __fastcall(HANDLE KeyHandle, __int16 *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003a1c0`
- `0x180054ba0`

## callees

- `0x18006d834`
- `0x18006dba4`

## import_xrefs

- `ntdll!NtClose` at `0x18006da4c`
- `ntdll!NtClose` at `0x18006da78`
- `ntdll!NtClose` at `0x18006da4c`
- `ntdll!NtClose` at `0x18006da78`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18006d8d5`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18006d8d5`
- `ntdll!NtCreateFile` at `0x18006d9ae`
- `ntdll!NtCreateFile` at `0x18006d9ae`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18006d8f8`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18006d8f8`
- `ntdll!RtlReleaseRelativeName` at `0x18006d9c0`
- `ntdll!RtlReleaseRelativeName` at `0x18006d9c0`
- `ntdll!NtSaveKey` at `0x18006da66`
- `ntdll!NtSaveKey` at `0x18006da66`
- `ntdll!NtSaveMergedKeys` at `0x18006da36`
- `ntdll!NtSaveMergedKeys` at `0x18006da36`
- `ntdll!RtlFreeHeap` at `0x18006d9de`
- `ntdll!RtlFreeHeap` at `0x18006d9de`
- `ntdll!RtlNtStatusToDosError` at `0x18006da86`
- `ntdll!RtlNtStatusToDosError` at `0x18006da86`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18006d834  mov     [rsp-8+arg_8], rbx
0x18006d839  mov     [rsp-8+arg_10], rsi
0x18006d83e  push    rbp
0x18006d83f  push    rdi
0x18006d840  push    r12
0x18006d842  push    r14
0x18006d844  push    r15
0x18006d846  lea     rbp, [rsp-37h]
0x18006d84b  sub     rsp, 0E0h
0x18006d852  xorps   xmm0, xmm0
0x18006d855  xor     r15d, r15d
0x18006d858  xorps   xmm1, xmm1
0x18006d85b  mov     [rbp+57h+FileHandle], r15
0x18006d85f  xor     eax, eax
0x18006d861  mov     rdi, r8
0x18006d864  mov     rbx, rdx
0x18006d867  mov     rsi, rcx
0x18006d86a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18006d86e  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18006d872  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x18006d876  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm1
0x18006d87a  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm1
0x18006d87e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18006d882  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18006d886  test    rcx, rcx
0x18006d889  jz      loc_18006DA94
0x18006d88f  test    rdx, rdx
0x18006d892  jz      loc_18006DA94
0x18006d898  cmp     [rdx+8], r15
0x18006d89c  jz      loc_18006DA94
0x18006d8a2  movzx   eax, word ptr [rdx]
0x18006d8a5  test    al, 1
0x18006d8a7  jnz     loc_18006DA94
0x18006d8ad  lea     r12d, [r15+2]
0x18006d8b1  test    ax, ax
0x18006d8b4  jz      short loc_18006D8BD
0x18006d8b6  sub     ax, r12w
0x18006d8ba  mov     [rdx], ax
0x18006d8bd  test    rdi, rdi
0x18006d8c0  jz      short loc_18006D8E9
0x18006d8c2  mov     rcx, [r8+8]; SecurityDescriptorInput
0x18006d8c6  test    rcx, rcx
0x18006d8c9  jz      loc_18006DA94
0x18006d8cf  mov     edx, [rdi+10h]; SecurityDescriptorLength
0x18006d8d2  xor     r8d, r8d; RequiredInformation
0x18006d8d5  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18006d8dc  nop     dword ptr [rax+rax+00h]
0x18006d8e1  test    al, al
0x18006d8e3  jz      loc_18006DA94
0x18006d8e9  mov     rcx, [rbx+8]; DosName
0x18006d8ed  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x18006d8f1  xor     r8d, r8d; PartName
0x18006d8f4  lea     rdx, [rbp+57h+NtName]; NtName
0x18006d8f8  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18006d8ff  nop     dword ptr [rax+rax+00h]
0x18006d904  test    al, al
0x18006d906  jz      loc_18006DA94
0x18006d90c  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x18006d910  mov     r14, [rbp+57h+NtName.Buffer]
0x18006d914  test    ax, ax
0x18006d917  jz      short loc_18006D939
0x18006d919  mov     [rbp+57h+NtName.Length], ax
0x18006d91d  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x18006d920  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x18006d923  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x18006d927  mov     word ptr [rbp+57h+NtName+6], ax
0x18006d92b  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x18006d92f  mov     [rbp+57h+NtName.Buffer], rax
0x18006d933  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x18006d937  jmp     short loc_18006D940
0x18006d939  mov     rax, r15
0x18006d93c  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x18006d940  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18006d944  lea     rax, [rbp+57h+NtName]
0x18006d948  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18006d94c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006d953  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18006d95a  test    rdi, rdi
0x18006d95d  jz      short loc_18006D969
0x18006d95f  mov     rax, [rdi+8]
0x18006d963  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x18006d967  jmp     short loc_18006D96D
0x18006d969  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r15
0x18006d96d  mov     [rsp+100h+EaLength], r15d; EaLength
0x18006d972  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18006d976  mov     [rsp+100h+EaBuffer], r15; EaBuffer
0x18006d97b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006d97f  mov     [rsp+100h+CreateOptions], 4020h; CreateOptions
0x18006d987  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18006d98b  mov     [rsp+100h+CreateDisposition], r12d; CreateDisposition
0x18006d990  mov     edx, 40100000h; DesiredAccess
0x18006d995  mov     [rsp+100h+ShareAccess], 1; ShareAccess
0x18006d99d  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x18006d9a5  mov     [rsp+100h+AllocationSize], r15; AllocationSize
0x18006d9aa  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r15
0x18006d9ae  call    cs:__imp_NtCreateFile
0x18006d9b5  nop     dword ptr [rax+rax+00h]
0x18006d9ba  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18006d9be  mov     ebx, eax
0x18006d9c0  call    cs:__imp_RtlReleaseRelativeName
0x18006d9c7  nop     dword ptr [rax+rax+00h]
0x18006d9cc  mov     rcx, gs:60h
0x18006d9d5  mov     r8, r14; P
0x18006d9d8  xor     edx, edx; Flags
0x18006d9da  mov     rcx, [rcx+30h]; HeapHandle
0x18006d9de  call    cs:__imp_RtlFreeHeap
0x18006d9e5  nop     dword ptr [rax+rax+00h]
0x18006d9ea  test    ebx, ebx
0x18006d9ec  js      loc_18006DA84
0x18006d9f2  test    r12b, sil
0x18006d9f5  jz      short loc_18006DA5F
0x18006d9f7  lea     rax, [rbp+57h+HighPrecedenceKeyHandle]
0x18006d9fb  mov     [rbp+57h+LowPrecedenceKeyHandle], r15
0x18006d9ff  lea     r9, [rbp+57h+LowPrecedenceKeyHandle]
0x18006da03  mov     [rsp+100h+AllocationSize], rax
0x18006da08  mov     rdx, rsi
0x18006da0b  mov     [rbp+57h+HighPrecedenceKeyHandle], r15
0x18006da0f  call    BaseRegGetUserAndMachineClass
0x18006da14  mov     ebx, eax
0x18006da16  test    eax, eax
0x18006da18  js      short loc_18006DA74
0x18006da1a  mov     r14, [rbp+57h+LowPrecedenceKeyHandle]
0x18006da1e  test    r14, r14
0x18006da21  jz      short loc_18006DA5F
0x18006da23  mov     rdi, [rbp+57h+HighPrecedenceKeyHandle]
0x18006da27  test    rdi, rdi
0x18006da2a  jz      short loc_18006DA5F
0x18006da2c  mov     r8, [rbp+57h+FileHandle]; FileHandle
0x18006da30  mov     rdx, r14; LowPrecedenceKeyHandle
0x18006da33  mov     rcx, rdi; HighPrecedenceKeyHandle
0x18006da36  call    cs:__imp_NtSaveMergedKeys
0x18006da3d  nop     dword ptr [rax+rax+00h]
0x18006da42  mov     ebx, eax
0x18006da44  cmp     rdi, rsi
0x18006da47  jz      short loc_18006DA5A
0x18006da49  mov     rcx, rdi; Handle
0x18006da4c  call    cs:__imp_NtClose
0x18006da53  nop     dword ptr [rax+rax+00h]
0x18006da58  jmp     short loc_18006DA74
0x18006da5a  mov     rcx, r14
0x18006da5d  jmp     short loc_18006DA4C
0x18006da5f  mov     rdx, [rbp+57h+FileHandle]; FileHandle
0x18006da63  mov     rcx, rsi; KeyHandle
0x18006da66  call    cs:__imp_NtSaveKey
0x18006da6d  nop     dword ptr [rax+rax+00h]
0x18006da72  mov     ebx, eax
0x18006da74  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18006da78  call    cs:__imp_NtClose
0x18006da7f  nop     dword ptr [rax+rax+00h]
0x18006da84  mov     ecx, ebx; Status
0x18006da86  call    cs:__imp_RtlNtStatusToDosError
0x18006da8d  nop     dword ptr [rax+rax+00h]
0x18006da92  jmp     short loc_18006DA99
0x18006da94  mov     eax, 57h ; 'W'
0x18006da99  lea     r11, [rsp+100h+var_20]
0x18006daa1  mov     rbx, [r11+38h]
0x18006daa5  mov     rsi, [r11+40h]
0x18006daa9  mov     rsp, r11
0x18006daac  pop     r15
0x18006daae  pop     r14
0x18006dab0  pop     r12
0x18006dab2  pop     rdi
0x18006dab3  pop     rbp
0x18006dab4  retn
```
