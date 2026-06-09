# std::_Regex_traits<ushort>::transform_primary<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>)

- ea: `0x18003d7a4`
- end: `0x18003d918`
- name: `??$transform_primary@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@?$_Regex_traits@G@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0@Z`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003c9d8`

## callees

- `0x1800060a0`
- `0x180007c98`
- `0x180008d50`
- `0x180009a80`
- `0x180035a70`
- `0x18003d7a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18003d821`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18003d835`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18003d821`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18003d835`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18003d80d`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18003d80d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall std::_Regex_traits<unsigned short>::transform_primary<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // r14
  __int64 v8; // rbp
  __int64 v9; // r14
  void *v10; // rcx
  unsigned __int64 v11; // rax
  __int128 v13; // [rsp+40h] [rbp-48h] BYREF
  __int128 v14; // [rsp+50h] [rbp-38h]

  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  if ( a3 != a4 )
  {
    v7 = *a1;
    v8 = __RTtypeid(*a1) + 8;
    if ( !(unsigned int)__std_type_info_compare(v8, &qword_1800F13F0)
      || !(unsigned int)__std_type_info_compare(v8, &qword_1800F13C8) )
    {
      v13 = 0;
      v14 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v13, a3, (a4 - a3) >> 1);
      if ( a2[2] < (unsigned __int64)v14 )
      {
        v9 = v7 + 16;
        do
        {
          std::wstring::resize(a2);
          if ( a2[3] <= 7u )
            v10 = a2;
          else
            v10 = (void *)*a2;
          v11 = _std_regex_transform_primary_wchar_t(v10, v9);
        }
        while ( v11 != -1 && a2[2] < v11 );
      }
      std::wstring::resize(a2);
      std::wstring::~wstring(&v13);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18003d7a4  mov     [rsp+arg_10], rbx
0x18003d7a9  mov     [rsp+arg_18], rbp
0x18003d7ae  push    rsi
0x18003d7af  push    rdi
0x18003d7b0  push    r14
0x18003d7b2  sub     rsp, 70h
0x18003d7b6  mov     rax, cs:__security_cookie
0x18003d7bd  xor     rax, rsp
0x18003d7c0  mov     [rsp+88h+var_28], rax
0x18003d7c5  mov     rbx, r9
0x18003d7c8  mov     rdi, r8
0x18003d7cb  mov     rsi, rdx
0x18003d7ce  mov     [rsp+88h+var_50], rdx
0x18003d7d3  mov     [rsp+88h+var_58], 0
0x18003d7db  xorps   xmm0, xmm0
0x18003d7de  movups  xmmword ptr [rdx], xmm0
0x18003d7e1  mov     qword ptr [rdx+10h], 0
0x18003d7e9  mov     qword ptr [rdx+18h], 7
0x18003d7f1  xor     eax, eax
0x18003d7f3  mov     [rdx], ax
0x18003d7f6  mov     [rsp+88h+var_58], 1
0x18003d7fe  cmp     r8, r9
0x18003d801  jz      loc_18003D8F2
0x18003d807  mov     r14, [rcx]
0x18003d80a  mov     rcx, r14
0x18003d80d  call    cs:__imp___RTtypeid
0x18003d813  lea     rbp, [rax+8]
0x18003d817  lea     rdx, qword_1800F13F0
0x18003d81e  mov     rcx, rbp
0x18003d821  call    cs:__imp___std_type_info_compare
0x18003d827  test    eax, eax
0x18003d829  jz      short loc_18003D843
0x18003d82b  lea     rdx, qword_1800F13C8
0x18003d832  mov     rcx, rbp
0x18003d835  call    cs:__imp___std_type_info_compare
0x18003d83b  test    eax, eax
0x18003d83d  jnz     loc_18003D8F2
0x18003d843  xorps   xmm0, xmm0
0x18003d846  movups  [rsp+88h+var_48], xmm0
0x18003d84b  xorps   xmm1, xmm1
0x18003d84e  movdqu  [rsp+88h+var_38], xmm1
0x18003d854  sub     rbx, rdi
0x18003d857  sar     rbx, 1
0x18003d85a  mov     r8, rbx
0x18003d85d  mov     rdx, rdi
0x18003d860  lea     rcx, [rsp+88h+var_48]
0x18003d865  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003d86a  nop
0x18003d86b  lea     rdi, [rsp+88h+var_48]
0x18003d870  cmp     qword ptr [rsp+88h+var_38+8], 7
0x18003d876  cmova   rdi, qword ptr [rsp+88h+var_48]
0x18003d87c  mov     rbx, qword ptr [rsp+88h+var_38]
0x18003d881  cmp     [rsi+10h], rbx
0x18003d885  jnb     short loc_18003D8D9
0x18003d887  lea     rbp, [rdi+rbx*2]
0x18003d88b  add     r14, 10h
0x18003d88f  xor     r8d, r8d
0x18003d892  mov     rdx, rbx
0x18003d895  mov     rcx, rsi; Src
0x18003d898  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18003d89d  cmp     qword ptr [rsi+18h], 7
0x18003d8a2  jbe     short loc_18003D8AC
0x18003d8a4  mov     rcx, [rsi]
0x18003d8a7  mov     rax, rcx
0x18003d8aa  jmp     short loc_18003D8B2
0x18003d8ac  mov     rax, rsi
0x18003d8af  mov     rcx, rsi; void *
0x18003d8b2  lea     rdx, [rax+rbx*2]
0x18003d8b6  mov     [rsp+88h+var_68], r14; __int64
0x18003d8bb  mov     r9, rbp
0x18003d8be  mov     r8, rdi
0x18003d8c1  call    __std_regex_transform_primary_wchar_t
0x18003d8c6  mov     rbx, rax
0x18003d8c9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003d8cd  jz      short loc_18003D8D7
0x18003d8cf  cmp     [rsi+10h], rax
0x18003d8d3  jb      short loc_18003D88F
0x18003d8d5  jmp     short loc_18003D8D9
0x18003d8d7  xor     ebx, ebx
0x18003d8d9  xor     r8d, r8d
0x18003d8dc  mov     rdx, rbx
0x18003d8df  mov     rcx, rsi; Src
0x18003d8e2  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18003d8e7  nop
0x18003d8e8  lea     rcx, [rsp+88h+var_48]
0x18003d8ed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d8f2  mov     rax, rsi
0x18003d8f5  mov     rcx, [rsp+88h+var_28]
0x18003d8fa  xor     rcx, rsp; StackCookie
0x18003d8fd  call    __security_check_cookie
0x18003d902  lea     r11, [rsp+88h+var_18]
0x18003d907  mov     rbx, [r11+30h]
0x18003d90b  mov     rbp, [r11+38h]
0x18003d90f  mov     rsp, r11
0x18003d912  pop     r14
0x18003d914  pop     rdi
0x18003d915  pop     rsi
0x18003d916  retn
```
