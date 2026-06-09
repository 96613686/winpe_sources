# CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(_GUID const &,IUnknown *,MARSHAL_KIND)

- ea: `0x18004ed6c`
- end: `0x18004ee2f`
- name: `?RuntimeClassInitialize@CMarshalStream@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z`
- size: `195`
- prototype: `int __high(const struct _GUID *, struct IUnknown *, enum MARSHAL_KIND)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003f194`

## callees

- `0x180011328`
- `0x18004ed6c`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ed81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ed81`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18004ee1c`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18004ee1c`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18004edb7`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18004edb7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(
        __int64 a1,
        const IID *a2,
        IUnknown *a3,
        int a4)
{
  __int64 v8; // rax
  unsigned int AgileReference; // ebx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v13; // [rsp+50h] [rbp+8h] BYREF

  *(_DWORD *)(a1 + 40) = GetCurrentThreadId();
  *(_DWORD *)(a1 + 24) = a4;
  if ( a4 == 2 )
  {
    v8 = 0;
    v13 = 0;
    AgileReference = 0;
    if ( a3 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v13);
      AgileReference = RoGetAgileReference(0, a2, a3, &v13);
      v8 = v13;
    }
    v10 = 0;
    v13 = 0;
    v11 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = v8;
    if ( v11 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      v10 = v13;
    }
    if ( v10 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a1 + 16);
    return (unsigned int)CoMarshalInterThreadInterfaceInStream(a2, a3, (LPSTREAM *)(a1 + 16));
  }
  return AgileReference;
}

```

## disassembly

```asm
0x18004ed6c  push    rbx
0x18004ed6e  push    rbp
0x18004ed6f  push    rsi
0x18004ed70  push    rdi
0x18004ed71  sub     rsp, 28h
0x18004ed75  mov     ebx, r9d
0x18004ed78  mov     rsi, r8
0x18004ed7b  mov     rbp, rdx
0x18004ed7e  mov     rdi, rcx
0x18004ed81  call    cs:__imp_GetCurrentThreadId
0x18004ed87  mov     [rdi+28h], eax
0x18004ed8a  mov     [rdi+18h], ebx
0x18004ed8d  cmp     ebx, 2
0x18004ed90  jnz     short loc_18004EE09
0x18004ed92  xor     eax, eax
0x18004ed94  mov     [rsp+48h+arg_0], rax
0x18004ed99  xor     ebx, ebx
0x18004ed9b  test    rsi, rsi
0x18004ed9e  jz      short loc_18004EDC4
0x18004eda0  lea     rcx, [rsp+48h+arg_0]
0x18004eda5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004edaa  lea     r9, [rsp+48h+arg_0]
0x18004edaf  mov     r8, rsi
0x18004edb2  mov     rdx, rbp
0x18004edb5  xor     ecx, ecx
0x18004edb7  call    cs:__imp_RoGetAgileReference
0x18004edbd  mov     ebx, eax
0x18004edbf  mov     rax, [rsp+48h+arg_0]
0x18004edc4  xor     ecx, ecx
0x18004edc6  mov     [rsp+48h+arg_0], rcx
0x18004edcb  mov     rdx, [rdi+20h]
0x18004edcf  mov     [rdi+20h], rax
0x18004edd3  test    rdx, rdx
0x18004edd6  jz      short loc_18004EDEC
0x18004edd8  mov     rax, [rdx]
0x18004eddb  mov     rcx, rdx
0x18004edde  mov     rax, [rax+10h]
0x18004ede2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ede7  mov     rcx, [rsp+48h+arg_0]
0x18004edec  test    rcx, rcx
0x18004edef  jz      short loc_18004EE07
0x18004edf1  mov     [rsp+48h+arg_0], 0
0x18004edfa  mov     rax, [rcx]
0x18004edfd  mov     rax, [rax+10h]
0x18004ee01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee06  nop
0x18004ee07  jmp     short loc_18004EE24
0x18004ee09  lea     rcx, [rdi+10h]
0x18004ee0d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004ee12  lea     r8, [rdi+10h]; ppStm
0x18004ee16  mov     rdx, rsi; pUnk
0x18004ee19  mov     rcx, rbp; riid
0x18004ee1c  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18004ee22  mov     ebx, eax
0x18004ee24  mov     eax, ebx
0x18004ee26  add     rsp, 28h
0x18004ee2a  pop     rdi
0x18004ee2b  pop     rsi
0x18004ee2c  pop     rbp
0x18004ee2d  pop     rbx
0x18004ee2e  retn
```
