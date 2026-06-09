# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<_FILETIME> const &)

- ea: `0x180017f10`
- end: `0x180018040`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@U_FILETIME@@@Diagnostics@3@@Z`
- size: `304`
- prototype: `__int64 __fastcall(Mso::Logging::StructuredTraceJsonSerializer *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x180017f10`
- `0x18001a170`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180017f5f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180017f5f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180017fd4`

## string_xrefs

- `0x18001801d`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x180017fdb`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  if ( !Mso::Logging::StructuredTraceJsonSerializer::WriteJson(this, (FILETIME *)(a2 + 16)) )
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
0x180017f10  mov     [rsp+arg_0], rbx
0x180017f15  mov     [rsp+arg_10], rbp
0x180017f1a  push    rsi
0x180017f1b  push    rdi
0x180017f1c  push    r14
0x180017f1e  sub     rsp, 40h
0x180017f22  mov     rdi, rdx
0x180017f25  mov     rbp, rcx
0x180017f28  mov     r8, [rdx+8]
0x180017f2c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180017f30  test    r8, r8
0x180017f33  jz      short loc_180017F44
0x180017f35  mov     rax, r9
0x180017f38  inc     rax
0x180017f3b  cmp     byte ptr [rax+r8], 0
0x180017f40  jnz     short loc_180017F38
0x180017f42  jmp     short loc_180017F46
0x180017f44  xor     eax, eax
0x180017f46  lea     r14d, [rax+1]
0x180017f4a  movsxd  rcx, r14d
0x180017f4d  mov     eax, 2
0x180017f52  mul     rcx
0x180017f55  mov     rsi, rax
0x180017f58  cmovb   rsi, r9
0x180017f5c  mov     rcx, rsi; Size
0x180017f5f  call    cs:__imp_malloc
0x180017f65  mov     rbx, rax
0x180017f68  test    rax, rax
0x180017f6b  jz      loc_180018001
0x180017f71  mov     r8, rsi; Size
0x180017f74  xor     edx, edx; Val
0x180017f76  mov     rcx, rax; void *
0x180017f79  call    memset
0x180017f7e  mov     [rsp+58h+arg_8], rbx
0x180017f83  mov     r8d, r14d; int
0x180017f86  mov     rdx, rbx; wchar_t *
0x180017f89  mov     rcx, [rdi+8]; char *
0x180017f8d  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x180017f92  mov     rcx, [rbp+8]
0x180017f96  test    rcx, rcx
0x180017f99  jz      short loc_18001800D
0x180017f9b  mov     rax, [rcx]
0x180017f9e  mov     rdx, rbx
0x180017fa1  mov     rax, [rax+30h]
0x180017fa5  call    cs:__guard_dispatch_icall_fptr
0x180017fab  test    al, al
0x180017fad  jz      short loc_18001801D
0x180017faf  lea     rdx, [rdi+10h]; lpFileTime
0x180017fb3  mov     rcx, rbp; this
0x180017fb6  call    ?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBU_FILETIME@@@Z; Mso::Logging::StructuredTraceJsonSerializer::WriteJson(_FILETIME const &)
0x180017fbb  test    al, al
0x180017fbd  jz      short loc_180017FDB
0x180017fbf  mov     rcx, rbx
0x180017fc2  mov     rbx, [rsp+58h+arg_0]
0x180017fc7  mov     rbp, [rsp+58h+arg_10]
0x180017fcc  add     rsp, 40h
0x180017fd0  pop     r14
0x180017fd2  pop     rdi
0x180017fd3  pop     rsi
0x180017fd4  jmp     cs:__imp_free
0x180017fdb  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x180017fe2  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180017fe7  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180017fec  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180017ff3  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180017ff8  call    _CxxThrowException
0x180017ffe  jmp     short $+2
0x180018000  nop
0x180018001  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180018007  jmp     short loc_18001800C
0x18001800c  nop
0x18001800d  xor     edx, edx; struct CrashContext *
0x18001800f  mov     ecx, 1E3C3840h; unsigned int
0x180018014  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18001801a  jmp     short $+2
0x18001801c  nop
0x18001801d  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x180018024  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018029  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001802e  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018035  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001803a  call    _CxxThrowException
```
