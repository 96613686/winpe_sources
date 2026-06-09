# SerializedRegistryKey::GetDwordValue(ushort const *)

- ea: `0x1800218a0`
- end: `0x18002196f`
- name: `?GetDwordValue@SerializedRegistryKey@@UEBAKPEBG@Z`
- size: `207`
- prototype: `unsigned int __fastcall(SerializedRegistryKey *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180004080`
- `0x18000d8f8`
- `0x18000f7a0`
- `0x18001f3ec`
- `0x1800218a0`
- `0x180021cf8`
- `0x180021f34`
- `0x1800227c0`

## import_xrefs

- `msvcrt!swscanf_s` at `0x18002193a`
- `msvcrt!swscanf_s` at `0x18002193a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SerializedRegistryKey::GetDwordValue(SerializedRegistryKey *this, const unsigned __int16 *a2)
{
  _QWORD *NameValuePairs; // rbx
  __int64 v4; // rcx
  const wchar_t *v5; // rcx
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+28h] [rbp-39h] BYREF
  __int64 v9; // [rsp+30h] [rbp-31h]
  _QWORD v10[4]; // [rsp+38h] [rbp-29h] BYREF
  wchar_t *Buffer[5]; // [rsp+58h] [rbp-9h] BYREF
  _BYTE v12[40]; // [rsp+80h] [rbp+1Fh] BYREF

  v9 = -2;
  NameValuePairs = SerializedRegistryKey::GetNameValuePairs((__int64)this, v10);
  std::wstring::wstring(v12, a2);
  SerializedRegistryKey::GetValueFromPairs(v4, Buffer, v12, NameValuePairs);
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v12);
  std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(v10);
  v8 = 0;
  if ( !(unsigned __int8)std::operator==<unsigned short>(Buffer) )
  {
    v5 = (const wchar_t *)Buffer;
    if ( Buffer[3] >= (wchar_t *)8 )
      v5 = Buffer[0];
    swscanf_s(v5, L"%x", &v8);
  }
  v6 = v8;
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(Buffer);
  return v6;
}

```

## disassembly

```asm
0x1800218a0  mov     rax, rsp
0x1800218a3  push    rbp
0x1800218a4  lea     rbp, [rax-5Fh]
0x1800218a8  sub     rsp, 0B0h
0x1800218af  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x1800218b7  mov     [rax+18h], rbx
0x1800218bb  mov     [rax+20h], rdi
0x1800218bf  mov     rax, cs:__security_cookie
0x1800218c6  xor     rax, rsp
0x1800218c9  mov     [rbp+57h+var_10], rax
0x1800218cd  mov     rdi, rdx
0x1800218d0  lea     rdx, [rbp+57h+var_80]
0x1800218d4  call    ?GetNameValuePairs@SerializedRegistryKey@@AEBA?AV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@XZ; SerializedRegistryKey::GetNameValuePairs(void)
0x1800218d9  mov     rbx, rax
0x1800218dc  mov     rdx, rdi
0x1800218df  lea     rcx, [rbp+57h+var_38]
0x1800218e3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800218e8  nop
0x1800218e9  mov     r9, rbx
0x1800218ec  lea     r8, [rbp+57h+var_38]
0x1800218f0  lea     rdx, [rbp+57h+Buffer]
0x1800218f4  call    ?GetValueFromPairs@SerializedRegistryKey@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@AEBV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@Z; SerializedRegistryKey::GetValueFromPairs(std::wstring const &,std::vector<std::pair<std::wstring,std::wstring>> const &)
0x1800218f9  nop
0x1800218fa  lea     rcx, [rbp+57h+var_38]
0x1800218fe  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x180021903  nop
0x180021904  lea     rcx, [rbp+57h+var_80]
0x180021908  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@IEAAXXZ; std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(void)
0x18002190d  mov     [rbp+57h+var_90], 0
0x180021914  lea     rcx, [rbp+57h+Buffer]
0x180021918  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x18002191d  test    al, al
0x18002191f  jnz     short loc_180021940
0x180021921  lea     rcx, [rbp+57h+Buffer]
0x180021925  cmp     [rbp+57h+var_48], 8
0x18002192a  cmovnb  rcx, [rbp+57h+Buffer]; Buffer
0x18002192f  lea     r8, [rbp+57h+var_90]
0x180021933  lea     rdx, asc_18002E728; "%x"
0x18002193a  call    cs:__imp_swscanf_s
0x180021940  mov     ebx, [rbp+57h+var_90]
0x180021943  lea     rcx, [rbp+57h+Buffer]
0x180021947  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18002194c  mov     eax, ebx
0x18002194e  mov     rcx, [rbp+57h+var_10]
0x180021952  xor     rcx, rsp; StackCookie
0x180021955  call    __security_check_cookie
0x18002195a  lea     r11, [rsp+0B0h+var_s0]
0x180021962  mov     rbx, [r11+20h]
0x180021966  mov     rdi, [r11+28h]
0x18002196a  mov     rsp, r11
0x18002196d  pop     rbp
0x18002196e  retn
```
