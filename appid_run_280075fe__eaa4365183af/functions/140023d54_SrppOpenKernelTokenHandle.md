# SrppOpenKernelTokenHandle

- ea: `0x140023d54`
- end: `0x140023df2`
- name: `SrppOpenKernelTokenHandle`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400236ac`

## callees

- `0x140023d54`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140023d88`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140023d88`
- `ntoskrnl!ObfDereferenceObject` at `0x140023dd8`
- `ntoskrnl!ObfDereferenceObject` at `0x140023dd8`
- `ntoskrnl!SeTokenObjectType` at `0x140023d6b`
- `ntoskrnl!SeTokenObjectType` at `0x140023d98`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140023dc7`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140023dc7`

## pseudocode

```c
NTSTATUS __fastcall SrppOpenKernelTokenHandle(void *a1, ACCESS_MASK a2, void **a3)
{
  NTSTATUS result; // eax
  PVOID v5; // rdi
  NTSTATUS v6; // ebx
  PVOID Object; // [rsp+68h] [rbp+20h] BYREF

  Object = 0;
  result = ObReferenceObjectByHandle(a1, a2, (POBJECT_TYPE)SeTokenObjectType, 1, &Object, 0);
  if ( result >= 0 )
  {
    v5 = Object;
    v6 = ObOpenObjectByPointer(Object, 0x200u, 0, 0x80000000, (POBJECT_TYPE)SeTokenObjectType, 0, a3);
    ObfDereferenceObject(v5);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x140023d54  mov     r11, rsp
0x140023d57  mov     [r11+8], rbx
0x140023d5b  push    rdi
0x140023d5c  sub     rsp, 40h
0x140023d60  mov     rbx, r8
0x140023d63  mov     qword ptr [r11-20h], 0
0x140023d6b  mov     r8, cs:__imp_SeTokenObjectType
0x140023d72  lea     rax, [r11+20h]
0x140023d76  mov     r9b, 1; AccessMode
0x140023d79  mov     qword ptr [r11+20h], 0
0x140023d81  mov     [r11-28h], rax
0x140023d85  mov     r8, [r8]; ObjectType
0x140023d88  call    cs:__imp_ObReferenceObjectByHandle
0x140023d8f  nop     dword ptr [rax+rax+00h]
0x140023d94  test    eax, eax
0x140023d96  js      short loc_140023DE6
0x140023d98  mov     rax, cs:__imp_SeTokenObjectType
0x140023d9f  mov     r9d, 80000000h; DesiredAccess
0x140023da5  mov     rdi, [rsp+48h+Object]
0x140023daa  xor     r8d, r8d; PassedAccessState
0x140023dad  mov     [rsp+48h+Handle], rbx; Handle
0x140023db2  mov     rcx, rdi; Object
0x140023db5  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140023dba  mov     rdx, [rax]
0x140023dbd  mov     [rsp+48h+ObjectType], rdx; ObjectType
0x140023dc2  mov     edx, 200h; HandleAttributes
0x140023dc7  call    cs:__imp_ObOpenObjectByPointer
0x140023dce  nop     dword ptr [rax+rax+00h]
0x140023dd3  mov     rcx, rdi; Object
0x140023dd6  mov     ebx, eax
0x140023dd8  call    cs:__imp_ObfDereferenceObject
0x140023ddf  nop     dword ptr [rax+rax+00h]
0x140023de4  mov     eax, ebx
0x140023de6  mov     rbx, [rsp+48h+arg_0]
0x140023deb  add     rsp, 40h
0x140023def  pop     rdi
0x140023df0  retn
```
