# AppxAllUserStore::CheckKeyForEnablement(Common::RegistryKey *,ushort const *,bool &)

- ea: `0x18000c594`
- end: `0x18000c6dd`
- name: `?CheckKeyForEnablement@AppxAllUserStore@@YAJPEAVRegistryKey@Common@@PEBGAEA_N@Z`
- size: `329`
- prototype: `__int64 __fastcall(HKEY *this, struct Common::RegistryKey *, unsigned __int16 *, bool *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000af10`
- `0x18000bba0`
- `0x180038f20`

## callees

- `0x180002040`
- `0x180002748`
- `0x18000c594`
- `0x180018248`
- `0x18001a324`
- `0x18001b3f0`
- `0x18001fe4c`
- `0x180038508`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000c65b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000c65b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18000c60e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18000c60e`

## string_xrefs

- `0x18000c607`: `api-ms-win-core-featurestaging-l1-1-0.dll`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::CheckKeyForEnablement(
        HKEY *this,
        struct Common::RegistryKey *a2,
        unsigned __int16 *a3,
        bool *a4)
{
  int UInt32ValueIf; // ebx
  __int64 v7; // rdx
  HMODULE v9; // rcx
  const char *v10; // r9
  FARPROC ProcAddress; // rax
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // [rsp+20h] [rbp-30h]
  unsigned int v16; // [rsp+40h] [rbp-10h] BYREF
  const unsigned __int16 *v17; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HMODULE LibraryW; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v20; // [rsp+88h] [rbp+38h] BYREF

  *(_BYTE *)a3 = 1;
  v20 = 0;
  LOBYTE(LibraryW) = 0;
  UInt32ValueIf = Common::RegistryKey::GetUInt32ValueIfExists<unsigned long>(
                    this,
                    L"FeatureID",
                    (BYTE *)&v20,
                    (bool *)&LibraryW);
  if ( UInt32ValueIf < 0 )
  {
    v7 = 1576;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)(unsigned int)UInt32ValueIf,
      v15);
    return (unsigned int)UInt32ValueIf;
  }
  if ( (_BYTE)LibraryW )
  {
    v9 = hLibModule;
    if ( !hLibModule )
    {
      LibraryW = LoadLibraryW(L"api-ms-win-core-featurestaging-l1-1-0.dll");
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
        &hLibModule,
        &LibraryW);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&LibraryW);
      v9 = hLibModule;
      if ( !hLibModule )
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x632,
                 (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
                 v10);
    }
    ProcAddress = GetProcAddress(v9, "GetFeatureEnabledState");
    if ( !ProcAddress )
    {
      UInt32ValueIf = -2147023728;
      v7 = 1592;
      goto LABEL_3;
    }
    *(_BYTE *)a3 = (((__int64 (__fastcall *)(_QWORD, __int64))ProcAddress)(v20, 3) & 2) != 0;
    v12 = AppxAllUserStoreTelemetry::Provider();
    if ( *(_DWORD *)v12 > 5u )
    {
      LODWORD(LibraryW) = *(unsigned __int8 *)a3;
      v16 = v20;
      v17 = (const unsigned __int16 *)a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)v12,
        (__int64)&word_18005D1BE,
        v13,
        v14,
        (__int64)&v16,
        &v17,
        (__int64)&LibraryW);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c594  mov     [rsp-18h+arg_0], rbx
0x18000c599  push    rbp
0x18000c59a  push    rsi
0x18000c59b  push    rdi
0x18000c59c  mov     rbp, rsp
0x18000c59f  sub     rsp, 50h
0x18000c5a3  mov     rdi, r8
0x18000c5a6  mov     byte ptr [r8], 1
0x18000c5aa  mov     rsi, rdx
0x18000c5ad  mov     [rbp+arg_18], 0
0x18000c5b4  lea     r8, [rbp+arg_18]
0x18000c5b8  mov     byte ptr [rbp+arg_10], 0
0x18000c5bc  lea     rdx, aFeatureid; "FeatureID"
0x18000c5c3  lea     r9, [rbp+arg_10]
0x18000c5c7  call    ??$GetUInt32ValueIfExists@K@RegistryKey@Common@@QEAAJPEBGPEAKPEA_N@Z; Common::RegistryKey::GetUInt32ValueIfExists<ulong>(ushort const *,ulong *,bool *)
0x18000c5cc  mov     ebx, eax
0x18000c5ce  test    eax, eax
0x18000c5d0  jns     short loc_18000C5F1
0x18000c5d2  mov     edx, 628h; void *
0x18000c5d7  mov     rcx, [rbp+18h]; this
0x18000c5db  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000c5e2  mov     r9d, ebx; char *
0x18000c5e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c5ea  mov     eax, ebx
0x18000c5ec  jmp     loc_18000C6D0
0x18000c5f1  cmp     byte ptr [rbp+arg_10], 0
0x18000c5f5  jz      loc_18000C6CE
0x18000c5fb  mov     rcx, cs:hLibModule; hModule
0x18000c602  test    rcx, rcx
0x18000c605  jnz     short loc_18000C654
0x18000c607  lea     rcx, aApiMsWinCoreFe; "api-ms-win-core-featurestaging-l1-1-0.d"...
0x18000c60e  call    cs:__imp_LoadLibraryW
0x18000c614  lea     rdx, [rbp+arg_10]
0x18000c618  mov     [rbp+arg_10], rax
0x18000c61c  lea     rcx, hLibModule
0x18000c623  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x18000c628  lea     rcx, [rbp+arg_10]
0x18000c62c  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18000c631  mov     rcx, cs:hLibModule
0x18000c638  test    rcx, rcx
0x18000c63b  jnz     short loc_18000C654
0x18000c63d  mov     rcx, [rbp+18h]; this
0x18000c641  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000c648  mov     edx, 632h; void *
0x18000c64d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c652  jmp     short loc_18000C6D0
0x18000c654  lea     rdx, aGetfeatureenab; "GetFeatureEnabledState"
0x18000c65b  call    cs:__imp_GetProcAddress
0x18000c661  test    rax, rax
0x18000c664  jnz     short loc_18000C675
0x18000c666  mov     ebx, 80070490h
0x18000c66b  mov     edx, 638h
0x18000c670  jmp     loc_18000C5D7
0x18000c675  mov     ecx, [rbp+arg_18]
0x18000c678  mov     edx, 3
0x18000c67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c682  shr     eax, 1
0x18000c684  and     al, 1
0x18000c686  mov     [rdi], al
0x18000c688  call    ?Provider@AppxAllUserStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppxAllUserStoreTelemetry::Provider(void)
0x18000c68d  mov     ecx, [rax]
0x18000c68f  cmp     ecx, 5
0x18000c692  jbe     short loc_18000C6CE
0x18000c694  movzx   ecx, byte ptr [rdi]
0x18000c697  lea     rdx, word_18005D1BE
0x18000c69e  mov     dword ptr [rbp+arg_10], ecx
0x18000c6a1  mov     ecx, [rbp+arg_18]
0x18000c6a4  mov     [rbp+var_10], ecx
0x18000c6a7  lea     rcx, [rbp+arg_10]
0x18000c6ab  mov     [rsp+50h+var_20], rcx
0x18000c6b0  lea     rcx, [rbp+var_8]
0x18000c6b4  mov     [rsp+50h+var_28], rcx
0x18000c6b9  lea     rcx, [rbp+var_10]
0x18000c6bd  mov     [rsp+50h+var_30], rcx
0x18000c6c2  mov     rcx, rax
0x18000c6c5  mov     [rbp+var_8], rsi
0x18000c6c9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000c6ce  xor     eax, eax
0x18000c6d0  mov     rbx, [rsp+50h+arg_0]
0x18000c6d5  add     rsp, 50h
0x18000c6d9  pop     rdi
0x18000c6da  pop     rsi
0x18000c6db  pop     rbp
0x18000c6dc  retn
```
