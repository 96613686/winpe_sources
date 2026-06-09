# Pal::CppEvent<>::~CppEvent<>(void)

- ea: `0x180010d7c`
- end: `0x180010daa`
- name: `??1?$CppEvent@$$V@Pal@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(__int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011750`
- `0x18001f968`
- `0x1800239b8`
- `0x18003c507`
- `0x18003f7b9`
- `0x18003f7cf`
- `0x18003f7e8`

## callees

- `0x180010de4`
- `0x180010e40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010da3`

## pseudocode

```c
void __fastcall Pal::CppEvent<>::~CppEvent<>(__int64 a1)
{
  Pal::Lockable<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>>::~Lockable<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>>(a1 + 160);
  Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>::~InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>(a1 + 48);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
}

```

## disassembly

```asm
0x180010d7c  push    rbx
0x180010d7e  sub     rsp, 20h
0x180010d82  mov     rbx, rcx
0x180010d85  add     rcx, 0A0h
0x180010d8c  call    ??1?$Lockable@V?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@$01@Core@@@Pal@@QEAA@XZ; Pal::Lockable<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>>::~Lockable<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>>(void)
0x180010d91  lea     rcx, [rbx+30h]
0x180010d95  call    ??1?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@$01@Core@@QEAA@XZ; Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>::~InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>(void)
0x180010d9a  lea     rcx, [rbx+8]
0x180010d9e  add     rsp, 20h
0x180010da2  pop     rbx
0x180010da3  jmp     cs:__imp_DeleteCriticalSection
```
