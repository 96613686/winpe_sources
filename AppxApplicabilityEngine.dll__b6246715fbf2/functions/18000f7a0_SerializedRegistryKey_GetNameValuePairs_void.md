# SerializedRegistryKey::GetNameValuePairs(void)

- ea: `0x18000f7a0`
- end: `0x18000fa1f`
- name: `?GetNameValuePairs@SerializedRegistryKey@@AEBA?AV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@XZ`
- size: `639`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000f520`
- `0x180010c40`
- `0x1800218a0`
- `0x180021d70`
- `0x180021e30`

## callees

- `0x180004050`
- `0x180004080`
- `0x18000e024`
- `0x18000f768`
- `0x18000f7a0`
- `0x180010078`
- `0x180021f90`
- `0x1800227c0`
- `0x180025010`

## pseudocode

```c
_QWORD *__fastcall SerializedRegistryKey::GetNameValuePairs(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rdx
  __int64 v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rbx
  unsigned __int64 v8; // rbx
  __int64 v9; // rsi
  __int64 v10; // r14
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // r8
  __int64 v14; // r8
  _DWORD v16[4]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-C0h]
  _QWORD *v18; // [rsp+50h] [rbp-B8h]
  _BYTE v19[16]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+68h] [rbp-A0h]
  _BYTE v21[16]; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int64 v22; // [rsp+90h] [rbp-78h]
  _BYTE v23[40]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v24[40]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v25[48]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v26[40]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v27[40]; // [rsp+150h] [rbp+48h] BYREF
  _BYTE v28[40]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v29[40]; // [rsp+1A0h] [rbp+98h] BYREF

  v17 = -2;
  v18 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v16[2] = 1;
  (***(void (__fastcall ****)(_QWORD, _BYTE *, const unsigned __int16 *, __int64))(a1 + 64))(
    *(_QWORD *)(a1 + 64),
    v23,
    L"Profile",
    2);
  v4 = (_QWORD *)(a1 + 8);
  v5 = *(_QWORD *)(a1 + 24);
  if ( *(_QWORD *)(a1 + 32) >= 8u )
    v4 = (_QWORD *)*v4;
  v6 = std::wstring::find(v23, v4, 0, *(_QWORD *)(a1 + 24));
  v7 = v6;
  if ( v6 != -1 )
  {
    std::wstring::find(v23, L"%", v6, 1);
    std::wstring::substr(v23, v21, v7 + v5 + 1);
    v8 = 0;
    while ( v8 < v22 )
    {
      LOWORD(v16[0]) = 38;
      std::wstring::find(v21, v16, v8, 1);
      std::wstring::substr(v21, v19, v8);
      v9 = v20;
      if ( v20 )
      {
        LOWORD(v16[0]) = 43;
        v10 = std::wstring::find(v19, v16, 0, 1);
        if ( v10 != -1 )
        {
          std::wstring::substr(v19, v25, 0);
          std::wstring::substr(v19, v24, v10 + 1);
          std::wstring::wstring((__int64)v26, (__int64)v25, v11);
          std::wstring::wstring((__int64)v27, (__int64)v24, v12);
          std::wstring::wstring((__int64)v28, (__int64)v26, v13);
          std::wstring::wstring((__int64)v29, (__int64)v27, v14);
          std::vector<std::pair<std::wstring,std::wstring>>::push_back(a2, v28);
          std::_Pair_base<std::wstring,std::wstring>::~_Pair_base<std::wstring,std::wstring>((__int64)v28);
          std::_Pair_base<std::wstring,std::wstring>::~_Pair_base<std::wstring,std::wstring>((__int64)v26);
          std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)v24);
          std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)v25);
          v9 = v20;
        }
      }
      v8 += v9 + 1;
      std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)v19);
    }
    std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)v21);
  }
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)v23);
  return a2;
}

```

## disassembly

```asm
0x18000f7a0  mov     rax, rsp
0x18000f7a3  push    rbp
0x18000f7a4  push    rdi
0x18000f7a5  push    r13
0x18000f7a7  push    r14
0x18000f7a9  push    r15
0x18000f7ab  lea     rbp, [rax-0F8h]
0x18000f7b2  sub     rsp, 1D0h
0x18000f7b9  mov     [rsp+1F0h+var_1B0], 0FFFFFFFFFFFFFFFEh
0x18000f7c2  mov     [rax+18h], rbx
0x18000f7c6  mov     [rax+20h], rsi
0x18000f7ca  mov     rax, cs:__security_cookie
0x18000f7d1  xor     rax, rsp
0x18000f7d4  mov     [rbp+0F0h+var_30], rax
0x18000f7db  mov     rdi, rdx
0x18000f7de  mov     rbx, rcx
0x18000f7e1  mov     [rsp+1F0h+var_1A8], rdx
0x18000f7e6  mov     dword ptr [rsp+1F0h+var_1B8], 0
0x18000f7ee  mov     qword ptr [rdx], 0
0x18000f7f5  mov     qword ptr [rdx+8], 0
0x18000f7fd  mov     qword ptr [rdx+10h], 0
0x18000f805  mov     r13d, 1
0x18000f80b  mov     dword ptr [rsp+1F0h+var_1B8], r13d
0x18000f810  mov     rcx, [rcx+40h]
0x18000f814  mov     rax, [rcx]
0x18000f817  lea     r9d, [r13+1]
0x18000f81b  lea     r8, ?REG_PROFILE_VALUE_NAME@Internal@Windows@@3QBGB; "Profile"
0x18000f822  lea     rdx, [rbp+0F0h+var_150]
0x18000f826  mov     rax, [rax]
0x18000f829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f82e  nop
0x18000f82f  lea     rdx, [rbx+8]
0x18000f833  mov     rsi, [rdx+10h]
0x18000f837  cmp     qword ptr [rdx+18h], 8
0x18000f83c  jb      short loc_18000F841
0x18000f83e  mov     rdx, [rdx]
0x18000f841  mov     r9, rsi
0x18000f844  xor     r8d, r8d
0x18000f847  lea     rcx, [rbp+0F0h+var_150]
0x18000f84b  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x18000f850  mov     rbx, rax
0x18000f853  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000f857  cmp     rax, r15
0x18000f85a  jz      loc_18000F9E7
0x18000f860  mov     r9, r13
0x18000f863  mov     r8, rax
0x18000f866  lea     rdx, asc_18002F258; "%"
0x18000f86d  lea     rcx, [rbp+0F0h+var_150]
0x18000f871  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x18000f876  lea     r8, [rsi+1]
0x18000f87a  add     r8, rbx
0x18000f87d  cmp     rax, r15
0x18000f880  jnz     short loc_18000F887
0x18000f882  mov     rax, r15
0x18000f885  jmp     short loc_18000F88A
0x18000f887  sub     rax, r8
0x18000f88a  mov     r9, rax
0x18000f88d  lea     rdx, [rsp+1F0h+var_178]
0x18000f892  lea     rcx, [rbp+0F0h+var_150]
0x18000f896  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000f89b  nop
0x18000f89c  xor     ebx, ebx
0x18000f89e  cmp     [rbp+0F0h+var_168], rbx
0x18000f8a2  jbe     loc_18000F9DC
0x18000f8a8  mov     eax, 26h ; '&'
0x18000f8ad  mov     word ptr [rsp+1F0h+var_1C0], ax
0x18000f8b2  mov     r9, r13
0x18000f8b5  mov     r8, rbx
0x18000f8b8  lea     rdx, [rsp+1F0h+var_1C0]
0x18000f8bd  lea     rcx, [rsp+1F0h+var_178]
0x18000f8c2  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x18000f8c7  cmp     rax, r15
0x18000f8ca  jnz     short loc_18000F8D1
0x18000f8cc  mov     rax, r15
0x18000f8cf  jmp     short loc_18000F8D4
0x18000f8d1  sub     rax, rbx
0x18000f8d4  mov     r9, rax
0x18000f8d7  mov     r8, rbx
0x18000f8da  lea     rdx, [rsp+1F0h+var_1A0]
0x18000f8df  lea     rcx, [rsp+1F0h+var_178]
0x18000f8e4  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000f8e9  nop
0x18000f8ea  mov     rsi, [rsp+1F0h+var_190]
0x18000f8ef  test    rsi, rsi
0x18000f8f2  jz      loc_18000F9C2
0x18000f8f8  mov     eax, 2Bh ; '+'
0x18000f8fd  mov     word ptr [rsp+1F0h+var_1C0], ax
0x18000f902  mov     r9, r13
0x18000f905  xor     r8d, r8d
0x18000f908  lea     rdx, [rsp+1F0h+var_1C0]
0x18000f90d  lea     rcx, [rsp+1F0h+var_1A0]
0x18000f912  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x18000f917  mov     r14, rax
0x18000f91a  cmp     rax, r15
0x18000f91d  jz      loc_18000F9C2
0x18000f923  mov     r9, rax
0x18000f926  xor     r8d, r8d
0x18000f929  lea     rdx, [rbp+0F0h+var_100]
0x18000f92d  lea     rcx, [rsp+1F0h+var_1A0]
0x18000f932  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000f937  nop
0x18000f938  lea     r8, [r14+1]
0x18000f93c  mov     r9, r15
0x18000f93f  lea     rdx, [rbp+0F0h+var_128]
0x18000f943  lea     rcx, [rsp+1F0h+var_1A0]
0x18000f948  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000f94d  nop
0x18000f94e  lea     rdx, [rbp+0F0h+var_100]
0x18000f952  lea     rcx, [rbp+0F0h+var_D0]
0x18000f956  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f95b  nop
0x18000f95c  lea     rdx, [rbp+0F0h+var_128]
0x18000f960  lea     rcx, [rbp+0F0h+var_A8]
0x18000f964  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f969  nop
0x18000f96a  lea     rdx, [rbp+0F0h+var_D0]
0x18000f96e  lea     rcx, [rbp+0F0h+var_80]
0x18000f972  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f977  nop
0x18000f978  lea     rdx, [rbp+0F0h+var_A8]
0x18000f97c  lea     rcx, [rbp+0F0h+var_58]
0x18000f983  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f988  nop
0x18000f989  lea     rdx, [rbp+0F0h+var_80]
0x18000f98d  mov     rcx, rdi
0x18000f990  call    ?push_back@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAX$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@2@@Z; std::vector<std::pair<std::wstring,std::wstring>>::push_back(std::pair<std::wstring,std::wstring> &&)
0x18000f995  nop
0x18000f996  lea     rcx, [rbp+0F0h+var_80]
0x18000f99a  call    ??1?$_Pair_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::_Pair_base<std::wstring,std::wstring>::~_Pair_base<std::wstring,std::wstring>(void)
0x18000f99f  nop
0x18000f9a0  lea     rcx, [rbp+0F0h+var_D0]
0x18000f9a4  call    ??1?$_Pair_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::_Pair_base<std::wstring,std::wstring>::~_Pair_base<std::wstring,std::wstring>(void)
0x18000f9a9  nop
0x18000f9aa  lea     rcx, [rbp+0F0h+var_128]
0x18000f9ae  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000f9b3  nop
0x18000f9b4  lea     rcx, [rbp+0F0h+var_100]
0x18000f9b8  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000f9bd  mov     rsi, [rsp+1F0h+var_190]
0x18000f9c2  inc     rbx
0x18000f9c5  add     rbx, rsi
0x18000f9c8  lea     rcx, [rsp+1F0h+var_1A0]
0x18000f9cd  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000f9d2  cmp     rbx, [rbp+0F0h+var_168]
0x18000f9d6  jb      loc_18000F8A8
0x18000f9dc  lea     rcx, [rsp+1F0h+var_178]
0x18000f9e1  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000f9e6  nop
0x18000f9e7  lea     rcx, [rbp+0F0h+var_150]
0x18000f9eb  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000f9f0  mov     rax, rdi
0x18000f9f3  mov     rcx, [rbp+0F0h+var_30]
0x18000f9fa  xor     rcx, rsp; StackCookie
0x18000f9fd  call    __security_check_cookie
0x18000fa02  lea     r11, [rsp+1F0h+var_20]
0x18000fa0a  mov     rbx, [r11+40h]
0x18000fa0e  mov     rsi, [r11+48h]
0x18000fa12  mov     rsp, r11
0x18000fa15  pop     r15
0x18000fa17  pop     r14
0x18000fa19  pop     r13
0x18000fa1b  pop     rdi
0x18000fa1c  pop     rbp
0x18000fa1d  retn
```
