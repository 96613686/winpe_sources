# KerbIumClearKey::Status(void)

- ea: `0x140014f38`
- end: `0x140014f55`
- name: `?Status@KerbIumClearKey@@QEBAJXZ`
- size: `29`
- prototype: `__int64 __fastcall(KerbIumClearKey *__hidden this)`
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x140015410`
- `0x140015590`
- `0x140015740`
- `0x1400158c0`
- `0x140015b90`
- `0x140016140`
- `0x140016310`
- `0x140016ac0`
- `0x140017450`
- `0x140017840`
- `0x140017a40`
- `0x140018340`
- `0x1400186e0`
- `0x140018ff0`
- `0x140019210`
- `0x140019890`
- `0x140019a00`
- `0x140019b50`
- `0x140019dd0`
- `0x140019f00`

## callees

- `0x140014f38`

## pseudocode

```c
__int64 __fastcall KerbIumClearKey::Status(KerbIumClearKey *this)
{
  unsigned int v1; // edx
  __int64 result; // rax

  v1 = *((_DWORD *)this + 10);
  result = 3221225485LL;
  if ( v1 + 1073741585 > 1 && v1 != -1073741789 )
    return v1;
  return result;
}

```

## disassembly

```asm
0x140014f38  mov     edx, [rcx+28h]
0x140014f3b  lea     eax, [rdx+3FFFFF11h]
0x140014f41  cmp     eax, 1
0x140014f44  mov     eax, 0C000000Dh
0x140014f49  jbe     short locret_140014F54
0x140014f4b  cmp     edx, 0C0000023h
0x140014f51  cmovnz  eax, edx
0x140014f54  retn
```
