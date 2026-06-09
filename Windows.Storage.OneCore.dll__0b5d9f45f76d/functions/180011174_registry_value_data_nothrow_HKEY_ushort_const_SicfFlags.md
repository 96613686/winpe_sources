# registry_value_data_nothrow(HKEY__ *,ushort const *,SicfFlags *)

- ea: `0x180011174`
- end: `0x180011213`
- name: `?registry_value_data_nothrow@@YAJPEAUHKEY__@@PEBGPEAW4SicfFlags@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, enum SicfFlags *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e2fc`
- `0x18000fa4c`

## callees

- `0x180007fac`
- `0x180011174`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800111be`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800111be`

## string_xrefs

- `0x1800111cf`: `onecore\base\windows.storage\src\Registry.h`
- `0x1800111e8`: `onecore\base\windows.storage\src\accesslistreadcache.cpp`

## pseudocode

```c
__int64 __fastcall registry_value_data_nothrow(HKEY a1, const unsigned __int16 *a2, enum SicfFlags *a3)
{
  LSTATUS ValueW; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-28h]
  int v8; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v10; // [rsp+58h] [rbp+10h] BYREF
  int v11; // [rsp+5Ch] [rbp+14h]
  DWORD v12; // [rsp+68h] [rbp+20h] BYREF

  v11 = HIDWORD(a2);
  v10 = 0;
  v12 = 4;
  ValueW = RegGetValueW(a1, 0, L"Flags", 0x10u, 0, &v10, &v12);
  v5 = ValueW;
  if ( ValueW >= 0 )
  {
    *(_DWORD *)a3 = v10;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecore\\base\\windows.storage\\src\\Registry.h",
      (const char *)(unsigned int)ValueW,
      v7);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\base\\windows.storage\\src\\accesslistreadcache.cpp",
      (const char *)v5,
      v8);
    return v5;
  }
}

```

## disassembly

```asm
0x180011174  mov     r11, rsp
0x180011177  mov     [r11+8], rbx
0x18001117b  mov     [r11+10h], rdx
0x18001117f  push    rdi
0x180011180  sub     rsp, 40h
0x180011184  lea     rax, [r11+20h]
0x180011188  mov     [rsp+48h+arg_8], 0
0x180011190  mov     [r11-18h], rax
0x180011194  mov     rdi, r8
0x180011197  lea     rax, [r11+10h]
0x18001119b  mov     [rsp+48h+arg_18], 4
0x1800111a3  mov     [r11-20h], rax
0x1800111a7  lea     r8, aFlags; "Flags"
0x1800111ae  mov     r9d, 10h; dwFlags
0x1800111b4  mov     qword ptr [r11-28h], 0
0x1800111bc  xor     edx, edx; lpSubKey
0x1800111be  call    cs:__imp_RegGetValueW
0x1800111c4  mov     ebx, eax
0x1800111c6  test    eax, eax
0x1800111c8  jns     short loc_180011200
0x1800111ca  mov     rcx, [rsp+48h]; this
0x1800111cf  lea     r8, aOnecoreBaseWin_7; "onecore\\base\\windows.storage\\src\\Re"...
0x1800111d6  mov     r9d, eax; char *
0x1800111d9  mov     edx, 0ADh; void *
0x1800111de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800111e3  mov     rcx, [rsp+48h]; this
0x1800111e8  lea     r8, aOnecoreBaseWin_6; "onecore\\base\\windows.storage\\src\\ac"...
0x1800111ef  mov     r9d, ebx; char *
0x1800111f2  mov     edx, 11h; void *
0x1800111f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800111fc  mov     eax, ebx
0x1800111fe  jmp     short loc_180011208
0x180011200  mov     eax, [rsp+48h+arg_8]
0x180011204  mov     [rdi], eax
0x180011206  xor     eax, eax
0x180011208  mov     rbx, [rsp+48h+arg_0]
0x18001120d  add     rsp, 40h
0x180011211  pop     rdi
0x180011212  retn
```
