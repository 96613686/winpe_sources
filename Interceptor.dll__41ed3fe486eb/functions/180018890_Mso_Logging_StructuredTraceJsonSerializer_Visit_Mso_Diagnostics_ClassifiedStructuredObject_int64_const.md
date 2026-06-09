# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<__int64> const &)

- ea: `0x180018890`
- end: `0x1800189ee`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@_J@Diagnostics@3@@Z`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x180018890`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800188df`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800188df`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001896e`

## string_xrefs

- `0x1800189bb`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x180018975`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 72LL))(v11, *(_QWORD *)(a2 + 16)) )
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
0x180018890  mov     [rsp+arg_0], rbx
0x180018895  mov     [rsp+arg_10], rbp
0x18001889a  push    rsi
0x18001889b  push    rdi
0x18001889c  push    r14
0x18001889e  sub     rsp, 40h
0x1800188a2  mov     rdi, rdx
0x1800188a5  mov     rbp, rcx
0x1800188a8  mov     r8, [rdx+8]
0x1800188ac  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800188b0  test    r8, r8
0x1800188b3  jz      short loc_1800188C4
0x1800188b5  mov     rax, r9
0x1800188b8  inc     rax
0x1800188bb  cmp     byte ptr [rax+r8], 0
0x1800188c0  jnz     short loc_1800188B8
0x1800188c2  jmp     short loc_1800188C6
0x1800188c4  xor     eax, eax
0x1800188c6  lea     r14d, [rax+1]
0x1800188ca  movsxd  rcx, r14d
0x1800188cd  mov     eax, 2
0x1800188d2  mul     rcx
0x1800188d5  mov     rsi, rax
0x1800188d8  cmovb   rsi, r9
0x1800188dc  mov     rcx, rsi; Size
0x1800188df  call    cs:__imp_malloc
0x1800188e5  mov     rbx, rax
0x1800188e8  test    rax, rax
0x1800188eb  jz      loc_1800189A1
0x1800188f1  mov     r8, rsi; Size
0x1800188f4  xor     edx, edx; Val
0x1800188f6  mov     rcx, rax; void *
0x1800188f9  call    memset
0x1800188fe  mov     [rsp+58h+arg_8], rbx
0x180018903  mov     r8d, r14d; int
0x180018906  mov     rdx, rbx; wchar_t *
0x180018909  mov     rcx, [rdi+8]; char *
0x18001890d  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x180018912  mov     rcx, [rbp+8]
0x180018916  test    rcx, rcx
0x180018919  jz      loc_1800189AB
0x18001891f  mov     rax, [rcx]
0x180018922  mov     rdx, rbx
0x180018925  mov     rax, [rax+30h]
0x180018929  call    cs:__guard_dispatch_icall_fptr
0x18001892f  test    al, al
0x180018931  jz      loc_1800189BB
0x180018937  mov     rcx, [rbp+8]
0x18001893b  test    rcx, rcx
0x18001893e  jz      loc_1800189E1
0x180018944  mov     rax, [rcx]
0x180018947  mov     rdx, [rdi+10h]
0x18001894b  mov     rax, [rax+48h]
0x18001894f  call    cs:__guard_dispatch_icall_fptr
0x180018955  test    al, al
0x180018957  jz      short loc_180018975
0x180018959  mov     rcx, rbx
0x18001895c  mov     rbx, [rsp+58h+arg_0]
0x180018961  mov     rbp, [rsp+58h+arg_10]
0x180018966  add     rsp, 40h
0x18001896a  pop     r14
0x18001896c  pop     rdi
0x18001896d  pop     rsi
0x18001896e  jmp     cs:__imp_free
0x180018975  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x18001897c  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018981  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018986  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001898d  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018992  call    _CxxThrowException
0x1800189a1  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800189a7  jmp     short loc_1800189AA
0x1800189aa  nop
0x1800189ab  xor     edx, edx; struct CrashContext *
0x1800189ad  mov     ecx, 1E3C3840h; unsigned int
0x1800189b2  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800189b8  jmp     short $+2
0x1800189ba  nop
0x1800189bb  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x1800189c2  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800189c7  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800189cc  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800189d3  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800189d8  call    _CxxThrowException
0x1800189de  jmp     short $+2
0x1800189e0  nop
0x1800189e1  xor     edx, edx; struct CrashContext *
0x1800189e3  mov     ecx, 1E3C3840h; unsigned int
0x1800189e8  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
