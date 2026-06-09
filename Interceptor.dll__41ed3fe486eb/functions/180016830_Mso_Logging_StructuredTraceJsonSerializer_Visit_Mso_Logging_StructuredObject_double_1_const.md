# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Logging::StructuredObject<double,1> const &)

- ea: `0x180016830`
- end: `0x180016946`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$StructuredObject@N$00@23@@Z`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000a434`
- `0x18000a580`
- `0x180012318`
- `0x180016658`
- `0x180016830`
- `0x180019f74`
- `0x1800266e0`
- `0x1800282a0`
- `0x18002b3c0`

## string_xrefs

- `0x180016911`: `StructuredTraceJsonSerializer::Visit failed to write structured value's name.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Mso::Logging::StructuredTraceJsonSerializer::Visit(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 result; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v9[32]; // [rsp+58h] [rbp-30h] BYREF

  v4 = *(_QWORD *)(a1 + 8);
  if ( !v4 )
    CrashWithRecovery(0x1E3C3840u, 0);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 48LL))(v4, *(_QWORD *)(a2 + 8)) )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject,
      "StructuredTraceJsonSerializer::Visit failed to write structured value's name.");
    throw (std::runtime_error *)pExceptionObject;
  }
  v5 = *(_QWORD *)(a1 + 8);
  if ( !v5 )
    CrashWithRecovery(0x1E3C3840u, 0);
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 88LL))(v5);
  if ( !(_BYTE)result )
  {
    Mso::StringCore::DoNotUse::StringFromWz(v8, *(_QWORD *)(a2 + 8));
    std::operator+<char>(v9);
    std::runtime_error::runtime_error(pExceptionObject, v9);
    throw (std::runtime_error *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180016830  mov     [rsp+arg_10], rbx
0x180016835  push    rdi
0x180016836  sub     rsp, 80h
0x18001683d  mov     rax, cs:__security_cookie
0x180016844  xor     rax, rsp
0x180016847  mov     [rsp+88h+var_10], rax
0x18001684c  mov     rdi, rdx
0x18001684f  mov     rbx, rcx
0x180016852  mov     rcx, [rcx+8]
0x180016856  test    rcx, rcx
0x180016859  jz      loc_180016901
0x18001685f  mov     rax, [rcx]
0x180016862  mov     rdx, [rdx+8]
0x180016866  mov     rax, [rax+30h]
0x18001686a  call    cs:__guard_dispatch_icall_fptr
0x180016870  test    al, al
0x180016872  jz      loc_180016911
0x180016878  mov     rcx, [rbx+8]
0x18001687c  test    rcx, rcx
0x18001687f  jz      loc_180016939
0x180016885  mov     rax, [rcx]
0x180016888  movsd   xmm1, qword ptr [rdi+10h]
0x18001688d  mov     rax, [rax+58h]
0x180016891  call    cs:__guard_dispatch_icall_fptr
0x180016897  test    al, al
0x180016899  jz      short loc_1800168B9
0x18001689b  mov     rcx, [rsp+88h+var_10]
0x1800168a0  xor     rcx, rsp; StackCookie
0x1800168a3  call    __security_check_cookie
0x1800168a8  mov     rbx, [rsp+88h+arg_10]
0x1800168b0  add     rsp, 80h
0x1800168b7  pop     rdi
0x1800168b8  retn
0x1800168b9  mov     rdx, [rdi+8]
0x1800168bd  lea     rcx, [rsp+88h+var_50]
0x1800168c2  call    ?StringFromWz@DoNotUse@StringCore@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; Mso::StringCore::DoNotUse::StringFromWz(wchar_t const *,unsigned __int64)
0x1800168c7  lea     r8, [rsp+88h+var_50]
0x1800168cc  lea     rcx, [rsp+88h+var_30]; void *
0x1800168d1  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x1800168d6  lea     rdx, [rsp+88h+var_30]
0x1800168db  lea     rcx, [rsp+88h+pExceptionObject]
0x1800168e0  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x1800168e5  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800168ec  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800168f1  call    _CxxThrowException
0x180016901  xor     edx, edx; struct CrashContext *
0x180016903  mov     ecx, 1E3C3840h; unsigned int
0x180016908  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18001690e  jmp     short $+2
0x180016910  nop
0x180016911  lea     rdx, aStructuredtrac_7; "StructuredTraceJsonSerializer::Visit fa"...
0x180016918  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18001691d  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180016922  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180016929  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18001692e  call    _CxxThrowException
0x180016934  jmp     short loc_180016938
0x180016938  nop
0x180016939  xor     edx, edx; struct CrashContext *
0x18001693b  mov     ecx, 1E3C3840h; unsigned int
0x180016940  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
