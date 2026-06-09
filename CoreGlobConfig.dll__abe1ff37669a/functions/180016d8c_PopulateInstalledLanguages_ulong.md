# PopulateInstalledLanguages(ulong)

- ea: `0x180016d8c`
- end: `0x180016e67`
- name: `?PopulateInstalledLanguages@@YAJK@Z`
- size: `219`
- prototype: `__int64 __fastcall(DWORD dwFlags)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1800190bc`
- `0x18001fb70`

## callees

- `0x180008274`
- `0x18000c5e0`
- `0x18000cd24`
- `0x18000fa14`
- `0x180016d8c`
- `0x18001ddf4`

## import_xrefs

- `KERNELBASE!EnumUILanguagesW` at `0x180016ded`
- `KERNELBASE!EnumUILanguagesW` at `0x180016ded`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016e1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016e4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016e1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016e4c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016da7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016da7`

## string_xrefs

- `0x180016dfc`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PopulateInstalledLanguages(DWORD dwFlags)
{
  const char *v3; // r9
  unsigned int LastError; // ebx
  __int64 result; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  LONG_PTR lParam; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  AcquireSRWLockExclusive(&stru_180032FB8);
  if ( qword_180032FA0 != qword_180032FA8 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(qword_180032FA0, qword_180032FA8);
    qword_180032FA8 = qword_180032FA0;
  }
  std::vector<bond::blob>::vector<bond::blob>(&lParam);
  if ( EnumUILanguagesW(EnumUILanguagesProc, dwFlags, (LONG_PTR)&lParam) )
  {
    try
    {
      std::vector<std::wstring>::_Assign_counted_range<std::wstring *>();
      std::vector<std::wstring>::_Tidy(&lParam);
      ReleaseSRWLockExclusive(&stru_180032FB8);
      result = 0;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0xB8, v6, v7);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xB4,
                  (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
                  v3);
    std::vector<std::wstring>::_Tidy(&lParam);
    ReleaseSRWLockExclusive(&stru_180032FB8);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180016d8c  mov     [rsp+arg_0], rbx
0x180016d91  push    rdi
0x180016d92  sub     rsp, 40h
0x180016d96  mov     ebx, ecx
0x180016d98  lea     rdi, stru_180032FB8
0x180016d9f  mov     [rsp+48h+arg_8], rdi
0x180016da4  mov     rcx, rdi; SRWLock
0x180016da7  call    cs:__imp_AcquireSRWLockExclusive
0x180016dad  nop
0x180016dae  mov     rdx, cs:qword_180032FA8
0x180016db5  mov     rcx, cs:qword_180032FA0
0x180016dbc  cmp     rcx, rdx
0x180016dbf  jz      short loc_180016DD4
0x180016dc1  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180016dc6  mov     rax, cs:qword_180032FA0
0x180016dcd  mov     cs:qword_180032FA8, rax
0x180016dd4  lea     rcx, [rsp+48h+lParam]
0x180016dd9  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x180016dde  nop
0x180016ddf  lea     r8, [rsp+48h+lParam]; lParam
0x180016de4  mov     edx, ebx; dwFlags
0x180016de6  lea     rcx, ?EnumUILanguagesProc@@YAHPEAG_J@Z; lpUILanguageEnumProc
0x180016ded  call    cs:__imp_EnumUILanguagesW
0x180016df3  test    eax, eax
0x180016df5  jnz     short loc_180016E27
0x180016df7  mov     rcx, [rsp+48h]; this
0x180016dfc  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180016e03  mov     edx, 0B4h; void *
0x180016e08  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016e0d  mov     ebx, eax
0x180016e0f  lea     rcx, [rsp+48h+lParam]
0x180016e14  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180016e19  nop
0x180016e1a  mov     rcx, rdi; SRWLock
0x180016e1d  call    cs:__imp_ReleaseSRWLockExclusive
0x180016e23  mov     eax, ebx
0x180016e25  jmp     short loc_180016E5B
0x180016e27  mov     rdx, [rsp+48h+lParam]
0x180016e2c  mov     r8, [rsp+48h+var_20]
0x180016e31  sub     r8, rdx
0x180016e34  sar     r8, 5
0x180016e38  call    ??$_Assign_counted_range@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::vector<std::wstring>::_Assign_counted_range<std::wstring *>(std::wstring *,unsigned __int64)
0x180016e3d  nop
0x180016e3e  lea     rcx, [rsp+48h+lParam]
0x180016e43  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180016e48  nop
0x180016e49  mov     rcx, rdi; SRWLock
0x180016e4c  call    cs:__imp_ReleaseSRWLockExclusive
0x180016e52  nop
0x180016e53  xor     eax, eax
0x180016e55  jmp     short loc_180016E5B
0x180016e57  mov     eax, dword ptr [rsp+48h+arg_8]
0x180016e5b  mov     rbx, [rsp+48h+arg_0]
0x180016e60  add     rsp, 40h
0x180016e64  pop     rdi
0x180016e65  retn
```
