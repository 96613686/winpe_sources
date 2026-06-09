# std::_Regex_traits<wchar_t>::transform_primary<std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>(std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>)

- ea: `0x1400348e0`
- end: `0x140034a4e`
- name: `??$transform_primary@V?$_String_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@@?$_Regex_traits@_W@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$_String_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@1@0@Z`
- size: `366`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140033e58`

## callees

- `0x140003e50`
- `0x14000a7bc`
- `0x14000ba60`
- `0x14000c2b8`
- `0x1400180e8`
- `0x1400348e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14003495d`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140034971`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14003495d`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140034971`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140034949`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140034949`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Regex_traits<wchar_t>::transform_primary<std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>(
        _QWORD *a1,
        _QWORD *a2,
        _BYTE *a3,
        _BYTE *a4)
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
    if ( !(unsigned int)__std_type_info_compare(v8, &qword_1400CBB60)
      || !(unsigned int)__std_type_info_compare(v8, &qword_1400CBB38) )
    {
      v13 = 0;
      v14 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v13, a3, (a4 - a3) >> 1);
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
      std::wstring::_Tidy_deallocate(&v13);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1400348e0  mov     [rsp+arg_10], rbx
0x1400348e5  mov     [rsp+arg_18], rbp
0x1400348ea  push    rsi
0x1400348eb  push    rdi
0x1400348ec  push    r14
0x1400348ee  sub     rsp, 70h
0x1400348f2  mov     rax, cs:__security_cookie
0x1400348f9  xor     rax, rsp
0x1400348fc  mov     [rsp+88h+var_28], rax
0x140034901  mov     rbx, r9
0x140034904  mov     rdi, r8
0x140034907  mov     rsi, rdx
0x14003490a  mov     [rsp+88h+var_50], rdx
0x14003490f  mov     [rsp+88h+var_58], 0
0x140034917  xorps   xmm0, xmm0
0x14003491a  movups  xmmword ptr [rdx], xmm0
0x14003491d  mov     qword ptr [rdx+10h], 0
0x140034925  mov     qword ptr [rdx+18h], 7
0x14003492d  xor     eax, eax
0x14003492f  mov     [rdx], ax
0x140034932  mov     [rsp+88h+var_58], 1
0x14003493a  cmp     r8, r9
0x14003493d  jz      loc_140034A28
0x140034943  mov     r14, [rcx]
0x140034946  mov     rcx, r14
0x140034949  call    cs:__imp___RTtypeid
0x14003494f  lea     rbp, [rax+8]
0x140034953  lea     rdx, qword_1400CBB60
0x14003495a  mov     rcx, rbp
0x14003495d  call    cs:__imp___std_type_info_compare
0x140034963  test    eax, eax
0x140034965  jz      short loc_14003497F
0x140034967  lea     rdx, qword_1400CBB38
0x14003496e  mov     rcx, rbp
0x140034971  call    cs:__imp___std_type_info_compare
0x140034977  test    eax, eax
0x140034979  jnz     loc_140034A28
0x14003497f  xorps   xmm0, xmm0
0x140034982  movups  [rsp+88h+var_48], xmm0
0x140034987  xorps   xmm1, xmm1
0x14003498a  movdqu  [rsp+88h+var_38], xmm1
0x140034990  sub     rbx, rdi
0x140034993  sar     rbx, 1
0x140034996  mov     r8, rbx
0x140034999  mov     rdx, rdi
0x14003499c  lea     rcx, [rsp+88h+var_48]
0x1400349a1  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1400349a6  nop
0x1400349a7  lea     rdi, [rsp+88h+var_48]
0x1400349ac  cmp     qword ptr [rsp+88h+var_38+8], 7
0x1400349b2  cmova   rdi, qword ptr [rsp+88h+var_48]
0x1400349b8  mov     rbx, qword ptr [rsp+88h+var_38]
0x1400349bd  cmp     [rsi+10h], rbx
0x1400349c1  jnb     short loc_140034A12
0x1400349c3  lea     rbp, [rdi+rbx*2]
0x1400349c7  add     r14, 10h
0x1400349cb  mov     rdx, rbx
0x1400349ce  mov     rcx, rsi; Src
0x1400349d1  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1400349d6  cmp     qword ptr [rsi+18h], 7
0x1400349db  jbe     short loc_1400349E5
0x1400349dd  mov     rcx, [rsi]
0x1400349e0  mov     rax, rcx
0x1400349e3  jmp     short loc_1400349EB
0x1400349e5  mov     rax, rsi
0x1400349e8  mov     rcx, rsi; void *
0x1400349eb  lea     rdx, [rax+rbx*2]
0x1400349ef  mov     [rsp+88h+var_68], r14; __int64
0x1400349f4  mov     r9, rbp
0x1400349f7  mov     r8, rdi
0x1400349fa  call    __std_regex_transform_primary_wchar_t
0x1400349ff  mov     rbx, rax
0x140034a02  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140034a06  jz      short loc_140034A10
0x140034a08  cmp     [rsi+10h], rax
0x140034a0c  jb      short loc_1400349CB
0x140034a0e  jmp     short loc_140034A12
0x140034a10  xor     ebx, ebx
0x140034a12  mov     rdx, rbx
0x140034a15  mov     rcx, rsi; Src
0x140034a18  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x140034a1d  nop
0x140034a1e  lea     rcx, [rsp+88h+var_48]
0x140034a23  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140034a28  mov     rax, rsi
0x140034a2b  mov     rcx, [rsp+88h+var_28]
0x140034a30  xor     rcx, rsp; StackCookie
0x140034a33  call    __security_check_cookie
0x140034a38  lea     r11, [rsp+88h+var_18]
0x140034a3d  mov     rbx, [r11+30h]
0x140034a41  mov     rbp, [r11+38h]
0x140034a45  mov     rsp, r11
0x140034a48  pop     r14
0x140034a4a  pop     rdi
0x140034a4b  pop     rsi
0x140034a4c  retn
```
