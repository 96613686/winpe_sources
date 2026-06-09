# GetSystemPaths(void)

- ea: `0x14001d480`
- end: `0x14001d629`
- name: `?GetSystemPaths@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `425`
- prototype: `__int128 *()`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001ce88`

## callees

- `0x140002310`
- `0x1400073c4`
- `0x14000894c`
- `0x14000e828`
- `0x14001d480`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14001d4f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14001d4f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14001d55c`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14001d55c`

## string_xrefs

- `0x14001d5fd`: `onecore\vm\compute\service\cexec\lib\pathhandling.cpp`
- `0x14001d617`: `onecore\vm\compute\service\cexec\lib\pathhandling.cpp`

## pseudocode

```c
__int128 *GetSystemPaths()
{
  const char *v0; // r9
  __int64 v1; // rdx
  __int128 *v2; // rcx
  const char *v3; // r9
  __int64 v4; // rdx
  __int128 *v5; // rcx
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  xmmword_14003A700 = 0;
  qword_14003A710 = 0;
  qword_14003A718 = 7;
  LOWORD(xmmword_14003A700) = 0;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\pathhandling.cpp",
      v0);
  std::wstring::operator+=(&xmmword_14003A700, Buffer);
  v1 = qword_14003A710;
  v2 = &xmmword_14003A700;
  if ( qword_14003A710 >= (unsigned __int64)qword_14003A718 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&xmmword_14003A700);
  }
  else
  {
    ++qword_14003A710;
    if ( (unsigned __int64)qword_14003A718 > 7 )
      v2 = (__int128 *)xmmword_14003A700;
    *(_DWORD *)((char *)v2 + 2 * v1) = 59;
  }
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\pathhandling.cpp",
      v3);
  std::wstring::operator+=(&xmmword_14003A700, Buffer);
  std::wstring::operator+=(&xmmword_14003A700, L"\\System;");
  std::wstring::operator+=(&xmmword_14003A700, Buffer);
  v4 = qword_14003A710;
  v5 = &xmmword_14003A700;
  if ( qword_14003A710 >= (unsigned __int64)qword_14003A718 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&xmmword_14003A700);
  }
  else
  {
    ++qword_14003A710;
    if ( (unsigned __int64)qword_14003A718 > 7 )
      v5 = (__int128 *)xmmword_14003A700;
    *(_DWORD *)((char *)v5 + 2 * v4) = 59;
  }
  return &xmmword_14003A700;
}

```

## disassembly

```asm
0x14001d480  mov     [rsp+arg_0], rbx
0x14001d485  push    rdi
0x14001d486  sub     rsp, 250h
0x14001d48d  mov     rax, cs:__security_cookie
0x14001d494  xor     rax, rsp
0x14001d497  mov     [rsp+258h+var_18], rax
0x14001d49f  mov     rax, [rsp+258h+var_230]
0x14001d4a4  mov     [rsp+258h+var_230], rax
0x14001d4a9  mov     [rsp+258h+var_238], 0
0x14001d4b1  lea     rdi, xmmword_14003A700
0x14001d4b8  mov     [rsp+258h+var_230], rdi
0x14001d4bd  xorps   xmm0, xmm0
0x14001d4c0  movups  cs:xmmword_14003A700, xmm0
0x14001d4c7  mov     cs:qword_14003A710, 0
0x14001d4d2  mov     cs:qword_14003A718, 7
0x14001d4dd  xor     eax, eax
0x14001d4df  mov     word ptr cs:xmmword_14003A700, ax
0x14001d4e6  mov     [rsp+258h+var_238], 1
0x14001d4ee  mov     edx, 104h; uSize
0x14001d4f3  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x14001d4f8  call    cs:__imp_GetSystemDirectoryW
0x14001d4fe  test    eax, eax
0x14001d500  jz      loc_14001D60F
0x14001d506  lea     rdx, [rsp+258h+Buffer]; void *
0x14001d50b  mov     rcx, rdi; Src
0x14001d50e  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x14001d513  mov     rdx, cs:qword_14003A710
0x14001d51a  mov     r8, cs:qword_14003A718
0x14001d521  mov     rcx, rdi; Src
0x14001d524  mov     ebx, 3Bh ; ';'
0x14001d529  cmp     rdx, r8
0x14001d52c  jnb     short loc_14001D54A
0x14001d52e  lea     rax, [rdx+1]
0x14001d532  mov     cs:qword_14003A710, rax
0x14001d539  cmp     r8, 7
0x14001d53d  cmova   rcx, qword ptr cs:xmmword_14003A700
0x14001d545  mov     [rcx+rdx*2], ebx
0x14001d548  jmp     short loc_14001D552
0x14001d54a  mov     r9d, ebx
0x14001d54d  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001d552  mov     edx, 104h; uSize
0x14001d557  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x14001d55c  call    cs:__imp_GetWindowsDirectoryW
0x14001d562  test    eax, eax
0x14001d564  jz      loc_14001D5F5
0x14001d56a  lea     rdx, [rsp+258h+Buffer]; void *
0x14001d56f  mov     rcx, rdi; Src
0x14001d572  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x14001d577  lea     rdx, aSystem; "\\System;"
0x14001d57e  mov     rcx, rdi; Src
0x14001d581  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x14001d586  lea     rdx, [rsp+258h+Buffer]; void *
0x14001d58b  mov     rcx, rdi; Src
0x14001d58e  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x14001d593  mov     rdx, cs:qword_14003A710
0x14001d59a  mov     r8, cs:qword_14003A718
0x14001d5a1  mov     rcx, rdi; Src
0x14001d5a4  cmp     rdx, r8
0x14001d5a7  jnb     short loc_14001D5C9
0x14001d5a9  lea     rax, [rdx+1]
0x14001d5ad  mov     cs:qword_14003A710, rax
0x14001d5b4  cmp     r8, 7
0x14001d5b8  cmova   rcx, qword ptr cs:xmmword_14003A700
0x14001d5c0  mov     dword ptr [rcx+rdx*2], 3Bh ; ';'
0x14001d5c7  jmp     short loc_14001D5D1
0x14001d5c9  mov     r9d, ebx
0x14001d5cc  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14001d5d1  mov     rax, rdi
0x14001d5d4  mov     rcx, [rsp+258h+var_18]
0x14001d5dc  xor     rcx, rsp; StackCookie
0x14001d5df  call    __security_check_cookie
0x14001d5e4  mov     rbx, [rsp+258h+arg_0]
0x14001d5ec  add     rsp, 250h
0x14001d5f3  pop     rdi
0x14001d5f4  retn
0x14001d5f5  mov     rcx, [rsp+258h]; this
0x14001d5fd  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14001d604  mov     edx, 23h ; '#'; void *
0x14001d609  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14001d60f  mov     rcx, [rsp+258h]; this
0x14001d617  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14001d61e  mov     edx, 1Fh; void *
0x14001d623  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
