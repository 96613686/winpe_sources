# std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>::~unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>(void)

- ea: `0x180003f84`
- end: `0x180003fad`
- name: `??1?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(Windows::Internal::DialogBlocking::HookMgr **)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000ce42`
- `0x18000ce54`
- `0x18000ce66`

## callees

- `0x180001644`
- `0x180003f84`
- `0x18000899c`

## pseudocode

```c
void __fastcall std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>::~unique_ptr<Windows::Internal::DialogBlocking::HookMgr>(
        Windows::Internal::DialogBlocking::HookMgr **a1)
{
  Windows::Internal::DialogBlocking::HookMgr *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    Windows::Internal::DialogBlocking::HookMgr::~HookMgr(*a1);
    operator delete(v1, 0x28u);
  }
}

```

## disassembly

```asm
0x180003f84  push    rbx
0x180003f86  sub     rsp, 20h
0x180003f8a  mov     rbx, [rcx]
0x180003f8d  test    rbx, rbx
0x180003f90  jz      short loc_180003FA7
0x180003f92  mov     rcx, rbx; this
0x180003f95  call    ??1HookMgr@DialogBlocking@Internal@Windows@@QEAA@XZ; Windows::Internal::DialogBlocking::HookMgr::~HookMgr(void)
0x180003f9a  mov     edx, 28h ; '('; unsigned __int64
0x180003f9f  mov     rcx, rbx; void *
0x180003fa2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003fa7  add     rsp, 20h
0x180003fab  pop     rbx
0x180003fac  retn
```
