# DdcTaskStateHandlerDesktopFactory::LockServer(int)

- ea: `0x1800022f0`
- end: `0x180002303`
- name: `?LockServer@DdcTaskStateHandlerDesktopFactory@@UEAAJH@Z`
- size: `19`
- prototype: `__int64 __fastcall(DdcTaskStateHandlerDesktopFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800022f0`

## pseudocode

```c
__int64 __fastcall DdcTaskStateHandlerDesktopFactory::LockServer(DdcTaskStateHandlerDesktopFactory *this, int a2)
{
  volatile signed __int32 *v2; // rax

  v2 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  if ( a2 )
    _InterlockedIncrement(v2);
  else
    _InterlockedDecrement(v2);
  return 0;
}

```

## disassembly

```asm
0x1800022f0  mov     rax, [rcx+10h]
0x1800022f4  test    edx, edx
0x1800022f6  jz      short loc_1800022FD
0x1800022f8  lock inc dword ptr [rax]
0x1800022fb  jmp     short loc_180002300
0x1800022fd  lock dec dword ptr [rax]
0x180002300  xor     eax, eax
0x180002302  retn
```
