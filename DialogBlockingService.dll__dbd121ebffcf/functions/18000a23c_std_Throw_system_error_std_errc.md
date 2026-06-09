# std::_Throw_system_error(std::errc)

- ea: `0x18000a23c`
- end: `0x18000a276`
- name: `?_Throw_system_error@std@@YAXW4errc@1@@Z`
- size: `58`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800099d8`
- `0x18000a538`
- `0x18000a65c`

## callees

- `0x1800020dc`
- `0x180009824`
- `0x18000a9c8`

## pseudocode

```c
void __fastcall __noreturn std::_Throw_system_error(unsigned int a1)
{
  __int128 v1; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v2[16]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+40h] [rbp-38h] BYREF

  v1 = *(_OWORD *)std::make_error_code(v2, a1);
  std::system_error::system_error(pExceptionObject, &v1);
  throw (std::system_error *)pExceptionObject;
}

```

## disassembly

```asm
0x18000a23c  sub     rsp, 78h
0x18000a240  mov     edx, ecx
0x18000a242  lea     rcx, [rsp+78h+var_48]
0x18000a247  call    ?make_error_code@std@@YA?AVerror_code@1@W4errc@1@@Z; std::make_error_code(std::errc)
0x18000a24c  lea     rdx, [rsp+78h+var_58]
0x18000a251  lea     rcx, [rsp+78h+pExceptionObject]
0x18000a256  movups  xmm0, xmmword ptr [rax]
0x18000a259  movdqu  [rsp+78h+var_58], xmm0
0x18000a25f  call    ??0system_error@std@@QEAA@Verror_code@1@@Z; std::system_error::system_error(std::error_code)
0x18000a264  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18000a26b  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000a270  call    _CxxThrowException_0
```
