# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Logging::StructuredObject<_SYSTEMTIME,1> const &)

- ea: `0x1800172f0`
- end: `0x1800173e8`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$StructuredObject@U_SYSTEMTIME@@$00@23@@Z`
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
- `0x1800172f0`
- `0x180019f74`
- `0x18001a3e0`
- `0x1800266e0`
- `0x1800282a0`
- `0x18002b3c0`

## string_xrefs

- `0x1800173c5`: `StructuredTraceJsonSerializer::Visit failed to write structured value's name.`

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
  result = Mso::Logging::StructuredTraceJsonSerializer::WriteJson(this, (const struct _SYSTEMTIME *)(a2 + 16));
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
0x1800172f0  mov     [rsp+arg_10], rbx
0x1800172f5  push    rdi
0x1800172f6  sub     rsp, 80h
0x1800172fd  mov     rax, cs:__security_cookie
0x180017304  xor     rax, rsp
0x180017307  mov     [rsp+88h+var_10], rax
0x18001730c  mov     rbx, rdx
0x18001730f  mov     rdi, rcx
0x180017312  mov     rcx, [rcx+8]
0x180017316  test    rcx, rcx
0x180017319  jz      loc_1800173B5
0x18001731f  mov     rax, [rcx]
0x180017322  mov     rdx, [rdx+8]
0x180017326  mov     rax, [rax+30h]
0x18001732a  call    cs:__guard_dispatch_icall_fptr
0x180017330  test    al, al
0x180017332  jz      loc_1800173C5
0x180017338  lea     rdx, [rbx+10h]; struct _SYSTEMTIME *
0x18001733c  mov     rcx, rdi; this
0x18001733f  call    ?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBU_SYSTEMTIME@@@Z; Mso::Logging::StructuredTraceJsonSerializer::WriteJson(_SYSTEMTIME const &)
0x180017344  test    al, al
0x180017346  jz      short loc_180017366
0x180017348  mov     rcx, [rsp+88h+var_10]
0x18001734d  xor     rcx, rsp; StackCookie
0x180017350  call    __security_check_cookie
0x180017355  mov     rbx, [rsp+88h+arg_10]
0x18001735d  add     rsp, 80h
0x180017364  pop     rdi
0x180017365  retn
0x180017366  mov     rdx, [rbx+8]
0x18001736a  lea     rcx, [rsp+88h+var_50]
0x18001736f  call    ?StringFromWz@DoNotUse@StringCore@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; Mso::StringCore::DoNotUse::StringFromWz(wchar_t const *,unsigned __int64)
0x180017374  lea     r8, [rsp+88h+var_50]
0x180017379  lea     rcx, [rsp+88h+var_30]; void *
0x18001737e  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x180017383  lea     rdx, [rsp+88h+var_30]
0x180017388  lea     rcx, [rsp+88h+pExceptionObject]
0x18001738d  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x180017392  nop     dword ptr [rax+00h]
0x180017396  nop     word ptr [rax+rax+00000000h]
0x1800173a0  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800173a7  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800173ac  call    _CxxThrowException
0x1800173b2  jmp     short $+2
0x1800173b4  nop
0x1800173b5  xor     edx, edx; struct CrashContext *
0x1800173b7  mov     ecx, 1E3C3840h; unsigned int
0x1800173bc  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800173c2  jmp     short $+2
0x1800173c4  nop
0x1800173c5  lea     rdx, aStructuredtrac_7; "StructuredTraceJsonSerializer::Visit fa"...
0x1800173cc  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800173d1  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800173d6  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800173dd  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800173e2  call    _CxxThrowException
```
