# xml_exception::xml_exception(long)

- ea: `0x1400119d4`
- end: `0x140011a4d`
- name: `??0xml_exception@@QEAA@J@Z`
- size: `121`
- prototype: `xml_exception *__fastcall(xml_exception *__hidden this, int)`
- caller_count: `11`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140011c40`
- `0x140011d68`
- `0x140011fa0`
- `0x1400121d8`
- `0x140012278`
- `0x140012764`
- `0x140012950`
- `0x140012a74`
- `0x140012b94`
- `0x1400130ec`
- `0x140013548`

## callees

- `0x140008368`
- `0x1400099b4`
- `0x140009d04`
- `0x140013b10`

## pseudocode

```c
xml_exception *__fastcall xml_exception::xml_exception(xml_exception *this, int a2)
{
  __int64 v4; // rdx
  _BYTE v6[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v6);
  Sharp::Util::standard_exception::standard_exception(this, a2, (__int64)v6);
  LOBYTE(v4) = 1;
  std::wstring::_Tidy(v6, v4, 0);
  *(_QWORD *)this = &xml_exception::`vftable';
  return this;
}

```

## disassembly

```asm
0x1400119d4  mov     [rsp+arg_8], rbx
0x1400119d9  push    rdi
0x1400119da  sub     rsp, 60h
0x1400119de  mov     rax, cs:__security_cookie
0x1400119e5  xor     rax, rsp
0x1400119e8  mov     [rsp+68h+var_18], rax
0x1400119ed  mov     ebx, edx
0x1400119ef  mov     rdi, rcx
0x1400119f2  mov     [rsp+68h+var_48], rcx
0x1400119f7  lea     rdx, dword_140018714
0x1400119fe  lea     rcx, [rsp+68h+var_38]
0x140011a03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140011a08  nop
0x140011a09  lea     r8, [rsp+68h+var_38]
0x140011a0e  mov     edx, ebx
0x140011a10  mov     rcx, rdi
0x140011a13  call    ??0standard_exception@Util@Sharp@@QEAA@JAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::standard_exception::standard_exception(long,std::wstring const &)
0x140011a18  nop
0x140011a19  xor     r8d, r8d
0x140011a1c  mov     dl, 1
0x140011a1e  lea     rcx, [rsp+68h+var_38]
0x140011a23  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140011a28  lea     rax, ??_7xml_exception@@6B@; const xml_exception::`vftable'
0x140011a2f  mov     [rdi], rax
0x140011a32  mov     rax, rdi
0x140011a35  mov     rcx, [rsp+68h+var_18]
0x140011a3a  xor     rcx, rsp; StackCookie
0x140011a3d  call    __security_check_cookie
0x140011a42  mov     rbx, [rsp+68h+arg_8]
0x140011a47  add     rsp, 60h
0x140011a4b  pop     rdi
0x140011a4c  retn
```
