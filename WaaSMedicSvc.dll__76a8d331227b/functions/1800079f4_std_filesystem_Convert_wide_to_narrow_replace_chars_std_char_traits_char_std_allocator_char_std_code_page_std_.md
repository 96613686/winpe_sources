# std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort,std::char_traits<ushort>>,std::allocator<char> const &)

- ea: `0x1800079f4`
- end: `0x180007b4c`
- name: `??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z`
- size: `344`
- prototype: `_QWORD *__fastcall(_QWORD *Src, UINT CodePage, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ae6c`

## callees

- `0x18000187c`
- `0x180002f7c`
- `0x1800079f4`
- `0x1800083ac`
- `0x18000b2fc`
- `0x18000b33c`

## pseudocode

```c
_QWORD *__fastcall std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
        _QWORD *Src,
        UINT CodePage,
        __int64 a3)
{
  int v5; // r15d
  const WCHAR *v6; // r12
  __int64 v7; // rbx
  unsigned __int64 v8; // rdx
  _QWORD *v9; // rax
  unsigned __int64 v10; // r14
  _QWORD *v11; // rax
  char *v12; // rdi
  CHAR *v13; // r9
  unsigned __int64 v14; // rax

  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 15;
  *(_BYTE *)Src = 0;
  if ( *(_QWORD *)(a3 + 8) )
  {
    if ( *(_QWORD *)(a3 + 8) > 0x7FFFFFFFu )
      std::_Throw_system_error();
    v5 = *(_DWORD *)(a3 + 8);
    v6 = *(const WCHAR **)a3;
    v7 = _std_fs_convert_wide_to_narrow_replace_chars(CodePage, *(LPCWCH *)a3, v5, 0, 0);
    if ( HIDWORD(v7) )
      ((void (__noreturn *)(void))std::_Throw_system_error_from_std_win_error)();
    v8 = Src[2];
    if ( (int)v7 > v8 )
    {
      v10 = (int)v7 - v8;
      if ( v10 > Src[3] - v8 )
      {
        std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(Src);
      }
      else
      {
        Src[2] = (int)v7;
        if ( Src[3] <= 0xFu )
          v11 = Src;
        else
          v11 = (_QWORD *)*Src;
        v12 = (char *)v11 + v8;
        memset_0((char *)v11 + v8, 0, (int)v7 - v8);
        v12[v10] = 0;
      }
    }
    else
    {
      Src[2] = (int)v7;
      if ( Src[3] <= 0xFu )
        v9 = Src;
      else
        v9 = (_QWORD *)*Src;
      *((_BYTE *)v9 + (int)v7) = 0;
    }
    if ( Src[3] <= 0xFu )
      v13 = (CHAR *)Src;
    else
      v13 = (CHAR *)*Src;
    v14 = (unsigned __int64)_std_fs_convert_wide_to_narrow_replace_chars(CodePage, v6, v5, v13, v7) >> 32;
    if ( (_DWORD)v14 )
      std::_Throw_system_error_from_std_win_error((unsigned int)v14);
  }
  return Src;
}

```

## disassembly

```asm
0x1800079f4  mov     rax, rsp
0x1800079f7  mov     [rax+10h], rbx
0x1800079fb  mov     [rax+18h], rbp
0x1800079ff  mov     [rax+8], rcx
0x180007a03  push    rsi
0x180007a04  push    rdi
0x180007a05  push    r12
0x180007a07  push    r14
0x180007a09  push    r15
0x180007a0b  sub     rsp, 40h
0x180007a0f  mov     ebp, edx
0x180007a11  mov     rsi, rcx
0x180007a14  mov     dword ptr [rax-38h], 0
0x180007a1b  xorps   xmm0, xmm0
0x180007a1e  movups  xmmword ptr [rcx], xmm0
0x180007a21  mov     qword ptr [rcx+10h], 0
0x180007a29  mov     qword ptr [rcx+18h], 0Fh
0x180007a31  mov     byte ptr [rcx], 0
0x180007a34  mov     dword ptr [rax-38h], 1
0x180007a3b  cmp     qword ptr [r8+8], 0
0x180007a40  jz      loc_180007B1C
0x180007a46  cmp     qword ptr [r8+8], 7FFFFFFFh
0x180007a4e  ja      loc_180007B40
0x180007a54  mov     r15d, [r8+8]
0x180007a58  mov     r12, [r8]
0x180007a5b  mov     dword ptr [rax-48h], 0
0x180007a62  xor     r9d, r9d; lpMultiByteStr
0x180007a65  mov     r8d, r15d; cchWideChar
0x180007a68  mov     rdx, r12; lpWideCharStr
0x180007a6b  mov     ecx, ebp; CodePage
0x180007a6d  call    __std_fs_convert_wide_to_narrow_replace_chars
0x180007a72  mov     rbx, rax
0x180007a75  mov     rcx, rax
0x180007a78  shr     rcx, 20h
0x180007a7c  test    ecx, ecx
0x180007a7e  jnz     loc_180007B46
0x180007a84  mov     rdx, [rsi+10h]
0x180007a88  movsxd  rcx, ebx
0x180007a8b  cmp     rcx, rdx
0x180007a8e  ja      short loc_180007AA9
0x180007a90  mov     [rsi+10h], rcx
0x180007a94  cmp     qword ptr [rsi+18h], 0Fh
0x180007a99  jbe     short loc_180007AA0
0x180007a9b  mov     rax, [rsi]
0x180007a9e  jmp     short loc_180007AA3
0x180007aa0  mov     rax, rsi
0x180007aa3  mov     byte ptr [rcx+rax], 0
0x180007aa7  jmp     short loc_180007AF4
0x180007aa9  mov     r14, rcx
0x180007aac  sub     r14, rdx
0x180007aaf  mov     rax, [rsi+18h]
0x180007ab3  sub     rax, rdx
0x180007ab6  cmp     r14, rax
0x180007ab9  ja      short loc_180007AE6
0x180007abb  mov     [rsi+10h], rcx
0x180007abf  cmp     qword ptr [rsi+18h], 0Fh
0x180007ac4  jbe     short loc_180007ACB
0x180007ac6  mov     rax, [rsi]
0x180007ac9  jmp     short loc_180007ACE
0x180007acb  mov     rax, rsi
0x180007ace  lea     rdi, [rdx+rax]
0x180007ad2  mov     r8, r14; Size
0x180007ad5  xor     edx, edx; Val
0x180007ad7  mov     rcx, rdi; void *
0x180007ada  call    memset_0
0x180007adf  mov     byte ptr [r14+rdi], 0
0x180007ae4  jmp     short loc_180007AF4
0x180007ae6  mov     r9, r14
0x180007ae9  mov     rdx, r14
0x180007aec  mov     rcx, rsi; Src
0x180007aef  call    ??$_Reallocate_grow_by@V_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@Z; std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(unsigned __int64,_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char)
0x180007af4  cmp     qword ptr [rsi+18h], 0Fh
0x180007af9  jbe     short loc_180007B00
0x180007afb  mov     r9, [rsi]
0x180007afe  jmp     short loc_180007B03
0x180007b00  mov     r9, rsi; lpMultiByteStr
0x180007b03  mov     [rsp+68h+var_48], ebx; int
0x180007b07  mov     r8d, r15d; cchWideChar
0x180007b0a  mov     rdx, r12; lpWideCharStr
0x180007b0d  mov     ecx, ebp; CodePage
0x180007b0f  call    __std_fs_convert_wide_to_narrow_replace_chars
0x180007b14  shr     rax, 20h
0x180007b18  test    eax, eax
0x180007b1a  jnz     short loc_180007B38
0x180007b1c  mov     rax, rsi
0x180007b1f  lea     r11, [rsp+68h+var_28]
0x180007b24  mov     rbx, [r11+38h]
0x180007b28  mov     rbp, [r11+40h]
0x180007b2c  mov     rsp, r11
0x180007b2f  pop     r15
0x180007b31  pop     r14
0x180007b33  pop     r12
0x180007b35  pop     rdi
0x180007b36  pop     rsi
0x180007b37  retn
0x180007b38  mov     ecx, eax
0x180007b3a  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
0x180007b40  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x180007b46  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
```
