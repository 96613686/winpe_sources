# CommonUtil::CFlatEnumFiles::GetCurrentDir(void)

- ea: `0x140011e40`
- end: `0x140011e45`
- name: `?GetCurrentDir@CFlatEnumFiles@CommonUtil@@UEBAPEBGXZ`
- size: `5`
- prototype: `const unsigned __int16 *__fastcall(CommonUtil::CFlatEnumFiles *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
const unsigned __int16 *__fastcall CommonUtil::CFlatEnumFiles::GetCurrentDir(CommonUtil::CFlatEnumFiles *this)
{
  return (const unsigned __int16 *)*((_QWORD *)this + 3);
}

```

## disassembly

```asm
0x140011e40  mov     rax, [rcx+18h]
0x140011e44  retn
```
