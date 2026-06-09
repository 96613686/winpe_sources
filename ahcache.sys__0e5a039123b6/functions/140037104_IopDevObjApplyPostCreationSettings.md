# IopDevObjApplyPostCreationSettings

- ea: `0x140037104`
- end: `0x1400371f3`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140036f70`

## callees

- `0x140037104`
- `0x140038194`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400371a9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400371a9`
- `ntoskrnl!ZwClose` at `0x1400371d9`
- `ntoskrnl!ZwClose` at `0x1400371d9`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400371c6`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400371c6`
- `ntoskrnl!IoDeviceObjectType` at `0x140037165`

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
0x140037104  mov     rax, rsp
0x140037107  mov     [rax+8], rbx
0x14003710b  push    rsi
0x14003710c  sub     rsp, 40h
0x140037110  mov     dword ptr [rax+18h], 0
0x140037117  mov     rbx, rdx
0x14003711a  mov     byte ptr [rax+10h], 0
0x14003711e  mov     rsi, rcx
0x140037121  mov     qword ptr [rax+20h], 0
0x140037129  mov     eax, [rdx]
0x14003712b  test    al, 2
0x14003712d  jnz     short loc_140037136
0x14003712f  xor     eax, eax
0x140037131  jmp     loc_1400371E7
0x140037136  mov     rcx, [rbx+8]; SecurityDescriptor
0x14003713a  lea     r8, [rsp+48h+SecurityInformation]
0x14003713f  lea     rdx, [rsp+48h+arg_8]
0x140037144  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140037149  test    eax, eax
0x14003714b  js      loc_1400371E7
0x140037151  mov     eax, [rsp+48h+SecurityInformation]
0x140037155  and     al, 3
0x140037157  neg     al
0x140037159  lea     rax, [rsp+48h+arg_18]
0x14003715e  sbb     ecx, ecx
0x140037160  mov     [rsp+48h+Handle], rax; Handle
0x140037165  mov     rax, cs:IoDeviceObjectType
0x14003716c  and     ecx, 80000h
0x140037172  mov     edx, ecx
0x140037174  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140037179  bts     edx, 12h
0x14003717d  test    byte ptr [rsp+48h+SecurityInformation], 4
0x140037182  cmovz   edx, ecx
0x140037185  mov     rcx, [rax]
0x140037188  mov     r9d, edx
0x14003718b  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x140037190  bts     r9d, 18h
0x140037195  mov     rcx, rsi; Object
0x140037198  test    byte ptr [rsp+48h+SecurityInformation], 8
0x14003719d  cmovz   r9d, edx; DesiredAccess
0x1400371a1  xor     r8d, r8d; PassedAccessState
0x1400371a4  mov     edx, 200h; HandleAttributes
0x1400371a9  call    cs:__imp_ObOpenObjectByPointer
0x1400371b0  nop     dword ptr [rax+rax+00h]
0x1400371b5  test    eax, eax
0x1400371b7  js      short loc_1400371E7
0x1400371b9  mov     r8, [rbx+8]; SecurityDescriptor
0x1400371bd  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x1400371c1  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400371c6  call    cs:__imp_ZwSetSecurityObject
0x1400371cd  nop     dword ptr [rax+rax+00h]
0x1400371d2  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400371d7  mov     ebx, eax
0x1400371d9  call    cs:__imp_ZwClose
0x1400371e0  nop     dword ptr [rax+rax+00h]
0x1400371e5  mov     eax, ebx
0x1400371e7  mov     rbx, [rsp+48h+arg_0]
0x1400371ec  add     rsp, 40h
0x1400371f0  pop     rsi
0x1400371f1  retn
```
