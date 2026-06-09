# std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::allocator<char> const &)

- ea: `0x180004168`
- end: `0x1800042bc`
- name: `??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@D@1@@Z`
- size: `340`
- prototype: `__int64 __fastcall(void *Src, UINT CodePage)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180002358`

## callees

- `0x1800018d8`
- `0x180001c5c`
- `0x180004168`
- `0x1800053d4`
- `0x18000dd94`
- `0x1800154b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  unsigned __int64 v10; // rbp
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
        v11 = Src;
        if ( Src[3] > 0xFu )
          v11 = (_QWORD *)*Src;
        v12 = (char *)v11 + v8;
        memset((char *)v11 + v8, 0, (int)v7 - v8);
        v12[v10] = 0;
      }
    }
    else
    {
      Src[2] = (int)v7;
      v9 = Src;
      if ( Src[3] > 0xFu )
        v9 = (_QWORD *)*Src;
      *((_BYTE *)v9 + (int)v7) = 0;
    }
    v13 = (CHAR *)Src;
    if ( Src[3] > 0xFu )
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
0x180004168  mov     rax, rsp
0x18000416b  mov     [rax+10h], rbx
0x18000416f  mov     [rax+18h], rbp
0x180004173  mov     [rax+8], rcx
0x180004177  push    rsi
0x180004178  push    rdi
0x180004179  push    r12
0x18000417b  push    r14
0x18000417d  push    r15
0x18000417f  sub     rsp, 40h
0x180004183  mov     r14d, edx
0x180004186  mov     rsi, rcx
0x180004189  mov     dword ptr [rax-38h], 0
0x180004190  xorps   xmm0, xmm0
0x180004193  movups  xmmword ptr [rcx], xmm0
0x180004196  mov     qword ptr [rcx+10h], 0
0x18000419e  mov     qword ptr [rcx+18h], 0Fh
0x1800041a6  mov     byte ptr [rcx], 0
0x1800041a9  mov     dword ptr [rax-38h], 1
0x1800041b0  cmp     qword ptr [r8+8], 0
0x1800041b5  jz      loc_18000428C
0x1800041bb  cmp     qword ptr [r8+8], 7FFFFFFFh
0x1800041c3  ja      loc_1800042B0
0x1800041c9  mov     r15d, [r8+8]
0x1800041cd  mov     r12, [r8]
0x1800041d0  mov     dword ptr [rax-48h], 0
0x1800041d7  xor     r9d, r9d; lpMultiByteStr
0x1800041da  mov     r8d, r15d; cchWideChar
0x1800041dd  mov     rdx, r12; lpWideCharStr
0x1800041e0  mov     ecx, r14d; CodePage
0x1800041e3  call    __std_fs_convert_wide_to_narrow_replace_chars
0x1800041e8  mov     rbx, rax
0x1800041eb  mov     rcx, rax
0x1800041ee  shr     rcx, 20h
0x1800041f2  test    ecx, ecx
0x1800041f4  jnz     loc_1800042B6
0x1800041fa  mov     rdx, [rsi+10h]
0x1800041fe  movsxd  rcx, ebx
0x180004201  cmp     rcx, rdx
0x180004204  ja      short loc_18000421D
0x180004206  mov     [rsi+10h], rcx
0x18000420a  mov     rax, rsi
0x18000420d  cmp     qword ptr [rsi+18h], 0Fh
0x180004212  jbe     short loc_180004217
0x180004214  mov     rax, [rsi]
0x180004217  mov     byte ptr [rcx+rax], 0
0x18000421b  jmp     short loc_180004265
0x18000421d  mov     rbp, rcx
0x180004220  sub     rbp, rdx
0x180004223  mov     rax, [rsi+18h]
0x180004227  sub     rax, rdx
0x18000422a  cmp     rbp, rax
0x18000422d  ja      short loc_180004257
0x18000422f  mov     [rsi+10h], rcx
0x180004233  mov     rax, rsi
0x180004236  cmp     qword ptr [rsi+18h], 0Fh
0x18000423b  jbe     short loc_180004240
0x18000423d  mov     rax, [rsi]
0x180004240  lea     rdi, [rax+rdx]
0x180004244  mov     r8, rbp; Size
0x180004247  xor     edx, edx; Val
0x180004249  mov     rcx, rdi; void *
0x18000424c  call    memset
0x180004251  mov     byte ptr [rdi+rbp], 0
0x180004255  jmp     short loc_180004265
0x180004257  mov     r9, rbp
0x18000425a  mov     rdx, rbp
0x18000425d  mov     rcx, rsi; Src
0x180004260  call    ??$_Reallocate_grow_by@V_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@Z; std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(unsigned __int64,_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char)
0x180004265  mov     r9, rsi
0x180004268  cmp     qword ptr [rsi+18h], 0Fh
0x18000426d  jbe     short loc_180004272
0x18000426f  mov     r9, [rsi]; lpMultiByteStr
0x180004272  mov     [rsp+68h+var_48], ebx; int
0x180004276  mov     r8d, r15d; cchWideChar
0x180004279  mov     rdx, r12; lpWideCharStr
0x18000427c  mov     ecx, r14d; CodePage
0x18000427f  call    __std_fs_convert_wide_to_narrow_replace_chars
0x180004284  shr     rax, 20h
0x180004288  test    eax, eax
0x18000428a  jnz     short loc_1800042A8
0x18000428c  mov     rax, rsi
0x18000428f  lea     r11, [rsp+68h+var_28]
0x180004294  mov     rbx, [r11+38h]
0x180004298  mov     rbp, [r11+40h]
0x18000429c  mov     rsp, r11
0x18000429f  pop     r15
0x1800042a1  pop     r14
0x1800042a3  pop     r12
0x1800042a5  pop     rdi
0x1800042a6  pop     rsi
0x1800042a7  retn
0x1800042a8  mov     ecx, eax
0x1800042aa  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
0x1800042b0  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x1800042b6  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
```
