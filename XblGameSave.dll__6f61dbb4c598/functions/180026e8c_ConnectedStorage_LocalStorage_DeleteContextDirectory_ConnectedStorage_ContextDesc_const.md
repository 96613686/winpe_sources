# ConnectedStorage::LocalStorage::DeleteContextDirectory(ConnectedStorage::ContextDesc const &)

- ea: `0x180026e8c`
- end: `0x18002702c`
- name: `?DeleteContextDirectory@LocalStorage@ConnectedStorage@@SAXAEBVContextDesc@2@@Z`
- size: `416`
- prototype: `void __fastcall(const struct ConnectedStorage::ContextDesc *)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031c14`
- `0x180033d80`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x180010e30`
- `0x18001b9c8`
- `0x18001c090`
- `0x180026e8c`
- `0x180027034`
- `0x1800270e8`
- `0x1800271ac`
- `0x180027248`
- `0x18004deec`
- `0x18004e3e0`
- `0x180050fa0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180026ef7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180026ef7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027006`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027006`
- `ntdll!RtlIsMultiSessionSku` at `0x180026eb5`
- `ntdll!RtlIsMultiSessionSku` at `0x180026eb5`

## string_xrefs

- `0x180026f01`: `CoCreateGuid(&guid)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ConnectedStorage::LocalStorage::DeleteContextDirectory(const struct ConnectedStorage::ContextDesc *a1)
{
  HRESULT v2; // eax
  const unsigned __int16 *v3; // r8
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // r9
  const unsigned __int16 *v8; // rax
  const unsigned __int16 *v9; // rdx
  __int64 v10; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v11; // [rsp+28h] [rbp-D8h] BYREF
  GUID pguid; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[32]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v14[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v15[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v16[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v17[528]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v18[528]; // [rsp+2D0h] [rbp+1D0h] BYREF

  if ( !(unsigned __int8)RtlIsMultiSessionSku() )
  {
    v11 = 0;
    ConnectedStorage::LocalStorage::GetUserContextRoot((__int64)v16, 0, &v11);
    ConnectedStorage::ContextDesc::GetContextDirectory(a1, v15);
    pguid = 0;
    v2 = CoCreateGuid(&pguid);
    if ( v2 < 0 )
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v2, (int)L"CoCreateGuid(&guid)", v3);
    std::wstring::wstring(v13);
    std::wstring::append(v13, v15);
    v4 = ConnectedStorage::GuidToString(v14, &pguid);
    std::wstring::append(v13, v4);
    std::wstring::_Tidy_deallocate(v14);
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
    ConnectedStorage::GenerateAbsolutePath<260>(v7, v6, v18);
    ConnectedStorage::GenerateAbsolutePath<260>(v10, v5, v17);
    v14[0] = &v10;
    v14[1] = v17;
    ConnectedStorage::_ExecuteWithVerifyFilePath__lambda_65b86daf9d6123feb67f065bf903dac4___(v18, v14);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
    v8 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
    ConnectedStorage::LocalStorage::DeleteDirectoryFromRoot(v8, v9);
    std::wstring::_Tidy_deallocate(v13);
    std::wstring::_Tidy_deallocate(v15);
    std::wstring::_Tidy_deallocate(v16);
    WindowsDeleteString(0);
  }
}

```

## disassembly

```asm
0x180026e8c  mov     [rsp-8+arg_8], rbx
0x180026e91  push    rbp
0x180026e92  lea     rbp, [rsp-3F0h]
0x180026e9a  sub     rsp, 4F0h
0x180026ea1  mov     rax, cs:__security_cookie
0x180026ea8  xor     rax, rsp
0x180026eab  mov     [rbp+3F0h+var_10], rax
0x180026eb2  mov     rbx, rcx
0x180026eb5  call    cs:__imp_RtlIsMultiSessionSku
0x180026ebb  test    al, al
0x180026ebd  jnz     loc_18002700C
0x180026ec3  mov     [rsp+4F0h+var_4C8], 0
0x180026ecc  lea     r8, [rsp+4F0h+var_4C8]
0x180026ed1  xor     edx, edx
0x180026ed3  lea     rcx, [rbp+3F0h+var_450]
0x180026ed7  call    ?GetUserContextRoot@LocalStorage@ConnectedStorage@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KAEBVSimpleHStringWrapper@2@@Z; ConnectedStorage::LocalStorage::GetUserContextRoot(unsigned __int64,ConnectedStorage::SimpleHStringWrapper const &)
0x180026edc  nop
0x180026edd  lea     rdx, [rbp+3F0h+var_470]
0x180026ee1  mov     rcx, rbx
0x180026ee4  call    ?GetContextDirectory@ContextDesc@ConnectedStorage@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConnectedStorage::ContextDesc::GetContextDirectory(void)
0x180026ee9  nop
0x180026eea  xorps   xmm0, xmm0
0x180026eed  movups  xmmword ptr [rsp+4F0h+pguid.Data1], xmm0
0x180026ef2  lea     rcx, [rsp+4F0h+pguid]; pguid
0x180026ef7  call    cs:__imp_CoCreateGuid
0x180026efd  test    eax, eax
0x180026eff  jns     short loc_180026F10
0x180026f01  lea     rdx, aCocreateguidGu; "CoCreateGuid(&guid)"
0x180026f08  mov     ecx, eax; this
0x180026f0a  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180026f10  lea     rdx, aD_1; "d_"
0x180026f17  lea     rcx, [rsp+4F0h+var_4B0]
0x180026f1c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180026f21  nop
0x180026f22  lea     rdx, [rbp+3F0h+var_470]
0x180026f26  lea     rcx, [rsp+4F0h+var_4B0]
0x180026f2b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180026f30  lea     rdx, [rsp+4F0h+pguid]
0x180026f35  lea     rcx, [rsp+4F0h+var_490]
0x180026f3a  call    ?GuidToString@ConnectedStorage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; ConnectedStorage::GuidToString(_GUID const &)
0x180026f3f  nop
0x180026f40  mov     rdx, rax
0x180026f43  lea     rcx, [rsp+4F0h+var_4B0]
0x180026f48  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180026f4d  nop
0x180026f4e  lea     rcx, [rsp+4F0h+var_490]
0x180026f53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026f58  lea     rcx, [rsp+4F0h+var_4B0]
0x180026f5d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026f62  mov     rbx, rax
0x180026f65  lea     rcx, [rbp+3F0h+var_450]
0x180026f69  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026f6e  mov     r9, rax
0x180026f71  mov     [rsp+4F0h+var_4D0], rax
0x180026f76  lea     rcx, [rbp+3F0h+var_470]
0x180026f7a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026f7f  mov     rdx, rax
0x180026f82  lea     r8, [rbp+3F0h+var_220]
0x180026f89  mov     rcx, r9
0x180026f8c  call    ??$GenerateAbsolutePath@$0BAE@@ConnectedStorage@@YAXPEBG0AEAY0BAE@G@Z; ConnectedStorage::GenerateAbsolutePath<260>(ushort const *,ushort const *,ushort (&)[260])
0x180026f91  lea     r8, [rbp+3F0h+var_430]
0x180026f95  mov     rdx, rbx
0x180026f98  mov     rcx, [rsp+4F0h+var_4D0]
0x180026f9d  call    ??$GenerateAbsolutePath@$0BAE@@ConnectedStorage@@YAXPEBG0AEAY0BAE@G@Z; ConnectedStorage::GenerateAbsolutePath<260>(ushort const *,ushort const *,ushort (&)[260])
0x180026fa2  lea     rax, [rsp+4F0h+var_4D0]
0x180026fa7  mov     [rsp+4F0h+var_490], rax
0x180026fac  lea     rax, [rbp+3F0h+var_430]
0x180026fb0  mov     [rsp+4F0h+var_488], rax
0x180026fb5  lea     rdx, [rsp+4F0h+var_490]
0x180026fba  lea     rcx, [rbp+3F0h+var_220]
0x180026fc1  call    ConnectedStorage___ExecuteWithVerifyFilePath__lambda_65b86daf9d6123feb67f065bf903dac4___
0x180026fc6  lea     rcx, [rsp+4F0h+var_4B0]
0x180026fcb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026fd0  mov     rdx, rax
0x180026fd3  lea     rcx, [rbp+3F0h+var_450]
0x180026fd7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026fdc  mov     rcx, rax; unsigned __int16 *
0x180026fdf  call    ?DeleteDirectoryFromRoot@LocalStorage@ConnectedStorage@@SAXPEBG0@Z; ConnectedStorage::LocalStorage::DeleteDirectoryFromRoot(ushort const *,ushort const *)
0x180026fe4  nop
0x180026fe5  lea     rcx, [rsp+4F0h+var_4B0]
0x180026fea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026fef  nop
0x180026ff0  lea     rcx, [rbp+3F0h+var_470]
0x180026ff4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026ff9  nop
0x180026ffa  lea     rcx, [rbp+3F0h+var_450]
0x180026ffe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027003  nop
0x180027004  xor     ecx, ecx; string
0x180027006  call    cs:__imp_WindowsDeleteString
0x18002700c  mov     rcx, [rbp+3F0h+var_10]
0x180027013  xor     rcx, rsp; StackCookie
0x180027016  call    __security_check_cookie
0x18002701b  mov     rbx, [rsp+4F0h+arg_8]
0x180027023  add     rsp, 4F0h
0x18002702a  pop     rbp
0x18002702b  retn
```
