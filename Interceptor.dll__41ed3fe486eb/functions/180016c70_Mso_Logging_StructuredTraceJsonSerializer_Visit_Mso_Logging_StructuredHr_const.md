# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Logging::StructuredHr const &)

- ea: `0x180016c70`
- end: `0x180016d8c`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBUStructuredHr@23@@Z`
- size: `284`
- prototype: `void __fastcall(Mso::Logging::StructuredTraceJsonSerializer *__hidden this, const struct Mso::Logging::StructuredHr *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x18000a010`
- `0x18000a580`
- `0x180012318`
- `0x180016c70`
- `0x1800266e0`
- `0x1800282a0`
- `0x18002b3c0`

## string_xrefs

- `0x180016d59`: `StructuredTraceJsonSerializer::Visit failed to write structured value's name.`
- `0x180016d22`: `StructuredTraceJsonSerializer::Visit failed to write structured value.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Mso::Logging::StructuredTraceJsonSerializer::Visit(
        Mso::Logging::StructuredTraceJsonSerializer *this,
        const struct Mso::Logging::StructuredHr *a2)
{
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rcx
  int v7; // [rsp+20h] [rbp-58h]
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-48h] BYREF
  wchar_t Buffer[16]; // [rsp+48h] [rbp-30h] BYREF

  v4 = *((_QWORD *)this + 1);
  if ( !v4 )
    CrashWithRecovery(0x1E3C3840u, 0);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 48LL))(v4, *((_QWORD *)a2 + 1)) )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject,
      "StructuredTraceJsonSerializer::Visit failed to write structured value's name.");
    throw (std::runtime_error *)pExceptionObject;
  }
  v5 = *((_DWORD *)a2 + 4);
  Buffer[0] = 0;
  v7 = v5;
  snwprintf_s(Buffer, 0x10u, 0xFFFFFFFFFFFFFFFFuLL, L"0x%08x", v7);
  v6 = *((_QWORD *)this + 1);
  if ( !v6 )
    CrashWithRecovery(0x1E3C3840u, 0);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, wchar_t *))(*(_QWORD *)v6 + 56LL))(v6, Buffer) )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject,
      "StructuredTraceJsonSerializer::Visit failed to write structured value.");
    throw (std::runtime_error *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180016c70  mov     [rsp+arg_10], rbx
0x180016c75  mov     [rsp+arg_18], rsi
0x180016c7a  push    rdi
0x180016c7b  sub     rsp, 70h
0x180016c7f  mov     rax, cs:__security_cookie
0x180016c86  xor     rax, rsp
0x180016c89  mov     [rsp+78h+var_10], rax
0x180016c8e  mov     rdi, rdx
0x180016c91  mov     rbx, rcx
0x180016c94  mov     rcx, [rcx+8]
0x180016c98  xor     esi, esi
0x180016c9a  test    rcx, rcx
0x180016c9d  jz      loc_180016D48
0x180016ca3  mov     rax, [rcx]
0x180016ca6  mov     rdx, [rdx+8]
0x180016caa  mov     rax, [rax+30h]
0x180016cae  call    cs:__guard_dispatch_icall_fptr
0x180016cb4  test    al, al
0x180016cb6  jz      loc_180016D59
0x180016cbc  mov     eax, [rdi+10h]
0x180016cbf  mov     [rsp+78h+Buffer], si
0x180016cc4  mov     [rsp+78h+var_58], eax
0x180016cc8  lea     r9, a0x08x; "0x%08x"
0x180016ccf  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180016cd3  lea     edx, [rsi+10h]; BufferCount
0x180016cd6  lea     rcx, [rsp+78h+Buffer]; Buffer
0x180016cdb  call    _snwprintf_s
0x180016ce0  mov     rcx, [rbx+8]
0x180016ce4  test    rcx, rcx
0x180016ce7  jz      loc_180016D7F
0x180016ced  mov     rax, [rcx]
0x180016cf0  lea     rdx, [rsp+78h+Buffer]
0x180016cf5  mov     rax, [rax+38h]
0x180016cf9  call    cs:__guard_dispatch_icall_fptr
0x180016cff  test    al, al
0x180016d01  jz      short loc_180016D22
0x180016d03  mov     rcx, [rsp+78h+var_10]
0x180016d08  xor     rcx, rsp; StackCookie
0x180016d0b  call    __security_check_cookie
0x180016d10  lea     r11, [rsp+78h+var_8]
0x180016d15  mov     rbx, [r11+20h]
0x180016d19  mov     rsi, [r11+28h]
0x180016d1d  mov     rsp, r11
0x180016d20  pop     rdi
0x180016d21  retn
0x180016d22  lea     rdx, aStructuredtrac_6; "StructuredTraceJsonSerializer::Visit fa"...
0x180016d29  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180016d2e  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180016d33  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180016d3a  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180016d3f  call    _CxxThrowException
0x180016d45  jmp     short $+2
0x180016d47  nop
0x180016d48  xor     edx, edx; struct CrashContext *
0x180016d4a  mov     ecx, 1E3C3840h; unsigned int
0x180016d4f  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180016d55  jmp     short loc_180016D58
0x180016d58  nop
0x180016d59  lea     rdx, aStructuredtrac_7; "StructuredTraceJsonSerializer::Visit fa"...
0x180016d60  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180016d65  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180016d6a  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180016d71  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180016d76  call    _CxxThrowException
0x180016d7c  jmp     short $+2
0x180016d7e  nop
0x180016d7f  xor     edx, edx; struct CrashContext *
0x180016d81  mov     ecx, 1E3C3840h; unsigned int
0x180016d86  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
