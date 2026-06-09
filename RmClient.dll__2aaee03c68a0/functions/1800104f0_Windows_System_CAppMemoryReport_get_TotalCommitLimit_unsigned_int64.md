# Windows::System::CAppMemoryReport::get_TotalCommitLimit(unsigned __int64 *)

- ea: `0x1800104f0`
- end: `0x1800104fa`
- name: `?get_TotalCommitLimit@CAppMemoryReport@System@Windows@@UEAAJPEA_K@Z`
- size: `10`
- prototype: `__int64 __fastcall(Windows::System::CAppMemoryReport *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall Windows::System::CAppMemoryReport::get_TotalCommitLimit(
        Windows::System::CAppMemoryReport *this,
        unsigned __int64 *a2)
{
  *a2 = *((_QWORD *)this + 9);
  return 0;
}

```

## disassembly

```asm
0x1800104f0  mov     rax, [rcx+48h]
0x1800104f4  mov     [rdx], rax
0x1800104f7  xor     eax, eax
0x1800104f9  retn
```
