# CMILCOMBase::InternalRelease(void)

- ea: `0x180008c00`
- end: `0x180008c33`
- name: `?InternalRelease@CMILCOMBase@@QEAAKXZ`
- size: `51`
- prototype: `unsigned int __fastcall(CMILCOMBase *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008980`
- `0x180008990`
- `0x180008c50`
- `0x180008f24`
- `0x1800098fc`
- `0x180009e04`
- `0x180014650`
- `0x180014920`
- `0x1800180a0`
- `0x180020204`
- `0x180020620`
- `0x18002be80`
- `0x18002cac0`
- `0x18002dc48`
- `0x18002e5f0`

## callees

- `0x180008c00`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMILCOMBase::InternalRelease(CMILCOMBase *this)
{
  unsigned __int32 v1; // ebx
  __int64 v3; // rax

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 )
  {
    v3 = *(_QWORD *)this;
    --*((_DWORD *)this + 2);
    (*(void (__fastcall **)(CMILCOMBase *, __int64))(v3 + 24))(this, 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180008c00  push    rbx
0x180008c02  sub     rsp, 20h
0x180008c06  mov     ebx, 0FFFFFFFFh
0x180008c0b  lock xadd [rcx+8], ebx
0x180008c10  sub     ebx, 1
0x180008c13  jz      short loc_180008C1D
0x180008c15  mov     eax, ebx
0x180008c17  add     rsp, 20h
0x180008c1b  pop     rbx
0x180008c1c  retn
0x180008c1d  mov     rax, [rcx]
0x180008c20  mov     edx, 1
0x180008c25  dec     dword ptr [rcx+8]
0x180008c28  mov     rax, [rax+18h]
0x180008c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c31  jmp     short loc_180008C15
```
