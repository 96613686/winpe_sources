# Concurrency::details::FreeLibraryAndDestroyThread(ulong)

- ea: `0x18030ff1c`
- end: `0x18030ff54`
- name: `?FreeLibraryAndDestroyThread@details@Concurrency@@YAXK@Z`
- size: `56`
- prototype: `void __fastcall(DWORD dwExitCode, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180312090`
- `0x1803283f0`

## callees

- `0x18030ff1c`
- `0x1803162e8`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x18030ff47`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18030ff47`

## pseudocode

```c
void __fastcall Concurrency::details::FreeLibraryAndDestroyThread(DWORD dwExitCode)
{
  if ( _InterlockedExchangeAdd(&Concurrency::details::LoadLibraryCount, 0xFFFFFFFF) == 1 )
  {
    Concurrency::details::SchedulerBase::CheckOneShotStaticDestruction();
    if ( Concurrency::details::HostModule )
      FreeLibraryAndExitThread(Concurrency::details::HostModule, dwExitCode);
  }
}

```

## disassembly

```asm
0x18030ff1c  push    rbx
0x18030ff1e  sub     rsp, 20h
0x18030ff22  mov     ebx, ecx
0x18030ff24  or      eax, 0FFFFFFFFh
0x18030ff27  lock xadd cs:?LoadLibraryCount@details@Concurrency@@3JC, eax; long volatile Concurrency::details::LoadLibraryCount
0x18030ff2f  cmp     eax, 1
0x18030ff32  jnz     short loc_18030FF4E
0x18030ff34  call    ?CheckOneShotStaticDestruction@SchedulerBase@details@Concurrency@@SAXXZ; Concurrency::details::SchedulerBase::CheckOneShotStaticDestruction(void)
0x18030ff39  mov     rcx, cs:?HostModule@details@Concurrency@@3PEAUHINSTANCE__@@EA; hLibModule
0x18030ff40  test    rcx, rcx
0x18030ff43  jz      short loc_18030FF4E
0x18030ff45  mov     edx, ebx; dwExitCode
0x18030ff47  call    cs:__imp_FreeLibraryAndExitThread
0x18030ff4e  add     rsp, 20h
0x18030ff52  pop     rbx
0x18030ff53  retn
```
