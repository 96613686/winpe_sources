# IsLicensedComponentAAC_Internal(void)

- ea: `0x180031298`
- end: `0x1800312c7`
- name: `?IsLicensedComponentAAC_Internal@@YAHXZ`
- size: `47`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180030114`
- `0x1800556b0`

## callees

- `0x18002fecc`
- `0x180031298`
- `0x1800312d0`
- `0x18003156c`

## pseudocode

```c
__int64 IsLicensedComponentAAC_Internal(void)
{
  unsigned int v0; // ebx

  if ( (unsigned int)WarbirdDecryptSegment39Inline() )
    return 0;
  v0 = IsLicensedComponentAAC();
  if ( (unsigned int)WarbirdEncryptSegment39Inline() )
    return 0;
  return v0;
}

```

## disassembly

```asm
0x180031298  push    rbx
0x18003129a  sub     rsp, 20h
0x18003129e  call    WarbirdDecryptSegment39Inline
0x1800312a3  test    eax, eax
0x1800312a5  jnz     short loc_1800312BE
0x1800312a7  call    ?IsLicensedComponentAAC@@YAHXZ; IsLicensedComponentAAC(void)
0x1800312ac  mov     ebx, eax
0x1800312ae  call    WarbirdEncryptSegment39Inline
0x1800312b3  xor     ecx, ecx
0x1800312b5  test    eax, eax
0x1800312b7  cmovnz  ebx, ecx
0x1800312ba  mov     eax, ebx
0x1800312bc  jmp     short loc_1800312C0
0x1800312be  xor     eax, eax
0x1800312c0  add     rsp, 20h
0x1800312c4  pop     rbx
0x1800312c5  retn
```
