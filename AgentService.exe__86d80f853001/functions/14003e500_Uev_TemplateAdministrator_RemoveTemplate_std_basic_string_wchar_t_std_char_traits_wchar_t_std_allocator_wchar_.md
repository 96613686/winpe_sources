# Uev::TemplateAdministrator::RemoveTemplate(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x14003e500`
- end: `0x14003e7c0`
- name: `?RemoveTemplate@TemplateAdministrator@Uev@@UEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `704`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, registry_config`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x14000ba60`
- `0x14000d1d8`
- `0x140019748`
- `0x140020568`
- `0x1400322b8`
- `0x140032354`
- `0x140034c14`
- `0x140034db4`
- `0x14003a044`
- `0x14003ad50`
- `0x14003b94c`
- `0x14003be24`
- `0x14003c630`
- `0x14003e42c`
- `0x14003e500`
- `0x140045af8`
- `0x140045db8`
- `0x140045ea8`
- `0x14009b010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14003e590`
- `KERNEL32!DeleteFileW` at `0x14003e590`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003e657`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003e713`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003e657`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003e713`

## string_xrefs

- `0x14003e78d`: `Template file could not be deleted`

## pseudocode

```c
__int64 __fastcall Uev::TemplateAdministrator::RemoveTemplate(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // r14
  const WCHAR *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rax
  char v7; // al
  int v8; // edx
  _QWORD *v9; // rbx
  _QWORD *v10; // rdx
  _QWORD *v11; // rcx
  _QWORD *v12; // rdi
  _QWORD *v13; // r15
  _QWORD *v14; // r12
  __int64 v15; // rdi
  _QWORD *v16; // rdx
  _BYTE v18[32]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v21[3]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v22; // [rsp+B0h] [rbp-50h]
  __int128 v23; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+C8h] [rbp-38h]
  LPCWSTR lpFileName[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v26[2]; // [rsp+F0h] [rbp-10h] BYREF
  char v27[16]; // [rsp+100h] [rbp+0h] BYREF
  char v28[48]; // [rsp+110h] [rbp+10h] BYREF

  v2 = a2;
  Uev::TemplateAdministrator::GetPrimaryTemplateIdFromSecondaryId(v21, a2);
  v23 = 0;
  v24 = 0;
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 16LL))(a1, &v23);
  if ( (unsigned __int8)Uev::FindExistingId(v21, &v23) )
  {
    Uev::TemplateAdministrator::GetTemplateFilenameForId(lpFileName, (__int64)v21);
    v4 = (const WCHAR *)lpFileName;
    if ( lpFileName[3] > (LPCWSTR)7 )
      v4 = lpFileName[0];
    if ( !DeleteFileW(v4) )
    {
      std::wstring::wstring(v18, L"Template file could not be deleted");
      Uev::FileIOException::FileIOException(pExceptionObject, v18);
      throw (Uev::FileIOException *)pExceptionObject;
    }
    Uev::TemplateIndex::TemplateIndex((Uev::TemplateIndex *)v26);
    Uev::TemplateIndex::LoadIndex((Uev::TemplateIndex *)v26);
    Uev::TemplateIndex::RemoveTemplateID(v26, v21);
    Uev::TemplateIndex::SaveIndex((Uev::TemplateIndex *)v26);
    v5 = Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance();
    v20 = 0x300000002LL;
    v6 = *(_QWORD *)(v5 + 19920);
    if ( v6 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, __int64 *))((v6 & 0xFFFFFFFFFFFFFFFEuLL) + 8))(
             v5 + 19928,
             3,
             v21,
             &v20);
      v8 = v20;
      if ( v7 )
        v8 = 0;
      LODWORD(v20) = v8;
    }
    if ( *(_BYTE *)(a1 + 72) )
    {
      v9 = *(_QWORD **)(a1 + 24);
      while ( v9 != *(_QWORD **)(a1 + 32) )
      {
        if ( v9[3] <= 7u )
          v10 = v9;
        else
          v10 = (_QWORD *)*v9;
        v11 = v21;
        if ( v22 > 7 )
          v11 = (_QWORD *)v21[0];
        v12 = v9 + 29;
        if ( (unsigned int)_o__wcsicmp(v11, v10) )
        {
          v9 += 29;
        }
        else
        {
          v13 = v9;
          v14 = *(_QWORD **)(a1 + 32);
          while ( v12 != v14 )
          {
            Uev::TemplateInfo::operator=(v13, v12);
            v13 += 29;
            v12 += 29;
          }
          v15 = *(_QWORD *)(a1 + 32) - 232LL;
          std::vector<Uev::ProcessFileCriteriaDefinition>::_Tidy(v15 + 208);
          std::wstring::_Tidy_deallocate(v15 + 160);
          std::wstring::_Tidy_deallocate(v15 + 120);
          std::wstring::_Tidy_deallocate(v15 + 88);
          std::wstring::_Tidy_deallocate(v15 + 56);
          std::vector<std::wstring>::_Tidy(v15 + 32);
          std::wstring::_Tidy_deallocate(v15);
          *(_QWORD *)(a1 + 32) -= 232LL;
        }
      }
      Uev::TemplateAdministrator::RemoveIDFromCache(a1, v2);
      v16 = v21;
      if ( v22 > 7 )
        v16 = (_QWORD *)v21[0];
      if ( v2[3] > 7u )
        v2 = (_QWORD *)*v2;
      if ( (unsigned int)_o__wcsicmp(v2, v16) )
        Uev::TemplateAdministrator::RemoveIDFromCache(a1, v21);
    }
    v26[0] = &Uev::TemplateIndex::`vftable';
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v28);
    std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(v27);
    std::wstring::_Tidy_deallocate(lpFileName);
  }
  std::vector<std::wstring>::_Tidy(&v23);
  return std::wstring::_Tidy_deallocate(v21);
}

```

## disassembly

```asm
0x14003e500  mov     [rsp-8+arg_10], rbx
0x14003e505  mov     [rsp-8+arg_18], rsi
0x14003e50a  push    rbp
0x14003e50b  push    rdi
0x14003e50c  push    r12
0x14003e50e  push    r14
0x14003e510  push    r15
0x14003e512  lea     rbp, [rsp-50h]
0x14003e517  sub     rsp, 150h
0x14003e51e  mov     rax, cs:__security_cookie
0x14003e525  xor     rax, rsp
0x14003e528  mov     [rbp+70h+var_30], rax
0x14003e52c  mov     r14, rdx
0x14003e52f  mov     rsi, rcx
0x14003e532  lea     rcx, [rbp+70h+var_D8]
0x14003e536  call    ?GetPrimaryTemplateIdFromSecondaryId@TemplateAdministrator@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@@Z; Uev::TemplateAdministrator::GetPrimaryTemplateIdFromSecondaryId(std::wstring const &)
0x14003e53b  nop
0x14003e53c  xorps   xmm0, xmm0
0x14003e53f  movdqu  [rbp+70h+var_B8], xmm0
0x14003e544  mov     [rbp+70h+var_A8], 0
0x14003e54c  mov     rax, [rsi]
0x14003e54f  lea     rdx, [rbp+70h+var_B8]
0x14003e553  mov     rcx, rsi
0x14003e556  mov     rax, [rax+10h]
0x14003e55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e55f  lea     rdx, [rbp+70h+var_B8]
0x14003e563  lea     rcx, [rbp+70h+var_D8]
0x14003e567  call    ?FindExistingId@Uev@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@@Z; Uev::FindExistingId(std::wstring const &,std::vector<std::wstring> const &)
0x14003e56c  test    al, al
0x14003e56e  jz      loc_14003E752
0x14003e574  lea     rdx, [rbp+70h+var_D8]
0x14003e578  lea     rcx, [rbp+70h+lpFileName]; Src
0x14003e57c  call    ?GetTemplateFilenameForId@TemplateAdministrator@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@@Z; Uev::TemplateAdministrator::GetTemplateFilenameForId(std::wstring const &)
0x14003e581  nop
0x14003e582  lea     rcx, [rbp+70h+lpFileName]
0x14003e586  cmp     [rbp+70h+var_88], 7
0x14003e58b  cmova   rcx, [rbp+70h+lpFileName]; lpFileName
0x14003e590  call    cs:__imp_DeleteFileW
0x14003e596  test    eax, eax
0x14003e598  jz      loc_14003E78D
0x14003e59e  lea     rcx, [rbp+70h+var_80]; this
0x14003e5a2  call    ??0TemplateIndex@Uev@@QEAA@XZ; Uev::TemplateIndex::TemplateIndex(void)
0x14003e5a7  nop
0x14003e5a8  lea     rcx, [rbp+70h+var_80]; this
0x14003e5ac  call    ?LoadIndex@TemplateIndex@Uev@@QEAAXXZ; Uev::TemplateIndex::LoadIndex(void)
0x14003e5b1  lea     rdx, [rbp+70h+var_D8]
0x14003e5b5  lea     rcx, [rbp+70h+var_80]
0x14003e5b9  call    ?RemoveTemplateID@TemplateIndex@Uev@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::TemplateIndex::RemoveTemplateID(std::wstring const &)
0x14003e5be  lea     rcx, [rbp+70h+var_80]; this
0x14003e5c2  call    ?SaveIndex@TemplateIndex@Uev@@QEBAXXZ; Uev::TemplateIndex::SaveIndex(void)
0x14003e5c7  mov     [rbp+70h+var_E0], 0
0x14003e5cf  call    ?Instance@?$Singleton@VConfiguration@Uev@@V12@@Uev@@SAPEAVConfiguration@2@XZ; Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance(void)
0x14003e5d4  mov     rcx, rax
0x14003e5d7  mov     dword ptr [rbp+70h+var_E0], 2
0x14003e5de  mov     edx, 3
0x14003e5e3  mov     dword ptr [rbp+70h+var_E0+4], edx
0x14003e5e6  mov     rax, [rax+4DD0h]
0x14003e5ed  test    rax, rax
0x14003e5f0  jz      short loc_14003E61B
0x14003e5f2  and     rax, 0FFFFFFFFFFFFFFFEh
0x14003e5f6  add     rcx, 4DD8h
0x14003e5fd  lea     r9, [rbp+70h+var_E0]
0x14003e601  lea     r8, [rbp+70h+var_D8]
0x14003e605  mov     rax, [rax+8]
0x14003e609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e60e  mov     edx, dword ptr [rbp+70h+var_E0]
0x14003e611  xor     ecx, ecx
0x14003e613  test    al, al
0x14003e615  cmovnz  edx, ecx
0x14003e618  mov     dword ptr [rbp+70h+var_E0], edx
0x14003e61b  cmp     byte ptr [rsi+48h], 0
0x14003e61f  jz      loc_14003E72A
0x14003e625  mov     rbx, [rsi+18h]
0x14003e629  cmp     rbx, [rsi+20h]
0x14003e62d  jz      loc_14003E6ED
0x14003e633  cmp     qword ptr [rbx+18h], 7
0x14003e638  jbe     short loc_14003E63F
0x14003e63a  mov     rdx, [rbx]
0x14003e63d  jmp     short loc_14003E642
0x14003e63f  mov     rdx, rbx
0x14003e642  lea     rcx, [rbp+70h+var_D8]
0x14003e646  cmp     [rbp+70h+var_C0], 7
0x14003e64b  cmova   rcx, [rbp+70h+var_D8]
0x14003e650  lea     rdi, [rbx+0E8h]
0x14003e657  call    cs:__imp__o__wcsicmp
0x14003e65d  test    eax, eax
0x14003e65f  jnz     loc_14003E6E5
0x14003e665  mov     r15, rbx
0x14003e668  mov     r12, [rsi+20h]
0x14003e66c  jmp     short loc_14003E684
0x14003e66e  mov     rdx, rdi
0x14003e671  mov     rcx, r15
0x14003e674  call    ??4TemplateInfo@Uev@@QEAAAEAV01@AEBV01@@Z; Uev::TemplateInfo::operator=(Uev::TemplateInfo const &)
0x14003e679  mov     eax, 0E8h
0x14003e67e  add     r15, rax
0x14003e681  add     rdi, rax
0x14003e684  cmp     rdi, r12
0x14003e687  jnz     short loc_14003E66E
0x14003e689  mov     rdi, [rsi+20h]
0x14003e68d  add     rdi, 0FFFFFFFFFFFFFF18h
0x14003e694  lea     rcx, [rdi+0D0h]
0x14003e69b  call    ?_Tidy@?$vector@VProcessFileCriteriaDefinition@Uev@@V?$allocator@VProcessFileCriteriaDefinition@Uev@@@std@@@std@@AEAAXXZ; std::vector<Uev::ProcessFileCriteriaDefinition>::_Tidy(void)
0x14003e6a0  lea     rcx, [rdi+0A0h]
0x14003e6a7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003e6ac  lea     rcx, [rdi+78h]
0x14003e6b0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003e6b5  lea     rcx, [rdi+58h]
0x14003e6b9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003e6be  lea     rcx, [rdi+38h]
0x14003e6c2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003e6c7  lea     rcx, [rdi+20h]
0x14003e6cb  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x14003e6d0  mov     rcx, rdi
0x14003e6d3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003e6d8  add     qword ptr [rsi+20h], 0FFFFFFFFFFFFFF18h
0x14003e6e0  jmp     loc_14003E629
0x14003e6e5  mov     rbx, rdi
0x14003e6e8  jmp     loc_14003E629
0x14003e6ed  mov     rdx, r14
0x14003e6f0  mov     rcx, rsi
0x14003e6f3  call    ?RemoveIDFromCache@TemplateAdministrator@Uev@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::TemplateAdministrator::RemoveIDFromCache(std::wstring const &)
0x14003e6f8  lea     rdx, [rbp+70h+var_D8]
0x14003e6fc  cmp     [rbp+70h+var_C0], 7
0x14003e701  cmova   rdx, [rbp+70h+var_D8]
0x14003e706  cmp     qword ptr [r14+18h], 7
0x14003e70b  jbe     short loc_14003E710
0x14003e70d  mov     r14, [r14]
0x14003e710  mov     rcx, r14
0x14003e713  call    cs:__imp__o__wcsicmp
0x14003e719  test    eax, eax
0x14003e71b  jz      short loc_14003E72A
0x14003e71d  lea     rdx, [rbp+70h+var_D8]
0x14003e721  mov     rcx, rsi
0x14003e724  call    ?RemoveIDFromCache@TemplateAdministrator@Uev@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::TemplateAdministrator::RemoveIDFromCache(std::wstring const &)
0x14003e729  nop
0x14003e72a  lea     rax, ??_7TemplateIndex@Uev@@6B@; const Uev::TemplateIndex::`vftable'
0x14003e731  mov     [rbp+70h+var_80], rax
0x14003e735  lea     rcx, [rbp+70h+var_60]
0x14003e739  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(void)
0x14003e73e  lea     rcx, [rbp+70h+var_70]
0x14003e742  call    ??1?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(void)
0x14003e747  nop
0x14003e748  lea     rcx, [rbp+70h+lpFileName]
0x14003e74c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003e751  nop
0x14003e752  lea     rcx, [rbp+70h+var_B8]
0x14003e756  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x14003e75b  nop
0x14003e75c  lea     rcx, [rbp+70h+var_D8]
0x14003e760  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003e765  mov     rcx, [rbp+70h+var_30]
0x14003e769  xor     rcx, rsp; StackCookie
0x14003e76c  call    __security_check_cookie
0x14003e771  lea     r11, [rsp+170h+var_20]
0x14003e779  mov     rbx, [r11+40h]
0x14003e77d  mov     rsi, [r11+48h]
0x14003e781  mov     rsp, r11
0x14003e784  pop     r15
0x14003e786  pop     r14
0x14003e788  pop     r12
0x14003e78a  pop     rdi
0x14003e78b  pop     rbp
0x14003e78c  retn
0x14003e78d  lea     rdx, aTemplateFileCo; "Template file could not be deleted"
0x14003e794  lea     rcx, [rsp+170h+var_140]
0x14003e799  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14003e79e  nop
0x14003e79f  lea     rdx, [rsp+170h+var_140]
0x14003e7a4  lea     rcx, [rsp+170h+pExceptionObject]
0x14003e7a9  call    ??0FileIOException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::FileIOException::FileIOException(std::wstring const &)
0x14003e7ae  lea     rdx, _TI3?AVFileIOException@Uev@@; pThrowInfo
0x14003e7b5  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x14003e7ba  call    _CxxThrowException_0
```
