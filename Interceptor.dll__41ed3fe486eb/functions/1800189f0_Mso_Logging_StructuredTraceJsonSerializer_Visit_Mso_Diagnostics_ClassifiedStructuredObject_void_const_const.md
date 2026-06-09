# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<void const *> const &)

- ea: `0x1800189f0`
- end: `0x180018b20`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@PEBX@Diagnostics@3@@Z`
- size: `304`
- prototype: `__int64 __fastcall(Mso::Logging::StructuredTraceJsonSerializer *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x1800189f0`
- `0x18001a364`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180018a3f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180018a3f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180018ab4`

## string_xrefs

- `0x180018afd`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x180018abb`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF

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
  if ( !Mso::Logging::StructuredTraceJsonSerializer::WriteJson(this, (const void *const *)(a2 + 16)) )
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
0x1800189f0  mov     [rsp+arg_0], rbx
0x1800189f5  mov     [rsp+arg_10], rbp
0x1800189fa  push    rsi
0x1800189fb  push    rdi
0x1800189fc  push    r14
0x1800189fe  sub     rsp, 40h
0x180018a02  mov     rdi, rdx
0x180018a05  mov     rbp, rcx
0x180018a08  mov     r8, [rdx+8]
0x180018a0c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180018a10  test    r8, r8
0x180018a13  jz      short loc_180018A24
0x180018a15  mov     rax, r9
0x180018a18  inc     rax
0x180018a1b  cmp     byte ptr [rax+r8], 0
0x180018a20  jnz     short loc_180018A18
0x180018a22  jmp     short loc_180018A26
0x180018a24  xor     eax, eax
0x180018a26  lea     r14d, [rax+1]
0x180018a2a  movsxd  rcx, r14d
0x180018a2d  mov     eax, 2
0x180018a32  mul     rcx
0x180018a35  mov     rsi, rax
0x180018a38  cmovb   rsi, r9
0x180018a3c  mov     rcx, rsi; Size
0x180018a3f  call    cs:__imp_malloc
0x180018a45  mov     rbx, rax
0x180018a48  test    rax, rax
0x180018a4b  jz      loc_180018AE1
0x180018a51  mov     r8, rsi; Size
0x180018a54  xor     edx, edx; Val
0x180018a56  mov     rcx, rax; void *
0x180018a59  call    memset
0x180018a5e  mov     [rsp+58h+arg_8], rbx
0x180018a63  mov     r8d, r14d; int
0x180018a66  mov     rdx, rbx; wchar_t *
0x180018a69  mov     rcx, [rdi+8]; char *
0x180018a6d  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x180018a72  mov     rcx, [rbp+8]
0x180018a76  test    rcx, rcx
0x180018a79  jz      short loc_180018AED
0x180018a7b  mov     rax, [rcx]
0x180018a7e  mov     rdx, rbx
0x180018a81  mov     rax, [rax+30h]
0x180018a85  call    cs:__guard_dispatch_icall_fptr
0x180018a8b  test    al, al
0x180018a8d  jz      short loc_180018AFD
0x180018a8f  lea     rdx, [rdi+10h]; void **
0x180018a93  mov     rcx, rbp; this
0x180018a96  call    ?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBQEBX@Z; Mso::Logging::StructuredTraceJsonSerializer::WriteJson(void const * const &)
0x180018a9b  test    al, al
0x180018a9d  jz      short loc_180018ABB
0x180018a9f  mov     rcx, rbx
0x180018aa2  mov     rbx, [rsp+58h+arg_0]
0x180018aa7  mov     rbp, [rsp+58h+arg_10]
0x180018aac  add     rsp, 40h
0x180018ab0  pop     r14
0x180018ab2  pop     rdi
0x180018ab3  pop     rsi
0x180018ab4  jmp     cs:__imp_free
0x180018abb  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x180018ac2  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018ac7  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018acc  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018ad3  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018ad8  call    _CxxThrowException
0x180018ade  jmp     short $+2
0x180018ae0  nop
0x180018ae1  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180018ae7  jmp     short loc_180018AEC
0x180018aec  nop
0x180018aed  xor     edx, edx; struct CrashContext *
0x180018aef  mov     ecx, 1E3C3840h; unsigned int
0x180018af4  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180018afa  jmp     short $+2
0x180018afc  nop
0x180018afd  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x180018b04  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018b09  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018b0e  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018b15  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018b1a  call    _CxxThrowException
```
