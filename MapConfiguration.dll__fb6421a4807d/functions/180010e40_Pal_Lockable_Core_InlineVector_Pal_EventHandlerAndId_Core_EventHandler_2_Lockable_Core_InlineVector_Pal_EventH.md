# Pal::Lockable<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>>::~Lockable<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>>(void)

- ea: `0x180010e40`
- end: `0x180010e61`
- name: `??1?$Lockable@V?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@$01@Core@@@Pal@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180010d7c`

## callees

- `0x180010de4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010e5a`

## pseudocode

```c
void __fastcall Pal::Lockable<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>>::~Lockable<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>::~InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>(&a1[1]);
  DeleteCriticalSection(a1);
}

```

## disassembly

```asm
0x180010e40  push    rbx
0x180010e42  sub     rsp, 20h
0x180010e46  mov     rbx, rcx
0x180010e49  add     rcx, 28h ; '('
0x180010e4d  call    ??1?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@$01@Core@@QEAA@XZ; Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>::~InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>(void)
0x180010e52  mov     rcx, rbx
0x180010e55  add     rsp, 20h
0x180010e59  pop     rbx
0x180010e5a  jmp     cs:__imp_DeleteCriticalSection
```
