# IopDevObjApplyPostCreationSettings

- ea: `0x1400aaa54`
- end: `0x1400aab43`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `NTSTATUS __fastcall(PVOID Object, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400aa8c0`

## callees

- `0x1400aaa54`
- `0x1400abb2c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400aab29`
- `ntoskrnl!ZwClose` at `0x1400aab29`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400aab16`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400aab16`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400aaaf9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400aaaf9`
- `ntoskrnl!IoDeviceObjectType` at `0x1400aaab5`

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
0x1400aaa54  mov     rax, rsp
0x1400aaa57  mov     [rax+8], rbx
0x1400aaa5b  push    rsi
0x1400aaa5c  sub     rsp, 40h
0x1400aaa60  mov     dword ptr [rax+18h], 0
0x1400aaa67  mov     rbx, rdx
0x1400aaa6a  mov     byte ptr [rax+10h], 0
0x1400aaa6e  mov     rsi, rcx
0x1400aaa71  mov     qword ptr [rax+20h], 0
0x1400aaa79  mov     eax, [rdx]
0x1400aaa7b  test    al, 2
0x1400aaa7d  jnz     short loc_1400AAA86
0x1400aaa7f  xor     eax, eax
0x1400aaa81  jmp     loc_1400AAB37
0x1400aaa86  mov     rcx, [rbx+8]; SecurityDescriptor
0x1400aaa8a  lea     r8, [rsp+48h+SecurityInformation]
0x1400aaa8f  lea     rdx, [rsp+48h+arg_8]
0x1400aaa94  call    SeUtilSecurityInfoFromSecurityDescriptor
0x1400aaa99  test    eax, eax
0x1400aaa9b  js      loc_1400AAB37
0x1400aaaa1  mov     eax, [rsp+48h+SecurityInformation]
0x1400aaaa5  and     al, 3
0x1400aaaa7  neg     al
0x1400aaaa9  lea     rax, [rsp+48h+arg_18]
0x1400aaaae  sbb     ecx, ecx
0x1400aaab0  mov     [rsp+48h+Handle], rax; Handle
0x1400aaab5  mov     rax, cs:IoDeviceObjectType
0x1400aaabc  and     ecx, 80000h
0x1400aaac2  mov     edx, ecx
0x1400aaac4  mov     [rsp+48h+AccessMode], 0; AccessMode
0x1400aaac9  bts     edx, 12h
0x1400aaacd  test    byte ptr [rsp+48h+SecurityInformation], 4
0x1400aaad2  cmovz   edx, ecx
0x1400aaad5  mov     rcx, [rax]
0x1400aaad8  mov     r9d, edx
0x1400aaadb  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x1400aaae0  bts     r9d, 18h
0x1400aaae5  mov     rcx, rsi; Object
0x1400aaae8  test    byte ptr [rsp+48h+SecurityInformation], 8
0x1400aaaed  cmovz   r9d, edx; DesiredAccess
0x1400aaaf1  xor     r8d, r8d; PassedAccessState
0x1400aaaf4  mov     edx, 200h; HandleAttributes
0x1400aaaf9  call    cs:__imp_ObOpenObjectByPointer
0x1400aab00  nop     dword ptr [rax+rax+00h]
0x1400aab05  test    eax, eax
0x1400aab07  js      short loc_1400AAB37
0x1400aab09  mov     r8, [rbx+8]; SecurityDescriptor
0x1400aab0d  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x1400aab11  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400aab16  call    cs:__imp_ZwSetSecurityObject
0x1400aab1d  nop     dword ptr [rax+rax+00h]
0x1400aab22  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400aab27  mov     ebx, eax
0x1400aab29  call    cs:__imp_ZwClose
0x1400aab30  nop     dword ptr [rax+rax+00h]
0x1400aab35  mov     eax, ebx
0x1400aab37  mov     rbx, [rsp+48h+arg_0]
0x1400aab3c  add     rsp, 40h
0x1400aab40  pop     rsi
0x1400aab41  retn
```
