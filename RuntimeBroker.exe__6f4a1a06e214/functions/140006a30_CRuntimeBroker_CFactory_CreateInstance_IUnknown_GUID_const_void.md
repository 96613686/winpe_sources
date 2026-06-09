# CRuntimeBroker::CFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140006a30`
- end: `0x140006ac9`
- name: `?CreateInstance@CFactory@CRuntimeBroker@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `153`
- prototype: `__int64 __fastcall(CRuntimeBroker::CFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006a30`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140006a56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140006a56`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x140006a75`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x140006a75`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::CFactory::CreateInstance(
        CRuntimeBroker::CFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  _DWORD *v6; // rbx
  unsigned int v7; // edi

  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v6 = CoTaskMemAlloc(0x10u);
  if ( !v6 )
    return 2147942414LL;
  v6[2] = 1;
  *(_QWORD *)v6 = &CRuntimeBroker::`vftable';
  CoAddRefServerProcess();
  v7 = (**(__int64 (__fastcall ***)(_DWORD *, const struct _GUID *, void **))v6)(v6, a3, a4);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  return v7;
}

```

## disassembly

```asm
0x140006a30  mov     [rsp+arg_8], rsi
0x140006a35  push    rdi
0x140006a36  sub     rsp, 20h
0x140006a3a  mov     qword ptr [r9], 0
0x140006a41  mov     rdi, r9
0x140006a44  mov     rsi, r8
0x140006a47  test    rdx, rdx
0x140006a4a  jnz     short loc_140006AB9
0x140006a4c  mov     ecx, 10h; cb
0x140006a51  mov     [rsp+28h+arg_0], rbx
0x140006a56  call    cs:__imp_CoTaskMemAlloc
0x140006a5c  mov     rbx, rax
0x140006a5f  test    rax, rax
0x140006a62  jz      short loc_140006AB2
0x140006a64  lea     rax, ??_7CRuntimeBroker@@6B@; const CRuntimeBroker::`vftable'
0x140006a6b  mov     dword ptr [rbx+8], 1
0x140006a72  mov     [rbx], rax
0x140006a75  call    cs:__imp_CoAddRefServerProcess
0x140006a7b  mov     rax, [rbx]
0x140006a7e  mov     r8, rdi
0x140006a81  mov     rdx, rsi
0x140006a84  mov     rcx, rbx
0x140006a87  mov     rax, [rax]
0x140006a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a8f  mov     rcx, [rbx]
0x140006a92  mov     edi, eax
0x140006a94  mov     rax, [rcx+10h]
0x140006a98  mov     rcx, rbx
0x140006a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006aa0  mov     eax, edi
0x140006aa2  mov     rbx, [rsp+28h+arg_0]
0x140006aa7  mov     rsi, [rsp+28h+arg_8]
0x140006aac  add     rsp, 20h
0x140006ab0  pop     rdi
0x140006ab1  retn
0x140006ab2  mov     eax, 8007000Eh
0x140006ab7  jmp     short loc_140006AA2
0x140006ab9  mov     rsi, [rsp+28h+arg_8]
0x140006abe  mov     eax, 80040110h
0x140006ac3  add     rsp, 20h
0x140006ac7  pop     rdi
0x140006ac8  retn
```
