# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<bool> const &)

- ea: `0x180017c50`
- end: `0x180017da2`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@_N@Diagnostics@3@@Z`
- size: `338`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x180017c50`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180017c9f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180017c9f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180017d29`

## string_xrefs

- `0x180017d6f`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x180017d30`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Mso::Logging::StructuredTraceJsonSerializer::Visit(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  __int64 v5; // rax
  int v6; // r14d
  size_t v7; // rsi
  wchar_t *v8; // rax
  wchar_t *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
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
  v10 = *(_QWORD *)(a1 + 8);
  if ( !v10 )
    CrashWithRecovery(0x1E3C3840u, 0);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, wchar_t *))(*(_QWORD *)v10 + 48LL))(v10, v9) )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject,
      "StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.");
    throw (std::runtime_error *)pExceptionObject;
  }
  v12 = *(_QWORD *)(a1 + 8);
  if ( !v12 )
    CrashWithRecovery(0x1E3C3840u, 0);
  LOBYTE(v11) = *(_BYTE *)(a2 + 16);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 64LL))(v12, v11) )
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
0x180017c50  mov     [rsp+arg_0], rbx
0x180017c55  mov     [rsp+arg_10], rbp
0x180017c5a  push    rsi
0x180017c5b  push    rdi
0x180017c5c  push    r14
0x180017c5e  sub     rsp, 40h
0x180017c62  mov     rdi, rdx
0x180017c65  mov     rbp, rcx
0x180017c68  mov     r8, [rdx+8]
0x180017c6c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180017c70  test    r8, r8
0x180017c73  jz      short loc_180017C84
0x180017c75  mov     rax, r9
0x180017c78  inc     rax
0x180017c7b  cmp     byte ptr [rax+r8], 0
0x180017c80  jnz     short loc_180017C78
0x180017c82  jmp     short loc_180017C86
0x180017c84  xor     eax, eax
0x180017c86  lea     r14d, [rax+1]
0x180017c8a  movsxd  rcx, r14d
0x180017c8d  mov     eax, 2
0x180017c92  mul     rcx
0x180017c95  mov     rsi, rax
0x180017c98  cmovb   rsi, r9
0x180017c9c  mov     rcx, rsi; Size
0x180017c9f  call    cs:__imp_malloc
0x180017ca5  mov     rbx, rax
0x180017ca8  test    rax, rax
0x180017cab  jz      loc_180017D56
0x180017cb1  mov     r8, rsi; Size
0x180017cb4  xor     edx, edx; Val
0x180017cb6  mov     rcx, rax; void *
0x180017cb9  call    memset
0x180017cbe  mov     [rsp+58h+arg_8], rbx
0x180017cc3  mov     r8d, r14d; int
0x180017cc6  mov     rdx, rbx; wchar_t *
0x180017cc9  mov     rcx, [rdi+8]; char *
0x180017ccd  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x180017cd2  mov     rcx, [rbp+8]
0x180017cd6  test    rcx, rcx
0x180017cd9  jz      loc_180017D5F
0x180017cdf  mov     rax, [rcx]
0x180017ce2  mov     rdx, rbx
0x180017ce5  mov     rax, [rax+30h]
0x180017ce9  call    cs:__guard_dispatch_icall_fptr
0x180017cef  test    al, al
0x180017cf1  jz      short loc_180017D6F
0x180017cf3  mov     rcx, [rbp+8]
0x180017cf7  test    rcx, rcx
0x180017cfa  jz      loc_180017D95
0x180017d00  mov     rax, [rcx]
0x180017d03  mov     dl, [rdi+10h]
0x180017d06  mov     rax, [rax+40h]
0x180017d0a  call    cs:__guard_dispatch_icall_fptr
0x180017d10  test    al, al
0x180017d12  jz      short loc_180017D30
0x180017d14  mov     rcx, rbx
0x180017d17  mov     rbx, [rsp+58h+arg_0]
0x180017d1c  mov     rbp, [rsp+58h+arg_10]
0x180017d21  add     rsp, 40h
0x180017d25  pop     r14
0x180017d27  pop     rdi
0x180017d28  pop     rsi
0x180017d29  jmp     cs:__imp_free
0x180017d30  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x180017d37  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180017d3c  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180017d41  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180017d48  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180017d4d  call    _CxxThrowException
0x180017d53  jmp     short $+2
0x180017d55  nop
0x180017d56  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180017d5c  jmp     short $+2
0x180017d5e  nop
0x180017d5f  xor     edx, edx; struct CrashContext *
0x180017d61  mov     ecx, 1E3C3840h; unsigned int
0x180017d66  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180017d6c  jmp     short $+2
0x180017d6e  nop
0x180017d6f  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x180017d76  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180017d7b  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180017d80  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180017d87  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180017d8c  call    _CxxThrowException
0x180017d92  jmp     short $+2
0x180017d94  nop
0x180017d95  xor     edx, edx; struct CrashContext *
0x180017d97  mov     ecx, 1E3C3840h; unsigned int
0x180017d9c  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
