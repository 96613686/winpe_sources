# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Logging::StructuredObject<__int64,1> const &)

- ea: `0x1800170e0`
- end: `0x1800171ec`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$StructuredObject@_J$00@23@@Z`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000a434`
- `0x18000a580`
- `0x180012318`
- `0x180016658`
- `0x1800170e0`
- `0x180019f74`
- `0x1800266e0`
- `0x1800282a0`
- `0x18002b3c0`

## string_xrefs

- `0x1800171b9`: `StructuredTraceJsonSerializer::Visit failed to write structured value's name.`

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
  result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 72LL))(v5, *(_QWORD *)(a2 + 16));
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
0x1800170e0  mov     [rsp+arg_10], rbx
0x1800170e5  push    rdi
0x1800170e6  sub     rsp, 80h
0x1800170ed  mov     rax, cs:__security_cookie
0x1800170f4  xor     rax, rsp
0x1800170f7  mov     [rsp+88h+var_10], rax
0x1800170fc  mov     rdi, rdx
0x1800170ff  mov     rbx, rcx
0x180017102  mov     rcx, [rcx+8]
0x180017106  test    rcx, rcx
0x180017109  jz      loc_1800171A9
0x18001710f  mov     rax, [rcx]
0x180017112  mov     rdx, [rdx+8]
0x180017116  mov     rax, [rax+30h]
0x18001711a  call    cs:__guard_dispatch_icall_fptr
0x180017120  test    al, al
0x180017122  jz      loc_1800171B9
0x180017128  mov     rcx, [rbx+8]
0x18001712c  test    rcx, rcx
0x18001712f  jz      loc_1800171DF
0x180017135  mov     rax, [rcx]
0x180017138  mov     rdx, [rdi+10h]
0x18001713c  mov     rax, [rax+48h]
0x180017140  call    cs:__guard_dispatch_icall_fptr
0x180017146  test    al, al
0x180017148  jz      short loc_180017168
0x18001714a  mov     rcx, [rsp+88h+var_10]
0x18001714f  xor     rcx, rsp; StackCookie
0x180017152  call    __security_check_cookie
0x180017157  mov     rbx, [rsp+88h+arg_10]
0x18001715f  add     rsp, 80h
0x180017166  pop     rdi
0x180017167  retn
0x180017168  mov     rdx, [rdi+8]
0x18001716c  lea     rcx, [rsp+88h+var_50]
0x180017171  call    ?StringFromWz@DoNotUse@StringCore@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; Mso::StringCore::DoNotUse::StringFromWz(wchar_t const *,unsigned __int64)
0x180017176  lea     r8, [rsp+88h+var_50]
0x18001717b  lea     rcx, [rsp+88h+var_30]; void *
0x180017180  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x180017185  lea     rdx, [rsp+88h+var_30]
0x18001718a  lea     rcx, [rsp+88h+pExceptionObject]
0x18001718f  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x180017194  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001719b  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800171a0  call    _CxxThrowException
0x1800171a6  jmp     short $+2
0x1800171a8  nop
0x1800171a9  xor     edx, edx; struct CrashContext *
0x1800171ab  mov     ecx, 1E3C3840h; unsigned int
0x1800171b0  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800171b6  jmp     short $+2
0x1800171b8  nop
0x1800171b9  lea     rdx, aStructuredtrac_7; "StructuredTraceJsonSerializer::Visit fa"...
0x1800171c0  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800171c5  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800171ca  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800171d1  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800171d6  call    _CxxThrowException
0x1800171dc  jmp     short $+2
0x1800171de  nop
0x1800171df  xor     edx, edx; struct CrashContext *
0x1800171e1  mov     ecx, 1E3C3840h; unsigned int
0x1800171e6  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
