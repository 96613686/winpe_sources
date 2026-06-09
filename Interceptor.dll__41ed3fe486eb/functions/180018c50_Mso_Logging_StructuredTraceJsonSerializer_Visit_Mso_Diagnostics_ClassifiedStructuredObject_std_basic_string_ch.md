# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<std::basic_string<char,std::char_traits<char>,std::allocator<char>>> const &)

- ea: `0x180018c50`
- end: `0x180018d9c`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Diagnostics@3@@Z`
- size: `332`
- prototype: `__int64 __fastcall(Mso::Logging::StructuredTraceJsonSerializer *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x180018c50`
- `0x18001a530`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180018c9f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180018c9f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180018d30`

## string_xrefs

- `0x180018d79`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x180018d37`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Mso::Logging::StructuredTraceJsonSerializer::Visit(
        Mso::Logging::StructuredTraceJsonSerializer *this,
        __int64 a2)
{
  __int64 v4; // r8
  __int64 v5; // rax
  int v6; // r14d
  size_t v7; // rsi
  wchar_t *v8; // rax
  wchar_t *v9; // rbx
  __int64 v10; // rcx
  char *v11; // rax
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF
  char *v13; // [rsp+68h] [rbp+10h] BYREF
  wchar_t *v14; // [rsp+70h] [rbp+18h]

  v4 = *(_QWORD *)(a2 + 8);
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
  v14 = v9;
  MsoSzToWzSimple(*(const char **)(a2 + 8), v9, v6);
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
  v11 = (char *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 40) > 0xFu )
    v11 = *(char **)v11;
  v13 = v11;
  if ( !Mso::Logging::StructuredTraceJsonSerializer::WriteJson(this, (const char *const *)&v13) )
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
0x180018c50  mov     [rsp+arg_0], rbx
0x180018c55  mov     [rsp+arg_18], rbp
0x180018c5a  push    rsi
0x180018c5b  push    rdi
0x180018c5c  push    r14
0x180018c5e  sub     rsp, 40h
0x180018c62  mov     rdi, rdx
0x180018c65  mov     rbp, rcx
0x180018c68  mov     r8, [rdx+8]
0x180018c6c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180018c70  test    r8, r8
0x180018c73  jz      short loc_180018C84
0x180018c75  mov     rax, r9
0x180018c78  inc     rax
0x180018c7b  cmp     byte ptr [rax+r8], 0
0x180018c80  jnz     short loc_180018C78
0x180018c82  jmp     short loc_180018C86
0x180018c84  xor     eax, eax
0x180018c86  lea     r14d, [rax+1]
0x180018c8a  movsxd  rcx, r14d
0x180018c8d  mov     eax, 2
0x180018c92  mul     rcx
0x180018c95  mov     rsi, rax
0x180018c98  cmovb   rsi, r9
0x180018c9c  mov     rcx, rsi; Size
0x180018c9f  call    cs:__imp_malloc
0x180018ca5  mov     rbx, rax
0x180018ca8  test    rax, rax
0x180018cab  jz      loc_180018D5D
0x180018cb1  mov     r8, rsi; Size
0x180018cb4  xor     edx, edx; Val
0x180018cb6  mov     rcx, rax; void *
0x180018cb9  call    memset
0x180018cbe  mov     [rsp+58h+arg_10], rbx
0x180018cc3  mov     r8d, r14d; int
0x180018cc6  mov     rdx, rbx; wchar_t *
0x180018cc9  mov     rcx, [rdi+8]; char *
0x180018ccd  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x180018cd2  mov     rcx, [rbp+8]
0x180018cd6  test    rcx, rcx
0x180018cd9  jz      loc_180018D69
0x180018cdf  mov     rax, [rcx]
0x180018ce2  mov     rdx, rbx
0x180018ce5  mov     rax, [rax+30h]
0x180018ce9  call    cs:__guard_dispatch_icall_fptr
0x180018cef  test    al, al
0x180018cf1  jz      loc_180018D79
0x180018cf7  lea     rax, [rdi+10h]
0x180018cfb  cmp     qword ptr [rax+18h], 0Fh
0x180018d00  jbe     short loc_180018D05
0x180018d02  mov     rax, [rax]
0x180018d05  mov     [rsp+58h+arg_8], rax
0x180018d0a  lea     rdx, [rsp+58h+arg_8]; char **
0x180018d0f  mov     rcx, rbp; this
0x180018d12  call    ?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBQEBD@Z; Mso::Logging::StructuredTraceJsonSerializer::WriteJson(char const * const &)
0x180018d17  test    al, al
0x180018d19  jz      short loc_180018D37
0x180018d1b  mov     rcx, rbx
0x180018d1e  mov     rbx, [rsp+58h+arg_0]
0x180018d23  mov     rbp, [rsp+58h+arg_18]
0x180018d28  add     rsp, 40h
0x180018d2c  pop     r14
0x180018d2e  pop     rdi
0x180018d2f  pop     rsi
0x180018d30  jmp     cs:__imp_free
0x180018d37  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x180018d3e  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018d43  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018d48  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018d4f  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018d54  call    _CxxThrowException
0x180018d5a  jmp     short $+2
0x180018d5c  nop
0x180018d5d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180018d63  jmp     short loc_180018D68
0x180018d68  nop
0x180018d69  xor     edx, edx; struct CrashContext *
0x180018d6b  mov     ecx, 1E3C3840h; unsigned int
0x180018d70  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180018d76  jmp     short $+2
0x180018d78  nop
0x180018d79  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x180018d80  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018d85  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018d8a  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018d91  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018d96  call    _CxxThrowException
```
