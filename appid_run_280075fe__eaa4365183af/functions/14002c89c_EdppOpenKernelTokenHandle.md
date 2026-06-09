# EdppOpenKernelTokenHandle

- ea: `0x14002c89c`
- end: `0x14002c93c`
- name: `EdppOpenKernelTokenHandle`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14002c524`
- `0x14002c944`

## callees

- `0x14002c89c`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002c8d7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002c8d7`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c91d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c91d`
- `ntoskrnl!SeTokenObjectType` at `0x14002c8ac`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14002c90c`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14002c90c`

## pseudocode

```c
NTSTATUS __fastcall EdppOpenKernelTokenHandle(void *a1, ACCESS_MASK a2, void **a3)
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
0x14002c89c  mov     r11, rsp
0x14002c89f  mov     [r11+8], rbx
0x14002c8a3  mov     [r11+10h], rsi
0x14002c8a7  push    rdi
0x14002c8a8  sub     rsp, 40h
0x14002c8ac  mov     rax, cs:__imp_SeTokenObjectType
0x14002c8b3  mov     rsi, r8
0x14002c8b6  mov     qword ptr [r11-20h], 0
0x14002c8be  mov     r9b, 1; AccessMode
0x14002c8c1  mov     qword ptr [r11+20h], 0
0x14002c8c9  mov     rbx, [rax]
0x14002c8cc  lea     rax, [r11+20h]
0x14002c8d0  mov     r8, rbx; ObjectType
0x14002c8d3  mov     [r11-28h], rax
0x14002c8d7  call    cs:__imp_ObReferenceObjectByHandle
0x14002c8de  nop     dword ptr [rax+rax+00h]
0x14002c8e3  test    eax, eax
0x14002c8e5  js      short loc_14002C92B
0x14002c8e7  mov     rdi, [rsp+48h+Object]
0x14002c8ec  mov     r9d, 80000000h; DesiredAccess
0x14002c8f2  mov     [rsp+48h+Handle], rsi; Handle
0x14002c8f7  mov     rcx, rdi; Object
0x14002c8fa  mov     [rsp+48h+AccessMode], 0; AccessMode
0x14002c8ff  xor     r8d, r8d; PassedAccessState
0x14002c902  mov     edx, 200h; HandleAttributes
0x14002c907  mov     [rsp+48h+ObjectType], rbx; ObjectType
0x14002c90c  call    cs:__imp_ObOpenObjectByPointer
0x14002c913  nop     dword ptr [rax+rax+00h]
0x14002c918  mov     rcx, rdi; Object
0x14002c91b  mov     ebx, eax
0x14002c91d  call    cs:__imp_ObfDereferenceObject
0x14002c924  nop     dword ptr [rax+rax+00h]
0x14002c929  mov     eax, ebx
0x14002c92b  mov     rbx, [rsp+48h+arg_0]
0x14002c930  mov     rsi, [rsp+48h+arg_8]
0x14002c935  add     rsp, 40h
0x14002c939  pop     rdi
0x14002c93a  retn
```
