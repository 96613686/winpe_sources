# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<uchar> const &)

- ea: `0x180018ed0`
- end: `0x18001902e`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@E@Diagnostics@3@@Z`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x180018ed0`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180018f1f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180018f1f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180018fae`

## string_xrefs

- `0x180018ffb`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x180018fb5`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  __int64 v11; // rcx
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
  v11 = *(_QWORD *)(a1 + 8);
  if ( !v11 )
    CrashWithRecovery(0x1E3C3840u, 0);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 80LL))(v11, *(unsigned __int8 *)(a2 + 16)) )
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
0x180018ed0  mov     [rsp+arg_0], rbx
0x180018ed5  mov     [rsp+arg_10], rbp
0x180018eda  push    rsi
0x180018edb  push    rdi
0x180018edc  push    r14
0x180018ede  sub     rsp, 40h
0x180018ee2  mov     rdi, rdx
0x180018ee5  mov     rbp, rcx
0x180018ee8  mov     r8, [rdx+8]
0x180018eec  or      r9, 0FFFFFFFFFFFFFFFFh
0x180018ef0  test    r8, r8
0x180018ef3  jz      short loc_180018F04
0x180018ef5  mov     rax, r9
0x180018ef8  inc     rax
0x180018efb  cmp     byte ptr [rax+r8], 0
0x180018f00  jnz     short loc_180018EF8
0x180018f02  jmp     short loc_180018F06
0x180018f04  xor     eax, eax
0x180018f06  lea     r14d, [rax+1]
0x180018f0a  movsxd  rcx, r14d
0x180018f0d  mov     eax, 2
0x180018f12  mul     rcx
0x180018f15  mov     rsi, rax
0x180018f18  cmovb   rsi, r9
0x180018f1c  mov     rcx, rsi; Size
0x180018f1f  call    cs:__imp_malloc
0x180018f25  mov     rbx, rax
0x180018f28  test    rax, rax
0x180018f2b  jz      loc_180018FE1
0x180018f31  mov     r8, rsi; Size
0x180018f34  xor     edx, edx; Val
0x180018f36  mov     rcx, rax; void *
0x180018f39  call    memset
0x180018f3e  mov     [rsp+58h+arg_8], rbx
0x180018f43  mov     r8d, r14d; int
0x180018f46  mov     rdx, rbx; wchar_t *
0x180018f49  mov     rcx, [rdi+8]; char *
0x180018f4d  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x180018f52  mov     rcx, [rbp+8]
0x180018f56  test    rcx, rcx
0x180018f59  jz      loc_180018FEB
0x180018f5f  mov     rax, [rcx]
0x180018f62  mov     rdx, rbx
0x180018f65  mov     rax, [rax+30h]
0x180018f69  call    cs:__guard_dispatch_icall_fptr
0x180018f6f  test    al, al
0x180018f71  jz      loc_180018FFB
0x180018f77  mov     rcx, [rbp+8]
0x180018f7b  test    rcx, rcx
0x180018f7e  jz      loc_180019021
0x180018f84  mov     rax, [rcx]
0x180018f87  movzx   edx, byte ptr [rdi+10h]
0x180018f8b  mov     rax, [rax+50h]
0x180018f8f  call    cs:__guard_dispatch_icall_fptr
0x180018f95  test    al, al
0x180018f97  jz      short loc_180018FB5
0x180018f99  mov     rcx, rbx
0x180018f9c  mov     rbx, [rsp+58h+arg_0]
0x180018fa1  mov     rbp, [rsp+58h+arg_10]
0x180018fa6  add     rsp, 40h
0x180018faa  pop     r14
0x180018fac  pop     rdi
0x180018fad  pop     rsi
0x180018fae  jmp     cs:__imp_free
0x180018fb5  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x180018fbc  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018fc1  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018fc6  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018fcd  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018fd2  call    _CxxThrowException
0x180018fe1  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180018fe7  jmp     short loc_180018FEA
0x180018fea  nop
0x180018feb  xor     edx, edx; struct CrashContext *
0x180018fed  mov     ecx, 1E3C3840h; unsigned int
0x180018ff2  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180018ff8  jmp     short $+2
0x180018ffa  nop
0x180018ffb  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x180019002  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180019007  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001900c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180019013  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180019018  call    _CxxThrowException
0x18001901e  jmp     short $+2
0x180019020  nop
0x180019021  xor     edx, edx; struct CrashContext *
0x180019023  mov     ecx, 1E3C3840h; unsigned int
0x180019028  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
