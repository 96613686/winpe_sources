# ICMModule::GetColorDirectoryW(ushort const *,ushort *,ulong *)

- ea: `0x18002ae30`
- end: `0x18002ae6f`
- name: `?GetColorDirectoryW@ICMModule@@SAHPEBGPEAGPEAK@Z`
- size: `63`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002a940`
- `0x18002aae0`

## callees

- `0x180007410`
- `0x18002ae30`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall ICMModule::GetColorDirectoryW(const unsigned __int16 *a1, unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int v6; // ebx

  v6 = 0;
  if ( ICMModule::EnsureLoaded() )
    return (unsigned int)((__int64 (__fastcall *)(const unsigned __int16 *, unsigned __int16 *, unsigned int *))ICMModule::s_pfnGetColorDirectoryW)(
                           a1,
                           a2,
                           a3);
  return v6;
}

```

## disassembly

```asm
0x18002ae30  push    rbx
0x18002ae32  push    rbp
0x18002ae33  push    rsi
0x18002ae34  push    rdi
0x18002ae35  sub     rsp, 28h
0x18002ae39  mov     rdi, r8
0x18002ae3c  mov     rsi, rdx
0x18002ae3f  mov     rbp, rcx
0x18002ae42  xor     ebx, ebx
0x18002ae44  call    ?EnsureLoaded@ICMModule@@SAHXZ; ICMModule::EnsureLoaded(void)
0x18002ae49  test    eax, eax
0x18002ae4b  jz      short loc_18002AE64
0x18002ae4d  mov     rax, cs:?s_pfnGetColorDirectoryW@ICMModule@@0P6AHPEBGPEAGPEAK@ZEA; int (*ICMModule::s_pfnGetColorDirectoryW)(ushort const *,ushort *,ulong *)
0x18002ae54  mov     r8, rdi
0x18002ae57  mov     rdx, rsi
0x18002ae5a  mov     rcx, rbp
0x18002ae5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae62  mov     ebx, eax
0x18002ae64  mov     eax, ebx
0x18002ae66  add     rsp, 28h
0x18002ae6a  pop     rdi
0x18002ae6b  pop     rsi
0x18002ae6c  pop     rbp
0x18002ae6d  pop     rbx
0x18002ae6e  retn
```
