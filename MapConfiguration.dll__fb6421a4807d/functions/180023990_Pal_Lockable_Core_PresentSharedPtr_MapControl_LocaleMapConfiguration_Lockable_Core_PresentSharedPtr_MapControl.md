# Pal::Lockable<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>::~Lockable<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>(void)

- ea: `0x180023990`
- end: `0x1800239b1`
- name: `??1?$Lockable@V?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@@Pal@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800239b8`
- `0x18003f7a7`

## callees

- `0x180010f34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800239aa`

## pseudocode

```c
void __fastcall Pal::Lockable<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>::~Lockable<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(&a1[1]);
  DeleteCriticalSection(a1);
}

```

## disassembly

```asm
0x180023990  push    rbx
0x180023992  sub     rsp, 20h
0x180023996  mov     rbx, rcx
0x180023999  add     rcx, 28h ; '('
0x18002399d  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x1800239a2  mov     rcx, rbx
0x1800239a5  add     rsp, 20h
0x1800239a9  pop     rbx
0x1800239aa  jmp     cs:__imp_DeleteCriticalSection
```
