# std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>::operator()(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000fe1c`
- end: `0x18000feb1`
- name: `??R?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z`
- size: `149`
- prototype: `bool __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011e50`
- `0x180012858`
- `0x180012ef8`

## callees

- `0x18000f744`
- `0x18000fe1c`
- `0x1800124fc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000fe78`
- `msvcrt!_wcsicmp` at `0x18000fe78`

## pseudocode

```c
bool __fastcall std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>::operator()(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rdi
  const wchar_t *v7; // rdx
  const wchar_t *v8; // rcx
  int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v13; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v14[40]; // [rsp+48h] [rbp-30h] BYREF

  v4 = std::wstring::wstring((__int64)&v13, a3);
  v5 = std::wstring::wstring((__int64)v14, a2);
  v6 = v5;
  if ( *(_QWORD *)(v4 + 24) < 8u )
    v7 = (const wchar_t *)v4;
  else
    v7 = *(const wchar_t **)v4;
  if ( *(_QWORD *)(v5 + 24) < 8u )
    v8 = (const wchar_t *)v5;
  else
    v8 = *(const wchar_t **)v5;
  v9 = _wcsicmp(v8, v7);
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(v6, v10, 0);
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(v4, v11, 0);
  return v9 != 0;
}

```

## disassembly

```asm
0x18000fe1c  mov     r11, rsp
0x18000fe1f  mov     [r11+10h], rbx
0x18000fe23  mov     [r11+18h], rsi
0x18000fe27  mov     [r11+8], rcx
0x18000fe2b  push    rdi
0x18000fe2c  sub     rsp, 70h
0x18000fe30  mov     rbx, rdx
0x18000fe33  lea     rax, [r11-58h]
0x18000fe37  mov     [r11+8], rax
0x18000fe3b  mov     rdx, r8
0x18000fe3e  lea     rcx, [r11-58h]
0x18000fe42  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000fe47  mov     rsi, rax
0x18000fe4a  mov     rdx, rbx
0x18000fe4d  lea     rcx, [rsp+78h+var_30]
0x18000fe52  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000fe57  mov     rdi, rax
0x18000fe5a  cmp     qword ptr [rsi+18h], 8
0x18000fe5f  jb      short loc_18000FE66
0x18000fe61  mov     rdx, [rsi]
0x18000fe64  jmp     short loc_18000FE69
0x18000fe66  mov     rdx, rsi; String2
0x18000fe69  cmp     qword ptr [rax+18h], 8
0x18000fe6e  jb      short loc_18000FE75
0x18000fe70  mov     rcx, [rax]
0x18000fe73  jmp     short loc_18000FE78
0x18000fe75  mov     rcx, rdi; String1
0x18000fe78  call    cs:__imp__wcsicmp
0x18000fe7e  mov     ebx, eax
0x18000fe80  xor     r8d, r8d
0x18000fe83  mov     dl, 1
0x18000fe85  mov     rcx, rdi
0x18000fe88  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000fe8d  xor     r8d, r8d
0x18000fe90  mov     dl, 1
0x18000fe92  mov     rcx, rsi
0x18000fe95  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000fe9a  test    ebx, ebx
0x18000fe9c  setnz   al
0x18000fe9f  lea     r11, [rsp+78h+var_8]
0x18000fea4  mov     rbx, [r11+18h]
0x18000fea8  mov     rsi, [r11+20h]
0x18000feac  mov     rsp, r11
0x18000feaf  pop     rdi
0x18000feb0  retn
```
