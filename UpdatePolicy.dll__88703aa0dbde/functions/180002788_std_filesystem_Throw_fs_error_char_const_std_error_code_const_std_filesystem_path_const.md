# std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)

- ea: `0x180002788`
- end: `0x1800027de`
- name: `?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z`
- size: `86`
- prototype: `void __fastcall __noreturn(std::filesystem *__hidden this, const char *, const struct std::error_code *, const struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002bd8`

## callees

- `0x18000226c`
- `0x1800047a0`
- `0x180010f24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180002788  mov     rax, rsp
0x18000278b  push    rbx
0x18000278c  sub     rsp, 0F0h
0x180002793  movaps  xmmword ptr [rax-18h], xmm6
0x180002797  mov     rbx, r8
0x18000279a  movups  xmm6, xmmword ptr [rdx]
0x18000279d  lea     rdx, aExists; "exists"
0x1800027a4  lea     rcx, [rsp+0F8h+var_C8]
0x1800027a9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800027ae  nop
0x1800027af  movdqu  [rsp+0F8h+var_D8], xmm6
0x1800027b5  lea     r9, [rsp+0F8h+var_D8]
0x1800027ba  mov     r8, rbx
0x1800027bd  lea     rdx, [rsp+0F8h+var_C8]
0x1800027c2  lea     rcx, [rsp+0F8h+pExceptionObject]
0x1800027c7  call    ??0filesystem_error@filesystem@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBVpath@12@Verror_code@2@@Z; std::filesystem::filesystem_error::filesystem_error(std::string const &,std::filesystem::path const &,std::error_code)
0x1800027cc  lea     rdx, _TI5?AVfilesystem_error@filesystem@std@@; pThrowInfo
0x1800027d3  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x1800027d8  call    _CxxThrowException
```
