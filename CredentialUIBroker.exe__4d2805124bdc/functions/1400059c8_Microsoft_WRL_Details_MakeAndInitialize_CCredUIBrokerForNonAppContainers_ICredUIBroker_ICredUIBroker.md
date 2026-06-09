# Microsoft::WRL::Details::MakeAndInitialize<CCredUIBrokerForNonAppContainers,ICredUIBroker,>(ICredUIBroker * *)

- ea: `0x1400059c8`
- end: `0x140005a6f`
- name: `??$MakeAndInitialize@VCCredUIBrokerForNonAppContainers@@UICredUIBroker@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUICredUIBroker@@@Z`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140011100`

## callees

- `0x140003644`
- `0x1400059c8`
- `0x1400080b8`
- `0x140008920`
- `0x14000ab00`
- `0x14001f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CCredUIBrokerForNonAppContainers,ICredUIBroker,>(
        _QWORD *a1)
{
  CCredUIBrokerForNonAppContainers *v2; // rax
  unsigned int v3; // edi
  CCredUIBrokerForNonAppContainers *v4; // rax
  __int64 (__fastcall ***v5)(_QWORD, GUID *, _QWORD *); // rbx
  __int64 (__fastcall ***v7)(_QWORD, GUID *, _QWORD *); // [rsp+30h] [rbp+8h] BYREF
  CCredUIBrokerForNonAppContainers *v8; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = (CCredUIBrokerForNonAppContainers *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v2;
  if ( v2 )
  {
    v4 = CCredUIBrokerForNonAppContainers::CCredUIBrokerForNonAppContainers(v2);
    v7 = 0;
    Microsoft::WRL::ComPtr<CCredUIBrokerForNonAppContainers>::Attach(&v7, v4);
    v5 = v7;
    v8 = 0;
    v3 = (**v7)(v7, &GUID_0129ca94_3d53_4386_bcef_f773d0e46cc1, a1);
    if ( v5 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v5)[2])(v5);
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(&v8);
  return v3;
}

```

## disassembly

```asm
0x1400059c8  mov     [rsp+arg_10], rbx
0x1400059cd  push    rdi
0x1400059ce  sub     rsp, 20h
0x1400059d2  mov     rdi, rcx
0x1400059d5  mov     qword ptr [rcx], 0
0x1400059dc  mov     ecx, 50h ; 'P'; unsigned __int64
0x1400059e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400059e8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400059ed  mov     [rsp+28h+arg_8], rax
0x1400059f2  test    rax, rax
0x1400059f5  jnz     short loc_1400059FE
0x1400059f7  mov     edi, 8007000Eh
0x1400059fc  jmp     short loc_140005A58
0x1400059fe  mov     rcx, rax; this
0x140005a01  call    ??0CCredUIBrokerForNonAppContainers@@QEAA@XZ; CCredUIBrokerForNonAppContainers::CCredUIBrokerForNonAppContainers(void)
0x140005a06  mov     rdx, rax
0x140005a09  mov     [rsp+28h+arg_0], 0
0x140005a12  lea     rcx, [rsp+28h+arg_0]
0x140005a17  call    ?Attach@?$ComPtr@VCCredUIBrokerForNonAppContainers@@@WRL@Microsoft@@QEAAXPEAVCCredUIBrokerForNonAppContainers@@@Z; Microsoft::WRL::ComPtr<CCredUIBrokerForNonAppContainers>::Attach(CCredUIBrokerForNonAppContainers *)
0x140005a1c  mov     rbx, [rsp+28h+arg_0]
0x140005a21  lea     rdx, _GUID_0129ca94_3d53_4386_bcef_f773d0e46cc1
0x140005a28  mov     r8, rdi
0x140005a2b  mov     [rsp+28h+arg_8], 0
0x140005a34  mov     rcx, rbx
0x140005a37  mov     rax, [rbx]
0x140005a3a  mov     rax, [rax]
0x140005a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a42  mov     edi, eax
0x140005a44  test    rbx, rbx
0x140005a47  jz      short loc_140005A58
0x140005a49  mov     rdx, [rbx]
0x140005a4c  mov     rcx, rbx
0x140005a4f  mov     rax, [rdx+10h]
0x140005a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a58  lea     rcx, [rsp+28h+arg_8]
0x140005a5d  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(void)
0x140005a62  mov     rbx, [rsp+28h+arg_10]
0x140005a67  mov     eax, edi
0x140005a69  add     rsp, 20h
0x140005a6d  pop     rdi
0x140005a6e  retn
```
