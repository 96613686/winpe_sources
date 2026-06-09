# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Logging::StructuredObject<_GUID,1> const &)

- ea: `0x180016b70`
- end: `0x180016c68`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$StructuredObject@U_GUID@@$00@23@@Z`
- size: `248`
- prototype: `__int64 __fastcall(Mso::Logging::StructuredTraceJsonSerializer *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x18000a434`
- `0x18000a580`
- `0x180012318`
- `0x180016658`
- `0x180016b70`
- `0x180019f74`
- `0x18001a1d4`
- `0x1800266e0`
- `0x1800282a0`
- `0x18002b3c0`

## string_xrefs

- `0x180016c45`: `StructuredTraceJsonSerializer::Visit failed to write structured value's name.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall Mso::Logging::StructuredTraceJsonSerializer::Visit(
        Mso::Logging::StructuredTraceJsonSerializer *this,
        const struct _GUID *a2)
{
  __int64 v4; // rcx
  bool result; // al
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v7[32]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v8[32]; // [rsp+58h] [rbp-30h] BYREF

  v4 = *((_QWORD *)this + 1);
  if ( !v4 )
    CrashWithRecovery(0x1E3C3840u, 0);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 48LL))(v4, *(_QWORD *)a2->Data4) )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject,
      "StructuredTraceJsonSerializer::Visit failed to write structured value's name.");
    throw (std::runtime_error *)pExceptionObject;
  }
  result = Mso::Logging::StructuredTraceJsonSerializer::WriteJson(this, a2 + 1);
  if ( !result )
  {
    Mso::StringCore::DoNotUse::StringFromWz(v7, *(_QWORD *)a2->Data4);
    std::operator+<char>(v8);
    std::runtime_error::runtime_error(pExceptionObject, v8);
    throw (std::runtime_error *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180016b70  mov     [rsp+arg_10], rbx
0x180016b75  push    rdi
0x180016b76  sub     rsp, 80h
0x180016b7d  mov     rax, cs:__security_cookie
0x180016b84  xor     rax, rsp
0x180016b87  mov     [rsp+88h+var_10], rax
0x180016b8c  mov     rbx, rdx
0x180016b8f  mov     rdi, rcx
0x180016b92  mov     rcx, [rcx+8]
0x180016b96  test    rcx, rcx
0x180016b99  jz      loc_180016C35
0x180016b9f  mov     rax, [rcx]
0x180016ba2  mov     rdx, [rdx+8]
0x180016ba6  mov     rax, [rax+30h]
0x180016baa  call    cs:__guard_dispatch_icall_fptr
0x180016bb0  test    al, al
0x180016bb2  jz      loc_180016C45
0x180016bb8  lea     rdx, [rbx+10h]; struct _GUID *
0x180016bbc  mov     rcx, rdi; this
0x180016bbf  call    ?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBU_GUID@@@Z; Mso::Logging::StructuredTraceJsonSerializer::WriteJson(_GUID const &)
0x180016bc4  test    al, al
0x180016bc6  jz      short loc_180016BE6
0x180016bc8  mov     rcx, [rsp+88h+var_10]
0x180016bcd  xor     rcx, rsp; StackCookie
0x180016bd0  call    __security_check_cookie
0x180016bd5  mov     rbx, [rsp+88h+arg_10]
0x180016bdd  add     rsp, 80h
0x180016be4  pop     rdi
0x180016be5  retn
0x180016be6  mov     rdx, [rbx+8]
0x180016bea  lea     rcx, [rsp+88h+var_50]
0x180016bef  call    ?StringFromWz@DoNotUse@StringCore@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; Mso::StringCore::DoNotUse::StringFromWz(wchar_t const *,unsigned __int64)
0x180016bf4  lea     r8, [rsp+88h+var_50]
0x180016bf9  lea     rcx, [rsp+88h+var_30]; void *
0x180016bfe  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x180016c03  lea     rdx, [rsp+88h+var_30]
0x180016c08  lea     rcx, [rsp+88h+pExceptionObject]
0x180016c0d  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x180016c12  nop     dword ptr [rax+00h]
0x180016c16  nop     word ptr [rax+rax+00000000h]
0x180016c20  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180016c27  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180016c2c  call    _CxxThrowException
0x180016c32  jmp     short $+2
0x180016c34  nop
0x180016c35  xor     edx, edx; struct CrashContext *
0x180016c37  mov     ecx, 1E3C3840h; unsigned int
0x180016c3c  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180016c42  jmp     short $+2
0x180016c44  nop
0x180016c45  lea     rdx, aStructuredtrac_7; "StructuredTraceJsonSerializer::Visit fa"...
0x180016c4c  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180016c51  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180016c56  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180016c5d  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180016c62  call    _CxxThrowException
```
