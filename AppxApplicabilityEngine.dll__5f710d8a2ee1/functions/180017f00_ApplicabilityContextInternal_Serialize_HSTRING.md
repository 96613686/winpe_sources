# ApplicabilityContextInternal::Serialize(HSTRING__ * *)

- ea: `0x180017f00`
- end: `0x18001808e`
- name: `?Serialize@ApplicabilityContextInternal@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `398`
- prototype: `int(ApplicabilityContextInternal *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180004080`
- `0x180009288`
- `0x18000951c`
- `0x180010c10`
- `0x18001577c`
- `0x180017f00`
- `0x1800227c0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001801f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001801f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ApplicabilityContextInternal::Serialize(ApplicabilityContextInternal *this, HSTRING *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  const WCHAR *v7; // rcx
  HRESULT String; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  int v12; // [rsp+20h] [rbp-78h]
  PCNZWCH sourceString[2]; // [rsp+30h] [rbp-68h] BYREF
  UINT32 length; // [rsp+40h] [rbp-58h]
  unsigned __int64 v15; // [rsp+48h] [rbp-50h]
  _BYTE v16[40]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  std::wstring::wstring(sourceString);
  try
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1));
    std::wstring::append(sourceString, v4, 0, -1);
    std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v16);
    std::wstring::append(sourceString, L",", 1);
    v5 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2), v16);
    std::wstring::append(sourceString, v5, 0, -1);
    std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v16);
    std::wstring::append(sourceString, L",", 1);
    v6 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3), v16);
    std::wstring::append(sourceString, v6, 0, -1);
    std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v16);
    v7 = (const WCHAR *)sourceString;
    if ( v15 >= 8 )
      v7 = sourceString[0];
    String = WindowsCreateString(v7, length, a2);
    v9 = String;
    if ( String >= 0 )
    {
      std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(sourceString);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x133,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\applicabilitycontext.cpp",
        (const char *)(unsigned int)String,
        v12);
      std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(sourceString);
      result = v9;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x137,
                           (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\applicabilitycontext.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180017f00  mov     r11, rsp
0x180017f03  push    rdi
0x180017f04  sub     rsp, 90h
0x180017f0b  mov     qword ptr [r11-70h], 0FFFFFFFFFFFFFFFEh
0x180017f13  mov     [r11+18h], rbx
0x180017f17  mov     [r11+20h], rsi
0x180017f1b  mov     rax, cs:__security_cookie
0x180017f22  xor     rax, rsp
0x180017f25  mov     [rsp+98h+var_18], rax
0x180017f2d  mov     rdi, rdx
0x180017f30  mov     rbx, rcx
0x180017f33  lea     rcx, [r11-68h]
0x180017f37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017f3c  nop
0x180017f3d  mov     rcx, [rbx+8]
0x180017f41  mov     rax, [rcx]
0x180017f44  lea     rdx, [rsp+98h+var_40]
0x180017f49  mov     rax, [rax+20h]
0x180017f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f52  nop
0x180017f53  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180017f57  mov     r9, rsi
0x180017f5a  xor     r8d, r8d
0x180017f5d  mov     rdx, rax
0x180017f60  lea     rcx, [rsp+98h+sourceString]
0x180017f65  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180017f6a  nop
0x180017f6b  lea     rcx, [rsp+98h+var_40]
0x180017f70  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x180017f75  lea     r8d, [rsi+2]
0x180017f79  lea     rdx, asc_18002E714; ","
0x180017f80  lea     rcx, [rsp+98h+sourceString]
0x180017f85  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180017f8a  mov     rcx, [rbx+10h]
0x180017f8e  mov     rax, [rcx]
0x180017f91  lea     rdx, [rsp+98h+var_40]
0x180017f96  mov     rax, [rax+18h]
0x180017f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f9f  nop
0x180017fa0  mov     r9, rsi
0x180017fa3  xor     r8d, r8d
0x180017fa6  mov     rdx, rax
0x180017fa9  lea     rcx, [rsp+98h+sourceString]
0x180017fae  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180017fb3  nop
0x180017fb4  lea     rcx, [rsp+98h+var_40]
0x180017fb9  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x180017fbe  lea     r8d, [rsi+2]
0x180017fc2  lea     rdx, asc_18002E714; ","
0x180017fc9  lea     rcx, [rsp+98h+sourceString]
0x180017fce  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180017fd3  mov     rcx, [rbx+18h]
0x180017fd7  mov     rax, [rcx]
0x180017fda  lea     rdx, [rsp+98h+var_40]
0x180017fdf  mov     rax, [rax+18h]
0x180017fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fe8  nop
0x180017fe9  mov     r9, rsi
0x180017fec  xor     r8d, r8d
0x180017fef  mov     rdx, rax
0x180017ff2  lea     rcx, [rsp+98h+sourceString]
0x180017ff7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180017ffc  nop
0x180017ffd  lea     rcx, [rsp+98h+var_40]
0x180018002  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x180018007  lea     rcx, [rsp+98h+sourceString]
0x18001800c  cmp     [rsp+98h+var_50], 8
0x180018012  cmovnb  rcx, [rsp+98h+sourceString]; sourceString
0x180018018  mov     r8, rdi; string
0x18001801b  mov     edx, [rsp+98h+length]; length
0x18001801f  call    cs:__imp_WindowsCreateString
0x180018025  mov     ebx, eax
0x180018027  test    eax, eax
0x180018029  jns     short loc_180018056
0x18001802b  mov     rcx, [rsp+98h]; this
0x180018033  mov     r9d, eax; char *
0x180018036  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18001803d  mov     edx, 133h; void *
0x180018042  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018047  nop
0x180018048  lea     rcx, [rsp+98h+sourceString]
0x18001804d  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x180018052  mov     eax, ebx
0x180018054  jmp     short loc_180018068
0x180018056  lea     rcx, [rsp+98h+sourceString]
0x18001805b  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x180018060  xor     eax, eax
0x180018062  jmp     short loc_180018068
0x180018064  mov     eax, [rsp+98h+var_78]
0x180018068  mov     rcx, [rsp+98h+var_18]
0x180018070  xor     rcx, rsp; StackCookie
0x180018073  call    __security_check_cookie
0x180018078  lea     r11, [rsp+98h+var_8]
0x180018080  mov     rbx, [r11+20h]
0x180018084  mov     rsi, [r11+28h]
0x180018088  mov     rsp, r11
0x18001808b  pop     rdi
0x18001808c  retn
```
