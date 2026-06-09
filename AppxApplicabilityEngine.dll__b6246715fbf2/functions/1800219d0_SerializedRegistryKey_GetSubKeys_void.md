# SerializedRegistryKey::GetSubKeys(void)

- ea: `0x1800219d0`
- end: `0x180021bbb`
- name: `?GetSubKeys@SerializedRegistryKey@@UEBA?AV?$vector@V?$shared_ptr@VIRegistryKey@@@tr1@std@@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@@std@@XZ`
- size: `491`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x180004080`
- `0x18000e024`
- `0x18000f768`
- `0x180010078`
- `0x180011a64`
- `0x1800200c8`
- `0x180020edc`
- `0x1800211a8`
- `0x180021638`
- `0x1800219d0`
- `0x1800227c0`
- `0x180025010`

## pseudocode

```c
_QWORD *__fastcall SerializedRegistryKey::GetSubKeys(__int64 a1, _QWORD *a2)
{
  __int64 *v4; // rdi
  __int64 v5; // rdx
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rsi
  __int64 v8; // r15
  _QWORD *v9; // rax
  SerializedRegistryKey *v10; // rax
  __int64 v11; // r8
  SerializedRegistryKey *v12; // rbx
  __int64 v13; // rax
  _QWORD *v14; // r8
  __int64 v15; // rdx
  unsigned __int64 v16; // rbx
  std::tr1::_Ref_count_base *v18[2]; // [rsp+40h] [rbp-71h] BYREF
  __int64 v19; // [rsp+50h] [rbp-61h]
  _QWORD *v20; // [rsp+58h] [rbp-59h]
  SerializedRegistryKey *v21; // [rsp+60h] [rbp-51h]
  char v22[40]; // [rsp+68h] [rbp-49h] BYREF
  _QWORD v23[2]; // [rsp+90h] [rbp-21h] BYREF
  unsigned __int64 v24; // [rsp+A0h] [rbp-11h]
  unsigned __int64 v25; // [rsp+A8h] [rbp-9h]
  _QWORD v26[5]; // [rsp+B8h] [rbp+7h] BYREF

  v19 = -2;
  v20 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  (***(void (__fastcall ****)(_QWORD, _QWORD *, const unsigned __int16 *, __int64))(a1 + 64))(
    *(_QWORD *)(a1 + 64),
    v23,
    L"Profile",
    2);
  v4 = (__int64 *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 32) < 8u )
    v5 = a1 + 8;
  else
    v5 = *v4;
  v6 = std::wstring::find(v23, v5, 0, *(_QWORD *)(a1 + 24));
  v7 = v24;
  while ( 1 )
  {
    v16 = v6;
    if ( v6 >= v7 )
      break;
    v8 = std::wstring::find(v23, L"#", v6, 1);
    if ( !v16 )
      goto LABEL_9;
    v9 = v23;
    if ( v25 >= 8 )
      v9 = (_QWORD *)v23[0];
    if ( *((_WORD *)v9 + v16 - 1) == 37 )
    {
LABEL_9:
      if ( v8 - v16 > *(_QWORD *)(a1 + 24) )
      {
        std::wstring::substr(v23, v26, v16);
        v10 = (SerializedRegistryKey *)operator new(0x78u);
        v12 = v10;
        v21 = v10;
        if ( v10 )
        {
          v13 = std::wstring::wstring((__int64)v22, a1 + 80, v11);
          v14 = v26;
          if ( v26[3] >= 8u )
            v14 = (_QWORD *)v26[0];
          v10 = SerializedRegistryKey::SerializedRegistryKey(v12, *(HKEY *)(a1 + 56), (__int64)v14, v13);
        }
        *(_OWORD *)v18 = 0;
        std::tr1::shared_ptr<IRegistryKey>::_Resetp<RegistryKey>((__int64)v18, (__int64)v10);
        std::vector<std::tr1::shared_ptr<IRegistryKey>>::push_back(a2, v18);
        if ( v18[1] )
          std::tr1::_Ref_count_base::_Decref(v18[1]);
        std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)v26);
        v7 = v24;
      }
    }
    if ( *(_QWORD *)(a1 + 32) < 8u )
      v15 = a1 + 8;
    else
      v15 = *v4;
    v6 = std::wstring::find(v23, v15, v8, *(_QWORD *)(a1 + 24));
  }
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)v23);
  return a2;
}

```

## disassembly

```asm
0x1800219d0  mov     rax, rsp
0x1800219d3  push    rbp
0x1800219d4  push    rdi
0x1800219d5  push    r13
0x1800219d7  push    r14
0x1800219d9  push    r15
0x1800219db  lea     rbp, [rax-5Fh]
0x1800219df  sub     rsp, 0E0h
0x1800219e6  mov     [rbp+57h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1800219ee  mov     [rax+18h], rbx
0x1800219f2  mov     [rax+20h], rsi
0x1800219f6  mov     rax, cs:__security_cookie
0x1800219fd  xor     rax, rsp
0x180021a00  mov     [rbp+57h+var_28], rax
0x180021a04  mov     r14, rdx
0x180021a07  mov     r13, rcx
0x180021a0a  mov     [rbp+57h+var_B0], rdx
0x180021a0e  mov     [rbp+57h+var_D0], 0
0x180021a15  mov     qword ptr [rdx], 0
0x180021a1c  mov     qword ptr [rdx+8], 0
0x180021a24  mov     qword ptr [rdx+10h], 0
0x180021a2c  mov     [rbp+57h+var_D0], 1
0x180021a33  mov     rcx, [rcx+40h]
0x180021a37  mov     rax, [rcx]
0x180021a3a  mov     r9d, 2
0x180021a40  lea     r8, ?REG_PROFILE_VALUE_NAME@Internal@Windows@@3QBGB; "Profile"
0x180021a47  lea     rdx, [rbp+57h+var_78]
0x180021a4b  mov     rax, [rax]
0x180021a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a53  nop
0x180021a54  lea     rdi, [r13+8]
0x180021a58  cmp     qword ptr [rdi+18h], 8
0x180021a5d  jb      short loc_180021A64
0x180021a5f  mov     rdx, [rdi]
0x180021a62  jmp     short loc_180021A67
0x180021a64  mov     rdx, rdi
0x180021a67  mov     r9, [rdi+10h]
0x180021a6b  xor     r8d, r8d
0x180021a6e  lea     rcx, [rbp+57h+var_78]
0x180021a72  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x180021a77  mov     rsi, [rbp+57h+var_68]
0x180021a7b  jmp     loc_180021B7A
0x180021a80  mov     r9d, 1
0x180021a86  mov     r8, rbx
0x180021a89  lea     rdx, asc_18002EC04; "#"
0x180021a90  lea     rcx, [rbp+57h+var_78]
0x180021a94  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x180021a99  mov     r15, rax
0x180021a9c  test    rbx, rbx
0x180021a9f  jz      short loc_180021ABB
0x180021aa1  lea     rax, [rbp+57h+var_78]
0x180021aa5  cmp     [rbp+57h+var_60], 8
0x180021aaa  cmovnb  rax, [rbp+57h+var_78]
0x180021aaf  cmp     word ptr [rax+rbx*2-2], 25h ; '%'
0x180021ab5  jnz     loc_180021B5B
0x180021abb  mov     r9, r15
0x180021abe  sub     r9, rbx
0x180021ac1  cmp     r9, [r13+18h]
0x180021ac5  jbe     loc_180021B5B
0x180021acb  mov     r8, rbx
0x180021ace  lea     rdx, [rbp+57h+var_50]
0x180021ad2  lea     rcx, [rbp+57h+var_78]
0x180021ad6  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180021adb  nop
0x180021adc  mov     ecx, 78h ; 'x'; Size
0x180021ae1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021ae6  mov     rbx, rax
0x180021ae9  mov     [rbp+57h+var_A8], rax
0x180021aed  test    rax, rax
0x180021af0  jz      short loc_180021B1D
0x180021af2  lea     rdx, [r13+50h]
0x180021af6  lea     rcx, [rbp+57h+var_A0]
0x180021afa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180021aff  lea     r8, [rbp+57h+var_50]
0x180021b03  cmp     [rbp+57h+var_38], 8
0x180021b08  cmovnb  r8, [rbp+57h+var_50]
0x180021b0d  mov     r9, rax
0x180021b10  mov     rdx, [r13+38h]; HKEY
0x180021b14  mov     rcx, rbx; this
0x180021b17  call    ??0SerializedRegistryKey@@QEAA@PEAUHKEY__@@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SerializedRegistryKey::SerializedRegistryKey(HKEY__ *,ushort const *,std::wstring)
0x180021b1c  nop
0x180021b1d  xorps   xmm0, xmm0
0x180021b20  movdqu  xmmword ptr [rbp+57h+var_C8], xmm0
0x180021b25  mov     rdx, rax
0x180021b28  lea     rcx, [rbp+57h+var_C8]
0x180021b2c  call    ??$_Resetp@VRegistryKey@@@?$shared_ptr@VIRegistryKey@@@tr1@std@@AEAAXPEAVRegistryKey@@@Z; std::tr1::shared_ptr<IRegistryKey>::_Resetp<RegistryKey>(RegistryKey *)
0x180021b31  nop
0x180021b32  lea     rdx, [rbp+57h+var_C8]
0x180021b36  mov     rcx, r14
0x180021b39  call    ?push_back@?$vector@V?$shared_ptr@VIRegistryKey@@@tr1@std@@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@@std@@QEAAX$$QEAV?$shared_ptr@VIRegistryKey@@@tr1@2@@Z; std::vector<std::tr1::shared_ptr<IRegistryKey>>::push_back(std::tr1::shared_ptr<IRegistryKey> &&)
0x180021b3e  nop
0x180021b3f  mov     rcx, [rbp+57h+var_C8+8]; this
0x180021b43  test    rcx, rcx
0x180021b46  jz      short loc_180021B4E
0x180021b48  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180021b4d  nop
0x180021b4e  lea     rcx, [rbp+57h+var_50]
0x180021b52  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x180021b57  mov     rsi, [rbp+57h+var_68]
0x180021b5b  cmp     qword ptr [rdi+18h], 8
0x180021b60  jb      short loc_180021B67
0x180021b62  mov     rdx, [rdi]
0x180021b65  jmp     short loc_180021B6A
0x180021b67  mov     rdx, rdi
0x180021b6a  mov     r9, [rdi+10h]
0x180021b6e  mov     r8, r15
0x180021b71  lea     rcx, [rbp+57h+var_78]
0x180021b75  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x180021b7a  cmp     rax, rsi
0x180021b7d  mov     rbx, rax
0x180021b80  jb      loc_180021A80
0x180021b86  lea     rcx, [rbp+57h+var_78]
0x180021b8a  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x180021b8f  mov     rax, r14
0x180021b92  mov     rcx, [rbp+57h+var_28]
0x180021b96  xor     rcx, rsp; StackCookie
0x180021b99  call    __security_check_cookie
0x180021b9e  lea     r11, [rsp+100h+var_20]
0x180021ba6  mov     rbx, [r11+40h]
0x180021baa  mov     rsi, [r11+48h]
0x180021bae  mov     rsp, r11
0x180021bb1  pop     r15
0x180021bb3  pop     r14
0x180021bb5  pop     r13
0x180021bb7  pop     rdi
0x180021bb8  pop     rbp
0x180021bb9  retn
```
