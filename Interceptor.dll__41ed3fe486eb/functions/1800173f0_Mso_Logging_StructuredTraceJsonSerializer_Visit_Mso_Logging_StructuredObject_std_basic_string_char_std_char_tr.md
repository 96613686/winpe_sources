# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Logging::StructuredObject<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,0> const &)

- ea: `0x1800173f0`
- end: `0x1800174f8`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$StructuredObject@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@23@@Z`
- size: `264`
- prototype: `__int64 __fastcall(Mso::Logging::StructuredTraceJsonSerializer *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x18000a434`
- `0x18000a580`
- `0x180012318`
- `0x180016658`
- `0x1800173f0`
- `0x180019f74`
- `0x18001a530`
- `0x1800266e0`
- `0x1800282a0`
- `0x18002b3c0`

## string_xrefs

- `0x1800174d5`: `StructuredTraceJsonSerializer::Visit failed to write structured value's name.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall Mso::Logging::StructuredTraceJsonSerializer::Visit(
        Mso::Logging::StructuredTraceJsonSerializer *this,
        __int64 a2)
{
  __int64 v4; // rcx
  char *v5; // rax
  bool result; // al
  char *v7; // [rsp+20h] [rbp-78h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-70h] BYREF
  _BYTE v9[32]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v10[32]; // [rsp+60h] [rbp-38h] BYREF

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
  v5 = (char *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 40) > 0xFu )
    v5 = *(char **)v5;
  v7 = v5;
  result = Mso::Logging::StructuredTraceJsonSerializer::WriteJson(this, (const char *const *)&v7);
  if ( !result )
  {
    Mso::StringCore::DoNotUse::StringFromWz(v9, *(_QWORD *)(a2 + 8));
    std::operator+<char>(v10);
    std::runtime_error::runtime_error(pExceptionObject, v10);
    throw (std::runtime_error *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x1800173f0  mov     [rsp+arg_10], rbx
0x1800173f5  push    rdi
0x1800173f6  sub     rsp, 90h
0x1800173fd  mov     rax, cs:__security_cookie
0x180017404  xor     rax, rsp
0x180017407  mov     [rsp+98h+var_18], rax
0x18001740f  mov     rbx, rdx
0x180017412  mov     rdi, rcx
0x180017415  mov     rcx, [rcx+8]
0x180017419  test    rcx, rcx
0x18001741c  jz      loc_1800174C3
0x180017422  mov     rax, [rcx]
0x180017425  mov     rdx, [rdx+8]
0x180017429  mov     rax, [rax+30h]
0x18001742d  call    cs:__guard_dispatch_icall_fptr
0x180017433  test    al, al
0x180017435  jz      loc_1800174D5
0x18001743b  lea     rax, [rbx+10h]
0x18001743f  cmp     qword ptr [rax+18h], 0Fh
0x180017444  jbe     short loc_180017449
0x180017446  mov     rax, [rax]
0x180017449  mov     [rsp+98h+var_78], rax
0x18001744e  lea     rdx, [rsp+98h+var_78]; char **
0x180017453  mov     rcx, rdi; this
0x180017456  call    ?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBQEBD@Z; Mso::Logging::StructuredTraceJsonSerializer::WriteJson(char const * const &)
0x18001745b  test    al, al
0x18001745d  jz      short loc_180017480
0x18001745f  mov     rcx, [rsp+98h+var_18]
0x180017467  xor     rcx, rsp; StackCookie
0x18001746a  call    __security_check_cookie
0x18001746f  mov     rbx, [rsp+98h+arg_10]
0x180017477  add     rsp, 90h
0x18001747e  pop     rdi
0x18001747f  retn
0x180017480  mov     rdx, [rbx+8]
0x180017484  lea     rcx, [rsp+98h+var_58]
0x180017489  call    ?StringFromWz@DoNotUse@StringCore@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; Mso::StringCore::DoNotUse::StringFromWz(wchar_t const *,unsigned __int64)
0x18001748e  nop
0x18001748f  lea     r8, [rsp+98h+var_58]
0x180017494  lea     rcx, [rsp+98h+var_38]; void *
0x180017499  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x18001749e  nop
0x18001749f  lea     rdx, [rsp+98h+var_38]
0x1800174a4  lea     rcx, [rsp+98h+pExceptionObject]
0x1800174a9  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x1800174ae  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800174b5  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800174ba  call    _CxxThrowException
0x1800174c0  jmp     short $+2
0x1800174c2  nop
0x1800174c3  xor     edx, edx; struct CrashContext *
0x1800174c5  mov     ecx, 1E3C3840h; unsigned int
0x1800174ca  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800174d0  jmp     short loc_1800174D4
0x1800174d4  nop
0x1800174d5  lea     rdx, aStructuredtrac_7; "StructuredTraceJsonSerializer::Visit fa"...
0x1800174dc  lea     rcx, [rsp+98h+pExceptionObject]; this
0x1800174e1  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800174e6  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800174ed  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800174f2  call    _CxxThrowException
```
