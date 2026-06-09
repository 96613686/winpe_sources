# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Logging::StructuredObject<char const *,1> const &)

- ea: `0x180017500`
- end: `0x1800175ec`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$StructuredObject@PEBD$00@23@@Z`
- size: `236`
- prototype: `__int64 __fastcall(Mso::Logging::StructuredTraceJsonSerializer *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x18000a434`
- `0x18000a580`
- `0x180012318`
- `0x180016658`
- `0x180017500`
- `0x180019f74`
- `0x18001a530`
- `0x1800266e0`
- `0x1800282a0`
- `0x18002b3c0`

## string_xrefs

- `0x1800175c9`: `StructuredTraceJsonSerializer::Visit failed to write structured value's name.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall Mso::Logging::StructuredTraceJsonSerializer::Visit(
        Mso::Logging::StructuredTraceJsonSerializer *this,
        __int64 a2)
{
  __int64 v4; // rcx
  bool result; // al
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v7[32]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v8[32]; // [rsp+58h] [rbp-30h] BYREF

  v4 = *((_QWORD *)this + 1);
  if ( !v4 )
    CrashWithRecovery(0x1E3C3840u, 0);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 48LL))(v4, *(_QWORD *)(a2 + 8)) )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject,
      "StructuredTraceJsonSerializer::Visit failed to write structured value's name.");
    throw (std::runtime_error *)pExceptionObject;
  }
  result = Mso::Logging::StructuredTraceJsonSerializer::WriteJson(this, (const char *const *)(a2 + 16));
  if ( !result )
  {
    Mso::StringCore::DoNotUse::StringFromWz(v7, *(_QWORD *)(a2 + 8));
    std::operator+<char>(v8);
    std::runtime_error::runtime_error(pExceptionObject, v8);
    throw (std::runtime_error *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180017500  mov     [rsp+arg_10], rbx
0x180017505  push    rdi
0x180017506  sub     rsp, 80h
0x18001750d  mov     rax, cs:__security_cookie
0x180017514  xor     rax, rsp
0x180017517  mov     [rsp+88h+var_10], rax
0x18001751c  mov     rbx, rdx
0x18001751f  mov     rdi, rcx
0x180017522  mov     rcx, [rcx+8]
0x180017526  test    rcx, rcx
0x180017529  jz      loc_1800175B9
0x18001752f  mov     rax, [rcx]
0x180017532  mov     rdx, [rdx+8]
0x180017536  mov     rax, [rax+30h]
0x18001753a  call    cs:__guard_dispatch_icall_fptr
0x180017540  test    al, al
0x180017542  jz      loc_1800175C9
0x180017548  lea     rdx, [rbx+10h]; char **
0x18001754c  mov     rcx, rdi; this
0x18001754f  call    ?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBQEBD@Z; Mso::Logging::StructuredTraceJsonSerializer::WriteJson(char const * const &)
0x180017554  test    al, al
0x180017556  jz      short loc_180017576
0x180017558  mov     rcx, [rsp+88h+var_10]
0x18001755d  xor     rcx, rsp; StackCookie
0x180017560  call    __security_check_cookie
0x180017565  mov     rbx, [rsp+88h+arg_10]
0x18001756d  add     rsp, 80h
0x180017574  pop     rdi
0x180017575  retn
0x180017576  mov     rdx, [rbx+8]
0x18001757a  lea     rcx, [rsp+88h+var_50]
0x18001757f  call    ?StringFromWz@DoNotUse@StringCore@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; Mso::StringCore::DoNotUse::StringFromWz(wchar_t const *,unsigned __int64)
0x180017584  nop
0x180017585  lea     r8, [rsp+88h+var_50]
0x18001758a  lea     rcx, [rsp+88h+var_30]; void *
0x18001758f  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x180017594  nop
0x180017595  lea     rdx, [rsp+88h+var_30]
0x18001759a  lea     rcx, [rsp+88h+pExceptionObject]
0x18001759f  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x1800175a4  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800175ab  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800175b0  call    _CxxThrowException
0x1800175b6  jmp     short $+2
0x1800175b8  nop
0x1800175b9  xor     edx, edx; struct CrashContext *
0x1800175bb  mov     ecx, 1E3C3840h; unsigned int
0x1800175c0  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800175c6  jmp     short $+2
0x1800175c8  nop
0x1800175c9  lea     rdx, aStructuredtrac_7; "StructuredTraceJsonSerializer::Visit fa"...
0x1800175d0  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800175d5  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800175da  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800175e1  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800175e6  call    _CxxThrowException
```
