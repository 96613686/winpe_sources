# BASIC_AUTH_PROVIDER::SetupParsedMetadata(IHttpContext *,INativeSectionException * *)

- ea: `0x1800037b0`
- end: `0x1800038b0`
- name: `?SetupParsedMetadata@BASIC_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `256`
- prototype: `int(BASIC_AUTH_PROVIDER *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x1800037b0`
- `0x18000394c`
- `0x180006010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180003832`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000383c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003832`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000383c`

## pseudocode

```c
__int64 __fastcall BASIC_AUTH_PROVIDER::SetupParsedMetadata(
        BASIC_AUTH_PROVIDER *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v5; // rax
  __int64 v6; // rsi
  int v7; // edi
  _DWORD *v8; // rbx

  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
  if ( (**(__int64 (__fastcall ***)(__int64, void *))v6)(v6, s_pModuleContext) )
    return 0;
  v8 = operator new(0x88u);
  if ( v8 )
  {
    v8[2] = 1;
    *(_QWORD *)v8 = &BASIC_META_STORED_CONTEXT::`vftable';
    STRU::STRU((STRU *)(v8 + 4));
    STRU::STRU((STRU *)(v8 + 18));
    v7 = BASIC_META_STORED_CONTEXT::Initialize((BASIC_META_STORED_CONTEXT *)v8, a2, a3);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, _DWORD *, void *))(*(_QWORD *)v6 + 8LL))(v6, v8, s_pModuleContext);
      if ( v7 < 0 )
      {
        (**(void (__fastcall ***)(_DWORD *))v8)(v8);
        if ( v7 == -2147024811 )
          return 0;
      }
    }
    else
    {
      (**(void (__fastcall ***)(_DWORD *))v8)(v8);
    }
    return (unsigned int)v7;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x1800037b0  push    rbx
0x1800037b2  push    rbp
0x1800037b3  push    rsi
0x1800037b4  push    rdi
0x1800037b5  sub     rsp, 28h
0x1800037b9  mov     rax, [rdx]
0x1800037bc  mov     rcx, rdx
0x1800037bf  mov     rbp, r8
0x1800037c2  mov     rdi, rdx
0x1800037c5  mov     rax, [rax+0A0h]
0x1800037cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037d1  mov     r9, rax
0x1800037d4  mov     rcx, [rax]
0x1800037d7  mov     rax, [rcx+18h]
0x1800037db  mov     rcx, r9
0x1800037de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e3  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x1800037ea  mov     rsi, rax
0x1800037ed  mov     rcx, [rax]
0x1800037f0  mov     rax, [rcx]
0x1800037f3  mov     rcx, rsi
0x1800037f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037fb  test    rax, rax
0x1800037fe  jz      short loc_180003807
0x180003800  xor     edi, edi
0x180003802  jmp     loc_18000389E
0x180003807  mov     ecx, 88h; Size
0x18000380c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003811  mov     rbx, rax
0x180003814  test    rax, rax
0x180003817  jz      loc_1800038A2
0x18000381d  lea     rax, ??_7BASIC_META_STORED_CONTEXT@@6B@; const BASIC_META_STORED_CONTEXT::`vftable'
0x180003824  mov     dword ptr [rbx+8], 1
0x18000382b  lea     rcx, [rbx+10h]
0x18000382f  mov     [rbx], rax
0x180003832  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003838  lea     rcx, [rbx+48h]
0x18000383c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003842  mov     r8, rbp; struct INativeSectionException **
0x180003845  mov     rdx, rdi; struct IHttpContext *
0x180003848  mov     rcx, rbx; this
0x18000384b  call    ?Initialize@BASIC_META_STORED_CONTEXT@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; BASIC_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)
0x180003850  mov     edi, eax
0x180003852  test    eax, eax
0x180003854  jns     short loc_180003866
0x180003856  mov     rcx, [rbx]
0x180003859  mov     rax, [rcx]
0x18000385c  mov     rcx, rbx
0x18000385f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003864  jmp     short loc_18000389E
0x180003866  mov     rax, [rsi]
0x180003869  mov     rdx, rbx
0x18000386c  mov     r8, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180003873  mov     rcx, rsi
0x180003876  mov     rax, [rax+8]
0x18000387a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000387f  mov     edi, eax
0x180003881  test    eax, eax
0x180003883  jns     short loc_18000389E
0x180003885  mov     rax, [rbx]
0x180003888  mov     rcx, rbx
0x18000388b  mov     rax, [rax]
0x18000388e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003893  xor     eax, eax
0x180003895  cmp     edi, 80070055h
0x18000389b  cmovz   edi, eax
0x18000389e  mov     eax, edi
0x1800038a0  jmp     short loc_1800038A7
0x1800038a2  mov     eax, 80070008h
0x1800038a7  add     rsp, 28h
0x1800038ab  pop     rdi
0x1800038ac  pop     rsi
0x1800038ad  pop     rbp
0x1800038ae  pop     rbx
0x1800038af  retn
```
