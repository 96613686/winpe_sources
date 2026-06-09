# Pal::Lockable<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>::get(void)

- ea: `0x180023a0c`
- end: `0x180023a45`
- name: `?get@?$Lockable@V?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@@Pal@@QEBA?AV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@XZ`
- size: `57`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002149c`
- `0x180021694`
- `0x1800238fc`
- `0x1800239b8`
- `0x180023a4c`
- `0x180023a88`
- `0x180031b04`
- `0x180032574`
- `0x180032634`
- `0x1800334b0`

## callees

- `0x18000cb24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023a1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023a1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023a31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023a31`

## pseudocode

```c
_QWORD *__fastcall Pal::Lockable<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>::get(
        LPCRITICAL_SECTION lpCriticalSection,
        _QWORD *a2)
{
  EnterCriticalSection(lpCriticalSection);
  std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(
    a2,
    &lpCriticalSection[1].DebugInfo);
  LeaveCriticalSection(lpCriticalSection);
  return a2;
}

```

## disassembly

```asm
0x180023a0c  mov     [rsp+arg_0], rbx
0x180023a11  push    rdi
0x180023a12  sub     rsp, 20h
0x180023a16  mov     rdi, rdx
0x180023a19  mov     rbx, rcx
0x180023a1c  call    cs:__imp_EnterCriticalSection
0x180023a22  lea     rdx, [rbx+28h]
0x180023a26  mov     rcx, rdi
0x180023a29  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x180023a2e  mov     rcx, rbx; lpCriticalSection
0x180023a31  call    cs:__imp_LeaveCriticalSection
0x180023a37  mov     rbx, [rsp+28h+arg_0]
0x180023a3c  mov     rax, rdi
0x180023a3f  add     rsp, 20h
0x180023a43  pop     rdi
0x180023a44  retn
```
