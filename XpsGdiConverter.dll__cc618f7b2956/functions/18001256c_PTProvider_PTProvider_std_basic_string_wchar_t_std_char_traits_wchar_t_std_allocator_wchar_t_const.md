# PTProvider::PTProvider(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18001256c`
- end: `0x1800125d8`
- name: `??0PTProvider@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `108`
- prototype: `__int64 __fastcall(HPTPROVIDER *phProvider)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800108f4`

## callees

- `0x18001256c`
- `0x180012704`
- `0x180037278`

## import_xrefs

- `prntvpt!__imp_PTQuerySchemaVersionSupport` at `0x180012594`
- `prntvpt!__imp_PTQuerySchemaVersionSupport` at `0x180012594`
- `prntvpt!__imp_PTOpenProvider` at `0x1800125b8`
- `prntvpt!__imp_PTOpenProvider` at `0x1800125b8`

## pseudocode

```c
HPTPROVIDER *__fastcall PTProvider::PTProvider(HPTPROVIDER *phProvider, __int64 a2)
{
  const WCHAR *v4; // rax
  HRESULT v5; // eax
  int v6; // edx
  const char *v7; // r8
  int v8; // r9d
  const WCHAR *v9; // rax
  HRESULT v10; // eax
  int v11; // edx
  const char *v12; // r8
  int v13; // r9d
  DWORD pMaxVersion; // [rsp+38h] [rbp+10h] BYREF

  pMaxVersion = 1;
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  v5 = PTQuerySchemaVersionSupport(v4, &pMaxVersion);
  if ( v5 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v5, v6, v7, v8);
  v9 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  v10 = PTOpenProvider(v9, pMaxVersion, phProvider);
  if ( v10 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v10, v11, v12, v13);
  return phProvider;
}

```

## disassembly

```asm
0x18001256c  mov     [rsp+arg_0], rbx
0x180012571  push    rdi
0x180012572  sub     rsp, 20h
0x180012576  mov     rbx, rcx
0x180012579  mov     [rsp+28h+pMaxVersion], 1
0x180012581  mov     rcx, rdx
0x180012584  mov     rdi, rdx
0x180012587  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001258c  mov     rcx, rax; pszPrinterName
0x18001258f  lea     rdx, [rsp+28h+pMaxVersion]; pMaxVersion
0x180012594  call    cs:__imp_PTQuerySchemaVersionSupport
0x18001259a  test    eax, eax
0x18001259c  jns     short loc_1800125A6
0x18001259e  mov     ecx, eax; this
0x1800125a0  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800125a6  mov     rcx, rdi
0x1800125a9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800125ae  mov     edx, [rsp+28h+pMaxVersion]; dwVersion
0x1800125b2  mov     rcx, rax; pszPrinterName
0x1800125b5  mov     r8, rbx; phProvider
0x1800125b8  call    cs:__imp_PTOpenProvider
0x1800125be  test    eax, eax
0x1800125c0  jns     short loc_1800125CA
0x1800125c2  mov     ecx, eax; this
0x1800125c4  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800125ca  mov     rax, rbx
0x1800125cd  mov     rbx, [rsp+28h+arg_0]
0x1800125d2  add     rsp, 20h
0x1800125d6  pop     rdi
0x1800125d7  retn
```
