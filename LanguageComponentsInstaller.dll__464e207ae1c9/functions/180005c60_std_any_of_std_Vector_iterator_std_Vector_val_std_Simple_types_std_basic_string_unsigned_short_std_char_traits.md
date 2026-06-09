# std::any_of_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________lambda_66b8c4f79f3bf798e0a4948ec80e691d___

- ea: `0x180005c60`
- end: `0x180005d61`
- name: `std::any_of_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________lambda_66b8c4f79f3bf798e0a4948ec80e691d___`
- size: `257`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007594`

## callees

- `0x180003520`
- `0x180005c60`
- `0x180005d68`
- `0x180006380`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005ce4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005ce4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005cf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005cf9`
- `Bcp47Langs!Bcp47GetDistance` at `0x180005d0c`
- `Bcp47Langs!Bcp47GetDistance` at `0x180005d0c`

## pseudocode

```c
char __fastcall std::any_of_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________lambda_66b8c4f79f3bf798e0a4948ec80e691d___(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v5; // rsi
  __int64 v6; // rax
  char **v7; // r14
  const WCHAR *v8; // r15
  unsigned __int64 v9; // rbp
  char v10; // bp
  HSTRING string; // [rsp+20h] [rbp-98h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-90h] BYREF
  _BYTE v14[32]; // [rsp+40h] [rbp-78h] BYREF
  int v15; // [rsp+60h] [rbp-58h] BYREF

  v5 = a1;
  if ( a1 == a2 )
    return 0;
  while ( 1 )
  {
    v6 = std::wstring::wstring((__int64)v14, v5);
    v7 = (char **)v6;
    v15 = 0;
    if ( *(_QWORD *)(v6 + 24) <= 7u )
      v8 = (const WCHAR *)v6;
    else
      v8 = *(const WCHAR **)v6;
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    if ( v9 > 0xFFFFFFFF )
    {
      LODWORD(v9) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(v8, v9, &hstringHeader, &string);
    if ( (int)Bcp47GetDistance(*a3, string, &v15) < 0 || (v10 = 1, v15) )
      v10 = 0;
    std::wstring::~wstring(v7);
    if ( v10 )
      break;
    v5 += 32;
    if ( v5 == a2 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180005c60  push    rbx
0x180005c62  push    rbp
0x180005c63  push    rsi
0x180005c64  push    rdi
0x180005c65  push    r12
0x180005c67  push    r13
0x180005c69  push    r14
0x180005c6b  push    r15
0x180005c6d  sub     rsp, 78h
0x180005c71  mov     rax, cs:__security_cookie
0x180005c78  xor     rax, rsp
0x180005c7b  mov     [rsp+0B8h+var_50], rax
0x180005c80  mov     rdi, r8
0x180005c83  mov     rbx, rdx
0x180005c86  mov     rsi, rcx
0x180005c89  cmp     rcx, rdx
0x180005c8c  jz      loc_180005D3D
0x180005c92  xor     r12d, r12d
0x180005c95  mov     r13d, 0FFFFFFFFh
0x180005c9b  mov     rdx, rsi
0x180005c9e  lea     rcx, [rsp+0B8h+var_78]
0x180005ca3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180005ca8  mov     r14, rax
0x180005cab  mov     [rsp+0B8h+var_58], r12d
0x180005cb0  cmp     qword ptr [rax+18h], 7
0x180005cb5  jbe     short loc_180005CBC
0x180005cb7  mov     r15, [rax]
0x180005cba  jmp     short loc_180005CBF
0x180005cbc  mov     r15, r14
0x180005cbf  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180005cc3  inc     rbp
0x180005cc6  cmp     [r15+rbp*2], r12w
0x180005ccb  jnz     short loc_180005CC3
0x180005ccd  cmp     rbp, r13
0x180005cd0  jbe     short loc_180005CEA
0x180005cd2  xor     r9d, r9d; lpArguments
0x180005cd5  xor     r8d, r8d; nNumberOfArguments
0x180005cd8  mov     ecx, 0C000000Dh; dwExceptionCode
0x180005cdd  mov     ebp, r13d
0x180005ce0  lea     edx, [r9+1]; dwExceptionFlags
0x180005ce4  call    cs:__imp_RaiseException
0x180005cea  lea     r9, [rsp+0B8h+string]; string
0x180005cef  mov     edx, ebp; length
0x180005cf1  lea     r8, [rsp+0B8h+hstringHeader]; hstringHeader
0x180005cf6  mov     rcx, r15; sourceString
0x180005cf9  call    cs:__imp_WindowsCreateStringReference
0x180005cff  mov     rdx, [rsp+0B8h+string]
0x180005d04  lea     r8, [rsp+0B8h+var_58]
0x180005d09  mov     rcx, [rdi]
0x180005d0c  call    cs:__imp_Bcp47GetDistance
0x180005d12  test    eax, eax
0x180005d14  js      short loc_180005D20
0x180005d16  mov     bpl, 1
0x180005d19  cmp     [rsp+0B8h+var_58], r12d
0x180005d1e  jz      short loc_180005D23
0x180005d20  mov     bpl, r12b
0x180005d23  mov     rcx, r14; void *
0x180005d26  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180005d2b  test    bpl, bpl
0x180005d2e  jnz     short loc_180005D5D
0x180005d30  add     rsi, 20h ; ' '
0x180005d34  cmp     rsi, rbx
0x180005d37  jnz     loc_180005C9B
0x180005d3d  xor     al, al
0x180005d3f  mov     rcx, [rsp+0B8h+var_50]
0x180005d44  xor     rcx, rsp; StackCookie
0x180005d47  call    __security_check_cookie
0x180005d4c  add     rsp, 78h
0x180005d50  pop     r15
0x180005d52  pop     r14
0x180005d54  pop     r13
0x180005d56  pop     r12
0x180005d58  pop     rdi
0x180005d59  pop     rsi
0x180005d5a  pop     rbp
0x180005d5b  pop     rbx
0x180005d5c  retn
0x180005d5d  mov     al, 1
0x180005d5f  jmp     short loc_180005D3F
```
