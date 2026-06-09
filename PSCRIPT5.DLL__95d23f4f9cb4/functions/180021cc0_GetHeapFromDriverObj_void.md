# GetHeapFromDriverObj(void *)

- ea: `0x180021cc0`
- end: `0x180021cf8`
- name: `?GetHeapFromDriverObj@@YAPEAXPEAX@Z`
- size: `56`
- prototype: `void *__fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180021cc0`

## import_xrefs

- `KERNEL32!HeapCreate` at `0x180021ce1`
- `KERNEL32!HeapCreate` at `0x180021ce1`

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
0x180021cc0  push    rbx
0x180021cc2  sub     rsp, 20h
0x180021cc6  mov     rbx, rcx
0x180021cc9  test    rcx, rcx
0x180021ccc  jz      short loc_180021CF0
0x180021cce  mov     rax, [rcx+0E98h]
0x180021cd5  test    rax, rax
0x180021cd8  jnz     short loc_180021CF2
0x180021cda  xor     r8d, r8d; dwMaximumSize
0x180021cdd  xor     edx, edx; dwInitialSize
0x180021cdf  xor     ecx, ecx; flOptions
0x180021ce1  call    cs:__imp_HeapCreate
0x180021ce7  mov     [rbx+0E98h], rax
0x180021cee  jmp     short loc_180021CF2
0x180021cf0  xor     eax, eax
0x180021cf2  add     rsp, 20h
0x180021cf6  pop     rbx
0x180021cf7  retn
```
