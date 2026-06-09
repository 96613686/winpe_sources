# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Logging::StructuredObject<float,1> const &)

- ea: `0x180016a50`
- end: `0x180016b66`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$StructuredObject@M$00@23@@Z`
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
- `0x180016a50`
- `0x180019f74`
- `0x1800266e0`
- `0x1800282a0`
- `0x18002b3c0`

## string_xrefs

- `0x180016b31`: `StructuredTraceJsonSerializer::Visit failed to write structured value's name.`

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
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 96LL))(v5);
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
0x180016a50  mov     [rsp+arg_10], rbx
0x180016a55  push    rdi
0x180016a56  sub     rsp, 80h
0x180016a5d  mov     rax, cs:__security_cookie
0x180016a64  xor     rax, rsp
0x180016a67  mov     [rsp+88h+var_10], rax
0x180016a6c  mov     rdi, rdx
0x180016a6f  mov     rbx, rcx
0x180016a72  mov     rcx, [rcx+8]
0x180016a76  test    rcx, rcx
0x180016a79  jz      loc_180016B21
0x180016a7f  mov     rax, [rcx]
0x180016a82  mov     rdx, [rdx+8]
0x180016a86  mov     rax, [rax+30h]
0x180016a8a  call    cs:__guard_dispatch_icall_fptr
0x180016a90  test    al, al
0x180016a92  jz      loc_180016B31
0x180016a98  mov     rcx, [rbx+8]
0x180016a9c  test    rcx, rcx
0x180016a9f  jz      loc_180016B59
0x180016aa5  mov     rax, [rcx]
0x180016aa8  movss   xmm1, dword ptr [rdi+10h]
0x180016aad  mov     rax, [rax+60h]
0x180016ab1  call    cs:__guard_dispatch_icall_fptr
0x180016ab7  test    al, al
0x180016ab9  jz      short loc_180016AD9
0x180016abb  mov     rcx, [rsp+88h+var_10]
0x180016ac0  xor     rcx, rsp; StackCookie
0x180016ac3  call    __security_check_cookie
0x180016ac8  mov     rbx, [rsp+88h+arg_10]
0x180016ad0  add     rsp, 80h
0x180016ad7  pop     rdi
0x180016ad8  retn
0x180016ad9  mov     rdx, [rdi+8]
0x180016add  lea     rcx, [rsp+88h+var_50]
0x180016ae2  call    ?StringFromWz@DoNotUse@StringCore@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; Mso::StringCore::DoNotUse::StringFromWz(wchar_t const *,unsigned __int64)
0x180016ae7  lea     r8, [rsp+88h+var_50]
0x180016aec  lea     rcx, [rsp+88h+var_30]; void *
0x180016af1  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x180016af6  lea     rdx, [rsp+88h+var_30]
0x180016afb  lea     rcx, [rsp+88h+pExceptionObject]
0x180016b00  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x180016b05  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180016b0c  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180016b11  call    _CxxThrowException
0x180016b21  xor     edx, edx; struct CrashContext *
0x180016b23  mov     ecx, 1E3C3840h; unsigned int
0x180016b28  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180016b2e  jmp     short $+2
0x180016b30  nop
0x180016b31  lea     rdx, aStructuredtrac_7; "StructuredTraceJsonSerializer::Visit fa"...
0x180016b38  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180016b3d  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180016b42  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180016b49  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180016b4e  call    _CxxThrowException
0x180016b54  jmp     short loc_180016B58
0x180016b58  nop
0x180016b59  xor     edx, edx; struct CrashContext *
0x180016b5b  mov     ecx, 1E3C3840h; unsigned int
0x180016b60  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
