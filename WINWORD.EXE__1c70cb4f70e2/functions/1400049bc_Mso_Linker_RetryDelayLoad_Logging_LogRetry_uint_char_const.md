# Mso::Linker::RetryDelayLoad::Logging::LogRetry(uint,char const *)

- ea: `0x1400049bc`
- end: `0x140004b00`
- name: `?LogRetry@Logging@RetryDelayLoad@Linker@Mso@@YAXIPEBD@Z`
- size: `324`
- prototype: `void __fastcall(Mso::Linker::RetryDelayLoad::Logging *__hidden this, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400045d0`

## callees

- `0x140001000`
- `0x1400048fc`
- `0x14000498c`
- `0x1400049bc`
- `0x140004c2c`

## import_xrefs

- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x140004a65`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x140004a65`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x140004acc`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x140004acc`

## string_xrefs

- `0x140004a22`: `DllName`

## pseudocode

```c
void __fastcall Mso::Linker::RetryDelayLoad::Logging::LogRetry(
        Mso::Linker::RetryDelayLoad::Logging *this,
        __int64 a2,
        const char *a3)
{
  int v3; // edi
  _QWORD *v4; // rax
  __int64 v5; // [rsp+30h] [rbp-98h] BYREF
  _QWORD v6[2]; // [rsp+40h] [rbp-88h] BYREF
  int v7; // [rsp+50h] [rbp-78h]
  __int16 v8; // [rsp+54h] [rbp-74h]
  _QWORD v9[3]; // [rsp+58h] [rbp-70h] BYREF
  _QWORD v10[3]; // [rsp+70h] [rbp-58h] BYREF
  __int16 v11; // [rsp+88h] [rbp-40h]
  _BYTE Src[32]; // [rsp+90h] [rbp-38h] BYREF

  v3 = (int)this;
  if ( sub_14000498C() )
  {
    v4 = (_QWORD *)sub_1400048FC(Src);
    if ( v4[3] > 7u )
      v4 = (_QWORD *)*v4;
    v10[2] = v4;
    v10[0] = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
    v6[0] = &Mso::Logging::StructuredObject<int,1>::`vftable';
    v10[1] = L"DllName";
    v6[1] = L"NumRetries";
    v11 = 0;
    v8 = 0;
    v7 = v3;
    if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(50685656, 51, 50, 0) )
    {
      v9[0] = &Mso::Logging::CompositeStructuredTrace::`vftable';
      v9[1] = &v5;
      v9[2] = v6;
      Mso::Logging::MsoSendStructuredTraceTag(50685656, 51, 50, 0, L"DelayloadRetry", v9, v6, v10);
    }
    std::wstring::_Tidy_deallocate(Src);
  }
}

```

## disassembly

```asm
0x1400049bc  mov     [rsp+arg_0], rbx
0x1400049c1  push    rdi
0x1400049c2  sub     rsp, 0C0h
0x1400049c9  mov     rax, cs:__security_cookie
0x1400049d0  xor     rax, rsp
0x1400049d3  mov     [rsp+0C8h+var_18], rax
0x1400049db  mov     rbx, rdx
0x1400049de  mov     edi, ecx
0x1400049e0  call    sub_14000498C
0x1400049e5  test    al, al
0x1400049e7  jz      loc_140004ADF
0x1400049ed  mov     rdx, rbx
0x1400049f0  lea     rcx, [rsp+0C8h+Src]; Src
0x1400049f8  call    sub_1400048FC
0x1400049fd  cmp     qword ptr [rax+18h], 7
0x140004a02  jbe     short loc_140004A07
0x140004a04  mov     rax, [rax]
0x140004a07  mov     [rsp+0C8h+var_48], rax
0x140004a0f  lea     rcx, ??_7?$StructuredObject@PEB_W$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable'
0x140004a16  mov     [rsp+0C8h+var_58], rcx
0x140004a1b  lea     rax, ??_7?$StructuredObject@H$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<int,1>::`vftable'
0x140004a22  lea     rcx, aDllname; "DllName"
0x140004a29  mov     [rsp+0C8h+var_88], rax
0x140004a2e  mov     [rsp+0C8h+var_50], rcx
0x140004a33  lea     rax, aNumretries; "NumRetries"
0x140004a3a  xor     ecx, ecx
0x140004a3c  mov     [rsp+0C8h+var_80], rax
0x140004a41  mov     [rsp+0C8h+var_40], cx
0x140004a49  xor     r9d, r9d
0x140004a4c  mov     [rsp+0C8h+var_74], cx
0x140004a51  mov     edx, 33h ; '3'
0x140004a56  mov     ecx, 30566D8h
0x140004a5b  mov     [rsp+0C8h+var_78], edi
0x140004a5f  mov     r8d, 32h ; '2'
0x140004a65  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x140004a6b  test    al, al
0x140004a6d  jz      short loc_140004AD2
0x140004a6f  lea     rax, [rsp+0C8h+var_88]
0x140004a74  xor     r9d, r9d
0x140004a77  mov     [rsp+0C8h+var_98], rax
0x140004a7c  mov     edx, 33h ; '3'
0x140004a81  lea     rax, [rsp+0C8h+var_58]
0x140004a86  mov     r8d, 32h ; '2'
0x140004a8c  mov     [rsp+0C8h+var_90], rax
0x140004a91  mov     ecx, 30566D8h
0x140004a96  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x140004a9d  mov     [rsp+0C8h+var_70], rax
0x140004aa2  lea     rax, [rsp+0C8h+var_98]
0x140004aa7  mov     [rsp+0C8h+var_68], rax
0x140004aac  lea     rax, [rsp+0C8h+var_88]
0x140004ab1  mov     [rsp+0C8h+var_60], rax
0x140004ab6  lea     rax, [rsp+0C8h+var_70]
0x140004abb  mov     [rsp+0C8h+var_A0], rax
0x140004ac0  lea     rax, aDelayloadretry; "DelayloadRetry"
0x140004ac7  mov     [rsp+0C8h+var_A8], rax
0x140004acc  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,Mso::Logging::IStructuredTrace const &)
0x140004ad2  lea     rcx, [rsp+0C8h+Src]
0x140004ada  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140004adf  mov     rcx, [rsp+0C8h+var_18]
0x140004ae7  xor     rcx, rsp; StackCookie
0x140004aea  call    __security_check_cookie
0x140004aef  mov     rbx, [rsp+0C8h+arg_0]
0x140004af7  add     rsp, 0C0h
0x140004afe  pop     rdi
0x140004aff  retn
```
