# GetHeapFromDriverObj(void *)

- ea: `0x18003c750`
- end: `0x18003c78a`
- name: `?GetHeapFromDriverObj@@YAPEAXPEAX@Z`
- size: `58`
- prototype: `void *__fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003c750`

## import_xrefs

- `KERNEL32!HeapCreate` at `0x18003c777`
- `KERNEL32!HeapCreate` at `0x18003c777`

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
0x18003c750  push    rbx
0x18003c752  sub     rsp, 20h
0x18003c756  mov     rbx, rcx
0x18003c759  test    rcx, rcx
0x18003c75c  jz      short loc_18003C786
0x18003c75e  mov     rax, [rcx+748h]
0x18003c765  test    rax, rax
0x18003c768  jz      short loc_18003C770
0x18003c76a  add     rsp, 20h
0x18003c76e  pop     rbx
0x18003c76f  retn
0x18003c770  xor     r8d, r8d; dwMaximumSize
0x18003c773  xor     edx, edx; dwInitialSize
0x18003c775  xor     ecx, ecx; flOptions
0x18003c777  call    cs:__imp_HeapCreate
0x18003c77d  mov     [rbx+748h], rax
0x18003c784  jmp     short loc_18003C76A
0x18003c786  xor     eax, eax
0x18003c788  jmp     short loc_18003C76A
```
