# AppHostNavigatorException::SetCannotComparePositionOfDifferentTypesException(void)

- ea: `0x18000fbe8`
- end: `0x18000fc23`
- name: `?SetCannotComparePositionOfDifferentTypesException@AppHostNavigatorException@@SAJXZ`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002700`
- `0x180004980`
- `0x180005f10`
- `0x180006bd0`
- `0x180009160`

## callees

- `0x18000fc2c`
- `0x18001277c`
- `0x180012ed4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppHostNavigatorException::SetCannotComparePositionOfDifferentTypesException(HINSTANCE a1)
{
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  LoadResourceString(a1, 0x68u, (struct String *)&v2);
  AppHostNavigatorException::SetException((struct String *)&v2);
  String::Reset((String *)&v2);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000fbe8  sub     rsp, 28h
0x18000fbec  mov     [rsp+28h+arg_0], 0
0x18000fbf5  lea     r8, [rsp+28h+arg_0]; struct String *
0x18000fbfa  mov     edx, 68h ; 'h'; unsigned int
0x18000fbff  call    ?LoadResourceString@@YAJPEAUHINSTANCE__@@IAEAVString@@@Z; LoadResourceString(HINSTANCE__ *,uint,String &)
0x18000fc04  lea     rcx, [rsp+28h+arg_0]; struct String *
0x18000fc09  call    ?SetException@AppHostNavigatorException@@CAJAEAVString@@@Z; AppHostNavigatorException::SetException(String &)
0x18000fc0e  nop
0x18000fc0f  lea     rcx, [rsp+28h+arg_0]; this
0x18000fc14  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000fc19  mov     eax, 80070057h
0x18000fc1e  add     rsp, 28h
0x18000fc22  retn
```
