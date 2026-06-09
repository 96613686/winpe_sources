# Uev::TemplateIndex::LoadIndex(void)

- ea: `0x140045af8`
- end: `0x140045daf`
- name: `?LoadIndex@TemplateIndex@Uev@@QEAAXXZ`
- size: `695`
- prototype: `void __fastcall(Uev::TemplateIndex *__hidden this)`
- caller_count: `5`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140035b48`
- `0x14003b0a0`
- `0x14003bea0`
- `0x14003d840`
- `0x14003e500`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140004ab4`
- `0x14000d1d8`
- `0x14000d260`
- `0x14000d5ac`
- `0x140019190`
- `0x1400322b8`
- `0x14004550c`
- `0x140045724`
- `0x1400458b0`
- `0x140045af8`
- `0x14004691c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140045b6b`
- `ADVAPI32!RegOpenKeyExW` at `0x140045bea`
- `ADVAPI32!RegOpenKeyExW` at `0x140045b6b`
- `ADVAPI32!RegOpenKeyExW` at `0x140045bea`

## string_xrefs

- `0x140045cdb`: `Attempting to use an invalid handle.`
- `0x140045d51`: `Attempting to use an invalid handle.`
- `0x140045d80`: `Attempting to use an invalid handle.`
- `0x140045d22`: `Unable to open index registry key.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Uev::TemplateIndex::LoadIndex(Uev::TemplateIndex *this)
{
  unsigned int v2; // r15d
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  __int64 v5; // rcx
  _QWORD *v6; // r14
  __int64 i; // rbx
  _QWORD *v8; // rsi
  int v9; // r15d
  const WCHAR *v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rdi
  _QWORD **SubKeyNames; // rax
  void *v14; // rdi
  __int64 j; // rdi
  void *v16; // [rsp+38h] [rbp-61h] BYREF
  _QWORD *v17; // [rsp+40h] [rbp-59h]
  void *Block; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v19[32]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+70h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+17h] BYREF
  HKEY phkResult; // [rsp+B8h] [rbp+1Fh] BYREF

  v2 = 0;
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,Uev::TemplateIndex::ihash,Uev::TemplateIndex::iequal_to>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::clear((char *)this + 8);
  hKey = 0;
  v3 = (const WCHAR *)&Uev::TemplateIndex::s_templateIndexKeyName;
  if ( (unsigned __int64)qword_1400D17E8 > 7 )
    v3 = Uev::TemplateIndex::s_templateIndexKeyName;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x109u, &hKey);
  if ( v4 )
  {
    if ( v4 != 2 )
    {
      if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v5, TemplateMsg_UnableToOpenIndexRegistryKey, v4);
      std::wstring::wstring(v19, L"Unable to open index registry key.");
      Uev::TemplateIndexException::TemplateIndexException(pExceptionObject, v19);
      throw (Uev::TemplateIndexException *)pExceptionObject;
    }
  }
  else
  {
    if ( !hKey )
    {
      std::wstring::wstring(v19, L"Attempting to use an invalid handle.");
      Uev::SmartHandleException::SmartHandleException(pExceptionObject, v19);
      throw (Uev::SmartHandleException *)pExceptionObject;
    }
    Uev::TemplateIndex::GetSubKeyNames(v5, &v16);
    v6 = v16;
    if ( v16 )
    {
      for ( i = *(_QWORD *)v16; i != v6[1]; i += 32 )
      {
        if ( !hKey )
        {
          std::wstring::wstring(v19, L"Attempting to use an invalid handle.");
          Uev::SmartHandleException::SmartHandleException(pExceptionObject, v19);
          throw (Uev::SmartHandleException *)pExceptionObject;
        }
        v8 = 0;
        v17 = 0;
        v9 = v2 | 1;
        phkResult = 0;
        if ( *(_QWORD *)(i + 24) <= 7u )
          v10 = (const WCHAR *)i;
        else
          v10 = *(const WCHAR **)i;
        v12 = 0;
        if ( !RegOpenKeyExW(hKey, v10, 0, 0x109u, &phkResult) )
        {
          if ( !phkResult )
          {
            std::wstring::wstring(v19, L"Attempting to use an invalid handle.");
            Uev::SmartHandleException::SmartHandleException(pExceptionObject, v19);
            throw (Uev::SmartHandleException *)pExceptionObject;
          }
          SubKeyNames = (_QWORD **)Uev::TemplateIndex::GetSubKeyNames(v11, &Block);
          v8 = *SubKeyNames;
          *SubKeyNames = 0;
          v17 = v8;
          v14 = Block;
          if ( Block )
          {
            std::vector<std::wstring>::_Tidy(Block);
            operator delete(v14);
          }
          v12 = v8;
        }
        Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&phkResult);
        if ( v12 )
        {
          for ( j = *v8; j != v8[1]; j += 32 )
            Uev::TemplateIndex::AddTemplateID(this, i, j);
        }
        v2 = v9 & 0xFFFFFFFE;
        if ( v8 )
        {
          std::vector<std::wstring>::_Tidy(v8);
          operator delete(v8);
        }
      }
    }
    if ( v6 )
    {
      std::vector<std::wstring>::_Tidy(v6);
      operator delete(v6);
    }
  }
  Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&hKey);
}

```

## disassembly

```asm
0x140045af8  mov     [rsp-8+arg_8], rbx
0x140045afd  mov     [rsp-8+arg_10], rsi
0x140045b02  push    rbp
0x140045b03  push    rdi
0x140045b04  push    r13
0x140045b06  push    r14
0x140045b08  push    r15
0x140045b0a  lea     rbp, [rsp-37h]
0x140045b0f  sub     rsp, 0D0h
0x140045b16  mov     rax, cs:__security_cookie
0x140045b1d  xor     rax, rsp
0x140045b20  mov     [rbp+57h+var_30], rax
0x140045b24  mov     r13, rcx
0x140045b27  xor     r15d, r15d
0x140045b2a  mov     [rbp+57h+var_C0], r15d
0x140045b2e  add     rcx, 8
0x140045b32  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vihash@TemplateIndex@Uev@@Uiequal_to@45@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$00@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,Uev::TemplateIndex::ihash,Uev::TemplateIndex::iequal_to>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::clear(void)
0x140045b37  mov     [rbp+57h+hKey], r15
0x140045b3b  lea     rdx, ?s_templateIndexKeyName@TemplateIndex@Uev@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@A; std::wstring Uev::TemplateIndex::s_templateIndexKeyName
0x140045b42  cmp     cs:qword_1400D17E8, 7
0x140045b4a  cmova   rdx, cs:?s_templateIndexKeyName@TemplateIndex@Uev@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@A; lpSubKey
0x140045b52  lea     rax, [rbp+57h+hKey]
0x140045b56  mov     [rsp+0F0h+phkResult], rax; phkResult
0x140045b5b  mov     r9d, 109h; samDesired
0x140045b61  xor     r8d, r8d; ulOptions
0x140045b64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140045b6b  call    cs:__imp_RegOpenKeyExW
0x140045b71  test    eax, eax
0x140045b73  jnz     loc_140045CA5
0x140045b79  mov     r8, [rbp+57h+hKey]
0x140045b7d  test    r8, r8
0x140045b80  jz      loc_140045D51
0x140045b86  lea     rdx, [rbp+57h+var_B8]
0x140045b8a  call    ?GetSubKeyNames@TemplateIndex@Uev@@AEBA?AV?$unique_ptr@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@U?$default_delete@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@2@@std@@PEAUHKEY__@@@Z; Uev::TemplateIndex::GetSubKeyNames(HKEY__ *)
0x140045b8f  nop
0x140045b90  mov     r14, [rbp+57h+var_B8]
0x140045b94  test    r14, r14
0x140045b97  jz      loc_140045C89
0x140045b9d  mov     rbx, [r14]
0x140045ba0  cmp     rbx, [r14+8]
0x140045ba4  jz      loc_140045C89
0x140045baa  mov     rcx, [rbp+57h+hKey]; hKey
0x140045bae  test    rcx, rcx
0x140045bb1  jz      loc_140045CDB
0x140045bb7  xor     esi, esi
0x140045bb9  mov     [rbp+57h+var_B0], rsi
0x140045bbd  or      r15d, 1
0x140045bc1  mov     [rbp+57h+var_C0], r15d
0x140045bc5  mov     [rbp+57h+var_38], rsi
0x140045bc9  cmp     qword ptr [rbx+18h], 7
0x140045bce  jbe     short loc_140045BD5
0x140045bd0  mov     rdx, [rbx]
0x140045bd3  jmp     short loc_140045BD8
0x140045bd5  mov     rdx, rbx; lpSubKey
0x140045bd8  lea     rax, [rbp+57h+var_38]
0x140045bdc  mov     [rsp+0F0h+phkResult], rax; phkResult
0x140045be1  mov     r9d, 109h; samDesired
0x140045be7  xor     r8d, r8d; ulOptions
0x140045bea  call    cs:__imp_RegOpenKeyExW
0x140045bf0  xor     edi, edi
0x140045bf2  test    eax, eax
0x140045bf4  jnz     short loc_140045C37
0x140045bf6  mov     r8, [rbp+57h+var_38]
0x140045bfa  test    r8, r8
0x140045bfd  jz      loc_140045D80
0x140045c03  lea     rdx, [rbp+57h+Block]
0x140045c07  call    ?GetSubKeyNames@TemplateIndex@Uev@@AEBA?AV?$unique_ptr@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@U?$default_delete@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@2@@std@@PEAUHKEY__@@@Z; Uev::TemplateIndex::GetSubKeyNames(HKEY__ *)
0x140045c0c  mov     rsi, [rax]
0x140045c0f  mov     [rax], rdi
0x140045c12  mov     [rbp+57h+var_B0], rsi
0x140045c16  mov     rdi, [rbp+57h+Block]
0x140045c1a  test    rdi, rdi
0x140045c1d  jz      short loc_140045C34
0x140045c1f  mov     rcx, rdi
0x140045c22  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x140045c27  mov     edx, 18h
0x140045c2c  mov     rcx, rdi; Block
0x140045c2f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140045c34  mov     rdi, rsi
0x140045c37  lea     rcx, [rbp+57h+var_38]
0x140045c3b  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x140045c40  test    rdi, rdi
0x140045c43  jz      short loc_140045C62
0x140045c45  mov     rdi, [rsi]
0x140045c48  cmp     rdi, [rsi+8]
0x140045c4c  jz      short loc_140045C62
0x140045c4e  mov     r8, rdi
0x140045c51  mov     rdx, rbx
0x140045c54  mov     rcx, r13
0x140045c57  call    ?AddTemplateID@TemplateIndex@Uev@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; Uev::TemplateIndex::AddTemplateID(std::wstring const &,std::wstring const &)
0x140045c5c  add     rdi, 20h ; ' '
0x140045c60  jmp     short loc_140045C48
0x140045c62  and     r15d, 0FFFFFFFEh
0x140045c66  test    rsi, rsi
0x140045c69  jz      short loc_140045C80
0x140045c6b  mov     rcx, rsi
0x140045c6e  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x140045c73  mov     edx, 18h
0x140045c78  mov     rcx, rsi; Block
0x140045c7b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140045c80  add     rbx, 20h ; ' '
0x140045c84  jmp     loc_140045BA0
0x140045c89  test    r14, r14
0x140045c8c  jz      short loc_140045CAA
0x140045c8e  mov     rcx, r14
0x140045c91  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x140045c96  mov     edx, 18h
0x140045c9b  mov     rcx, r14; Block
0x140045c9e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140045ca3  jmp     short loc_140045CAA
0x140045ca5  cmp     eax, 2
0x140045ca8  jnz     short loc_140045D0A
0x140045caa  lea     rcx, [rbp+57h+hKey]
0x140045cae  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x140045cb3  mov     rcx, [rbp+57h+var_30]
0x140045cb7  xor     rcx, rsp; StackCookie
0x140045cba  call    __security_check_cookie
0x140045cbf  lea     r11, [rsp+0F0h+var_20]
0x140045cc7  mov     rbx, [r11+38h]
0x140045ccb  mov     rsi, [r11+40h]
0x140045ccf  mov     rsp, r11
0x140045cd2  pop     r15
0x140045cd4  pop     r14
0x140045cd6  pop     r13
0x140045cd8  pop     rdi
0x140045cd9  pop     rbp
0x140045cda  retn
0x140045cdb  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x140045ce2  lea     rcx, [rbp+57h+var_A0]
0x140045ce6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140045ceb  nop
0x140045cec  lea     rdx, [rbp+57h+var_A0]
0x140045cf0  lea     rcx, [rbp+57h+pExceptionObject]
0x140045cf4  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x140045cf9  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x140045d00  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140045d04  call    _CxxThrowException_0
0x140045d0a  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 2
0x140045d11  jz      short loc_140045D22
0x140045d13  mov     r8d, eax
0x140045d16  lea     rdx, TemplateMsg_UnableToOpenIndexRegistryKey
0x140045d1d  call    McTemplateU0q_EventWriteTransfer
0x140045d22  lea     rdx, aUnableToOpenIn; "Unable to open index registry key."
0x140045d29  lea     rcx, [rbp+57h+var_A0]
0x140045d2d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140045d32  nop
0x140045d33  lea     rdx, [rbp+57h+var_A0]
0x140045d37  lea     rcx, [rbp+57h+pExceptionObject]
0x140045d3b  call    ??0TemplateIndexException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::TemplateIndexException::TemplateIndexException(std::wstring const &)
0x140045d40  lea     rdx, _TI3?AVTemplateIndexException@Uev@@; pThrowInfo
0x140045d47  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140045d4b  call    _CxxThrowException_0
0x140045d51  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x140045d58  lea     rcx, [rbp+57h+var_A0]
0x140045d5c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140045d61  nop
0x140045d62  lea     rdx, [rbp+57h+var_A0]
0x140045d66  lea     rcx, [rbp+57h+pExceptionObject]
0x140045d6a  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x140045d6f  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x140045d76  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140045d7a  call    _CxxThrowException_0
0x140045d80  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x140045d87  lea     rcx, [rbp+57h+var_A0]
0x140045d8b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140045d90  nop
0x140045d91  lea     rdx, [rbp+57h+var_A0]
0x140045d95  lea     rcx, [rbp+57h+pExceptionObject]
0x140045d99  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x140045d9e  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x140045da5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140045da9  call    _CxxThrowException_0
```
