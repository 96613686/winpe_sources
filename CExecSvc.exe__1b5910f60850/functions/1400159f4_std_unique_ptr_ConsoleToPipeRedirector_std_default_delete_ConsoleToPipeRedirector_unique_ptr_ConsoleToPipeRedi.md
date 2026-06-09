# std::unique_ptr<ConsoleToPipeRedirector,std::default_delete<ConsoleToPipeRedirector>>::~unique_ptr<ConsoleToPipeRedirector,std::default_delete<ConsoleToPipeRedirector>>(void)

- ea: `0x1400159f4`
- end: `0x140015a1d`
- name: `??1?$unique_ptr@VConsoleToPipeRedirector@@U?$default_delete@VConsoleToPipeRedirector@@@std@@@std@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(ConsoleToPipeRedirector **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140022ef0`

## callees

- `0x1400026b8`
- `0x1400159f4`
- `0x14001b8ac`

## pseudocode

```c
void __fastcall std::unique_ptr<ConsoleToPipeRedirector>::~unique_ptr<ConsoleToPipeRedirector>(
        ConsoleToPipeRedirector **a1)
{
  ConsoleToPipeRedirector *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    ConsoleToPipeRedirector::~ConsoleToPipeRedirector(*a1);
    operator delete(v1, 0x180u);
  }
}

```

## disassembly

```asm
0x1400159f4  push    rbx
0x1400159f6  sub     rsp, 20h
0x1400159fa  mov     rbx, [rcx]
0x1400159fd  test    rbx, rbx
0x140015a00  jz      short loc_140015A17
0x140015a02  mov     rcx, rbx; this
0x140015a05  call    ??1ConsoleToPipeRedirector@@QEAA@XZ; ConsoleToPipeRedirector::~ConsoleToPipeRedirector(void)
0x140015a0a  mov     edx, 180h; unsigned __int64
0x140015a0f  mov     rcx, rbx; void *
0x140015a12  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140015a17  add     rsp, 20h
0x140015a1b  pop     rbx
0x140015a1c  retn
```
