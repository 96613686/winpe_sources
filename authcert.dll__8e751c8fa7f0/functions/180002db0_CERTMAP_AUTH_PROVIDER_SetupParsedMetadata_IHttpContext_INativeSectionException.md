# CERTMAP_AUTH_PROVIDER::SetupParsedMetadata(IHttpContext *,INativeSectionException * *)

- ea: `0x180002db0`
- end: `0x180002e95`
- name: `?SetupParsedMetadata@CERTMAP_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(CERTMAP_AUTH_PROVIDER *this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x180002db0`
- `0x180002f24`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall CERTMAP_AUTH_PROVIDER::SetupParsedMetadata(
        CERTMAP_AUTH_PROVIDER *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v5; // rax
  __int64 v6; // rsi
  int v7; // ebx
  CERTMAP_META_STORED_CONTEXT *v8; // rdi

  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
  if ( (**(__int64 (__fastcall ***)(__int64, void *))v6)(v6, s_pModuleContext) )
    return 0;
  v8 = (CERTMAP_META_STORED_CONTEXT *)operator new(0x10u);
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 1;
    *(_QWORD *)v8 = &CERTMAP_META_STORED_CONTEXT::`vftable';
    v7 = CERTMAP_META_STORED_CONTEXT::Initialize(v8, a2, a3);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, CERTMAP_META_STORED_CONTEXT *, void *))(*(_QWORD *)v6 + 8LL))(
             v6,
             v8,
             s_pModuleContext);
      if ( v7 < 0 )
      {
        (**(void (__fastcall ***)(CERTMAP_META_STORED_CONTEXT *))v8)(v8);
        if ( v7 == -2147024811 )
          return 0;
      }
    }
    else
    {
      (**(void (__fastcall ***)(CERTMAP_META_STORED_CONTEXT *))v8)(v8);
    }
    return (unsigned int)v7;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180002db0  push    rbx
0x180002db2  push    rbp
0x180002db3  push    rsi
0x180002db4  push    rdi
0x180002db5  sub     rsp, 28h
0x180002db9  mov     rax, [rdx]
0x180002dbc  mov     rcx, rdx
0x180002dbf  mov     rbp, r8
0x180002dc2  mov     rbx, rdx
0x180002dc5  mov     rax, [rax+0A0h]
0x180002dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dd1  mov     r9, rax
0x180002dd4  mov     rcx, [rax]
0x180002dd7  mov     rax, [rcx+18h]
0x180002ddb  mov     rcx, r9
0x180002dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de3  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180002dea  mov     rsi, rax
0x180002ded  mov     rcx, [rax]
0x180002df0  mov     rax, [rcx]
0x180002df3  mov     rcx, rsi
0x180002df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dfb  test    rax, rax
0x180002dfe  jz      short loc_180002E04
0x180002e00  xor     ebx, ebx
0x180002e02  jmp     short loc_180002E83
0x180002e04  mov     ecx, 10h; Size
0x180002e09  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e0e  mov     rdi, rax
0x180002e11  test    rax, rax
0x180002e14  jz      short loc_180002E87
0x180002e16  lea     rax, ??_7CERTMAP_META_STORED_CONTEXT@@6B@; const CERTMAP_META_STORED_CONTEXT::`vftable'
0x180002e1d  mov     dword ptr [rdi+8], 1
0x180002e24  mov     r8, rbp; struct INativeSectionException **
0x180002e27  mov     [rdi], rax
0x180002e2a  mov     rdx, rbx; struct IHttpContext *
0x180002e2d  mov     rcx, rdi; this
0x180002e30  call    ?Initialize@CERTMAP_META_STORED_CONTEXT@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; CERTMAP_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)
0x180002e35  mov     ebx, eax
0x180002e37  test    eax, eax
0x180002e39  jns     short loc_180002E4B
0x180002e3b  mov     rcx, [rdi]
0x180002e3e  mov     rax, [rcx]
0x180002e41  mov     rcx, rdi
0x180002e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e49  jmp     short loc_180002E83
0x180002e4b  mov     rax, [rsi]
0x180002e4e  mov     rdx, rdi
0x180002e51  mov     r8, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180002e58  mov     rcx, rsi
0x180002e5b  mov     rax, [rax+8]
0x180002e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e64  mov     ebx, eax
0x180002e66  test    eax, eax
0x180002e68  jns     short loc_180002E83
0x180002e6a  mov     rax, [rdi]
0x180002e6d  mov     rcx, rdi
0x180002e70  mov     rax, [rax]
0x180002e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e78  xor     eax, eax
0x180002e7a  cmp     ebx, 80070055h
0x180002e80  cmovz   ebx, eax
0x180002e83  mov     eax, ebx
0x180002e85  jmp     short loc_180002E8C
0x180002e87  mov     eax, 80070008h
0x180002e8c  add     rsp, 28h
0x180002e90  pop     rdi
0x180002e91  pop     rsi
0x180002e92  pop     rbp
0x180002e93  pop     rbx
0x180002e94  retn
```
