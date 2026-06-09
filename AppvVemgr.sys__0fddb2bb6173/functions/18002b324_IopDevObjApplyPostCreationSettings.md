# IopDevObjApplyPostCreationSettings

- ea: `0x18002b324`
- end: `0x18002b413`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `NTSTATUS __fastcall(PVOID Object, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002b190`

## callees

- `0x18002b324`
- `0x18002c40c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18002b3f9`
- `ntoskrnl!ZwClose` at `0x18002b3f9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x18002b3c9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x18002b3c9`
- `ntoskrnl!IoDeviceObjectType` at `0x18002b385`
- `ntoskrnl!ZwSetSecurityObject` at `0x18002b3e6`
- `ntoskrnl!ZwSetSecurityObject` at `0x18002b3e6`

## pseudocode

```c
NTSTATUS __fastcall IopDevObjApplyPostCreationSettings(PVOID Object, __int64 a2)
{
  NTSTATUS result; // eax
  NTSTATUS v5; // ebx
  HANDLE Handle; // [rsp+68h] [rbp+20h] BYREF

  Handle = 0;
  if ( (*(_DWORD *)a2 & 2) == 0 )
    return 0;
  result = SeUtilSecurityInfoFromSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8));
  if ( result >= 0 )
  {
    result = ObOpenObjectByPointer(Object, 0x200u, 0, 0, IoDeviceObjectType, 0, &Handle);
    if ( result >= 0 )
    {
      v5 = ZwSetSecurityObject(Handle, 0, *(PSECURITY_DESCRIPTOR *)(a2 + 8));
      ZwClose(Handle);
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b324  mov     rax, rsp
0x18002b327  mov     [rax+8], rbx
0x18002b32b  push    rsi
0x18002b32c  sub     rsp, 40h
0x18002b330  mov     dword ptr [rax+18h], 0
0x18002b337  mov     rbx, rdx
0x18002b33a  mov     byte ptr [rax+10h], 0
0x18002b33e  mov     rsi, rcx
0x18002b341  mov     qword ptr [rax+20h], 0
0x18002b349  mov     eax, [rdx]
0x18002b34b  test    al, 2
0x18002b34d  jnz     short loc_18002B356
0x18002b34f  xor     eax, eax
0x18002b351  jmp     loc_18002B407
0x18002b356  mov     rcx, [rbx+8]; SecurityDescriptor
0x18002b35a  lea     r8, [rsp+48h+SecurityInformation]
0x18002b35f  lea     rdx, [rsp+48h+arg_8]
0x18002b364  call    SeUtilSecurityInfoFromSecurityDescriptor
0x18002b369  test    eax, eax
0x18002b36b  js      loc_18002B407
0x18002b371  mov     eax, [rsp+48h+SecurityInformation]
0x18002b375  and     al, 3
0x18002b377  neg     al
0x18002b379  lea     rax, [rsp+48h+arg_18]
0x18002b37e  sbb     ecx, ecx
0x18002b380  mov     [rsp+48h+Handle], rax; Handle
0x18002b385  mov     rax, cs:IoDeviceObjectType
0x18002b38c  and     ecx, 80000h
0x18002b392  mov     edx, ecx
0x18002b394  mov     [rsp+48h+AccessMode], 0; AccessMode
0x18002b399  bts     edx, 12h
0x18002b39d  test    byte ptr [rsp+48h+SecurityInformation], 4
0x18002b3a2  cmovz   edx, ecx
0x18002b3a5  mov     rcx, [rax]
0x18002b3a8  mov     r9d, edx
0x18002b3ab  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x18002b3b0  bts     r9d, 18h
0x18002b3b5  mov     rcx, rsi; Object
0x18002b3b8  test    byte ptr [rsp+48h+SecurityInformation], 8
0x18002b3bd  cmovz   r9d, edx; DesiredAccess
0x18002b3c1  xor     r8d, r8d; PassedAccessState
0x18002b3c4  mov     edx, 200h; HandleAttributes
0x18002b3c9  call    cs:__imp_ObOpenObjectByPointer
0x18002b3d0  nop     dword ptr [rax+rax+00h]
0x18002b3d5  test    eax, eax
0x18002b3d7  js      short loc_18002B407
0x18002b3d9  mov     r8, [rbx+8]; SecurityDescriptor
0x18002b3dd  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x18002b3e1  mov     rcx, [rsp+48h+arg_18]; Handle
0x18002b3e6  call    cs:__imp_ZwSetSecurityObject
0x18002b3ed  nop     dword ptr [rax+rax+00h]
0x18002b3f2  mov     rcx, [rsp+48h+arg_18]; Handle
0x18002b3f7  mov     ebx, eax
0x18002b3f9  call    cs:__imp_ZwClose
0x18002b400  nop     dword ptr [rax+rax+00h]
0x18002b405  mov     eax, ebx
0x18002b407  mov     rbx, [rsp+48h+arg_0]
0x18002b40c  add     rsp, 40h
0x18002b410  pop     rsi
0x18002b411  retn
```
