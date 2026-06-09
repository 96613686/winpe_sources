# RegistryKeyIterator::operator*(void)

- ea: `0x1800047e0`
- end: `0x180004bf8`
- name: `??DRegistryKeyIterator@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `1048`
- prototype: `unsigned __int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `5`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18000442c`
- `0x1800163d0`
- `0x180048af8`
- `0x18006f470`
- `0x18007f894`

## callees

- `0x1800047e0`
- `0x180005aa0`
- `0x180026a04`
- `0x180052698`
- `0x18005532c`
- `0x18005b034`
- `0x1800647e0`
- `0x18006480c`
- `0x180065035`
- `0x180065056`
- `0x180065062`
- `0x18006a070`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180004879`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180004879`

## pseudocode

```c
unsigned __int64 __fastcall RegistryKeyIterator::operator*(__int64 a1, unsigned __int64 a2)
{
  unsigned int v3; // eax
  signed int v4; // edi
  unsigned __int64 v5; // r14
  size_t v6; // rbp
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r12
  __int64 v9; // r8
  __int64 v10; // rcx
  _WORD *v11; // rsi
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rsi
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // r15
  unsigned __int64 v17; // r12
  unsigned __int64 v18; // r12
  unsigned __int64 v19; // rdi
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rcx
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rdx
  __int64 v28; // rcx
  unsigned __int64 v29; // rax
  __int64 v30; // rsi
  unsigned __int64 v31; // rdx
  unsigned __int64 v32; // rcx
  _WORD *v33; // rcx
  _BYTE pExceptionObject[208]; // [rsp+58h] [rbp-320h] BYREF
  DWORD cchName; // [rsp+128h] [rbp-250h] BYREF
  WCHAR Name[256]; // [rsp+130h] [rbp-248h] BYREF

  *(_QWORD *)(a2 + 24) = 7;
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)a2 = 0;
  cchName = 256;
  v3 = RegEnumKeyExW(**(HKEY **)a1, *(_DWORD *)(a1 + 8), Name, &cchName, 0, 0, 0, 0);
  v4 = v3;
  if ( v3 == 259 )
    return a2;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids, v3);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v4);
    throw (Win32Exception *)pExceptionObject;
  }
  v5 = cchName;
  v6 = 2LL * cchName;
  v7 = *(_QWORD *)(a2 + 24);
  v8 = *(_QWORD *)(a2 + 16);
  v9 = 2 * v8;
  if ( v7 < 8 )
  {
    v10 = v9 + a2;
    v11 = (_WORD *)a2;
  }
  else
  {
    v10 = v9 + *(_QWORD *)a2;
    v11 = *(_WORD **)a2;
  }
  if ( !v6 )
  {
    if ( v10 )
      v28 = (v10 - (__int64)v11) >> 1;
    else
      v28 = 0;
    if ( v7 < 8 )
      v29 = a2;
    else
      v29 = *(_QWORD *)a2;
    if ( v11 )
      v30 = (__int64)((__int64)v11 - v29) >> 1;
    else
      v30 = 0;
    std::wstring::erase(a2, v30, v28);
    return a2;
  }
  if ( v10 )
    v12 = (v10 - (__int64)v11) >> 1;
  else
    v12 = 0;
  if ( v7 < 8 )
    v13 = a2;
  else
    v13 = *(_QWORD *)a2;
  if ( v11 )
    v14 = (__int64)((__int64)v11 - v13) >> 1;
  else
    v14 = 0;
  if ( v7 < 8 )
    v15 = a2;
  else
    v15 = *(_QWORD *)a2;
  if ( (unsigned __int64)Name >= v15 )
  {
    v26 = v7 < 8 ? a2 : *(_QWORD *)a2;
    if ( v9 + v26 > (unsigned __int64)Name )
    {
      if ( v7 < 8 )
        v27 = a2;
      else
        v27 = *(_QWORD *)a2;
      std::wstring::replace(a2, v14, v12, a2, (__int64)((__int64)Name - v27) >> 1, cchName);
      return a2;
    }
  }
  if ( v8 < v14 )
    std::_Xout_of_range("invalid string position");
  v16 = v8 - v14;
  if ( v8 - v14 >= v12 )
    v16 = v12;
  v17 = v8 - v16;
  if ( -1LL - (unsigned __int64)cchName <= v17 )
    goto LABEL_39;
  v18 = v17 - v14;
  if ( cchName < v16 )
  {
    if ( v7 < 8 )
    {
      v31 = a2;
      v32 = a2;
    }
    else
    {
      v31 = *(_QWORD *)a2;
      v32 = *(_QWORD *)a2;
    }
    std::char_traits<wchar_t>::move(v32 + 2 * (cchName + v14), v31 + 2 * (v16 + v14), v18);
  }
  if ( !v5 && !v16 )
    return a2;
  v19 = v5 + *(_QWORD *)(a2 + 16) - v16;
  if ( v19 > 0x7FFFFFFFFFFFFFFELL )
LABEL_39:
    std::_Xlength_error("string too long");
  v20 = *(_QWORD *)(a2 + 24);
  if ( v20 >= v19 )
  {
    if ( !v19 )
    {
      if ( v20 < 8 )
        v33 = (_WORD *)a2;
      else
        v33 = *(_WORD **)a2;
      *(_QWORD *)(a2 + 16) = 0;
      *v33 = 0;
      return a2;
    }
  }
  else
  {
    std::wstring::_Copy(a2, v5 + *(_QWORD *)(a2 + 16) - v16, *(_QWORD *)(a2 + 16));
    if ( !v19 )
      return a2;
  }
  if ( v16 < v5 )
  {
    if ( *(_QWORD *)(a2 + 24) < 8u )
    {
      v21 = a2;
      v22 = a2;
    }
    else
    {
      v21 = *(_QWORD *)a2;
      v22 = *(_QWORD *)a2;
    }
    if ( v18 )
      memmove_0((void *)(v22 + 2 * (v5 + v14)), (const void *)(v21 + 2 * (v16 + v14)), 2 * v18);
  }
  if ( *(_QWORD *)(a2 + 24) < 8u )
    v23 = a2;
  else
    v23 = *(_QWORD *)a2;
  if ( v5 )
    memcpy_0((void *)(v23 + 2 * v14), Name, v6);
  if ( *(_QWORD *)(a2 + 24) < 8u )
    v24 = a2;
  else
    v24 = *(_QWORD *)a2;
  *(_QWORD *)(a2 + 16) = v19;
  *(_WORD *)(v24 + 2 * v19) = 0;
  return a2;
}

```

## disassembly

```asm
0x1800047e0  push    rbp
0x1800047e2  push    rsi
0x1800047e3  push    rdi
0x1800047e4  push    r12
0x1800047e6  push    r13
0x1800047e8  push    r14
0x1800047ea  push    r15
0x1800047ec  sub     rsp, 340h
0x1800047f3  mov     [rsp+378h+var_330], 0FFFFFFFFFFFFFFFEh
0x1800047fc  mov     [rsp+378h+arg_10], rbx
0x180004804  mov     rax, cs:__security_cookie
0x18000480b  xor     rax, rsp
0x18000480e  mov     [rsp+378h+var_48], rax
0x180004816  mov     rbx, rdx
0x180004819  mov     rdx, rcx
0x18000481c  mov     [rsp+378h+var_328], rbx
0x180004821  xor     r13d, r13d
0x180004824  mov     [rsp+378h+var_338], r13d
0x180004829  mov     qword ptr [rbx+18h], 7
0x180004831  mov     [rbx+10h], r13
0x180004835  mov     [rbx], r13w
0x180004839  mov     [rsp+378h+var_338], 1
0x180004841  mov     [rsp+378h+cchName], 100h
0x18000484c  mov     rcx, [rcx]
0x18000484f  mov     [rsp+378h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180004854  mov     [rsp+378h+lpcchClass], r13; lpcchClass
0x180004859  mov     [rsp+378h+lpClass], r13; lpClass
0x18000485e  mov     [rsp+378h+lpReserved], r13; lpReserved
0x180004863  lea     r9, [rsp+378h+cchName]; lpcchName
0x18000486b  lea     r8, [rsp+378h+Name]; lpName
0x180004873  mov     edx, [rdx+8]; dwIndex
0x180004876  mov     rcx, [rcx]; hKey
0x180004879  call    cs:__imp_RegEnumKeyExW
0x18000487f  mov     edi, eax
0x180004881  cmp     eax, 103h
0x180004886  jz      loc_1800049F4
0x18000488c  test    eax, eax
0x18000488e  jnz     loc_180004B8D
0x180004894  mov     r14d, [rsp+378h+cchName]
0x18000489c  lea     rbp, [r14+r14]
0x1800048a0  mov     rdx, [rbx+18h]
0x1800048a4  mov     r12, [rbx+10h]
0x1800048a8  lea     r8, [r12+r12]
0x1800048ac  cmp     rdx, 8
0x1800048b0  jb      loc_180004A8B
0x1800048b6  mov     rax, [rbx]
0x1800048b9  lea     rcx, [r8+rax]
0x1800048bd  mov     rsi, rax
0x1800048c0  test    rbp, rbp
0x1800048c3  jz      loc_180004AF8
0x1800048c9  test    rcx, rcx
0x1800048cc  jz      loc_180004AE8
0x1800048d2  sub     rcx, rsi
0x1800048d5  sar     rcx, 1
0x1800048d8  cmp     rdx, 8
0x1800048dc  jb      loc_180004A97
0x1800048e2  mov     rax, [rbx]
0x1800048e5  test    rsi, rsi
0x1800048e8  jz      loc_180004AF0
0x1800048ee  sub     rsi, rax
0x1800048f1  sar     rsi, 1
0x1800048f4  cmp     rdx, 8
0x1800048f8  jb      loc_180004A9F
0x1800048fe  mov     rax, [rbx]
0x180004901  lea     r9, [rsp+378h+Name]
0x180004909  cmp     r9, rax
0x18000490c  jnb     loc_180004A2F
0x180004912  cmp     r12, rsi
0x180004915  jb      loc_180004BDC
0x18000491b  mov     r15, r12
0x18000491e  sub     r15, rsi
0x180004921  cmp     r15, rcx
0x180004924  cmovnb  r15, rcx
0x180004928  sub     r12, r15
0x18000492b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004932  sub     rax, r14
0x180004935  cmp     rax, r12
0x180004938  jbe     loc_180004A22
0x18000493e  sub     r12, rsi
0x180004941  cmp     r14, r15
0x180004944  jb      loc_180004B41
0x18000494a  test    r14, r14
0x18000494d  jz      loc_180004BE9
0x180004953  mov     r8, [rbx+10h]
0x180004957  mov     rdi, r8
0x18000495a  sub     rdi, r15
0x18000495d  add     rdi, r14
0x180004960  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000496a  cmp     rdi, rax
0x18000496d  ja      loc_180004A22
0x180004973  mov     rax, [rbx+18h]
0x180004977  cmp     rax, rdi
0x18000497a  jnb     short loc_18000498E
0x18000497c  mov     rdx, rdi
0x18000497f  mov     rcx, rbx
0x180004982  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180004987  test    rdi, rdi
0x18000498a  jnz     short loc_180004997
0x18000498c  jmp     short loc_1800049F4
0x18000498e  test    rdi, rdi
0x180004991  jz      loc_180004B72
0x180004997  cmp     r15, r14
0x18000499a  jnb     short loc_1800049B6
0x18000499c  cmp     qword ptr [rbx+18h], 8
0x1800049a1  jb      loc_180004AB7
0x1800049a7  mov     rdx, [rbx]
0x1800049aa  mov     rcx, rdx
0x1800049ad  test    r12, r12
0x1800049b0  jnz     loc_180004AC2
0x1800049b6  cmp     qword ptr [rbx+18h], 8
0x1800049bb  jb      loc_180004AA7
0x1800049c1  mov     rax, [rbx]
0x1800049c4  test    r14, r14
0x1800049c7  jz      short loc_1800049DD
0x1800049c9  lea     rcx, [rax+rsi*2]; void *
0x1800049cd  mov     r8, rbp; Size
0x1800049d0  lea     rdx, [rsp+378h+Name]; Src
0x1800049d8  call    memcpy_0
0x1800049dd  cmp     qword ptr [rbx+18h], 8
0x1800049e2  jb      loc_180004AAF
0x1800049e8  mov     rcx, [rbx]
0x1800049eb  mov     [rbx+10h], rdi
0x1800049ef  mov     [rcx+rdi*2], r13w
0x1800049f4  mov     rax, rbx
0x1800049f7  mov     rcx, [rsp+378h+var_48]
0x1800049ff  xor     rcx, rsp; StackCookie
0x180004a02  call    __security_check_cookie
0x180004a07  mov     rbx, [rsp+378h+arg_10]
0x180004a0f  add     rsp, 340h
0x180004a16  pop     r15
0x180004a18  pop     r14
0x180004a1a  pop     r13
0x180004a1c  pop     r12
0x180004a1e  pop     rdi
0x180004a1f  pop     rsi
0x180004a20  pop     rbp
0x180004a21  retn
0x180004a22  lea     rcx, aStringTooLong; "string too long"
0x180004a29  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180004a2f  cmp     rdx, 8
0x180004a33  jb      loc_180004AE0
0x180004a39  mov     rax, [rbx]
0x180004a3c  add     rax, r8
0x180004a3f  lea     r8, [rsp+378h+Name]
0x180004a47  cmp     rax, r8
0x180004a4a  jbe     loc_180004912
0x180004a50  cmp     rdx, 8
0x180004a54  jb      loc_180004B39
0x180004a5a  mov     rdx, [rbx]
0x180004a5d  lea     rax, [rsp+378h+Name]
0x180004a65  sub     rax, rdx
0x180004a68  sar     rax, 1
0x180004a6b  mov     [rsp+378h+lpClass], r14
0x180004a70  mov     [rsp+378h+lpReserved], rax
0x180004a75  mov     r9, rbx
0x180004a78  mov     r8, rcx
0x180004a7b  mov     rdx, rsi
0x180004a7e  mov     rcx, rbx
0x180004a81  call    ?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z; std::wstring::replace(unsigned __int64,unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x180004a86  jmp     loc_1800049F4
0x180004a8b  lea     rcx, [r8+rbx]
0x180004a8f  mov     rsi, rbx
0x180004a92  jmp     loc_1800048C0
0x180004a97  mov     rax, rbx
0x180004a9a  jmp     loc_1800048E5
0x180004a9f  mov     rax, rbx
0x180004aa2  jmp     loc_180004901
0x180004aa7  mov     rax, rbx
0x180004aaa  jmp     loc_1800049C4
0x180004aaf  mov     rcx, rbx
0x180004ab2  jmp     loc_1800049EB
0x180004ab7  mov     rdx, rbx
0x180004aba  mov     rcx, rbx
0x180004abd  jmp     loc_1800049AD
0x180004ac2  lea     r8, [r12+r12]; Size
0x180004ac6  lea     rax, [r15+rsi]
0x180004aca  lea     rdx, [rdx+rax*2]; Src
0x180004ace  lea     rax, [r14+rsi]
0x180004ad2  lea     rcx, [rcx+rax*2]; void *
0x180004ad6  call    memmove_0
0x180004adb  jmp     loc_1800049B6
0x180004ae0  mov     rax, rbx
0x180004ae3  jmp     loc_180004A3C
0x180004ae8  mov     rcx, r13
0x180004aeb  jmp     loc_1800048D8
0x180004af0  mov     rsi, r13
0x180004af3  jmp     loc_1800048F4
0x180004af8  test    rcx, rcx
0x180004afb  jnz     short loc_180004B24
0x180004afd  mov     rcx, r13
0x180004b00  cmp     rdx, 8
0x180004b04  jb      short loc_180004B2C
0x180004b06  mov     rax, [rbx]
0x180004b09  test    rsi, rsi
0x180004b0c  jnz     short loc_180004B31
0x180004b0e  mov     rsi, r13
0x180004b11  mov     r8, rcx
0x180004b14  mov     rdx, rsi
0x180004b17  mov     rcx, rbx
0x180004b1a  call    ?erase@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x180004b1f  jmp     loc_1800049F4
0x180004b24  sub     rcx, rsi
0x180004b27  sar     rcx, 1
0x180004b2a  jmp     short loc_180004B00
0x180004b2c  mov     rax, rbx
0x180004b2f  jmp     short loc_180004B09
0x180004b31  sub     rsi, rax
0x180004b34  sar     rsi, 1
0x180004b37  jmp     short loc_180004B11
0x180004b39  mov     rdx, rbx
0x180004b3c  jmp     loc_180004A5D
0x180004b41  cmp     rdx, 8
0x180004b45  jb      short loc_180004B6A
0x180004b47  mov     rdx, [rbx]
0x180004b4a  mov     rcx, rdx
0x180004b4d  lea     rax, [r15+rsi]
0x180004b51  lea     rdx, [rdx+rax*2]
0x180004b55  lea     rax, [r14+rsi]
0x180004b59  lea     rcx, [rcx+rax*2]
0x180004b5d  mov     r8, r12
0x180004b60  call    ?move@?$char_traits@_W@std@@SAPEA_WPEA_WPEB_W_K@Z; std::char_traits<wchar_t>::move(wchar_t *,wchar_t const *,unsigned __int64)
0x180004b65  jmp     loc_18000494A
0x180004b6a  mov     rdx, rbx
0x180004b6d  mov     rcx, rbx
0x180004b70  jmp     short loc_180004B4D
0x180004b72  cmp     rax, 8
0x180004b76  jb      short loc_180004B88
0x180004b78  mov     rcx, [rbx]
0x180004b7b  mov     [rbx+10h], r13
0x180004b7f  mov     [rcx], r13w
0x180004b83  jmp     loc_1800049F4
0x180004b88  mov     rcx, rbx
0x180004b8b  jmp     short loc_180004B7B
0x180004b8d  lea     rax, WPP_GLOBAL_Control
0x180004b94  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b9b  cmp     rcx, rax
0x180004b9e  jz      short loc_180004BBE
0x180004ba0  cmp     byte ptr [rcx+19h], 2
0x180004ba4  jb      short loc_180004BBE
0x180004ba6  mov     edx, 0Bh
0x180004bab  mov     r9d, edi
0x180004bae  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x180004bb5  mov     rcx, [rcx+10h]
0x180004bb9  call    WPP_SF_d
0x180004bbe  mov     edx, edi; int
0x180004bc0  lea     rcx, [rsp+378h+pExceptionObject]; this
0x180004bc5  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180004bca  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180004bd1  lea     rcx, [rsp+378h+pExceptionObject]; pExceptionObject
0x180004bd6  call    _CxxThrowException_0
0x180004bdc  lea     rcx, aInvalidStringP; "invalid string position"
0x180004be3  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180004be9  test    r15, r15
0x180004bec  jz      loc_1800049F4
0x180004bf2  jmp     loc_180004953
```
