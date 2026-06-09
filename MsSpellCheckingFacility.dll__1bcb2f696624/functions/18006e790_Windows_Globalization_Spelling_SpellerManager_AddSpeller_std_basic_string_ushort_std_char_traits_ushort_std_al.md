# Windows::Globalization::Spelling::SpellerManager::AddSpeller(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18006e790`
- end: `0x18006e8dd`
- name: `?AddSpeller@SpellerManager@Spelling@Globalization@Windows@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `333`
- prototype: `HRESULT __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004293c`

## callees

- `0x1800331b0`
- `0x1800379b8`
- `0x180039040`
- `0x180061320`
- `0x18006e628`
- `0x18006e790`
- `0x180070908`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18006e7d0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18006e7d0`

## pseudocode

```c
HRESULT __fastcall Windows::Globalization::Spelling::SpellerManager::AddSpeller(__int64 a1, __int64 a2, __int64 a3)
{
  bool v3; // cc
  const OLECHAR *v7; // rcx
  HRESULT result; // eax
  _QWORD *v9; // rax
  __int64 v10; // r8
  int v11; // ebx
  __int64 v12; // r8
  __int64 v13; // [rsp+30h] [rbp-40h] BYREF
  struct ISpellCheckProviderFactory *v14; // [rsp+38h] [rbp-38h] BYREF
  GUID pclsid; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v16[16]; // [rsp+50h] [rbp-20h] BYREF

  v3 = *(_QWORD *)(a3 + 24) <= 7u;
  pclsid = 0;
  if ( v3 )
    v7 = (const OLECHAR *)a3;
  else
    v7 = *(const OLECHAR **)a3;
  result = CLSIDFromString(v7, &pclsid);
  v14 = 0;
  if ( result >= 0 )
  {
    result = Windows::Globalization::Spelling::SpellerManager::InstantiateSpellCheckerFactory(&pclsid, &v14);
    if ( result >= 0 )
    {
      v9 = (_QWORD *)std::map<std::wstring const,std::wstring,Windows::Globalization::OrdinalIgnoreCaseLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::_Try_emplace<std::wstring const &,>(
                       a1 + 8,
                       v16,
                       a2);
      std::wstring::operator=(*v9 + 64LL, a3);
      if ( (Microsoft_Windows_Spell_CheckingEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          SPELL_CHECKING_ETW_PROVIDER_Context,
          ProviderSupportedLanguagesSend,
          v10,
          1,
          v16);
      v13 = 0;
      v11 = (*(__int64 (__fastcall **)(struct ISpellCheckProviderFactory *, __int64 *))(*(_QWORD *)v14 + 24LL))(
              v14,
              &v13);
      if ( (Microsoft_Windows_Spell_CheckingEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          SPELL_CHECKING_ETW_PROVIDER_Context,
          ProviderSupportedLanguagesReceive,
          v12,
          1,
          v16);
      if ( v11 >= 0 )
      {
        Windows::Globalization::Spelling::SpellerManager::AddLanguages(a1, a2, v13);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      return (*(__int64 (__fastcall **)(struct ISpellCheckProviderFactory *))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006e790  mov     [rsp-18h+arg_18], rbx
0x18006e795  push    rbp
0x18006e796  push    rsi
0x18006e797  push    rdi
0x18006e798  mov     rbp, rsp
0x18006e79b  sub     rsp, 70h
0x18006e79f  mov     rax, cs:__security_cookie
0x18006e7a6  xor     rax, rsp
0x18006e7a9  mov     [rbp+var_10], rax
0x18006e7ad  cmp     qword ptr [r8+18h], 7
0x18006e7b2  xorps   xmm0, xmm0
0x18006e7b5  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x18006e7b9  mov     rbx, r8
0x18006e7bc  mov     rsi, rdx
0x18006e7bf  mov     rdi, rcx
0x18006e7c2  jbe     short loc_18006E7C9
0x18006e7c4  mov     rcx, [r8]
0x18006e7c7  jmp     short loc_18006E7CC
0x18006e7c9  mov     rcx, rbx; lpsz
0x18006e7cc  lea     rdx, [rbp+pclsid]; pclsid
0x18006e7d0  call    cs:__imp_CLSIDFromString
0x18006e7d6  mov     [rbp+var_38], 0
0x18006e7de  test    eax, eax
0x18006e7e0  js      loc_18006E8C1
0x18006e7e6  lea     rdx, [rbp+var_38]; struct ISpellCheckProviderFactory **
0x18006e7ea  lea     rcx, [rbp+pclsid]; struct _GUID *
0x18006e7ee  call    ?InstantiateSpellCheckerFactory@SpellerManager@Spelling@Globalization@Windows@@SAJAEBU_GUID@@PEAPEAUISpellCheckProviderFactory@@@Z; Windows::Globalization::Spelling::SpellerManager::InstantiateSpellCheckerFactory(_GUID const &,ISpellCheckProviderFactory * *)
0x18006e7f3  test    eax, eax
0x18006e7f5  js      loc_18006E8C1
0x18006e7fb  lea     rcx, [rdi+8]
0x18006e7ff  mov     r8, rsi
0x18006e802  lea     rdx, [rbp+var_20]
0x18006e806  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@VOrdinalIgnoreCaseLess@Globalization@Windows@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring const,std::wstring,Windows::Globalization::OrdinalIgnoreCaseLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18006e80b  mov     rdx, rbx
0x18006e80e  mov     rcx, [rax]
0x18006e811  add     rcx, 40h ; '@'
0x18006e815  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18006e81a  test    cs:Microsoft_Windows_Spell_CheckingEnableBits, 1
0x18006e821  jz      short loc_18006E845
0x18006e823  lea     rax, [rbp+var_20]
0x18006e827  mov     r9d, 1
0x18006e82d  lea     rdx, ProviderSupportedLanguagesSend
0x18006e834  mov     [rsp+70h+var_50], rax
0x18006e839  lea     rcx, SPELL_CHECKING_ETW_PROVIDER_Context
0x18006e840  call    McGenEventWrite_EventWriteTransfer
0x18006e845  mov     rcx, [rbp+var_38]
0x18006e849  lea     rdx, [rbp+var_40]
0x18006e84d  mov     [rbp+var_40], 0
0x18006e855  mov     rax, [rcx]
0x18006e858  mov     rax, [rax+18h]
0x18006e85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e861  test    cs:Microsoft_Windows_Spell_CheckingEnableBits, 1
0x18006e868  mov     ebx, eax
0x18006e86a  jz      short loc_18006E88E
0x18006e86c  lea     rax, [rbp+var_20]
0x18006e870  mov     r9d, 1
0x18006e876  lea     rdx, ProviderSupportedLanguagesReceive
0x18006e87d  mov     [rsp+70h+var_50], rax
0x18006e882  lea     rcx, SPELL_CHECKING_ETW_PROVIDER_Context
0x18006e889  call    McGenEventWrite_EventWriteTransfer
0x18006e88e  test    ebx, ebx
0x18006e890  js      short loc_18006E8B1
0x18006e892  mov     r8, [rbp+var_40]
0x18006e896  mov     rdx, rsi
0x18006e899  mov     rcx, rdi
0x18006e89c  call    ?AddLanguages@SpellerManager@Spelling@Globalization@Windows@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIEnumString@@@Z; Windows::Globalization::Spelling::SpellerManager::AddLanguages(std::wstring const &,IEnumString *)
0x18006e8a1  mov     rcx, [rbp+var_40]
0x18006e8a5  mov     rax, [rcx]
0x18006e8a8  mov     rax, [rax+10h]
0x18006e8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e8b1  mov     rcx, [rbp+var_38]
0x18006e8b5  mov     rax, [rcx]
0x18006e8b8  mov     rax, [rax+10h]
0x18006e8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e8c1  mov     rcx, [rbp+var_10]
0x18006e8c5  xor     rcx, rsp; StackCookie
0x18006e8c8  call    __security_check_cookie
0x18006e8cd  mov     rbx, [rsp+70h+arg_18]
0x18006e8d5  add     rsp, 70h
0x18006e8d9  pop     rdi
0x18006e8da  pop     rsi
0x18006e8db  pop     rbp
0x18006e8dc  retn
```
