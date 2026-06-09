# DedupUtil::IsVolumeRootPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140067588`
- end: `0x1400676ac`
- name: `?IsVolumeRootPath@DedupUtil@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `292`
- prototype: `bool __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400674e0`

## callees

- `0x140004870`
- `0x140015f60`
- `0x140019504`
- `0x140019600`
- `0x14001983c`
- `0x1400198e4`
- `0x140063e60`
- `0x140067588`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140067674`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140067674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006760d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006760d`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400675fd`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400675fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall DedupUtil::IsVolumeRootPath(__int64 a1)
{
  WCHAR *v3; // rax
  LPCWSTR v4; // r9
  int v5; // edx
  int v6; // ecx
  __int64 v7; // rax
  __int64 v8; // r8
  bool v9; // bl
  DWORD LastError; // [rsp+30h] [rbp-40h] BYREF
  __int64 v11; // [rsp+38h] [rbp-38h] BYREF
  __int64 v12; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v13[16]; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v14; // [rsp+58h] [rbp-18h]

  if ( !*(_QWORD *)(a1 + 16) )
    return 0;
  std::wstring::wstring(v13);
  if ( v14 < 0x105 )
    std::wstring::append(v13, 261 - v14);
  else
    std::wstring::_Eos(v13);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v3 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
  if ( !GetVolumePathNameW(v4, v3, 0x104u) )
  {
    LastError = GetLastError();
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
    v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    DedupUtil::Print<unsigned short const *,unsigned short const *,unsigned long>(
      v6,
      v5,
      (unsigned int)&v12,
      (unsigned int)&v11,
      (__int64)&LastError);
    std::wstring::_Tidy_deallocate(v13);
    return 0;
  }
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
  v9 = (unsigned int)_o__wcsicmp(v8, v7) == 0;
  std::wstring::_Tidy_deallocate(v13);
  return v9;
}

```

## disassembly

```asm
0x140067588  mov     [rsp-8+arg_8], rbx
0x14006758d  push    rbp
0x14006758e  mov     rbp, rsp
0x140067591  sub     rsp, 70h
0x140067595  mov     rax, cs:__security_cookie
0x14006759c  xor     rax, rsp
0x14006759f  mov     [rbp+var_8], rax
0x1400675a3  mov     rbx, rcx
0x1400675a6  cmp     qword ptr [rcx+10h], 0
0x1400675ab  jnz     short loc_1400675B4
0x1400675ad  xor     al, al
0x1400675af  jmp     loc_140067691
0x1400675b4  lea     rcx, [rbp+var_28]
0x1400675b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400675bd  nop
0x1400675be  mov     edx, 105h
0x1400675c3  lea     rcx, [rbp+var_28]
0x1400675c7  cmp     [rbp+var_18], rdx
0x1400675cb  jb      short loc_1400675D4
0x1400675cd  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1400675d2  jmp     short loc_1400675DD
0x1400675d4  sub     rdx, [rbp+var_18]
0x1400675d8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x1400675dd  mov     rcx, rbx
0x1400675e0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400675e5  mov     r9, rax
0x1400675e8  lea     rcx, [rbp+var_28]
0x1400675ec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400675f1  mov     rdx, rax; lpszVolumePathName
0x1400675f4  mov     r8d, 104h; cchBufferLength
0x1400675fa  mov     rcx, r9; lpszFileName
0x1400675fd  call    cs:__imp_GetVolumePathNameW
0x140067604  nop     dword ptr [rax+rax+00h]
0x140067609  test    eax, eax
0x14006760b  jnz     short loc_14006765A
0x14006760d  call    cs:__imp_GetLastError
0x140067614  nop     dword ptr [rax+rax+00h]
0x140067619  mov     [rbp+var_40], eax
0x14006761c  lea     rcx, [rbp+var_28]
0x140067620  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140067625  mov     [rbp+var_38], rax
0x140067629  mov     rcx, rbx
0x14006762c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140067631  mov     [rbp+var_30], rax
0x140067635  lea     rax, [rbp+var_40]
0x140067639  mov     [rsp+70h+var_50], rax
0x14006763e  lea     r9, [rbp+var_38]
0x140067642  lea     r8, [rbp+var_30]
0x140067646  call    ??$Print@PEBGPEBGK@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBG2$$QEAK@Z; DedupUtil::Print<ushort const *,ushort const *,ulong>(DedupUtil::MessageType,ushort const *,ushort const * &&,ushort const * &&,ulong &&)
0x14006764b  nop
0x14006764c  lea     rcx, [rbp+var_28]
0x140067650  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140067655  jmp     loc_1400675AD
0x14006765a  mov     rcx, rbx
0x14006765d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140067662  mov     r8, rax
0x140067665  lea     rcx, [rbp+var_28]
0x140067669  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006766e  mov     rdx, rax
0x140067671  mov     rcx, r8
0x140067674  call    cs:__imp__o__wcsicmp
0x14006767b  nop     dword ptr [rax+rax+00h]
0x140067680  nop
0x140067681  test    eax, eax
0x140067683  setz    bl
0x140067686  lea     rcx, [rbp+var_28]
0x14006768a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006768f  mov     al, bl
0x140067691  mov     rcx, [rbp+var_8]
0x140067695  xor     rcx, rsp; StackCookie
0x140067698  call    __security_check_cookie
0x14006769d  mov     rbx, [rsp+70h+arg_8]
0x1400676a5  add     rsp, 70h
0x1400676a9  pop     rbp
0x1400676aa  retn
```
