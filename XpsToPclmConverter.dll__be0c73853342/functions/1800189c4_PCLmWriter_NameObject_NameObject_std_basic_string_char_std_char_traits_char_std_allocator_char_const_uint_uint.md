# PCLmWriter::NameObject::NameObject(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,uint,uint)

- ea: `0x1800189c4`
- end: `0x180018a99`
- name: `??0NameObject@PCLmWriter@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@II@Z`
- size: `213`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180010ba0`
- `0x180018640`
- `0x180018fb0`
- `0x180019db0`

## callees

- `0x1800015f0`
- `0x180002154`
- `0x18000f398`
- `0x180010618`
- `0x180018870`
- `0x180018950`
- `0x1800189c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PCLmWriter::NameObject::NameObject(__int64 a1, __int64 a2, int a3, int a4)
{
  __int64 v5; // rdi
  unsigned __int64 v6; // rdx
  __int64 v7; // rax
  int v8; // edx
  _BYTE pExceptionObject[64]; // [rsp+30h] [rbp-58h] BYREF

  *(_DWORD *)(a1 + 8) = a3;
  *(_DWORD *)(a1 + 12) = a4;
  *(_DWORD *)(a1 + 16) = 7;
  *(_QWORD *)a1 = &PCLmWriter::NameObject::`vftable';
  v5 = a1 + 24;
  std::string::string(a1 + 24);
  v6 = *(_QWORD *)(a1 + 40);
  if ( !v6 || *(_BYTE *)std::_String_val<std::_Simple_types<char>>::_Myptr(v5) != 47 )
  {
    PCLmWriter::InvalidObjectException::InvalidObjectException(
      (PCLmWriter::InvalidObjectException *)pExceptionObject,
      v6);
    throw (PCLmWriter::InvalidObjectException *)pExceptionObject;
  }
  if ( v6 > 1 )
  {
    v7 = std::_String_val<std::_Simple_types<char>>::_Myptr(v5);
    if ( std::_Traits_find_ch<std::char_traits<char>>(v7) != -1 )
    {
      PCLmWriter::InvalidObjectException::InvalidObjectException(
        (PCLmWriter::InvalidObjectException *)pExceptionObject,
        v8);
      throw (PCLmWriter::InvalidObjectException *)pExceptionObject;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800189c4  mov     [rsp+arg_10], rbx
0x1800189c9  push    rdi
0x1800189ca  sub     rsp, 80h
0x1800189d1  mov     rax, cs:__security_cookie
0x1800189d8  xor     rax, rsp
0x1800189db  mov     [rsp+88h+var_18], rax
0x1800189e0  mov     rbx, rcx
0x1800189e3  mov     [rsp+88h+var_68], rcx
0x1800189e8  mov     [rcx+8], r8d
0x1800189ec  mov     [rcx+0Ch], r9d
0x1800189f0  mov     dword ptr [rcx+10h], 7
0x1800189f7  lea     rax, ??_7NameObject@PCLmWriter@@6B@; const PCLmWriter::NameObject::`vftable'
0x1800189fe  mov     [rcx], rax
0x180018a01  lea     rdi, [rcx+18h]
0x180018a05  mov     rcx, rdi
0x180018a08  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180018a0d  nop
0x180018a0e  mov     rdx, [rbx+28h]; int
0x180018a12  test    rdx, rdx
0x180018a15  jz      short loc_180018A7D
0x180018a17  mov     rcx, rdi
0x180018a1a  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180018a1f  cmp     byte ptr [rax], 2Fh ; '/'
0x180018a22  jnz     short loc_180018A7D
0x180018a24  cmp     rdx, 1
0x180018a28  jbe     short loc_180018A5C
0x180018a2a  mov     rcx, rdi
0x180018a2d  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180018a32  mov     rcx, rax
0x180018a35  call    ??$_Traits_find_ch@U?$char_traits@D@std@@@std@@YA_KQEBD_K1D@Z; std::_Traits_find_ch<std::char_traits<char>>(char const * const,unsigned __int64,unsigned __int64,char)
0x180018a3a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018a3e  jz      short loc_180018A5C
0x180018a40  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180018a45  call    ??0InvalidObjectException@PCLmWriter@@QEAA@J@Z; PCLmWriter::InvalidObjectException::InvalidObjectException(long)
0x180018a4a  lea     rdx, _TI3?AVInvalidObjectException@PCLmWriter@@; pThrowInfo
0x180018a51  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180018a56  call    _CxxThrowException_0
0x180018a5c  mov     rax, rbx
0x180018a5f  mov     rcx, [rsp+88h+var_18]
0x180018a64  xor     rcx, rsp; StackCookie
0x180018a67  call    __security_check_cookie
0x180018a6c  mov     rbx, [rsp+88h+arg_10]
0x180018a74  add     rsp, 80h
0x180018a7b  pop     rdi
0x180018a7c  retn
0x180018a7d  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180018a82  call    ??0InvalidObjectException@PCLmWriter@@QEAA@J@Z; PCLmWriter::InvalidObjectException::InvalidObjectException(long)
0x180018a87  lea     rdx, _TI3?AVInvalidObjectException@PCLmWriter@@; pThrowInfo
0x180018a8e  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180018a93  call    _CxxThrowException_0
```
