# std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)

- ea: `0x14000a1d0`
- end: `0x14000a226`
- name: `?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z`
- size: `86`
- prototype: `void __fastcall __noreturn(std::filesystem *__hidden this, const char *, const struct std::error_code *, const struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009390`

## callees

- `0x140002c88`
- `0x140007e8c`
- `0x1400083e4`

## pseudocode

```c
void __fastcall __noreturn std::filesystem::_Throw_fs_error(
        std::filesystem *this,
        const char *a2,
        const struct std::error_code *a3,
        const struct std::filesystem::path *a4)
{
  __int128 v5; // xmm6
  __int128 v6; // [rsp+20h] [rbp-D8h] BYREF
  _BYTE v7[32]; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[168]; // [rsp+50h] [rbp-A8h] BYREF

  v5 = *(_OWORD *)a2;
  std::string::string(v7, "exists", a3, a4);
  v6 = v5;
  std::filesystem::filesystem_error::filesystem_error((__int64)pExceptionObject, (__int64)v7, a3, &v6);
  throw (std::filesystem::filesystem_error *)pExceptionObject;
}

```

## disassembly

```asm
0x14000a1d0  mov     rax, rsp
0x14000a1d3  push    rbx
0x14000a1d4  sub     rsp, 0F0h
0x14000a1db  movaps  xmmword ptr [rax-18h], xmm6
0x14000a1df  mov     rbx, r8
0x14000a1e2  movups  xmm6, xmmword ptr [rdx]
0x14000a1e5  lea     rdx, aExists; "exists"
0x14000a1ec  lea     rcx, [rsp+0F8h+var_C8]
0x14000a1f1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000a1f6  nop
0x14000a1f7  movdqu  [rsp+0F8h+var_D8], xmm6
0x14000a1fd  lea     r9, [rsp+0F8h+var_D8]
0x14000a202  mov     r8, rbx
0x14000a205  lea     rdx, [rsp+0F8h+var_C8]
0x14000a20a  lea     rcx, [rsp+0F8h+pExceptionObject]
0x14000a20f  call    ??0filesystem_error@filesystem@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBVpath@12@Verror_code@2@@Z; std::filesystem::filesystem_error::filesystem_error(std::string const &,std::filesystem::path const &,std::error_code)
0x14000a214  lea     rdx, _TI5?AVfilesystem_error@filesystem@std@@; pThrowInfo
0x14000a21b  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x14000a220  call    _CxxThrowException_0
```
