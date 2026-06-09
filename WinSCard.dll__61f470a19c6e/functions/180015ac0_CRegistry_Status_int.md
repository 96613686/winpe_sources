# CRegistry::Status(int)

- ea: `0x180015ac0`
- end: `0x180015aea`
- name: `?Status@CRegistry@@QEBAJH@Z`
- size: `42`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, int)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001aae0`
- `0x18001b044`
- `0x18002a528`
- `0x18002aaf8`
- `0x18002ad8c`
- `0x18002b0ec`
- `0x18002b2d8`

## callees

- `0x180015ac0`
- `0x18002ef20`

## pseudocode

```c
__int64 __fastcall CRegistry::Status(CRegistry *this, int a2)
{
  __int64 result; // rax
  ulong pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  result = *((unsigned int *)this + 10);
  if ( (_DWORD)result )
  {
    if ( !a2 )
    {
      pExceptionObject = *((_DWORD *)this + 10);
      throw &pExceptionObject;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015ac0  sub     rsp, 28h
0x180015ac4  mov     eax, [rcx+28h]
0x180015ac7  test    eax, eax
0x180015ac9  jnz     short loc_180015AD0
0x180015acb  add     rsp, 28h
0x180015acf  retn
0x180015ad0  test    edx, edx
0x180015ad2  jnz     short loc_180015ACB
0x180015ad4  lea     rdx, _TI1K; pThrowInfo
0x180015adb  mov     [rsp+28h+pExceptionObject], eax
0x180015adf  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180015ae4  call    _CxxThrowException_0
```
