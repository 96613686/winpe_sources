# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> const &)

- ea: `0x1800195c0`
- end: `0x1800196f0`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@PEB_W@Diagnostics@3@@Z`
- size: `304`
- prototype: `__int64 __fastcall(Mso::Logging::StructuredTraceJsonSerializer *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x1800195c0`
- `0x18001a670`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001960f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001960f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180019684`

## string_xrefs

- `0x1800196cd`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x18001968b`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  if ( !Mso::Logging::StructuredTraceJsonSerializer::WriteJson(this, (const wchar_t *const *)(a2 + 16)) )
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
0x1800195c0  mov     [rsp+arg_0], rbx
0x1800195c5  mov     [rsp+arg_10], rbp
0x1800195ca  push    rsi
0x1800195cb  push    rdi
0x1800195cc  push    r14
0x1800195ce  sub     rsp, 40h
0x1800195d2  mov     rdi, rdx
0x1800195d5  mov     rbp, rcx
0x1800195d8  mov     r8, [rdx+8]
0x1800195dc  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800195e0  test    r8, r8
0x1800195e3  jz      short loc_1800195F4
0x1800195e5  mov     rax, r9
0x1800195e8  inc     rax
0x1800195eb  cmp     byte ptr [rax+r8], 0
0x1800195f0  jnz     short loc_1800195E8
0x1800195f2  jmp     short loc_1800195F6
0x1800195f4  xor     eax, eax
0x1800195f6  lea     r14d, [rax+1]
0x1800195fa  movsxd  rcx, r14d
0x1800195fd  mov     eax, 2
0x180019602  mul     rcx
0x180019605  mov     rsi, rax
0x180019608  cmovb   rsi, r9
0x18001960c  mov     rcx, rsi; Size
0x18001960f  call    cs:__imp_malloc
0x180019615  mov     rbx, rax
0x180019618  test    rax, rax
0x18001961b  jz      loc_1800196B1
0x180019621  mov     r8, rsi; Size
0x180019624  xor     edx, edx; Val
0x180019626  mov     rcx, rax; void *
0x180019629  call    memset
0x18001962e  mov     [rsp+58h+arg_8], rbx
0x180019633  mov     r8d, r14d; int
0x180019636  mov     rdx, rbx; wchar_t *
0x180019639  mov     rcx, [rdi+8]; char *
0x18001963d  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x180019642  mov     rcx, [rbp+8]
0x180019646  test    rcx, rcx
0x180019649  jz      short loc_1800196BD
0x18001964b  mov     rax, [rcx]
0x18001964e  mov     rdx, rbx
0x180019651  mov     rax, [rax+30h]
0x180019655  call    cs:__guard_dispatch_icall_fptr
0x18001965b  test    al, al
0x18001965d  jz      short loc_1800196CD
0x18001965f  lea     rdx, [rdi+10h]; wchar_t **
0x180019663  mov     rcx, rbp; this
0x180019666  call    ?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBQEB_W@Z; Mso::Logging::StructuredTraceJsonSerializer::WriteJson(wchar_t const * const &)
0x18001966b  test    al, al
0x18001966d  jz      short loc_18001968B
0x18001966f  mov     rcx, rbx
0x180019672  mov     rbx, [rsp+58h+arg_0]
0x180019677  mov     rbp, [rsp+58h+arg_10]
0x18001967c  add     rsp, 40h
0x180019680  pop     r14
0x180019682  pop     rdi
0x180019683  pop     rsi
0x180019684  jmp     cs:__imp_free
0x18001968b  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x180019692  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180019697  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001969c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800196a3  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800196a8  call    _CxxThrowException
0x1800196ae  jmp     short $+2
0x1800196b0  nop
0x1800196b1  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800196b7  jmp     short loc_1800196BC
0x1800196bc  nop
0x1800196bd  xor     edx, edx; struct CrashContext *
0x1800196bf  mov     ecx, 1E3C3840h; unsigned int
0x1800196c4  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800196ca  jmp     short $+2
0x1800196cc  nop
0x1800196cd  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x1800196d4  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800196d9  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800196de  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800196e5  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800196ea  call    _CxxThrowException
```
