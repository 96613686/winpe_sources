# ResourceLoader6::SimpleResourceLoader::get_Option(ushort *,tagVARIANT *)

- ea: `0x180038660`
- end: `0x18003888f`
- name: `?get_Option@SimpleResourceLoader@ResourceLoader6@@UEAAJPEAGPEAUtagVARIANT@@@Z`
- size: `559`
- prototype: `int(ResourceLoader6::SimpleResourceLoader *__hidden this, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009790`
- `0x180024954`
- `0x1800325e8`
- `0x18003757c`
- `0x180038660`
- `0x180038898`
- `0x1800388ec`
- `0x180041974`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003869e`
- `OLEAUT32!__imp_VariantInit` at `0x18003869e`

## string_xrefs

- `0x1800386a4`: `BinaryPath`
- `0x1800386ee`: `RegistryPath`
- `0x1800387b2`: `QuerySpellerLexiconPath`
- `0x1800387d5`: `ProofLexPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ResourceLoader6::SimpleResourceLoader::get_Option(
        ResourceLoader6::SimpleResourceLoader *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  __int64 v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  char *v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 result; // rax
  _com_error *v14; // rbx
  _com_error *v16; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v17[32]; // [rsp+38h] [rbp-40h] BYREF
  void *retaddr; // [rsp+78h] [rbp+0h]

  if ( !a2 || !a3 )
    return 2147942487LL;
  try
  {
    VariantInit(a3);
    if ( !(unsigned int)CMN_CompareStringNoCaseW(a2, L"BinaryPath")
      && (__int64)(*((_QWORD *)this + 3) - *((_QWORD *)this + 2)) >> 5 )
    {
      v7 = (_QWORD *)ResourceLoader6::SimpleResourceLoader::PathsToString(v6, v17);
      if ( v7[3] >= 8u )
        v7 = (_QWORD *)*v7;
LABEL_13:
      _variant_t::operator=(a3, v7);
      LOBYTE(v9) = 1;
      std::wstring::_Tidy(v17, v9, 0);
      return 0;
    }
    if ( !(unsigned int)CMN_CompareStringNoCaseW(a2, L"RegistryPath")
      && (__int64)(*((_QWORD *)this + 6) - *((_QWORD *)this + 5)) >> 5 )
    {
      v7 = (_QWORD *)ResourceLoader6::SimpleResourceLoader::PathsToString(v8, v17);
      if ( v7[3] >= 8u )
        v7 = (_QWORD *)*v7;
      goto LABEL_13;
    }
    if ( !(unsigned int)CMN_CompareStringNoCaseW(a2, L"CustomDict") && *((_QWORD *)this + 11) )
    {
      v10 = (char *)this + 72;
LABEL_30:
      if ( *((_QWORD *)v10 + 3) >= 8u )
        v10 = *(char **)v10;
      _variant_t::operator=(a3, v10);
      return 0;
    }
    if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"QuerySpeller") || !*((_BYTE *)this + 105) )
    {
      if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsPreReform") || !*((_BYTE *)this + 107) )
      {
        if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"QuerySpellerLexiconPath") || !*((_QWORD *)this + 16) )
        {
          if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"ProofLexPath") || !*((_QWORD *)this + 20) )
          {
            if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"Locale") || *((_WORD *)this + 34) == 0xFFFF )
            {
              if ( *((_QWORD *)this + 1) )
              {
                v12 = _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->((__int64 *)this + 1);
                return (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, struct tagVARIANT *))(*(_QWORD *)v12 + 40LL))(
                         v12,
                         a2,
                         a3);
              }
            }
            else
            {
              _variant_t::operator=(a3, *((unsigned __int16 *)this + 34));
            }
            return 0;
          }
          v10 = (char *)this + 144;
        }
        else
        {
          v10 = (char *)this + 112;
        }
        goto LABEL_30;
      }
      LOBYTE(v11) = *((_BYTE *)this + 106);
    }
    else
    {
      LOBYTE(v11) = *((_BYTE *)this + 104);
    }
    _variant_t::operator=(a3, v11);
    return 0;
  }
  catch ( _com_error *v16 )
  {
    v14 = v16;
    ImxTraceCatch(1, *((unsigned int *)v16 + 2), retaddr);
    return *((unsigned int *)v14 + 2);
  }
  catch ( exception )
  {
    ImxTraceCatch(2, 2147500037LL, retaddr);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180038660  push    rbx
0x180038662  push    rsi
0x180038663  push    rdi
0x180038664  sub     rsp, 60h
0x180038668  mov     [rsp+78h+var_50], 0FFFFFFFFFFFFFFFEh
0x180038671  mov     rax, cs:__security_cookie
0x180038678  xor     rax, rsp
0x18003867b  mov     [rsp+78h+var_20], rax
0x180038680  mov     rdi, r8
0x180038683  mov     rsi, rdx
0x180038686  mov     rbx, rcx
0x180038689  test    rdx, rdx
0x18003868c  jz      loc_180038874
0x180038692  test    r8, r8
0x180038695  jz      loc_180038874
0x18003869b  mov     rcx, r8; pvarg
0x18003869e  call    cs:__imp_VariantInit
0x1800386a4  lea     rdx, aBinarypath; "BinaryPath"
0x1800386ab  mov     rcx, rsi
0x1800386ae  call    CMN_CompareStringNoCaseW
0x1800386b3  test    eax, eax
0x1800386b5  jnz     short loc_1800386EE
0x1800386b7  lea     r8, [rbx+10h]
0x1800386bb  mov     rax, [r8+8]
0x1800386bf  sub     rax, [r8]
0x1800386c2  sar     rax, 5
0x1800386c6  test    rax, rax
0x1800386c9  jz      short loc_1800386EE
0x1800386cb  lea     rdx, [rsp+78h+var_40]
0x1800386d0  call    ?PathsToString@SimpleResourceLoader@ResourceLoader6@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z; ResourceLoader6::SimpleResourceLoader::PathsToString(std::vector<std::wstring> &)
0x1800386d5  nop
0x1800386d6  cmp     qword ptr [rax+18h], 8
0x1800386db  jb      short loc_1800386E0
0x1800386dd  mov     rax, [rax]
0x1800386e0  mov     rdx, rax
0x1800386e3  mov     rcx, rdi
0x1800386e6  call    ??4_variant_t@@QEAAAEAV0@PEBG@Z; _variant_t::operator=(ushort const *)
0x1800386eb  nop
0x1800386ec  jmp     short loc_180038736
0x1800386ee  lea     rdx, aRegistrypath; "RegistryPath"
0x1800386f5  mov     rcx, rsi
0x1800386f8  call    CMN_CompareStringNoCaseW
0x1800386fd  test    eax, eax
0x1800386ff  jnz     short loc_18003874A
0x180038701  lea     r8, [rbx+28h]
0x180038705  mov     rax, [r8+8]
0x180038709  sub     rax, [r8]
0x18003870c  sar     rax, 5
0x180038710  test    rax, rax
0x180038713  jz      short loc_18003874A
0x180038715  lea     rdx, [rsp+78h+var_40]
0x18003871a  call    ?PathsToString@SimpleResourceLoader@ResourceLoader6@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z; ResourceLoader6::SimpleResourceLoader::PathsToString(std::vector<std::wstring> &)
0x18003871f  nop
0x180038720  cmp     qword ptr [rax+18h], 8
0x180038725  jb      short loc_18003872A
0x180038727  mov     rax, [rax]
0x18003872a  mov     rdx, rax
0x18003872d  mov     rcx, rdi
0x180038730  call    ??4_variant_t@@QEAAAEAV0@PEBG@Z; _variant_t::operator=(ushort const *)
0x180038735  nop
0x180038736  xor     r8d, r8d
0x180038739  mov     dl, 1
0x18003873b  lea     rcx, [rsp+78h+var_40]
0x180038740  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180038745  jmp     loc_180038863
0x18003874a  lea     rdx, aCustomdict; "CustomDict"
0x180038751  mov     rcx, rsi
0x180038754  call    CMN_CompareStringNoCaseW
0x180038759  test    eax, eax
0x18003875b  jnz     short loc_18003876D
0x18003875d  cmp     qword ptr [rbx+58h], 0
0x180038762  jbe     short loc_18003876D
0x180038764  lea     rdx, [rbx+48h]
0x180038768  jmp     loc_1800387F9
0x18003876d  lea     rdx, aQueryspeller; "QuerySpeller"
0x180038774  mov     rcx, rsi
0x180038777  call    CMN_CompareStringNoCaseW
0x18003877c  test    eax, eax
0x18003877e  jnz     short loc_18003878A
0x180038780  cmp     [rbx+69h], al
0x180038783  jz      short loc_18003878A
0x180038785  mov     dl, [rbx+68h]
0x180038788  jmp     short loc_1800387A5
0x18003878a  lea     rdx, aIsprereform; "IsPreReform"
0x180038791  mov     rcx, rsi
0x180038794  call    CMN_CompareStringNoCaseW
0x180038799  test    eax, eax
0x18003879b  jnz     short loc_1800387B2
0x18003879d  cmp     [rbx+6Bh], al
0x1800387a0  jz      short loc_1800387B2
0x1800387a2  mov     dl, [rbx+6Ah]
0x1800387a5  mov     rcx, rdi
0x1800387a8  call    ??4_variant_t@@QEAAAEAV0@_N@Z; _variant_t::operator=(bool)
0x1800387ad  jmp     loc_180038863
0x1800387b2  lea     rdx, aQueryspellerle; "QuerySpellerLexiconPath"
0x1800387b9  mov     rcx, rsi
0x1800387bc  call    CMN_CompareStringNoCaseW
0x1800387c1  test    eax, eax
0x1800387c3  jnz     short loc_1800387D5
0x1800387c5  cmp     qword ptr [rbx+80h], 0
0x1800387cd  jbe     short loc_1800387D5
0x1800387cf  lea     rdx, [rbx+70h]
0x1800387d3  jmp     short loc_1800387F9
0x1800387d5  lea     rdx, aProoflexpath; "ProofLexPath"
0x1800387dc  mov     rcx, rsi
0x1800387df  call    CMN_CompareStringNoCaseW
0x1800387e4  test    eax, eax
0x1800387e6  jnz     short loc_18003880D
0x1800387e8  cmp     qword ptr [rbx+0A0h], 0
0x1800387f0  jbe     short loc_18003880D
0x1800387f2  lea     rdx, [rbx+90h]
0x1800387f9  cmp     qword ptr [rdx+18h], 8
0x1800387fe  jb      short loc_180038803
0x180038800  mov     rdx, [rdx]
0x180038803  mov     rcx, rdi
0x180038806  call    ??4_variant_t@@QEAAAEAV0@PEBG@Z; _variant_t::operator=(ushort const *)
0x18003880b  jmp     short loc_180038863
0x18003880d  lea     rdx, aLocale; "Locale"
0x180038814  mov     rcx, rsi
0x180038817  call    CMN_CompareStringNoCaseW
0x18003881c  test    eax, eax
0x18003881e  jnz     short loc_18003883A
0x180038820  movzx   eax, word ptr [rbx+44h]
0x180038824  mov     ecx, 0FFFFh
0x180038829  cmp     ax, cx
0x18003882c  jz      short loc_18003883A
0x18003882e  mov     edx, eax
0x180038830  mov     rcx, rdi
0x180038833  call    ??4_variant_t@@QEAAAEAV0@J@Z; _variant_t::operator=(long)
0x180038838  jmp     short loc_180038863
0x18003883a  lea     rcx, [rbx+8]
0x18003883e  cmp     qword ptr [rcx], 0
0x180038842  jz      short loc_180038863
0x180038844  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x180038849  mov     r9, rax
0x18003884c  mov     rcx, [rax]
0x18003884f  mov     rax, [rcx+28h]
0x180038853  mov     r8, rdi
0x180038856  mov     rdx, rsi
0x180038859  mov     rcx, r9
0x18003885c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038861  jmp     short loc_180038879
0x180038863  xor     eax, eax
0x180038865  jmp     short loc_180038879
0x180038867  mov     eax, [rsp+78h+var_58]
0x18003886b  jmp     short loc_180038872
0x18003886d  mov     eax, 80004005h
0x180038872  jmp     short loc_180038879
0x180038874  mov     eax, 80070057h
0x180038879  mov     rcx, [rsp+78h+var_20]
0x18003887e  xor     rcx, rsp; StackCookie
0x180038881  call    __security_check_cookie
0x180038886  add     rsp, 60h
0x18003888a  pop     rdi
0x18003888b  pop     rsi
0x18003888c  pop     rbx
0x18003888d  retn
```
