# StateRepository::Globals::Registry::Open(Common::RegistryKey &,wchar_t const *,ulong,bool)

- ea: `0x180106008`
- end: `0x18010607e`
- name: `?Open@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WK_N@Z`
- size: `118`
- prototype: `__int64 __fastcall(PHKEY phkResult, struct Common::RegistryKey *, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180103964`

## callees

- `0x1800fb7b4`
- `0x180106008`
- `0x18010968c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180106025`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180106025`

## string_xrefs

- `0x180106054`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180106048`: `OpenSetting: Subkey=%ls`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::Registry::Open(
        PHKEY phkResult,
        struct Common::RegistryKey *a2,
        const wchar_t *a3,
        unsigned int a4)
{
  HKEY v6; // rcx
  int v7; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v6 = *phkResult;
  if ( (unsigned __int64)v6 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v6);
  *phkResult = 0;
  v7 = Common::RegistryKey::Open(phkResult, (HKEY)a2, (const unsigned __int16 *)a2, a4);
  if ( v7 >= 0 )
    return 0;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x69E,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
    (const char *)(unsigned int)v7,
    (int)"OpenSetting: Subkey=%ls",
    (const char *)a2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180106008  mov     [rsp+arg_0], rbx
0x18010600d  push    rdi
0x18010600e  sub     rsp, 30h
0x180106012  mov     rbx, rcx
0x180106015  mov     rdi, rdx
0x180106018  mov     rcx, [rcx]; hKey
0x18010601b  lea     rax, [rcx-1]
0x18010601f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180106023  ja      short loc_18010602B
0x180106025  call    cs:__imp_RegCloseKey
0x18010602b  mov     r8, rdi; unsigned __int16 *
0x18010602e  mov     qword ptr [rbx], 0
0x180106035  mov     rcx, rbx; phkResult
0x180106038  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18010603d  mov     ebx, eax
0x18010603f  test    eax, eax
0x180106041  jns     short loc_180106071
0x180106043  mov     rcx, [rsp+38h]; this
0x180106048  lea     rax, aOpensettingSub; "OpenSetting: Subkey=%ls"
0x18010604f  mov     [rsp+38h+var_10], rdi; char *
0x180106054  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x18010605b  mov     r9d, ebx; char *
0x18010605e  mov     qword ptr [rsp+38h+var_18], rax; int
0x180106063  mov     edx, 69Eh; void *
0x180106068  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18010606d  mov     eax, ebx
0x18010606f  jmp     short loc_180106073
0x180106071  xor     eax, eax
0x180106073  mov     rbx, [rsp+38h+arg_0]
0x180106078  add     rsp, 30h
0x18010607c  pop     rdi
0x18010607d  retn
```
