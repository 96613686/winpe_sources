# web::json::details::JSON_Parser<char>::handle_unescape_char(web::json::details::JSON_Parser<char>::Token &)

- ea: `0x18002f95c`
- end: `0x18002fcac`
- name: `?handle_unescape_char@?$JSON_Parser@D@details@json@web@@IEAA_NAEAUToken@1234@@Z`
- size: `848`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18002eac0`

## callees

- `0x180027e54`
- `0x180027ecc`
- `0x180028514`
- `0x180029518`
- `0x180029644`
- `0x18002f95c`
- `0x180031b14`
- `0x180031f2c`
- `0x180042426`
- `0x18004256a`
- `0x1800427d0`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall web::json::details::JSON_Parser<char>::handle_unescape_char(
        __int64 (__fastcall ***a1)(_QWORD),
        __int64 a2)
{
  int v4; // eax
  int v5; // r14d
  int v6; // edi
  unsigned int v7; // eax
  __int64 v8; // rsi
  struct __crt_locale_pointers *v9; // rax
  unsigned int v10; // ebp
  __int64 v11; // rax
  int v12; // eax
  struct __crt_locale_data *locinfo; // rdx
  _QWORD *v15; // rcx
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rdx
  _BYTE Src[32]; // [rsp+28h] [rbp-70h] BYREF
  _OWORD v25[2]; // [rsp+48h] [rbp-50h] BYREF

  *(_BYTE *)(a2 + 56) = 1;
  v4 = (**a1)(a1);
  switch ( v4 )
  {
    case '"':
      v15 = (_QWORD *)(a2 + 8);
      v23 = *(_QWORD *)(a2 + 24);
      if ( v23 < *(_QWORD *)(a2 + 32) )
      {
        *(_QWORD *)(a2 + 24) = v23 + 1;
        if ( *(_QWORD *)(a2 + 32) > 0xFu )
          v15 = (_QWORD *)*v15;
        *(_WORD *)((char *)v15 + v23) = 34;
        return 1;
      }
      goto LABEL_63;
    case '/':
      v15 = (_QWORD *)(a2 + 8);
      v22 = *(_QWORD *)(a2 + 24);
      if ( v22 < *(_QWORD *)(a2 + 32) )
      {
        *(_QWORD *)(a2 + 24) = v22 + 1;
        if ( *(_QWORD *)(a2 + 32) > 0xFu )
          v15 = (_QWORD *)*v15;
        *(_WORD *)((char *)v15 + v22) = 47;
        return 1;
      }
      goto LABEL_63;
    case '\\':
      v15 = (_QWORD *)(a2 + 8);
      v21 = *(_QWORD *)(a2 + 24);
      if ( v21 < *(_QWORD *)(a2 + 32) )
      {
        *(_QWORD *)(a2 + 24) = v21 + 1;
        if ( *(_QWORD *)(a2 + 32) > 0xFu )
          v15 = (_QWORD *)*v15;
        *(_WORD *)((char *)v15 + v21) = 92;
        return 1;
      }
      goto LABEL_63;
    case 'b':
      v15 = (_QWORD *)(a2 + 8);
      v20 = *(_QWORD *)(a2 + 24);
      if ( v20 < *(_QWORD *)(a2 + 32) )
      {
        *(_QWORD *)(a2 + 24) = v20 + 1;
        if ( *(_QWORD *)(a2 + 32) > 0xFu )
          v15 = (_QWORD *)*v15;
        *(_WORD *)((char *)v15 + v20) = 8;
        return 1;
      }
      goto LABEL_63;
    case 'f':
      v15 = (_QWORD *)(a2 + 8);
      v19 = *(_QWORD *)(a2 + 24);
      if ( v19 < *(_QWORD *)(a2 + 32) )
      {
        *(_QWORD *)(a2 + 24) = v19 + 1;
        if ( *(_QWORD *)(a2 + 32) > 0xFu )
          v15 = (_QWORD *)*v15;
        *(_WORD *)((char *)v15 + v19) = 12;
        return 1;
      }
      goto LABEL_63;
    case 'n':
      v15 = (_QWORD *)(a2 + 8);
      v18 = *(_QWORD *)(a2 + 24);
      if ( v18 < *(_QWORD *)(a2 + 32) )
      {
        *(_QWORD *)(a2 + 24) = v18 + 1;
        if ( *(_QWORD *)(a2 + 32) > 0xFu )
          v15 = (_QWORD *)*v15;
        *(_WORD *)((char *)v15 + v18) = 10;
        return 1;
      }
      goto LABEL_63;
    case 'r':
      v15 = (_QWORD *)(a2 + 8);
      v17 = *(_QWORD *)(a2 + 24);
      if ( v17 < *(_QWORD *)(a2 + 32) )
      {
        *(_QWORD *)(a2 + 24) = v17 + 1;
        if ( *(_QWORD *)(a2 + 32) > 0xFu )
          v15 = (_QWORD *)*v15;
        *(_WORD *)((char *)v15 + v17) = 13;
        return 1;
      }
      goto LABEL_63;
    case 't':
      v15 = (_QWORD *)(a2 + 8);
      v16 = *(_QWORD *)(a2 + 24);
      if ( v16 < *(_QWORD *)(a2 + 32) )
      {
        *(_QWORD *)(a2 + 24) = v16 + 1;
        if ( *(_QWORD *)(a2 + 32) > 0xFu )
          v15 = (_QWORD *)*v15;
        *(_WORD *)((char *)v15 + v16) = 9;
        return 1;
      }
LABEL_63:
      std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v15);
      return 1;
    case 'u':
      v5 = 0;
      v6 = 12;
      while ( 1 )
      {
        v7 = (**a1)(a1);
        v8 = (int)v7;
        if ( v7 > 0x7F )
          return 0;
        v9 = utility::details::scoped_c_thread_locale::c_locale();
        v10 = v8 + 1;
        if ( v9 )
          break;
        v11 = o___pctype_func_0();
        if ( v10 <= 0x100 )
          goto LABEL_17;
        v12 = 0;
LABEL_20:
        if ( !v12 )
          return 0;
        v5 |= *((char *)_hexval + v8) << v6;
        v6 -= 4;
        if ( v6 <= -4 )
        {
          memset(v25, 0, sizeof(v25));
          std::wstring::_Construct<1,wchar_t const *>(v25);
          utility::conversions::utf16_to_utf8(Src);
          std::string::append((void *)(a2 + 8));
          std::string::~string(Src);
          std::wstring::_Tidy_deallocate(v25);
          return 1;
        }
      }
      locinfo = v9->locinfo;
      if ( v10 > 0x100 )
      {
        if ( *((int *)locinfo + 2) <= 1 )
          return 0;
        v12 = isctype_l(v8, 128, v9);
        goto LABEL_20;
      }
      v11 = *(_QWORD *)locinfo;
LABEL_17:
      v12 = *(_WORD *)(v11 + 2 * v8) & 0x80;
      goto LABEL_20;
  }
  return 0;
}

```

## disassembly

```asm
0x18002f95c  mov     [rsp+arg_10], rbx
0x18002f961  push    rbp
0x18002f962  push    rsi
0x18002f963  push    rdi
0x18002f964  push    r14
0x18002f966  push    r15
0x18002f968  sub     rsp, 70h
0x18002f96c  mov     rax, cs:__security_cookie
0x18002f973  xor     rax, rsp
0x18002f976  mov     [rsp+98h+var_30], rax
0x18002f97b  mov     rbx, rdx
0x18002f97e  mov     r15, rcx
0x18002f981  mov     byte ptr [rdx+38h], 1
0x18002f985  mov     rax, [rcx]
0x18002f988  mov     rax, [rax]
0x18002f98b  call    _guard_dispatch_icall
0x18002f990  mov     r8d, eax
0x18002f993  sub     r8d, 22h ; '"'
0x18002f997  jz      loc_18002FC59
0x18002f99d  sub     r8d, 0Dh
0x18002f9a1  jz      loc_18002FC2C
0x18002f9a7  sub     r8d, 2Dh ; '-'
0x18002f9ab  jz      loc_18002FBFF
0x18002f9b1  sub     r8d, 6
0x18002f9b5  jz      loc_18002FBCC
0x18002f9bb  sub     r8d, 4
0x18002f9bf  jz      loc_18002FB96
0x18002f9c5  sub     r8d, 8
0x18002f9c9  jz      loc_18002FB63
0x18002f9cf  sub     r8d, 4
0x18002f9d3  jz      loc_18002FB30
0x18002f9d9  sub     r8d, 2
0x18002f9dd  jz      loc_18002FAFD
0x18002f9e3  cmp     r8d, 1
0x18002f9e7  jnz     loc_18002FAF6
0x18002f9ed  xor     r14d, r14d
0x18002f9f0  lea     edi, [r8+0Bh]
0x18002f9f4  mov     rax, [r15]
0x18002f9f7  mov     rcx, r15
0x18002f9fa  mov     rax, [rax]
0x18002f9fd  call    _guard_dispatch_icall
0x18002fa02  movsxd  rsi, eax
0x18002fa05  cmp     esi, 7Fh
0x18002fa08  ja      loc_18002FAF6
0x18002fa0e  call    ?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ; utility::details::scoped_c_thread_locale::c_locale(void)
0x18002fa13  lea     ebp, [rsi+1]
0x18002fa16  test    rax, rax
0x18002fa19  jnz     short loc_18002FA2C
0x18002fa1b  call    _o___pctype_func_0
0x18002fa20  cmp     ebp, 100h
0x18002fa26  jbe     short loc_18002FA3A
0x18002fa28  xor     eax, eax
0x18002fa2a  jmp     short loc_18002FA5E
0x18002fa2c  mov     rdx, [rax]
0x18002fa2f  cmp     ebp, 100h
0x18002fa35  ja      short loc_18002FA45
0x18002fa37  mov     rax, [rdx]
0x18002fa3a  movzx   eax, word ptr [rax+rsi*2]
0x18002fa3e  and     eax, 80h
0x18002fa43  jmp     short loc_18002FA5E
0x18002fa45  cmp     dword ptr [rdx+8], 1
0x18002fa49  jle     loc_18002FAF6
0x18002fa4f  mov     r8, rax; Locale
0x18002fa52  mov     edx, 80h; Type
0x18002fa57  mov     ecx, esi; C
0x18002fa59  call    _isctype_l
0x18002fa5e  test    eax, eax
0x18002fa60  jz      loc_18002FAF6
0x18002fa66  lea     rcx, ?_hexval@@3V?$array@C$0IA@@std@@A; std::array<signed char,128> _hexval
0x18002fa6d  movsx   edx, byte ptr [rsi+rcx]
0x18002fa71  mov     ecx, edi
0x18002fa73  shl     edx, cl
0x18002fa75  or      r14d, edx
0x18002fa78  sub     edi, 4
0x18002fa7b  cmp     edi, 0FFFFFFFCh
0x18002fa7e  jg      loc_18002F9F4
0x18002fa84  mov     [rsp+98h+var_78], r14w
0x18002fa8a  xorps   xmm0, xmm0
0x18002fa8d  movups  [rsp+98h+var_50], xmm0
0x18002fa92  xorps   xmm1, xmm1
0x18002fa95  movdqu  [rsp+98h+var_40], xmm1
0x18002fa9b  mov     r8d, 1
0x18002faa1  lea     rdx, [rsp+98h+var_78]
0x18002faa6  lea     rcx, [rsp+98h+var_50]
0x18002faab  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002fab0  nop
0x18002fab1  lea     rdx, [rsp+98h+var_50]
0x18002fab6  lea     rcx, [rsp+98h+Src]; Src
0x18002fabb  call    ?utf16_to_utf8@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; utility::conversions::utf16_to_utf8(std::wstring const &)
0x18002fac0  nop
0x18002fac1  mov     r8, [rax+10h]
0x18002fac5  cmp     qword ptr [rax+18h], 0Fh
0x18002faca  jbe     short loc_18002FACF
0x18002facc  mov     rax, [rax]
0x18002facf  mov     rdx, rax
0x18002fad2  lea     rcx, [rbx+8]; Src
0x18002fad6  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x18002fadb  nop
0x18002fadc  lea     rcx, [rsp+98h+Src]
0x18002fae1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002fae6  nop
0x18002fae7  lea     rcx, [rsp+98h+var_50]
0x18002faec  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002faf1  jmp     loc_18002FC89
0x18002faf6  xor     al, al
0x18002faf8  jmp     loc_18002FC8B
0x18002fafd  lea     rcx, [rbx+8]
0x18002fb01  mov     rdx, [rcx+10h]
0x18002fb05  cmp     rdx, [rcx+18h]
0x18002fb09  jnb     short loc_18002FB28
0x18002fb0b  lea     rax, [rdx+1]
0x18002fb0f  mov     [rcx+10h], rax
0x18002fb13  cmp     qword ptr [rcx+18h], 0Fh
0x18002fb18  jbe     short loc_18002FB1D
0x18002fb1a  mov     rcx, [rcx]
0x18002fb1d  mov     word ptr [rcx+rdx], 9
0x18002fb23  jmp     loc_18002FC89
0x18002fb28  mov     r9b, 9
0x18002fb2b  jmp     loc_18002FC84
0x18002fb30  lea     rcx, [rbx+8]
0x18002fb34  mov     rdx, [rcx+10h]
0x18002fb38  cmp     rdx, [rcx+18h]
0x18002fb3c  jnb     short loc_18002FB5B
0x18002fb3e  lea     rax, [rdx+1]
0x18002fb42  mov     [rcx+10h], rax
0x18002fb46  cmp     qword ptr [rcx+18h], 0Fh
0x18002fb4b  jbe     short loc_18002FB50
0x18002fb4d  mov     rcx, [rcx]
0x18002fb50  mov     word ptr [rcx+rdx], 0Dh
0x18002fb56  jmp     loc_18002FC89
0x18002fb5b  mov     r9b, 0Dh
0x18002fb5e  jmp     loc_18002FC84
0x18002fb63  lea     rcx, [rbx+8]
0x18002fb67  mov     rdx, [rcx+10h]
0x18002fb6b  cmp     rdx, [rcx+18h]
0x18002fb6f  jnb     short loc_18002FB8E
0x18002fb71  lea     rax, [rdx+1]
0x18002fb75  mov     [rcx+10h], rax
0x18002fb79  cmp     qword ptr [rcx+18h], 0Fh
0x18002fb7e  jbe     short loc_18002FB83
0x18002fb80  mov     rcx, [rcx]
0x18002fb83  mov     word ptr [rcx+rdx], 0Ah
0x18002fb89  jmp     loc_18002FC89
0x18002fb8e  mov     r9b, 0Ah
0x18002fb91  jmp     loc_18002FC84
0x18002fb96  lea     rcx, [rbx+8]
0x18002fb9a  mov     rdx, [rcx+10h]
0x18002fb9e  cmp     rdx, [rcx+18h]
0x18002fba2  jnb     short loc_18002FBC1
0x18002fba4  lea     rax, [rdx+1]
0x18002fba8  mov     [rcx+10h], rax
0x18002fbac  cmp     qword ptr [rcx+18h], 0Fh
0x18002fbb1  jbe     short loc_18002FBB6
0x18002fbb3  mov     rcx, [rcx]
0x18002fbb6  mov     word ptr [rcx+rdx], 0Ch
0x18002fbbc  jmp     loc_18002FC89
0x18002fbc1  mov     r9d, 0Ch
0x18002fbc7  jmp     loc_18002FC84
0x18002fbcc  lea     rcx, [rbx+8]
0x18002fbd0  mov     rdx, [rcx+10h]
0x18002fbd4  cmp     rdx, [rcx+18h]
0x18002fbd8  jnb     short loc_18002FBF7
0x18002fbda  lea     rax, [rdx+1]
0x18002fbde  mov     [rcx+10h], rax
0x18002fbe2  cmp     qword ptr [rcx+18h], 0Fh
0x18002fbe7  jbe     short loc_18002FBEC
0x18002fbe9  mov     rcx, [rcx]
0x18002fbec  mov     word ptr [rcx+rdx], 8
0x18002fbf2  jmp     loc_18002FC89
0x18002fbf7  mov     r9b, 8
0x18002fbfa  jmp     loc_18002FC84
0x18002fbff  lea     rcx, [rbx+8]
0x18002fc03  mov     rdx, [rcx+10h]
0x18002fc07  cmp     rdx, [rcx+18h]
0x18002fc0b  jnb     short loc_18002FC27
0x18002fc0d  lea     rax, [rdx+1]
0x18002fc11  mov     [rcx+10h], rax
0x18002fc15  cmp     qword ptr [rcx+18h], 0Fh
0x18002fc1a  jbe     short loc_18002FC1F
0x18002fc1c  mov     rcx, [rcx]
0x18002fc1f  mov     word ptr [rcx+rdx], 5Ch ; '\'
0x18002fc25  jmp     short loc_18002FC89
0x18002fc27  mov     r9b, 5Ch ; '\'
0x18002fc2a  jmp     short loc_18002FC84
0x18002fc2c  lea     rcx, [rbx+8]
0x18002fc30  mov     rdx, [rcx+10h]
0x18002fc34  cmp     rdx, [rcx+18h]
0x18002fc38  jnb     short loc_18002FC54
0x18002fc3a  lea     rax, [rdx+1]
0x18002fc3e  mov     [rcx+10h], rax
0x18002fc42  cmp     qword ptr [rcx+18h], 0Fh
0x18002fc47  jbe     short loc_18002FC4C
0x18002fc49  mov     rcx, [rcx]
0x18002fc4c  mov     word ptr [rcx+rdx], 2Fh ; '/'
0x18002fc52  jmp     short loc_18002FC89
0x18002fc54  mov     r9b, 2Fh ; '/'
0x18002fc57  jmp     short loc_18002FC84
0x18002fc59  lea     rcx, [rbx+8]; Src
0x18002fc5d  mov     rdx, [rcx+10h]
0x18002fc61  cmp     rdx, [rcx+18h]
0x18002fc65  jnb     short loc_18002FC81
0x18002fc67  lea     rax, [rdx+1]
0x18002fc6b  mov     [rcx+10h], rax
0x18002fc6f  cmp     qword ptr [rcx+18h], 0Fh
0x18002fc74  jbe     short loc_18002FC79
0x18002fc76  mov     rcx, [rcx]
0x18002fc79  mov     word ptr [rcx+rdx], 22h ; '"'
0x18002fc7f  jmp     short loc_18002FC89
0x18002fc81  mov     r9b, 22h ; '"'
0x18002fc84  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18002fc89  mov     al, 1
0x18002fc8b  mov     rcx, [rsp+98h+var_30]
0x18002fc90  xor     rcx, rsp; StackCookie
0x18002fc93  call    __security_check_cookie
0x18002fc98  mov     rbx, [rsp+98h+arg_10]
0x18002fca0  add     rsp, 70h
0x18002fca4  pop     r15
0x18002fca6  pop     r14
0x18002fca8  pop     rdi
0x18002fca9  pop     rsi
0x18002fcaa  pop     rbp
0x18002fcab  retn
```
