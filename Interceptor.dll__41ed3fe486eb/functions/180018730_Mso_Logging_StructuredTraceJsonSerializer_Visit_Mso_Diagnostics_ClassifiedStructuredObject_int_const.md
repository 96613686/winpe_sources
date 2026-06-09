# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<int> const &)

- ea: `0x180018730`
- end: `0x18001888e`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@H@Diagnostics@3@@Z`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x180018730`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001877f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001877f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001880e`

## string_xrefs

- `0x18001885b`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x180018815`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 72LL))(v11, *(int *)(a2 + 16)) )
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
0x180018730  mov     [rsp+arg_0], rbx
0x180018735  mov     [rsp+arg_10], rbp
0x18001873a  push    rsi
0x18001873b  push    rdi
0x18001873c  push    r14
0x18001873e  sub     rsp, 40h
0x180018742  mov     rdi, rdx
0x180018745  mov     rbp, rcx
0x180018748  mov     r8, [rdx+8]
0x18001874c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180018750  test    r8, r8
0x180018753  jz      short loc_180018764
0x180018755  mov     rax, r9
0x180018758  inc     rax
0x18001875b  cmp     byte ptr [rax+r8], 0
0x180018760  jnz     short loc_180018758
0x180018762  jmp     short loc_180018766
0x180018764  xor     eax, eax
0x180018766  lea     r14d, [rax+1]
0x18001876a  movsxd  rcx, r14d
0x18001876d  mov     eax, 2
0x180018772  mul     rcx
0x180018775  mov     rsi, rax
0x180018778  cmovb   rsi, r9
0x18001877c  mov     rcx, rsi; Size
0x18001877f  call    cs:__imp_malloc
0x180018785  mov     rbx, rax
0x180018788  test    rax, rax
0x18001878b  jz      loc_180018841
0x180018791  mov     r8, rsi; Size
0x180018794  xor     edx, edx; Val
0x180018796  mov     rcx, rax; void *
0x180018799  call    memset
0x18001879e  mov     [rsp+58h+arg_8], rbx
0x1800187a3  mov     r8d, r14d; int
0x1800187a6  mov     rdx, rbx; wchar_t *
0x1800187a9  mov     rcx, [rdi+8]; char *
0x1800187ad  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x1800187b2  mov     rcx, [rbp+8]
0x1800187b6  test    rcx, rcx
0x1800187b9  jz      loc_18001884B
0x1800187bf  mov     rax, [rcx]
0x1800187c2  mov     rdx, rbx
0x1800187c5  mov     rax, [rax+30h]
0x1800187c9  call    cs:__guard_dispatch_icall_fptr
0x1800187cf  test    al, al
0x1800187d1  jz      loc_18001885B
0x1800187d7  mov     rcx, [rbp+8]
0x1800187db  test    rcx, rcx
0x1800187de  jz      loc_180018881
0x1800187e4  mov     rax, [rcx]
0x1800187e7  movsxd  rdx, dword ptr [rdi+10h]
0x1800187eb  mov     rax, [rax+48h]
0x1800187ef  call    cs:__guard_dispatch_icall_fptr
0x1800187f5  test    al, al
0x1800187f7  jz      short loc_180018815
0x1800187f9  mov     rcx, rbx
0x1800187fc  mov     rbx, [rsp+58h+arg_0]
0x180018801  mov     rbp, [rsp+58h+arg_10]
0x180018806  add     rsp, 40h
0x18001880a  pop     r14
0x18001880c  pop     rdi
0x18001880d  pop     rsi
0x18001880e  jmp     cs:__imp_free
0x180018815  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x18001881c  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018821  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018826  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001882d  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018832  call    _CxxThrowException
0x180018841  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180018847  jmp     short loc_18001884A
0x18001884a  nop
0x18001884b  xor     edx, edx; struct CrashContext *
0x18001884d  mov     ecx, 1E3C3840h; unsigned int
0x180018852  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180018858  jmp     short $+2
0x18001885a  nop
0x18001885b  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x180018862  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018867  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001886c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018873  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018878  call    _CxxThrowException
0x18001887e  jmp     short $+2
0x180018880  nop
0x180018881  xor     edx, edx; struct CrashContext *
0x180018883  mov     ecx, 1E3C3840h; unsigned int
0x180018888  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
