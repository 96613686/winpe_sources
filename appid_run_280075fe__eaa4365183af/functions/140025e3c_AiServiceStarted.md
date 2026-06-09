# AiServiceStarted

- ea: `0x140025e3c`
- end: `0x140025f8a`
- name: `AiServiceStarted`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x140033f50`

## callees

- `0x140025e3c`
- `0x14002b2a0`
- `0x14002b330`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140025f26`
- `ntoskrnl!ObfDereferenceObject` at `0x140025f26`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025f70`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025f70`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025e49`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025e49`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140025e94`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140025e94`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140025f0d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140025f0d`
- `ntoskrnl!PsProcessType` at `0x140025eed`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140025e5e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140025e5e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140025f64`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140025f64`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140025eaa`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140025eaa`

## pseudocode

```c
__int64 __fastcall AiServiceStarted(void *a1)
{
  NTSTATUS v2; // ebx
  HANDLE CurrentProcessId; // rax

  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&AipServiceContext, 0);
  if ( Binding )
  {
    v2 = -1073741811;
  }
  else
  {
    v2 = AiRpcConnect(&Binding);
    if ( v2 >= 0 )
    {
      CurrentProcessId = PsGetCurrentProcessId();
      v2 = PsLookupProcessByProcessId(CurrentProcessId, (PEPROCESS *)&Binding + 1);
      if ( v2 >= 0 )
      {
        v2 = ObOpenObjectByPointer(
               *(&Binding + 1),
               0x200u,
               0,
               0x1FFFFFu,
               (POBJECT_TYPE)PsProcessType,
               0,
               &TargetProcessHandle);
        if ( v2 < 0 )
        {
          ObfDereferenceObject(*(&Binding + 1));
          *(&Binding + 1) = 0;
          AiRpcDisconnect(&Binding);
          Binding = 0;
        }
        *(&TargetProcessHandle + 1) = a1;
      }
      else
      {
        AiRpcDisconnect(&Binding);
        Binding = 0;
      }
    }
  }
  ExReleasePushLockExclusiveEx(&AipServiceContext, 0);
  KeLeaveCriticalRegion();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140025e3c  mov     [rsp+arg_0], rbx
0x140025e41  push    rdi
0x140025e42  sub     rsp, 40h
0x140025e46  mov     rdi, rcx
0x140025e49  call    cs:__imp_KeEnterCriticalRegion
0x140025e50  nop     dword ptr [rax+rax+00h]
0x140025e55  xor     edx, edx
0x140025e57  lea     rcx, AipServiceContext
0x140025e5e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140025e65  nop     dword ptr [rax+rax+00h]
0x140025e6a  cmp     qword ptr cs:Binding, 0
0x140025e72  jz      short loc_140025E7E
0x140025e74  mov     ebx, 0C000000Dh
0x140025e79  jmp     loc_140025F5B
0x140025e7e  lea     rcx, Binding; Binding
0x140025e85  call    AiRpcConnect
0x140025e8a  mov     ebx, eax
0x140025e8c  test    eax, eax
0x140025e8e  js      loc_140025F5B
0x140025e94  call    cs:__imp_PsGetCurrentProcessId
0x140025e9b  nop     dword ptr [rax+rax+00h]
0x140025ea0  mov     rcx, rax; ProcessId
0x140025ea3  lea     rdx, Binding+8; Process
0x140025eaa  call    cs:__imp_PsLookupProcessByProcessId
0x140025eb1  nop     dword ptr [rax+rax+00h]
0x140025eb6  mov     ebx, eax
0x140025eb8  test    eax, eax
0x140025eba  jns     short loc_140025ED8
0x140025ebc  lea     rcx, Binding; Binding
0x140025ec3  call    AiRpcDisconnect
0x140025ec8  mov     qword ptr cs:Binding, 0
0x140025ed3  jmp     loc_140025F5B
0x140025ed8  lea     rax, TargetProcessHandle
0x140025edf  mov     r9d, 1FFFFFh; DesiredAccess
0x140025ee5  mov     [rsp+48h+Handle], rax; Handle
0x140025eea  xor     r8d, r8d; PassedAccessState
0x140025eed  mov     rax, cs:__imp_PsProcessType
0x140025ef4  mov     edx, 200h; HandleAttributes
0x140025ef9  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140025efe  mov     rcx, [rax]
0x140025f01  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x140025f06  mov     rcx, qword ptr cs:Binding+8; Object
0x140025f0d  call    cs:__imp_ObOpenObjectByPointer
0x140025f14  nop     dword ptr [rax+rax+00h]
0x140025f19  mov     ebx, eax
0x140025f1b  test    eax, eax
0x140025f1d  jns     short loc_140025F54
0x140025f1f  mov     rcx, qword ptr cs:Binding+8; Object
0x140025f26  call    cs:__imp_ObfDereferenceObject
0x140025f2d  nop     dword ptr [rax+rax+00h]
0x140025f32  lea     rcx, Binding; Binding
0x140025f39  mov     qword ptr cs:Binding+8, 0
0x140025f44  call    AiRpcDisconnect
0x140025f49  mov     qword ptr cs:Binding, 0
0x140025f54  mov     qword ptr cs:TargetProcessHandle+8, rdi
0x140025f5b  xor     edx, edx
0x140025f5d  lea     rcx, AipServiceContext
0x140025f64  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140025f6b  nop     dword ptr [rax+rax+00h]
0x140025f70  call    cs:__imp_KeLeaveCriticalRegion
0x140025f77  nop     dword ptr [rax+rax+00h]
0x140025f7c  mov     eax, ebx
0x140025f7e  mov     rbx, [rsp+48h+arg_0]
0x140025f83  add     rsp, 40h
0x140025f87  pop     rdi
0x140025f88  retn
```
