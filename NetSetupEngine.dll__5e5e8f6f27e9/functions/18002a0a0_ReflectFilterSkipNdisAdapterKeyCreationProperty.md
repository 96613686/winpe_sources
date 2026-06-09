# ReflectFilterSkipNdisAdapterKeyCreationProperty

- ea: `0x18002a0a0`
- end: `0x18002a340`
- name: `ReflectFilterSkipNdisAdapterKeyCreationProperty`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18007cd50`

## callees

- `0x180005580`
- `0x180005c94`
- `0x18000a430`
- `0x18000fd70`
- `0x180012108`
- `0x180015f50`
- `0x180017320`
- `0x18001f2c4`
- `0x180025c18`
- `0x180027ac0`
- `0x180027b38`
- `0x1800285fc`
- `0x180028a90`
- `0x180028db4`
- `0x180029d20`
- `0x18002a0a0`
- `0x18002b624`
- `0x18005e1a8`
- `0x180064704`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a1f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a296`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a2e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a1f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a296`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a2e1`

## string_xrefs

- `0x18002a171`: `Services\`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ReflectFilterSkipNdisAdapterKeyCreationProperty(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  HKEY CurrentControlSetRegistryHandle; // rbx
  HKEY v5; // rdi
  const WCHAR *p_Block; // r8
  HKEY v7; // rax
  HKEY v8; // rcx
  bool Boolean; // bl
  __int64 v10; // rdx
  void **v12; // r9
  HKEY hKey[2]; // [rsp+30h] [rbp-A8h] BYREF
  HKEY v14; // [rsp+40h] [rbp-98h] BYREF
  HKEY v15; // [rsp+48h] [rbp-90h] BYREF
  GUID Block; // [rsp+50h] [rbp-88h] BYREF
  int v17; // [rsp+60h] [rbp-78h]
  __int128 v18; // [rsp+64h] [rbp-74h] BYREF
  void *v19[3]; // [rsp+80h] [rbp-58h] BYREF
  unsigned __int64 v20; // [rsp+98h] [rbp-40h]
  void **v21; // [rsp+A0h] [rbp-38h] BYREF
  __int64 v22; // [rsp+A8h] [rbp-30h] BYREF
  int v23; // [rsp+B0h] [rbp-28h]
  __int128 v24; // [rsp+B4h] [rbp-24h]

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  v21 = *(void ***)a4;
  v22 = 0;
  v23 = *(_DWORD *)(a4 + 16);
  v24 = *(_OWORD *)(a4 + 20);
  *(_QWORD *)&Block.Data1 = a2;
  *(_QWORD *)Block.Data4 = 0;
  v17 = 9;
  v18 = 0;
  CurrentControlSetRegistryHandle = NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle((NetSetup2::TransactionObject *)&Block);
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(Block.Data4);
  RegistryKey::DuplicateFrom(&v15, CurrentControlSetRegistryHandle);
  NetSetup2::ActiveObject::GetProperty(&v21, &Block, &NETSETUPPKEY_Driver_NtServiceName, 0);
  NetSetup2::Property::GetString(&Block, v19);
  std::vector<_NETSETUPPROPKEY>::_Tidy((char *)&v18 + 4);
  v5 = 0;
  v14 = 0;
  try
  {
    std::wstring::wstring(&Block, L"Services\\");
    std::wstring::append(&Block, v19, 0, -1);
    std::wstring::append(&Block, L"\\Parameters");
    p_Block = (const WCHAR *)&Block;
    if ( *(_QWORD *)((char *)&v18 + 4) >= 8u )
      p_Block = *(const WCHAR **)&Block.Data1;
    v7 = RegistryKey::OpenSubKey(&v15, (HKEY)hKey, p_Block, 3u, 0);
    v8 = *(HKEY *)v7;
    *(_QWORD *)v7 = 0;
    if ( v8 )
      v5 = v8;
    v14 = v5;
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    if ( *(_QWORD *)((char *)&v18 + 4) >= 8u )
      operator delete(*(void **)&Block.Data1);
  }
  catch ( ... )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v12 = v19;
      if ( v20 >= 8 )
        v12 = (void **)v19[0];
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_29ba87a86234370c6b57ad2ad12324db_Traceguids, v12);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v14);
    LOBYTE(v10) = 1;
    std::wstring::_Tidy(v19, v10, 0);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
    return std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v22);
  }
  NetSetup2::ActiveObject::GetProperty(
    &v21,
    &Block,
    (__int128 *)&NETSETUPPKEY_FilterDriver_SkipNdisAdaptersKeyGeneration,
    0);
  Boolean = NetSetup2::Property::GetBoolean((NetSetup2::Property *)&Block);
  std::vector<_NETSETUPPROPKEY>::_Tidy((char *)&v18 + 4);
  if ( Boolean )
  {
    RegistryKey::SetValue((RegistryKey *)&v14, L"SkipNdisAdaptersKeyGeneration", 1, 0);
    RegistryKey::DeleteSubKey((RegistryKey *)&v14, L"NdisAdapters");
    v5 = v14;
  }
  else if ( RegistryKey::ValueExists((RegistryKey *)&v14, L"SkipNdisAdaptersKeyGeneration") )
  {
    RegistryKey::DeleteValue(&v14, L"SkipNdisAdaptersKeyGeneration");
  }
  if ( v5 )
    RegCloseKey(v5);
  if ( v20 >= 8 )
    operator delete(v19[0]);
  v20 = 7;
  v19[2] = 0;
  LOWORD(v19[0]) = 0;
  if ( v15 )
    RegCloseKey(v15);
  return std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v22);
}

```

## disassembly

```asm
0x18002a0a0  mov     r11, rsp
0x18002a0a3  push    rdi
0x18002a0a4  sub     rsp, 0D0h
0x18002a0ab  mov     [rsp+0D8h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18002a0b4  mov     [r11+8], rbx
0x18002a0b8  mov     rax, cs:__security_cookie
0x18002a0bf  xor     rax, rsp
0x18002a0c2  mov     [rsp+0D8h+var_10], rax
0x18002a0ca  mov     rax, [r9]
0x18002a0cd  mov     [r11-38h], rax
0x18002a0d1  mov     qword ptr [r11-30h], 0
0x18002a0d9  mov     eax, [r9+10h]
0x18002a0dd  mov     [r11-28h], eax
0x18002a0e1  movups  xmm0, xmmword ptr [r9+14h]
0x18002a0e6  movdqu  xmmword ptr [r11-24h], xmm0
0x18002a0ec  xorps   xmm0, xmm0
0x18002a0ef  mov     [rsp+0D8h+Block], rdx
0x18002a0f4  mov     qword ptr [r11-80h], 0
0x18002a0fc  mov     [rsp+0D8h+var_78], 9
0x18002a104  movdqu  [rsp+0D8h+var_74], xmm0
0x18002a10a  lea     rcx, [rsp+0D8h+Block]; this
0x18002a10f  call    ?get_CurrentControlSetRegistryHandle@TransactionObject@NetSetup2@@QEBAPEAUHKEY__@@XZ; NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle(void)
0x18002a114  mov     rbx, rax
0x18002a117  lea     rcx, [rsp+0D8h+var_80]
0x18002a11c  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18002a121  mov     rdx, rbx
0x18002a124  lea     rcx, [rsp+0D8h+var_90]
0x18002a129  call    ?DuplicateFrom@RegistryKey@@SA?AV1@PEAUHKEY__@@@Z; RegistryKey::DuplicateFrom(HKEY__ *)
0x18002a12e  nop
0x18002a12f  xor     r9d, r9d
0x18002a132  lea     r8, NETSETUPPKEY_Driver_NtServiceName; unsigned int
0x18002a139  lea     rdx, [rsp+0D8h+Block]; struct _NETSETUPPROPKEY *
0x18002a13e  lea     rcx, [rsp+0D8h+var_38]; this
0x18002a146  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x18002a14b  nop
0x18002a14c  lea     rdx, [rsp+0D8h+var_58]
0x18002a154  lea     rcx, [rsp+0D8h+Block]
0x18002a159  call    ?GetString@Property@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::Property::GetString(void)
0x18002a15e  nop
0x18002a15f  lea     rcx, [rsp+0D8h+var_74+4]
0x18002a164  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18002a169  nop
0x18002a16a  xor     edi, edi
0x18002a16c  mov     [rsp+0D8h+var_98], rdi
0x18002a171  lea     rdx, aServices_0; "Services\\"
0x18002a178  lea     rcx, [rsp+0D8h+Block]
0x18002a17d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18002a182  nop
0x18002a183  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002a187  xor     r8d, r8d
0x18002a18a  lea     rdx, [rsp+0D8h+var_58]
0x18002a192  lea     rcx, [rsp+0D8h+Block]
0x18002a197  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002a19c  lea     rdx, aParameters; "\\Parameters"
0x18002a1a3  lea     rcx, [rsp+0D8h+Block]
0x18002a1a8  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::append(wchar_t const *)
0x18002a1ad  lea     r8, [rsp+0D8h+Block]
0x18002a1b2  cmp     qword ptr [rsp+0D8h+var_74+4], 8
0x18002a1b8  cmovnb  r8, [rsp+0D8h+Block]
0x18002a1be  mov     [rsp+0D8h+var_B8], rdi
0x18002a1c3  lea     r9d, [rdi+3]
0x18002a1c7  lea     rdx, [rsp+0D8h+hKey]
0x18002a1cc  lea     rcx, [rsp+0D8h+var_90]
0x18002a1d1  call    ?OpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::OpenSubKey(wchar_t const *,ulong,void *)
0x18002a1d6  mov     rcx, [rax]
0x18002a1d9  mov     [rax], rdi
0x18002a1dc  test    rcx, rcx
0x18002a1df  cmovnz  rdi, rcx
0x18002a1e3  mov     [rsp+0D8h+var_98], rdi
0x18002a1e8  mov     rcx, [rsp+0D8h+hKey]; hKey
0x18002a1ed  test    rcx, rcx
0x18002a1f0  jz      short loc_18002A1F9
0x18002a1f2  call    cs:__imp_RegCloseKey
0x18002a1f8  nop
0x18002a1f9  cmp     qword ptr [rsp+0D8h+var_74+4], 8
0x18002a1ff  jb      short loc_18002A20C
0x18002a201  mov     rcx, [rsp+0D8h+Block]; Block
0x18002a206  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a20b  nop
0x18002a20c  xor     r9d, r9d
0x18002a20f  lea     r8, NETSETUPPKEY_FilterDriver_SkipNdisAdaptersKeyGeneration; unsigned int
0x18002a216  lea     rdx, [rsp+0D8h+Block]; struct _NETSETUPPROPKEY *
0x18002a21b  lea     rcx, [rsp+0D8h+var_38]; this
0x18002a223  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x18002a228  nop
0x18002a229  lea     rcx, [rsp+0D8h+Block]; this
0x18002a22e  call    ?GetBoolean@Property@NetSetup2@@QEBA_NXZ; NetSetup2::Property::GetBoolean(void)
0x18002a233  mov     bl, al
0x18002a235  lea     rcx, [rsp+0D8h+var_74+4]
0x18002a23a  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18002a23f  lea     rdx, aSkipndisadapte; "SkipNdisAdaptersKeyGeneration"
0x18002a246  lea     rcx, [rsp+0D8h+var_98]; this
0x18002a24b  test    bl, bl
0x18002a24d  jz      short loc_18002A273
0x18002a24f  xor     r9d, r9d
0x18002a252  lea     r8d, [r9+1]
0x18002a256  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x18002a25b  lea     rdx, aNdisadapters; "NdisAdapters"
0x18002a262  lea     rcx, [rsp+0D8h+var_98]; this
0x18002a267  call    ?DeleteSubKey@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteSubKey(wchar_t const *)
0x18002a26c  mov     rdi, [rsp+0D8h+var_98]
0x18002a271  jmp     short loc_18002A28E
0x18002a273  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18002a278  test    al, al
0x18002a27a  jz      short loc_18002A28E
0x18002a27c  lea     rdx, aSkipndisadapte; "SkipNdisAdaptersKeyGeneration"
0x18002a283  lea     rcx, [rsp+0D8h+var_98]; this
0x18002a288  call    ?DeleteValue@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteValue(wchar_t const *)
0x18002a28d  nop
0x18002a28e  test    rdi, rdi
0x18002a291  jz      short loc_18002A29D
0x18002a293  mov     rcx, rdi; hKey
0x18002a296  call    cs:__imp_RegCloseKey
0x18002a29c  nop
0x18002a29d  cmp     [rsp+0D8h+var_40], 8
0x18002a2a6  jb      short loc_18002A2B5
0x18002a2a8  mov     rcx, [rsp+0D8h+var_58]; Block
0x18002a2b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a2b5  mov     [rsp+0D8h+var_40], 7
0x18002a2c1  mov     [rsp+0D8h+var_48], 0
0x18002a2cd  xor     eax, eax
0x18002a2cf  mov     word ptr [rsp+0D8h+var_58], ax
0x18002a2d7  mov     rcx, [rsp+0D8h+var_90]; hKey
0x18002a2dc  test    rcx, rcx
0x18002a2df  jz      short loc_18002A312
0x18002a2e1  call    cs:__imp_RegCloseKey
0x18002a2e7  jmp     short loc_18002A312
0x18002a2e9  lea     rcx, [rsp+0D8h+var_98]
0x18002a2ee  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a2f3  nop
0x18002a2f4  xor     r8d, r8d
0x18002a2f7  mov     dl, 1
0x18002a2f9  lea     rcx, [rsp+0D8h+var_58]
0x18002a301  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002a306  nop
0x18002a307  lea     rcx, [rsp+0D8h+var_90]
0x18002a30c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a311  nop
0x18002a312  lea     rcx, [rsp+0D8h+var_30]
0x18002a31a  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18002a31f  mov     rcx, [rsp+0D8h+var_10]
0x18002a327  xor     rcx, rsp; StackCookie
0x18002a32a  call    __security_check_cookie
0x18002a32f  mov     rbx, [rsp+0D8h+arg_0]
0x18002a337  add     rsp, 0D0h
0x18002a33e  pop     rdi
0x18002a33f  retn
```
