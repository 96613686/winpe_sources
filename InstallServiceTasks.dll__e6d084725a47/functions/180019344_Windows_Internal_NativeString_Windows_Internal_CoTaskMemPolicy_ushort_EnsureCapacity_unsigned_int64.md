# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180019344`
- end: `0x1800194ad`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `361`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014d8c`

## callees

- `0x180012494`
- `0x180012f10`
- `0x180019344`
- `0x1800194b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001941d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001941d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180019489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180019489`

## string_xrefs

- `0x1800193d1`: `Windows::Internal::NativeString<class Windows::Internal::CoTaskMemPolicy<unsigned short> >::_EnsureCapacity`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rbp
  int v4; // ebx
  unsigned __int64 v5; // r9
  _WORD *v6; // rax
  __int64 v7; // r9
  SIZE_T v8; // rsi
  LPVOID v9; // rax
  SIZE_T cb; // [rsp+88h] [rbp+10h] BYREF

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v5 = *(_QWORD *)(a1 + 16);
  if ( v5 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount();
    if ( *(_QWORD *)a1 )
      v5 = *(_QWORD *)(a1 + 8) + 1LL;
    else
      v5 = 0;
    *(_QWORD *)(a1 + 16) = v5;
  }
  if ( v5 )
  {
    v4 = 0;
    if ( v2 > v5 )
    {
      cb = 0;
      v4 = ULongLongMult(v5, 2u, &cb);
      if ( v4 >= 0 )
      {
        v8 = cb;
        if ( cb - v7 > 0x800 )
          v8 = v7 + 2048;
        if ( v2 > v8 )
          v8 = v2;
        v9 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v8);
        if ( v9 )
        {
          *(_QWORD *)(a1 + 16) = v8;
          *(_QWORD *)a1 = v9;
          return (unsigned int)v4;
        }
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    if ( *(_QWORD *)a1 )
      LogMessage(
        1u,
        "onecore\\internal\\shell\\inc\\WindowsInternalString.h",
        0x74Eu,
        "Windows::Internal::NativeString<class Windows::Internal::CoTaskMemPolicy<unsigned short> >::_EnsureCapacity",
        -1,
        L"Assert (%s): %s",
        0,
        0,
        L"_pszStringData == nullptr",
        L"Failed");
    cb = 0;
    v4 = ULongLongMult(v2, 2u, &cb);
    if ( v4 >= 0 )
    {
      v6 = CoTaskMemAlloc(cb);
      if ( v6 )
      {
        *(_QWORD *)(a1 + 16) = v2;
        *(_QWORD *)a1 = v6;
        *v6 = 0;
        return (unsigned int)v4;
      }
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180019344  push    rbx
0x180019346  push    rbp
0x180019347  push    rsi
0x180019348  push    rdi
0x180019349  sub     rsp, 58h
0x18001934d  lea     rbp, [rdx+1]
0x180019351  mov     rdi, rcx
0x180019354  cmp     rbp, rdx
0x180019357  jnb     short loc_180019363
0x180019359  mov     ebx, 80070216h
0x18001935e  jmp     loc_1800194A2
0x180019363  mov     r9, [rcx+10h]
0x180019367  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18001936b  jnz     short loc_180019388
0x18001936d  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180019372  cmp     qword ptr [rdi], 0
0x180019376  jz      short loc_180019381
0x180019378  mov     r9, [rdi+8]
0x18001937c  inc     r9
0x18001937f  jmp     short loc_180019384
0x180019381  xor     r9d, r9d
0x180019384  mov     [rdi+10h], r9
0x180019388  test    r9, r9
0x18001938b  jnz     loc_180019436
0x180019391  cmp     [rdi], r9
0x180019394  jz      short loc_1800193EA
0x180019396  lea     rax, aFailed; "Failed"
0x18001939d  mov     r8d, 74Eh; unsigned int
0x1800193a3  mov     [rsp+78h+var_30], rax
0x1800193a8  lea     rdx, aOnecoreInterna_3; "onecore\\internal\\shell\\inc\\WindowsI"...
0x1800193af  lea     rax, aPszstringdataN; "_pszStringData == nullptr"
0x1800193b6  mov     ecx, 1; unsigned int
0x1800193bb  mov     [rsp+78h+var_38], rax
0x1800193c0  lea     rax, aAssertSS; "Assert (%s): %s"
0x1800193c7  mov     [rsp+78h+var_40], r9; unsigned __int16 *
0x1800193cc  mov     [rsp+78h+var_48], r9; char *
0x1800193d1  lea     r9, aWindowsInterna; "Windows::Internal::NativeString<class W"...
0x1800193d8  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x1800193dd  mov     [rsp+78h+var_58], 0FFFFFFFFh; int
0x1800193e5  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800193ea  lea     r8, [rsp+78h+cb]; unsigned __int64 *
0x1800193f2  mov     [rsp+78h+cb], 0
0x1800193fe  mov     edx, 2; unsigned __int64
0x180019403  mov     rcx, rbp; unsigned __int64
0x180019406  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001940b  mov     ebx, eax
0x18001940d  test    eax, eax
0x18001940f  js      loc_1800194A2
0x180019415  mov     rcx, [rsp+78h+cb]; cb
0x18001941d  call    cs:__imp_CoTaskMemAlloc
0x180019423  test    rax, rax
0x180019426  jz      short loc_18001949D
0x180019428  xor     ecx, ecx
0x18001942a  mov     [rdi+10h], rbp
0x18001942e  mov     [rdi], rax
0x180019431  mov     [rax], cx
0x180019434  jmp     short loc_1800194A2
0x180019436  xor     ebx, ebx
0x180019438  cmp     rbp, r9
0x18001943b  jbe     short loc_1800194A2
0x18001943d  lea     r8, [rsp+78h+cb]; unsigned __int64 *
0x180019445  mov     [rsp+78h+cb], rbx
0x18001944d  lea     edx, [rbx+2]; unsigned __int64
0x180019450  mov     rcx, r9; unsigned __int64
0x180019453  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180019458  mov     ebx, eax
0x18001945a  test    eax, eax
0x18001945c  js      short loc_1800194A2
0x18001945e  mov     rsi, [rsp+78h+cb]
0x180019466  mov     rax, rsi
0x180019469  sub     rax, r9
0x18001946c  cmp     rax, 800h
0x180019472  jbe     short loc_18001947B
0x180019474  lea     rsi, [r9+800h]
0x18001947b  mov     rcx, [rdi]; pv
0x18001947e  cmp     rbp, rsi
0x180019481  cmova   rsi, rbp
0x180019485  lea     rdx, [rsi+rsi]; cb
0x180019489  call    cs:__imp_CoTaskMemRealloc
0x18001948f  test    rax, rax
0x180019492  jz      short loc_18001949D
0x180019494  mov     [rdi+10h], rsi
0x180019498  mov     [rdi], rax
0x18001949b  jmp     short loc_1800194A2
0x18001949d  mov     ebx, 8007000Eh
0x1800194a2  mov     eax, ebx
0x1800194a4  add     rsp, 58h
0x1800194a8  pop     rdi
0x1800194a9  pop     rsi
0x1800194aa  pop     rbp
0x1800194ab  pop     rbx
0x1800194ac  retn
```
