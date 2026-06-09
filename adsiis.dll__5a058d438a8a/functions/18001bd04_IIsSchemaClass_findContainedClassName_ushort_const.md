# IIsSchemaClass::findContainedClassName(ushort const *)

- ea: `0x18001bd04`
- end: `0x18001bd8b`
- name: `?findContainedClassName@IIsSchemaClass@@QEAAJPEBG@Z`
- size: `135`
- prototype: `int(IIsSchemaClass *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180007e04`

## callees

- `0x18001bd04`
- `0x18001be58`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001bd55`
- `msvcrt!_wcsicmp` at `0x18001bd55`

## pseudocode

```c
int __fastcall IIsSchemaClass::findContainedClassName(
        IIsSchemaClass *this,
        const unsigned __int16 *a2,
        unsigned __int64 a3)
{
  unsigned __int16 *v3; // rbx
  int result; // eax
  wchar_t String1[264]; // [rsp+20h] [rbp-228h] BYREF

  v3 = (unsigned __int16 *)*((_QWORD *)this + 9);
  while ( 1 )
  {
    v3 = grabProp(String1, v3, a3);
    if ( !v3 )
      break;
    if ( String1[0] )
    {
      result = _wcsicmp(String1, a2);
      if ( !result )
        return result;
    }
  }
  return -2147463153;
}

```

## disassembly

```asm
0x18001bd04  mov     [rsp+arg_10], rbx
0x18001bd09  mov     [rsp+arg_18], rsi
0x18001bd0e  push    rdi
0x18001bd0f  sub     rsp, 240h
0x18001bd16  mov     rax, cs:__security_cookie
0x18001bd1d  xor     rax, rsp
0x18001bd20  mov     [rsp+248h+var_18], rax
0x18001bd28  mov     rbx, [rcx+48h]
0x18001bd2c  mov     rdi, rdx
0x18001bd2f  xor     esi, esi
0x18001bd31  mov     rdx, rbx; unsigned __int16 *
0x18001bd34  lea     rcx, [rsp+248h+String1]; unsigned __int16 *
0x18001bd39  call    ?grabProp@@YAPEAGPEAG0_K@Z; grabProp(ushort *,ushort *,unsigned __int64)
0x18001bd3e  mov     rbx, rax
0x18001bd41  test    rax, rax
0x18001bd44  jz      short loc_18001BD61
0x18001bd46  cmp     [rsp+248h+String1], si
0x18001bd4b  jz      short loc_18001BD31
0x18001bd4d  mov     rdx, rdi; String2
0x18001bd50  lea     rcx, [rsp+248h+String1]; String1
0x18001bd55  call    cs:__imp__wcsicmp
0x18001bd5b  test    eax, eax
0x18001bd5d  jnz     short loc_18001BD31
0x18001bd5f  jmp     short loc_18001BD66
0x18001bd61  mov     eax, 8000500Fh
0x18001bd66  mov     rcx, [rsp+248h+var_18]
0x18001bd6e  xor     rcx, rsp; StackCookie
0x18001bd71  call    __security_check_cookie
0x18001bd76  lea     r11, [rsp+248h+var_8]
0x18001bd7e  mov     rbx, [r11+20h]
0x18001bd82  mov     rsi, [r11+28h]
0x18001bd86  mov     rsp, r11
0x18001bd89  pop     rdi
0x18001bd8a  retn
```
