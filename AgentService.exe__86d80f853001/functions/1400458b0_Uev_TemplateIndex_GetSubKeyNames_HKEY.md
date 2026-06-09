# Uev::TemplateIndex::GetSubKeyNames(HKEY__ *)

- ea: `0x1400458b0`
- end: `0x140045aef`
- name: `?GetSubKeyNames@TemplateIndex@Uev@@AEBA?AV?$unique_ptr@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@U?$default_delete@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@2@@std@@PEAUHKEY__@@@Z`
- size: `575`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140045af8`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x140003f88`
- `0x140003fcc`
- `0x140004ab4`
- `0x14000ba60`
- `0x14000c2b8`
- `0x14000d1d8`
- `0x140019190`
- `0x140038a64`
- `0x14004550c`
- `0x1400458b0`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x140045945`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140045945`
- `ADVAPI32!RegEnumKeyExW` at `0x1400459ac`
- `ADVAPI32!RegEnumKeyExW` at `0x1400459ac`

## string_xrefs

- `0x140045a79`: `Unable to query template index.`
- `0x140045ac0`: `Unable to enumerate template index subkeys.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Uev::TemplateIndex::GetSubKeyNames(__int64 a1, _QWORD *a2, HKEY a3)
{
  _QWORD *v5; // rbx
  unsigned int v6; // eax
  __int64 v7; // rcx
  DWORD v8; // r15d
  WCHAR *v9; // rsi
  DWORD i; // edi
  unsigned int v11; // eax
  __int64 v12; // rcx
  _OWORD *v13; // rdx
  __int128 v15; // [rsp+60h] [rbp-79h] BYREF
  __int128 v16; // [rsp+70h] [rbp-69h]
  _QWORD *v17; // [rsp+88h] [rbp-51h]
  WCHAR *v18; // [rsp+90h] [rbp-49h]
  _QWORD pExceptionObject[8]; // [rsp+A0h] [rbp-39h] BYREF
  DWORD cSubKeys; // [rsp+E0h] [rbp+7h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+E4h] [rbp+Bh] BYREF
  DWORD cchName[2]; // [rsp+E8h] [rbp+Fh] BYREF

  *(_QWORD *)cchName = a2;
  v5 = operator new(0x18u);
  *v5 = 0;
  v5[1] = 0;
  v5[2] = 0;
  v17 = v5;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v6 = RegQueryInfoKeyW(a3, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v6 )
  {
    if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 2) != 0 )
      McTemplateU0q_EventWriteTransfer(v7, TemplateMsg_UnableToQueryTemplateIndexKeyInformation, v6);
    std::wstring::wstring(&v15, L"Unable to query template index.");
    Uev::TemplateIndexException::TemplateIndexException(pExceptionObject, (__int64)&v15);
    throw (Uev::TemplateIndexException *)pExceptionObject;
  }
  v8 = cbMaxSubKeyLen + 1;
  v9 = (WCHAR *)operator new[](saturated_mul(cbMaxSubKeyLen + 1, 2u));
  v18 = v9;
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName[0] = v8;
    v11 = RegEnumKeyExW(a3, i, v9, cchName, 0, 0, 0, 0);
    if ( v11 )
    {
      if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v12, TemplateMsg_UnableToEnumerateTemplateIndexSubKey, v11);
      std::wstring::wstring(&v15, L"Unable to enumerate template index subkeys.");
      Uev::TemplateIndexException::TemplateIndexException(pExceptionObject, (__int64)&v15);
      throw (Uev::TemplateIndexException *)pExceptionObject;
    }
    v15 = 0;
    v16 = 0u;
    std::wstring::_Construct<1,wchar_t *>(&v15, v9, cchName[0]);
    v13 = (_OWORD *)v5[1];
    if ( v13 == (_OWORD *)v5[2] )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v5, v13, &v15);
    }
    else
    {
      *v13 = v15;
      v13[1] = v16;
      *(_QWORD *)&v16 = 0;
      *((_QWORD *)&v16 + 1) = 7;
      LOWORD(v15) = 0;
      v5[1] += 32LL;
    }
    std::wstring::_Tidy_deallocate(&v15);
  }
  operator delete(v9);
  *a2 = v5;
  return a2;
}

```

## disassembly

```asm
0x1400458b0  mov     [rsp-8+arg_0], rbx
0x1400458b5  push    rbp
0x1400458b6  push    rsi
0x1400458b7  push    rdi
0x1400458b8  push    r12
0x1400458ba  push    r13
0x1400458bc  push    r14
0x1400458be  push    r15
0x1400458c0  lea     rbp, [rsp-27h]
0x1400458c5  sub     rsp, 100h
0x1400458cc  mov     rax, cs:__security_cookie
0x1400458d3  xor     rax, rsp
0x1400458d6  mov     [rbp+57h+var_40], rax
0x1400458da  mov     r12, r8
0x1400458dd  mov     r14, rdx
0x1400458e0  mov     qword ptr [rbp+57h+cchName], rdx
0x1400458e4  xor     r13d, r13d
0x1400458e7  lea     ecx, [r13+18h]; Size
0x1400458eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400458f0  mov     rbx, rax
0x1400458f3  mov     [rax], r13
0x1400458f6  mov     [rax+8], r13
0x1400458fa  mov     [rax+10h], r13
0x1400458fe  mov     [rbp+57h+var_A8], rax
0x140045902  mov     [rbp+57h+cSubKeys], r13d
0x140045906  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x14004590a  mov     [rsp+130h+lpftLastWriteTime], r13; lpftLastWriteTime
0x14004590f  mov     [rsp+130h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x140045914  mov     [rsp+130h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x140045919  mov     [rsp+130h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x14004591e  mov     [rsp+130h+lpcValues], r13; lpcValues
0x140045923  mov     [rsp+130h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x140045928  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x14004592c  mov     [rsp+130h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140045931  lea     rax, [rbp+57h+cSubKeys]
0x140045935  mov     [rsp+130h+lpcSubKeys], rax; lpcSubKeys
0x14004593a  xor     r9d, r9d; lpReserved
0x14004593d  xor     r8d, r8d; lpcchClass
0x140045940  xor     edx, edx; lpClass
0x140045942  mov     rcx, r12; hKey
0x140045945  call    cs:__imp_RegQueryInfoKeyW
0x14004594b  test    eax, eax
0x14004594d  jnz     loc_140045A61
0x140045953  mov     r15d, [rbp+57h+cbMaxSubKeyLen]
0x140045957  inc     r15d
0x14004595a  mov     ecx, r15d
0x14004595d  lea     eax, [r13+2]
0x140045961  mul     rcx
0x140045964  lea     rcx, [r13-1]
0x140045968  cmovb   rax, rcx
0x14004596c  mov     rcx, rax; unsigned __int64
0x14004596f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140045974  mov     rsi, rax
0x140045977  mov     [rbp+57h+var_A0], rax
0x14004597b  mov     edi, r13d
0x14004597e  cmp     [rbp+57h+cSubKeys], r13d
0x140045982  jbe     loc_140045A2C
0x140045988  mov     [rbp+57h+cchName], r15d
0x14004598c  mov     [rsp+130h+lpcValues], r13; lpftLastWriteTime
0x140045991  mov     [rsp+130h+lpcbMaxClassLen], r13; lpcchClass
0x140045996  mov     [rsp+130h+lpcbMaxSubKeyLen], r13; lpClass
0x14004599b  mov     [rsp+130h+lpcSubKeys], r13; lpReserved
0x1400459a0  lea     r9, [rbp+57h+cchName]; lpcchName
0x1400459a4  mov     r8, rsi; lpName
0x1400459a7  mov     edx, edi; dwIndex
0x1400459a9  mov     rcx, r12; hKey
0x1400459ac  call    cs:__imp_RegEnumKeyExW
0x1400459b2  test    eax, eax
0x1400459b4  jnz     loc_140045AA8
0x1400459ba  xorps   xmm0, xmm0
0x1400459bd  movups  [rbp+57h+var_D0], xmm0
0x1400459c1  mov     qword ptr [rbp+57h+var_C0], r13
0x1400459c5  mov     qword ptr [rbp+57h+var_C0+8], r13
0x1400459c9  mov     r8d, [rbp+57h+cchName]
0x1400459cd  mov     rdx, rsi
0x1400459d0  lea     rcx, [rbp+57h+var_D0]
0x1400459d4  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1400459d9  nop
0x1400459da  mov     rdx, [rbx+8]
0x1400459de  cmp     rdx, [rbx+10h]
0x1400459e2  jz      short loc_140045A0B
0x1400459e4  movups  xmm0, [rbp+57h+var_D0]
0x1400459e8  movups  xmmword ptr [rdx], xmm0
0x1400459eb  movups  xmm1, [rbp+57h+var_C0]
0x1400459ef  movups  xmmword ptr [rdx+10h], xmm1
0x1400459f3  mov     qword ptr [rbp+57h+var_C0], r13
0x1400459f7  mov     qword ptr [rbp+57h+var_C0+8], 7
0x1400459ff  mov     word ptr [rbp+57h+var_D0], r13w
0x140045a04  add     qword ptr [rbx+8], 20h ; ' '
0x140045a09  jmp     short loc_140045A18
0x140045a0b  lea     r8, [rbp+57h+var_D0]
0x140045a0f  mov     rcx, rbx
0x140045a12  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x140045a17  nop
0x140045a18  lea     rcx, [rbp+57h+var_D0]
0x140045a1c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140045a21  inc     edi
0x140045a23  cmp     edi, [rbp+57h+cSubKeys]
0x140045a26  jb      loc_140045988
0x140045a2c  mov     rcx, rsi; Block
0x140045a2f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140045a34  mov     [r14], rbx
0x140045a37  mov     rax, r14
0x140045a3a  mov     rcx, [rbp+57h+var_40]
0x140045a3e  xor     rcx, rsp; StackCookie
0x140045a41  call    __security_check_cookie
0x140045a46  mov     rbx, [rsp+130h+arg_0]
0x140045a4e  add     rsp, 100h
0x140045a55  pop     r15
0x140045a57  pop     r14
0x140045a59  pop     r13
0x140045a5b  pop     r12
0x140045a5d  pop     rdi
0x140045a5e  pop     rsi
0x140045a5f  pop     rbp
0x140045a60  retn
0x140045a61  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 2
0x140045a68  jz      short loc_140045A79
0x140045a6a  mov     r8d, eax
0x140045a6d  lea     rdx, TemplateMsg_UnableToQueryTemplateIndexKeyInformation
0x140045a74  call    McTemplateU0q_EventWriteTransfer
0x140045a79  lea     rdx, aUnableToQueryT; "Unable to query template index."
0x140045a80  lea     rcx, [rbp+57h+var_D0]
0x140045a84  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140045a89  nop
0x140045a8a  lea     rdx, [rbp+57h+var_D0]
0x140045a8e  lea     rcx, [rbp+57h+pExceptionObject]
0x140045a92  call    ??0TemplateIndexException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::TemplateIndexException::TemplateIndexException(std::wstring const &)
0x140045a97  lea     rdx, _TI3?AVTemplateIndexException@Uev@@; pThrowInfo
0x140045a9e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140045aa2  call    _CxxThrowException_0
0x140045aa8  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 2
0x140045aaf  jz      short loc_140045AC0
0x140045ab1  mov     r8d, eax
0x140045ab4  lea     rdx, TemplateMsg_UnableToEnumerateTemplateIndexSubKey
0x140045abb  call    McTemplateU0q_EventWriteTransfer
0x140045ac0  lea     rdx, aUnableToEnumer; "Unable to enumerate template index subk"...
0x140045ac7  lea     rcx, [rbp+57h+var_D0]
0x140045acb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140045ad0  nop
0x140045ad1  lea     rdx, [rbp+57h+var_D0]
0x140045ad5  lea     rcx, [rbp+57h+pExceptionObject]
0x140045ad9  call    ??0TemplateIndexException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::TemplateIndexException::TemplateIndexException(std::wstring const &)
0x140045ade  lea     rdx, _TI3?AVTemplateIndexException@Uev@@; pThrowInfo
0x140045ae5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140045ae9  call    _CxxThrowException_0
```
