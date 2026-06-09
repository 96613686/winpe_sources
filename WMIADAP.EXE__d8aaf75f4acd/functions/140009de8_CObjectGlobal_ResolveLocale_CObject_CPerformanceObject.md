# CObjectGlobal::ResolveLocale(CObject *,CPerformanceObject *)

- ea: `0x140009de8`
- end: `0x14000a3cd`
- name: `?ResolveLocale@CObjectGlobal@@AEAAJPEAVCObject@@PEAVCPerformanceObject@@@Z`
- size: `1509`
- prototype: `__int64 __fastcall(CObjectGlobal *this, struct CObject *, struct CPerformanceObject *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400097d0`

## callees

- `0x140006284`
- `0x140008f9c`
- `0x14000919c`
- `0x140009688`
- `0x140009de8`
- `0x14000f218`
- `0x14000f298`

## import_xrefs

- `msvcrt!wcslen` at `0x140009e7a`
- `msvcrt!wcslen` at `0x14000a10d`
- `msvcrt!wcslen` at `0x140009e7a`
- `msvcrt!wcslen` at `0x14000a10d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140009e23`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140009ea8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140009f5f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000a0a0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000a136`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000a230`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140009e23`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140009ea8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140009f5f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000a0a0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000a136`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000a230`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000a077`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000a077`

## pseudocode

```c
__int64 __fastcall CObjectGlobal::ResolveLocale(CObjectGlobal *this, struct CObject *a2, struct CPerformanceObject *a3)
{
  unsigned int v5; // r15d
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  const wchar_t *v8; // rcx
  int v9; // eax
  unsigned int v10; // eax
  unsigned __int16 *v11; // r11
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // kr30_8
  unsigned __int16 *v15; // rax
  PCNZWCH v17; // r11
  unsigned __int64 v18; // rax
  WCHAR *v19; // rax
  unsigned __int16 *v20; // rbx
  const wchar_t *v21; // rcx
  int v22; // eax
  unsigned int v23; // eax
  unsigned __int16 *v24; // r11
  unsigned __int64 v25; // rsi
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // kr40_8
  unsigned __int16 *v28; // rax
  unsigned __int16 *v29; // r11
  unsigned __int64 v30; // rax
  unsigned __int16 *v31; // rax
  void **v32; // [rsp+30h] [rbp-78h] BYREF
  _QWORD *v33; // [rsp+38h] [rbp-70h]
  void **v34; // [rsp+40h] [rbp-68h] BYREF
  unsigned __int16 *v35; // [rsp+48h] [rbp-60h] BYREF
  void **v36; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int16 *v37; // [rsp+58h] [rbp-50h] BYREF
  void **v38; // [rsp+60h] [rbp-48h] BYREF
  PCNZWCH lpString1; // [rsp+68h] [rbp-40h] BYREF
  void **v40; // [rsp+70h] [rbp-38h] BYREF
  unsigned __int16 *v41; // [rsp+78h] [rbp-30h] BYREF

  v5 = 0;
  v33 = 0;
  v32 = &__WrapperPtr<CLocale>::`vftable';
  v6 = CWin32DefaultArena::WbemMemAlloc(0x18u);
  v7 = v6;
  if ( v6 )
  {
    *v6 = &CLocale::`vftable';
    v6[1] = 0;
    v6[2] = 0;
    v33 = v6;
    v35 = 0;
    v34 = &__WrapperBuffer<unsigned short>::`vftable';
    CPerformanceObject::GetQualifierValue(a3, L"displayname", &v35);
    v8 = (const wchar_t *)*((_QWORD *)a2 + 1);
    if ( v8 )
      v9 = wcslen(v8);
    else
      v9 = 0;
    v10 = v9 + 1;
    v11 = v35;
    if ( v35 )
    {
      v12 = v10;
    }
    else
    {
      v12 = v10;
      v14 = v10;
      v13 = 2LL * v10;
      if ( !is_mul_ok(v14, 2u) )
        v13 = -1;
      try
      {
        v15 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v13);
      }
      catch ( ... )
      {
        __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v34);
        __Wrapper<CLocale>::~__Wrapper<CLocale>(&v32);
        return 2147549183LL;
      }
      v35 = v15;
      if ( !v15 )
      {
        __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v34);
        __Wrapper<CLocale>::~__Wrapper<CLocale>(&v32);
        return 2147942414LL;
      }
      StringCchCopyW(v15, v12, *((const unsigned __int16 **)a2 + 1));
    }
    v35 = 0;
    v7[1] = v11;
    lpString1 = 0;
    v38 = &__WrapperBuffer<unsigned short>::`vftable';
    CPerformanceObject::GetQualifierValue(a3, L"description", (unsigned __int16 **)&lpString1);
    v17 = lpString1;
    if ( !lpString1 )
    {
      v18 = 2 * v12;
      if ( !is_mul_ok(v12, 2u) )
        v18 = -1;
      try
      {
        v19 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(v18);
      }
      catch ( ... )
      {
        __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v38);
        __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v34);
        __Wrapper<CLocale>::~__Wrapper<CLocale>(&v32);
        return 2147549183LL;
      }
      lpString1 = v19;
      if ( !v19 )
      {
        __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v38);
        __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v34);
        __Wrapper<CLocale>::~__Wrapper<CLocale>(&v32);
        return 2147942414LL;
      }
      StringCchCopyW(v19, v12, *((const unsigned __int16 **)a2 + 1));
    }
    lpString1 = 0;
    v7[2] = v17;
    __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v38);
    __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v34);
    v33 = 0;
    __WrapperARRAY<CLocale *>::DataAdd((char *)a2 + 16, v7);
    while ( 1 )
    {
      if ( v5 >= *((_DWORD *)a2 + 14) )
      {
        __Wrapper<CLocale>::~__Wrapper<CLocale>(&v32);
        return 0;
      }
      lpString1 = 0;
      v38 = &__WrapperBuffer<unsigned short>::`vftable';
      CPerformanceObject::GetQualifierValue(
        a3,
        *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)a2 + 6) + 8LL * v5) + 8LL),
        L"show",
        (unsigned __int16 **)&lpString1);
      if ( !lpString1 || CompareStringW(0x7Fu, 1u, lpString1, -1, L"false", -1) != 2 )
      {
        v35 = 0;
        v34 = &__WrapperPtr<CLocale>::`vftable';
        v20 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x18u);
        if ( !v20 )
        {
          v35 = 0;
          __Wrapper<CLocale>::~__Wrapper<CLocale>(&v34);
          __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v38);
          __Wrapper<CLocale>::~__Wrapper<CLocale>(&v32);
          return 2147942414LL;
        }
        *(_QWORD *)v20 = &CLocale::`vftable';
        *((_QWORD *)v20 + 1) = 0;
        *((_QWORD *)v20 + 2) = 0;
        v35 = v20;
        v37 = 0;
        v36 = &__WrapperBuffer<unsigned short>::`vftable';
        CPerformanceObject::GetQualifierValue(
          a3,
          *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)a2 + 6) + 8LL * v5) + 8LL),
          L"displayname",
          &v37);
        v21 = *(const wchar_t **)(*(_QWORD *)(*((_QWORD *)a2 + 6) + 8LL * v5) + 8LL);
        if ( v21 )
          v22 = wcslen(v21);
        else
          v22 = 0;
        v23 = v22 + 1;
        v24 = v37;
        if ( v37 )
        {
          v25 = v23;
        }
        else
        {
          v25 = v23;
          v27 = v23;
          v26 = 2LL * v23;
          if ( !is_mul_ok(v27, 2u) )
            v26 = -1;
          try
          {
            v28 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v26);
          }
          catch ( ... )
          {
            __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v36);
            __Wrapper<CLocale>::~__Wrapper<CLocale>(&v34);
            __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v38);
            __Wrapper<CLocale>::~__Wrapper<CLocale>(&v32);
            return 2147549183LL;
          }
          v37 = v28;
          if ( !v28 )
          {
            __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v36);
            __Wrapper<CLocale>::~__Wrapper<CLocale>(&v34);
            __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v38);
            __Wrapper<CLocale>::~__Wrapper<CLocale>(&v32);
            return 2147942414LL;
          }
          StringCchCopyW(v28, v25, *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)a2 + 6) + 8LL * v5) + 8LL));
        }
        v37 = 0;
        *((_QWORD *)v20 + 1) = v24;
        v41 = 0;
        v40 = &__WrapperBuffer<unsigned short>::`vftable';
        CPerformanceObject::GetQualifierValue(
          a3,
          *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)a2 + 6) + 8LL * v5) + 8LL),
          L"description",
          &v41);
        v29 = v41;
        if ( !v41 )
        {
          v30 = 2 * v25;
          if ( !is_mul_ok(v25, 2u) )
            v30 = -1;
          try
          {
            v31 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v30);
          }
          catch ( ... )
          {
            __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v40);
            __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v36);
            __Wrapper<CLocale>::~__Wrapper<CLocale>(&v34);
            __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v38);
            __Wrapper<CLocale>::~__Wrapper<CLocale>(&v32);
            return 2147549183LL;
          }
          v41 = v31;
          if ( !v31 )
          {
            __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v40);
            __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v36);
            __Wrapper<CLocale>::~__Wrapper<CLocale>(&v34);
            __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v38);
            __Wrapper<CLocale>::~__Wrapper<CLocale>(&v32);
            return 2147942414LL;
          }
          StringCchCopyW(v31, v25, *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)a2 + 6) + 8LL * v5) + 8LL));
        }
        v41 = 0;
        *((_QWORD *)v20 + 2) = v29;
        __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v40);
        __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v36);
        v35 = 0;
        __WrapperARRAY<CLocale *>::DataAdd(*(_QWORD *)(*((_QWORD *)a2 + 6) + 8LL * v5) + 24LL, v20);
        __Wrapper<CLocale>::~__Wrapper<CLocale>(&v34);
      }
      __WrapperBuffer<unsigned short>::~__WrapperBuffer<unsigned short>(&v38);
      ++v5;
    }
  }
  v33 = 0;
  __Wrapper<CLocale>::~__Wrapper<CLocale>(&v32);
  return 2147942414LL;
}

```

## disassembly

```asm
0x140009de8  mov     r11, rsp
0x140009deb  mov     [r11+10h], rbx
0x140009def  mov     [r11+20h], rsi
0x140009df3  mov     [r11+18h], r8
0x140009df7  push    rdi
0x140009df8  push    r12
0x140009dfa  push    r13
0x140009dfc  push    r14
0x140009dfe  push    r15
0x140009e00  sub     rsp, 80h
0x140009e07  mov     r14, r8
0x140009e0a  mov     rdi, rdx
0x140009e0d  xor     r15d, r15d
0x140009e10  mov     [r11-70h], r15
0x140009e14  lea     rax, ??_7?$__WrapperPtr@VCLocale@@@@6B@; const __WrapperPtr<CLocale>::`vftable'
0x140009e1b  mov     [r11-78h], rax
0x140009e1f  lea     ecx, [r15+18h]
0x140009e23  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140009e29  mov     rbx, rax
0x140009e2c  test    rax, rax
0x140009e2f  jz      loc_14000A38B
0x140009e35  lea     rax, ??_7CLocale@@6B@; const CLocale::`vftable'
0x140009e3c  mov     [rbx], rax
0x140009e3f  mov     [rbx+8], r15
0x140009e43  mov     [rbx+10h], r15
0x140009e47  mov     [rsp+0A8h+var_70], rbx
0x140009e4c  mov     [rsp+0A8h+var_60], r15
0x140009e51  lea     rax, ??_7?$__WrapperBuffer@G@@6B@; const __WrapperBuffer<ushort>::`vftable'
0x140009e58  mov     [rsp+0A8h+var_68], rax
0x140009e5d  lea     r8, [rsp+0A8h+var_60]; unsigned __int16 **
0x140009e62  lea     rdx, aDisplayname; "displayname"
0x140009e69  mov     rcx, r14; this
0x140009e6c  call    ?GetQualifierValue@CPerformanceObject@@QEAAJPEBGPEAPEAG@Z; CPerformanceObject::GetQualifierValue(ushort const *,ushort * *)
0x140009e71  mov     rcx, [rdi+8]; String
0x140009e75  test    rcx, rcx
0x140009e78  jz      short loc_140009E82
0x140009e7a  call    cs:__imp_wcslen
0x140009e80  jmp     short loc_140009E85
0x140009e82  mov     rax, r15
0x140009e85  inc     eax
0x140009e87  mov     r11, [rsp+0A8h+var_60]
0x140009e8c  test    r11, r11
0x140009e8f  jnz     short loc_140009F0A
0x140009e91  mov     esi, eax
0x140009e93  lea     r13d, [r11+2]
0x140009e97  mov     eax, r13d
0x140009e9a  mul     rsi
0x140009e9d  lea     r12, [r11-1]
0x140009ea1  cmovb   rax, r12
0x140009ea5  mov     rcx, rax
0x140009ea8  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140009eae  mov     r11, rax
0x140009eb1  mov     [rsp+0A8h+var_60], rax
0x140009eb6  test    rax, rax
0x140009eb9  jnz     short loc_140009EDA
0x140009ebb  lea     rcx, [rsp+0A8h+var_68]
0x140009ec0  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x140009ec5  nop
0x140009ec6  lea     rcx, [rsp+0A8h+var_78]
0x140009ecb  call    ??1?$__Wrapper@VCLocale@@@@UEAA@XZ; __Wrapper<CLocale>::~__Wrapper<CLocale>(void)
0x140009ed0  mov     eax, 8007000Eh
0x140009ed5  jmp     loc_14000A3B0
0x140009eda  mov     r8, [rdi+8]; unsigned __int16 *
0x140009ede  mov     rdx, rsi; unsigned __int64
0x140009ee1  mov     rcx, rax; unsigned __int16 *
0x140009ee4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140009ee9  jmp     short loc_140009F16
0x140009eeb  lea     rcx, [rsp+0A8h+var_68]
0x140009ef0  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x140009ef5  nop
0x140009ef6  lea     rcx, [rsp+0A8h+var_78]
0x140009efb  call    ??1?$__Wrapper@VCLocale@@@@UEAA@XZ; __Wrapper<CLocale>::~__Wrapper<CLocale>(void)
0x140009f00  mov     eax, 8000FFFFh
0x140009f05  jmp     loc_14000A3B0
0x140009f0a  mov     esi, eax
0x140009f0c  mov     r13d, 2
0x140009f12  or      r12, 0FFFFFFFFFFFFFFFFh
0x140009f16  mov     [rsp+0A8h+var_60], r15
0x140009f1b  mov     [rbx+8], r11
0x140009f1f  mov     [rsp+0A8h+lpString1], r15
0x140009f24  lea     rax, ??_7?$__WrapperBuffer@G@@6B@; const __WrapperBuffer<ushort>::`vftable'
0x140009f2b  mov     [rsp+0A8h+var_48], rax
0x140009f30  lea     r8, [rsp+0A8h+lpString1]; unsigned __int16 **
0x140009f35  lea     rdx, aDescription_0; "description"
0x140009f3c  mov     rcx, r14; this
0x140009f3f  call    ?GetQualifierValue@CPerformanceObject@@QEAAJPEBGPEAPEAG@Z; CPerformanceObject::GetQualifierValue(ushort const *,ushort * *)
0x140009f44  mov     r11, [rsp+0A8h+lpString1]
0x140009f49  test    r11, r11
0x140009f4c  jnz     loc_140009FD7
0x140009f52  mov     rax, r13
0x140009f55  mul     rsi
0x140009f58  cmovb   rax, r12
0x140009f5c  mov     rcx, rax
0x140009f5f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140009f65  mov     r11, rax
0x140009f68  mov     [rsp+0A8h+lpString1], rax
0x140009f6d  test    rax, rax
0x140009f70  jnz     short loc_140009F9C
0x140009f72  lea     rcx, [rsp+0A8h+var_48]
0x140009f77  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x140009f7c  nop
0x140009f7d  lea     rcx, [rsp+0A8h+var_68]
0x140009f82  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x140009f87  nop
0x140009f88  lea     rcx, [rsp+0A8h+var_78]
0x140009f8d  call    ??1?$__Wrapper@VCLocale@@@@UEAA@XZ; __Wrapper<CLocale>::~__Wrapper<CLocale>(void)
0x140009f92  mov     eax, 8007000Eh
0x140009f97  jmp     loc_14000A3B0
0x140009f9c  mov     r8, [rdi+8]; unsigned __int16 *
0x140009fa0  mov     rdx, rsi; unsigned __int64
0x140009fa3  mov     rcx, rax; unsigned __int16 *
0x140009fa6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140009fab  jmp     short loc_140009FD7
0x140009fad  lea     rcx, [rsp+0A8h+var_48]
0x140009fb2  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x140009fb7  nop
0x140009fb8  lea     rcx, [rsp+0A8h+var_68]
0x140009fbd  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x140009fc2  nop
0x140009fc3  lea     rcx, [rsp+0A8h+var_78]
0x140009fc8  call    ??1?$__Wrapper@VCLocale@@@@UEAA@XZ; __Wrapper<CLocale>::~__Wrapper<CLocale>(void)
0x140009fcd  mov     eax, 8000FFFFh
0x140009fd2  jmp     loc_14000A3B0
0x140009fd7  mov     [rsp+0A8h+lpString1], r15
0x140009fdc  mov     [rbx+10h], r11
0x140009fe0  lea     rcx, [rsp+0A8h+var_48]
0x140009fe5  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x140009fea  nop
0x140009feb  lea     rcx, [rsp+0A8h+var_68]
0x140009ff0  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x140009ff5  nop
0x140009ff6  mov     [rsp+0A8h+var_70], r15
0x140009ffb  lea     rcx, [rdi+10h]
0x140009fff  mov     rdx, rbx
0x14000a002  call    ?DataAdd@?$__WrapperARRAY@PEAVCLocale@@@@QEAAJPEAVCLocale@@@Z; __WrapperARRAY<CLocale *>::DataAdd(CLocale *)
0x14000a007  cmp     r15d, [rdi+38h]
0x14000a00b  jnb     loc_14000A37D
0x14000a011  mov     [rsp+0A8h+lpString1], 0
0x14000a01a  lea     rax, ??_7?$__WrapperBuffer@G@@6B@; const __WrapperBuffer<ushort>::`vftable'
0x14000a021  mov     [rsp+0A8h+var_48], rax
0x14000a026  mov     r14d, r15d
0x14000a029  mov     rax, [rdi+30h]
0x14000a02d  mov     rdx, [rax+r14*8]
0x14000a031  lea     r9, [rsp+0A8h+lpString1]; unsigned __int16 **
0x14000a036  lea     r8, aShow; "show"
0x14000a03d  mov     rdx, [rdx+8]; unsigned __int16 *
0x14000a041  mov     rsi, [rsp+0A8h+arg_10]
0x14000a049  mov     rcx, rsi; this
0x14000a04c  call    ?GetQualifierValue@CPerformanceObject@@QEAAJPEBG0PEAPEAG@Z; CPerformanceObject::GetQualifierValue(ushort const *,ushort const *,ushort * *)
0x14000a051  mov     r8, [rsp+0A8h+lpString1]; lpString1
0x14000a056  test    r8, r8
0x14000a059  jz      short loc_14000A086
0x14000a05b  mov     [rsp+0A8h+cchCount2], r12d; cchCount2
0x14000a060  lea     rax, String2; "false"
0x14000a067  mov     [rsp+0A8h+lpString2], rax; lpString2
0x14000a06c  mov     r9d, r12d; cchCount1
0x14000a06f  mov     edx, 1; dwCmpFlags
0x14000a074  lea     ecx, [rdx+7Eh]; Locale
0x14000a077  call    cs:__imp_CompareStringW
0x14000a07d  cmp     eax, r13d
0x14000a080  jz      loc_14000A328
0x14000a086  mov     [rsp+0A8h+var_60], 0
0x14000a08f  lea     rax, ??_7?$__WrapperPtr@VCLocale@@@@6B@; const __WrapperPtr<CLocale>::`vftable'
0x14000a096  mov     [rsp+0A8h+var_68], rax
0x14000a09b  mov     ecx, 18h
0x14000a0a0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x14000a0a6  mov     rbx, rax
0x14000a0a9  xor     eax, eax
0x14000a0ab  test    rbx, rbx
0x14000a0ae  jz      loc_14000A33A
0x14000a0b4  lea     rcx, ??_7CLocale@@6B@; const CLocale::`vftable'
0x14000a0bb  mov     [rbx], rcx
0x14000a0be  mov     [rbx+8], rax
0x14000a0c2  mov     [rbx+10h], rax
0x14000a0c6  mov     [rsp+0A8h+var_60], rbx
0x14000a0cb  mov     [rsp+0A8h+var_50], rax
0x14000a0d0  lea     rax, ??_7?$__WrapperBuffer@G@@6B@; const __WrapperBuffer<ushort>::`vftable'
0x14000a0d7  mov     [rsp+0A8h+var_58], rax
0x14000a0dc  mov     rax, [rdi+30h]
0x14000a0e0  mov     rdx, [rax+r14*8]
0x14000a0e4  lea     r9, [rsp+0A8h+var_50]; unsigned __int16 **
0x14000a0e9  lea     r8, aDisplayname; "displayname"
0x14000a0f0  mov     rdx, [rdx+8]; unsigned __int16 *
0x14000a0f4  mov     rcx, rsi; this
0x14000a0f7  call    ?GetQualifierValue@CPerformanceObject@@QEAAJPEBG0PEAPEAG@Z; CPerformanceObject::GetQualifierValue(ushort const *,ushort const *,ushort * *)
0x14000a0fc  mov     rax, [rdi+30h]
0x14000a100  mov     rcx, [rax+r14*8]
0x14000a104  mov     rcx, [rcx+8]; String
0x14000a108  test    rcx, rcx
0x14000a10b  jz      short loc_14000A115
0x14000a10d  call    cs:__imp_wcslen
0x14000a113  jmp     short loc_14000A117
0x14000a115  xor     eax, eax
0x14000a117  inc     eax
0x14000a119  mov     r11, [rsp+0A8h+var_50]
0x14000a11e  test    r11, r11
0x14000a121  jnz     loc_14000A1CC
0x14000a127  mov     esi, eax
0x14000a129  mov     rax, r13
0x14000a12c  mul     rsi
0x14000a12f  cmovb   rax, r12
0x14000a133  mov     rcx, rax
0x14000a136  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x14000a13c  mov     r11, rax
0x14000a13f  mov     [rsp+0A8h+var_50], rax
0x14000a144  test    rax, rax
0x14000a147  jnz     short loc_14000A17E
0x14000a149  lea     rcx, [rsp+0A8h+var_58]
0x14000a14e  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x14000a153  nop
0x14000a154  lea     rcx, [rsp+0A8h+var_68]
0x14000a159  call    ??1?$__Wrapper@VCLocale@@@@UEAA@XZ; __Wrapper<CLocale>::~__Wrapper<CLocale>(void)
0x14000a15e  nop
0x14000a15f  lea     rcx, [rsp+0A8h+var_48]
0x14000a164  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x14000a169  nop
0x14000a16a  lea     rcx, [rsp+0A8h+var_78]
0x14000a16f  call    ??1?$__Wrapper@VCLocale@@@@UEAA@XZ; __Wrapper<CLocale>::~__Wrapper<CLocale>(void)
0x14000a174  mov     eax, 8007000Eh
0x14000a179  jmp     loc_14000A3B0
0x14000a17e  mov     rax, [rdi+30h]
0x14000a182  mov     r8, [rax+r14*8]
0x14000a186  mov     r8, [r8+8]; unsigned __int16 *
0x14000a18a  mov     rdx, rsi; unsigned __int64
0x14000a18d  mov     rcx, r11; unsigned __int16 *
0x14000a190  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000a195  jmp     short loc_14000A1CE
0x14000a197  lea     rcx, [rsp+0A8h+var_58]
0x14000a19c  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x14000a1a1  nop
0x14000a1a2  lea     rcx, [rsp+0A8h+var_68]
0x14000a1a7  call    ??1?$__Wrapper@VCLocale@@@@UEAA@XZ; __Wrapper<CLocale>::~__Wrapper<CLocale>(void)
0x14000a1ac  nop
0x14000a1ad  lea     rcx, [rsp+0A8h+var_48]
0x14000a1b2  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x14000a1b7  nop
0x14000a1b8  lea     rcx, [rsp+0A8h+var_78]
0x14000a1bd  call    ??1?$__Wrapper@VCLocale@@@@UEAA@XZ; __Wrapper<CLocale>::~__Wrapper<CLocale>(void)
0x14000a1c2  mov     eax, 8000FFFFh
0x14000a1c7  jmp     loc_14000A3B0
0x14000a1cc  mov     esi, eax
0x14000a1ce  mov     [rsp+0A8h+var_50], 0
0x14000a1d7  mov     [rbx+8], r11
0x14000a1db  mov     [rsp+0A8h+var_30], 0
0x14000a1e4  lea     rax, ??_7?$__WrapperBuffer@G@@6B@; const __WrapperBuffer<ushort>::`vftable'
0x14000a1eb  mov     [rsp+0A8h+var_38], rax
0x14000a1f0  mov     rax, [rdi+30h]
0x14000a1f4  mov     rdx, [rax+r14*8]
0x14000a1f8  lea     r9, [rsp+0A8h+var_30]; unsigned __int16 **
0x14000a1fd  lea     r8, aDescription_0; "description"
0x14000a204  mov     rdx, [rdx+8]; unsigned __int16 *
0x14000a208  mov     rcx, [rsp+0A8h+arg_10]; this
0x14000a210  call    ?GetQualifierValue@CPerformanceObject@@QEAAJPEBG0PEAPEAG@Z; CPerformanceObject::GetQualifierValue(ushort const *,ushort const *,ushort * *)
0x14000a215  mov     r11, [rsp+0A8h+var_30]
0x14000a21a  test    r11, r11
0x14000a21d  jnz     loc_14000A2DC
0x14000a223  mov     rax, r13
0x14000a226  mul     rsi
0x14000a229  cmovb   rax, r12
0x14000a22d  mov     rcx, rax
0x14000a230  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x14000a236  mov     r11, rax
0x14000a239  mov     [rsp+0A8h+var_30], rax
0x14000a23e  test    rax, rax
0x14000a241  jnz     short loc_14000A283
0x14000a243  lea     rcx, [rsp+0A8h+var_38]
0x14000a248  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x14000a24d  nop
0x14000a24e  lea     rcx, [rsp+0A8h+var_58]
0x14000a253  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x14000a258  nop
0x14000a259  lea     rcx, [rsp+0A8h+var_68]
0x14000a25e  call    ??1?$__Wrapper@VCLocale@@@@UEAA@XZ; __Wrapper<CLocale>::~__Wrapper<CLocale>(void)
0x14000a263  nop
0x14000a264  lea     rcx, [rsp+0A8h+var_48]
0x14000a269  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x14000a26e  nop
0x14000a26f  lea     rcx, [rsp+0A8h+var_78]
0x14000a274  call    ??1?$__Wrapper@VCLocale@@@@UEAA@XZ; __Wrapper<CLocale>::~__Wrapper<CLocale>(void)
0x14000a279  mov     eax, 8007000Eh
0x14000a27e  jmp     loc_14000A3B0
0x14000a283  mov     rax, [rdi+30h]
0x14000a287  mov     r8, [rax+r14*8]
0x14000a28b  mov     r8, [r8+8]; unsigned __int16 *
0x14000a28f  mov     rdx, rsi; unsigned __int64
0x14000a292  mov     rcx, r11; unsigned __int16 *
0x14000a295  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000a29a  jmp     short loc_14000A2DC
0x14000a29c  lea     rcx, [rsp+0A8h+var_38]
0x14000a2a1  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x14000a2a6  nop
0x14000a2a7  lea     rcx, [rsp+0A8h+var_58]
0x14000a2ac  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x14000a2b1  nop
0x14000a2b2  lea     rcx, [rsp+0A8h+var_68]
0x14000a2b7  call    ??1?$__Wrapper@VCLocale@@@@UEAA@XZ; __Wrapper<CLocale>::~__Wrapper<CLocale>(void)
0x14000a2bc  nop
0x14000a2bd  lea     rcx, [rsp+0A8h+var_48]
0x14000a2c2  call    ??1?$__WrapperBuffer@G@@UEAA@XZ; __WrapperBuffer<ushort>::~__WrapperBuffer<ushort>(void)
0x14000a2c7  nop
  ... truncated ...
```
