# CD3DShaderCacheInstaller::CD3DShaderCacheInstaller(ID3DShaderCacheInstallerClient *)

- ea: `0x180084fa4`
- end: `0x1800852f1`
- name: `??0CD3DShaderCacheInstaller@@QEAA@PEAUID3DShaderCacheInstallerClient@@@Z`
- size: `845`
- prototype: `CD3DShaderCacheInstaller *__fastcall(CD3DShaderCacheInstaller *__hidden this, struct ID3DShaderCacheInstallerClient *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18012907c`

## callees

- `0x180004a20`
- `0x18000b010`
- `0x180016c2c`
- `0x180016c90`
- `0x1800235dc`
- `0x1800578c4`
- `0x1800847d0`
- `0x18008487c`
- `0x180084938`
- `0x180084fa4`
- `0x180085970`
- `0x180085cc0`
- `0x1800a4854`
- `0x1800b8c14`
- `0x1800bb480`
- `0x1800c8ca0`
- `0x1800c9000`
- `0x180128e08`
- `0x18012a10c`
- `0x18012a130`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180085189`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180085189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800851bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800851bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800851ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800851ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008521a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008521a`

## string_xrefs

- `0x1800850b6`: `Software\Microsoft\DirectX\ShaderCache`
- `0x180085280`: `Software\Microsoft\DirectX\ShaderCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
CD3DShaderCacheInstaller *__fastcall CD3DShaderCacheInstaller::CD3DShaderCacheInstaller(
        CD3DShaderCacheInstaller *this,
        struct ID3DShaderCacheInstallerClient *a2)
{
  const unsigned __int16 *v4; // rdi
  HKEY *v5; // r15
  int v6; // eax
  char *v7; // r8
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  const wchar_t *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rax
  const WCHAR *p_lpName; // r8
  HANDLE MutexW; // r14
  char *v17; // rsi
  signed int LastError; // eax
  HKEY v19; // rsi
  int Key; // eax
  RegistryWriter *v21; // rcx
  int D3DAdapterState; // eax
  HKEY v24; // [rsp+20h] [rbp-79h] BYREF
  __int64 v25; // [rsp+28h] [rbp-71h] BYREF
  _BYTE v26[8]; // [rsp+30h] [rbp-69h] BYREF
  CD3DShaderCacheInstaller *v27; // [rsp+38h] [rbp-61h]
  LPCWSTR lpName; // [rsp+40h] [rbp-59h] BYREF
  char v29; // [rsp+48h] [rbp-51h]
  unsigned __int64 v30; // [rsp+58h] [rbp-41h]
  _BYTE v31[32]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v32[32]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v33[32]; // [rsp+A0h] [rbp+7h] BYREF

  v27 = this;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ID3D12StateObjectDatabaseFactory>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ID3D12StateObjectDatabaseFactory>();
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ID3DShaderCacheInstaller>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &CD3DShaderCacheInstaller::`vftable';
  *((_QWORD *)this + 2) = a2;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>((char *)this + 24);
  v4 = (const unsigned __int16 *)((char *)this + 48);
  std::wstring::wstring((char *)this + 48);
  *((_DWORD *)this + 20) = (*(__int64 (__fastcall **)(struct ID3DShaderCacheInstallerClient *))(*(_QWORD *)a2 + 8LL))(a2);
  v5 = (HKEY *)((char *)this + 88);
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  std::wstring::wstring((char *)this + 104);
  *((_QWORD *)this + 17) = 0;
  v25 = 0;
  v6 = (**(__int64 (__fastcall ***)(struct ID3DShaderCacheInstallerClient *, __int64 *, _QWORD))a2)(a2, &v25, 0);
  ThrowFailure(v6);
  std::wstring::resize((char *)this + 104, v25);
  if ( *((_QWORD *)this + 16) <= 7u )
    v7 = (char *)this + 104;
  else
    v7 = (char *)*((_QWORD *)this + 13);
  v8 = (**(__int64 (__fastcall ***)(struct ID3DShaderCacheInstallerClient *, __int64 *, char *))a2)(a2, &v25, v7);
  ThrowFailure(v8);
  v9 = std::wstring::wstring(v32, L"Software\\Microsoft\\DirectX\\ShaderCache");
  v10 = std::operator+<unsigned short>(&lpName, v9, L"\\");
  v11 = std::operator+<unsigned short>(v31, v10, (char *)this + 104);
  std::wstring::operator=((char *)this + 48, v11);
  std::wstring::_Tidy_deallocate(v31);
  std::wstring::_Tidy_deallocate(&lpName);
  std::wstring::_Tidy_deallocate(v32);
  v12 = L"Local";
  if ( *((_DWORD *)this + 20) )
    v12 = L"Global";
  std::wstring::wstring(v31, v12);
  v13 = std::wstring::wstring(v33, L"\\D3DSCR_");
  v14 = std::operator+<unsigned short>(v32, v31, v13);
  std::operator+<unsigned short>(&lpName, v14, (char *)this + 104);
  std::wstring::_Tidy_deallocate(v32);
  std::wstring::_Tidy_deallocate(v33);
  p_lpName = (const WCHAR *)&lpName;
  if ( v30 > 7 )
    p_lpName = lpName;
  MutexW = CreateMutexW(0, 0, p_lpName);
  v17 = (char *)*((_QWORD *)this + 12);
  if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v24);
    CloseHandle(v17);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v24);
  }
  *((_QWORD *)this + 12) = MutexW;
  LastError = GetLastError();
  if ( !*((_QWORD *)this + 12) || LastError == 183 )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ThrowFailure(LastError);
  }
  std::wstring::_Tidy_deallocate(&lpName);
  std::wstring::_Tidy_deallocate(v31);
  lpName = (LPCWSTR)-1LL;
  v29 = 0;
  v19 = *v5;
  if ( *v5 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v26);
    RegCloseKey(v19);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v26);
  }
  *v5 = 0;
  if ( *((_QWORD *)this + 9) > 7u )
    v4 = *(const unsigned __int16 **)v4;
  Key = RegistryWriter::CreateKey(
          (RegistryWriter *)&lpName,
          (HKEY)((*((_DWORD *)this + 20) != 0) - 0x7FFFFFFFLL),
          v4,
          (HKEY *)this + 11);
  ThrowFailure(Key);
  v24 = 0;
  if ( RegistryWriter::CreateKey(
         (RegistryWriter *)&lpName,
         (HKEY)((*((_DWORD *)this + 20) != 0) - 0x7FFFFFFFLL),
         L"Software\\Microsoft\\DirectX\\ShaderCache",
         &v24) >= 0 )
    RegistryWriter::AddUnsignedValueToKey(v21, v24, L"AdapterLuid", 0);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v24);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<long (*)(void *),&long NtClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<long (*)(void *),&long NtClose(void *)>>(&lpName);
  D3DAdapterState = CD3DShaderCacheInstaller::QueryD3DAdapterState(this);
  ThrowFailure(D3DAdapterState);
  return this;
}

```

## disassembly

```asm
0x180084fa4  mov     [rsp-8+arg_10], rbx
0x180084fa9  push    rbp
0x180084faa  push    rsi
0x180084fab  push    rdi
0x180084fac  push    r14
0x180084fae  push    r15
0x180084fb0  lea     rbp, [rsp-37h]
0x180084fb5  sub     rsp, 0D0h
0x180084fbc  mov     rax, cs:__security_cookie
0x180084fc3  xor     rax, rsp
0x180084fc6  mov     [rbp+57h+var_30], rax
0x180084fca  mov     rsi, rdx
0x180084fcd  mov     rbx, rcx
0x180084fd0  mov     [rbp+57h+var_B8], rcx
0x180084fd4  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UID3D12StateObjectDatabaseFactory@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ID3D12StateObjectDatabaseFactory>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ID3D12StateObjectDatabaseFactory>(void)
0x180084fd9  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UID3DShaderCacheInstaller@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ID3DShaderCacheInstaller>::`vftable'
0x180084fe0  mov     [rbx], rcx
0x180084fe3  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180084fea  test    rcx, rcx
0x180084fed  jz      short loc_180084FFC
0x180084fef  mov     rax, [rcx]
0x180084ff2  mov     rax, [rax+8]
0x180084ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084ffb  nop
0x180084ffc  lea     rax, ??_7CD3DShaderCacheInstaller@@6B@; const CD3DShaderCacheInstaller::`vftable'
0x180085003  mov     [rbx], rax
0x180085006  mov     [rbx+10h], rsi
0x18008500a  lea     rcx, [rbx+18h]; void *
0x18008500e  call    ??$?0AEBV?$allocator@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>(std::allocator<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>> const &)
0x180085013  nop
0x180085014  lea     rdi, [rbx+30h]
0x180085018  mov     rcx, rdi; void *
0x18008501b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180085020  nop
0x180085021  mov     rax, [rsi]
0x180085024  mov     rcx, rsi
0x180085027  mov     rax, [rax+8]
0x18008502b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085030  mov     [rbx+50h], eax
0x180085033  lea     r15, [rbx+58h]
0x180085037  mov     qword ptr [r15], 0
0x18008503e  mov     qword ptr [rbx+60h], 0
0x180085046  lea     r14, [rbx+68h]
0x18008504a  mov     rcx, r14; void *
0x18008504d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180085052  nop
0x180085053  mov     qword ptr [rbx+88h], 0
0x18008505e  mov     [rbp+57h+var_C8], 0
0x180085066  mov     rax, [rsi]
0x180085069  xor     r8d, r8d
0x18008506c  lea     rdx, [rbp+57h+var_C8]
0x180085070  mov     rcx, rsi
0x180085073  mov     rax, [rax]
0x180085076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008507b  mov     ecx, eax; int
0x18008507d  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180085082  mov     rdx, [rbp+57h+var_C8]
0x180085086  mov     rcx, r14
0x180085089  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18008508e  mov     rax, [rsi]
0x180085091  cmp     qword ptr [r14+18h], 7
0x180085096  jbe     short loc_18008509D
0x180085098  mov     r8, [r14]
0x18008509b  jmp     short loc_1800850A0
0x18008509d  mov     r8, r14
0x1800850a0  lea     rdx, [rbp+57h+var_C8]
0x1800850a4  mov     rcx, rsi
0x1800850a7  mov     rax, [rax]
0x1800850aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800850af  mov     ecx, eax; int
0x1800850b1  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800850b6  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\DirectX\\ShaderCac"...
0x1800850bd  lea     rcx, [rbp+57h+var_70]
0x1800850c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800850c6  nop
0x1800850c7  lea     r8, SubBlock; "\\"
0x1800850ce  mov     rdx, rax
0x1800850d1  lea     rcx, [rbp+57h+lpName]
0x1800850d5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800850da  nop
0x1800850db  mov     r8, r14
0x1800850de  mov     rdx, rax
0x1800850e1  lea     rcx, [rbp+57h+var_90]
0x1800850e5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800850ea  mov     rdx, rax
0x1800850ed  mov     rcx, rdi
0x1800850f0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800850f5  lea     rcx, [rbp+57h+var_90]
0x1800850f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800850fe  nop
0x1800850ff  lea     rcx, [rbp+57h+lpName]
0x180085103  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085108  nop
0x180085109  lea     rcx, [rbp+57h+var_70]
0x18008510d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085112  lea     rax, aGlobal; "Global"
0x180085119  lea     rdx, aLocal; "Local"
0x180085120  cmp     dword ptr [rbx+50h], 0
0x180085124  cmovnz  rdx, rax
0x180085128  lea     rcx, [rbp+57h+var_90]
0x18008512c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085131  nop
0x180085132  lea     rdx, aD3dscr; "\\D3DSCR_"
0x180085139  lea     rcx, [rbp+57h+var_50]
0x18008513d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085142  nop
0x180085143  mov     r8, rax
0x180085146  lea     rdx, [rbp+57h+var_90]
0x18008514a  lea     rcx, [rbp+57h+var_70]
0x18008514e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x180085153  nop
0x180085154  mov     r8, r14
0x180085157  mov     rdx, rax
0x18008515a  lea     rcx, [rbp+57h+lpName]
0x18008515e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180085163  nop
0x180085164  lea     rcx, [rbp+57h+var_70]
0x180085168  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008516d  nop
0x18008516e  lea     rcx, [rbp+57h+var_50]
0x180085172  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085177  lea     r8, [rbp+57h+lpName]
0x18008517b  cmp     [rbp+57h+var_98], 7
0x180085180  cmova   r8, [rbp+57h+lpName]; lpName
0x180085185  xor     edx, edx; bInitialOwner
0x180085187  xor     ecx, ecx; lpMutexAttributes
0x180085189  call    cs:__imp_CreateMutexW
0x18008518f  mov     r14, rax
0x180085192  mov     rsi, [rbx+60h]
0x180085196  lea     rax, [rsi-1]
0x18008519a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008519e  ja      short loc_1800851BB
0x1800851a0  lea     rcx, [rbp+57h+var_D0]; this
0x1800851a4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800851a9  mov     rcx, rsi; hObject
0x1800851ac  call    cs:__imp_CloseHandle
0x1800851b2  lea     rcx, [rbp+57h+var_D0]; this
0x1800851b6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800851bb  mov     [rbx+60h], r14
0x1800851bf  call    cs:__imp_GetLastError
0x1800851c5  cmp     qword ptr [rbx+60h], 0
0x1800851ca  jz      short loc_1800851D3
0x1800851cc  cmp     eax, 0B7h
0x1800851d1  jnz     short loc_1800851E7
0x1800851d3  test    eax, eax
0x1800851d5  jle     short loc_1800851DF
0x1800851d7  movzx   eax, ax
0x1800851da  or      eax, 80070000h
0x1800851df  mov     ecx, eax; int
0x1800851e1  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800851e6  nop
0x1800851e7  lea     rcx, [rbp+57h+lpName]
0x1800851eb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800851f0  nop
0x1800851f1  lea     rcx, [rbp+57h+var_90]
0x1800851f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800851fa  mov     [rbp+57h+lpName], 0FFFFFFFFFFFFFFFFh
0x180085202  mov     [rbp+57h+var_A8], 0
0x180085206  mov     rsi, [r15]
0x180085209  test    rsi, rsi
0x18008520c  jz      short loc_180085229
0x18008520e  lea     rcx, [rbp+57h+var_C0]; this
0x180085212  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180085217  mov     rcx, rsi; hKey
0x18008521a  call    cs:__imp_RegCloseKey
0x180085220  lea     rcx, [rbp+57h+var_C0]; this
0x180085224  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180085229  mov     qword ptr [r15], 0
0x180085230  cmp     qword ptr [rdi+18h], 7
0x180085235  jbe     short loc_18008523A
0x180085237  mov     rdi, [rdi]
0x18008523a  mov     eax, [rbx+50h]
0x18008523d  neg     eax
0x18008523f  sbb     rdx, rdx
0x180085242  neg     rdx
0x180085245  mov     rsi, 0FFFFFFFF80000001h
0x18008524c  add     rdx, rsi; HKEY
0x18008524f  mov     r9, r15; HKEY *
0x180085252  mov     r8, rdi; unsigned __int16 *
0x180085255  lea     rcx, [rbp+57h+lpName]; this
0x180085259  call    ?CreateKey@RegistryWriter@@QEAAJPEAUHKEY__@@PEBGPEAPEAU2@@Z; RegistryWriter::CreateKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18008525e  mov     ecx, eax; int
0x180085260  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180085265  nop
0x180085266  mov     [rbp+57h+var_D0], 0
0x18008526e  mov     eax, [rbx+50h]
0x180085271  neg     eax
0x180085273  sbb     rdx, rdx
0x180085276  neg     rdx
0x180085279  add     rdx, rsi; HKEY
0x18008527c  lea     r9, [rbp+57h+var_D0]; HKEY *
0x180085280  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\DirectX\\ShaderCac"...
0x180085287  lea     rcx, [rbp+57h+lpName]; this
0x18008528b  call    ?CreateKey@RegistryWriter@@QEAAJPEAUHKEY__@@PEBGPEAPEAU2@@Z; RegistryWriter::CreateKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180085290  test    eax, eax
0x180085292  js      short loc_1800852A8
0x180085294  xor     r9d, r9d; unsigned __int64
0x180085297  lea     r8, aAdapterluid; "AdapterLuid"
0x18008529e  mov     rdx, [rbp+57h+var_D0]; HKEY
0x1800852a2  call    ?AddUnsignedValueToKey@RegistryWriter@@QEAAJPEAUHKEY__@@PEBG_K@Z; RegistryWriter::AddUnsignedValueToKey(HKEY__ *,ushort const *,unsigned __int64)
0x1800852a7  nop
0x1800852a8  lea     rcx, [rbp+57h+var_D0]
0x1800852ac  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800852b1  nop
0x1800852b2  lea     rcx, [rbp+57h+lpName]
0x1800852b6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AJPEAX@Z$1?NtClose@@YAJ0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<long (*)(void *),&NtClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<long (*)(void *),&NtClose(void *)>>(void)
0x1800852bb  mov     rcx, rbx; this
0x1800852be  call    ?QueryD3DAdapterState@CD3DShaderCacheInstaller@@AEAAJXZ; CD3DShaderCacheInstaller::QueryD3DAdapterState(void)
0x1800852c3  mov     ecx, eax; int
0x1800852c5  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800852ca  nop
0x1800852cb  mov     rax, rbx
0x1800852ce  mov     rcx, [rbp+57h+var_30]
0x1800852d2  xor     rcx, rsp; StackCookie
0x1800852d5  call    __security_check_cookie
0x1800852da  mov     rbx, [rsp+0F0h+arg_10]
0x1800852e2  add     rsp, 0D0h
0x1800852e9  pop     r15
0x1800852eb  pop     r14
0x1800852ed  pop     rdi
0x1800852ee  pop     rsi
0x1800852ef  pop     rbp
0x1800852f0  retn
```
