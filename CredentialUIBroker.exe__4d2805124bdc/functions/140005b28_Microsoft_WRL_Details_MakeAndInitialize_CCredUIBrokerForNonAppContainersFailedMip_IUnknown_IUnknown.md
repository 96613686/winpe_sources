# Microsoft::WRL::Details::MakeAndInitialize<CCredUIBrokerForNonAppContainersFailedMip,IUnknown,>(IUnknown * *)

- ea: `0x140005b28`
- end: `0x140005c00`
- name: `??$MakeAndInitialize@VCCredUIBrokerForNonAppContainersFailedMip@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000b320`

## callees

- `0x140003644`
- `0x140005b28`
- `0x140007e7c`
- `0x140008920`
- `0x14001f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CCredUIBrokerForNonAppContainersFailedMip,IUnknown,>(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  unsigned int v4; // edi
  _QWORD *v6; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v2;
  v3 = v2;
  if ( v2 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICredUIBroker>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICredUIBroker>(v2);
    v3[2] = 0;
    v3[3] = 0;
    v3[4] = 0;
    v3[5] = 0;
    v3[6] = 0;
    v3[7] = 0;
    v3[8] = 0;
    v3[9] = 0;
    *v3 = &CCredUIBrokerForNonAppContainersFailedMip::`vftable';
    v6 = 0;
    v4 = ((__int64 (__fastcall *)(_QWORD *, GUID *, _QWORD *))CCredUIBrokerForNonAppContainersFailedMip::`vftable')(
           v3,
           &GUID_00000000_0000_0000_c000_000000000046,
           a1);
    (*(void (__fastcall **)(_QWORD *))(*v3 + 16LL))(v3);
  }
  else
  {
    v4 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(&v6);
  return v4;
}

```

## disassembly

```asm
0x140005b28  mov     [rsp+arg_8], rbx
0x140005b2d  push    rdi
0x140005b2e  sub     rsp, 20h
0x140005b32  mov     rdi, rcx
0x140005b35  mov     qword ptr [rcx], 0
0x140005b3c  mov     ecx, 50h ; 'P'; unsigned __int64
0x140005b41  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140005b48  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140005b4d  mov     [rsp+28h+arg_0], rax
0x140005b52  mov     rbx, rax
0x140005b55  test    rax, rax
0x140005b58  jnz     short loc_140005B64
0x140005b5a  mov     edi, 8007000Eh
0x140005b5f  jmp     loc_140005BE9
0x140005b64  mov     rcx, rbx
0x140005b67  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICredUIBroker@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICredUIBroker>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICredUIBroker>(void)
0x140005b6c  mov     qword ptr [rbx+10h], 0
0x140005b74  lea     rax, ??_7CCredUIBrokerForNonAppContainersFailedMip@@6B@; const CCredUIBrokerForNonAppContainersFailedMip::`vftable'
0x140005b7b  mov     qword ptr [rbx+18h], 0
0x140005b83  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140005b8a  mov     qword ptr [rbx+20h], 0
0x140005b92  mov     r8, rdi
0x140005b95  mov     qword ptr [rbx+28h], 0
0x140005b9d  mov     rcx, rbx
0x140005ba0  mov     qword ptr [rbx+30h], 0
0x140005ba8  mov     qword ptr [rbx+38h], 0
0x140005bb0  mov     qword ptr [rbx+40h], 0
0x140005bb8  mov     qword ptr [rbx+48h], 0
0x140005bc0  mov     [rbx], rax
0x140005bc3  mov     rax, cs:??_7CCredUIBrokerForNonAppContainersFailedMip@@6B@; const CCredUIBrokerForNonAppContainersFailedMip::`vftable'
0x140005bca  mov     [rsp+28h+arg_0], 0
0x140005bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bd8  mov     rcx, [rbx]
0x140005bdb  mov     edi, eax
0x140005bdd  mov     rax, [rcx+10h]
0x140005be1  mov     rcx, rbx
0x140005be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005be9  lea     rcx, [rsp+28h+arg_0]
0x140005bee  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(void)
0x140005bf3  mov     rbx, [rsp+28h+arg_8]
0x140005bf8  mov     eax, edi
0x140005bfa  add     rsp, 20h
0x140005bfe  pop     rdi
0x140005bff  retn
```
