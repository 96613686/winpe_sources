# ParseScdSettings(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,std::shared_ptr<SCDProvider>,SCDSetting &)

- ea: `0x1800ec560`
- end: `0x1800ec8cc`
- name: `?ParseScdSettings@@YAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@V?$shared_ptr@VSCDProvider@@@std@@AEAVSCDSetting@@@Z`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800eb948`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180019188`
- `0x180019208`
- `0x180019d38`
- `0x1800370d4`
- `0x18004abf8`
- `0x1800eaec8`
- `0x1800ec038`
- `0x1800ec560`
- `0x1800ec8d4`
- `0x1800f4508`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec61c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec68f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec61c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec68f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec5b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec63f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec88b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec5b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec63f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec88b`

## string_xrefs

- `0x1800ec5f1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`
- `0x1800ec794`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`
- `0x1800ec862`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserjson.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ParseScdSettings(__int64 *a1, _QWORD *a2, __int64 a3)
{
  __int64 v6; // r15
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v9; // rax
  int v10; // eax
  int v11; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // r8
  __int64 v14; // rdi
  unsigned int (__fastcall *v15)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v16; // rax
  PCWSTR v17; // rax
  __int64 v18; // rdi
  unsigned int (__fastcall *v19)(__int64, _QWORD, int *); // rbx
  __int64 v20; // rax
  __int64 v21; // rdi
  unsigned int (__fastcall *v22)(__int64, _QWORD, char *); // rbx
  __int64 v23; // rax
  __int64 v24; // rdi
  unsigned int (__fastcall *v25)(__int64, _QWORD, __int64 *); // rbx
  __int64 v26; // rax
  _QWORD *v27; // rax
  _QWORD *v28; // r15
  __int64 v29; // rdx
  __int64 v30; // rdi
  unsigned int (__fastcall *v31)(__int64, _QWORD, __int64 *); // rbx
  __int64 v32; // rax
  _QWORD *v33; // rax
  __int64 v34; // rdx
  _QWORD *v35; // rax
  std::_Ref_count_base *v36; // rcx
  int v38; // [rsp+20h] [rbp-60h] BYREF
  HSTRING v39; // [rsp+28h] [rbp-58h] BYREF
  HSTRING string[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v41; // [rsp+40h] [rbp-40h] BYREF
  __int64 v42[2]; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v43[32]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v42[1] = (__int64)a2;
  v6 = -1;
  if ( !*(_QWORD *)(a3 + 16) )
  {
    string[0] = 0;
    v7 = *a1;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a1 + 80LL);
    WindowsDeleteString(0);
    string[0] = 0;
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v43, &c_tagName);
    v10 = v8(v7, *(_QWORD *)(v9 + 24), string);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
        (const char *)(unsigned int)v10,
        v38);
      WindowsDeleteString(string[0]);
      string[0] = 0;
      goto LABEL_31;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
    v13 = -1;
    do
      ++v13;
    while ( StringRawBuffer[v13] );
    std::wstring::_Assign<unsigned short>((char **)a3, StringRawBuffer, (char *)v13);
    WindowsDeleteString(string[0]);
  }
  v39 = 0;
  v14 = *a1;
  v15 = *(unsigned int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a1 + 80LL);
  WindowsDeleteString(0);
  v39 = 0;
  v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v43, &c_tagDescription);
  if ( !v15(v14, *(_QWORD *)(v16 + 24), &v39) )
  {
    v17 = WindowsGetStringRawBuffer(v39, 0);
    do
      ++v6;
    while ( v17[v6] );
    std::wstring::_Assign<unsigned short>((char **)(a3 + 32), v17, (char *)v6);
  }
  LOBYTE(v38) = 0;
  v18 = *a1;
  v19 = *(unsigned int (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)*a1 + 96LL);
  v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v43, &c_tagReadOnly);
  if ( !v19(v18, *(_QWORD *)(v20 + 24), &v38) )
    *(_BYTE *)(a3 + 64) = (_BYTE)v38 == 1;
  BYTE1(v38) = 0;
  v21 = *a1;
  v22 = *(unsigned int (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)*a1 + 96LL);
  v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v43, &c_tagWriteOnly);
  if ( !v22(v21, *(_QWORD *)(v23 + 24), (char *)&v38 + 1) )
    *(_BYTE *)(a3 + 65) = BYTE1(v38) == 1;
  v41 = 0;
  v24 = *a1;
  v25 = *(unsigned int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*a1 + 64LL);
  v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v43, &c_tagProvider);
  if ( v25(v24, *(_QWORD *)(v26 + 24), &v41) )
  {
    if ( *a2 )
    {
      v35 = std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(string, a2);
      v28 = (_QWORD *)(a3 + 72);
      v11 = SCDCombineProviderFromParent(a3, v35, a3 + 72);
      if ( v11 < 0 )
      {
        v29 = 1644;
        goto LABEL_18;
      }
    }
    else
    {
      v28 = (_QWORD *)(a3 + 72);
    }
LABEL_21:
    v42[0] = 0;
    v30 = *a1;
    v31 = *(unsigned int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*a1 + 64LL);
    v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v43, &c_tagSchema);
    if ( v31(v30, *(_QWORD *)(v32 + 24), v42)
      || (v33 = std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(string, v28),
          v11 = ParseScdSchema(v42, v33, a3),
          v11 >= 0) )
    {
      v11 = ValidateScdSetting(a3, 0, 0);
      if ( v11 >= 0 )
      {
LABEL_29:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v42);
        goto LABEL_30;
      }
      v34 = 1653;
    }
    else
    {
      v34 = 1650;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
      (const char *)(unsigned int)v11,
      v38);
    goto LABEL_29;
  }
  v27 = std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(string, a2);
  v28 = (_QWORD *)(a3 + 72);
  v11 = ParseScdProvider(&v41, v27, (__int64 *)(a3 + 72));
  if ( v11 >= 0 )
    goto LABEL_21;
  v29 = 1640;
LABEL_18:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v29,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserjson.cpp",
    (const char *)(unsigned int)v11,
    v38);
LABEL_30:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
  WindowsDeleteString(v39);
  v39 = 0;
LABEL_31:
  v36 = (std::_Ref_count_base *)a2[1];
  if ( v36 )
    std::_Ref_count_base::_Decref(v36);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800ec560  mov     [rsp-38h+arg_18], rbx
0x1800ec565  push    rbp
0x1800ec566  push    rsi
0x1800ec567  push    rdi
0x1800ec568  push    r12
0x1800ec56a  push    r13
0x1800ec56c  push    r14
0x1800ec56e  push    r15
0x1800ec570  mov     rbp, rsp
0x1800ec573  sub     rsp, 80h
0x1800ec57a  mov     rax, cs:__security_cookie
0x1800ec581  xor     rax, rsp
0x1800ec584  mov     [rbp+var_8], rax
0x1800ec588  mov     rsi, r8
0x1800ec58b  mov     r14, rdx
0x1800ec58e  mov     r12, rcx
0x1800ec591  mov     [rbp+var_30], rdx
0x1800ec595  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800ec599  xor     r13d, r13d
0x1800ec59c  cmp     [r8+10h], r13
0x1800ec5a0  jnz     loc_1800EC645
0x1800ec5a6  mov     [rbp+string], r13
0x1800ec5aa  mov     rdi, [rcx]
0x1800ec5ad  mov     rax, [rdi]
0x1800ec5b0  mov     rbx, [rax+50h]
0x1800ec5b4  xor     ecx, ecx; string
0x1800ec5b6  call    cs:__imp_WindowsDeleteString
0x1800ec5bc  mov     [rbp+string], r13
0x1800ec5c0  lea     rdx, ?c_tagName@@3PEBGEB; ushort const * const c_tagName
0x1800ec5c7  lea     rcx, [rbp+var_28]
0x1800ec5cb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ec5d0  nop
0x1800ec5d1  lea     r8, [rbp+string]
0x1800ec5d5  mov     rdx, [rax+18h]
0x1800ec5d9  mov     rcx, rdi
0x1800ec5dc  mov     rax, rbx
0x1800ec5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec5e4  mov     ebx, eax
0x1800ec5e6  test    eax, eax
0x1800ec5e8  jns     short loc_1800EC616
0x1800ec5ea  mov     rcx, [rbp+38h]; this
0x1800ec5ee  mov     r9d, eax; char *
0x1800ec5f1  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ec5f8  mov     edx, 64Fh; void *
0x1800ec5fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec602  nop
0x1800ec603  mov     rcx, [rbp+string]; string
0x1800ec607  call    cs:__imp_WindowsDeleteString
0x1800ec60d  mov     [rbp+string], r13
0x1800ec611  jmp     loc_1800EC895
0x1800ec616  xor     edx, edx; length
0x1800ec618  mov     rcx, [rbp+string]; string
0x1800ec61c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ec622  mov     r8, r15
0x1800ec625  inc     r8
0x1800ec628  cmp     [rax+r8*2], r13w
0x1800ec62d  jnz     short loc_1800EC625
0x1800ec62f  mov     rdx, rax
0x1800ec632  mov     rcx, rsi
0x1800ec635  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ec63a  nop
0x1800ec63b  mov     rcx, [rbp+string]; string
0x1800ec63f  call    cs:__imp_WindowsDeleteString
0x1800ec645  mov     [rbp+var_58], r13
0x1800ec649  mov     rdi, [r12]
0x1800ec64d  mov     rax, [rdi]
0x1800ec650  mov     rbx, [rax+50h]
0x1800ec654  xor     ecx, ecx; string
0x1800ec656  call    cs:__imp_WindowsDeleteString
0x1800ec65c  mov     [rbp+var_58], r13
0x1800ec660  lea     rdx, ?c_tagDescription@@3PEBGEB; ushort const * const c_tagDescription
0x1800ec667  lea     rcx, [rbp+var_28]
0x1800ec66b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ec670  nop
0x1800ec671  lea     r8, [rbp+var_58]
0x1800ec675  mov     rdx, [rax+18h]
0x1800ec679  mov     rcx, rdi
0x1800ec67c  mov     rax, rbx
0x1800ec67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec684  nop
0x1800ec685  test    eax, eax
0x1800ec687  jnz     short loc_1800EC6AE
0x1800ec689  xor     edx, edx; length
0x1800ec68b  mov     rcx, [rbp+var_58]; string
0x1800ec68f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ec695  inc     r15
0x1800ec698  cmp     [rax+r15*2], r13w
0x1800ec69d  jnz     short loc_1800EC695
0x1800ec69f  lea     rcx, [rsi+20h]
0x1800ec6a3  mov     r8, r15
0x1800ec6a6  mov     rdx, rax
0x1800ec6a9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ec6ae  mov     [rbp+var_60], r13b
0x1800ec6b2  mov     rdi, [r12]
0x1800ec6b6  mov     rax, [rdi]
0x1800ec6b9  mov     rbx, [rax+60h]
0x1800ec6bd  lea     rdx, ?c_tagReadOnly@@3PEBGEB; ushort const * const c_tagReadOnly
0x1800ec6c4  lea     rcx, [rbp+var_28]
0x1800ec6c8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ec6cd  nop
0x1800ec6ce  lea     r8, [rbp+var_60]
0x1800ec6d2  mov     rdx, [rax+18h]
0x1800ec6d6  mov     rcx, rdi
0x1800ec6d9  mov     rax, rbx
0x1800ec6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec6e1  nop
0x1800ec6e2  test    eax, eax
0x1800ec6e4  jnz     short loc_1800EC6F0
0x1800ec6e6  cmp     [rbp+var_60], 1
0x1800ec6ea  setz    al
0x1800ec6ed  mov     [rsi+40h], al
0x1800ec6f0  mov     [rbp+var_5F], r13b
0x1800ec6f4  mov     rdi, [r12]
0x1800ec6f8  mov     rax, [rdi]
0x1800ec6fb  mov     rbx, [rax+60h]
0x1800ec6ff  lea     rdx, ?c_tagWriteOnly@@3PEBGEB; ushort const * const c_tagWriteOnly
0x1800ec706  lea     rcx, [rbp+var_28]
0x1800ec70a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ec70f  nop
0x1800ec710  lea     r8, [rbp+var_5F]
0x1800ec714  mov     rdx, [rax+18h]
0x1800ec718  mov     rcx, rdi
0x1800ec71b  mov     rax, rbx
0x1800ec71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec723  nop
0x1800ec724  test    eax, eax
0x1800ec726  jnz     short loc_1800EC732
0x1800ec728  cmp     [rbp+var_5F], 1
0x1800ec72c  setz    al
0x1800ec72f  mov     [rsi+41h], al
0x1800ec732  mov     [rbp+var_40], r13
0x1800ec736  mov     rdi, [r12]
0x1800ec73a  mov     rax, [rdi]
0x1800ec73d  mov     rbx, [rax+40h]
0x1800ec741  lea     rdx, ?c_tagProvider@@3PEBGEB; ushort const * const c_tagProvider
0x1800ec748  lea     rcx, [rbp+var_28]
0x1800ec74c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ec751  nop
0x1800ec752  lea     r8, [rbp+var_40]
0x1800ec756  mov     rdx, [rax+18h]
0x1800ec75a  mov     rcx, rdi
0x1800ec75d  mov     rax, rbx
0x1800ec760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec765  nop
0x1800ec766  test    eax, eax
0x1800ec768  jnz     short loc_1800EC7AC
0x1800ec76a  mov     rdx, r14
0x1800ec76d  lea     rcx, [rbp+string]
0x1800ec771  call    ??0?$shared_ptr@VSCDSetting@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(std::shared_ptr<SCDSetting> const &)
0x1800ec776  lea     r15, [rsi+48h]
0x1800ec77a  mov     r8, r15
0x1800ec77d  mov     rdx, rax
0x1800ec780  lea     rcx, [rbp+var_40]
0x1800ec784  call    ?ParseScdProvider@@YAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@V?$shared_ptr@VSCDProvider@@@std@@AEAV45@@Z; ParseScdProvider(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,std::shared_ptr<SCDProvider>,std::shared_ptr<SCDProvider> &)
0x1800ec789  mov     ebx, eax
0x1800ec78b  test    eax, eax
0x1800ec78d  jns     short loc_1800EC7B5
0x1800ec78f  mov     edx, 668h; void *
0x1800ec794  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ec79b  mov     r9d, ebx; char *
0x1800ec79e  mov     rcx, [rbp+38h]; this
0x1800ec7a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec7a7  jmp     loc_1800EC87D
0x1800ec7ac  cmp     [r14], r13
0x1800ec7af  jnz     short loc_1800EC815
0x1800ec7b1  lea     r15, [rsi+48h]
0x1800ec7b5  mov     [rbp+var_38], r13
0x1800ec7b9  mov     rdi, [r12]
0x1800ec7bd  mov     rax, [rdi]
0x1800ec7c0  mov     rbx, [rax+40h]
0x1800ec7c4  lea     rdx, ?c_tagSchema@@3PEBGEB; ushort const * const c_tagSchema
0x1800ec7cb  lea     rcx, [rbp+var_28]
0x1800ec7cf  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ec7d4  nop
0x1800ec7d5  lea     r8, [rbp+var_38]
0x1800ec7d9  mov     rdx, [rax+18h]
0x1800ec7dd  mov     rcx, rdi
0x1800ec7e0  mov     rax, rbx
0x1800ec7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec7e8  nop
0x1800ec7e9  test    eax, eax
0x1800ec7eb  jnz     short loc_1800EC847
0x1800ec7ed  mov     rdx, r15
0x1800ec7f0  lea     rcx, [rbp+string]
0x1800ec7f4  call    ??0?$shared_ptr@VSCDSetting@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(std::shared_ptr<SCDSetting> const &)
0x1800ec7f9  mov     r8, rsi
0x1800ec7fc  mov     rdx, rax
0x1800ec7ff  lea     rcx, [rbp+var_38]
0x1800ec803  call    ?ParseScdSchema@@YAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@V?$shared_ptr@VSCDProvider@@@std@@AEAVSCDSetting@@@Z; ParseScdSchema(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,std::shared_ptr<SCDProvider>,SCDSetting &)
0x1800ec808  mov     ebx, eax
0x1800ec80a  test    eax, eax
0x1800ec80c  jns     short loc_1800EC847
0x1800ec80e  mov     edx, 672h
0x1800ec813  jmp     short loc_1800EC85F
0x1800ec815  mov     rdx, r14
0x1800ec818  lea     rcx, [rbp+string]
0x1800ec81c  call    ??0?$shared_ptr@VSCDSetting@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(std::shared_ptr<SCDSetting> const &)
0x1800ec821  lea     r15, [rsi+48h]
0x1800ec825  mov     r8, r15
0x1800ec828  mov     rdx, rax
0x1800ec82b  mov     rcx, rsi
0x1800ec82e  call    ?SCDCombineProviderFromParent@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VSCDProvider@@@2@AEAV32@@Z; SCDCombineProviderFromParent(std::wstring &,std::shared_ptr<SCDProvider>,std::shared_ptr<SCDProvider> &)
0x1800ec833  mov     ebx, eax
0x1800ec835  test    eax, eax
0x1800ec837  jns     loc_1800EC7B5
0x1800ec83d  mov     edx, 66Ch
0x1800ec842  jmp     loc_1800EC794
0x1800ec847  xor     r8d, r8d
0x1800ec84a  xor     edx, edx
0x1800ec84c  mov     rcx, rsi
0x1800ec84f  call    ?ValidateScdSetting@@YAJAEBVSCDSetting@@PEBV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_N@Z; ValidateScdSetting(SCDSetting const &,std::unordered_set<std::wstring> const *,bool)
0x1800ec854  mov     ebx, eax
0x1800ec856  test    eax, eax
0x1800ec858  jns     short loc_1800EC873
0x1800ec85a  mov     edx, 675h; void *
0x1800ec85f  mov     r9d, ebx; char *
0x1800ec862  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ec869  mov     rcx, [rbp+38h]; this
0x1800ec86d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec872  nop
0x1800ec873  lea     rcx, [rbp+var_38]
0x1800ec877  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ec87c  nop
0x1800ec87d  lea     rcx, [rbp+var_40]
0x1800ec881  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ec886  nop
0x1800ec887  mov     rcx, [rbp+var_58]; string
0x1800ec88b  call    cs:__imp_WindowsDeleteString
0x1800ec891  mov     [rbp+var_58], r13
0x1800ec895  mov     rcx, [r14+8]; this
0x1800ec899  test    rcx, rcx
0x1800ec89c  jz      short loc_1800EC8A3
0x1800ec89e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ec8a3  mov     eax, ebx
0x1800ec8a5  mov     rcx, [rbp+var_8]
0x1800ec8a9  xor     rcx, rsp; StackCookie
0x1800ec8ac  call    __security_check_cookie
0x1800ec8b1  mov     rbx, [rsp+80h+arg_18]
0x1800ec8b9  add     rsp, 80h
0x1800ec8c0  pop     r15
0x1800ec8c2  pop     r14
0x1800ec8c4  pop     r13
0x1800ec8c6  pop     r12
0x1800ec8c8  pop     rdi
0x1800ec8c9  pop     rsi
0x1800ec8ca  pop     rbp
0x1800ec8cb  retn
```
