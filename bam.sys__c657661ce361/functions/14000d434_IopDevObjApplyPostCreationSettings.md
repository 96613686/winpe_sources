# IopDevObjApplyPostCreationSettings

- ea: `0x14000d434`
- end: `0x14000d523`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000d2a0`

## callees

- `0x14000d434`
- `0x14000e50c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000d509`
- `ntoskrnl!ZwClose` at `0x14000d509`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000d4d9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000d4d9`
- `ntoskrnl!IoDeviceObjectType` at `0x14000d495`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000d4f6`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000d4f6`

## pseudocode

```c
NTSTATUS __fastcall IopDevObjApplyPostCreationSettings(PVOID Object, __int64 a2)
{
  NTSTATUS result; // eax
  int v5; // edx
  ACCESS_MASK v6; // r9d
  NTSTATUS v7; // ebx
  unsigned __int8 v8; // [rsp+58h] [rbp+10h] BYREF
  SECURITY_INFORMATION SecurityInformation; // [rsp+60h] [rbp+18h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp+20h] BYREF

  SecurityInformation = 0;
  v8 = 0;
  Handle = 0;
  if ( (*(_DWORD *)a2 & 2) == 0 )
    return 0;
  result = SeUtilSecurityInfoFromSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8), &v8, &SecurityInformation);
  if ( result >= 0 )
  {
    v5 = ((SecurityInformation & 3) != 0 ? 0x80000 : 0) | 0x40000;
    if ( (SecurityInformation & 4) == 0 )
      v5 = (SecurityInformation & 3) != 0 ? 0x80000 : 0;
    v6 = v5 | 0x1000000;
    if ( (SecurityInformation & 8) == 0 )
      v6 = v5;
    result = ObOpenObjectByPointer(Object, 0x200u, 0, v6, IoDeviceObjectType, 0, &Handle);
    if ( result >= 0 )
    {
      v7 = ZwSetSecurityObject(Handle, SecurityInformation, *(PSECURITY_DESCRIPTOR *)(a2 + 8));
      ZwClose(Handle);
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d434  mov     rax, rsp
0x14000d437  mov     [rax+8], rbx
0x14000d43b  push    rsi
0x14000d43c  sub     rsp, 40h
0x14000d440  mov     dword ptr [rax+18h], 0
0x14000d447  mov     rbx, rdx
0x14000d44a  mov     byte ptr [rax+10h], 0
0x14000d44e  mov     rsi, rcx
0x14000d451  mov     qword ptr [rax+20h], 0
0x14000d459  mov     eax, [rdx]
0x14000d45b  test    al, 2
0x14000d45d  jnz     short loc_14000D466
0x14000d45f  xor     eax, eax
0x14000d461  jmp     loc_14000D517
0x14000d466  mov     rcx, [rbx+8]; SecurityDescriptor
0x14000d46a  lea     r8, [rsp+48h+SecurityInformation]
0x14000d46f  lea     rdx, [rsp+48h+arg_8]
0x14000d474  call    SeUtilSecurityInfoFromSecurityDescriptor
0x14000d479  test    eax, eax
0x14000d47b  js      loc_14000D517
0x14000d481  mov     eax, [rsp+48h+SecurityInformation]
0x14000d485  and     al, 3
0x14000d487  neg     al
0x14000d489  lea     rax, [rsp+48h+arg_18]
0x14000d48e  sbb     ecx, ecx
0x14000d490  mov     [rsp+48h+Handle], rax; Handle
0x14000d495  mov     rax, cs:IoDeviceObjectType
0x14000d49c  and     ecx, 80000h
0x14000d4a2  mov     edx, ecx
0x14000d4a4  mov     [rsp+48h+AccessMode], 0; AccessMode
0x14000d4a9  bts     edx, 12h
0x14000d4ad  test    byte ptr [rsp+48h+SecurityInformation], 4
0x14000d4b2  cmovz   edx, ecx
0x14000d4b5  mov     rcx, [rax]
0x14000d4b8  mov     r9d, edx
0x14000d4bb  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x14000d4c0  bts     r9d, 18h
0x14000d4c5  mov     rcx, rsi; Object
0x14000d4c8  test    byte ptr [rsp+48h+SecurityInformation], 8
0x14000d4cd  cmovz   r9d, edx; DesiredAccess
0x14000d4d1  xor     r8d, r8d; PassedAccessState
0x14000d4d4  mov     edx, 200h; HandleAttributes
0x14000d4d9  call    cs:__imp_ObOpenObjectByPointer
0x14000d4e0  nop     dword ptr [rax+rax+00h]
0x14000d4e5  test    eax, eax
0x14000d4e7  js      short loc_14000D517
0x14000d4e9  mov     r8, [rbx+8]; SecurityDescriptor
0x14000d4ed  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x14000d4f1  mov     rcx, [rsp+48h+arg_18]; Handle
0x14000d4f6  call    cs:__imp_ZwSetSecurityObject
0x14000d4fd  nop     dword ptr [rax+rax+00h]
0x14000d502  mov     rcx, [rsp+48h+arg_18]; Handle
0x14000d507  mov     ebx, eax
0x14000d509  call    cs:__imp_ZwClose
0x14000d510  nop     dword ptr [rax+rax+00h]
0x14000d515  mov     eax, ebx
0x14000d517  mov     rbx, [rsp+48h+arg_0]
0x14000d51c  add     rsp, 40h
0x14000d520  pop     rsi
0x14000d521  retn
```
