# CStubAVIStream::Create(IUnknown *,IRpcStubBuffer * *)

- ea: `0x18000ec20`
- end: `0x18000eccc`
- name: `?Create@CStubAVIStream@@SAJPEAUIUnknown@@PEAPEAUIRpcStubBuffer@@@Z`
- size: `172`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IRpcStubBuffer **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ee80`

## callees

- `0x180001008`
- `0x18000ec20`
- `0x1800102b8`
- `0x180018010`

## import_xrefs

- `ole32!OleInitialize` at `0x18000ec74`
- `ole32!OleInitialize` at `0x18000ec74`

## pseudocode

```c
__int64 __fastcall CStubAVIStream::Create(struct IUnknown *a1, struct IRpcStubBuffer **a2)
{
  struct IRpcStubBuffer *v4; // rbx
  unsigned int v5; // esi

  *a2 = 0;
  v4 = (struct IRpcStubBuffer *)operator new(0x18u);
  if ( !v4 )
    return 2147942414LL;
  ++uUseCount;
  v4->lpVtbl = (struct IRpcStubBufferVtbl *)&CStubAVIStream::`vftable';
  LODWORD(v4[1].lpVtbl) = 1;
  v4[2].lpVtbl = 0;
  RegisterStubUsage();
  if ( OleInitialize(0) >= 0 )
    _InterlockedIncrement(&glOleRefCount);
  v5 = ((__int64 (__fastcall *)(struct IRpcStubBuffer *, struct IUnknown *))v4->lpVtbl->Connect)(v4, a1);
  if ( v5 )
  {
    ((void (__fastcall *)(struct IRpcStubBuffer *))v4->lpVtbl->Release)(v4);
    return v5;
  }
  else
  {
    *a2 = v4;
    return 0;
  }
}

```

## disassembly

```asm
0x18000ec20  mov     [rsp+arg_0], rbx
0x18000ec25  mov     [rsp+arg_8], rsi
0x18000ec2a  push    rdi
0x18000ec2b  sub     rsp, 20h
0x18000ec2f  mov     rsi, rcx
0x18000ec32  mov     qword ptr [rdx], 0
0x18000ec39  mov     ecx, 18h; Size
0x18000ec3e  mov     rdi, rdx
0x18000ec41  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ec46  mov     rbx, rax
0x18000ec49  test    rax, rax
0x18000ec4c  jz      short loc_18000ECB7
0x18000ec4e  inc     cs:uUseCount
0x18000ec54  lea     rax, ??_7CStubAVIStream@@6B@; const CStubAVIStream::`vftable'
0x18000ec5b  mov     [rbx], rax
0x18000ec5e  mov     dword ptr [rbx+8], 1
0x18000ec65  mov     qword ptr [rbx+10h], 0
0x18000ec6d  call    ?RegisterStubUsage@@YAXXZ; RegisterStubUsage(void)
0x18000ec72  xor     ecx, ecx; pvReserved
0x18000ec74  call    cs:__imp_OleInitialize
0x18000ec7a  test    eax, eax
0x18000ec7c  js      short loc_18000EC85
0x18000ec7e  lock inc cs:glOleRefCount
0x18000ec85  mov     rax, [rbx]
0x18000ec88  mov     rdx, rsi
0x18000ec8b  mov     rcx, rbx
0x18000ec8e  mov     rax, [rax+18h]
0x18000ec92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec97  mov     esi, eax
0x18000ec99  test    eax, eax
0x18000ec9b  jz      short loc_18000ECB0
0x18000ec9d  mov     rcx, [rbx]
0x18000eca0  mov     rax, [rcx+10h]
0x18000eca4  mov     rcx, rbx
0x18000eca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecac  mov     eax, esi
0x18000ecae  jmp     short loc_18000ECBC
0x18000ecb0  mov     [rdi], rbx
0x18000ecb3  xor     eax, eax
0x18000ecb5  jmp     short loc_18000ECBC
0x18000ecb7  mov     eax, 8007000Eh
0x18000ecbc  mov     rbx, [rsp+28h+arg_0]
0x18000ecc1  mov     rsi, [rsp+28h+arg_8]
0x18000ecc6  add     rsp, 20h
0x18000ecca  pop     rdi
0x18000eccb  retn
```
