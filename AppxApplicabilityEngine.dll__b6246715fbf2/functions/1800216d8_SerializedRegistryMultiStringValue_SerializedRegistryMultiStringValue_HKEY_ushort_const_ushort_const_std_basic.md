# SerializedRegistryMultiStringValue::SerializedRegistryMultiStringValue(HKEY__ *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800216d8`
- end: `0x1800217ca`
- name: `??0SerializedRegistryMultiStringValue@@QEAA@PEAUHKEY__@@PEBG1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `242`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001ea98`

## callees

- `0x180004080`
- `0x18000d8f8`
- `0x18000e024`
- `0x180011a64`
- `0x180021638`
- `0x1800216d8`
- `0x1800227c0`

## pseudocode

```c
_QWORD *__fastcall SerializedRegistryMultiStringValue::SerializedRegistryMultiStringValue(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v6; // rdi
  SerializedRegistryKey *v7; // rax
  __int64 v8; // r8
  SerializedRegistryKey *v9; // rbp
  __int64 v10; // rax
  _BYTE v12[40]; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v13[40]; // [rsp+78h] [rbp-60h] BYREF
  __int64 v14; // [rsp+A0h] [rbp-38h]

  v14 = a5;
  v6 = std::wstring::wstring((__int64)v12, (__int64)L"Languages");
  v7 = (SerializedRegistryKey *)operator new(0x78u);
  v9 = v7;
  if ( v7 )
  {
    v10 = std::wstring::wstring((__int64)v13, a5, v8);
    v7 = SerializedRegistryKey::SerializedRegistryKey(v9, HKEY_LOCAL_MACHINE, (__int64)L"User Profile", v10);
  }
  *a1 = &UserLanguageRegistryValue::`vftable';
  a1[1] = v7;
  std::wstring::wstring((__int64)(a1 + 2), v6, v8);
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v6);
  *a1 = &UserLanguageRegistryValue::`vftable';
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(a5);
  return a1;
}

```

## disassembly

```asm
0x1800216d8  mov     r11, rsp
0x1800216db  push    rbx
0x1800216dc  push    rbp
0x1800216dd  push    rsi
0x1800216de  push    rdi
0x1800216df  sub     rsp, 0B8h
0x1800216e6  mov     [rsp+0D8h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1800216ef  mov     rax, cs:__security_cookie
0x1800216f6  xor     rax, rsp
0x1800216f9  mov     [rsp+0D8h+var_30], rax
0x180021701  mov     rbx, rcx
0x180021704  mov     [rsp+0D8h+var_B0], rcx
0x180021709  mov     rsi, [rsp+0D8h+arg_20]
0x180021711  mov     [r11-38h], rsi
0x180021715  lea     rax, [rsp+0D8h+var_88]
0x18002171a  mov     [rsp+0D8h+var_A8], rax
0x18002171f  lea     rdx, ?USER_LANGUAGES_REGKEY_VALUE@Internal@Windows@@3QBGB; "Languages"
0x180021726  lea     rcx, [rsp+0D8h+var_88]
0x18002172b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180021730  mov     rdi, rax
0x180021733  mov     [rsp+0D8h+var_A0], rax
0x180021738  mov     ecx, 78h ; 'x'; Size
0x18002173d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021742  mov     rbp, rax
0x180021745  mov     [rsp+0D8h+var_98], rax
0x18002174a  test    rax, rax
0x18002174d  jz      short loc_180021776
0x18002174f  mov     rdx, rsi
0x180021752  lea     rcx, [rsp+0D8h+var_60]
0x180021757  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002175c  mov     r9, rax
0x18002175f  lea     r8, ?USER_PROFILE_REGKEY_NAME@Internal@Windows@@3QBGB; "User Profile"
0x180021766  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18002176d  mov     rcx, rbp; this
0x180021770  call    ??0SerializedRegistryKey@@QEAA@PEAUHKEY__@@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SerializedRegistryKey::SerializedRegistryKey(HKEY__ *,ushort const *,std::wstring)
0x180021775  nop
0x180021776  lea     rcx, ??_7UserLanguageRegistryValue@@6B@; const UserLanguageRegistryValue::`vftable'
0x18002177d  mov     [rbx], rcx
0x180021780  mov     [rbx+8], rax
0x180021784  lea     rcx, [rbx+10h]
0x180021788  mov     rdx, rdi
0x18002178b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180021790  nop
0x180021791  mov     rcx, rdi
0x180021794  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x180021799  lea     rax, ??_7UserLanguageRegistryValue@@6B@; const UserLanguageRegistryValue::`vftable'
0x1800217a0  mov     [rbx], rax
0x1800217a3  mov     rcx, rsi
0x1800217a6  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x1800217ab  mov     rax, rbx
0x1800217ae  mov     rcx, [rsp+0D8h+var_30]
0x1800217b6  xor     rcx, rsp; StackCookie
0x1800217b9  call    __security_check_cookie
0x1800217be  add     rsp, 0B8h
0x1800217c5  pop     rdi
0x1800217c6  pop     rsi
0x1800217c7  pop     rbp
0x1800217c8  pop     rbx
0x1800217c9  retn
```
