# OfficeAddinPathAccessor::IsFileNameOfOfficeAddin(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004b950`
- end: `0x18004ba85`
- name: `?IsFileNameOfOfficeAddin@OfficeAddinPathAccessor@@UEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800020a0`
- `0x180002d1c`
- `0x180002d84`
- `0x18002589c`
- `0x18002649c`
- `0x18004b950`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004b9fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004b9fa`

## string_xrefs

- `0x18004ba3e`: `adxloader.dll`
- `0x18004ba54`: `adxloader64.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall OfficeAddinPathAccessor::IsFileNameOfOfficeAddin(__int64 a1, _QWORD *a2)
{
  int *v4; // rbx
  _QWORD *v5; // rsi
  _QWORD *i; // rbx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  _QWORD *v9; // rax
  _QWORD *v10; // rdx

  v4 = (int *)&unk_180097E80;
  if ( dword_180097E78 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180097E78);
    if ( dword_180097E78 == -1 )
    {
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
        &unk_180097E80,
        L"adxloader.dll",
        256);
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
        &unk_180097EA8,
        L"adxloader64.dll",
        256);
      atexit(OfficeAddinPathAccessor::IsFileNameOfOfficeAddin_::_2_::_dynamic_atexit_destructor_for__exceptions__);
      Init_thread_footer(&dword_180097E78);
    }
  }
  while ( !(unsigned __int8)std::regex_search<std::char_traits<unsigned short>,std::allocator<unsigned short>,unsigned short,std::regex_traits<unsigned short>>(
                              a2,
                              v4) )
  {
    v4 += 10;
    if ( v4 == &dword_180097ED0 )
    {
      v5 = *(_QWORD **)(a1 + 16);
      for ( i = (_QWORD *)*v5; i != v5; i = (_QWORD *)*i )
      {
        v7 = a2[2];
        v8 = i[4];
        if ( v8 >= v7 )
        {
          v9 = i + 2;
          v10 = a2[3] <= 7u ? a2 : (_QWORD *)*a2;
          if ( i[5] > 7u )
            v9 = (_QWORD *)*v9;
          if ( !(unsigned int)_o__wcsnicmp((char *)v9 + 2 * (v8 - v7), v10) )
            return 1;
        }
      }
      return 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004b950  push    rdi
0x18004b952  sub     rsp, 30h
0x18004b956  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18004b95f  mov     [rsp+38h+arg_0], rbx
0x18004b964  mov     [rsp+38h+arg_8], rsi
0x18004b969  mov     rdi, rdx
0x18004b96c  mov     rsi, rcx
0x18004b96f  mov     r8d, cs:_tls_index
0x18004b976  mov     rax, gs:58h
0x18004b97f  mov     ecx, 4
0x18004b984  mov     rax, [rax+r8*8]
0x18004b988  lea     rbx, unk_180097E80
0x18004b98f  mov     eax, [rcx+rax]
0x18004b992  cmp     cs:dword_180097E78, eax
0x18004b998  jg      loc_18004BA1F
0x18004b99e  mov     rdx, rbx
0x18004b9a1  mov     rcx, rdi
0x18004b9a4  call    ??$regex_search@U?$char_traits@G@std@@V?$allocator@G@2@GV?$regex_traits@G@2@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_search<std::char_traits<ushort>,std::allocator<ushort>,ushort,std::regex_traits<ushort>>(std::wstring const &,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type)
0x18004b9a9  test    al, al
0x18004b9ab  jnz     short loc_18004BA0D
0x18004b9ad  add     rbx, 28h ; '('
0x18004b9b1  lea     rax, dword_180097ED0
0x18004b9b8  cmp     rbx, rax
0x18004b9bb  jnz     short loc_18004B99E
0x18004b9bd  mov     rsi, [rsi+10h]
0x18004b9c1  mov     rbx, [rsi]
0x18004b9c4  cmp     rbx, rsi
0x18004b9c7  jz      short loc_18004BA0D
0x18004b9c9  mov     r8, [rdi+10h]
0x18004b9cd  mov     rcx, [rbx+20h]
0x18004b9d1  cmp     rcx, r8
0x18004b9d4  jb      short loc_18004BA04
0x18004b9d6  lea     rax, [rbx+10h]
0x18004b9da  cmp     qword ptr [rdi+18h], 7
0x18004b9df  jbe     short loc_18004B9E6
0x18004b9e1  mov     rdx, [rdi]
0x18004b9e4  jmp     short loc_18004B9E9
0x18004b9e6  mov     rdx, rdi
0x18004b9e9  cmp     qword ptr [rax+18h], 7
0x18004b9ee  jbe     short loc_18004B9F3
0x18004b9f0  mov     rax, [rax]
0x18004b9f3  sub     rcx, r8
0x18004b9f6  lea     rcx, [rax+rcx*2]
0x18004b9fa  call    cs:__imp__o__wcsnicmp
0x18004ba00  test    eax, eax
0x18004ba02  jz      short loc_18004BA09
0x18004ba04  mov     rbx, [rbx]
0x18004ba07  jmp     short loc_18004B9C4
0x18004ba09  mov     al, 1
0x18004ba0b  jmp     short loc_18004BA0F
0x18004ba0d  xor     al, al
0x18004ba0f  mov     rbx, [rsp+38h+arg_0]
0x18004ba14  mov     rsi, [rsp+38h+arg_8]
0x18004ba19  add     rsp, 30h
0x18004ba1d  pop     rdi
0x18004ba1e  retn
0x18004ba1f  lea     rcx, dword_180097E78
0x18004ba26  call    _Init_thread_header
0x18004ba2b  cmp     cs:dword_180097E78, 0FFFFFFFFh
0x18004ba32  jnz     loc_18004B99E
0x18004ba38  mov     r8d, 100h
0x18004ba3e  lea     rdx, aAdxloaderDll; "adxloader.dll"
0x18004ba45  mov     rcx, rbx
0x18004ba48  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x18004ba4d  nop
0x18004ba4e  mov     r8d, 100h
0x18004ba54  lea     rdx, aAdxloader64Dll; "adxloader64.dll"
0x18004ba5b  lea     rcx, unk_180097EA8
0x18004ba62  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x18004ba67  nop
0x18004ba68  lea     rcx, _OfficeAddinPathAccessor__IsFileNameOfOfficeAddin____2____dynamic_atexit_destructor_for__exceptions__; void (__cdecl *)()
0x18004ba6f  call    atexit
0x18004ba74  lea     rcx, dword_180097E78
0x18004ba7b  call    _Init_thread_footer
0x18004ba80  jmp     loc_18004B99E
```
