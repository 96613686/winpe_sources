# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> const &)

- ea: `0x1800192f0`
- end: `0x18001944e`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@_K@Diagnostics@3@@Z`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x1800192f0`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001933f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001933f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800193ce`

## string_xrefs

- `0x18001941b`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x1800193d5`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 80LL))(v11, *(_QWORD *)(a2 + 16)) )
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
0x1800192f0  mov     [rsp+arg_0], rbx
0x1800192f5  mov     [rsp+arg_10], rbp
0x1800192fa  push    rsi
0x1800192fb  push    rdi
0x1800192fc  push    r14
0x1800192fe  sub     rsp, 40h
0x180019302  mov     rdi, rdx
0x180019305  mov     rbp, rcx
0x180019308  mov     r8, [rdx+8]
0x18001930c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180019310  test    r8, r8
0x180019313  jz      short loc_180019324
0x180019315  mov     rax, r9
0x180019318  inc     rax
0x18001931b  cmp     byte ptr [rax+r8], 0
0x180019320  jnz     short loc_180019318
0x180019322  jmp     short loc_180019326
0x180019324  xor     eax, eax
0x180019326  lea     r14d, [rax+1]
0x18001932a  movsxd  rcx, r14d
0x18001932d  mov     eax, 2
0x180019332  mul     rcx
0x180019335  mov     rsi, rax
0x180019338  cmovb   rsi, r9
0x18001933c  mov     rcx, rsi; Size
0x18001933f  call    cs:__imp_malloc
0x180019345  mov     rbx, rax
0x180019348  test    rax, rax
0x18001934b  jz      loc_180019401
0x180019351  mov     r8, rsi; Size
0x180019354  xor     edx, edx; Val
0x180019356  mov     rcx, rax; void *
0x180019359  call    memset
0x18001935e  mov     [rsp+58h+arg_8], rbx
0x180019363  mov     r8d, r14d; int
0x180019366  mov     rdx, rbx; wchar_t *
0x180019369  mov     rcx, [rdi+8]; char *
0x18001936d  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x180019372  mov     rcx, [rbp+8]
0x180019376  test    rcx, rcx
0x180019379  jz      loc_18001940B
0x18001937f  mov     rax, [rcx]
0x180019382  mov     rdx, rbx
0x180019385  mov     rax, [rax+30h]
0x180019389  call    cs:__guard_dispatch_icall_fptr
0x18001938f  test    al, al
0x180019391  jz      loc_18001941B
0x180019397  mov     rcx, [rbp+8]
0x18001939b  test    rcx, rcx
0x18001939e  jz      loc_180019441
0x1800193a4  mov     rax, [rcx]
0x1800193a7  mov     rdx, [rdi+10h]
0x1800193ab  mov     rax, [rax+50h]
0x1800193af  call    cs:__guard_dispatch_icall_fptr
0x1800193b5  test    al, al
0x1800193b7  jz      short loc_1800193D5
0x1800193b9  mov     rcx, rbx
0x1800193bc  mov     rbx, [rsp+58h+arg_0]
0x1800193c1  mov     rbp, [rsp+58h+arg_10]
0x1800193c6  add     rsp, 40h
0x1800193ca  pop     r14
0x1800193cc  pop     rdi
0x1800193cd  pop     rsi
0x1800193ce  jmp     cs:__imp_free
0x1800193d5  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x1800193dc  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800193e1  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800193e6  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800193ed  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800193f2  call    _CxxThrowException
0x180019401  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180019407  jmp     short loc_18001940A
0x18001940a  nop
0x18001940b  xor     edx, edx; struct CrashContext *
0x18001940d  mov     ecx, 1E3C3840h; unsigned int
0x180019412  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180019418  jmp     short $+2
0x18001941a  nop
0x18001941b  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x180019422  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180019427  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001942c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180019433  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180019438  call    _CxxThrowException
0x18001943e  jmp     short $+2
0x180019440  nop
0x180019441  xor     edx, edx; struct CrashContext *
0x180019443  mov     ecx, 1E3C3840h; unsigned int
0x180019448  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
