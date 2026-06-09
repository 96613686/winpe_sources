# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredHr const &)

- ea: `0x1800182d0`
- end: `0x18001846a`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBUClassifiedStructuredHr@Diagnostics@3@@Z`
- size: `410`
- prototype: `void __fastcall(Mso::Logging::StructuredTraceJsonSerializer *__hidden this, const struct Mso::Diagnostics::ClassifiedStructuredHr *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x18000a010`
- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x1800182d0`
- `0x18001e944`
- `0x1800266e0`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001832f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001832f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800183ce`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800183ce`

## string_xrefs

- `0x180018437`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x1800183f8`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Mso::Logging::StructuredTraceJsonSerializer::Visit(
        Mso::Logging::StructuredTraceJsonSerializer *this,
        const struct Mso::Diagnostics::ClassifiedStructuredHr *a2)
{
  __int64 v4; // r8
  __int64 v5; // rax
  int v6; // r14d
  size_t v7; // rdi
  wchar_t *v8; // rax
  wchar_t *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rcx
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-70h] BYREF
  wchar_t Buffer[16]; // [rsp+50h] [rbp-58h] BYREF

  v4 = *((_QWORD *)a2 + 1);
  if ( v4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_BYTE *)(v5 + v4) );
  }
  else
  {
    LODWORD(v5) = 0;
  }
  v6 = v5 + 1;
  v7 = saturated_mul((int)v5 + 1, 2u);
  v8 = (wchar_t *)malloc(v7);
  v9 = v8;
  if ( !v8 )
    std::_Xbad_alloc();
  memset(v8, 0, v7);
  MsoSzToWzSimple(*((const char **)a2 + 1), v9, v6);
  v10 = *((_QWORD *)this + 1);
  if ( !v10 )
    CrashWithRecovery(0x1E3C3840u, 0);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, wchar_t *))(*(_QWORD *)v10 + 48LL))(v10, v9) )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject,
      "StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.");
    throw (std::runtime_error *)pExceptionObject;
  }
  snwprintf_s(Buffer, 0x10u, 0xFFFFFFFFFFFFFFFFuLL, L"0x%08x", *((_DWORD *)a2 + 4));
  v11 = *((_QWORD *)this + 1);
  if ( !v11 )
    CrashWithRecovery(0x1E3C3840u, 0);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, wchar_t *))(*(_QWORD *)v11 + 56LL))(v11, Buffer) )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject,
      "StructuredTraceJsonSerializer::Visit failed to write classified structured value.");
    throw (std::runtime_error *)pExceptionObject;
  }
  free(v9);
}

```

## disassembly

```asm
0x1800182d0  mov     [rsp+arg_10], rbx
0x1800182d5  push    rbp
0x1800182d6  push    rsi
0x1800182d7  push    rdi
0x1800182d8  push    r14
0x1800182da  push    r15
0x1800182dc  sub     rsp, 80h
0x1800182e3  mov     rax, cs:__security_cookie
0x1800182ea  xor     rax, rsp
0x1800182ed  mov     [rsp+0A8h+var_38], rax
0x1800182f2  mov     rsi, rdx
0x1800182f5  mov     rbp, rcx
0x1800182f8  mov     r8, [rdx+8]
0x1800182fc  or      r15, 0FFFFFFFFFFFFFFFFh
0x180018300  test    r8, r8
0x180018303  jz      short loc_180018314
0x180018305  mov     rax, r15
0x180018308  inc     rax
0x18001830b  cmp     byte ptr [rax+r8], 0
0x180018310  jnz     short loc_180018308
0x180018312  jmp     short loc_180018316
0x180018314  xor     eax, eax
0x180018316  lea     r14d, [rax+1]
0x18001831a  movsxd  rcx, r14d
0x18001831d  mov     eax, 2
0x180018322  mul     rcx
0x180018325  mov     rdi, rax
0x180018328  cmovb   rdi, r15
0x18001832c  mov     rcx, rdi; Size
0x18001832f  call    cs:__imp_malloc
0x180018335  mov     rbx, rax
0x180018338  test    rax, rax
0x18001833b  jz      loc_18001841E
0x180018341  mov     r8, rdi; Size
0x180018344  xor     edx, edx; Val
0x180018346  mov     rcx, rax; void *
0x180018349  call    memset
0x18001834e  mov     [rsp+0A8h+var_78], rbx
0x180018353  mov     r8d, r14d; int
0x180018356  mov     rdx, rbx; wchar_t *
0x180018359  mov     rcx, [rsi+8]; char *
0x18001835d  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x180018362  mov     rcx, [rbp+8]
0x180018366  test    rcx, rcx
0x180018369  jz      loc_180018427
0x18001836f  nop
0x180018370  mov     rax, [rcx]
0x180018373  mov     rdx, rbx
0x180018376  mov     rax, [rax+30h]
0x18001837a  call    cs:__guard_dispatch_icall_fptr
0x180018380  test    al, al
0x180018382  jz      loc_180018437
0x180018388  mov     eax, [rsi+10h]
0x18001838b  mov     [rsp+0A8h+var_88], eax
0x18001838f  lea     r9, a0x08x; "0x%08x"
0x180018396  mov     r8, r15; MaxCount
0x180018399  mov     edx, 10h; BufferCount
0x18001839e  lea     rcx, [rsp+0A8h+Buffer]; Buffer
0x1800183a3  call    _snwprintf_s
0x1800183a8  mov     rcx, [rbp+8]
0x1800183ac  test    rcx, rcx
0x1800183af  jz      loc_18001845D
0x1800183b5  mov     rax, [rcx]
0x1800183b8  lea     rdx, [rsp+0A8h+Buffer]
0x1800183bd  mov     rax, [rax+38h]
0x1800183c1  call    cs:__guard_dispatch_icall_fptr
0x1800183c7  test    al, al
0x1800183c9  jz      short loc_1800183F8
0x1800183cb  mov     rcx, rbx; Block
0x1800183ce  call    cs:__imp_free
0x1800183d4  mov     rcx, [rsp+0A8h+var_38]
0x1800183d9  xor     rcx, rsp; StackCookie
0x1800183dc  call    __security_check_cookie
0x1800183e1  mov     rbx, [rsp+0A8h+arg_10]
0x1800183e9  add     rsp, 80h
0x1800183f0  pop     r15
0x1800183f2  pop     r14
0x1800183f4  pop     rdi
0x1800183f5  pop     rsi
0x1800183f6  pop     rbp
0x1800183f7  retn
0x1800183f8  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x1800183ff  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x180018404  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018409  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018410  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180018415  call    _CxxThrowException
0x18001841b  jmp     short $+2
0x18001841d  nop
0x18001841e  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180018424  jmp     short $+2
0x180018426  nop
0x180018427  xor     edx, edx; struct CrashContext *
0x180018429  mov     ecx, 1E3C3840h; unsigned int
0x18001842e  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180018434  jmp     short $+2
0x180018436  nop
0x180018437  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x18001843e  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x180018443  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018448  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001844f  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180018454  call    _CxxThrowException
0x18001845a  jmp     short $+2
0x18001845c  nop
0x18001845d  xor     edx, edx; struct CrashContext *
0x18001845f  mov     ecx, 1E3C3840h; unsigned int
0x180018464  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
