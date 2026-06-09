# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<_GUID> const &)

- ea: `0x1800181a0`
- end: `0x1800182d0`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@U_GUID@@@Diagnostics@3@@Z`
- size: `304`
- prototype: `__int64 __fastcall(Mso::Logging::StructuredTraceJsonSerializer *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x1800181a0`
- `0x18001a1d4`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800181ef`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800181ef`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180018264`

## string_xrefs

- `0x1800182ad`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x18001826b`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  if ( !Mso::Logging::StructuredTraceJsonSerializer::WriteJson(this, (const struct _GUID *)(a2 + 16)) )
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
0x1800181a0  mov     [rsp+arg_0], rbx
0x1800181a5  mov     [rsp+arg_10], rbp
0x1800181aa  push    rsi
0x1800181ab  push    rdi
0x1800181ac  push    r14
0x1800181ae  sub     rsp, 40h
0x1800181b2  mov     rdi, rdx
0x1800181b5  mov     rbp, rcx
0x1800181b8  mov     r8, [rdx+8]
0x1800181bc  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800181c0  test    r8, r8
0x1800181c3  jz      short loc_1800181D4
0x1800181c5  mov     rax, r9
0x1800181c8  inc     rax
0x1800181cb  cmp     byte ptr [rax+r8], 0
0x1800181d0  jnz     short loc_1800181C8
0x1800181d2  jmp     short loc_1800181D6
0x1800181d4  xor     eax, eax
0x1800181d6  lea     r14d, [rax+1]
0x1800181da  movsxd  rcx, r14d
0x1800181dd  mov     eax, 2
0x1800181e2  mul     rcx
0x1800181e5  mov     rsi, rax
0x1800181e8  cmovb   rsi, r9
0x1800181ec  mov     rcx, rsi; Size
0x1800181ef  call    cs:__imp_malloc
0x1800181f5  mov     rbx, rax
0x1800181f8  test    rax, rax
0x1800181fb  jz      loc_180018291
0x180018201  mov     r8, rsi; Size
0x180018204  xor     edx, edx; Val
0x180018206  mov     rcx, rax; void *
0x180018209  call    memset
0x18001820e  mov     [rsp+58h+arg_8], rbx
0x180018213  mov     r8d, r14d; int
0x180018216  mov     rdx, rbx; wchar_t *
0x180018219  mov     rcx, [rdi+8]; char *
0x18001821d  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x180018222  mov     rcx, [rbp+8]
0x180018226  test    rcx, rcx
0x180018229  jz      short loc_18001829D
0x18001822b  mov     rax, [rcx]
0x18001822e  mov     rdx, rbx
0x180018231  mov     rax, [rax+30h]
0x180018235  call    cs:__guard_dispatch_icall_fptr
0x18001823b  test    al, al
0x18001823d  jz      short loc_1800182AD
0x18001823f  lea     rdx, [rdi+10h]; struct _GUID *
0x180018243  mov     rcx, rbp; this
0x180018246  call    ?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBU_GUID@@@Z; Mso::Logging::StructuredTraceJsonSerializer::WriteJson(_GUID const &)
0x18001824b  test    al, al
0x18001824d  jz      short loc_18001826B
0x18001824f  mov     rcx, rbx
0x180018252  mov     rbx, [rsp+58h+arg_0]
0x180018257  mov     rbp, [rsp+58h+arg_10]
0x18001825c  add     rsp, 40h
0x180018260  pop     r14
0x180018262  pop     rdi
0x180018263  pop     rsi
0x180018264  jmp     cs:__imp_free
0x18001826b  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x180018272  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018277  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001827c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018283  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018288  call    _CxxThrowException
0x18001828e  jmp     short $+2
0x180018290  nop
0x180018291  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180018297  jmp     short loc_18001829C
0x18001829c  nop
0x18001829d  xor     edx, edx; struct CrashContext *
0x18001829f  mov     ecx, 1E3C3840h; unsigned int
0x1800182a4  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800182aa  jmp     short $+2
0x1800182ac  nop
0x1800182ad  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x1800182b4  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800182b9  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800182be  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800182c5  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800182ca  call    _CxxThrowException
```
