# std::make_shared<CBroker::SebBroker,>(void)

- ea: `0x18001c824`
- end: `0x18001c8dd`
- name: `??$make_shared@VSebBroker@CBroker@@$$V@std@@YA?AV?$shared_ptr@VSebBroker@CBroker@@@0@XZ`
- size: `185`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c4d8`

## callees

- `0x18000b168`
- `0x18001cf74`
- `0x1800208bc`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x18001c8bc`
- `ntdll!RtlInitializeSRWLock` at `0x18001c8bc`

## pseudocode

```c
_QWORD *__fastcall std::make_shared<CBroker::SebBroker,>(_QWORD *a1)
{
  _DWORD *v3; // [rsp+40h] [rbp+8h]

  v3 = operator new(0x178u);
  *(_OWORD *)v3 = 0;
  v3[2] = 1;
  v3[3] = 1;
  *(_QWORD *)v3 = &std::_Ref_count_obj2<CBroker::SebBroker>::`vftable';
  *((_BYTE *)v3 + 16) = 0;
  *((_QWORD *)v3 + 4) = 0;
  *((_QWORD *)v3 + 5) = 0;
  std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<CBroker::SebEvent>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>,0>>::_Alloc_sentinel_and_proxy();
  *((_QWORD *)v3 + 6) = 0;
  *((_QWORD *)v3 + 7) = 0;
  std::vector<_GUID>::vector<_GUID>(v3 + 84);
  v3[90] = 0;
  *((_QWORD *)v3 + 46) = 0;
  RtlInitializeSRWLock(v3 + 6);
  *a1 = v3 + 4;
  a1[1] = v3;
  return a1;
}

```

## disassembly

```asm
0x18001c824  mov     [rsp+arg_10], rbx
0x18001c829  mov     [rsp+arg_18], rsi
0x18001c82e  mov     [rsp+arg_0], rcx
0x18001c833  push    rdi
0x18001c834  sub     rsp, 30h
0x18001c838  mov     rsi, rcx
0x18001c83b  mov     ecx, 178h; Size
0x18001c840  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c845  mov     rdi, rax
0x18001c848  mov     [rsp+38h+arg_0], rax
0x18001c84d  xorps   xmm0, xmm0
0x18001c850  movups  xmmword ptr [rax], xmm0
0x18001c853  mov     eax, 1
0x18001c858  mov     [rdi+8], eax
0x18001c85b  mov     [rdi+0Ch], eax
0x18001c85e  lea     rax, ??_7?$_Ref_count_obj2@VSebBroker@CBroker@@@std@@6B@; const std::_Ref_count_obj2<CBroker::SebBroker>::`vftable'
0x18001c865  mov     [rdi], rax
0x18001c868  lea     rbx, [rdi+10h]
0x18001c86c  mov     byte ptr [rbx], 0
0x18001c86f  lea     rcx, [rbx+10h]
0x18001c873  mov     qword ptr [rcx], 0
0x18001c87a  mov     qword ptr [rcx+8], 0
0x18001c882  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<CBroker::SebEvent>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18001c887  mov     qword ptr [rbx+20h], 0
0x18001c88f  mov     qword ptr [rbx+28h], 0
0x18001c897  lea     rcx, [rbx+140h]
0x18001c89e  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18001c8a3  mov     dword ptr [rbx+158h], 0
0x18001c8ad  mov     qword ptr [rbx+160h], 0
0x18001c8b8  lea     rcx, [rbx+8]
0x18001c8bc  call    cs:__imp_RtlInitializeSRWLock
0x18001c8c2  nop
0x18001c8c3  mov     [rsi], rbx
0x18001c8c6  mov     [rsi+8], rdi
0x18001c8ca  mov     rax, rsi
0x18001c8cd  mov     rbx, [rsp+38h+arg_10]
0x18001c8d2  mov     rsi, [rsp+38h+arg_18]
0x18001c8d7  add     rsp, 30h
0x18001c8db  pop     rdi
0x18001c8dc  retn
```
