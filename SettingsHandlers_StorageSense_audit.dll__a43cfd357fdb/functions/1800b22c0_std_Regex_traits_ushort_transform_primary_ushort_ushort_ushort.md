# std::_Regex_traits<ushort>::transform_primary<ushort *>(ushort *,ushort *)

- ea: `0x1800b22c0`
- end: `0x1800b2400`
- name: `??$transform_primary@PEAG@?$_Regex_traits@G@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEAG0@Z`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800b634c`

## callees

- `0x180006e50`
- `0x180009608`
- `0x180023578`
- `0x180023928`
- `0x180024eac`
- `0x1800b06cc`
- `0x1800b22c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800b2336`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800b234a`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800b2336`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800b234a`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1800b2322`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1800b2322`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Regex_traits<unsigned short>::transform_primary<unsigned short *>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rsi
  __int64 v8; // rdi
  unsigned __int64 v9; // rdi
  __int64 v10; // rsi
  void *v11; // rax
  unsigned __int64 v12; // rax
  _BYTE v14[16]; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int64 v15; // [rsp+50h] [rbp-48h]

  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 7;
  *(_WORD *)a2 = 0;
  if ( a3 != a4 )
  {
    v7 = *a1;
    v8 = __RTtypeid(*a1) + 8;
    if ( !(unsigned int)__std_type_info_compare(v8, &qword_180170FF0)
      || !(unsigned int)__std_type_info_compare(v8, &qword_180171580) )
    {
      std::wstring::wstring(v14, a3, a4);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
      v9 = v15;
      if ( *(_QWORD *)(a2 + 16) < v15 )
      {
        v10 = v7 + 16;
        while ( 1 )
        {
          std::wstring::resize(a2, v9);
          std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
          v11 = (void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
          v12 = _std_regex_transform_primary_wchar_t(v11, v10);
          v9 = v12;
          if ( v12 == -1 )
            break;
          if ( *(_QWORD *)(a2 + 16) >= v12 )
            goto LABEL_10;
        }
        v9 = 0;
      }
LABEL_10:
      std::wstring::resize(a2, v9);
      std::wstring::_Tidy_deallocate(v14);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800b22c0  push    rbx
0x1800b22c2  push    rbp
0x1800b22c3  push    rsi
0x1800b22c4  push    rdi
0x1800b22c5  push    r14
0x1800b22c7  sub     rsp, 70h
0x1800b22cb  mov     rax, cs:__security_cookie
0x1800b22d2  xor     rax, rsp
0x1800b22d5  mov     [rsp+98h+var_38], rax
0x1800b22da  mov     r14, r9
0x1800b22dd  mov     rbp, r8
0x1800b22e0  mov     rbx, rdx
0x1800b22e3  mov     [rsp+98h+var_60], rdx
0x1800b22e8  mov     [rsp+98h+var_68], 0
0x1800b22f0  xorps   xmm0, xmm0
0x1800b22f3  movups  xmmword ptr [rdx], xmm0
0x1800b22f6  mov     qword ptr [rdx+10h], 0
0x1800b22fe  mov     qword ptr [rdx+18h], 7
0x1800b2306  xor     eax, eax
0x1800b2308  mov     [rdx], ax
0x1800b230b  mov     [rsp+98h+var_68], 1
0x1800b2313  cmp     r8, r9
0x1800b2316  jz      loc_1800B23E4
0x1800b231c  mov     rsi, [rcx]
0x1800b231f  mov     rcx, rsi
0x1800b2322  call    cs:__imp___RTtypeid
0x1800b2328  lea     rdi, [rax+8]
0x1800b232c  lea     rdx, qword_180170FF0
0x1800b2333  mov     rcx, rdi
0x1800b2336  call    cs:__imp___std_type_info_compare
0x1800b233c  test    eax, eax
0x1800b233e  jz      short loc_1800B2358
0x1800b2340  lea     rdx, qword_180171580
0x1800b2347  mov     rcx, rdi
0x1800b234a  call    cs:__imp___std_type_info_compare
0x1800b2350  test    eax, eax
0x1800b2352  jnz     loc_1800B23E4
0x1800b2358  mov     r8, r14
0x1800b235b  mov     rdx, rbp
0x1800b235e  lea     rcx, [rsp+98h+var_58]
0x1800b2363  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x1800b2368  nop
0x1800b2369  lea     rcx, [rsp+98h+var_58]
0x1800b236e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b2373  mov     r14, rax
0x1800b2376  mov     rdi, [rsp+98h+var_48]
0x1800b237b  lea     rbp, [rax+rdi*2]
0x1800b237f  cmp     [rbx+10h], rdi
0x1800b2383  jnb     short loc_1800B23CE
0x1800b2385  add     rsi, 10h
0x1800b2389  mov     rdx, rdi
0x1800b238c  mov     rcx, rbx
0x1800b238f  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800b2394  mov     rcx, rbx
0x1800b2397  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b239c  lea     rdx, [rax+rdi*2]
0x1800b23a0  mov     rcx, rbx
0x1800b23a3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b23a8  mov     [rsp+98h+var_78], rsi; __int64
0x1800b23ad  mov     r9, rbp
0x1800b23b0  mov     r8, r14
0x1800b23b3  mov     rcx, rax; void *
0x1800b23b6  call    __std_regex_transform_primary_wchar_t
0x1800b23bb  mov     rdi, rax
0x1800b23be  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b23c2  jz      short loc_1800B23CC
0x1800b23c4  cmp     [rbx+10h], rax
0x1800b23c8  jb      short loc_1800B2389
0x1800b23ca  jmp     short loc_1800B23CE
0x1800b23cc  xor     edi, edi
0x1800b23ce  mov     rdx, rdi
0x1800b23d1  mov     rcx, rbx
0x1800b23d4  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800b23d9  nop
0x1800b23da  lea     rcx, [rsp+98h+var_58]
0x1800b23df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b23e4  mov     rax, rbx
0x1800b23e7  mov     rcx, [rsp+98h+var_38]
0x1800b23ec  xor     rcx, rsp; StackCookie
0x1800b23ef  call    __security_check_cookie
0x1800b23f4  add     rsp, 70h
0x1800b23f8  pop     r14
0x1800b23fa  pop     rdi
0x1800b23fb  pop     rsi
0x1800b23fc  pop     rbp
0x1800b23fd  pop     rbx
0x1800b23fe  retn
```
