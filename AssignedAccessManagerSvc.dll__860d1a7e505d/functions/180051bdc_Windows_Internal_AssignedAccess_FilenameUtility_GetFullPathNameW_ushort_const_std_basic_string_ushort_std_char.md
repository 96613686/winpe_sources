# Windows::Internal::AssignedAccess::FilenameUtility::GetFullPathNameW(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180051bdc`
- end: `0x180051c91`
- name: `?GetFullPathNameW@FilenameUtility@AssignedAccess@Internal@Windows@@AEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180051d8c`

## callees

- `0x18000b694`
- `0x18002074c`
- `0x1800221e0`
- `0x18004b930`
- `0x18004c19c`
- `0x180051bdc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180051bfc`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180051c39`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180051bfc`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180051c39`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AssignedAccess::FilenameUtility::GetFullPathNameW(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3)
{
  DWORD FullPathNameW; // eax
  const char *v6; // r9
  DWORD v7; // ebx
  const char *v9; // r9
  unsigned int LastError; // ebx
  unsigned __int64 v11; // rax
  __int64 v12; // rcx
  LPWSTR lpBuffer[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  FullPathNameW = GetFullPathNameW(a2, 0, 0, 0);
  v7 = FullPathNameW;
  if ( !FullPathNameW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x21,
             (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\filenameutility.cpp",
             v6);
  std::vector<unsigned short>::vector<unsigned short>(lpBuffer, FullPathNameW);
  if ( GetFullPathNameW(a2, v7, lpBuffer[0], 0) )
  {
    v11 = std::_WChar_traits<unsigned short>::length(lpBuffer[0]);
    std::wstring::_Assign<unsigned short>(a3, v12, v11);
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x24,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\filenameutility.cpp",
                  v9);
  }
  std::vector<unsigned short>::_Tidy(lpBuffer);
  return LastError;
}

```

## disassembly

```asm
0x180051bdc  mov     [rsp+arg_0], rbx
0x180051be1  mov     [rsp+arg_8], rsi
0x180051be6  push    rdi
0x180051be7  sub     rsp, 40h
0x180051beb  mov     rsi, r8
0x180051bee  mov     rdi, rdx
0x180051bf1  xor     r9d, r9d; lpFilePart
0x180051bf4  xor     r8d, r8d; lpBuffer
0x180051bf7  xor     edx, edx; nBufferLength
0x180051bf9  mov     rcx, rdi; lpFileName
0x180051bfc  call    cs:__imp_GetFullPathNameW
0x180051c02  mov     ebx, eax
0x180051c04  test    eax, eax
0x180051c06  jnz     short loc_180051C1E
0x180051c08  mov     rcx, [rsp+48h]; this
0x180051c0d  lea     r8, aOnecoreuapBase_89; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180051c14  lea     edx, [rax+21h]; void *
0x180051c17  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180051c1c  jmp     short loc_180051C81
0x180051c1e  mov     rdx, rbx
0x180051c21  lea     rcx, [rsp+48h+lpBuffer]
0x180051c26  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180051c2b  nop
0x180051c2c  xor     r9d, r9d; lpFilePart
0x180051c2f  mov     r8, [rsp+48h+lpBuffer]; lpBuffer
0x180051c34  mov     edx, ebx; nBufferLength
0x180051c36  mov     rcx, rdi; lpFileName
0x180051c39  call    cs:__imp_GetFullPathNameW
0x180051c3f  test    eax, eax
0x180051c41  jnz     short loc_180051C5B
0x180051c43  mov     rcx, [rsp+48h]; this
0x180051c48  lea     r8, aOnecoreuapBase_89; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180051c4f  lea     edx, [rax+24h]; void *
0x180051c52  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180051c57  mov     ebx, eax
0x180051c59  jmp     short loc_180051C75
0x180051c5b  mov     rcx, [rsp+48h+lpBuffer]
0x180051c60  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180051c65  mov     r8, rax
0x180051c68  mov     rdx, rcx
0x180051c6b  mov     rcx, rsi
0x180051c6e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180051c73  xor     ebx, ebx
0x180051c75  lea     rcx, [rsp+48h+lpBuffer]
0x180051c7a  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180051c7f  mov     eax, ebx
0x180051c81  mov     rbx, [rsp+48h+arg_0]
0x180051c86  mov     rsi, [rsp+48h+arg_8]
0x180051c8b  add     rsp, 40h
0x180051c8f  pop     rdi
0x180051c90  retn
```
