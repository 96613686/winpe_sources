# Windows::System::CAppMemoryReport::get_TotalCommitUsage(unsigned __int64 *)

- ea: `0x180010510`
- end: `0x18001051a`
- name: `?get_TotalCommitUsage@CAppMemoryReport@System@Windows@@UEAAJPEA_K@Z`
- size: `10`
- prototype: `__int64 __fastcall(Windows::System::CAppMemoryReport *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall Windows::System::CAppMemoryReport::get_TotalCommitUsage(
        Windows::System::CAppMemoryReport *this,
        unsigned __int64 *a2)
{
  *a2 = *((_QWORD *)this + 8);
  return 0;
}

```

## disassembly

```asm
0x180010510  mov     rax, [rcx+40h]
0x180010514  mov     [rdx], rax
0x180010517  xor     eax, eax
0x180010519  retn
```
