# Mso::Logging::StructuredTraceJsonSerializer::Visit(Mso::Diagnostics::ClassifiedStructuredObject<float> const &)

- ea: `0x180018040`
- end: `0x180018194`
- name: `?Visit@StructuredTraceJsonSerializer@Logging@Mso@@UEAAXAEBU?$ClassifiedStructuredObject@M@Diagnostics@3@@Z`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000a580`
- `0x18000ab0c`
- `0x180012318`
- `0x180018040`
- `0x18001e944`
- `0x1800282a0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001808f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001808f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001811b`

## string_xrefs

- `0x180018161`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value's name.`
- `0x180018122`: `StructuredTraceJsonSerializer::Visit failed to write classified structured value.`

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
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v11 + 96LL))(v11) )
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
0x180018040  mov     [rsp+arg_0], rbx
0x180018045  mov     [rsp+arg_10], rbp
0x18001804a  push    rsi
0x18001804b  push    rdi
0x18001804c  push    r14
0x18001804e  sub     rsp, 40h
0x180018052  mov     rdi, rdx
0x180018055  mov     rbp, rcx
0x180018058  mov     r8, [rdx+8]
0x18001805c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180018060  test    r8, r8
0x180018063  jz      short loc_180018074
0x180018065  mov     rax, r9
0x180018068  inc     rax
0x18001806b  cmp     byte ptr [rax+r8], 0
0x180018070  jnz     short loc_180018068
0x180018072  jmp     short loc_180018076
0x180018074  xor     eax, eax
0x180018076  lea     r14d, [rax+1]
0x18001807a  movsxd  rcx, r14d
0x18001807d  mov     eax, 2
0x180018082  mul     rcx
0x180018085  mov     rsi, rax
0x180018088  cmovb   rsi, r9
0x18001808c  mov     rcx, rsi; Size
0x18001808f  call    cs:__imp_malloc
0x180018095  mov     rbx, rax
0x180018098  test    rax, rax
0x18001809b  jz      loc_180018148
0x1800180a1  mov     r8, rsi; Size
0x1800180a4  xor     edx, edx; Val
0x1800180a6  mov     rcx, rax; void *
0x1800180a9  call    memset
0x1800180ae  mov     [rsp+58h+arg_8], rbx
0x1800180b3  mov     r8d, r14d; int
0x1800180b6  mov     rdx, rbx; wchar_t *
0x1800180b9  mov     rcx, [rdi+8]; char *
0x1800180bd  call    ?MsoSzToWzSimple@@YAXPEBDPEA_WH@Z; MsoSzToWzSimple(char const *,wchar_t *,int)
0x1800180c2  mov     rcx, [rbp+8]
0x1800180c6  test    rcx, rcx
0x1800180c9  jz      loc_180018151
0x1800180cf  mov     rax, [rcx]
0x1800180d2  mov     rdx, rbx
0x1800180d5  mov     rax, [rax+30h]
0x1800180d9  call    cs:__guard_dispatch_icall_fptr
0x1800180df  test    al, al
0x1800180e1  jz      short loc_180018161
0x1800180e3  mov     rcx, [rbp+8]
0x1800180e7  test    rcx, rcx
0x1800180ea  jz      loc_180018187
0x1800180f0  mov     rax, [rcx]
0x1800180f3  movss   xmm1, dword ptr [rdi+10h]
0x1800180f8  mov     rax, [rax+60h]
0x1800180fc  call    cs:__guard_dispatch_icall_fptr
0x180018102  test    al, al
0x180018104  jz      short loc_180018122
0x180018106  mov     rcx, rbx
0x180018109  mov     rbx, [rsp+58h+arg_0]
0x18001810e  mov     rbp, [rsp+58h+arg_10]
0x180018113  add     rsp, 40h
0x180018117  pop     r14
0x180018119  pop     rdi
0x18001811a  pop     rsi
0x18001811b  jmp     cs:__imp_free
0x180018122  lea     rdx, aStructuredtrac_5; "StructuredTraceJsonSerializer::Visit fa"...
0x180018129  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001812e  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018133  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001813a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001813f  call    _CxxThrowException
0x180018145  jmp     short $+2
0x180018147  nop
0x180018148  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001814e  jmp     short $+2
0x180018150  nop
0x180018151  xor     edx, edx; struct CrashContext *
0x180018153  mov     ecx, 1E3C3840h; unsigned int
0x180018158  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18001815e  jmp     short $+2
0x180018160  nop
0x180018161  lea     rdx, aStructuredtrac_8; "StructuredTraceJsonSerializer::Visit fa"...
0x180018168  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001816d  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180018172  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018179  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001817e  call    _CxxThrowException
0x180018184  jmp     short $+2
0x180018186  nop
0x180018187  xor     edx, edx; struct CrashContext *
0x180018189  mov     ecx, 1E3C3840h; unsigned int
0x18001818e  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
