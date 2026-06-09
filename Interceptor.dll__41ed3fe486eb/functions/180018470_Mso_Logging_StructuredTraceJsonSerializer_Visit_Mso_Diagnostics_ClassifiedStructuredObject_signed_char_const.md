# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<signed char> const &)

- ea: `0x180018470`
- end: `0x1800185c4`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@C@Diagnostics@3@@Z`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x180018470`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800184bf`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800184bf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001854b`

## string_xrefs

- `0x180018591`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x180018552`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 72LL))(v11, *(char *)(a2 + 16)) )
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
0x180018470  mov     [rsp+arg_0], rbx
0x180018475  mov     [rsp+arg_10], rbp
0x18001847a  push    rsi
0x18001847b  push    rdi
0x18001847c  push    r14
0x18001847e  sub     rsp, 40h
0x180018482  mov     rdi, rdx
0x180018485  mov     rbp, rcx
0x180018488  mov     r8, [rdx+8]
0x18001848c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180018490  test    r8, r8
0x180018493  jz      short loc_1800184A4
0x180018495  mov     rax, r9
0x180018498  inc     rax
0x18001849b  cmp     byte ptr [rax+r8], 0
0x1800184a0  jnz     short loc_180018498
0x1800184a2  jmp     short loc_1800184A6
0x1800184a4  xor     eax, eax
0x1800184a6  lea     r14d, [rax+1]
0x1800184aa  movsxd  rcx, r14d
0x1800184ad  mov     eax, 2
0x1800184b2  mul     rcx
0x1800184b5  mov     rsi, rax
0x1800184b8  cmovb   rsi, r9
0x1800184bc  mov     rcx, rsi; Size
0x1800184bf  call    cs:__imp_malloc
0x1800184c5  mov     rbx, rax
0x1800184c8  test    rax, rax
0x1800184cb  jz      loc_180018578
0x1800184d1  mov     r8, rsi; Size
0x1800184d4  xor     edx, edx; Val
0x1800184d6  mov     rcx, rax; void *
0x1800184d9  call    memset
0x1800184de  mov     [rsp+58h+arg_8], rbx
0x1800184e3  mov     r8d, r14d; int
0x1800184e6  mov     rdx, rbx; wchar_t *
0x1800184e9  mov     rcx, [rdi+8]; char *
0x1800184ed  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x1800184f2  mov     rcx, [rbp+8]
0x1800184f6  test    rcx, rcx
0x1800184f9  jz      loc_180018581
0x1800184ff  mov     rax, [rcx]
0x180018502  mov     rdx, rbx
0x180018505  mov     rax, [rax+30h]
0x180018509  call    cs:__guard_dispatch_icall_fptr
0x18001850f  test    al, al
0x180018511  jz      short loc_180018591
0x180018513  mov     rcx, [rbp+8]
0x180018517  test    rcx, rcx
0x18001851a  jz      loc_1800185B7
0x180018520  mov     rax, [rcx]
0x180018523  movsx   rdx, byte ptr [rdi+10h]
0x180018528  mov     rax, [rax+48h]
0x18001852c  call    cs:__guard_dispatch_icall_fptr
0x180018532  test    al, al
0x180018534  jz      short loc_180018552
0x180018536  mov     rcx, rbx
0x180018539  mov     rbx, [rsp+58h+arg_0]
0x18001853e  mov     rbp, [rsp+58h+arg_10]
0x180018543  add     rsp, 40h
0x180018547  pop     r14
0x180018549  pop     rdi
0x18001854a  pop     rsi
0x18001854b  jmp     cs:__imp_free
0x180018552  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x180018559  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001855e  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018563  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001856a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001856f  call    _CxxThrowException
0x180018575  jmp     short $+2
0x180018577  nop
0x180018578  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001857e  jmp     short $+2
0x180018580  nop
0x180018581  xor     edx, edx; struct CrashContext *
0x180018583  mov     ecx, 1E3C3840h; unsigned int
0x180018588  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18001858e  jmp     short $+2
0x180018590  nop
0x180018591  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x180018598  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001859d  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800185a2  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800185a9  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800185ae  call    _CxxThrowException
0x1800185b4  jmp     short $+2
0x1800185b6  nop
0x1800185b7  xor     edx, edx; struct CrashContext *
0x1800185b9  mov     ecx, 1E3C3840h; unsigned int
0x1800185be  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
