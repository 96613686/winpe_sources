# CFileStream::CreateInstance(void *,CFileStream * *)

- ea: `0x180001b60`
- end: `0x180001ba6`
- name: `?CreateInstance@CFileStream@@SAJPEAXPEAPEAV1@@Z`
- size: `70`
- prototype: `__int64 __fastcall(void *, struct CFileStream **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e940`

## callees

- `0x180001b60`
- `0x180001f7c`
- `0x18000e424`

## pseudocode

```c
__int64 __fastcall CFileStream::CreateInstance(void *a1, struct CFileStream **a2)
{
  CFileStream *v4; // rax
  struct CFileStream *v5; // rax

  v4 = (CFileStream *)operator new(0x18u);
  if ( !v4 )
    return 2147942414LL;
  v5 = CFileStream::CFileStream(v4, a1);
  if ( !v5 )
    return 2147942414LL;
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x180001b60  mov     [rsp+arg_0], rbx
0x180001b65  push    rdi
0x180001b66  sub     rsp, 20h
0x180001b6a  mov     rdi, rcx
0x180001b6d  mov     rbx, rdx
0x180001b70  mov     ecx, 18h; Size
0x180001b75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001b7a  test    rax, rax
0x180001b7d  jz      short loc_180001B96
0x180001b7f  mov     rdx, rdi; void *
0x180001b82  mov     rcx, rax; this
0x180001b85  call    ??0CFileStream@@AEAA@PEAX@Z; CFileStream::CFileStream(void *)
0x180001b8a  test    rax, rax
0x180001b8d  jz      short loc_180001B96
0x180001b8f  mov     [rbx], rax
0x180001b92  xor     eax, eax
0x180001b94  jmp     short loc_180001B9B
0x180001b96  mov     eax, 8007000Eh
0x180001b9b  mov     rbx, [rsp+28h+arg_0]
0x180001ba0  add     rsp, 20h
0x180001ba4  pop     rdi
0x180001ba5  retn
```
