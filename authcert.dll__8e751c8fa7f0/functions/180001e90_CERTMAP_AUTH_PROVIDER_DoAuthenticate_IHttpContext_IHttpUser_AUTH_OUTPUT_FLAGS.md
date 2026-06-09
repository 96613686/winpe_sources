# CERTMAP_AUTH_PROVIDER::DoAuthenticate(IHttpContext *,IHttpUser * *,AUTH_OUTPUT_FLAGS *)

- ea: `0x180001e90`
- end: `0x180001f58`
- name: `?DoAuthenticate@CERTMAP_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@PEAPEAVIHttpUser@@PEAW4AUTH_OUTPUT_FLAGS@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(CERTMAP_AUTH_PROVIDER *this, struct IHttpContext *, struct IHttpUser **, enum AUTH_OUTPUT_FLAGS *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001008`
- `0x180001ad8`
- `0x180001e90`
- `0x180003c9c`
- `0x180005010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180001ef1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001ef1`

## pseudocode

```c
__int64 __fastcall CERTMAP_AUTH_PROVIDER::DoAuthenticate(
        CERTMAP_AUTH_PROVIDER *this,
        struct IHttpContext *a2,
        struct IHttpUser **a3,
        enum AUTH_OUTPUT_FLAGS *a4)
{
  __int64 v7; // rax
  void *v8; // rbp
  _QWORD *v9; // rbx
  int v10; // edi
  int v11; // r8d

  v7 = (*(__int64 (__fastcall **)(struct IHttpContext *, struct IHttpContext *, struct IHttpUser **, enum AUTH_OUTPUT_FLAGS *))(*(_QWORD *)a2 + 24LL))(
         a2,
         a2,
         a3,
         a4);
  v8 = *(void **)(*(_QWORD *)(*(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7) + 840) + 32LL)
                + 16LL);
  v9 = operator new(0x58u);
  if ( !v9 )
    return 2147942408LL;
  *v9 = &CERTMAP_USER_CONTEXT::`vftable';
  STRU::STRU((STRU *)(v9 + 2));
  v9[10] = 0;
  v9[9] = 0;
  *((_DWORD *)v9 + 2) = 1;
  v10 = CERTMAP_USER_CONTEXT::Create((CERTMAP_USER_CONTEXT *)v9, v8, (struct _EXPLICIT_ACCESS_W *)((char *)this + 64));
  if ( v10 >= 0 )
  {
    *a3 = (struct IHttpUser *)v9;
    TraceAuthSucceeded(a2, (struct IHttpUser *)v9, v11);
    return 0;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*v9 + 56LL))(v9);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x180001e90  push    rbx
0x180001e92  push    rbp
0x180001e93  push    rsi
0x180001e94  push    rdi
0x180001e95  push    r14
0x180001e97  sub     rsp, 20h
0x180001e9b  mov     rax, [rdx]
0x180001e9e  mov     rdi, rcx
0x180001ea1  mov     rcx, rdx
0x180001ea4  mov     r14, r8
0x180001ea7  mov     rsi, rdx
0x180001eaa  mov     rax, [rax+18h]
0x180001eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eb3  mov     rcx, rax
0x180001eb6  mov     r9, [rax]
0x180001eb9  mov     rax, [r9+8]
0x180001ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ec2  mov     rcx, [rax+348h]
0x180001ec9  mov     rax, [rcx+20h]
0x180001ecd  mov     ecx, 58h ; 'X'; Size
0x180001ed2  mov     rbp, [rax+10h]
0x180001ed6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001edb  mov     rbx, rax
0x180001ede  test    rax, rax
0x180001ee1  jz      short loc_180001F48
0x180001ee3  lea     rax, ??_7CERTMAP_USER_CONTEXT@@6B@; const CERTMAP_USER_CONTEXT::`vftable'
0x180001eea  lea     rcx, [rbx+10h]
0x180001eee  mov     [rbx], rax
0x180001ef1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001ef7  lea     r8, [rdi+40h]; struct _EXPLICIT_ACCESS_W *
0x180001efb  mov     qword ptr [rbx+50h], 0
0x180001f03  mov     rdx, rbp; void *
0x180001f06  mov     qword ptr [rbx+48h], 0
0x180001f0e  mov     rcx, rbx; this
0x180001f11  mov     dword ptr [rbx+8], 1
0x180001f18  call    ?Create@CERTMAP_USER_CONTEXT@@QEAAJPEAXPEAU_EXPLICIT_ACCESS_W@@@Z; CERTMAP_USER_CONTEXT::Create(void *,_EXPLICIT_ACCESS_W *)
0x180001f1d  mov     edi, eax
0x180001f1f  test    eax, eax
0x180001f21  jns     short loc_180001F36
0x180001f23  mov     rcx, [rbx]
0x180001f26  mov     rax, [rcx+38h]
0x180001f2a  mov     rcx, rbx
0x180001f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f32  mov     eax, edi
0x180001f34  jmp     short loc_180001F4D
0x180001f36  mov     rdx, rbx; struct IHttpUser *
0x180001f39  mov     [r14], rbx
0x180001f3c  mov     rcx, rsi; struct IHttpContext *
0x180001f3f  call    ?TraceAuthSucceeded@@YAJPEAVIHttpContext@@PEAVIHttpUser@@H@Z; TraceAuthSucceeded(IHttpContext *,IHttpUser *,int)
0x180001f44  xor     eax, eax
0x180001f46  jmp     short loc_180001F4D
0x180001f48  mov     eax, 80070008h
0x180001f4d  add     rsp, 20h
0x180001f51  pop     r14
0x180001f53  pop     rdi
0x180001f54  pop     rsi
0x180001f55  pop     rbp
0x180001f56  pop     rbx
0x180001f57  retn
```
