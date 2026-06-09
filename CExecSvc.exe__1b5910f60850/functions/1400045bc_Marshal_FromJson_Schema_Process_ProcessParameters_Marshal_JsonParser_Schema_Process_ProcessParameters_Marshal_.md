# Marshal::FromJson<Schema::Process::ProcessParameters,>(Marshal::JsonParser &,Schema::Process::ProcessParameters *,Marshal::UnmarshalFlags)

- ea: `0x1400045bc`
- end: `0x140004740`
- name: `??$FromJson@UProcessParameters@Process@Schema@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@AEAVJsonParser@0@PEAUProcessParameters@Process@Schema@@W4UnmarshalFlags@0@@Z`
- size: `388`
- prototype: `_BYTE *__fastcall(__int64, Marshal::JsonParser *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140008670`

## callees

- `0x140002310`
- `0x140002ed8`
- `0x1400045bc`
- `0x14000a7bc`
- `0x14000e884`

## pseudocode

```c
_BYTE *__fastcall Marshal::FromJson<Schema::Process::ProcessParameters,>(__int64 a1, Marshal::JsonParser *a2)
{
  char v4; // r9
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rcx
  _BYTE *result; // rax
  __int64 v9; // rbx
  __int128 *v10; // rdi
  _QWORD *v11; // rax
  __int64 *v12; // rdi
  unsigned __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 v15; // rsi
  __int64 v16; // r14
  void **v17; // [rsp+38h] [rbp-C0h] BYREF
  __int128 *v18; // [rsp+40h] [rbp-B8h]
  __int64 *v19; // [rsp+48h] [rbp-B0h]
  __int64 v20[4]; // [rsp+50h] [rbp-A8h] BYREF
  int pExceptionObject; // [rsp+70h] [rbp-88h] BYREF
  _BYTE *v22; // [rsp+78h] [rbp-80h]
  _QWORD v23[2]; // [rsp+80h] [rbp-78h] BYREF
  __int128 v24; // [rsp+90h] [rbp-68h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-58h]
  __int64 v26; // [rsp+A8h] [rbp-50h]
  int v27; // [rsp+B0h] [rbp-48h]
  __int128 v28; // [rsp+B8h] [rbp-40h] BYREF
  __int128 v29; // [rsp+C8h] [rbp-30h]

  v22 = (_BYTE *)a1;
  v29 = 0;
  v28 = 0;
  *(_QWORD *)&v29 = 0;
  DWORD2(v29) = 2;
  v17 = &Marshal::UnmarshalContext::`vftable';
  v18 = &v28;
  v19 = 0;
  v23[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>,std::wstring,std::wstring,Marshal::ModifiedType<std::map<std::wstring,std::wstring>,Marshal::ModifierList<>,Marshal::ModifierList<>>,bool,bool,bool,bool,bool,Marshal::ModifiedType<std::array<unsigned short,2>,Marshal::ModifierList<>>,bool,bool,Marshal::ModifiedType<vmstd::optional<bool>,Marshal::ModifierList<>>>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value;
  v23[1] = &`CExec::Diagnostics::TraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
  v20[0] = (__int64)Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>,std::wstring,std::wstring,Marshal::ModifiedType<std::map<std::wstring,std::wstring>,Marshal::ModifierList<>,Marshal::ModifierList<>>,bool,bool,bool,bool,bool,Marshal::ModifiedType<std::array<unsigned short,2>,Marshal::ModifierList<>>,bool,bool,Marshal::ModifiedType<vmstd::optional<bool>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v20[1] = (__int64)&qword_140031088;
  try
  {
    v4 = Marshal::Details::ObjectFromJson(a2, (__int64)v20, (__int64)v23);
    if ( v4 && *((_QWORD *)a2 + 2) != *((_QWORD *)a2 + 1) )
    {
      pExceptionObject = 12;
      throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
    }
    v5 = v29;
    *(_QWORD *)&v29 = 0;
    v6 = *((_QWORD *)&v28 + 1);
    v7 = v28;
    v28 = 0u;
    *(_BYTE *)a1 = v4;
    v19 = 0;
    v18 = 0;
    v17 = 0;
    *(_QWORD *)(a1 + 8) = v7;
    *(_QWORD *)(a1 + 16) = v6;
    *(_QWORD *)(a1 + 24) = v5;
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v17);
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v28);
    result = (_BYTE *)a1;
  }
  catch ( Marshal::JsonParser::ParseException )
  {
    v24 = 0;
    v25 = 0;
    v26 = 0;
    std::wstring::_Construct<1,unsigned short const *>((__int64)&v24, L"$", 1u);
    v27 = 13;
    memset(v20, 0, 24);
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Buy_nonzero(v20, 1);
    v23[0] = v20;
    v9 = v20[0];
    v10 = &v24;
    v17 = (void **)v20[0];
    v18 = (__int128 *)v20[0];
    v19 = v20;
    do
    {
      std::wstring::wstring(v9, v10);
      *(_DWORD *)(v9 + 32) = *((_DWORD *)v10 + 8);
      v9 += 40;
      v18 = (__int128 *)v9;
      v10 = (__int128 *)((char *)v10 + 40);
    }
    while ( v10 != &v28 );
    v20[1] = v9;
    v11 = v22;
    *v22 = 0;
    v12 = v11 + 1;
    v11[1] = 0;
    v11[2] = 0;
    v11[3] = 0;
    v13 = 0xCCCCCCCCCCCCCCCDuLL * ((v9 - v20[0]) >> 3);
    if ( v13 )
    {
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Buy_nonzero(v12, v13);
      v23[0] = v12;
      v14 = *v12;
      v15 = v20[0];
      v16 = v20[1];
      v17 = (void **)v14;
      v18 = (__int128 *)v14;
      v19 = v12;
      while ( v15 != v16 )
      {
        std::wstring::wstring(v14, v15);
        *(_DWORD *)(v14 + 32) = *(_DWORD *)(v15 + 32);
        v14 += 40;
        v18 = (__int128 *)v14;
        v15 += 40;
      }
      v12[1] = v14;
    }
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v20);
    `eh vector destructor iterator'(
      &v24,
      0x28u,
      1u,
      std::pair<std::wstring,enum Marshal::UnmarshalError>::~pair<std::wstring,enum Marshal::UnmarshalError>);
    return v22;
  }
  v4 = Marshal::Details::ObjectFromJson(a2, (__int64)v20, (__int64)v23);
}

```

## disassembly

```asm
0x1400045bc  mov     r11, rsp
0x1400045bf  push    rbx
0x1400045c0  push    rsi
0x1400045c1  push    rdi
0x1400045c2  sub     rsp, 0E0h
0x1400045c9  mov     rax, cs:__security_cookie
0x1400045d0  xor     rax, rsp
0x1400045d3  mov     [rsp+0F8h+var_20], rax
0x1400045db  mov     rax, r8
0x1400045de  mov     rdi, rdx
0x1400045e1  mov     rbx, rcx
0x1400045e4  mov     [r11-80h], rcx
0x1400045e8  xor     esi, esi
0x1400045ea  mov     [rsp+0F8h+var_C8], esi
0x1400045ee  xorps   xmm0, xmm0
0x1400045f1  movups  xmmword ptr [r11-30h], xmm0
0x1400045f6  xorps   xmm1, xmm1
0x1400045f9  movdqu  xmmword ptr [r11-40h], xmm1
0x1400045ff  mov     [r11-30h], rsi
0x140004603  mov     dword ptr [r11-28h], 2
0x14000460b  lea     rcx, ??_7UnmarshalContext@Marshal@@6B@; const Marshal::UnmarshalContext::`vftable'
0x140004612  mov     [rsp+0F8h+var_C0], rcx
0x140004617  lea     rcx, [r11-40h]
0x14000461b  mov     [rsp+0F8h+var_B8], rcx
0x140004620  mov     [rsp+0F8h+var_B0], rsi
0x140004625  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$ModifiedType@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@V12@V12@U?$ModifiedType@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@U34@@4@_N_N_N_N_NU?$ModifiedType@V?$array@G$01@std@@U?$ModifierList@$$V@Marshal@@@4@_N_NU?$ModifiedType@U?$optional@_N@vmstd@@U?$ModifierList@$$V@Marshal@@@4@@Marshal@@UJsonTypeData@Details@2@UJsonTypeInfo@42@@Details@Marshal@@2V?$array@PEBUJsonTypeData@Details@Marshal@@$0P@@std@@A; std::array<Marshal::Details::JsonTypeData const *,15> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>,std::wstring,std::wstring,Marshal::ModifiedType<std::map<std::wstring,std::wstring>,Marshal::ModifierList<>,Marshal::ModifierList<>>,bool,bool,bool,bool,bool,Marshal::ModifiedType<std::array<ushort,2>,Marshal::ModifierList<>>,bool,bool,Marshal::ModifiedType<vmstd::optional<bool>,Marshal::ModifierList<>>>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value
0x14000462c  mov     [r11-78h], rcx
0x140004630  lea     rcx, ?__hInner@?1???0StaticHandle@TraceProvider@Diagnostics@CExec@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `CExec::Diagnostics::TraceProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140004637  mov     [r11-70h], rcx
0x14000463b  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$ModifiedType@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@V12@V12@U?$ModifiedType@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@U34@@4@_N_N_N_N_NU?$ModifiedType@V?$array@G$01@std@@U?$ModifierList@$$V@Marshal@@@4@_N_NU?$ModifiedType@U?$optional@_N@vmstd@@U?$ModifierList@$$V@Marshal@@@4@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$0P@@std@@A; std::array<Marshal::Details::BaseTypeData const *,15> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>,std::wstring,std::wstring,Marshal::ModifiedType<std::map<std::wstring,std::wstring>,Marshal::ModifierList<>,Marshal::ModifierList<>>,bool,bool,bool,bool,bool,Marshal::ModifiedType<std::array<ushort,2>,Marshal::ModifierList<>>,bool,bool,Marshal::ModifiedType<vmstd::optional<bool>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x140004642  mov     [rsp+0F8h+var_A8], rcx
0x140004647  lea     rcx, qword_140031088
0x14000464e  mov     [rsp+0F8h+var_A0], rcx
0x140004653  lea     rcx, [r11-78h]
0x140004657  mov     [rsp+0F8h+var_D0], rcx; __int64
0x14000465c  lea     rcx, [rsp+0F8h+var_A8]
0x140004661  mov     [rsp+0F8h+var_D8], rcx; __int64
0x140004666  lea     r9, ?ProcessParameters_ClassData@Process@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Process::ProcessParameters_ClassData
0x14000466d  lea     r8, [rsp+0F8h+var_C0]
0x140004672  mov     rdx, rax
0x140004675  mov     rcx, rdi; this
0x140004678  call    ?ObjectFromJson@Details@Marshal@@YA_NAEAVJsonParser@2@PEAXAEBVUnmarshalContext@2@AEBUClassData@2@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUJsonTypeData@Details@Marshal@@@12@@Z; Marshal::Details::ObjectFromJson(Marshal::JsonParser &,void *,Marshal::UnmarshalContext const &,Marshal::ClassData const &,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::JsonTypeData const *>)
0x14000467d  mov     r9b, al
0x140004680  test    al, al
0x140004682  jz      short loc_140004692
0x140004684  mov     rax, [rdi+8]
0x140004688  cmp     [rdi+10h], rax
0x14000468c  jnz     loc_140004725
0x140004692  mov     r8, qword ptr [rsp+0F8h+var_30]
0x14000469a  mov     qword ptr [rsp+0F8h+var_30], rsi
0x1400046a2  mov     rdx, [rsp+0F8h+var_38]
0x1400046aa  mov     [rsp+0F8h+var_38], rsi
0x1400046b2  mov     rcx, [rsp+0F8h+var_40]
0x1400046ba  mov     [rsp+0F8h+var_40], rsi
0x1400046c2  mov     [rbx], r9b
0x1400046c5  mov     [rsp+0F8h+var_B0], rsi
0x1400046ca  mov     [rsp+0F8h+var_B8], rsi
0x1400046cf  mov     [rsp+0F8h+var_C0], rsi
0x1400046d4  mov     [rbx+8], rcx
0x1400046d8  mov     [rbx+10h], rdx
0x1400046dc  mov     [rbx+18h], r8
0x1400046e0  mov     [rsp+0F8h+var_C8], 1
0x1400046e8  lea     rcx, [rsp+0F8h+var_C0]
0x1400046ed  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400046f2  nop
0x1400046f3  lea     rcx, [rsp+0F8h+var_40]
0x1400046fb  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x140004700  mov     rax, rbx
0x140004703  jmp     short loc_14000470A
0x140004705  mov     rax, [rsp+0F8h+var_80]
0x14000470a  mov     rcx, [rsp+0F8h+var_20]
0x140004712  xor     rcx, rsp; StackCookie
0x140004715  call    __security_check_cookie
0x14000471a  add     rsp, 0E0h
0x140004721  pop     rdi
0x140004722  pop     rsi
0x140004723  pop     rbx
0x140004724  retn
0x140004725  mov     [rsp+0F8h+pExceptionObject], 0Ch
0x14000472d  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x140004734  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x140004739  call    _CxxThrowException_0
```
