# SrSettings::CSrSettings::CheckDefaultValue(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180006c00`
- end: `0x180006df1`
- name: `?CheckDefaultValue@CSrSettings@SrSettings@@AEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18000a520`

## callees

- `0x180002178`
- `0x18000518c`
- `0x180006c00`
- `0x180009494`
- `0x180010a0c`
- `0x180011c80`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180006c91`
- `msvcrt!_wcsicmp` at `0x180006c91`

## string_xrefs

- `0x180006cca`: `Default value for setting %s not found in registry`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::CheckDefaultValue(__int64 a1, const wchar_t *a2, __int64 a3)
{
  unsigned __int64 v6; // r8
  unsigned int v7; // ebx
  const wchar_t **v8; // r14
  int DefaultValueFromRegistry; // eax
  unsigned int v10; // ebx
  __int64 v11; // rax
  void *v13[2]; // [rsp+30h] [rbp-20h] BYREF
  _WORD v14[8]; // [rsp+40h] [rbp-10h] BYREF

  v13[0] = v14;
  v13[1] = v14;
  v14[0] = 0;
  if ( a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
  }
  else
  {
    v6 = 0;
  }
  if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
         (__int64)v13,
         a2,
         v6) )
  {
    v7 = 0;
    while ( 1 )
    {
      v8 = (const wchar_t **)(&defaultSettingList + 4 * v7);
      if ( !_wcsicmp(a2, *v8) )
        break;
      if ( ++v7 >= 5 )
      {
        SrSettings::CSrSettings::Trace(a1, 2, L"Setting %s not found in default value table", a2);
LABEL_21:
        if ( v13[0] != v14 )
          operator delete(v13[0], (const struct std::nothrow_t *)&std::nothrow);
        return 2147942402LL;
      }
    }
    DefaultValueFromRegistry = SrSettings::CSrSettings::GetDefaultValueFromRegistry(a1, v8, a3);
    v10 = DefaultValueFromRegistry;
    if ( DefaultValueFromRegistry == 1 )
    {
      SrSettings::CSrSettings::Trace(a1, 0, L"Default value for setting %s not found in registry", a2);
      SrSettings::CSrSettings::Trace(a1, 0, L"Use default value in the table");
      if ( utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::_FindImpl<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>(
             a1 + 168,
             v13) == a1 + 168 )
      {
        SrSettings::CSrSettings::Trace(a1, 2, L"Default value for setting %s not found", a2);
        goto LABEL_21;
      }
      v11 = utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::_FindImpl<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>(
              a1 + 168,
              v13);
      if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
              a3,
              *(const void **)(v11 + 56),
              (__int64)(*(_QWORD *)(v11 + 64) - *(_QWORD *)(v11 + 56)) >> 1) )
      {
        SrSettings::CSrSettings::Trace(
          a1,
          2,
          L"Failed to assign default value to setting %s. Error: 0x%08x",
          a2,
          -2147024888);
        goto LABEL_16;
      }
      v10 = 0;
    }
    else if ( DefaultValueFromRegistry < 0 )
    {
      SrSettings::CSrSettings::Trace(
        a1,
        2,
        L"Failed to get default value for setting %s. Error: 0x%08x",
        a2,
        DefaultValueFromRegistry);
    }
    if ( v13[0] != v14 )
      operator delete(v13[0], (const struct std::nothrow_t *)&std::nothrow);
    return v10;
  }
  else
  {
    SrSettings::CSrSettings::Trace(a1, 2, L"Failed to assign setting name to string. Error: 0x%08x", 2147942408LL);
LABEL_16:
    if ( v13[0] != v14 )
      operator delete(v13[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942408LL;
  }
}

```

## disassembly

```asm
0x180006c00  push    rbp
0x180006c02  push    rbx
0x180006c03  push    rsi
0x180006c04  push    rdi
0x180006c05  push    r12
0x180006c07  push    r14
0x180006c09  push    r15
0x180006c0b  mov     rbp, rsp
0x180006c0e  sub     rsp, 50h
0x180006c12  mov     r15, r8
0x180006c15  mov     rdi, rdx
0x180006c18  mov     rsi, rcx
0x180006c1b  lea     rax, [rbp+var_10]
0x180006c1f  mov     [rbp+var_20], rax
0x180006c23  lea     rax, [rbp+var_10]
0x180006c27  mov     [rbp+var_18], rax
0x180006c2b  xor     r12d, r12d
0x180006c2e  mov     [rbp+var_10], r12w
0x180006c33  test    rdx, rdx
0x180006c36  jz      short loc_180006C48
0x180006c38  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006c3c  inc     r8
0x180006c3f  cmp     [rdx+r8*2], r12w
0x180006c44  jnz     short loc_180006C3C
0x180006c46  jmp     short loc_180006C4B
0x180006c48  mov     r8, r12
0x180006c4b  lea     rcx, [rbp+var_20]
0x180006c4f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180006c54  test    al, al
0x180006c56  jnz     short loc_180006C77
0x180006c58  mov     r9d, 80070008h
0x180006c5e  lea     r8, aFailedToAssign_1; "Failed to assign setting name to string"...
0x180006c65  mov     edx, 2
0x180006c6a  mov     rcx, rsi
0x180006c6d  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180006c72  jmp     loc_180006D4A
0x180006c77  mov     ebx, r12d
0x180006c7a  mov     r14d, ebx
0x180006c7d  shl     r14, 5
0x180006c81  lea     rcx, ?defaultSettingList@@3PAUDEFAULT_SETTING_VALUE@SrSettings@@A; SrSettings::DEFAULT_SETTING_VALUE near * defaultSettingList
0x180006c88  add     r14, rcx
0x180006c8b  mov     rdx, [r14]; String2
0x180006c8e  mov     rcx, rdi; String1
0x180006c91  call    cs:__imp__wcsicmp
0x180006c97  test    eax, eax
0x180006c99  jz      short loc_180006CAE
0x180006c9b  inc     ebx
0x180006c9d  cmp     ebx, 5
0x180006ca0  jb      short loc_180006C7A
0x180006ca2  lea     r8, aSettingSNotFou_2; "Setting %s not found in default value t"...
0x180006ca9  jmp     loc_180006D76
0x180006cae  mov     r8, r15
0x180006cb1  mov     rdx, r14
0x180006cb4  mov     rcx, rsi
0x180006cb7  call    ?GetDefaultValueFromRegistry@CSrSettings@SrSettings@@AEAAJAEBUDEFAULT_SETTING_VALUE@2@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SrSettings::CSrSettings::GetDefaultValueFromRegistry(SrSettings::DEFAULT_SETTING_VALUE const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180006cbc  mov     ebx, eax
0x180006cbe  cmp     eax, 1
0x180006cc1  jnz     loc_180006DA7
0x180006cc7  mov     r9, rdi
0x180006cca  lea     r8, aDefaultValueFo; "Default value for setting %s not found "...
0x180006cd1  xor     edx, edx
0x180006cd3  mov     rcx, rsi
0x180006cd6  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180006cdb  lea     r8, aUseDefaultValu; "Use default value in the table"
0x180006ce2  xor     edx, edx
0x180006ce4  mov     rcx, rsi
0x180006ce7  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180006cec  lea     rbx, [rsi+0A8h]
0x180006cf3  lea     rdx, [rbp+var_20]
0x180006cf7  mov     rcx, rbx
0x180006cfa  call    ??$_FindImpl@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@1@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::_FindImpl<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180006cff  cmp     rax, rbx
0x180006d02  jz      short loc_180006D6F
0x180006d04  lea     rdx, [rbp+var_20]
0x180006d08  mov     rcx, rbx
0x180006d0b  call    ??$_FindImpl@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@1@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::_FindImpl<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180006d10  mov     rdx, [rax+38h]
0x180006d14  mov     r8, [rax+40h]
0x180006d18  sub     r8, rdx
0x180006d1b  sar     r8, 1
0x180006d1e  mov     rcx, r15
0x180006d21  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180006d26  test    al, al
0x180006d28  jnz     short loc_180006D6A
0x180006d2a  mov     [rsp+50h+var_30], 80070008h
0x180006d32  mov     r9, rdi
0x180006d35  lea     r8, aFailedToAssign_9; "Failed to assign default value to setti"...
0x180006d3c  mov     edx, 2
0x180006d41  mov     rcx, rsi
0x180006d44  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180006d49  nop
0x180006d4a  lea     rax, [rbp+var_10]
0x180006d4e  mov     rcx, [rbp+var_20]; void *
0x180006d52  cmp     rcx, rax
0x180006d55  jz      short loc_180006D63
0x180006d57  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006d5e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006d63  mov     eax, 80070008h
0x180006d68  jmp     short loc_180006DE2
0x180006d6a  mov     ebx, r12d
0x180006d6d  jmp     short loc_180006DC7
0x180006d6f  lea     r8, aDefaultValueFo_0; "Default value for setting %s not found"
0x180006d76  mov     r9, rdi
0x180006d79  mov     edx, 2
0x180006d7e  mov     rcx, rsi
0x180006d81  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180006d86  nop
0x180006d87  lea     rax, [rbp+var_10]
0x180006d8b  mov     rcx, [rbp+var_20]; void *
0x180006d8f  cmp     rcx, rax
0x180006d92  jz      short loc_180006DA0
0x180006d94  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006d9b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006da0  mov     eax, 80070002h
0x180006da5  jmp     short loc_180006DE2
0x180006da7  test    ebx, ebx
0x180006da9  jns     short loc_180006DC7
0x180006dab  mov     [rsp+50h+var_30], ebx
0x180006daf  mov     r9, rdi
0x180006db2  lea     r8, aFailedToGetDef; "Failed to get default value for setting"...
0x180006db9  mov     edx, 2
0x180006dbe  mov     rcx, rsi
0x180006dc1  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180006dc6  nop
0x180006dc7  lea     rax, [rbp+var_10]
0x180006dcb  mov     rcx, [rbp+var_20]; void *
0x180006dcf  cmp     rcx, rax
0x180006dd2  jz      short loc_180006DE0
0x180006dd4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006ddb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006de0  mov     eax, ebx
0x180006de2  add     rsp, 50h
0x180006de6  pop     r15
0x180006de8  pop     r14
0x180006dea  pop     r12
0x180006dec  pop     rdi
0x180006ded  pop     rsi
0x180006dee  pop     rbx
0x180006def  pop     rbp
0x180006df0  retn
```
