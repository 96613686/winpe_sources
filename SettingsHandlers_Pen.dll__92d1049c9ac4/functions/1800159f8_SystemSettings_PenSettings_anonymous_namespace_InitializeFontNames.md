# SystemSettings::PenSettings::_anonymous_namespace_::InitializeFontNames

- ea: `0x1800159f8`
- end: `0x180015e72`
- name: `SystemSettings::PenSettings::_anonymous_namespace_::InitializeFontNames`
- size: `1146`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010788`

## callees

- `0x1800030e0`
- `0x1800037c0`
- `0x18000a2bc`
- `0x18000ed08`
- `0x18000eed4`
- `0x18000f0bc`
- `0x18000faf0`
- `0x180013940`
- `0x1800159f8`
- `0x180016910`
- `0x180019fcc`
- `0x18001a378`
- `0x18005d010`

## import_xrefs

- `DWrite!DWriteCreateFactory` at `0x180015a5d`
- `DWrite!DWriteCreateFactory` at `0x180015a5d`

## string_xrefs

- `0x180015a78`: `shellcommon\shell\settingshandlers\pen\lib\mischandlers.cpp`
- `0x180015b29`: `shellcommon\shell\settingshandlers\pen\lib\mischandlers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 SystemSettings::PenSettings::_anonymous_namespace_::InitializeFontNames()
{
  int v0; // eax
  unsigned int v1; // ebx
  __int64 v2; // rcx
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned int i; // edi
  int v9; // ecx
  _QWORD *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // ecx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-98h]
  __int64 v19; // [rsp+30h] [rbp-88h] BYREF
  __int64 v20; // [rsp+38h] [rbp-80h] BYREF
  __int64 v21; // [rsp+40h] [rbp-78h] BYREF
  __int64 v22; // [rsp+48h] [rbp-70h] BYREF
  __int128 v23; // [rsp+50h] [rbp-68h] BYREF
  __int64 v24; // [rsp+60h] [rbp-58h]
  int v25; // [rsp+68h] [rbp-50h] BYREF
  __int128 v26; // [rsp+70h] [rbp-48h] BYREF
  __int64 v27; // [rsp+80h] [rbp-38h]
  __int128 v28; // [rsp+88h] [rbp-30h] BYREF
  __int64 v29; // [rsp+98h] [rbp-20h]
  __int64 v30; // [rsp+A0h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( qword_18007CAE8 != (_QWORD)xmmword_18007CAF0 )
    return 0;
  v26 = 0;
  v27 = 0;
  v23 = 0;
  v24 = 0;
  v19 = 0;
  v0 = DWriteCreateFactory(0, &GUID_35d0e0b3_9076_4d2e_a016_a91b568a06b4, &v19);
  v1 = v0;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\mischandlers.cpp",
      (const char *)(unsigned int)v0,
      v18);
    v2 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    }
    if ( (_QWORD)v23 )
    {
      std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF8uLL);
      v23 = 0;
      v24 = 0;
    }
    if ( (_QWORD)v26 )
      std::_Deallocate<16>(v26, (v27 - v26) & 0xFFFFFFFFFFFFFFF8uLL);
    return v1;
  }
  v20 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 440LL))(v19, 0, &v20);
  v5 = v4;
  if ( v4 >= 0 )
  {
    for ( i = 0; i < (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20); ++i )
    {
      v21 = 0;
      if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v20 + 192LL))(v20, i, &v21) >= 0 )
      {
        v28 = 0;
        v29 = 0;
        v30 = 7;
        LOWORD(v28) = 0;
        LODWORD(v22) = 0;
        if ( (int)SystemSettings::PenSettings::_anonymous_namespace_::GetInformationalString(v21, 4, &v22, &v28) >= 0 )
        {
          v10 = operator new(0x20u);
          *(_OWORD *)v10 = 0;
          v10[2] = 0;
          v10[3] = 7;
          *(_WORD *)v10 = 0;
          v25 = 0;
          if ( (int)SystemSettings::PenSettings::_anonymous_namespace_::GetInformationalString(v21, 16, &v25, v10) >= 0 )
          {
            if ( v25 )
            {
              if ( (unsigned __int8)SystemSettings::PenSettings::_anonymous_namespace_::IsPartOfStaticList(
                                      v10,
                                      off_180063510) )
              {
                v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10);
                v22 = v11;
                if ( *((_QWORD *)&v26 + 1) == v27 )
                {
                  std::vector<unsigned short const *>::_Emplace_reallocate<unsigned short const *>(
                    &v26,
                    *((_QWORD *)&v26 + 1),
                    &v22);
                }
                else
                {
                  **((_QWORD **)&v26 + 1) = v11;
                  *((_QWORD *)&v26 + 1) += 8LL;
                }
              }
              else if ( (_DWORD)v22
                     && (unsigned __int8)SystemSettings::PenSettings::_anonymous_namespace_::IsPartOfStaticList(
                                           &v28,
                                           off_180063518) )
              {
                v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10);
                v22 = v12;
                if ( *((_QWORD *)&v23 + 1) == v24 )
                {
                  std::vector<unsigned short const *>::_Emplace_reallocate<unsigned short const *>(
                    &v23,
                    *((_QWORD *)&v23 + 1),
                    &v22);
                }
                else
                {
                  **((_QWORD **)&v23 + 1) = v12;
                  *((_QWORD *)&v23 + 1) += 8LL;
                }
              }
            }
          }
        }
        std::wstring::_Tidy_deallocate(&v28);
      }
      v13 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    std::vector<unsigned short const *>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short const *>>>,0>(
      v9,
      (unsigned int)&v21,
      xmmword_18007CAF0,
      v26,
      *((__int64 *)&v26 + 1));
    std::vector<unsigned short const *>::_Insert_counted_range<unsigned short const * const *>(
      v14,
      xmmword_18007CAF0,
      off_180063520,
      1);
    std::vector<unsigned short const *>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short const *>>>,0>(
      v15,
      (unsigned int)&v21,
      xmmword_18007CAF0,
      v23,
      *((__int64 *)&v23 + 1));
    v16 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    if ( (_QWORD)v23 )
    {
      std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF8uLL);
      v23 = 0;
      v24 = 0;
    }
    if ( (_QWORD)v26 )
      std::_Deallocate<16>(v26, (v27 - v26) & 0xFFFFFFFFFFFFFFF8uLL);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x99,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\mischandlers.cpp",
    (const char *)(unsigned int)v4,
    v18);
  v6 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v7 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  if ( (_QWORD)v23 )
  {
    std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF8uLL);
    v23 = 0;
    v24 = 0;
  }
  if ( (_QWORD)v26 )
    std::_Deallocate<16>(v26, (v27 - v26) & 0xFFFFFFFFFFFFFFF8uLL);
  return v5;
}

```

## disassembly

```asm
0x1800159f8  mov     r11, rsp
0x1800159fb  mov     [r11+8], rbx
0x1800159ff  mov     [r11+10h], rsi
0x180015a03  push    rdi
0x180015a04  sub     rsp, 0B0h
0x180015a0b  mov     rax, cs:__security_cookie
0x180015a12  xor     rax, rsp
0x180015a15  mov     [rsp+0B8h+var_10], rax
0x180015a1d  mov     rax, qword ptr cs:xmmword_18007CAF0
0x180015a24  cmp     cs:qword_18007CAE8, rax
0x180015a2b  jnz     loc_180015E4A
0x180015a31  xorps   xmm0, xmm0
0x180015a34  movdqu  [rsp+0B8h+var_48], xmm0
0x180015a3a  xor     esi, esi
0x180015a3c  mov     [r11-38h], rsi
0x180015a40  movdqu  [rsp+0B8h+var_68], xmm0
0x180015a46  mov     [r11-58h], rsi
0x180015a4a  mov     [rsp+0B8h+var_88], rsi
0x180015a4f  lea     r8, [rsp+0B8h+var_88]
0x180015a54  lea     rdx, _GUID_35d0e0b3_9076_4d2e_a016_a91b568a06b4
0x180015a5b  xor     ecx, ecx
0x180015a5d  call    cs:__imp_DWriteCreateFactory
0x180015a63  mov     ebx, eax
0x180015a65  test    eax, eax
0x180015a67  jns     loc_180015AF4
0x180015a6d  mov     rcx, [rsp+0B8h]; this
0x180015a75  mov     r9d, eax; char *
0x180015a78  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\p"...
0x180015a7f  mov     edx, 96h; void *
0x180015a84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015a89  nop
0x180015a8a  mov     rcx, [rsp+0B8h+var_88]
0x180015a8f  test    rcx, rcx
0x180015a92  jz      short loc_180015AA6
0x180015a94  mov     [rsp+0B8h+var_88], rsi
0x180015a99  mov     rax, [rcx]
0x180015a9c  mov     rax, [rax+10h]
0x180015aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aa5  nop
0x180015aa6  mov     rcx, qword ptr [rsp+0B8h+var_68]
0x180015aab  test    rcx, rcx
0x180015aae  jz      short loc_180015ACF
0x180015ab0  mov     rdx, [rsp+0B8h+var_58]
0x180015ab5  sub     rdx, rcx
0x180015ab8  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180015abc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015ac1  xorps   xmm0, xmm0
0x180015ac4  movdqu  [rsp+0B8h+var_68], xmm0
0x180015aca  mov     [rsp+0B8h+var_58], rsi
0x180015acf  mov     rcx, qword ptr [rsp+0B8h+var_48]
0x180015ad4  test    rcx, rcx
0x180015ad7  jz      short loc_180015AED
0x180015ad9  mov     rdx, [rsp+0B8h+var_38]
0x180015ae1  sub     rdx, rcx
0x180015ae4  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180015ae8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015aed  mov     eax, ebx
0x180015aef  jmp     loc_180015E4C
0x180015af4  mov     [rsp+0B8h+var_80], rsi
0x180015af9  mov     rcx, [rsp+0B8h+var_88]
0x180015afe  mov     rax, [rcx]
0x180015b01  lea     r8, [rsp+0B8h+var_80]
0x180015b06  xor     edx, edx
0x180015b08  mov     rax, [rax+1B8h]
0x180015b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b14  mov     ebx, eax
0x180015b16  test    eax, eax
0x180015b18  jns     loc_180015BC1
0x180015b1e  mov     rcx, [rsp+0B8h]; this
0x180015b26  mov     r9d, eax; char *
0x180015b29  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\p"...
0x180015b30  mov     edx, 99h; void *
0x180015b35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015b3a  nop
0x180015b3b  mov     rcx, [rsp+0B8h+var_80]
0x180015b40  test    rcx, rcx
0x180015b43  jz      short loc_180015B57
0x180015b45  mov     [rsp+0B8h+var_80], rsi
0x180015b4a  mov     rax, [rcx]
0x180015b4d  mov     rax, [rax+10h]
0x180015b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b56  nop
0x180015b57  mov     rcx, [rsp+0B8h+var_88]
0x180015b5c  test    rcx, rcx
0x180015b5f  jz      short loc_180015B73
0x180015b61  mov     [rsp+0B8h+var_88], rsi
0x180015b66  mov     rax, [rcx]
0x180015b69  mov     rax, [rax+10h]
0x180015b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b72  nop
0x180015b73  mov     rcx, qword ptr [rsp+0B8h+var_68]
0x180015b78  test    rcx, rcx
0x180015b7b  jz      short loc_180015B9C
0x180015b7d  mov     rdx, [rsp+0B8h+var_58]
0x180015b82  sub     rdx, rcx
0x180015b85  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180015b89  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015b8e  xorps   xmm0, xmm0
0x180015b91  movdqu  [rsp+0B8h+var_68], xmm0
0x180015b97  mov     [rsp+0B8h+var_58], rsi
0x180015b9c  mov     rcx, qword ptr [rsp+0B8h+var_48]
0x180015ba1  test    rcx, rcx
0x180015ba4  jz      short loc_180015BBA
0x180015ba6  mov     rdx, [rsp+0B8h+var_38]
0x180015bae  sub     rdx, rcx
0x180015bb1  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180015bb5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015bba  mov     eax, ebx
0x180015bbc  jmp     loc_180015E4C
0x180015bc1  mov     edi, esi
0x180015bc3  mov     rcx, [rsp+0B8h+var_80]
0x180015bc8  mov     rax, [rcx]
0x180015bcb  mov     rax, [rax+18h]
0x180015bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bd4  cmp     edi, eax
0x180015bd6  jnb     loc_180015D70
0x180015bdc  mov     [rsp+0B8h+var_78], rsi
0x180015be1  mov     rcx, [rsp+0B8h+var_80]
0x180015be6  mov     rax, [rcx]
0x180015be9  lea     r8, [rsp+0B8h+var_78]
0x180015bee  mov     edx, edi
0x180015bf0  mov     rax, [rax+0C0h]
0x180015bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bfc  test    eax, eax
0x180015bfe  js      loc_180015D4D
0x180015c04  xorps   xmm0, xmm0
0x180015c07  movups  [rsp+0B8h+var_30], xmm0
0x180015c0f  mov     [rsp+0B8h+var_20], rsi
0x180015c17  mov     [rsp+0B8h+var_18], 7
0x180015c23  mov     word ptr [rsp+0B8h+var_30], si
0x180015c2b  mov     dword ptr [rsp+0B8h+var_70], esi
0x180015c2f  lea     r9, [rsp+0B8h+var_30]
0x180015c37  lea     r8, [rsp+0B8h+var_70]
0x180015c3c  mov     edx, 4
0x180015c41  mov     rcx, [rsp+0B8h+var_78]
0x180015c46  call    SystemSettings__PenSettings___anonymous_namespace___GetInformationalString
0x180015c4b  test    eax, eax
0x180015c4d  js      loc_180015D3F
0x180015c53  mov     ecx, 20h ; ' '; Size
0x180015c58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015c5d  mov     rbx, rax
0x180015c60  xorps   xmm0, xmm0
0x180015c63  movups  xmmword ptr [rax], xmm0
0x180015c66  mov     [rax+10h], rsi
0x180015c6a  mov     qword ptr [rax+18h], 7
0x180015c72  mov     [rax], si
0x180015c75  mov     [rsp+0B8h+var_50], esi
0x180015c79  mov     r9, rax
0x180015c7c  lea     r8, [rsp+0B8h+var_50]
0x180015c81  mov     edx, 10h
0x180015c86  mov     rcx, [rsp+0B8h+var_78]
0x180015c8b  call    SystemSettings__PenSettings___anonymous_namespace___GetInformationalString
0x180015c90  test    eax, eax
0x180015c92  js      loc_180015D3F
0x180015c98  cmp     [rsp+0B8h+var_50], esi
0x180015c9c  jz      loc_180015D3F
0x180015ca2  lea     rdx, off_180063510; "Ink Free"
0x180015ca9  mov     rcx, rbx
0x180015cac  call    SystemSettings__PenSettings___anonymous_namespace___IsPartOfStaticList
0x180015cb1  test    al, al
0x180015cb3  jz      short loc_180015CED
0x180015cb5  mov     rcx, rbx
0x180015cb8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015cbd  mov     [rsp+0B8h+var_70], rax
0x180015cc2  mov     rdx, qword ptr [rsp+0B8h+var_48+8]
0x180015cc7  cmp     rdx, [rsp+0B8h+var_38]
0x180015ccf  jz      short loc_180015CDC
0x180015cd1  mov     [rdx], rax
0x180015cd4  add     qword ptr [rsp+0B8h+var_48+8], 8
0x180015cda  jmp     short loc_180015D3F
0x180015cdc  lea     r8, [rsp+0B8h+var_70]
0x180015ce1  lea     rcx, [rsp+0B8h+var_48]
0x180015ce6  call    ??$_Emplace_reallocate@PEBG@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAPEAPEBGQEAPEBG$$QEAPEBG@Z; std::vector<ushort const *>::_Emplace_reallocate<ushort const *>(ushort const * * const,ushort const * &&)
0x180015ceb  jmp     short loc_180015D3F
0x180015ced  cmp     dword ptr [rsp+0B8h+var_70], esi
0x180015cf1  jz      short loc_180015D3F
0x180015cf3  lea     rdx, off_180063518; "Microsoft Font Maker"
0x180015cfa  lea     rcx, [rsp+0B8h+var_30]
0x180015d02  call    SystemSettings__PenSettings___anonymous_namespace___IsPartOfStaticList
0x180015d07  test    al, al
0x180015d09  jz      short loc_180015D3F
0x180015d0b  mov     rcx, rbx
0x180015d0e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015d13  mov     [rsp+0B8h+var_70], rax
0x180015d18  mov     rdx, qword ptr [rsp+0B8h+var_68+8]
0x180015d1d  cmp     rdx, [rsp+0B8h+var_58]
0x180015d22  jz      short loc_180015D2F
0x180015d24  mov     [rdx], rax
0x180015d27  add     qword ptr [rsp+0B8h+var_68+8], 8
0x180015d2d  jmp     short loc_180015D3F
0x180015d2f  lea     r8, [rsp+0B8h+var_70]
0x180015d34  lea     rcx, [rsp+0B8h+var_68]
0x180015d39  call    ??$_Emplace_reallocate@PEBG@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAPEAPEBGQEAPEBG$$QEAPEBG@Z; std::vector<ushort const *>::_Emplace_reallocate<ushort const *>(ushort const * * const,ushort const * &&)
0x180015d3e  nop
0x180015d3f  lea     rcx, [rsp+0B8h+var_30]
0x180015d47  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015d4c  nop
0x180015d4d  mov     rcx, [rsp+0B8h+var_78]
0x180015d52  test    rcx, rcx
0x180015d55  jz      short loc_180015D69
0x180015d57  mov     [rsp+0B8h+var_78], rsi
0x180015d5c  mov     rax, [rcx]
0x180015d5f  mov     rax, [rax+10h]
0x180015d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d68  nop
0x180015d69  inc     edi
0x180015d6b  jmp     loc_180015BC3
0x180015d70  mov     rax, qword ptr [rsp+0B8h+var_48+8]
0x180015d75  mov     qword ptr [rsp+0B8h+var_98], rax
0x180015d7a  mov     r9, qword ptr [rsp+0B8h+var_48]
0x180015d7f  mov     r8, qword ptr cs:xmmword_18007CAF0
0x180015d86  lea     rdx, [rsp+0B8h+var_78]
0x180015d8b  call    ??$insert@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEBG@std@@@std@@@std@@$0A@@?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEBG@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@PEBG@std@@@std@@@1@V21@1@Z; std::vector<ushort const *>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort const *>>>,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ushort const *>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort const *>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort const *>>>)
0x180015d90  mov     r9d, 1
0x180015d96  lea     r8, off_180063520; "Segoe UI"
0x180015d9d  mov     rdx, qword ptr cs:xmmword_18007CAF0
0x180015da4  call    ??$_Insert_counted_range@PEBQEBG@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@PEBG@std@@@std@@@1@PEBQEBG_K@Z; std::vector<ushort const *>::_Insert_counted_range<ushort const * const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ushort const *>>>,ushort const * const *,unsigned __int64)
0x180015da9  mov     rax, qword ptr [rsp+0B8h+var_68+8]
0x180015dae  mov     qword ptr [rsp+0B8h+var_98], rax
0x180015db3  mov     r9, qword ptr [rsp+0B8h+var_68]
0x180015db8  mov     r8, qword ptr cs:xmmword_18007CAF0
0x180015dbf  lea     rdx, [rsp+0B8h+var_78]
0x180015dc4  call    ??$insert@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEBG@std@@@std@@@std@@$0A@@?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEBG@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@PEBG@std@@@std@@@1@V21@1@Z; std::vector<ushort const *>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort const *>>>,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ushort const *>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort const *>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort const *>>>)
0x180015dc9  nop
0x180015dca  mov     rcx, [rsp+0B8h+var_80]
0x180015dcf  test    rcx, rcx
0x180015dd2  jz      short loc_180015DE6
0x180015dd4  mov     [rsp+0B8h+var_80], rsi
0x180015dd9  mov     rax, [rcx]
0x180015ddc  mov     rax, [rax+10h]
0x180015de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015de5  nop
0x180015de6  mov     rcx, [rsp+0B8h+var_88]
0x180015deb  test    rcx, rcx
0x180015dee  jz      short loc_180015E02
0x180015df0  mov     [rsp+0B8h+var_88], rsi
0x180015df5  mov     rax, [rcx]
0x180015df8  mov     rax, [rax+10h]
0x180015dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e01  nop
0x180015e02  mov     rcx, qword ptr [rsp+0B8h+var_68]
0x180015e07  test    rcx, rcx
0x180015e0a  jz      short loc_180015E2B
0x180015e0c  mov     rdx, [rsp+0B8h+var_58]
0x180015e11  sub     rdx, rcx
0x180015e14  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180015e18  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015e1d  xorps   xmm0, xmm0
0x180015e20  movdqu  [rsp+0B8h+var_68], xmm0
0x180015e26  mov     [rsp+0B8h+var_58], rsi
0x180015e2b  mov     rcx, qword ptr [rsp+0B8h+var_48]
0x180015e30  test    rcx, rcx
0x180015e33  jz      short loc_180015E4A
0x180015e35  mov     rdx, [rsp+0B8h+var_38]
0x180015e3d  sub     rdx, rcx
0x180015e40  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180015e44  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015e49  nop
0x180015e4a  xor     eax, eax
0x180015e4c  mov     rcx, [rsp+0B8h+var_10]
0x180015e54  xor     rcx, rsp; StackCookie
0x180015e57  call    __security_check_cookie
0x180015e5c  lea     r11, [rsp+0B8h+var_8]
0x180015e64  mov     rbx, [r11+10h]
0x180015e68  mov     rsi, [r11+18h]
0x180015e6c  mov     rsp, r11
0x180015e6f  pop     rdi
0x180015e70  retn
```
