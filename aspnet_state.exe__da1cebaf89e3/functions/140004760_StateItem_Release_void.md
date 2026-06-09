# StateItem::Release(void)

- ea: `0x140004760`
- end: `0x140004783`
- name: `?Release@StateItem@@QEAAKXZ`
- size: `35`
- prototype: `__int64 __fastcall(StateItem *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140001394`
- `0x140002b60`
- `0x1400033ec`
- `0x140003588`

## callees

- `0x140001104`
- `0x140004760`

## pseudocode

```c
__int64 __fastcall StateItem::Release(StateItem *this)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this);
  if ( !(_DWORD)result )
  {
    BlockMem::Free(this);
    _InterlockedDecrement(&StateItem::s_cStateItems);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140004760  sub     rsp, 28h
0x140004764  or      eax, 0FFFFFFFFh
0x140004767  lock xadd [rcx], eax
0x14000476b  sub     eax, 1
0x14000476e  jnz     short loc_14000477E
0x140004770  call    ?Free@BlockMem@@SAXPEAX@Z; BlockMem::Free(void *)
0x140004775  lock dec cs:?s_cStateItems@StateItem@@0JA; long StateItem::s_cStateItems
0x14000477c  xor     eax, eax
0x14000477e  add     rsp, 28h
0x140004782  retn
```
