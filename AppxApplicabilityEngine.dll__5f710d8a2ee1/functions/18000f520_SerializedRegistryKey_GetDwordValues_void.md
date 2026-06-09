# SerializedRegistryKey::GetDwordValues(void)

- ea: `0x18000f520`
- end: `0x18000f67c`
- name: `?GetDwordValues@SerializedRegistryKey@@UEBA?AV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@XZ`
- size: `348`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180004050`
- `0x180004080`
- `0x180004c88`
- `0x18000f520`
- `0x18000f684`
- `0x18000f744`
- `0x18000f768`
- `0x18000f7a0`
- `0x18002148c`
- `0x180021f34`
- `0x1800227c0`

## import_xrefs

- `msvcrt!swscanf_s` at `0x18000f61b`
- `msvcrt!swscanf_s` at `0x18000f61b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall SerializedRegistryKey::GetDwordValues(__int64 a1, _QWORD *a2)
{
  __int64 i; // rdi
  __int64 v4; // rsi
  __int16 *v5; // rbx
  __int16 v6; // bx
  __int64 v7; // rax
  int v9; // [rsp+28h] [rbp-E0h]
  __int64 v10; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v11; // [rsp+38h] [rbp-D0h]
  __int64 v12; // [rsp+50h] [rbp-B8h]
  _QWORD *v13; // [rsp+58h] [rbp-B0h]
  _BYTE v14[56]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v15[40]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v16[5]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v17[40]; // [rsp+E8h] [rbp-20h] BYREF

  v12 = -2;
  v13 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v9 = 1;
  SerializedRegistryKey::GetNameValuePairs(a1, &v10);
  for ( i = v10; ; i += 80 )
  {
    v4 = v11;
    if ( i == v11 )
      break;
    do
    {
      std::pair<std::wstring const,std::wstring const>::pair<std::wstring const,std::wstring const>(v15, i);
      v5 = (__int16 *)v16;
      if ( v16[3] >= 8u )
        v5 = (__int16 *)v16[0];
      v6 = *v5;
      std::_Pair_base<std::wstring,std::wstring>::~_Pair_base<std::wstring,std::wstring>(v15);
      if ( v6 == 68 )
        break;
      i += 80;
    }
    while ( i != v4 );
    if ( i == v11 )
      break;
    std::pair<std::wstring,unsigned long>::pair<std::wstring,unsigned long>(v14);
    std::wstring::assign(v14, i, 0, -1, v9);
    v7 = std::wstring::substr(i + 40, v17, 1, -1);
    if ( *(_QWORD *)(v7 + 24) >= 8u )
      v7 = *(_QWORD *)v7;
    swscanf_s((const wchar_t *const)v7, L"%x", &v14[40]);
    std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v17);
    std::vector<std::pair<std::wstring,unsigned long>>::push_back(a2, v14);
    std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v14);
  }
  std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(&v10);
  return a2;
}

```

## disassembly

```asm
0x18000f520  mov     rax, rsp
0x18000f523  push    rbp
0x18000f524  push    rdi
0x18000f525  push    r14
0x18000f527  lea     rbp, [rax-28h]
0x18000f52b  sub     rsp, 110h
0x18000f532  mov     [rsp+120h+var_D8], 0FFFFFFFFFFFFFFFEh
0x18000f53b  mov     [rax+18h], rbx
0x18000f53f  mov     [rax+20h], rsi
0x18000f543  mov     rax, cs:__security_cookie
0x18000f54a  xor     rax, rsp
0x18000f54d  mov     [rbp+20h+var_18], rax
0x18000f551  mov     r14, rdx
0x18000f554  mov     [rsp+120h+var_D0], rdx
0x18000f559  xor     eax, eax
0x18000f55b  mov     dword ptr [rsp+120h+var_100], eax
0x18000f55f  mov     [rdx], rax
0x18000f562  mov     [rdx+8], rax
0x18000f566  mov     [rdx+10h], rax
0x18000f56a  mov     dword ptr [rsp+120h+var_100], 1
0x18000f572  lea     rdx, [rsp+120h+var_F8]
0x18000f577  call    ?GetNameValuePairs@SerializedRegistryKey@@AEBA?AV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@XZ; SerializedRegistryKey::GetNameValuePairs(void)
0x18000f57c  nop
0x18000f57d  mov     rdi, [rsp+120h+var_F8]
0x18000f582  mov     rsi, [rsp+120h+var_F0]
0x18000f587  cmp     rdi, rsi
0x18000f58a  jz      loc_18000F64A
0x18000f590  mov     rdx, rdi
0x18000f593  lea     rcx, [rbp+20h+var_90]
0x18000f597  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$CBV12@@std@@QEAA@AEBU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::pair<std::wstring const,std::wstring const>::pair<std::wstring const,std::wstring const>(std::pair<std::wstring,std::wstring> const &)
0x18000f59c  lea     rbx, [rbp+20h+var_68]
0x18000f5a0  cmp     [rbp+20h+var_50], 8
0x18000f5a5  cmovnb  rbx, [rbp+20h+var_68]
0x18000f5aa  movzx   ebx, word ptr [rbx]
0x18000f5ad  lea     rcx, [rbp+20h+var_90]
0x18000f5b1  call    ??1?$_Pair_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::_Pair_base<std::wstring,std::wstring>::~_Pair_base<std::wstring,std::wstring>(void)
0x18000f5b6  cmp     bx, 44h ; 'D'
0x18000f5ba  jz      short loc_18000F5C5
0x18000f5bc  add     rdi, 50h ; 'P'
0x18000f5c0  cmp     rdi, rsi
0x18000f5c3  jnz     short loc_18000F590
0x18000f5c5  mov     rsi, [rsp+120h+var_F0]
0x18000f5ca  cmp     rdi, rsi
0x18000f5cd  jz      short loc_18000F64A
0x18000f5cf  lea     rcx, [rsp+120h+var_C8]
0x18000f5d4  call    ??0?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::pair<std::wstring,ulong>(void)
0x18000f5d9  nop
0x18000f5da  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000f5de  xor     r8d, r8d
0x18000f5e1  mov     rdx, rdi
0x18000f5e4  lea     rcx, [rsp+120h+var_C8]
0x18000f5e9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000f5ee  lea     rcx, [rdi+28h]
0x18000f5f2  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000f5f6  lea     r8d, [r9+2]
0x18000f5fa  lea     rdx, [rbp+20h+var_40]
0x18000f5fe  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000f603  cmp     qword ptr [rax+18h], 8
0x18000f608  jb      short loc_18000F60D
0x18000f60a  mov     rax, [rax]
0x18000f60d  lea     r8, [rbp+20h+var_A0]
0x18000f611  lea     rdx, asc_18002E728; "%x"
0x18000f618  mov     rcx, rax; Buffer
0x18000f61b  call    cs:__imp_swscanf_s
0x18000f621  lea     rcx, [rbp+20h+var_40]
0x18000f625  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000f62a  lea     rdx, [rsp+120h+var_C8]
0x18000f62f  mov     rcx, r14
0x18000f632  call    ?push_back@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAAXAEBU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@2@@Z; std::vector<std::pair<std::wstring,ulong>>::push_back(std::pair<std::wstring,ulong> const &)
0x18000f637  add     rdi, 50h ; 'P'
0x18000f63b  lea     rcx, [rsp+120h+var_C8]
0x18000f640  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000f645  jmp     loc_18000F582
0x18000f64a  lea     rcx, [rsp+120h+var_F8]
0x18000f64f  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@IEAAXXZ; std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(void)
0x18000f654  mov     rax, r14
0x18000f657  mov     rcx, [rbp+20h+var_18]
0x18000f65b  xor     rcx, rsp; StackCookie
0x18000f65e  call    __security_check_cookie
0x18000f663  lea     r11, [rsp+120h+var_10]
0x18000f66b  mov     rbx, [r11+30h]
0x18000f66f  mov     rsi, [r11+38h]
0x18000f673  mov     rsp, r11
0x18000f676  pop     r14
0x18000f678  pop     rdi
0x18000f679  pop     rbp
0x18000f67a  retn
```
