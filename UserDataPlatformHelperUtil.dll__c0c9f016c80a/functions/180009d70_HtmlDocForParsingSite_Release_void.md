# HtmlDocForParsingSite::Release(void)

- ea: `0x180009d70`
- end: `0x180009d9f`
- name: `?Release@HtmlDocForParsingSite@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(HtmlDocForParsingSite *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009db0`
- `0x180009dc0`
- `0x180009dd0`
- `0x180009de0`

## callees

- `0x180009d70`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall HtmlDocForParsingSite::Release(HtmlDocForParsingSite *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 10);
  if ( !v1 && this )
    (*(void (__fastcall **)(HtmlDocForParsingSite *, __int64))(*(_QWORD *)this + 72LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x180009d70  push    rbx
0x180009d72  sub     rsp, 20h
0x180009d76  or      ebx, 0FFFFFFFFh
0x180009d79  lock xadd [rcx+28h], ebx
0x180009d7e  sub     ebx, 1
0x180009d81  jnz     short loc_180009D97
0x180009d83  test    rcx, rcx
0x180009d86  jz      short loc_180009D97
0x180009d88  mov     rdx, [rcx]
0x180009d8b  mov     rax, [rdx+48h]
0x180009d8f  lea     edx, [rbx+1]
0x180009d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d97  mov     eax, ebx
0x180009d99  add     rsp, 20h
0x180009d9d  pop     rbx
0x180009d9e  retn
```
