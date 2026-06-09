# ConfigValue<ConfigValueValueList>::_GetFromRegistry(HKEY__ *,ConfigValueValueList *,int *)

- ea: `0x18003c2dc`
- end: `0x18003c7d2`
- name: `?_GetFromRegistry@?$ConfigValue@VConfigValueValueList@@@@IEAAJPEAUHKEY__@@PEAVConfigValueValueList@@PEAH@Z`
- size: `1270`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003b4f8`

## callees

- `0x180005660`
- `0x1800056a0`
- `0x1800056ac`
- `0x1800091a8`
- `0x18001db10`
- `0x18002c580`
- `0x18003c2dc`
- `0x18004b39c`
- `0x18004b608`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003c4e6`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003c4e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003c3c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003c3c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c334`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c334`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c36a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c483`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c66a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c7c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c36a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c483`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c66a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c7c5`

## string_xrefs

- `0x18003c351`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003c417`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003c45b`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003c698`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003c6d7`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003c6fd`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003c71d`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003c74b`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003c79e`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`

## pseudocode

```c
__int64 __fastcall ConfigValue<ConfigValueValueList>::_GetFromRegistry(LPCWSTR *a1, HKEY a2, __int64 a3, _DWORD *a4)
{
  HKEY *phkResult; // rax
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  LSTATUS v13; // eax
  void *v14; // rbx
  BYTE *v15; // rdi
  __int64 v16; // r12
  DWORD v17; // r14d
  LSTATUS v18; // eax
  unsigned int v19; // esi
  __int64 v20; // rax
  BYTE *v21; // rcx
  _QWORD *v22; // rax
  _QWORD *v23; // r15
  struct ATL::CAtlModule *v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // r9
  __int64 v29; // rdx
  _QWORD *v30; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v31[8]; // [rsp+68h] [rbp-21h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-19h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp-15h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-11h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+80h] [rbp-9h] BYREF
  DWORD cbMaxValueLen; // [rsp+84h] [rbp-5h] BYREF
  DWORD cValues; // [rsp+88h] [rbp-1h] BYREF
  DWORD Type; // [rsp+8Ch] [rbp+3h] BYREF

  *a4 = 0;
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  v9 = RegOpenKeyExW(a2, *a1, 0, 1u, phkResult);
  v10 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    v11 = 447;
LABEL_5:
    Log_HREvent_7(v10, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", v11);
    if ( hKey )
      RegCloseKey(hKey);
    return v10;
  }
  cbMaxValueNameLen = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  v13 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v10 = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
    v11 = 456;
    goto LABEL_5;
  }
  cchValueName = cbMaxValueNameLen + 1;
  v14 = operator new[](saturated_mul(cbMaxValueNameLen + 1, 2u));
  if ( !v14 )
  {
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 460);
LABEL_17:
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942414LL;
  }
  cbData = cbMaxValueLen;
  v15 = (BYTE *)operator new[](saturated_mul((unsigned __int64)cbMaxValueLen >> 1, 2u));
  if ( !v15 )
  {
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 465);
LABEL_16:
    operator delete(v14);
    goto LABEL_17;
  }
  v16 = a3 + 8;
  utl::list<ATL::CComPtr<RegistryValue>,utl::allocator<ATL::CComPtr<RegistryValue>>>::clear(v16);
  v17 = 0;
  if ( cValues )
  {
    while ( 1 )
    {
      cchValueName = cbMaxValueNameLen + 1;
      cbData = cbMaxValueLen;
      Type = 0;
      v18 = RegEnumValueW(hKey, v17, (LPWSTR)v14, &cchValueName, 0, &Type, v15, &cbData);
      v19 = v18;
      if ( v18 )
        break;
      v20 = cbData;
      if ( cbData > 0x7FFFFFFFuLL )
      {
        v19 = -2147024809;
LABEL_53:
        v28 = 483;
        v29 = 1;
        goto LABEL_58;
      }
      v21 = v15;
      v19 = 0;
      if ( cbData )
      {
        while ( *(_WORD *)v21 )
        {
          v21 += 2;
          if ( !--v20 )
            goto LABEL_26;
        }
      }
      else
      {
LABEL_26:
        v19 = -2147024809;
      }
      if ( (v19 & 0x80000000) != 0 )
        goto LABEL_53;
      if ( Type != 1 )
      {
        v28 = 485;
        v19 = -2147024846;
        goto LABEL_57;
      }
      v22 = operator new(0x58u);
      v23 = v22;
      if ( !v22 )
      {
        Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1604);
LABEL_49:
        Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1671);
LABEL_50:
        Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 487);
        operator delete(v15);
        goto LABEL_16;
      }
      memset_0(v22, 0, 0x58u);
      v23[3] = v23 + 5;
      v23[4] = v23 + 5;
      v23[7] = v23 + 9;
      v23[8] = v23 + 9;
      v24 = ATL::_pAtlModule;
      *v23 = &ATL::CComObject<RegistryValue>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v24 + 8LL))(v24);
      (*(void (__fastcall **)(_QWORD *))(*v23 + 8LL))(v23);
      (*(void (__fastcall **)(_QWORD *))(*v23 + 8LL))(v23);
      (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
      v25 = -1;
      do
        ++v25;
      while ( *((_WORD *)v14 + v25) );
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(v23 + 3) )
      {
        v27 = 1606;
        goto LABEL_47;
      }
      v26 = -1;
      do
        ++v26;
      while ( *(_WORD *)&v15[2 * v26] );
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(v23 + 7) )
      {
        v27 = 1607;
LABEL_47:
        Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", v27);
        (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
        goto LABEL_49;
      }
      v30 = v23;
      if ( !*(_QWORD *)utl::list<ATL::CComPtr<RegistryValue>,utl::allocator<ATL::CComPtr<RegistryValue>>>::insert(
                         v16,
                         v31,
                         v16,
                         &v30) )
      {
        Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1672);
        if ( v30 )
          (*(void (**)(void))(*v30 + 16LL))();
        goto LABEL_50;
      }
      if ( v30 )
        (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
      if ( ++v17 >= cValues )
        goto LABEL_40;
    }
    if ( v18 > 0 )
      v19 = (unsigned __int16)v18 | 0x80070000;
    v28 = 479;
LABEL_57:
    v29 = 0;
LABEL_58:
    Log_HREvent_7(v19, v29, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", v28);
    operator delete(v15);
    operator delete(v14);
    if ( hKey )
      RegCloseKey(hKey);
    return v19;
  }
  else
  {
LABEL_40:
    *a4 = 1;
    operator delete(v15);
    operator delete(v14);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
}

```

## disassembly

```asm
0x18003c2dc  push    rbp
0x18003c2de  push    rbx
0x18003c2df  push    rsi
0x18003c2e0  push    rdi
0x18003c2e1  push    r12
0x18003c2e3  push    r13
0x18003c2e5  push    r14
0x18003c2e7  push    r15
0x18003c2e9  lea     rbp, [rsp-1Fh]
0x18003c2ee  sub     rsp, 0A8h
0x18003c2f5  mov     rax, cs:__security_cookie
0x18003c2fc  xor     rax, rsp
0x18003c2ff  mov     [rbp+57h+var_50], rax
0x18003c303  mov     rbx, rcx
0x18003c306  xor     r15d, r15d
0x18003c309  lea     rcx, [rbp+57h+hKey]
0x18003c30d  mov     [r9], r15d
0x18003c310  mov     [rbp+57h+hKey], r15
0x18003c314  mov     r13, r9
0x18003c317  mov     r12, r8
0x18003c31a  mov     rdi, rdx
0x18003c31d  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18003c322  mov     rdx, [rbx]; lpSubKey
0x18003c325  lea     r9d, [r15+1]; samDesired
0x18003c329  xor     r8d, r8d; ulOptions
0x18003c32c  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18003c331  mov     rcx, rdi; hKey
0x18003c334  call    cs:__imp_RegOpenKeyExW
0x18003c33a  mov     ebx, eax
0x18003c33c  test    eax, eax
0x18003c33e  jz      short loc_18003C377
0x18003c340  jle     short loc_18003C34B
0x18003c342  movzx   ebx, ax
0x18003c345  or      ebx, 80070000h
0x18003c34b  mov     r9d, 1BFh
0x18003c351  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003c358  xor     edx, edx
0x18003c35a  mov     ecx, ebx
0x18003c35c  call    Log_HREvent_7
0x18003c361  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c365  test    rcx, rcx
0x18003c368  jz      short loc_18003C370
0x18003c36a  call    cs:__imp_RegCloseKey
0x18003c370  mov     eax, ebx
0x18003c372  jmp     loc_18003C672
0x18003c377  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c37b  lea     rax, [rbp+57h+cbMaxValueLen]
0x18003c37f  mov     [rsp+0E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18003c384  xor     r9d, r9d; lpReserved
0x18003c387  mov     [rsp+0E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18003c38c  xor     r8d, r8d; lpcchClass
0x18003c38f  mov     [rsp+0E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18003c394  xor     edx, edx; lpClass
0x18003c396  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18003c39a  mov     [rbp+57h+cbMaxValueNameLen], r15d
0x18003c39e  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18003c3a3  lea     rax, [rbp+57h+cValues]
0x18003c3a7  mov     [rsp+0E0h+lpcValues], rax; lpcValues
0x18003c3ac  mov     [rsp+0E0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18003c3b1  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18003c3b6  mov     [rsp+0E0h+phkResult], r15; lpcSubKeys
0x18003c3bb  mov     [rbp+57h+cValues], r15d
0x18003c3bf  mov     [rbp+57h+cbMaxValueLen], r15d
0x18003c3c3  call    cs:__imp_RegQueryInfoKeyW
0x18003c3c9  mov     ebx, eax
0x18003c3cb  test    eax, eax
0x18003c3cd  jz      short loc_18003C3E5
0x18003c3cf  jle     short loc_18003C3DA
0x18003c3d1  movzx   ebx, ax
0x18003c3d4  or      ebx, 80070000h
0x18003c3da  mov     r9d, 1C8h
0x18003c3e0  jmp     loc_18003C351
0x18003c3e5  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18003c3e8  mov     esi, 2
0x18003c3ed  inc     eax
0x18003c3ef  mov     ecx, eax
0x18003c3f1  mov     [rbp+57h+cchValueName], eax
0x18003c3f4  mov     eax, esi
0x18003c3f6  mul     rcx
0x18003c3f9  lea     rdi, [rsi-3]
0x18003c3fd  cmovb   rax, rdi
0x18003c401  mov     rcx, rax; unsigned __int64
0x18003c404  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c409  mov     rbx, rax
0x18003c40c  test    rax, rax
0x18003c40f  jnz     short loc_18003C430
0x18003c411  mov     r14d, 8007000Eh
0x18003c417  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003c41e  mov     ecx, r14d
0x18003c421  mov     r9d, 1CCh
0x18003c427  xor     edx, edx
0x18003c429  call    Log_HREvent_7
0x18003c42e  jmp     short loc_18003C47A
0x18003c430  mov     eax, [rbp+57h+cbMaxValueLen]
0x18003c433  mov     ecx, eax
0x18003c435  mov     [rbp+57h+cbData], eax
0x18003c438  shr     rcx, 1
0x18003c43b  mov     rax, rsi
0x18003c43e  mul     rcx
0x18003c441  cmovb   rax, rdi
0x18003c445  mov     rcx, rax; unsigned __int64
0x18003c448  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c44d  mov     rdi, rax
0x18003c450  test    rax, rax
0x18003c453  jnz     short loc_18003C491
0x18003c455  mov     r14d, 8007000Eh
0x18003c45b  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003c462  mov     ecx, r14d
0x18003c465  mov     r9d, 1D1h
0x18003c46b  xor     edx, edx
0x18003c46d  call    Log_HREvent_7
0x18003c472  mov     rcx, rbx; Block
0x18003c475  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003c47a  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c47e  test    rcx, rcx
0x18003c481  jz      short loc_18003C489
0x18003c483  call    cs:__imp_RegCloseKey
0x18003c489  mov     eax, r14d
0x18003c48c  jmp     loc_18003C672
0x18003c491  add     r12, 8
0x18003c495  mov     rcx, r12
0x18003c498  call    ?clear@?$list@V?$CComPtr@VRegistryValue@@@ATL@@V?$allocator@V?$CComPtr@VRegistryValue@@@ATL@@@utl@@@utl@@QEAAXXZ; utl::list<ATL::CComPtr<RegistryValue>,utl::allocator<ATL::CComPtr<RegistryValue>>>::clear(void)
0x18003c49d  mov     r14d, r15d
0x18003c4a0  cmp     [rbp+57h+cValues], r15d
0x18003c4a4  jbe     loc_18003C649
0x18003c4aa  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18003c4ad  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18003c4b1  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c4b5  inc     eax
0x18003c4b7  mov     [rbp+57h+cchValueName], eax
0x18003c4ba  mov     r8, rbx; lpValueName
0x18003c4bd  mov     eax, [rbp+57h+cbMaxValueLen]
0x18003c4c0  mov     edx, r14d; dwIndex
0x18003c4c3  mov     [rbp+57h+cbData], eax
0x18003c4c6  lea     rax, [rbp+57h+cbData]
0x18003c4ca  mov     [rsp+0E0h+lpcValues], rax; lpcbData
0x18003c4cf  lea     rax, [rbp+57h+Type]
0x18003c4d3  mov     [rsp+0E0h+lpcbMaxClassLen], rdi; lpData
0x18003c4d8  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpType
0x18003c4dd  mov     [rsp+0E0h+phkResult], r15; lpReserved
0x18003c4e2  mov     [rbp+57h+Type], r15d
0x18003c4e6  call    cs:__imp_RegEnumValueW
0x18003c4ec  mov     esi, eax
0x18003c4ee  test    eax, eax
0x18003c4f0  jnz     loc_18003C78B
0x18003c4f6  mov     eax, [rbp+57h+cbData]
0x18003c4f9  cmp     rax, 7FFFFFFFh
0x18003c4ff  ja      loc_18003C779
0x18003c505  mov     rcx, rdi
0x18003c508  mov     esi, r15d
0x18003c50b  test    rax, rax
0x18003c50e  jz      short loc_18003C520
0x18003c510  cmp     [rcx], r15w
0x18003c514  jz      short loc_18003C525
0x18003c516  add     rcx, 2
0x18003c51a  sub     rax, 1
0x18003c51e  jnz     short loc_18003C510
0x18003c520  mov     esi, 80070057h
0x18003c525  test    esi, esi
0x18003c527  js      loc_18003C77E
0x18003c52d  cmp     [rbp+57h+Type], 1
0x18003c531  jnz     loc_18003C76C
0x18003c537  mov     ecx, 58h ; 'X'; Size
0x18003c53c  mov     rsi, r15
0x18003c53f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c544  mov     r15, rax
0x18003c547  test    rax, rax
0x18003c54a  jz      loc_18003C6F7
0x18003c550  xor     edx, edx; Val
0x18003c552  mov     rcx, rax; void *
0x18003c555  lea     r8d, [rdx+58h]; Size
0x18003c559  call    memset_0
0x18003c55e  lea     rcx, [r15+28h]
0x18003c562  mov     [r15+18h], rcx
0x18003c566  lea     rax, ??_7?$CComObject@VRegistryValue@@@ATL@@6B@; const ATL::CComObject<RegistryValue>::`vftable'
0x18003c56d  mov     [r15+20h], rcx
0x18003c571  lea     rcx, [r15+48h]
0x18003c575  mov     [r15+38h], rcx
0x18003c579  mov     [r15+40h], rcx
0x18003c57d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18003c584  mov     [r15], rax
0x18003c587  mov     rax, [rcx]
0x18003c58a  mov     rax, [rax+8]
0x18003c58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c593  mov     rax, [r15]
0x18003c596  mov     rcx, r15
0x18003c599  mov     rax, [rax+8]
0x18003c59d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5a2  mov     rax, [r15]
0x18003c5a5  mov     rcx, r15
0x18003c5a8  mov     rax, [rax+8]
0x18003c5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5b1  mov     rax, [r15]
0x18003c5b4  mov     rcx, r15
0x18003c5b7  mov     rax, [rax+10h]
0x18003c5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5c0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003c5c4  lea     rcx, [r15+18h]
0x18003c5c8  xor     eax, eax
0x18003c5ca  inc     r8
0x18003c5cd  cmp     [rbx+r8*2], ax
0x18003c5d2  jnz     short loc_18003C5CA
0x18003c5d4  mov     rdx, rbx
0x18003c5d7  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003c5dc  xor     edx, edx
0x18003c5de  test    al, al
0x18003c5e0  jz      loc_18003C6CB
0x18003c5e6  lea     rcx, [r15+38h]
0x18003c5ea  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003c5ee  inc     r8
0x18003c5f1  cmp     [rdi+r8*2], dx
0x18003c5f6  jnz     short loc_18003C5EE
0x18003c5f8  mov     rdx, rdi
0x18003c5fb  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003c600  test    al, al
0x18003c602  jz      loc_18003C6C1
0x18003c608  lea     r9, [rbp+57h+var_80]
0x18003c60c  mov     [rbp+57h+var_80], r15
0x18003c610  mov     r8, r12
0x18003c613  lea     rdx, [rbp+57h+var_78]
0x18003c617  mov     rcx, r12
0x18003c61a  call    ?insert@?$list@V?$CComPtr@VRegistryValue@@@ATL@@V?$allocator@V?$CComPtr@VRegistryValue@@@ATL@@@utl@@@utl@@QEAA?AV?$_DlistIt@U?$_DlistNode@V?$CComPtr@VRegistryValue@@@ATL@@@utl@@V?$CComPtr@VRegistryValue@@@ATL@@@2@V?$_DlistConstIt@U?$_DlistNode@V?$CComPtr@VRegistryValue@@@ATL@@@utl@@V?$CComPtr@VRegistryValue@@@ATL@@@2@AEBV?$CComPtr@VRegistryValue@@@ATL@@@Z; utl::list<ATL::CComPtr<RegistryValue>,utl::allocator<ATL::CComPtr<RegistryValue>>>::insert(utl::_DlistConstIt<utl::_DlistNode<ATL::CComPtr<RegistryValue>>,ATL::CComPtr<RegistryValue>>,ATL::CComPtr<RegistryValue> const &)
0x18003c61f  xor     r15d, r15d
0x18003c622  cmp     [rax], r15
0x18003c625  jz      short loc_18003C692
0x18003c627  mov     rcx, [rbp+57h+var_80]
0x18003c62b  test    rcx, rcx
0x18003c62e  jz      short loc_18003C63C
0x18003c630  mov     rax, [rcx]
0x18003c633  mov     rax, [rax+10h]
0x18003c637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c63c  inc     r14d
0x18003c63f  cmp     r14d, [rbp+57h+cValues]
0x18003c643  jb      loc_18003C4AA
0x18003c649  mov     rcx, rdi; Block
0x18003c64c  mov     dword ptr [r13+0], 1
0x18003c654  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003c659  mov     rcx, rbx; Block
0x18003c65c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003c661  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c665  test    rcx, rcx
0x18003c668  jz      short loc_18003C670
0x18003c66a  call    cs:__imp_RegCloseKey
0x18003c670  xor     eax, eax
0x18003c672  mov     rcx, [rbp+57h+var_50]
0x18003c676  xor     rcx, rsp; StackCookie
0x18003c679  call    __security_check_cookie
0x18003c67e  add     rsp, 0A8h
0x18003c685  pop     r15
0x18003c687  pop     r14
0x18003c689  pop     r13
0x18003c68b  pop     r12
0x18003c68d  pop     rdi
0x18003c68e  pop     rsi
0x18003c68f  pop     rbx
0x18003c690  pop     rbp
0x18003c691  retn
0x18003c692  mov     r14d, 8007000Eh
0x18003c698  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003c69f  mov     ecx, r14d
0x18003c6a2  mov     r9d, 688h
0x18003c6a8  xor     edx, edx
0x18003c6aa  call    Log_HREvent_7
0x18003c6af  mov     rcx, [rbp+57h+var_80]
0x18003c6b3  test    rcx, rcx
0x18003c6b6  jz      loc_18003C745
0x18003c6bc  mov     rax, [rcx]
0x18003c6bf  jmp     short loc_18003C73C
0x18003c6c1  mov     r9d, 647h
0x18003c6c7  xor     edx, edx
0x18003c6c9  jmp     short loc_18003C6D1
0x18003c6cb  mov     r9d, 646h
0x18003c6d1  mov     r14d, 8007000Eh
0x18003c6d7  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003c6de  mov     ecx, r14d
0x18003c6e1  call    Log_HREvent_7
0x18003c6e6  mov     rax, [r15]
0x18003c6e9  mov     rcx, r15
0x18003c6ec  mov     rax, [rax+10h]
0x18003c6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6f5  jmp     short loc_18003C717
0x18003c6f7  mov     r14d, 8007000Eh
0x18003c6fd  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003c704  mov     ecx, r14d
0x18003c707  mov     r9d, 644h
0x18003c70d  mov     edx, 1
0x18003c712  call    Log_HREvent_7
0x18003c717  mov     r9d, 687h
0x18003c71d  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003c724  mov     edx, 1
0x18003c729  mov     ecx, r14d
0x18003c72c  call    Log_HREvent_7
0x18003c731  test    rsi, rsi
0x18003c734  jz      short loc_18003C745
0x18003c736  mov     rax, [rsi]
0x18003c739  mov     rcx, rsi
0x18003c73c  mov     rax, [rax+10h]
0x18003c740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c745  mov     r9d, 1E7h
0x18003c74b  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
  ... truncated ...
```
