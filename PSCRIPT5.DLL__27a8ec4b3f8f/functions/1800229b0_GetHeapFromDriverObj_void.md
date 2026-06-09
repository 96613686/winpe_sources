# GetHeapFromDriverObj(void *)

- ea: `0x1800229b0`
- end: `0x1800229ef`
- name: `?GetHeapFromDriverObj@@YAPEAXPEAX@Z`
- size: `63`
- prototype: `HANDLE __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800229b0`

## import_xrefs

- `KERNEL32!HeapCreate` at `0x1800229d1`
- `KERNEL32!HeapCreate` at `0x1800229d1`

## pseudocode

```c
HANDLE __fastcall GetHeapFromDriverObj(_QWORD *a1)
{
  HANDLE result; // rax

  if ( !a1 )
    return 0;
  result = (HANDLE)a1[467];
  if ( !result )
  {
    result = HeapCreate(0, 0, 0);
    a1[467] = result;
  }
  return result;
}

```

## disassembly

```asm
0x1800229b0  push    rbx
0x1800229b2  sub     rsp, 20h
0x1800229b6  mov     rbx, rcx
0x1800229b9  test    rcx, rcx
0x1800229bc  jz      short loc_1800229E6
0x1800229be  mov     rax, [rcx+0E98h]
0x1800229c5  test    rax, rax
0x1800229c8  jnz     short loc_1800229E8
0x1800229ca  xor     r8d, r8d; dwMaximumSize
0x1800229cd  xor     edx, edx; dwInitialSize
0x1800229cf  xor     ecx, ecx; flOptions
0x1800229d1  call    cs:__imp_HeapCreate
0x1800229d8  nop     dword ptr [rax+rax+00h]
0x1800229dd  mov     [rbx+0E98h], rax
0x1800229e4  jmp     short loc_1800229E8
0x1800229e6  xor     eax, eax
0x1800229e8  add     rsp, 20h
0x1800229ec  pop     rbx
0x1800229ed  retn
```
