# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<short> const &)

- ea: `0x1800185d0`
- end: `0x180018724`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@F@Diagnostics@3@@Z`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x1800185d0`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001861f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001861f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800186ab`

## string_xrefs

- `0x1800186f1`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x1800186b2`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 72LL))(v11, *(__int16 *)(a2 + 16)) )
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
0x1800185d0  mov     [rsp+arg_0], rbx
0x1800185d5  mov     [rsp+arg_10], rbp
0x1800185da  push    rsi
0x1800185db  push    rdi
0x1800185dc  push    r14
0x1800185de  sub     rsp, 40h
0x1800185e2  mov     rdi, rdx
0x1800185e5  mov     rbp, rcx
0x1800185e8  mov     r8, [rdx+8]
0x1800185ec  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800185f0  test    r8, r8
0x1800185f3  jz      short loc_180018604
0x1800185f5  mov     rax, r9
0x1800185f8  inc     rax
0x1800185fb  cmp     byte ptr [rax+r8], 0
0x180018600  jnz     short loc_1800185F8
0x180018602  jmp     short loc_180018606
0x180018604  xor     eax, eax
0x180018606  lea     r14d, [rax+1]
0x18001860a  movsxd  rcx, r14d
0x18001860d  mov     eax, 2
0x180018612  mul     rcx
0x180018615  mov     rsi, rax
0x180018618  cmovb   rsi, r9
0x18001861c  mov     rcx, rsi; Size
0x18001861f  call    cs:__imp_malloc
0x180018625  mov     rbx, rax
0x180018628  test    rax, rax
0x18001862b  jz      loc_1800186D8
0x180018631  mov     r8, rsi; Size
0x180018634  xor     edx, edx; Val
0x180018636  mov     rcx, rax; void *
0x180018639  call    memset
0x18001863e  mov     [rsp+58h+arg_8], rbx
0x180018643  mov     r8d, r14d; int
0x180018646  mov     rdx, rbx; wchar_t *
0x180018649  mov     rcx, [rdi+8]; char *
0x18001864d  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x180018652  mov     rcx, [rbp+8]
0x180018656  test    rcx, rcx
0x180018659  jz      loc_1800186E1
0x18001865f  mov     rax, [rcx]
0x180018662  mov     rdx, rbx
0x180018665  mov     rax, [rax+30h]
0x180018669  call    cs:__guard_dispatch_icall_fptr
0x18001866f  test    al, al
0x180018671  jz      short loc_1800186F1
0x180018673  mov     rcx, [rbp+8]
0x180018677  test    rcx, rcx
0x18001867a  jz      loc_180018717
0x180018680  mov     rax, [rcx]
0x180018683  movsx   rdx, word ptr [rdi+10h]
0x180018688  mov     rax, [rax+48h]
0x18001868c  call    cs:__guard_dispatch_icall_fptr
0x180018692  test    al, al
0x180018694  jz      short loc_1800186B2
0x180018696  mov     rcx, rbx
0x180018699  mov     rbx, [rsp+58h+arg_0]
0x18001869e  mov     rbp, [rsp+58h+arg_10]
0x1800186a3  add     rsp, 40h
0x1800186a7  pop     r14
0x1800186a9  pop     rdi
0x1800186aa  pop     rsi
0x1800186ab  jmp     cs:__imp_free
0x1800186b2  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x1800186b9  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800186be  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800186c3  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800186ca  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800186cf  call    _CxxThrowException
0x1800186d5  jmp     short $+2
0x1800186d7  nop
0x1800186d8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800186de  jmp     short $+2
0x1800186e0  nop
0x1800186e1  xor     edx, edx; struct CrashContext *
0x1800186e3  mov     ecx, 1E3C3840h; unsigned int
0x1800186e8  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800186ee  jmp     short $+2
0x1800186f0  nop
0x1800186f1  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x1800186f8  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800186fd  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018702  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018709  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001870e  call    _CxxThrowException
0x180018714  jmp     short $+2
0x180018716  nop
0x180018717  xor     edx, edx; struct CrashContext *
0x180018719  mov     ecx, 1E3C3840h; unsigned int
0x18001871e  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
