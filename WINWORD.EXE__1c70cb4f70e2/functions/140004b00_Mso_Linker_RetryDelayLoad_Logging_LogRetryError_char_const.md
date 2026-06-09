# Mso::Linker::RetryDelayLoad::Logging::LogRetryError(char const *)

- ea: `0x140004b00`
- end: `0x140004bff`
- name: `?LogRetryError@Logging@RetryDelayLoad@Linker@Mso@@YAXPEBD@Z`
- size: `255`
- prototype: `void __fastcall(Mso::Linker::RetryDelayLoad::Logging *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400045d0`

## callees

- `0x140001000`
- `0x1400048fc`
- `0x14000498c`
- `0x140004b00`
- `0x140004c2c`

## import_xrefs

- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x140004b79`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x140004b79`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x140004bd6`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x140004bd6`

## string_xrefs

- `0x140004b55`: `DllName`

## pseudocode

```c
void __fastcall Mso::Linker::RetryDelayLoad::Logging::LogRetryError(
        Mso::Linker::RetryDelayLoad::Logging *this,
        const char *a2)
{
  _QWORD *v2; // rax
  __int64 v3; // [rsp+30h] [rbp-78h] BYREF
  _QWORD v4[3]; // [rsp+38h] [rbp-70h] BYREF
  _QWORD v5[3]; // [rsp+50h] [rbp-58h] BYREF
  __int16 v6; // [rsp+68h] [rbp-40h]
  _BYTE Src[32]; // [rsp+70h] [rbp-38h] BYREF

  if ( sub_14000498C() )
  {
    v2 = (_QWORD *)sub_1400048FC(Src);
    if ( v2[3] > 7u )
      v2 = (_QWORD *)*v2;
    v5[2] = v2;
    v5[0] = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
    v6 = 0;
    v5[1] = L"DllName";
    if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(50685657, 51, 10, 0) )
    {
      v4[0] = &Mso::Logging::CompositeStructuredTrace::`vftable';
      v4[1] = &v3;
      v4[2] = v4;
      ((void (__fastcall *)(__int64, __int64, __int64, _QWORD, const wchar_t *, _QWORD *, _QWORD *))Mso::Logging::MsoSendStructuredTraceTag)(
        50685657,
        51,
        10,
        0,
        L"DelayloadRetryError",
        v4,
        v5);
    }
    std::wstring::_Tidy_deallocate(Src);
  }
}

```

## disassembly

```asm
0x140004b00  push    rbx
0x140004b02  sub     rsp, 0A0h
0x140004b09  mov     rax, cs:__security_cookie
0x140004b10  xor     rax, rsp
0x140004b13  mov     [rsp+0A8h+var_18], rax
0x140004b1b  mov     rbx, rcx
0x140004b1e  call    sub_14000498C
0x140004b23  test    al, al
0x140004b25  jz      loc_140004BE6
0x140004b2b  mov     rdx, rbx
0x140004b2e  lea     rcx, [rsp+0A8h+Src]; Src
0x140004b33  call    sub_1400048FC
0x140004b38  cmp     qword ptr [rax+18h], 7
0x140004b3d  jbe     short loc_140004B42
0x140004b3f  mov     rax, [rax]
0x140004b42  lea     rcx, ??_7?$StructuredObject@PEB_W$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable'
0x140004b49  mov     [rsp+0A8h+var_48], rax
0x140004b4e  mov     [rsp+0A8h+var_58], rcx
0x140004b53  xor     eax, eax
0x140004b55  lea     rcx, aDllname; "DllName"
0x140004b5c  mov     [rsp+0A8h+var_40], ax
0x140004b61  mov     [rsp+0A8h+var_50], rcx
0x140004b66  xor     r9d, r9d
0x140004b69  mov     ecx, 30566D9h
0x140004b6e  mov     edx, 33h ; '3'
0x140004b73  mov     r8d, 0Ah
0x140004b79  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x140004b7f  test    al, al
0x140004b81  jz      short loc_140004BDC
0x140004b83  lea     rax, [rsp+0A8h+var_58]
0x140004b88  xor     r9d, r9d
0x140004b8b  mov     [rsp+0A8h+var_78], rax
0x140004b90  mov     edx, 33h ; '3'
0x140004b95  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x140004b9c  mov     r8d, 0Ah
0x140004ba2  mov     [rsp+0A8h+var_70], rax
0x140004ba7  mov     ecx, 30566D9h
0x140004bac  lea     rax, [rsp+0A8h+var_78]
0x140004bb1  mov     [rsp+0A8h+var_68], rax
0x140004bb6  lea     rax, [rsp+0A8h+var_70]
0x140004bbb  mov     [rsp+0A8h+var_60], rax
0x140004bc0  lea     rax, [rsp+0A8h+var_70]
0x140004bc5  mov     [rsp+0A8h+var_80], rax
0x140004bca  lea     rax, aDelayloadretry_0; "DelayloadRetryError"
0x140004bd1  mov     [rsp+0A8h+var_88], rax
0x140004bd6  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,Mso::Logging::IStructuredTrace const &)
0x140004bdc  lea     rcx, [rsp+0A8h+Src]
0x140004be1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140004be6  mov     rcx, [rsp+0A8h+var_18]
0x140004bee  xor     rcx, rsp; StackCookie
0x140004bf1  call    __security_check_cookie
0x140004bf6  add     rsp, 0A0h
0x140004bfd  pop     rbx
0x140004bfe  retn
```
