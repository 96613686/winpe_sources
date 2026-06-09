# IopDevObjApplyPostCreationSettings

- ea: `0x140024924`
- end: `0x140024a13`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `NTSTATUS __fastcall(PVOID Object, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140024790`

## callees

- `0x140024924`
- `0x140025a0c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400249f9`
- `ntoskrnl!ZwClose` at `0x1400249f9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400249c9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400249c9`
- `ntoskrnl!IoDeviceObjectType` at `0x140024985`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400249e6`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400249e6`

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
0x140024924  mov     rax, rsp
0x140024927  mov     [rax+8], rbx
0x14002492b  push    rsi
0x14002492c  sub     rsp, 40h
0x140024930  mov     dword ptr [rax+18h], 0
0x140024937  mov     rbx, rdx
0x14002493a  mov     byte ptr [rax+10h], 0
0x14002493e  mov     rsi, rcx
0x140024941  mov     qword ptr [rax+20h], 0
0x140024949  mov     eax, [rdx]
0x14002494b  test    al, 2
0x14002494d  jnz     short loc_140024956
0x14002494f  xor     eax, eax
0x140024951  jmp     loc_140024A07
0x140024956  mov     rcx, [rbx+8]; SecurityDescriptor
0x14002495a  lea     r8, [rsp+48h+SecurityInformation]
0x14002495f  lea     rdx, [rsp+48h+arg_8]
0x140024964  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140024969  test    eax, eax
0x14002496b  js      loc_140024A07
0x140024971  mov     eax, [rsp+48h+SecurityInformation]
0x140024975  and     al, 3
0x140024977  neg     al
0x140024979  lea     rax, [rsp+48h+arg_18]
0x14002497e  sbb     ecx, ecx
0x140024980  mov     [rsp+48h+Handle], rax; Handle
0x140024985  mov     rax, cs:IoDeviceObjectType
0x14002498c  and     ecx, 80000h
0x140024992  mov     edx, ecx
0x140024994  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140024999  bts     edx, 12h
0x14002499d  test    byte ptr [rsp+48h+SecurityInformation], 4
0x1400249a2  cmovz   edx, ecx
0x1400249a5  mov     rcx, [rax]
0x1400249a8  mov     r9d, edx
0x1400249ab  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x1400249b0  bts     r9d, 18h
0x1400249b5  mov     rcx, rsi; Object
0x1400249b8  test    byte ptr [rsp+48h+SecurityInformation], 8
0x1400249bd  cmovz   r9d, edx; DesiredAccess
0x1400249c1  xor     r8d, r8d; PassedAccessState
0x1400249c4  mov     edx, 200h; HandleAttributes
0x1400249c9  call    cs:__imp_ObOpenObjectByPointer
0x1400249d0  nop     dword ptr [rax+rax+00h]
0x1400249d5  test    eax, eax
0x1400249d7  js      short loc_140024A07
0x1400249d9  mov     r8, [rbx+8]; SecurityDescriptor
0x1400249dd  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x1400249e1  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400249e6  call    cs:__imp_ZwSetSecurityObject
0x1400249ed  nop     dword ptr [rax+rax+00h]
0x1400249f2  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400249f7  mov     ebx, eax
0x1400249f9  call    cs:__imp_ZwClose
0x140024a00  nop     dword ptr [rax+rax+00h]
0x140024a05  mov     eax, ebx
0x140024a07  mov     rbx, [rsp+48h+arg_0]
0x140024a0c  add     rsp, 40h
0x140024a10  pop     rsi
0x140024a11  retn
```
