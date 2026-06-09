# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Logging::StructuredObject<bool,1> const &)

- ea: `0x180016720`
- end: `0x18001682c`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$StructuredObject@_N$00@23@@Z`
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
- `0x180016720`
- `0x180019f74`
- `0x1800266e0`
- `0x1800282a0`
- `0x18002b3c0`

## string_xrefs

- `0x1800167f9`: `StructuredTraceJsonSerializer::Visit failed to write structured value's name.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Mso::Logging::StructuredTraceJsonSerializer::Visit(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 result; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v10[32]; // [rsp+58h] [rbp-30h] BYREF

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
  v6 = *(_QWORD *)(a1 + 8);
  if ( !v6 )
    CrashWithRecovery(0x1E3C3840u, 0);
  LOBYTE(v5) = *(_BYTE *)(a2 + 16);
  result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 64LL))(v6, v5);
  if ( !(_BYTE)result )
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
0x180016720  mov     [rsp+arg_10], rbx
0x180016725  push    rdi
0x180016726  sub     rsp, 80h
0x18001672d  mov     rax, cs:__security_cookie
0x180016734  xor     rax, rsp
0x180016737  mov     [rsp+88h+var_10], rax
0x18001673c  mov     rdi, rdx
0x18001673f  mov     rbx, rcx
0x180016742  mov     rcx, [rcx+8]
0x180016746  test    rcx, rcx
0x180016749  jz      loc_1800167E9
0x18001674f  mov     rax, [rcx]
0x180016752  mov     rdx, [rdx+8]
0x180016756  mov     rax, [rax+30h]
0x18001675a  call    cs:__guard_dispatch_icall_fptr
0x180016760  test    al, al
0x180016762  jz      loc_1800167F9
0x180016768  mov     rcx, [rbx+8]
0x18001676c  test    rcx, rcx
0x18001676f  jz      loc_18001681F
0x180016775  mov     rax, [rcx]
0x180016778  mov     dl, [rdi+10h]
0x18001677b  mov     rax, [rax+40h]
0x18001677f  call    cs:__guard_dispatch_icall_fptr
0x180016785  test    al, al
0x180016787  jz      short loc_1800167A7
0x180016789  mov     rcx, [rsp+88h+var_10]
0x18001678e  xor     rcx, rsp; StackCookie
0x180016791  call    __security_check_cookie
0x180016796  mov     rbx, [rsp+88h+arg_10]
0x18001679e  add     rsp, 80h
0x1800167a5  pop     rdi
0x1800167a6  retn
0x1800167a7  mov     rdx, [rdi+8]
0x1800167ab  lea     rcx, [rsp+88h+var_50]
0x1800167b0  call    ?StringFromWz@DoNotUse@StringCore@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; Mso::StringCore::DoNotUse::StringFromWz(wchar_t const *,unsigned __int64)
0x1800167b5  lea     r8, [rsp+88h+var_50]
0x1800167ba  lea     rcx, [rsp+88h+var_30]; void *
0x1800167bf  nop
0x1800167c0  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x1800167c5  lea     rdx, [rsp+88h+var_30]
0x1800167ca  lea     rcx, [rsp+88h+pExceptionObject]
0x1800167cf  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x1800167d4  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800167db  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800167e0  call    _CxxThrowException
0x1800167e6  jmp     short $+2
0x1800167e8  nop
0x1800167e9  xor     edx, edx; struct CrashContext *
0x1800167eb  mov     ecx, 1E3C3840h; unsigned int
0x1800167f0  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800167f6  jmp     short $+2
0x1800167f8  nop
0x1800167f9  lea     rdx, aStructuredtrac_7; "StructuredTraceJsonSerializer::Visit fa"...
0x180016800  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180016805  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001680a  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180016811  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180016816  call    _CxxThrowException
0x18001681c  jmp     short $+2
0x18001681e  nop
0x18001681f  xor     edx, edx; struct CrashContext *
0x180016821  mov     ecx, 1E3C3840h; unsigned int
0x180016826  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
