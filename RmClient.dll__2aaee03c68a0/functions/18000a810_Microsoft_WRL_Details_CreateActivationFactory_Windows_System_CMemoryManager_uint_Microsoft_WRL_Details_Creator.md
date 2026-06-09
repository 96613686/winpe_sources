# Microsoft::WRL::Details::CreateActivationFactory<Windows::System::CMemoryManager>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x18000a810`
- end: `0x18000a8de`
- name: `??$CreateActivationFactory@VCMemoryManager@System@Windows@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(_BYTE *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000a810`
- `0x18000a8e4`
- `0x18000a950`
- `0x18000acd0`
- `0x180013ce8`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Windows::System::CMemoryManager>(
        _BYTE *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  Windows::System::CMemoryManager *v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdi
  volatile int *v11; // rdx
  int CanCastTo; // ebp
  __int64 result; // rax

  v8 = (Windows::System::CMemoryManager *)operator new(0x88u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v8 )
    return 2147942414LL;
  v9 = Windows::System::CMemoryManager::CMemoryManager(v8);
  v10 = v9;
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::System::IMemoryManagerStatics,Windows::System::IMemoryManagerStatics2,Windows::System::IMemoryManagerStatics3,Windows::System::IMemoryManagerStatics4>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
                v10,
                a3,
                a4);
  if ( CanCastTo >= 0 )
  {
    if ( (*a1 & 4) == 0 )
      Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v10 + 108), v11);
    *(_DWORD *)(v10 + 128) = *(_DWORD *)a1;
    result = 0;
    *(_QWORD *)(v10 + 120) = a2;
  }
  else
  {
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    return (unsigned int)CanCastTo;
  }
  return result;
}

```

## disassembly

```asm
0x18000a810  push    rbx
0x18000a812  push    rbp
0x18000a813  push    rsi
0x18000a814  push    r14
0x18000a816  sub     rsp, 28h
0x18000a81a  mov     rsi, rdx
0x18000a81d  mov     rbx, rcx
0x18000a820  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a827  mov     ecx, 88h; unsigned __int64
0x18000a82c  mov     rbp, r9
0x18000a82f  mov     r14, r8
0x18000a832  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a837  test    rax, rax
0x18000a83a  jz      loc_18000A8D7
0x18000a840  mov     rcx, rax; this
0x18000a843  mov     [rsp+48h+arg_0], rdi
0x18000a848  call    ??0CMemoryManager@System@Windows@@QEAA@XZ; Windows::System::CMemoryManager::CMemoryManager(void)
0x18000a84d  mov     rdi, rax
0x18000a850  test    rax, rax
0x18000a853  jz      short loc_18000A873
0x18000a855  mov     rcx, [rax]
0x18000a858  mov     rax, [rcx+8]
0x18000a85c  mov     rcx, rdi
0x18000a85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a864  mov     rcx, [rdi]
0x18000a867  mov     rax, [rcx+10h]
0x18000a86b  mov     rcx, rdi
0x18000a86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a873  mov     r8, rbp
0x18000a876  mov     rdx, r14
0x18000a879  mov     rcx, rdi
0x18000a87c  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@U?$Implements@UIMemoryManagerStatics@System@Windows@@UIMemoryManagerStatics2@23@UIMemoryManagerStatics3@23@UIMemoryManagerStatics4@23@@23@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::System::IMemoryManagerStatics,Windows::System::IMemoryManagerStatics2,Windows::System::IMemoryManagerStatics3,Windows::System::IMemoryManagerStatics4>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x18000a881  mov     ebp, eax
0x18000a883  test    eax, eax
0x18000a885  jns     short loc_18000A8AC
0x18000a887  test    rdi, rdi
0x18000a88a  jz      short loc_18000A89B
0x18000a88c  mov     rcx, [rdi]
0x18000a88f  mov     rax, [rcx+10h]
0x18000a893  mov     rcx, rdi
0x18000a896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a89b  mov     rdi, [rsp+48h+arg_0]
0x18000a8a0  mov     eax, ebp
0x18000a8a2  add     rsp, 28h
0x18000a8a6  pop     r14
0x18000a8a8  pop     rsi
0x18000a8a9  pop     rbp
0x18000a8aa  pop     rbx
0x18000a8ab  retn
0x18000a8ac  test    byte ptr [rbx], 4
0x18000a8af  jnz     short loc_18000A8BA
0x18000a8b1  lea     rcx, [rdi+6Ch]; this
0x18000a8b5  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18000a8ba  mov     eax, [rbx]
0x18000a8bc  mov     [rdi+80h], eax
0x18000a8c2  xor     eax, eax
0x18000a8c4  mov     [rdi+78h], rsi
0x18000a8c8  mov     rdi, [rsp+48h+arg_0]
0x18000a8cd  add     rsp, 28h
0x18000a8d1  pop     r14
0x18000a8d3  pop     rsi
0x18000a8d4  pop     rbp
0x18000a8d5  pop     rbx
0x18000a8d6  retn
0x18000a8d7  mov     eax, 8007000Eh
0x18000a8dc  jmp     short loc_18000A8A2
```
