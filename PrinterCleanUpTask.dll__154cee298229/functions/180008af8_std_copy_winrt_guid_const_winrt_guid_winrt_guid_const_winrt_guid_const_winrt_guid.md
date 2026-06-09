# std::copy<winrt::guid const *,winrt::guid *>(winrt::guid const *,winrt::guid const *,winrt::guid *)

- ea: `0x180008af8`
- end: `0x180008b28`
- name: `??$copy@PEBUguid@winrt@@PEAU12@@std@@YAPEAUguid@winrt@@PEBU12@0PEAU12@@Z`
- size: `48`
- prototype: `__int64 __fastcall(void *Src, __int64, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000c3b0`

## callees

- `0x180003411`

## pseudocode

```c
__int64 __fastcall std::copy<winrt::guid const *,winrt::guid *>(void *Src, __int64 a2, void *a3)
{
  __int64 v4; // rbx

  v4 = a2 - (_QWORD)Src;
  memmove_0(a3, Src, a2 - (_QWORD)Src);
  return (__int64)a3 + v4;
}

```

## disassembly

```asm
0x180008af8  mov     [rsp+arg_0], rbx
0x180008afd  push    rdi
0x180008afe  sub     rsp, 20h
0x180008b02  mov     rbx, rdx
0x180008b05  mov     rdi, r8
0x180008b08  sub     rbx, rcx
0x180008b0b  mov     rdx, rcx; Src
0x180008b0e  mov     r8, rbx; Size
0x180008b11  mov     rcx, rdi; void *
0x180008b14  call    memmove_0
0x180008b19  lea     rax, [rbx+rdi]
0x180008b1d  mov     rbx, [rsp+28h+arg_0]
0x180008b22  add     rsp, 20h
0x180008b26  pop     rdi
0x180008b27  retn
```
