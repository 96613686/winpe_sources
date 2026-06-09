# CWinTaskClassFactoryT<CAppListBackupLauncher,1>::Release(void)

- ea: `0x18000b3c0`
- end: `0x18000b3ef`
- name: `?Release@?$CWinTaskClassFactoryT@VCAppListBackupLauncher@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000b3c0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CAppListBackupLauncher,1>::Release(volatile signed __int32 *a1)
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
0x18000b3c0  push    rbx
0x18000b3c2  sub     rsp, 20h
0x18000b3c6  or      ebx, 0FFFFFFFFh
0x18000b3c9  lock xadd [rcx+8], ebx
0x18000b3ce  sub     ebx, 1
0x18000b3d1  jnz     short loc_18000B3E7
0x18000b3d3  test    rcx, rcx
0x18000b3d6  jz      short loc_18000B3E7
0x18000b3d8  mov     rdx, [rcx]
0x18000b3db  mov     rax, [rdx+28h]
0x18000b3df  lea     edx, [rbx+1]
0x18000b3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3e7  mov     eax, ebx
0x18000b3e9  add     rsp, 20h
0x18000b3ed  pop     rbx
0x18000b3ee  retn
```
