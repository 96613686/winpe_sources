# SerializedRegistryKey::GetValue(ushort const *,ulong)

- ea: `0x180010c40`
- end: `0x180010d31`
- name: `?GetValue@SerializedRegistryKey@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGK@Z`
- size: `241`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180004080`
- `0x18000d8f8`
- `0x18000f7a0`
- `0x180010c40`
- `0x180010d38`
- `0x180021cf8`
- `0x180021f34`
- `0x1800227c0`

## pseudocode

```c
_QWORD *__fastcall SerializedRegistryKey::GetValue(__int64 a1, _QWORD *a2, __int64 a3, int a4)
{
  _QWORD *NameValuePairs; // rbx
  __int64 v8; // rcx
  __int64 v9; // r8
  _QWORD *v10; // r9
  __int16 *v11; // rax
  _WORD *v12; // r9
  __int16 *v13; // rdx
  __int16 v14; // cx
  _QWORD v16[2]; // [rsp+28h] [rbp-80h] BYREF
  _QWORD v17[4]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v18[40]; // [rsp+58h] [rbp-50h] BYREF

  v16[1] = -2;
  v16[0] = a2;
  NameValuePairs = SerializedRegistryKey::GetNameValuePairs(a1, v17);
  std::wstring::wstring((__int64)v18, a3);
  SerializedRegistryKey::GetValueFromPairs(v8, a2, v18, NameValuePairs);
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)v18);
  std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(v17);
  if ( a4 == 32 )
  {
    if ( a2[3] < 8u )
      v10 = a2;
    else
      v10 = (_QWORD *)*a2;
    v11 = *(__int16 **)std::wstring::end(a2, v16, v9, v10);
    if ( a2[3] < 8u )
      v13 = (__int16 *)a2;
    else
      v13 = (__int16 *)*a2;
    while ( v13 != v11 )
    {
      v14 = 0;
      if ( *v13 != 64 )
        v14 = *v13;
      *v12++ = v14;
      ++v13;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180010c40  mov     r11, rsp
0x180010c43  push    rsi
0x180010c44  push    rdi
0x180010c45  push    r14
0x180010c47  sub     rsp, 90h
0x180010c4e  mov     qword ptr [r11-78h], 0FFFFFFFFFFFFFFFEh
0x180010c56  mov     [r11+20h], rbx
0x180010c5a  mov     rax, cs:__security_cookie
0x180010c61  xor     rax, rsp
0x180010c64  mov     [rsp+0A8h+var_28], rax
0x180010c6c  mov     esi, r9d
0x180010c6f  mov     rdi, r8
0x180010c72  mov     r14, rdx
0x180010c75  mov     [rsp+0A8h+var_80], rdx
0x180010c7a  lea     rdx, [r11-70h]
0x180010c7e  call    ?GetNameValuePairs@SerializedRegistryKey@@AEBA?AV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@XZ; SerializedRegistryKey::GetNameValuePairs(void)
0x180010c83  mov     rbx, rax
0x180010c86  mov     rdx, rdi
0x180010c89  lea     rcx, [rsp+0A8h+var_50]
0x180010c8e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180010c93  nop
0x180010c94  mov     r9, rbx
0x180010c97  lea     r8, [rsp+0A8h+var_50]
0x180010c9c  mov     rdx, r14
0x180010c9f  call    ?GetValueFromPairs@SerializedRegistryKey@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@AEBV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@Z; SerializedRegistryKey::GetValueFromPairs(std::wstring const &,std::vector<std::pair<std::wstring,std::wstring>> const &)
0x180010ca4  nop
0x180010ca5  lea     rcx, [rsp+0A8h+var_50]
0x180010caa  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x180010caf  nop
0x180010cb0  lea     rcx, [rsp+0A8h+var_70]
0x180010cb5  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@IEAAXXZ; std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(void)
0x180010cba  cmp     esi, 20h ; ' '
0x180010cbd  jnz     short loc_180010D0A
0x180010cbf  cmp     qword ptr [r14+18h], 8
0x180010cc4  jb      short loc_180010CCB
0x180010cc6  mov     r9, [r14]
0x180010cc9  jmp     short loc_180010CCE
0x180010ccb  mov     r9, r14
0x180010cce  lea     rdx, [rsp+0A8h+var_80]
0x180010cd3  mov     rcx, r14
0x180010cd6  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::wstring::end(void)
0x180010cdb  mov     rax, [rax]
0x180010cde  cmp     qword ptr [r14+18h], 8
0x180010ce3  jb      short loc_180010CEA
0x180010ce5  mov     rdx, [r14]
0x180010ce8  jmp     short loc_180010D05
0x180010cea  mov     rdx, r14
0x180010ced  jmp     short loc_180010D05
0x180010cef  xor     ecx, ecx
0x180010cf1  cmp     word ptr [rdx], 40h ; '@'
0x180010cf5  cmovnz  cx, [rdx]
0x180010cf9  mov     [r9], cx
0x180010cfd  lea     r9, [r9+2]
0x180010d01  add     rdx, 2
0x180010d05  cmp     rdx, rax
0x180010d08  jnz     short loc_180010CEF
0x180010d0a  mov     rax, r14
0x180010d0d  mov     rcx, [rsp+0A8h+var_28]
0x180010d15  xor     rcx, rsp; StackCookie
0x180010d18  call    __security_check_cookie
0x180010d1d  mov     rbx, [rsp+0A8h+arg_18]
0x180010d25  add     rsp, 90h
0x180010d2c  pop     r14
0x180010d2e  pop     rdi
0x180010d2f  pop     rsi
0x180010d30  retn
```
