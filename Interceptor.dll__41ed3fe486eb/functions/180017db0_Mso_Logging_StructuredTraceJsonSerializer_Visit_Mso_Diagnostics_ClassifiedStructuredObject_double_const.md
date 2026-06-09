# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<double> const &)

- ea: `0x180017db0`
- end: `0x180017f04`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@N@Diagnostics@3@@Z`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x180017db0`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180017dff`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180017dff`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180017e8b`

## string_xrefs

- `0x180017ed1`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x180017e92`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v11 + 88LL))(v11) )
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
0x180017db0  mov     [rsp+arg_0], rbx
0x180017db5  mov     [rsp+arg_10], rbp
0x180017dba  push    rsi
0x180017dbb  push    rdi
0x180017dbc  push    r14
0x180017dbe  sub     rsp, 40h
0x180017dc2  mov     rdi, rdx
0x180017dc5  mov     rbp, rcx
0x180017dc8  mov     r8, [rdx+8]
0x180017dcc  or      r9, 0FFFFFFFFFFFFFFFFh
0x180017dd0  test    r8, r8
0x180017dd3  jz      short loc_180017DE4
0x180017dd5  mov     rax, r9
0x180017dd8  inc     rax
0x180017ddb  cmp     byte ptr [rax+r8], 0
0x180017de0  jnz     short loc_180017DD8
0x180017de2  jmp     short loc_180017DE6
0x180017de4  xor     eax, eax
0x180017de6  lea     r14d, [rax+1]
0x180017dea  movsxd  rcx, r14d
0x180017ded  mov     eax, 2
0x180017df2  mul     rcx
0x180017df5  mov     rsi, rax
0x180017df8  cmovb   rsi, r9
0x180017dfc  mov     rcx, rsi; Size
0x180017dff  call    cs:__imp_malloc
0x180017e05  mov     rbx, rax
0x180017e08  test    rax, rax
0x180017e0b  jz      loc_180017EB8
0x180017e11  mov     r8, rsi; Size
0x180017e14  xor     edx, edx; Val
0x180017e16  mov     rcx, rax; void *
0x180017e19  call    memset
0x180017e1e  mov     [rsp+58h+arg_8], rbx
0x180017e23  mov     r8d, r14d; int
0x180017e26  mov     rdx, rbx; wchar_t *
0x180017e29  mov     rcx, [rdi+8]; char *
0x180017e2d  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x180017e32  mov     rcx, [rbp+8]
0x180017e36  test    rcx, rcx
0x180017e39  jz      loc_180017EC1
0x180017e3f  mov     rax, [rcx]
0x180017e42  mov     rdx, rbx
0x180017e45  mov     rax, [rax+30h]
0x180017e49  call    cs:__guard_dispatch_icall_fptr
0x180017e4f  test    al, al
0x180017e51  jz      short loc_180017ED1
0x180017e53  mov     rcx, [rbp+8]
0x180017e57  test    rcx, rcx
0x180017e5a  jz      loc_180017EF7
0x180017e60  mov     rax, [rcx]
0x180017e63  movsd   xmm1, qword ptr [rdi+10h]
0x180017e68  mov     rax, [rax+58h]
0x180017e6c  call    cs:__guard_dispatch_icall_fptr
0x180017e72  test    al, al
0x180017e74  jz      short loc_180017E92
0x180017e76  mov     rcx, rbx
0x180017e79  mov     rbx, [rsp+58h+arg_0]
0x180017e7e  mov     rbp, [rsp+58h+arg_10]
0x180017e83  add     rsp, 40h
0x180017e87  pop     r14
0x180017e89  pop     rdi
0x180017e8a  pop     rsi
0x180017e8b  jmp     cs:__imp_free
0x180017e92  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x180017e99  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180017e9e  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180017ea3  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180017eaa  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180017eaf  call    _CxxThrowException
0x180017eb5  jmp     short $+2
0x180017eb7  nop
0x180017eb8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180017ebe  jmp     short $+2
0x180017ec0  nop
0x180017ec1  xor     edx, edx; struct CrashContext *
0x180017ec3  mov     ecx, 1E3C3840h; unsigned int
0x180017ec8  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180017ece  jmp     short $+2
0x180017ed0  nop
0x180017ed1  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x180017ed8  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180017edd  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180017ee2  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180017ee9  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180017eee  call    _CxxThrowException
0x180017ef4  jmp     short $+2
0x180017ef6  nop
0x180017ef7  xor     edx, edx; struct CrashContext *
0x180017ef9  mov     ecx, 1E3C3840h; unsigned int
0x180017efe  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
