# SSPI_AUTH_PROVIDER::SetupParsedAppContext(IHttpContext *,SSPI_APP_CONTEXT * *)

- ea: `0x180005eac`
- end: `0x180005fe8`
- name: `?SetupParsedAppContext@SSPI_AUTH_PROVIDER@@QEAAJPEAVIHttpContext@@PEAPEAVSSPI_APP_CONTEXT@@@Z`
- size: `316`
- prototype: `__int64 __fastcall(SSPI_AUTH_PROVIDER *this, struct IHttpContext *, struct SSPI_APP_CONTEXT **)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800021f0`
- `0x1800048f0`

## callees

- `0x180001024`
- `0x180005eac`
- `0x1800068c0`
- `0x180008b52`
- `0x180009010`

## import_xrefs

- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180005f2a`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180005f2a`

## pseudocode

```c
__int64 __fastcall SSPI_AUTH_PROVIDER::SetupParsedAppContext(
        SSPI_AUTH_PROVIDER *this,
        struct IHttpContext *a2,
        struct SSPI_APP_CONTEXT **a3)
{
  __int64 v5; // rax
  __int64 v6; // rsi
  struct SSPI_APP_CONTEXT *v7; // rax
  _DWORD *v9; // rdi
  int v10; // ebx

  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 8LL))(a2);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
  v7 = (struct SSPI_APP_CONTEXT *)(**(__int64 (__fastcall ***)(__int64, void *))v6)(v6, s_ModuleId);
  if ( v7 )
  {
    *a3 = v7;
    return 0;
  }
  v9 = operator new(0xB0u);
  if ( v9 )
  {
    *(_QWORD *)v9 = &SSPI_APP_CONTEXT::`vftable';
    MULTISZ::MULTISZ((MULTISZ *)(v9 + 26));
    memset_0(v9 + 4, 0, 0x40u);
    v9[4] = 1;
    v9[42] = 0;
    *((_QWORD *)v9 + 20) = 0;
    *((_QWORD *)v9 + 11) = 0;
    v10 = SSPI_APP_CONTEXT::Initialize((SSPI_APP_CONTEXT *)v9, a2);
    if ( v10 < 0 )
    {
      (**(void (__fastcall ***)(void *))v9)(v9);
      return (unsigned int)v10;
    }
    v10 = (*(__int64 (__fastcall **)(__int64, _DWORD *, void *))(*(_QWORD *)v6 + 8LL))(v6, v9, s_ModuleId);
    if ( v10 < 0 )
    {
      (**(void (__fastcall ***)(void *))v9)(v9);
      if ( v10 != -2147024811 )
        return (unsigned int)v10;
      v10 = 0;
    }
    *a3 = (struct SSPI_APP_CONTEXT *)(**(__int64 (__fastcall ***)(__int64, void *))v6)(v6, s_ModuleId);
    return (unsigned int)v10;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180005eac  push    rbx
0x180005eae  push    rsi
0x180005eaf  push    rdi
0x180005eb0  push    r14
0x180005eb2  push    r15
0x180005eb4  sub     rsp, 20h
0x180005eb8  mov     rax, [rdx]
0x180005ebb  mov     rcx, rdx
0x180005ebe  mov     r14, r8
0x180005ec1  mov     r15, rdx
0x180005ec4  mov     rax, [rax+8]
0x180005ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ecd  mov     r9, rax
0x180005ed0  mov     rcx, [rax]
0x180005ed3  mov     rax, [rcx+18h]
0x180005ed7  mov     rcx, r9
0x180005eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005edf  mov     rdx, cs:?s_ModuleId@@3PEAXEA; void * s_ModuleId
0x180005ee6  mov     rsi, rax
0x180005ee9  mov     rcx, [rax]
0x180005eec  mov     rax, [rcx]
0x180005eef  mov     rcx, rsi
0x180005ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef7  test    rax, rax
0x180005efa  jz      short loc_180005F06
0x180005efc  mov     [r14], rax
0x180005eff  xor     eax, eax
0x180005f01  jmp     loc_180005FDC
0x180005f06  mov     ecx, 0B0h; Size
0x180005f0b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005f10  mov     rdi, rax
0x180005f13  test    rax, rax
0x180005f16  jz      loc_180005FD7
0x180005f1c  lea     rax, ??_7SSPI_APP_CONTEXT@@6B@; const SSPI_APP_CONTEXT::`vftable'
0x180005f23  lea     rcx, [rdi+68h]
0x180005f27  mov     [rdi], rax
0x180005f2a  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180005f30  xor     edx, edx; Val
0x180005f32  lea     rcx, [rdi+10h]; void *
0x180005f36  lea     r8d, [rdx+40h]; Size
0x180005f3a  call    memset_0
0x180005f3f  mov     rdx, r15; struct IHttpContext *
0x180005f42  mov     dword ptr [rdi+10h], 1
0x180005f49  mov     rcx, rdi; this
0x180005f4c  mov     dword ptr [rdi+0A8h], 0
0x180005f56  mov     qword ptr [rdi+0A0h], 0
0x180005f61  mov     qword ptr [rdi+58h], 0
0x180005f69  call    ?Initialize@SSPI_APP_CONTEXT@@QEAAJPEAVIHttpContext@@@Z; SSPI_APP_CONTEXT::Initialize(IHttpContext *)
0x180005f6e  mov     ebx, eax
0x180005f70  test    eax, eax
0x180005f72  jns     short loc_180005F86
0x180005f74  mov     rcx, [rdi]
0x180005f77  mov     rax, [rcx]
0x180005f7a  mov     rcx, rdi
0x180005f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f82  mov     eax, ebx
0x180005f84  jmp     short loc_180005FDC
0x180005f86  mov     rax, [rsi]
0x180005f89  mov     rdx, rdi
0x180005f8c  mov     r8, cs:?s_ModuleId@@3PEAXEA; void * s_ModuleId
0x180005f93  mov     rcx, rsi
0x180005f96  mov     rax, [rax+8]
0x180005f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f9f  mov     ebx, eax
0x180005fa1  test    eax, eax
0x180005fa3  jns     short loc_180005FBD
0x180005fa5  mov     rcx, [rdi]
0x180005fa8  mov     rax, [rcx]
0x180005fab  mov     rcx, rdi
0x180005fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fb3  cmp     ebx, 80070055h
0x180005fb9  jnz     short loc_180005F82
0x180005fbb  xor     ebx, ebx
0x180005fbd  mov     rax, [rsi]
0x180005fc0  mov     rcx, rsi
0x180005fc3  mov     rdx, cs:?s_ModuleId@@3PEAXEA; void * s_ModuleId
0x180005fca  mov     rax, [rax]
0x180005fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fd2  mov     [r14], rax
0x180005fd5  jmp     short loc_180005F82
0x180005fd7  mov     eax, 80070008h
0x180005fdc  add     rsp, 20h
0x180005fe0  pop     r15
0x180005fe2  pop     r14
0x180005fe4  pop     rdi
0x180005fe5  pop     rsi
0x180005fe6  pop     rbx
0x180005fe7  retn
```
