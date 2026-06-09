# Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainers,0>,Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainers,0>,>(Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainers,0> * *)

- ea: `0x140005728`
- end: `0x1400057b6`
- name: `??$MakeAndInitialize@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainers@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VCCredUIBrokerForNonAppContainers@@$0A@@12@@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140004fb0`

## callees

- `0x140003644`
- `0x140005728`
- `0x140007ef4`
- `0x140008920`
- `0x14001f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainers,0>,Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainers,0>,>(
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
    v4 = Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainers,0>::SimpleClassFactory<CCredUIBrokerForNonAppContainers,0>(v2);
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
0x140005728  mov     [rsp+arg_8], rbx
0x14000572d  push    rdi
0x14000572e  sub     rsp, 20h
0x140005732  mov     rdi, rcx
0x140005735  mov     qword ptr [rcx], 0
0x14000573c  mov     ecx, 18h; unsigned __int64
0x140005741  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140005748  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000574d  mov     [rsp+28h+arg_0], rax
0x140005752  test    rax, rax
0x140005755  jnz     short loc_14000575E
0x140005757  mov     ebx, 8007000Eh
0x14000575c  jmp     short loc_14000579F
0x14000575e  mov     rcx, rax
0x140005761  call    ??0?$SimpleClassFactory@VCCredUIBrokerForNonAppContainers@@$0A@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainers,0>::SimpleClassFactory<CCredUIBrokerForNonAppContainers,0>(void)
0x140005766  mov     [rsp+28h+arg_0], 0
0x14000576f  mov     rbx, rax
0x140005772  test    rax, rax
0x140005775  jz      short loc_14000579A
0x140005777  mov     rcx, [rax]
0x14000577a  mov     rax, [rcx+8]
0x14000577e  mov     rcx, rbx
0x140005781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005786  mov     [rdi], rbx
0x140005789  mov     rcx, [rbx]
0x14000578c  mov     rax, [rcx+10h]
0x140005790  mov     rcx, rbx
0x140005793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005798  jmp     short loc_14000579D
0x14000579a  mov     [rdi], rbx
0x14000579d  xor     ebx, ebx
0x14000579f  lea     rcx, [rsp+28h+arg_0]
0x1400057a4  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(void)
0x1400057a9  mov     eax, ebx
0x1400057ab  mov     rbx, [rsp+28h+arg_8]
0x1400057b0  add     rsp, 20h
0x1400057b4  pop     rdi
0x1400057b5  retn
```
