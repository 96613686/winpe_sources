# Windows::System::CAppMemoryReport::get_PeakPrivateCommitUsage(unsigned __int64 *)

- ea: `0x180011570`
- end: `0x18001157a`
- name: `?get_PeakPrivateCommitUsage@CAppMemoryReport@System@Windows@@UEAAJPEA_K@Z`
- size: `10`
- prototype: `__int64 __fastcall(Windows::System::CAppMemoryReport *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall Windows::System::CAppMemoryReport::get_PeakPrivateCommitUsage(
        Windows::System::CAppMemoryReport *this,
        unsigned __int64 *a2)
{
  *a2 = *((_QWORD *)this + 7);
  return 0;
}

```

## disassembly

```asm
0x180011570  mov     rax, [rcx+38h]
0x180011574  mov     [rdx], rax
0x180011577  xor     eax, eax
0x180011579  retn
```
