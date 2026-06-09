# Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForAppContainers,0>,Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForAppContainers,0>,>(Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForAppContainers,0> * *)

- ea: `0x140005694`
- end: `0x140005722`
- name: `??$MakeAndInitialize@V?$SimpleClassFactory@VCCredUIBrokerForAppContainers@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VCCredUIBrokerForAppContainers@@$0A@@12@@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140004ef0`

## callees

- `0x140003644`
- `0x140005694`
- `0x140007ed0`
- `0x140008920`
- `0x14001f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForAppContainers,0>,Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForAppContainers,0>,>(
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
    v4 = Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForAppContainers,0>::SimpleClassFactory<CCredUIBrokerForAppContainers,0>(v2);
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
0x140005694  mov     [rsp+arg_8], rbx
0x140005699  push    rdi
0x14000569a  sub     rsp, 20h
0x14000569e  mov     rdi, rcx
0x1400056a1  mov     qword ptr [rcx], 0
0x1400056a8  mov     ecx, 18h; unsigned __int64
0x1400056ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400056b4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400056b9  mov     [rsp+28h+arg_0], rax
0x1400056be  test    rax, rax
0x1400056c1  jnz     short loc_1400056CA
0x1400056c3  mov     ebx, 8007000Eh
0x1400056c8  jmp     short loc_14000570B
0x1400056ca  mov     rcx, rax
0x1400056cd  call    ??0?$SimpleClassFactory@VCCredUIBrokerForAppContainers@@$0A@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForAppContainers,0>::SimpleClassFactory<CCredUIBrokerForAppContainers,0>(void)
0x1400056d2  mov     [rsp+28h+arg_0], 0
0x1400056db  mov     rbx, rax
0x1400056de  test    rax, rax
0x1400056e1  jz      short loc_140005706
0x1400056e3  mov     rcx, [rax]
0x1400056e6  mov     rax, [rcx+8]
0x1400056ea  mov     rcx, rbx
0x1400056ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400056f2  mov     [rdi], rbx
0x1400056f5  mov     rcx, [rbx]
0x1400056f8  mov     rax, [rcx+10h]
0x1400056fc  mov     rcx, rbx
0x1400056ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005704  jmp     short loc_140005709
0x140005706  mov     [rdi], rbx
0x140005709  xor     ebx, ebx
0x14000570b  lea     rcx, [rsp+28h+arg_0]
0x140005710  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(void)
0x140005715  mov     eax, ebx
0x140005717  mov     rbx, [rsp+28h+arg_8]
0x14000571c  add     rsp, 20h
0x140005720  pop     rdi
0x140005721  retn
```
