# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<char const *> const &)

- ea: `0x180018da0`
- end: `0x180018ed0`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@PEBD@Diagnostics@3@@Z`
- size: `304`
- prototype: `__int64 __fastcall(Mso::Logging::StructuredTraceJsonSerializer *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x180018da0`
- `0x18001a530`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180018def`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180018def`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180018e64`

## string_xrefs

- `0x180018ead`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x180018e6b`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  if ( !Mso::Logging::StructuredTraceJsonSerializer::WriteJson(this, (const char *const *)(a2 + 16)) )
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
0x180018da0  mov     [rsp+arg_0], rbx
0x180018da5  mov     [rsp+arg_10], rbp
0x180018daa  push    rsi
0x180018dab  push    rdi
0x180018dac  push    r14
0x180018dae  sub     rsp, 40h
0x180018db2  mov     rdi, rdx
0x180018db5  mov     rbp, rcx
0x180018db8  mov     r8, [rdx+8]
0x180018dbc  or      r9, 0FFFFFFFFFFFFFFFFh
0x180018dc0  test    r8, r8
0x180018dc3  jz      short loc_180018DD4
0x180018dc5  mov     rax, r9
0x180018dc8  inc     rax
0x180018dcb  cmp     byte ptr [rax+r8], 0
0x180018dd0  jnz     short loc_180018DC8
0x180018dd2  jmp     short loc_180018DD6
0x180018dd4  xor     eax, eax
0x180018dd6  lea     r14d, [rax+1]
0x180018dda  movsxd  rcx, r14d
0x180018ddd  mov     eax, 2
0x180018de2  mul     rcx
0x180018de5  mov     rsi, rax
0x180018de8  cmovb   rsi, r9
0x180018dec  mov     rcx, rsi; Size
0x180018def  call    cs:__imp_malloc
0x180018df5  mov     rbx, rax
0x180018df8  test    rax, rax
0x180018dfb  jz      loc_180018E91
0x180018e01  mov     r8, rsi; Size
0x180018e04  xor     edx, edx; Val
0x180018e06  mov     rcx, rax; void *
0x180018e09  call    memset
0x180018e0e  mov     [rsp+58h+arg_8], rbx
0x180018e13  mov     r8d, r14d; int
0x180018e16  mov     rdx, rbx; wchar_t *
0x180018e19  mov     rcx, [rdi+8]; char *
0x180018e1d  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x180018e22  mov     rcx, [rbp+8]
0x180018e26  test    rcx, rcx
0x180018e29  jz      short loc_180018E9D
0x180018e2b  mov     rax, [rcx]
0x180018e2e  mov     rdx, rbx
0x180018e31  mov     rax, [rax+30h]
0x180018e35  call    cs:__guard_dispatch_icall_fptr
0x180018e3b  test    al, al
0x180018e3d  jz      short loc_180018EAD
0x180018e3f  lea     rdx, [rdi+10h]; char **
0x180018e43  mov     rcx, rbp; this
0x180018e46  call    ?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBQEBD@Z; Mso::Logging::StructuredTraceJsonSerializer::WriteJson(char const * const &)
0x180018e4b  test    al, al
0x180018e4d  jz      short loc_180018E6B
0x180018e4f  mov     rcx, rbx
0x180018e52  mov     rbx, [rsp+58h+arg_0]
0x180018e57  mov     rbp, [rsp+58h+arg_10]
0x180018e5c  add     rsp, 40h
0x180018e60  pop     r14
0x180018e62  pop     rdi
0x180018e63  pop     rsi
0x180018e64  jmp     cs:__imp_free
0x180018e6b  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x180018e72  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018e77  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018e7c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018e83  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018e88  call    _CxxThrowException
0x180018e8e  jmp     short $+2
0x180018e90  nop
0x180018e91  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180018e97  jmp     short loc_180018E9C
0x180018e9c  nop
0x180018e9d  xor     edx, edx; struct CrashContext *
0x180018e9f  mov     ecx, 1E3C3840h; unsigned int
0x180018ea4  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180018eaa  jmp     short $+2
0x180018eac  nop
0x180018ead  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x180018eb4  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018eb9  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018ebe  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018ec5  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018eca  call    _CxxThrowException
```
