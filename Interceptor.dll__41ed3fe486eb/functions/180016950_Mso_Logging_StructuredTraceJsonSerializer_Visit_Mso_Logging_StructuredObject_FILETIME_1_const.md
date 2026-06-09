# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Logging::StructuredObject<_FILETIME,1> const &)

- ea: `0x180016950`
- end: `0x180016a48`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$StructuredObject@U_FILETIME@@$00@23@@Z`
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
- `0x180016950`
- `0x180019f74`
- `0x18001a170`
- `0x1800266e0`
- `0x1800282a0`
- `0x18002b3c0`

## string_xrefs

- `0x180016a25`: `StructuredTraceJsonSerializer::Visit failed to write structured value's name.`

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
  result = Mso::Logging::StructuredTraceJsonSerializer::WriteJson(this, (FILETIME *)(a2 + 16));
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
0x180016950  mov     [rsp+arg_10], rbx
0x180016955  push    rdi
0x180016956  sub     rsp, 80h
0x18001695d  mov     rax, cs:__security_cookie
0x180016964  xor     rax, rsp
0x180016967  mov     [rsp+88h+var_10], rax
0x18001696c  mov     rbx, rdx
0x18001696f  mov     rdi, rcx
0x180016972  mov     rcx, [rcx+8]
0x180016976  test    rcx, rcx
0x180016979  jz      loc_180016A15
0x18001697f  mov     rax, [rcx]
0x180016982  mov     rdx, [rdx+8]
0x180016986  mov     rax, [rax+30h]
0x18001698a  call    cs:__guard_dispatch_icall_fptr
0x180016990  test    al, al
0x180016992  jz      loc_180016A25
0x180016998  lea     rdx, [rbx+10h]; lpFileTime
0x18001699c  mov     rcx, rdi; this
0x18001699f  call    ?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBU_FILETIME@@@Z; Mso::Logging::StructuredTraceJsonSerializer::WriteJson(_FILETIME const &)
0x1800169a4  test    al, al
0x1800169a6  jz      short loc_1800169C6
0x1800169a8  mov     rcx, [rsp+88h+var_10]
0x1800169ad  xor     rcx, rsp; StackCookie
0x1800169b0  call    __security_check_cookie
0x1800169b5  mov     rbx, [rsp+88h+arg_10]
0x1800169bd  add     rsp, 80h
0x1800169c4  pop     rdi
0x1800169c5  retn
0x1800169c6  mov     rdx, [rbx+8]
0x1800169ca  lea     rcx, [rsp+88h+var_50]
0x1800169cf  call    ?StringFromWz@DoNotUse@StringCore@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; Mso::StringCore::DoNotUse::StringFromWz(wchar_t const *,unsigned __int64)
0x1800169d4  lea     r8, [rsp+88h+var_50]
0x1800169d9  lea     rcx, [rsp+88h+var_30]; void *
0x1800169de  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x1800169e3  lea     rdx, [rsp+88h+var_30]
0x1800169e8  lea     rcx, [rsp+88h+pExceptionObject]
0x1800169ed  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x1800169f2  nop     dword ptr [rax+00h]
0x1800169f6  nop     word ptr [rax+rax+00000000h]
0x180016a00  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180016a07  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180016a0c  call    _CxxThrowException
0x180016a12  jmp     short $+2
0x180016a14  nop
0x180016a15  xor     edx, edx; struct CrashContext *
0x180016a17  mov     ecx, 1E3C3840h; unsigned int
0x180016a1c  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180016a22  jmp     short $+2
0x180016a24  nop
0x180016a25  lea     rdx, aStructuredtrac_7; "StructuredTraceJsonSerializer::Visit fa"...
0x180016a2c  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180016a31  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180016a36  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180016a3d  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180016a42  call    _CxxThrowException
```
