# VfsDecodeFileHandle

- ea: `0x14000f058`
- end: `0x14000f11e`
- name: `VfsDecodeFileHandle`
- size: `198`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007f84`
- `0x140008038`
- `0x14000c100`
- `0x14000c1b4`

## callees

- `0x14000f058`
- `0x14000f124`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x14000f072`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000f0ab`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000f0ab`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f0ff`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f0ff`

## pseudocode

```c
char __fastcall VfsDecodeFileHandle(void *a1, KPROCESSOR_MODE a2, int *a3, _QWORD *a4)
{
  char v7; // bl
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rax
  PVOID Object; // [rsp+50h] [rbp+18h] BYREF
  __int64 v12; // [rsp+58h] [rbp+20h] BYREF

  *a3 = 0;
  *a4 = 0;
  Object = 0;
  v12 = 0;
  if ( ObReferenceObjectByHandle(a1, 0, (POBJECT_TYPE)IoFileObjectType, a2, &Object, 0) < 0 )
    return 0;
  v7 = 0;
  if ( VfsDecodeFileObject((__int64)Object, 0, &v12) )
  {
    v8 = v12;
    if ( (*(_DWORD *)(v12 + 4) & 4) != 0 )
    {
      v10 = *(_QWORD *)(v12 + 56);
    }
    else
    {
      v9 = *(_DWORD *)(v12 + 32);
      if ( v9 < 0 )
        *a3 = v9;
      v10 = *(_QWORD *)(v8 + 80);
    }
    *a4 = v10;
    v7 = 1;
  }
  ObfDereferenceObject(Object);
  return v7;
}

```

## disassembly

```asm
0x14000f058  mov     r11, rsp
0x14000f05b  mov     [r11+8], rbx
0x14000f05f  mov     [r11+10h], rsi
0x14000f063  push    rdi
0x14000f064  sub     rsp, 30h
0x14000f068  mov     rdi, r8
0x14000f06b  mov     dword ptr [r8], 0
0x14000f072  mov     r8, cs:__imp_IoFileObjectType
0x14000f079  lea     rax, [r11+18h]
0x14000f07d  mov     rsi, r9
0x14000f080  mov     qword ptr [r9], 0
0x14000f087  mov     r9b, dl; AccessMode
0x14000f08a  mov     qword ptr [r11-10h], 0
0x14000f092  xor     edx, edx; DesiredAccess
0x14000f094  mov     qword ptr [r11+18h], 0
0x14000f09c  mov     r8, [r8]; ObjectType
0x14000f09f  mov     qword ptr [r11+20h], 0
0x14000f0a7  mov     [r11-18h], rax
0x14000f0ab  call    cs:__imp_ObReferenceObjectByHandle
0x14000f0b2  nop     dword ptr [rax+rax+00h]
0x14000f0b7  test    eax, eax
0x14000f0b9  jns     short loc_14000F0BF
0x14000f0bb  xor     al, al
0x14000f0bd  jmp     short loc_14000F10D
0x14000f0bf  mov     rcx, [rsp+38h+Object]
0x14000f0c4  lea     r8, [rsp+38h+arg_18]
0x14000f0c9  xor     edx, edx
0x14000f0cb  xor     bl, bl
0x14000f0cd  call    VfsDecodeFileObject
0x14000f0d2  test    al, al
0x14000f0d4  jz      short loc_14000F0FA
0x14000f0d6  mov     rcx, [rsp+38h+arg_18]
0x14000f0db  mov     eax, [rcx+4]
0x14000f0de  test    al, 4
0x14000f0e0  jnz     short loc_14000F0F1
0x14000f0e2  mov     eax, [rcx+20h]
0x14000f0e5  test    eax, eax
0x14000f0e7  jns     short loc_14000F0EB
0x14000f0e9  mov     [rdi], eax
0x14000f0eb  mov     rax, [rcx+50h]
0x14000f0ef  jmp     short loc_14000F0F5
0x14000f0f1  mov     rax, [rcx+38h]
0x14000f0f5  mov     [rsi], rax
0x14000f0f8  mov     bl, 1
0x14000f0fa  mov     rcx, [rsp+38h+Object]; Object
0x14000f0ff  call    cs:__imp_ObfDereferenceObject
0x14000f106  nop     dword ptr [rax+rax+00h]
0x14000f10b  mov     al, bl
0x14000f10d  mov     rbx, [rsp+38h+arg_0]
0x14000f112  mov     rsi, [rsp+38h+arg_8]
0x14000f117  add     rsp, 30h
0x14000f11b  pop     rdi
0x14000f11c  retn
```
