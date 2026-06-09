# std::copy_if<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::back_insert_iterator<std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,_lambda_89e20cf5b205b052b5f2ed9adeb67dd7_>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::back_insert_iterator<std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,_lambda_89e20cf5b205b052b5f2ed9adeb67dd7_)

- ea: `0x18000fb40`
- end: `0x18000fd0d`
- name: `??$copy_if@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@V_lambda_89e20cf5b205b052b5f2ed9adeb67dd7_@@@std@@YA?AV?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@0@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@0@0V10@V_lambda_89e20cf5b205b052b5f2ed9adeb67dd7_@@@Z`
- size: `461`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017a80`

## callees

- `0x180003520`
- `0x180005d68`
- `0x1800092a4`
- `0x18000cca4`
- `0x18000fb40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000fbe7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000fc33`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000fbe7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000fc33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fbfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fc48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fbfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fc48`
- `Bcp47Langs!Bcp47GetDistance` at `0x18000fc5b`
- `Bcp47Langs!Bcp47GetDistance` at `0x18000fc5b`

## string_xrefs

- `0x18000fc6f`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\LanguageComponentsUninstaller.h`

## pseudocode

```c
_QWORD *__fastcall std::copy_if<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::back_insert_iterator<std::vector<std::wstring>>,_lambda_89e20cf5b205b052b5f2ed9adeb67dd7_>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5)
{
  __int64 v7; // r14
  _QWORD *result; // rax
  __int64 v9; // r15
  const WCHAR *v10; // r12
  const WCHAR *v11; // r13
  unsigned __int64 v12; // rbp
  HSTRING v13; // r12
  unsigned __int64 v14; // rbp
  int Distance; // eax
  int v16[2]; // [rsp+20h] [rbp-A8h]
  HSTRING string; // [rsp+30h] [rbp-98h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-90h] BYREF
  HSTRING v20; // [rsp+50h] [rbp-78h] BYREF
  HSTRING_HEADER v21; // [rsp+58h] [rbp-70h] BYREF
  int v22; // [rsp+70h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v7 = a2;
  result = a1;
  if ( a2 != a3 )
  {
    do
    {
      v9 = *a5;
      *(_QWORD *)v16 = a5[1];
      if ( *a5 != *(_QWORD *)v16 )
      {
        do
        {
          if ( *(_QWORD *)(v9 + 24) <= 7u )
            v10 = (const WCHAR *)v9;
          else
            v10 = *(const WCHAR **)v9;
          if ( *(_QWORD *)(v7 + 24) <= 7u )
            v11 = (const WCHAR *)v7;
          else
            v11 = *(const WCHAR **)v7;
          v22 = 0;
          v12 = -1;
          do
            ++v12;
          while ( v10[v12] );
          if ( v12 > 0xFFFFFFFF )
          {
            LODWORD(v12) = -1;
            RaiseException(0xC000000D, 1u, 0, 0);
          }
          WindowsCreateStringReference(v10, v12, &hstringHeader, &string);
          v13 = string;
          v14 = -1;
          do
            ++v14;
          while ( v11[v14] );
          if ( v14 > 0xFFFFFFFF )
          {
            LODWORD(v14) = -1;
            RaiseException(0xC000000D, 1u, 0, 0);
          }
          WindowsCreateStringReference(v11, v14, &v21, &v20);
          Distance = Bcp47GetDistance(v20, v13, &v22);
          if ( Distance >= 0 )
          {
            if ( !v22 )
              goto LABEL_24;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x98,
              (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\LanguageCompo"
                            "nentsUninstaller.h",
              (const char *)(unsigned int)Distance,
              v16[0]);
          }
          v9 += 32;
        }
        while ( v9 != *(_QWORD *)v16 );
      }
      if ( *(_QWORD *)(a4 + 8) == *(_QWORD *)(a4 + 16) )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a4, *(_QWORD *)(a4 + 8), v7);
      }
      else
      {
        std::wstring::wstring(*(_QWORD *)(a4 + 8), v7);
        *(_QWORD *)(a4 + 8) += 32LL;
      }
LABEL_24:
      v7 += 32;
    }
    while ( v7 != a3 );
    result = a1;
  }
  *result = a4;
  return result;
}

```

## disassembly

```asm
0x18000fb40  push    rbx
0x18000fb42  push    rbp
0x18000fb43  push    rsi
0x18000fb44  push    rdi
0x18000fb45  push    r12
0x18000fb47  push    r13
0x18000fb49  push    r14
0x18000fb4b  push    r15
0x18000fb4d  sub     rsp, 88h
0x18000fb54  mov     rax, cs:__security_cookie
0x18000fb5b  xor     rax, rsp
0x18000fb5e  mov     [rsp+0C8h+var_50], rax
0x18000fb63  mov     rsi, [rsp+0C8h+arg_20]
0x18000fb6b  mov     rbx, r9
0x18000fb6e  mov     [rsp+0C8h+var_A0], rcx
0x18000fb73  mov     rdi, r8
0x18000fb76  mov     r14, rdx
0x18000fb79  mov     rax, rcx
0x18000fb7c  cmp     rdx, r8
0x18000fb7f  jz      loc_18000FCE9
0x18000fb85  xor     ecx, ecx
0x18000fb87  mov     edx, 0FFFFFFFFh
0x18000fb8c  mov     rax, [rsi+8]
0x18000fb90  mov     r15, [rsi]
0x18000fb93  mov     qword ptr [rsp+0C8h+var_A8], rax; int
0x18000fb98  cmp     r15, rax
0x18000fb9b  jz      loc_18000FCA6
0x18000fba1  cmp     qword ptr [r15+18h], 7
0x18000fba6  jbe     short loc_18000FBAD
0x18000fba8  mov     r12, [r15]
0x18000fbab  jmp     short loc_18000FBB0
0x18000fbad  mov     r12, r15
0x18000fbb0  cmp     qword ptr [r14+18h], 7
0x18000fbb5  jbe     short loc_18000FBBC
0x18000fbb7  mov     r13, [r14]
0x18000fbba  jmp     short loc_18000FBBF
0x18000fbbc  mov     r13, r14
0x18000fbbf  mov     [rsp+0C8h+var_58], ecx
0x18000fbc3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000fbc7  inc     rbp
0x18000fbca  cmp     [r12+rbp*2], cx
0x18000fbcf  jnz     short loc_18000FBC7
0x18000fbd1  cmp     rbp, rdx
0x18000fbd4  jbe     short loc_18000FBED
0x18000fbd6  xor     r9d, r9d; lpArguments
0x18000fbd9  mov     ebp, edx
0x18000fbdb  xor     r8d, r8d; nNumberOfArguments
0x18000fbde  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000fbe3  lea     edx, [r9+1]; dwExceptionFlags
0x18000fbe7  call    cs:__imp_RaiseException
0x18000fbed  lea     r9, [rsp+0C8h+string]; string
0x18000fbf2  mov     edx, ebp; length
0x18000fbf4  lea     r8, [rsp+0C8h+hstringHeader]; hstringHeader
0x18000fbf9  mov     rcx, r12; sourceString
0x18000fbfc  call    cs:__imp_WindowsCreateStringReference
0x18000fc02  mov     r12, [rsp+0C8h+string]
0x18000fc07  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000fc0b  xor     eax, eax
0x18000fc0d  inc     rbp
0x18000fc10  cmp     [r13+rbp*2+0], ax
0x18000fc16  jnz     short loc_18000FC0D
0x18000fc18  mov     eax, 0FFFFFFFFh
0x18000fc1d  cmp     rbp, rax
0x18000fc20  jbe     short loc_18000FC39
0x18000fc22  xor     r9d, r9d; lpArguments
0x18000fc25  xor     r8d, r8d; nNumberOfArguments
0x18000fc28  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000fc2d  mov     ebp, eax
0x18000fc2f  lea     edx, [r9+1]; dwExceptionFlags
0x18000fc33  call    cs:__imp_RaiseException
0x18000fc39  lea     r9, [rsp+0C8h+var_78]; string
0x18000fc3e  mov     edx, ebp; length
0x18000fc40  lea     r8, [rsp+0C8h+var_70]; hstringHeader
0x18000fc45  mov     rcx, r13; sourceString
0x18000fc48  call    cs:__imp_WindowsCreateStringReference
0x18000fc4e  mov     rcx, [rsp+0C8h+var_78]
0x18000fc53  lea     r8, [rsp+0C8h+var_58]
0x18000fc58  mov     rdx, r12
0x18000fc5b  call    cs:__imp_Bcp47GetDistance
0x18000fc61  xor     ecx, ecx
0x18000fc63  test    eax, eax
0x18000fc65  jns     short loc_18000FC87
0x18000fc67  mov     rcx, [rsp+0C8h]; this
0x18000fc6f  lea     r8, aOnecoreShellCp_0; "onecore\\shell\\cpls\\internationalsett"...
0x18000fc76  mov     r9d, eax; char *
0x18000fc79  mov     edx, 98h; void *
0x18000fc7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fc83  xor     ecx, ecx
0x18000fc85  jmp     short loc_18000FC92
0x18000fc87  cmp     [rsp+0C8h+var_58], ecx
0x18000fc8b  setz    al
0x18000fc8e  test    al, al
0x18000fc90  jnz     short loc_18000FCD2
0x18000fc92  add     r15, 20h ; ' '
0x18000fc96  mov     edx, 0FFFFFFFFh
0x18000fc9b  cmp     r15, qword ptr [rsp+0C8h+var_A8]
0x18000fca0  jnz     loc_18000FBA1
0x18000fca6  mov     rax, [rbx+8]
0x18000fcaa  cmp     rax, [rbx+10h]
0x18000fcae  jz      short loc_18000FCC2
0x18000fcb0  mov     rdx, r14
0x18000fcb3  mov     rcx, rax
0x18000fcb6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000fcbb  add     qword ptr [rbx+8], 20h ; ' '
0x18000fcc0  jmp     short loc_18000FCD0
0x18000fcc2  mov     r8, r14
0x18000fcc5  mov     rdx, rax
0x18000fcc8  mov     rcx, rbx
0x18000fccb  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18000fcd0  xor     ecx, ecx
0x18000fcd2  add     r14, 20h ; ' '
0x18000fcd6  mov     edx, 0FFFFFFFFh
0x18000fcdb  cmp     r14, rdi
0x18000fcde  jnz     loc_18000FB8C
0x18000fce4  mov     rax, [rsp+0C8h+var_A0]
0x18000fce9  mov     [rax], rbx
0x18000fcec  mov     rcx, [rsp+0C8h+var_50]
0x18000fcf1  xor     rcx, rsp; StackCookie
0x18000fcf4  call    __security_check_cookie
0x18000fcf9  add     rsp, 88h
0x18000fd00  pop     r15
0x18000fd02  pop     r14
0x18000fd04  pop     r13
0x18000fd06  pop     r12
0x18000fd08  pop     rdi
0x18000fd09  pop     rsi
0x18000fd0a  pop     rbp
0x18000fd0b  pop     rbx
0x18000fd0c  retn
```
