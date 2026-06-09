# Microsoft::WRL::Details::MakeAndInitialize<CCredUIBrokerForAppContainers,IUnknown,>(IUnknown * *)

- ea: `0x1400058e8`
- end: `0x1400059c0`
- name: `??$MakeAndInitialize@VCCredUIBrokerForAppContainers@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000b200`

## callees

- `0x140003644`
- `0x1400058e8`
- `0x140007e7c`
- `0x140008920`
- `0x14001f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CCredUIBrokerForAppContainers,IUnknown,>(_QWORD *a1)
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
    *v3 = &CCredUIBrokerForAppContainers::`vftable';
    v6 = 0;
    v4 = ((__int64 (__fastcall *)(_QWORD *, GUID *, _QWORD *))CCredUIBrokerForAppContainers::`vftable')(
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
0x1400058e8  mov     [rsp+arg_8], rbx
0x1400058ed  push    rdi
0x1400058ee  sub     rsp, 20h
0x1400058f2  mov     rdi, rcx
0x1400058f5  mov     qword ptr [rcx], 0
0x1400058fc  mov     ecx, 50h ; 'P'; unsigned __int64
0x140005901  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140005908  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000590d  mov     [rsp+28h+arg_0], rax
0x140005912  mov     rbx, rax
0x140005915  test    rax, rax
0x140005918  jnz     short loc_140005924
0x14000591a  mov     edi, 8007000Eh
0x14000591f  jmp     loc_1400059A9
0x140005924  mov     rcx, rbx
0x140005927  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICredUIBroker@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICredUIBroker>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICredUIBroker>(void)
0x14000592c  mov     qword ptr [rbx+10h], 0
0x140005934  lea     rax, ??_7CCredUIBrokerForAppContainers@@6B@; const CCredUIBrokerForAppContainers::`vftable'
0x14000593b  mov     qword ptr [rbx+18h], 0
0x140005943  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14000594a  mov     qword ptr [rbx+20h], 0
0x140005952  mov     r8, rdi
0x140005955  mov     qword ptr [rbx+28h], 0
0x14000595d  mov     rcx, rbx
0x140005960  mov     qword ptr [rbx+30h], 0
0x140005968  mov     qword ptr [rbx+38h], 0
0x140005970  mov     qword ptr [rbx+40h], 0
0x140005978  mov     qword ptr [rbx+48h], 0
0x140005980  mov     [rbx], rax
0x140005983  mov     rax, cs:??_7CCredUIBrokerForAppContainers@@6B@; const CCredUIBrokerForAppContainers::`vftable'
0x14000598a  mov     [rsp+28h+arg_0], 0
0x140005993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005998  mov     rcx, [rbx]
0x14000599b  mov     edi, eax
0x14000599d  mov     rax, [rcx+10h]
0x1400059a1  mov     rcx, rbx
0x1400059a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059a9  lea     rcx, [rsp+28h+arg_0]
0x1400059ae  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(void)
0x1400059b3  mov     rbx, [rsp+28h+arg_8]
0x1400059b8  mov     eax, edi
0x1400059ba  add     rsp, 20h
0x1400059be  pop     rdi
0x1400059bf  retn
```
