# GetHeapFromDriverObj(void *)

- ea: `0x18003d4a0`
- end: `0x18003d4e1`
- name: `?GetHeapFromDriverObj@@YAPEAXPEAX@Z`
- size: `65`
- prototype: `HANDLE __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003d4a0`

## import_xrefs

- `KERNEL32!HeapCreate` at `0x18003d4c8`
- `KERNEL32!HeapCreate` at `0x18003d4c8`

## pseudocode

```c
HANDLE __fastcall GetHeapFromDriverObj(_QWORD *a1)
{
  HANDLE result; // rax

  if ( !a1 )
    return 0;
  result = (HANDLE)a1[233];
  if ( !result )
  {
    result = HeapCreate(0, 0, 0);
    a1[233] = result;
  }
  return result;
}

```

## disassembly

```asm
0x18003d4a0  push    rbx
0x18003d4a2  sub     rsp, 20h
0x18003d4a6  mov     rbx, rcx
0x18003d4a9  test    rcx, rcx
0x18003d4ac  jz      short loc_18003D4DD
0x18003d4ae  mov     rax, [rcx+748h]
0x18003d4b5  test    rax, rax
0x18003d4b8  jz      short loc_18003D4C1
0x18003d4ba  add     rsp, 20h
0x18003d4be  pop     rbx
0x18003d4bf  retn
0x18003d4c1  xor     r8d, r8d; dwMaximumSize
0x18003d4c4  xor     edx, edx; dwInitialSize
0x18003d4c6  xor     ecx, ecx; flOptions
0x18003d4c8  call    cs:__imp_HeapCreate
0x18003d4cf  nop     dword ptr [rax+rax+00h]
0x18003d4d4  mov     [rbx+748h], rax
0x18003d4db  jmp     short loc_18003D4BA
0x18003d4dd  xor     eax, eax
0x18003d4df  jmp     short loc_18003D4BA
```
