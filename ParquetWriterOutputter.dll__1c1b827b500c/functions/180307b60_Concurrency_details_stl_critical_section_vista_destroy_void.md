# Concurrency::details::stl_critical_section_vista::destroy(void)

- ea: `0x180307b60`
- end: `0x180307b6b`
- name: `?destroy@stl_critical_section_vista@details@Concurrency@@UEAAXXZ`
- size: `11`
- prototype: `void __fastcall(Concurrency::details::stl_critical_section_vista *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180307b64`

## pseudocode

```c
void __fastcall Concurrency::details::stl_critical_section_vista::destroy(
        Concurrency::details::stl_critical_section_vista *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180307b60  add     rcx, 8
0x180307b64  jmp     cs:__imp_DeleteCriticalSection
```
