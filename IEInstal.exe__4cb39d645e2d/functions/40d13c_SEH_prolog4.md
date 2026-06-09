# __SEH_prolog4

- ea: `0x40d13c`
- end: `0x40d181`
- name: `__SEH_prolog4`
- size: `69`
- prototype: `_DWORD *__cdecl(int, int)`
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x402e60`
- `0x409a59`
- `0x40c8c9`
- `0x40ccf0`
- `0x40ce40`

## pseudocode

```c
_DWORD *__cdecl _SEH_prolog4(int a1, int a2)
{
  void *v4; // esp
  void *v6; // [esp-18h] [ebp-18h]
  _DWORD v7[2]; // [esp-8h] [ebp-8h] BYREF
  _UNKNOWN *retaddr; // [esp+0h] [ebp+0h]
  int v9; // [esp+4h] [ebp+4h]

  v7[1] = _except_handler4;
  v7[0] = NtCurrentTeb()->NtTib.ExceptionList;
  v4 = alloca(a2);
  v9 = -2;
  retaddr = v6;
  return v7;
}

```

## disassembly

```asm
0x40d13c  push    offset __except_handler4
0x40d141  push    large dword ptr fs:0
0x40d148  mov     eax, [esp+8+arg_4]
0x40d14c  mov     [esp+8+arg_4], ebp
0x40d150  lea     ebp, [esp+8+arg_4]
0x40d154  sub     esp, eax
0x40d156  push    ebx
0x40d157  push    esi
0x40d158  push    edi
0x40d159  mov     eax, ___security_cookie
0x40d15e  xor     [ebp-4], eax
0x40d161  xor     eax, ebp
0x40d163  push    eax
0x40d164  mov     [ebp-18h], esp
0x40d167  push    dword ptr [ebp-8]
0x40d16a  mov     eax, [ebp-4]
0x40d16d  mov     dword ptr [ebp-4], 0FFFFFFFEh
0x40d174  mov     [ebp-8], eax
0x40d177  lea     eax, [ebp-10h]
0x40d17a  mov     large fs:0, eax
0x40d180  retn
```
