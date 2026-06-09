# ipx::mtf::CompositeFactory::_CreateIUnknownInstance(IUnknown *,IUnknown * *)

- ea: `0x180007da0`
- end: `0x180007de9`
- name: `?_CreateIUnknownInstance@CompositeFactory@mtf@ipx@@UEAAJPEAUIUnknown@@PEAPEAU4@@Z`
- size: `73`
- prototype: `__int64 __fastcall(ipx::mtf::CompositeFactory *__hidden this, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001fc4`
- `0x180007da0`
- `0x1800251b8`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CompositeFactory::_CreateIUnknownInstance(
        ipx::mtf::CompositeFactory *this,
        struct IUnknown *a2,
        struct IUnknown **a3)
{
  CMtfPredictionCandidate *v5; // rax

  if ( a2 )
    return 2147746064LL;
  v5 = (CMtfPredictionCandidate *)operator new(0x98u);
  if ( v5 )
    v5 = CMtfPredictionCandidate::CMtfPredictionCandidate(v5);
  *a3 = (struct IUnknown *)(((unsigned __int64)v5 + 8) & -(__int64)(v5 != 0));
  return 0;
}

```

## disassembly

```asm
0x180007da0  push    rbx
0x180007da2  sub     rsp, 20h
0x180007da6  mov     rbx, r8
0x180007da9  test    rdx, rdx
0x180007dac  jz      short loc_180007DB5
0x180007dae  mov     eax, 80040110h
0x180007db3  jmp     short loc_180007DE3
0x180007db5  mov     ecx, 98h; Size
0x180007dba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007dbf  mov     [rsp+28h+arg_8], rax
0x180007dc4  test    rax, rax
0x180007dc7  jz      short loc_180007DD1
0x180007dc9  mov     rcx, rax; this
0x180007dcc  call    ??0CMtfPredictionCandidate@@QEAA@XZ; CMtfPredictionCandidate::CMtfPredictionCandidate(void)
0x180007dd1  lea     rcx, [rax+8]
0x180007dd5  neg     rax
0x180007dd8  sbb     rax, rax
0x180007ddb  and     rax, rcx
0x180007dde  mov     [rbx], rax
0x180007de1  xor     eax, eax
0x180007de3  add     rsp, 20h
0x180007de7  pop     rbx
0x180007de8  retn
```
