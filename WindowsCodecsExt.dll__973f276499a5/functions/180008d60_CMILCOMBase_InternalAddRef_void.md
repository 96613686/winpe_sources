# CMILCOMBase::InternalAddRef(void)

- ea: `0x180008d60`
- end: `0x180008d8a`
- name: `?InternalAddRef@CMILCOMBase@@QEAAKXZ`
- size: `42`
- prototype: `unsigned int __fastcall(CMILCOMBase *__hidden this)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008c40`
- `0x180008c50`
- `0x180008f24`
- `0x180009e04`
- `0x180014810`
- `0x180014820`
- `0x1800180a0`
- `0x180020204`
- `0x180020620`
- `0x1800229f0`
- `0x18002be80`
- `0x18002c5f0`
- `0x18002cac0`
- `0x18002e5f0`

## callees

- `0x180008d60`
- `0x18002292c`

## pseudocode

```c
__int64 __fastcall CMILCOMBase::InternalAddRef(
        CMILCOMBase *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  if ( *((int *)this + 2) < 0 )
  {
    PrintAssertionMessageW((const unsigned __int16 *)this, a2, a3, a4);
    __int2c();
  }
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x180008d60  push    rbx
0x180008d62  sub     rsp, 30h
0x180008d66  cmp     dword ptr [rcx+8], 0
0x180008d6a  mov     rbx, rcx
0x180008d6d  jl      short loc_180008D81
0x180008d6f  mov     eax, 1
0x180008d74  lock xadd [rbx+8], eax
0x180008d79  inc     eax
0x180008d7b  add     rsp, 30h
0x180008d7f  pop     rbx
0x180008d80  retn
0x180008d81  call    ?PrintAssertionMessageW@@YAXPEBG000K@Z; PrintAssertionMessageW(ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x180008d86  int     2Ch; Windows NT - assertion failure
0x180008d88  jmp     short loc_180008D6F
```
