# SrpCloseTrackInstallIoctl

- ea: `0x1400232c8`
- end: `0x140023334`
- name: `SrpCloseTrackInstallIoctl`
- size: `108`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140033f50`

## callees

- `0x1400216dc`
- `0x1400232c8`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400232fe`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400232fe`
- `ntoskrnl!ObfDereferenceObject` at `0x14002331f`
- `ntoskrnl!ObfDereferenceObject` at `0x14002331f`
- `ntoskrnl!PsProcessType` at `0x1400232d0`

## pseudocode

```c
__int64 SrpCloseTrackInstallIoctl()
{
  NTSTATUS v0; // ebx
  PVOID Object; // [rsp+40h] [rbp+8h] BYREF

  Object = 0;
  v0 = ObReferenceObjectByHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x1FFFFFu, (POBJECT_TYPE)PsProcessType, 0, &Object, 0);
  if ( v0 >= 0 )
  {
    AiUnreferenceProcOriginList(Object);
    ObfDereferenceObject(Object);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1400232c8  mov     r11, rsp
0x1400232cb  push    rbx
0x1400232cc  sub     rsp, 30h
0x1400232d0  mov     r8, cs:__imp_PsProcessType
0x1400232d7  lea     rax, [r11+8]
0x1400232db  mov     qword ptr [r11-10h], 0
0x1400232e3  xor     r9d, r9d; AccessMode
0x1400232e6  mov     edx, 1FFFFFh; DesiredAccess
0x1400232eb  mov     qword ptr [r11+8], 0
0x1400232f3  or      rcx, 0FFFFFFFFFFFFFFFFh; Handle
0x1400232f7  mov     [r11-18h], rax
0x1400232fb  mov     r8, [r8]; ObjectType
0x1400232fe  call    cs:__imp_ObReferenceObjectByHandle
0x140023305  nop     dword ptr [rax+rax+00h]
0x14002330a  mov     ebx, eax
0x14002330c  test    eax, eax
0x14002330e  js      short loc_14002332B
0x140023310  mov     rcx, [rsp+38h+Object]
0x140023315  call    AiUnreferenceProcOriginList
0x14002331a  mov     rcx, [rsp+38h+Object]; Object
0x14002331f  call    cs:__imp_ObfDereferenceObject
0x140023326  nop     dword ptr [rax+rax+00h]
0x14002332b  mov     eax, ebx
0x14002332d  add     rsp, 30h
0x140023331  pop     rbx
0x140023332  retn
```
