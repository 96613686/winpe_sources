# CAVICmpStream::Create(IUnknown *,_GUID const &,void * *)

- ea: `0x18000d49c`
- end: `0x18000d589`
- name: `?Create@CAVICmpStream@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `237`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008a80`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000d49c`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CAVICmpStream::Create(struct IUnknown *a1, const struct _GUID *a2, void **a3)
{
  struct IUnknown *v6; // rax
  struct IUnknown *v7; // rbx
  int v8; // edi

  v6 = (struct IUnknown *)operator new(0x190u);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  v6[1].lpVtbl = (struct IUnknownVtbl *)v6;
  v6->lpVtbl = (struct IUnknownVtbl *)&CAVICmpStream::CUnknownImpl::`vftable';
  LODWORD(v6[2].lpVtbl) = 0;
  v6[3].lpVtbl = (struct IUnknownVtbl *)&CAVICmpStream::CS::`vftable';
  if ( a1 )
    v6 = a1;
  v7[4].lpVtbl = (struct IUnknownVtbl *)v7;
  v7[32].lpVtbl = 0;
  v7[33].lpVtbl = 0;
  v7[35].lpVtbl = 0;
  v7[36].lpVtbl = 0;
  v7[38].lpVtbl = 0;
  v7[40].lpVtbl = 0;
  LODWORD(v7[41].lpVtbl) = 0;
  v7[42].lpVtbl = 0;
  LODWORD(v7[43].lpVtbl) = 0;
  v7[45].lpVtbl = 0;
  LODWORD(v7[46].lpVtbl) = 0;
  v7[5].lpVtbl = (struct IUnknownVtbl *)v6;
  v8 = ((__int64 (__fastcall *)(struct IUnknown *, const struct _GUID *, void **))CAVICmpStream::CUnknownImpl::`vftable')(
         v7,
         a2,
         a3);
  if ( v8 < 0 )
  {
    v7[3].lpVtbl = (struct IUnknownVtbl *)&CAVICmpStream::CS::`vftable';
    operator delete(v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d49c  push    rbx
0x18000d49e  push    rbp
0x18000d49f  push    rsi
0x18000d4a0  push    rdi
0x18000d4a1  push    r12
0x18000d4a3  push    r14
0x18000d4a5  sub     rsp, 28h
0x18000d4a9  mov     rdi, rcx
0x18000d4ac  mov     rsi, r8
0x18000d4af  mov     ecx, 190h; Size
0x18000d4b4  mov     rbp, rdx
0x18000d4b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d4bc  xor     r14d, r14d
0x18000d4bf  mov     rbx, rax
0x18000d4c2  test    rax, rax
0x18000d4c5  jz      loc_18000D577
0x18000d4cb  mov     [rbx+8], rbx
0x18000d4cf  lea     rax, ??_7CUnknownImpl@CAVICmpStream@@6B@; const CAVICmpStream::CUnknownImpl::`vftable'
0x18000d4d6  mov     [rbx], rax
0x18000d4d9  lea     r12, ??_7CS@CAVICmpStream@@6B@; const CAVICmpStream::CS::`vftable'
0x18000d4e0  mov     [rbx+10h], r14d
0x18000d4e4  test    rdi, rdi
0x18000d4e7  mov     [rbx+18h], r12
0x18000d4eb  mov     rax, rbx
0x18000d4ee  cmovnz  rax, rdi
0x18000d4f2  mov     [rbx+20h], rbx
0x18000d4f6  mov     [rbx+100h], r14
0x18000d4fd  mov     r8, rsi
0x18000d500  mov     [rbx+108h], r14
0x18000d507  mov     rdx, rbp
0x18000d50a  mov     [rbx+118h], r14
0x18000d511  mov     rcx, rbx
0x18000d514  mov     [rbx+120h], r14
0x18000d51b  mov     [rbx+130h], r14
0x18000d522  mov     [rbx+140h], r14
0x18000d529  mov     [rbx+148h], r14d
0x18000d530  mov     [rbx+150h], r14
0x18000d537  mov     [rbx+158h], r14d
0x18000d53e  mov     [rbx+168h], r14
0x18000d545  mov     [rbx+170h], r14d
0x18000d54c  mov     [rbx+28h], rax
0x18000d550  mov     rax, cs:??_7CUnknownImpl@CAVICmpStream@@6B@; const CAVICmpStream::CUnknownImpl::`vftable'
0x18000d557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d55c  mov     edi, eax
0x18000d55e  test    eax, eax
0x18000d560  jns     short loc_18000D573
0x18000d562  mov     edx, 190h; unsigned __int64
0x18000d567  mov     [rbx+18h], r12
0x18000d56b  mov     rcx, rbx; void *
0x18000d56e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d573  mov     eax, edi
0x18000d575  jmp     short loc_18000D57C
0x18000d577  mov     eax, 8007000Eh
0x18000d57c  add     rsp, 28h
0x18000d580  pop     r14
0x18000d582  pop     r12
0x18000d584  pop     rdi
0x18000d585  pop     rsi
0x18000d586  pop     rbp
0x18000d587  pop     rbx
0x18000d588  retn
```
