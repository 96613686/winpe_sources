# _lambda_ce1a4b9cfbb1ac9495ae9aa2fdb3ea16_::operator()

- ea: `0x18001c8f0`
- end: `0x18001cb6a`
- name: `_lambda_ce1a4b9cfbb1ac9495ae9aa2fdb3ea16_::operator()`
- size: `634`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18001b80c`

## callees

- `0x18001c2bc`
- `0x18001c448`
- `0x18001c8f0`
- `0x18001ee18`
- `0x18001f008`
- `0x18001f0c0`
- `0x18001f47c`
- `0x180032728`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18001cb05`
- `KERNEL32!CopyFileW` at `0x18001cb05`
- `KERNEL32!GetFileAttributesW` at `0x18001c9c2`
- `KERNEL32!GetFileAttributesW` at `0x18001c9c2`
- `KERNEL32!CreateDirectoryW` at `0x18001c9ac`
- `KERNEL32!CreateDirectoryW` at `0x18001c9ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_ce1a4b9cfbb1ac9495ae9aa2fdb3ea16_::operator()(_QWORD **a1, int a2, _QWORD *a3)
{
  unsigned int v5; // ebx
  _QWORD *v6; // rax
  const WCHAR *v7; // rdi
  unsigned __int64 v8; // r8
  const WCHAR *v9; // rax
  __int64 v10; // rdx
  const WCHAR *v11; // rax
  DWORD FileAttributesW; // eax
  WCHAR *v13; // rax
  _QWORD *v14; // rcx
  _QWORD *v15; // rax
  const WCHAR *v16; // rdi
  _QWORD *v17; // rax
  const WCHAR *v18; // rcx
  unsigned __int64 v19; // rax
  __int64 v20; // rcx
  _QWORD *v21; // rax
  _QWORD *v22; // rcx
  unsigned __int64 v23; // rax
  const WCHAR *v24; // rax
  LPCWSTR v25; // rdx
  __int64 v26; // rdx
  WCHAR *v27; // rax
  _QWORD v29[2]; // [rsp+28h] [rbp-48h] BYREF
  __int64 v30; // [rsp+38h] [rbp-38h]
  _QWORD v31[4]; // [rsp+48h] [rbp-28h] BYREF

  if ( a2 )
  {
    if ( a2 != 2 )
      return 0;
    std::wstring::wstring(v31, *a1);
    v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
    v16 = L"\\";
    if ( *((_WORD *)v15 + v31[2] - 1) == 92
      || !(*a1)[2]
      || (v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*a1), v18 = L"\\", *(_WORD *)v17 == 92) )
    {
      v18 = &cchOriginalDestLength;
    }
    v19 = std::char_traits<unsigned short>::length(v18);
    std::wstring::append(v31, v20, v19);
    std::wstring::append(v31, a3, 0, -1);
    std::wstring::wstring(v29, a1[1]);
    v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    if ( *((_WORD *)v21 + v30 - 1) == 92
      || (v22 = a1[1], !v22[2])
      || *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22) == 92 )
    {
      v16 = &cchOriginalDestLength;
    }
    v23 = std::char_traits<unsigned short>::length(v16);
    std::wstring::append(v29, (__int64)v16, v23);
    std::wstring::append(v29, a3, 0, -1);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
    v5 = !CopyFileW(v24, v25, 0) ? 0x80004005 : 0;
    if ( *((_BYTE *)a1 + 16) )
    {
      v27 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
      winreSetACL(v27);
    }
    std::wstring::~wstring((__int64)v29, v26);
    v14 = v31;
  }
  else
  {
    v5 = 0;
    std::wstring::wstring(v29, a1[1]);
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    if ( *((_WORD *)v6 + v30 - 1) == 92
      || !a3[2]
      || (v7 = L"\\", *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3) == 92) )
    {
      v7 = &cchOriginalDestLength;
    }
    v8 = std::char_traits<unsigned short>::length(v7);
    std::wstring::append(v29, (__int64)v7, v8);
    std::wstring::append(v29, a3, 0, -1);
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    if ( !CreateDirectoryW(v9, 0) )
    {
      v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
      FileAttributesW = GetFileAttributesW(v11);
      if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
        v5 = -2147467259;
      else
        v5 = 0;
    }
    if ( *((_BYTE *)a1 + 16) && a3[2] )
    {
      v13 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
      winreSetACL(v13);
    }
    v14 = v29;
  }
  std::wstring::~wstring((__int64)v14, v10);
  return v5;
}

```

## disassembly

```asm
0x18001c8f0  mov     rax, rsp
0x18001c8f3  push    rbp
0x18001c8f4  push    rdi
0x18001c8f5  push    r14
0x18001c8f7  mov     rbp, rsp
0x18001c8fa  sub     rsp, 70h
0x18001c8fe  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x18001c906  mov     [rax+10h], rbx
0x18001c90a  mov     [rax+20h], rsi
0x18001c90e  mov     rax, cs:__security_cookie
0x18001c915  xor     rax, rsp
0x18001c918  mov     [rbp+var_8], rax
0x18001c91c  mov     r14, r8
0x18001c91f  mov     rsi, rcx
0x18001c922  test    edx, edx
0x18001c924  jnz     loc_18001CA02
0x18001c92a  xor     ebx, ebx
0x18001c92c  mov     rdx, [rcx+8]
0x18001c930  lea     rcx, [rbp+var_48]
0x18001c934  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001c939  nop
0x18001c93a  lea     rcx, [rbp+var_48]
0x18001c93e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c943  mov     rdx, rax
0x18001c946  mov     rax, [rbp+var_38]
0x18001c94a  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x18001c950  jz      short loc_18001C96D
0x18001c952  cmp     [r14+10h], rbx
0x18001c956  jz      short loc_18001C96D
0x18001c958  mov     rcx, r14
0x18001c95b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c960  cmp     word ptr [rax], 5Ch ; '\'
0x18001c964  lea     rdi, pszSrc; "\\"
0x18001c96b  jnz     short loc_18001C974
0x18001c96d  lea     rdi, cchOriginalDestLength
0x18001c974  mov     rcx, rdi
0x18001c977  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001c97c  mov     r8, rax
0x18001c97f  mov     rdx, rdi
0x18001c982  lea     rcx, [rbp+var_48]
0x18001c986  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18001c98b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001c98f  xor     r8d, r8d
0x18001c992  mov     rdx, r14
0x18001c995  lea     rcx, [rbp+var_48]
0x18001c999  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001c99e  lea     rcx, [rbp+var_48]
0x18001c9a2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c9a7  mov     rcx, rax; lpPathName
0x18001c9aa  xor     edx, edx; lpSecurityAttributes
0x18001c9ac  call    cs:__imp_CreateDirectoryW
0x18001c9b2  test    eax, eax
0x18001c9b4  jnz     short loc_18001C9DA
0x18001c9b6  lea     rcx, [rbp+var_48]
0x18001c9ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c9bf  mov     rcx, rax; lpFileName
0x18001c9c2  call    cs:__imp_GetFileAttributesW
0x18001c9c8  cmp     eax, 0FFFFFFFFh
0x18001c9cb  jz      short loc_18001C9D5
0x18001c9cd  test    al, 10h
0x18001c9cf  jz      short loc_18001C9D5
0x18001c9d1  xor     ebx, ebx
0x18001c9d3  jmp     short loc_18001C9DA
0x18001c9d5  mov     ebx, 80004005h
0x18001c9da  cmp     byte ptr [rsi+10h], 0
0x18001c9de  jz      short loc_18001C9F9
0x18001c9e0  cmp     qword ptr [r14+10h], 0
0x18001c9e5  jz      short loc_18001C9F9
0x18001c9e7  lea     rcx, [rbp+var_48]
0x18001c9eb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c9f0  mov     rcx, rax; lpFileName
0x18001c9f3  call    winreSetACL
0x18001c9f8  nop
0x18001c9f9  lea     rcx, [rbp+var_48]
0x18001c9fd  jmp     loc_18001CB3E
0x18001ca02  cmp     edx, 2
0x18001ca05  jnz     loc_18001CB45
0x18001ca0b  mov     rdx, [rcx]
0x18001ca0e  lea     rcx, [rbp+var_28]
0x18001ca12  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ca17  nop
0x18001ca18  lea     rcx, [rbp+var_28]
0x18001ca1c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ca21  mov     rdx, rax
0x18001ca24  lea     rdi, pszSrc; "\\"
0x18001ca2b  mov     rax, [rbp+var_18]
0x18001ca2f  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x18001ca35  jz      short loc_18001CA4F
0x18001ca37  mov     rcx, [rsi]
0x18001ca3a  cmp     qword ptr [rcx+10h], 0
0x18001ca3f  jz      short loc_18001CA4F
0x18001ca41  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ca46  cmp     word ptr [rax], 5Ch ; '\'
0x18001ca4a  mov     rcx, rdi
0x18001ca4d  jnz     short loc_18001CA56
0x18001ca4f  lea     rcx, cchOriginalDestLength
0x18001ca56  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001ca5b  mov     r8, rax
0x18001ca5e  mov     rdx, rcx
0x18001ca61  lea     rcx, [rbp+var_28]
0x18001ca65  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18001ca6a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001ca6e  xor     r8d, r8d
0x18001ca71  mov     rdx, r14
0x18001ca74  lea     rcx, [rbp+var_28]
0x18001ca78  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001ca7d  mov     rdx, [rsi+8]
0x18001ca81  lea     rcx, [rbp+var_48]
0x18001ca85  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ca8a  nop
0x18001ca8b  lea     rcx, [rbp+var_48]
0x18001ca8f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ca94  mov     rdx, rax
0x18001ca97  mov     rax, [rbp+var_38]
0x18001ca9b  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x18001caa1  jz      short loc_18001CAB9
0x18001caa3  mov     rcx, [rsi+8]
0x18001caa7  cmp     qword ptr [rcx+10h], 0
0x18001caac  jz      short loc_18001CAB9
0x18001caae  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cab3  cmp     word ptr [rax], 5Ch ; '\'
0x18001cab7  jnz     short loc_18001CAC0
0x18001cab9  lea     rdi, cchOriginalDestLength
0x18001cac0  mov     rcx, rdi
0x18001cac3  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001cac8  mov     r8, rax
0x18001cacb  mov     rdx, rdi
0x18001cace  lea     rcx, [rbp+var_48]
0x18001cad2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18001cad7  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001cadb  xor     r8d, r8d
0x18001cade  mov     rdx, r14
0x18001cae1  lea     rcx, [rbp+var_48]
0x18001cae5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001caea  lea     rcx, [rbp+var_48]
0x18001caee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001caf3  mov     rdx, rax
0x18001caf6  lea     rcx, [rbp+var_28]
0x18001cafa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001caff  mov     rcx, rax; lpExistingFileName
0x18001cb02  xor     r8d, r8d; bFailIfExists
0x18001cb05  call    cs:__imp_CopyFileW
0x18001cb0b  neg     eax
0x18001cb0d  sbb     ecx, ecx
0x18001cb0f  not     ecx
0x18001cb11  mov     ebx, 80004005h
0x18001cb16  and     ebx, ecx
0x18001cb18  cmp     byte ptr [rsi+10h], 0
0x18001cb1c  jz      short loc_18001CB30
0x18001cb1e  lea     rcx, [rbp+var_48]
0x18001cb22  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cb27  mov     rcx, rax; lpFileName
0x18001cb2a  call    winreSetACL
0x18001cb2f  nop
0x18001cb30  lea     rcx, [rbp+var_48]
0x18001cb34  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cb39  nop
0x18001cb3a  lea     rcx, [rbp+var_28]
0x18001cb3e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cb43  jmp     short loc_18001CB47
0x18001cb45  xor     ebx, ebx
0x18001cb47  mov     eax, ebx
0x18001cb49  mov     rcx, [rbp+var_8]
0x18001cb4d  xor     rcx, rsp; StackCookie
0x18001cb50  call    __security_check_cookie
0x18001cb55  lea     r11, [rsp+70h+var_s0]
0x18001cb5a  mov     rbx, [r11+28h]
0x18001cb5e  mov     rsi, [r11+38h]
0x18001cb62  mov     rsp, r11
0x18001cb65  pop     r14
0x18001cb67  pop     rdi
0x18001cb68  pop     rbp
0x18001cb69  retn
```
