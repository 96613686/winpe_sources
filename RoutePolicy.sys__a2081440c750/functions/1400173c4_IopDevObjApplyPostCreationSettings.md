# IopDevObjApplyPostCreationSettings

- ea: `0x1400173c4`
- end: `0x1400174b3`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140017230`

## callees

- `0x1400173c4`
- `0x1400184ac`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140017499`
- `ntoskrnl!ZwClose` at `0x140017499`
- `ntoskrnl!ZwSetSecurityObject` at `0x140017486`
- `ntoskrnl!ZwSetSecurityObject` at `0x140017486`
- `ntoskrnl!IoDeviceObjectType` at `0x140017425`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140017469`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140017469`

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
0x1400173c4  mov     rax, rsp
0x1400173c7  mov     [rax+8], rbx
0x1400173cb  push    rsi
0x1400173cc  sub     rsp, 40h
0x1400173d0  mov     dword ptr [rax+18h], 0
0x1400173d7  mov     rbx, rdx
0x1400173da  mov     byte ptr [rax+10h], 0
0x1400173de  mov     rsi, rcx
0x1400173e1  mov     qword ptr [rax+20h], 0
0x1400173e9  mov     eax, [rdx]
0x1400173eb  test    al, 2
0x1400173ed  jnz     short loc_1400173F6
0x1400173ef  xor     eax, eax
0x1400173f1  jmp     loc_1400174A7
0x1400173f6  mov     rcx, [rbx+8]; SecurityDescriptor
0x1400173fa  lea     r8, [rsp+48h+SecurityInformation]
0x1400173ff  lea     rdx, [rsp+48h+arg_8]
0x140017404  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140017409  test    eax, eax
0x14001740b  js      loc_1400174A7
0x140017411  mov     eax, [rsp+48h+SecurityInformation]
0x140017415  and     al, 3
0x140017417  neg     al
0x140017419  lea     rax, [rsp+48h+arg_18]
0x14001741e  sbb     ecx, ecx
0x140017420  mov     [rsp+48h+Handle], rax; Handle
0x140017425  mov     rax, cs:IoDeviceObjectType
0x14001742c  and     ecx, 80000h
0x140017432  mov     edx, ecx
0x140017434  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140017439  bts     edx, 12h
0x14001743d  test    byte ptr [rsp+48h+SecurityInformation], 4
0x140017442  cmovz   edx, ecx
0x140017445  mov     rcx, [rax]
0x140017448  mov     r9d, edx
0x14001744b  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x140017450  bts     r9d, 18h
0x140017455  mov     rcx, rsi; Object
0x140017458  test    byte ptr [rsp+48h+SecurityInformation], 8
0x14001745d  cmovz   r9d, edx; DesiredAccess
0x140017461  xor     r8d, r8d; PassedAccessState
0x140017464  mov     edx, 200h; HandleAttributes
0x140017469  call    cs:__imp_ObOpenObjectByPointer
0x140017470  nop     dword ptr [rax+rax+00h]
0x140017475  test    eax, eax
0x140017477  js      short loc_1400174A7
0x140017479  mov     r8, [rbx+8]; SecurityDescriptor
0x14001747d  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x140017481  mov     rcx, [rsp+48h+arg_18]; Handle
0x140017486  call    cs:__imp_ZwSetSecurityObject
0x14001748d  nop     dword ptr [rax+rax+00h]
0x140017492  mov     rcx, [rsp+48h+arg_18]; Handle
0x140017497  mov     ebx, eax
0x140017499  call    cs:__imp_ZwClose
0x1400174a0  nop     dword ptr [rax+rax+00h]
0x1400174a5  mov     eax, ebx
0x1400174a7  mov     rbx, [rsp+48h+arg_0]
0x1400174ac  add     rsp, 40h
0x1400174b0  pop     rsi
0x1400174b1  retn
```
