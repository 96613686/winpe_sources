# Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>,Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>,>(Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0> * *)

- ea: `0x1400057bc`
- end: `0x14000584a`
- name: `??$MakeAndInitialize@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@12@@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140005070`

## callees

- `0x140003644`
- `0x1400057bc`
- `0x140007f18`
- `0x140008920`
- `0x14001f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>,Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>,>(
        __int64 *a1)
{
  void *v2; // rax
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rbx
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v2;
  if ( v2 )
  {
    v4 = Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>(v2);
    v7 = 0;
    v5 = v4;
    if ( v4 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
      *a1 = v5;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    else
    {
      *a1 = 0;
    }
    v3 = 0;
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(&v7);
  return v3;
}

```

## disassembly

```asm
0x1400057bc  mov     [rsp+arg_8], rbx
0x1400057c1  push    rdi
0x1400057c2  sub     rsp, 20h
0x1400057c6  mov     rdi, rcx
0x1400057c9  mov     qword ptr [rcx], 0
0x1400057d0  mov     ecx, 18h; unsigned __int64
0x1400057d5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400057dc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400057e1  mov     [rsp+28h+arg_0], rax
0x1400057e6  test    rax, rax
0x1400057e9  jnz     short loc_1400057F2
0x1400057eb  mov     ebx, 8007000Eh
0x1400057f0  jmp     short loc_140005833
0x1400057f2  mov     rcx, rax
0x1400057f5  call    ??0?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>(void)
0x1400057fa  mov     [rsp+28h+arg_0], 0
0x140005803  mov     rbx, rax
0x140005806  test    rax, rax
0x140005809  jz      short loc_14000582E
0x14000580b  mov     rcx, [rax]
0x14000580e  mov     rax, [rcx+8]
0x140005812  mov     rcx, rbx
0x140005815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000581a  mov     [rdi], rbx
0x14000581d  mov     rcx, [rbx]
0x140005820  mov     rax, [rcx+10h]
0x140005824  mov     rcx, rbx
0x140005827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000582c  jmp     short loc_140005831
0x14000582e  mov     [rdi], rbx
0x140005831  xor     ebx, ebx
0x140005833  lea     rcx, [rsp+28h+arg_0]
0x140005838  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(void)
0x14000583d  mov     eax, ebx
0x14000583f  mov     rbx, [rsp+28h+arg_8]
0x140005844  add     rsp, 20h
0x140005848  pop     rdi
0x140005849  retn
```
