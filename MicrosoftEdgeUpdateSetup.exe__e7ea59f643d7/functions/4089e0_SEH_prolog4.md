# __SEH_prolog4

- ea: `0x4089e0`
- end: `0x408a25`
- name: `__SEH_prolog4`
- size: `69`
- prototype: `_DWORD *__cdecl(int, int)`
- caller_count: `33`
- callee_count: `0`
- tags: ``

## callers

- `0x408282`
- `0x408540`
- `0x408f60`
- `0x40a154`
- `0x40a292`
- `0x40ab0d`
- `0x40ad7d`
- `0x40b89d`
- `0x40b8ea`
- `0x40bbcf`
- `0x40bd35`
- `0x40bd90`
- `0x40c24f`
- `0x40e4d2`
- `0x40e524`
- `0x40e58f`
- `0x40e5e4`
- `0x40f765`
- `0x40fbdd`
- `0x410359`
- `0x4106c0`
- `0x411105`
- `0x41178f`
- `0x4117eb`
- `0x4118fe`
- `0x411af1`
- `0x411b7d`
- `0x413ce6`
- `0x414580`
- `0x41484c`
- `0x41498d`
- `0x4169a1`
- `0x4175ac`

## pseudocode

```c
_DWORD *__cdecl _SEH_prolog4(int a1, int a2)
{
  void *v4; // esp
  void *v6; // [esp-18h] [ebp-18h]
  _DWORD v7[2]; // [esp-8h] [ebp-8h] BYREF
  _UNKNOWN *retaddr; // [esp+0h] [ebp+0h]
  int v9; // [esp+4h] [ebp+4h]

  v7[1] = SEH_419030;
  v7[0] = NtCurrentTeb()->NtTib.ExceptionList;
  v4 = alloca(a2);
  v9 = -2;
  retaddr = v6;
  return v7;
}

```

## disassembly

```asm
0x4089e0  push    offset SEH_419030
0x4089e5  push    large dword ptr fs:0
0x4089ec  mov     eax, [esp+8+arg_4]
0x4089f0  mov     [esp+8+arg_4], ebp
0x4089f4  lea     ebp, [esp+8+arg_4]
0x4089f8  sub     esp, eax
0x4089fa  push    ebx
0x4089fb  push    esi
0x4089fc  push    edi
0x4089fd  mov     eax, ___security_cookie
0x408a02  xor     [ebp-4], eax
0x408a05  xor     eax, ebp
0x408a07  push    eax
0x408a08  mov     [ebp-18h], esp
0x408a0b  push    dword ptr [ebp-8]
0x408a0e  mov     eax, [ebp-4]
0x408a11  mov     dword ptr [ebp-4], 0FFFFFFFEh
0x408a18  mov     [ebp-8], eax
0x408a1b  lea     eax, [ebp-10h]
0x408a1e  mov     large fs:0, eax
0x408a24  retn
```
