# Microsoft::WRL::Details::MakeAndInitialize<CCredUIBrokerForNonAppContainers,IUnknown,>(IUnknown * *)

- ea: `0x140005a78`
- end: `0x140005b1f`
- name: `??$MakeAndInitialize@VCCredUIBrokerForNonAppContainers@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000b290`

## callees

- `0x140003644`
- `0x140005a78`
- `0x1400080b8`
- `0x140008920`
- `0x14000ab00`
- `0x14001f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CCredUIBrokerForNonAppContainers,IUnknown,>(_QWORD *a1)
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
    v3 = (**v7)(v7, &GUID_00000000_0000_0000_c000_000000000046, a1);
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
0x140005a78  mov     [rsp+arg_10], rbx
0x140005a7d  push    rdi
0x140005a7e  sub     rsp, 20h
0x140005a82  mov     rdi, rcx
0x140005a85  mov     qword ptr [rcx], 0
0x140005a8c  mov     ecx, 50h ; 'P'; unsigned __int64
0x140005a91  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140005a98  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140005a9d  mov     [rsp+28h+arg_8], rax
0x140005aa2  test    rax, rax
0x140005aa5  jnz     short loc_140005AAE
0x140005aa7  mov     edi, 8007000Eh
0x140005aac  jmp     short loc_140005B08
0x140005aae  mov     rcx, rax; this
0x140005ab1  call    ??0CCredUIBrokerForNonAppContainers@@QEAA@XZ; CCredUIBrokerForNonAppContainers::CCredUIBrokerForNonAppContainers(void)
0x140005ab6  mov     rdx, rax
0x140005ab9  mov     [rsp+28h+arg_0], 0
0x140005ac2  lea     rcx, [rsp+28h+arg_0]
0x140005ac7  call    ?Attach@?$ComPtr@VCCredUIBrokerForNonAppContainers@@@WRL@Microsoft@@QEAAXPEAVCCredUIBrokerForNonAppContainers@@@Z; Microsoft::WRL::ComPtr<CCredUIBrokerForNonAppContainers>::Attach(CCredUIBrokerForNonAppContainers *)
0x140005acc  mov     rbx, [rsp+28h+arg_0]
0x140005ad1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140005ad8  mov     r8, rdi
0x140005adb  mov     [rsp+28h+arg_8], 0
0x140005ae4  mov     rcx, rbx
0x140005ae7  mov     rax, [rbx]
0x140005aea  mov     rax, [rax]
0x140005aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005af2  mov     edi, eax
0x140005af4  test    rbx, rbx
0x140005af7  jz      short loc_140005B08
0x140005af9  mov     rdx, [rbx]
0x140005afc  mov     rcx, rbx
0x140005aff  mov     rax, [rdx+10h]
0x140005b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b08  lea     rcx, [rsp+28h+arg_8]
0x140005b0d  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(void)
0x140005b12  mov     rbx, [rsp+28h+arg_10]
0x140005b17  mov     eax, edi
0x140005b19  add     rsp, 20h
0x140005b1d  pop     rdi
0x140005b1e  retn
```
