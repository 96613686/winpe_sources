# PCLmWriter::PCLmPageImageCalculator::ReInitialize(uint,IPageBitmapProvider *)

- ea: `0x180017350`
- end: `0x180017411`
- name: `?ReInitialize@PCLmPageImageCalculator@PCLmWriter@@QEAAXIPEAUIPageBitmapProvider@@@Z`
- size: `193`
- prototype: `void __fastcall(PCLmWriter::PCLmPageImageCalculator *__hidden this, unsigned int, struct IPageBitmapProvider *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010290`

## callees

- `0x18000df30`
- `0x18000edf4`
- `0x180017350`
- `0x180017418`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PCLmWriter::PCLmPageImageCalculator::ReInitialize(
        PCLmWriter::PCLmPageImageCalculator *this,
        int a2,
        struct IPageBitmapProvider *a3)
{
  __int64 v6; // rdx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  if ( *((struct IPageBitmapProvider **)this + 3) != a3 )
  {
    if ( a3 )
      (*(void (__fastcall **)(struct IPageBitmapProvider *))(*(_QWORD *)a3 + 8LL))(a3);
    v7 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = a3;
    Microsoft::WRL::ComPtr<IPCLmWriter>::InternalRelease(&v7);
  }
  *((_DWORD *)this + 14) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 48LL))(*((_QWORD *)this + 3));
  *((_DWORD *)this + 15) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 48LL))(*((_QWORD *)this + 3));
  *((_DWORD *)this + 20) = a2;
  *((_DWORD *)this + 22) = ((*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 64LL))(*((_QWORD *)this + 3))
                          + 7) >> 3;
  *((_DWORD *)this + 21) = 0;
  v6 = *((_QWORD *)this + 1);
  if ( *(_QWORD *)this != v6 )
  {
    std::_Destroy_range<std::allocator<PCLmWriter::PDFImageData>>(*(_QWORD *)this, v6);
    *((_QWORD *)this + 1) = *(_QWORD *)this;
  }
  PCLmWriter::PCLmPageImageCalculator::_CalculatePageData(this);
}

```

## disassembly

```asm
0x180017350  mov     [rsp+arg_8], rbx
0x180017355  mov     [rsp+arg_10], rsi
0x18001735a  push    rdi
0x18001735b  sub     rsp, 20h
0x18001735f  mov     rdi, r8
0x180017362  mov     esi, edx
0x180017364  mov     rbx, rcx
0x180017367  cmp     [rcx+18h], r8
0x18001736b  jz      short loc_180017399
0x18001736d  test    r8, r8
0x180017370  jz      short loc_180017382
0x180017372  mov     rax, [r8]
0x180017375  mov     rcx, r8
0x180017378  mov     rax, [rax+8]
0x18001737c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017381  nop
0x180017382  mov     rax, [rbx+18h]
0x180017386  mov     [rsp+28h+arg_0], rax
0x18001738b  mov     [rbx+18h], rdi
0x18001738f  lea     rcx, [rsp+28h+arg_0]
0x180017394  call    ?InternalRelease@?$ComPtr@UIPCLmWriter@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPCLmWriter>::InternalRelease(void)
0x180017399  mov     rcx, [rbx+18h]
0x18001739d  mov     rax, [rcx]
0x1800173a0  mov     rax, [rax+30h]
0x1800173a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173a9  mov     [rbx+38h], eax
0x1800173ac  mov     rcx, [rbx+18h]
0x1800173b0  mov     rax, [rcx]
0x1800173b3  mov     rax, [rax+30h]
0x1800173b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173bc  mov     [rbx+3Ch], eax
0x1800173bf  mov     [rbx+50h], esi
0x1800173c2  mov     rcx, [rbx+18h]
0x1800173c6  mov     rax, [rcx]
0x1800173c9  mov     rax, [rax+40h]
0x1800173cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173d2  add     eax, 7
0x1800173d5  shr     eax, 3
0x1800173d8  mov     [rbx+58h], eax
0x1800173db  mov     dword ptr [rbx+54h], 0
0x1800173e2  mov     rdx, [rbx+8]
0x1800173e6  cmp     [rbx], rdx
0x1800173e9  jz      short loc_1800173FA
0x1800173eb  mov     rcx, [rbx]
0x1800173ee  call    ??$_Destroy_range@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@YAXPEAUPDFImageData@PCLmWriter@@QEAU12@AEAV?$allocator@UPDFImageData@PCLmWriter@@@0@@Z; std::_Destroy_range<std::allocator<PCLmWriter::PDFImageData>>(PCLmWriter::PDFImageData *,PCLmWriter::PDFImageData * const,std::allocator<PCLmWriter::PDFImageData> &)
0x1800173f3  mov     rax, [rbx]
0x1800173f6  mov     [rbx+8], rax
0x1800173fa  mov     rcx, rbx; this
0x1800173fd  mov     rbx, [rsp+28h+arg_8]
0x180017402  mov     rsi, [rsp+28h+arg_10]
0x180017407  add     rsp, 20h
0x18001740b  pop     rdi
0x18001740c  jmp     ?_CalculatePageData@PCLmPageImageCalculator@PCLmWriter@@AEAAXXZ; PCLmWriter::PCLmPageImageCalculator::_CalculatePageData(void)
```
