# __SEH_prolog4

- ea: `0x40bfc0`
- end: `0x40c005`
- name: `__SEH_prolog4`
- size: `69`
- prototype: `_DWORD *__cdecl(int, int)`
- caller_count: `29`
- callee_count: `0`
- tags: ``

## callers

- `0x40b702`
- `0x40bb18`
- `0x40d4f0`
- `0x40e238`
- `0x40eab4`
- `0x40eb01`
- `0x40ede6`
- `0x40ef40`
- `0x40ef9b`
- `0x40f45f`
- `0x40f660`
- `0x40f6b2`
- `0x40f71d`
- `0x40f772`
- `0x41057c`
- `0x4109f4`
- `0x411024`
- `0x411390`
- `0x411ad9`
- `0x4120e3`
- `0x4121f6`
- `0x4123e9`
- `0x412475`
- `0x413686`
- `0x413f20`
- `0x4141ec`
- `0x41432d`
- `0x414733`
- `0x414c9c`

## pseudocode

```c
_DWORD *__cdecl _SEH_prolog4(int a1, int a2)
{
  void *v4; // esp
  void *v6; // [esp-18h] [ebp-18h]
  _DWORD v7[2]; // [esp-8h] [ebp-8h] BYREF
  _UNKNOWN *retaddr; // [esp+0h] [ebp+0h]
  int v9; // [esp+4h] [ebp+4h]

  v7[1] = SEH_416610;
  v7[0] = NtCurrentTeb()->NtTib.ExceptionList;
  v4 = alloca(a2);
  v9 = -2;
  retaddr = v6;
  return v7;
}

```

## disassembly

```asm
0x40bfc0  push    offset SEH_416610
0x40bfc5  push    large dword ptr fs:0
0x40bfcc  mov     eax, [esp+8+arg_4]
0x40bfd0  mov     [esp+8+arg_4], ebp
0x40bfd4  lea     ebp, [esp+8+arg_4]
0x40bfd8  sub     esp, eax
0x40bfda  push    ebx
0x40bfdb  push    esi
0x40bfdc  push    edi
0x40bfdd  mov     eax, ___security_cookie
0x40bfe2  xor     [ebp-4], eax
0x40bfe5  xor     eax, ebp
0x40bfe7  push    eax
0x40bfe8  mov     [ebp-18h], esp
0x40bfeb  push    dword ptr [ebp-8]
0x40bfee  mov     eax, [ebp-4]
0x40bff1  mov     dword ptr [ebp-4], 0FFFFFFFEh
0x40bff8  mov     [ebp-8], eax
0x40bffb  lea     eax, [ebp-10h]
0x40bffe  mov     large fs:0, eax
0x40c004  retn
```
