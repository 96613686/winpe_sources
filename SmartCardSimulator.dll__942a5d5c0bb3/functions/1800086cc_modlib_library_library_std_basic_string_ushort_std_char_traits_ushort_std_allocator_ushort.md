# modlib::library::library(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800086cc`
- end: `0x18000876c`
- name: `??0library@modlib@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180008080`

## callees

- `0x180003590`
- `0x180008018`
- `0x1800086cc`
- `0x18000879c`
- `0x18000a960`
- `0x180058700`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180008712`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180008712`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
const WCHAR *__fastcall modlib::library::library(const WCHAR *lpLibFileName, __int64 a2)
{
  const WCHAR *v4; // rcx
  HMODULE LibraryW; // rax
  __int64 v6; // rdx
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v9; // [rsp+40h] [rbp-18h]

  v9 = a2;
  std::wstring::wstring(lpLibFileName, a2);
  *((_QWORD *)lpLibFileName + 5) = 0;
  if ( *((_QWORD *)lpLibFileName + 3) < 8u )
    v4 = lpLibFileName;
  else
    v4 = *(const WCHAR **)lpLibFileName;
  LibraryW = LoadLibraryW(v4);
  *((_QWORD *)lpLibFileName + 5) = LibraryW;
  if ( !LibraryW )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "module failed to load");
    throw (std::runtime_error *)pExceptionObject;
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(a2, v6, 0);
  return lpLibFileName;
}

```

## disassembly

```asm
0x1800086cc  mov     [rsp+arg_10], rbx
0x1800086d1  push    rdi
0x1800086d2  sub     rsp, 50h
0x1800086d6  mov     rax, cs:__security_cookie
0x1800086dd  xor     rax, rsp
0x1800086e0  mov     [rsp+58h+var_10], rax
0x1800086e5  mov     rdi, rdx
0x1800086e8  mov     rbx, rcx
0x1800086eb  mov     [rsp+58h+var_38], rcx
0x1800086f0  mov     [rsp+58h+var_18], rdx
0x1800086f5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800086fa  nop
0x1800086fb  mov     qword ptr [rbx+28h], 0
0x180008703  cmp     qword ptr [rbx+18h], 8
0x180008708  jb      short loc_18000870F
0x18000870a  mov     rcx, [rbx]
0x18000870d  jmp     short loc_180008712
0x18000870f  mov     rcx, rbx; lpLibFileName
0x180008712  call    cs:__imp_LoadLibraryW
0x180008718  mov     [rbx+28h], rax
0x18000871c  test    rax, rax
0x18000871f  jnz     short loc_180008744
0x180008721  lea     rdx, aModuleFailedTo; "module failed to load"
0x180008728  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18000872d  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180008732  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180008739  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000873e  call    _CxxThrowException_0
0x180008744  xor     r8d, r8d
0x180008747  mov     dl, 1
0x180008749  mov     rcx, rdi
0x18000874c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180008751  mov     rax, rbx
0x180008754  mov     rcx, [rsp+58h+var_10]
0x180008759  xor     rcx, rsp; StackCookie
0x18000875c  call    __security_check_cookie
0x180008761  mov     rbx, [rsp+58h+arg_10]
0x180008766  add     rsp, 50h
0x18000876a  pop     rdi
0x18000876b  retn
```
