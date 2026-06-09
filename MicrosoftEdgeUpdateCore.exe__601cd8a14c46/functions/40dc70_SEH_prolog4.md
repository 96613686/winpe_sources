# __SEH_prolog4

- ea: `0x40dc70`
- end: `0x40dcb5`
- name: `__SEH_prolog4`
- size: `69`
- prototype: `_DWORD *__cdecl(int, int)`
- caller_count: `39`
- callee_count: `0`
- tags: ``

## callers

- `0x4068c7`
- `0x406f1e`
- `0x407069`
- `0x40710c`
- `0x4075aa`
- `0x408c16`
- `0x40d3c2`
- `0x40d5c2`
- `0x40e6e0`
- `0x40f240`
- `0x40f37e`
- `0x40fbed`
- `0x40fe5d`
- `0x41061b`
- `0x410687`
- `0x410e77`
- `0x410ed2`
- `0x4114b1`
- `0x411615`
- `0x4136ec`
- `0x41373e`
- `0x4137a9`
- `0x4137fe`
- `0x41439c`
- `0x414814`
- `0x4153b0`
- `0x415511`
- `0x41556d`
- `0x415680`
- `0x415873`
- `0x4158ff`
- `0x415dda`
- `0x416b01`
- `0x4186ab`
- `0x418f45`
- `0x419211`
- `0x4193a1`
- `0x41b301`
- `0x41bf0c`

## pseudocode

```c
_DWORD *__cdecl _SEH_prolog4(int a1, int a2)
{
  void *v4; // esp
  void *v6; // [esp-18h] [ebp-18h]
  _DWORD v7[2]; // [esp-8h] [ebp-8h] BYREF
  _UNKNOWN *retaddr; // [esp+0h] [ebp+0h]
  int v9; // [esp+4h] [ebp+4h]

  v7[1] = SEH_41D8F0;
  v7[0] = NtCurrentTeb()->NtTib.ExceptionList;
  v4 = alloca(a2);
  v9 = -2;
  retaddr = v6;
  return v7;
}

```

## disassembly

```asm
0x40dc70  push    offset SEH_41D8F0
0x40dc75  push    large dword ptr fs:0
0x40dc7c  mov     eax, [esp+8+arg_4]
0x40dc80  mov     [esp+8+arg_4], ebp
0x40dc84  lea     ebp, [esp+8+arg_4]
0x40dc88  sub     esp, eax
0x40dc8a  push    ebx
0x40dc8b  push    esi
0x40dc8c  push    edi
0x40dc8d  mov     eax, ___security_cookie
0x40dc92  xor     [ebp-4], eax
0x40dc95  xor     eax, ebp
0x40dc97  push    eax
0x40dc98  mov     [ebp-18h], esp
0x40dc9b  push    dword ptr [ebp-8]
0x40dc9e  mov     eax, [ebp-4]
0x40dca1  mov     dword ptr [ebp-4], 0FFFFFFFEh
0x40dca8  mov     [ebp-8], eax
0x40dcab  lea     eax, [ebp-10h]
0x40dcae  mov     large fs:0, eax
0x40dcb4  retn
```
