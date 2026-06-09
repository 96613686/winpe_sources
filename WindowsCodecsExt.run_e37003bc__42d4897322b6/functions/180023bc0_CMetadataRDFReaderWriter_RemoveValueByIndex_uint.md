# CMetadataRDFReaderWriter::RemoveValueByIndex(uint)

- ea: `0x180023bc0`
- end: `0x180023c0a`
- name: `?RemoveValueByIndex@CMetadataRDFReaderWriter@@UEAAJI@Z`
- size: `74`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::RemoveValueByIndex(CMetadataRDFReaderWriter *this, unsigned int a2)
{
  unsigned int v4; // ebx
  char *v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = (char *)this + 40;
  CMTALock::Enter((CMetadataRDFReaderWriter *)((char *)this + 40));
  v4 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, _QWORD))(*(_QWORD *)this + 200LL))(this, a2);
  CGuard<CMTALock>::~CGuard<CMTALock>(&v6);
  return v4;
}

```

## disassembly

```asm
0x180023bc0  mov     [rsp+arg_8], rbx
0x180023bc5  push    rdi
0x180023bc6  sub     rsp, 20h
0x180023bca  mov     rdi, rcx
0x180023bcd  mov     ebx, edx
0x180023bcf  add     rcx, 28h ; '('; this
0x180023bd3  mov     [rsp+28h+arg_0], rcx
0x180023bd8  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180023bdd  mov     rax, [rdi]
0x180023be0  mov     edx, ebx
0x180023be2  mov     rcx, rdi
0x180023be5  mov     rax, [rax+0C8h]
0x180023bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bf1  lea     rcx, [rsp+28h+arg_0]
0x180023bf6  mov     ebx, eax
0x180023bf8  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x180023bfd  mov     eax, ebx
0x180023bff  mov     rbx, [rsp+28h+arg_8]
0x180023c04  add     rsp, 20h
0x180023c08  pop     rdi
0x180023c09  retn
```
