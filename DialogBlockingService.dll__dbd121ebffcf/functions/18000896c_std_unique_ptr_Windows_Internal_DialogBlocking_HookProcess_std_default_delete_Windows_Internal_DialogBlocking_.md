# std::unique_ptr<Windows::Internal::DialogBlocking::HookProcess,std::default_delete<Windows::Internal::DialogBlocking::HookProcess>>::~unique_ptr<Windows::Internal::DialogBlocking::HookProcess,std::default_delete<Windows::Internal::DialogBlocking::HookProcess>>(void)

- ea: `0x18000896c`
- end: `0x180008995`
- name: `??1?$unique_ptr@VHookProcess@DialogBlocking@Internal@Windows@@U?$default_delete@VHookProcess@DialogBlocking@Internal@Windows@@@std@@@std@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(Windows::Internal::DialogBlocking::HookProcess **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000cd0b`
- `0x18000cd21`

## callees

- `0x180001644`
- `0x18000896c`
- `0x180008a58`

## pseudocode

```c
void __fastcall std::unique_ptr<Windows::Internal::DialogBlocking::HookProcess>::~unique_ptr<Windows::Internal::DialogBlocking::HookProcess>(
        Windows::Internal::DialogBlocking::HookProcess **a1)
{
  Windows::Internal::DialogBlocking::HookProcess *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    Windows::Internal::DialogBlocking::HookProcess::~HookProcess(*a1);
    operator delete(v1, 0x28u);
  }
}

```

## disassembly

```asm
0x18000896c  push    rbx
0x18000896e  sub     rsp, 20h
0x180008972  mov     rbx, [rcx]
0x180008975  test    rbx, rbx
0x180008978  jz      short loc_18000898F
0x18000897a  mov     rcx, rbx; this
0x18000897d  call    ??1HookProcess@DialogBlocking@Internal@Windows@@QEAA@XZ; Windows::Internal::DialogBlocking::HookProcess::~HookProcess(void)
0x180008982  mov     edx, 28h ; '('; unsigned __int64
0x180008987  mov     rcx, rbx; void *
0x18000898a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000898f  add     rsp, 20h
0x180008993  pop     rbx
0x180008994  retn
```
