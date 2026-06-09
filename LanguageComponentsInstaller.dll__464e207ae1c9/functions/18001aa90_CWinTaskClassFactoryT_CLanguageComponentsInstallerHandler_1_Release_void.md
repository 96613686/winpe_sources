# CWinTaskClassFactoryT<CLanguageComponentsInstallerHandler,1>::Release(void)

- ea: `0x18001aa90`
- end: `0x18001aabf`
- name: `?Release@?$CWinTaskClassFactoryT@VCLanguageComponentsInstallerHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001aa90`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CLanguageComponentsInstallerHandler,1>::Release(volatile signed __int32 *a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(a1 + 2);
  if ( !v1 && a1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
  return v1;
}

```

## disassembly

```asm
0x18001aa90  push    rbx
0x18001aa92  sub     rsp, 20h
0x18001aa96  or      ebx, 0FFFFFFFFh
0x18001aa99  lock xadd [rcx+8], ebx
0x18001aa9e  sub     ebx, 1
0x18001aaa1  jnz     short loc_18001AAB7
0x18001aaa3  test    rcx, rcx
0x18001aaa6  jz      short loc_18001AAB7
0x18001aaa8  mov     rdx, [rcx]
0x18001aaab  mov     rax, [rdx+28h]
0x18001aaaf  lea     edx, [rbx+1]
0x18001aab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aab7  mov     eax, ebx
0x18001aab9  add     rsp, 20h
0x18001aabd  pop     rbx
0x18001aabe  retn
```
