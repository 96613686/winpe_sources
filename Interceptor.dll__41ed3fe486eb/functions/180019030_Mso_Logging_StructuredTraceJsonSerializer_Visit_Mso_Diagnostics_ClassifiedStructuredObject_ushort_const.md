# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<ushort> const &)

- ea: `0x180019030`
- end: `0x18001918e`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@G@Diagnostics@3@@Z`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x180019030`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001907f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001907f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001910e`

## string_xrefs

- `0x18001915b`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x180019115`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 80LL))(
          v11,
          *(unsigned __int16 *)(a2 + 16)) )
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
0x180019030  mov     [rsp+arg_0], rbx
0x180019035  mov     [rsp+arg_10], rbp
0x18001903a  push    rsi
0x18001903b  push    rdi
0x18001903c  push    r14
0x18001903e  sub     rsp, 40h
0x180019042  mov     rdi, rdx
0x180019045  mov     rbp, rcx
0x180019048  mov     r8, [rdx+8]
0x18001904c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180019050  test    r8, r8
0x180019053  jz      short loc_180019064
0x180019055  mov     rax, r9
0x180019058  inc     rax
0x18001905b  cmp     byte ptr [rax+r8], 0
0x180019060  jnz     short loc_180019058
0x180019062  jmp     short loc_180019066
0x180019064  xor     eax, eax
0x180019066  lea     r14d, [rax+1]
0x18001906a  movsxd  rcx, r14d
0x18001906d  mov     eax, 2
0x180019072  mul     rcx
0x180019075  mov     rsi, rax
0x180019078  cmovb   rsi, r9
0x18001907c  mov     rcx, rsi; Size
0x18001907f  call    cs:__imp_malloc
0x180019085  mov     rbx, rax
0x180019088  test    rax, rax
0x18001908b  jz      loc_180019141
0x180019091  mov     r8, rsi; Size
0x180019094  xor     edx, edx; Val
0x180019096  mov     rcx, rax; void *
0x180019099  call    memset
0x18001909e  mov     [rsp+58h+arg_8], rbx
0x1800190a3  mov     r8d, r14d; int
0x1800190a6  mov     rdx, rbx; wchar_t *
0x1800190a9  mov     rcx, [rdi+8]; char *
0x1800190ad  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x1800190b2  mov     rcx, [rbp+8]
0x1800190b6  test    rcx, rcx
0x1800190b9  jz      loc_18001914B
0x1800190bf  mov     rax, [rcx]
0x1800190c2  mov     rdx, rbx
0x1800190c5  mov     rax, [rax+30h]
0x1800190c9  call    cs:__guard_dispatch_icall_fptr
0x1800190cf  test    al, al
0x1800190d1  jz      loc_18001915B
0x1800190d7  mov     rcx, [rbp+8]
0x1800190db  test    rcx, rcx
0x1800190de  jz      loc_180019181
0x1800190e4  mov     rax, [rcx]
0x1800190e7  movzx   edx, word ptr [rdi+10h]
0x1800190eb  mov     rax, [rax+50h]
0x1800190ef  call    cs:__guard_dispatch_icall_fptr
0x1800190f5  test    al, al
0x1800190f7  jz      short loc_180019115
0x1800190f9  mov     rcx, rbx
0x1800190fc  mov     rbx, [rsp+58h+arg_0]
0x180019101  mov     rbp, [rsp+58h+arg_10]
0x180019106  add     rsp, 40h
0x18001910a  pop     r14
0x18001910c  pop     rdi
0x18001910d  pop     rsi
0x18001910e  jmp     cs:__imp_free
0x180019115  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x18001911c  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180019121  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180019126  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001912d  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180019132  call    _CxxThrowException
0x180019141  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180019147  jmp     short loc_18001914A
0x18001914a  nop
0x18001914b  xor     edx, edx; struct CrashContext *
0x18001914d  mov     ecx, 1E3C3840h; unsigned int
0x180019152  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180019158  jmp     short $+2
0x18001915a  nop
0x18001915b  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x180019162  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180019167  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001916c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180019173  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180019178  call    _CxxThrowException
0x18001917e  jmp     short $+2
0x180019180  nop
0x180019181  xor     edx, edx; struct CrashContext *
0x180019183  mov     ecx, 1E3C3840h; unsigned int
0x180019188  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
