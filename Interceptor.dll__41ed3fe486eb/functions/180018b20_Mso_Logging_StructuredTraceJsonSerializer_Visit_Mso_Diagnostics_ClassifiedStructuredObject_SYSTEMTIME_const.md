# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<_SYSTEMTIME> const &)

- ea: `0x180018b20`
- end: `0x180018c50`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@U_SYSTEMTIME@@@Diagnostics@3@@Z`
- size: `304`
- prototype: `__int64 __fastcall(Mso::Logging::StructuredTraceJsonSerializer *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x180018b20`
- `0x18001a3e0`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180018b6f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180018b6f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180018be4`

## string_xrefs

- `0x180018c2d`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x180018beb`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  if ( !Mso::Logging::StructuredTraceJsonSerializer::WriteJson(this, (const struct _SYSTEMTIME *)(a2 + 16)) )
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
0x180018b20  mov     [rsp+arg_0], rbx
0x180018b25  mov     [rsp+arg_10], rbp
0x180018b2a  push    rsi
0x180018b2b  push    rdi
0x180018b2c  push    r14
0x180018b2e  sub     rsp, 40h
0x180018b32  mov     rdi, rdx
0x180018b35  mov     rbp, rcx
0x180018b38  mov     r8, [rdx+8]
0x180018b3c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180018b40  test    r8, r8
0x180018b43  jz      short loc_180018B54
0x180018b45  mov     rax, r9
0x180018b48  inc     rax
0x180018b4b  cmp     byte ptr [rax+r8], 0
0x180018b50  jnz     short loc_180018B48
0x180018b52  jmp     short loc_180018B56
0x180018b54  xor     eax, eax
0x180018b56  lea     r14d, [rax+1]
0x180018b5a  movsxd  rcx, r14d
0x180018b5d  mov     eax, 2
0x180018b62  mul     rcx
0x180018b65  mov     rsi, rax
0x180018b68  cmovb   rsi, r9
0x180018b6c  mov     rcx, rsi; Size
0x180018b6f  call    cs:__imp_malloc
0x180018b75  mov     rbx, rax
0x180018b78  test    rax, rax
0x180018b7b  jz      loc_180018C11
0x180018b81  mov     r8, rsi; Size
0x180018b84  xor     edx, edx; Val
0x180018b86  mov     rcx, rax; void *
0x180018b89  call    memset
0x180018b8e  mov     [rsp+58h+arg_8], rbx
0x180018b93  mov     r8d, r14d; int
0x180018b96  mov     rdx, rbx; wchar_t *
0x180018b99  mov     rcx, [rdi+8]; char *
0x180018b9d  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x180018ba2  mov     rcx, [rbp+8]
0x180018ba6  test    rcx, rcx
0x180018ba9  jz      short loc_180018C1D
0x180018bab  mov     rax, [rcx]
0x180018bae  mov     rdx, rbx
0x180018bb1  mov     rax, [rax+30h]
0x180018bb5  call    cs:__guard_dispatch_icall_fptr
0x180018bbb  test    al, al
0x180018bbd  jz      short loc_180018C2D
0x180018bbf  lea     rdx, [rdi+10h]; struct _SYSTEMTIME *
0x180018bc3  mov     rcx, rbp; this
0x180018bc6  call    ?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBU_SYSTEMTIME@@@Z; Mso::Logging::StructuredTraceJsonSerializer::WriteJson(_SYSTEMTIME const &)
0x180018bcb  test    al, al
0x180018bcd  jz      short loc_180018BEB
0x180018bcf  mov     rcx, rbx
0x180018bd2  mov     rbx, [rsp+58h+arg_0]
0x180018bd7  mov     rbp, [rsp+58h+arg_10]
0x180018bdc  add     rsp, 40h
0x180018be0  pop     r14
0x180018be2  pop     rdi
0x180018be3  pop     rsi
0x180018be4  jmp     cs:__imp_free
0x180018beb  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x180018bf2  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018bf7  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018bfc  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018c03  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018c08  call    _CxxThrowException
0x180018c0e  jmp     short $+2
0x180018c10  nop
0x180018c11  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180018c17  jmp     short loc_180018C1C
0x180018c1c  nop
0x180018c1d  xor     edx, edx; struct CrashContext *
0x180018c1f  mov     ecx, 1E3C3840h; unsigned int
0x180018c24  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180018c2a  jmp     short $+2
0x180018c2c  nop
0x180018c2d  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x180018c34  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018c39  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018c3e  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018c45  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018c4a  call    _CxxThrowException
```
