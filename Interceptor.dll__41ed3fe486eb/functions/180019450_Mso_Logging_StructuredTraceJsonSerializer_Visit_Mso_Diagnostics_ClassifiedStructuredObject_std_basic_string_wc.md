# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> const &)

- ea: `0x180019450`
- end: `0x1800195b6`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Diagnostics@3@@Z`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x180019450`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001949f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001949f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180019539`

## string_xrefs

- `0x180019581`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x180019540`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v11 + 56LL))(v11) )
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
0x180019450  mov     [rsp+arg_0], rbx
0x180019455  mov     [rsp+arg_10], rbp
0x18001945a  push    rsi
0x18001945b  push    rdi
0x18001945c  push    r14
0x18001945e  sub     rsp, 40h
0x180019462  mov     rdi, rdx
0x180019465  mov     rbp, rcx
0x180019468  mov     r8, [rdx+8]
0x18001946c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180019470  test    r8, r8
0x180019473  jz      short loc_180019484
0x180019475  mov     rax, r9
0x180019478  inc     rax
0x18001947b  cmp     byte ptr [rax+r8], 0
0x180019480  jnz     short loc_180019478
0x180019482  jmp     short loc_180019486
0x180019484  xor     eax, eax
0x180019486  lea     r14d, [rax+1]
0x18001948a  movsxd  rcx, r14d
0x18001948d  mov     eax, 2
0x180019492  mul     rcx
0x180019495  mov     rsi, rax
0x180019498  cmovb   rsi, r9
0x18001949c  mov     rcx, rsi; Size
0x18001949f  call    cs:__imp_malloc
0x1800194a5  mov     rbx, rax
0x1800194a8  test    rax, rax
0x1800194ab  jz      loc_180019567
0x1800194b1  mov     r8, rsi; Size
0x1800194b4  xor     edx, edx; Val
0x1800194b6  mov     rcx, rax; void *
0x1800194b9  call    memset
0x1800194be  mov     [rsp+58h+arg_8], rbx
0x1800194c3  mov     r8d, r14d; int
0x1800194c6  mov     rdx, rbx; wchar_t *
0x1800194c9  mov     rcx, [rdi+8]; char *
0x1800194cd  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x1800194d2  mov     rcx, [rbp+8]
0x1800194d6  test    rcx, rcx
0x1800194d9  jz      loc_180019571
0x1800194df  nop
0x1800194e0  mov     rax, [rcx]
0x1800194e3  mov     rdx, rbx
0x1800194e6  mov     rax, [rax+30h]
0x1800194ea  call    cs:__guard_dispatch_icall_fptr
0x1800194f0  test    al, al
0x1800194f2  jz      loc_180019581
0x1800194f8  mov     rcx, [rbp+8]
0x1800194fc  test    rcx, rcx
0x1800194ff  jz      loc_1800195A9
0x180019505  mov     rax, [rcx]
0x180019508  lea     rdx, [rdi+10h]
0x18001950c  cmp     qword ptr [rdx+18h], 7
0x180019511  jbe     short loc_180019516
0x180019513  mov     rdx, [rdx]
0x180019516  mov     rax, [rax+38h]
0x18001951a  call    cs:__guard_dispatch_icall_fptr
0x180019520  test    al, al
0x180019522  jz      short loc_180019540
0x180019524  mov     rcx, rbx
0x180019527  mov     rbx, [rsp+58h+arg_0]
0x18001952c  mov     rbp, [rsp+58h+arg_10]
0x180019531  add     rsp, 40h
0x180019535  pop     r14
0x180019537  pop     rdi
0x180019538  pop     rsi
0x180019539  jmp     cs:__imp_free
0x180019540  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x180019547  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001954c  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180019551  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180019558  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001955d  call    _CxxThrowException
0x180019563  jmp     short loc_180019566
0x180019566  nop
0x180019567  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180019571  xor     edx, edx; struct CrashContext *
0x180019573  mov     ecx, 1E3C3840h; unsigned int
0x180019578  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18001957e  jmp     short $+2
0x180019580  nop
0x180019581  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x180019588  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001958d  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180019592  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180019599  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001959e  call    _CxxThrowException
0x1800195a4  jmp     short loc_1800195A8
0x1800195a8  nop
0x1800195a9  xor     edx, edx; struct CrashContext *
0x1800195ab  mov     ecx, 1E3C3840h; unsigned int
0x1800195b0  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
