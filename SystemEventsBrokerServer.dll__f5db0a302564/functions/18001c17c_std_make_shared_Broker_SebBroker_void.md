# std::make_shared<Broker::SebBroker,>(void)

- ea: `0x18001c17c`
- end: `0x18001c220`
- name: `??$make_shared@VSebBroker@Broker@@$$V@std@@YA?AV?$shared_ptr@VSebBroker@Broker@@@0@XZ`
- size: `164`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c100`

## callees

- `0x180016318`
- `0x18001a198`
- `0x18001cf74`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x18001c1ff`
- `ntdll!RtlInitializeSRWLock` at `0x18001c1ff`

## pseudocode

```c
_QWORD *__fastcall std::make_shared<Broker::SebBroker,>(_QWORD *a1)
{
  _DWORD *v3; // [rsp+40h] [rbp+8h]

  v3 = operator new(0xA0u);
  *(_OWORD *)v3 = 0;
  v3[2] = 1;
  v3[3] = 1;
  *(_QWORD *)v3 = &std::_Ref_count_obj2<Broker::SebBroker>::`vftable';
  *((_BYTE *)v3 + 16) = 0;
  *((_QWORD *)v3 + 4) = 0;
  *((_QWORD *)v3 + 5) = 0;
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::_Alloc_sentinel_and_proxy(v3 + 8);
  Broker::ApplicationIdentity::ApplicationIdentity((Broker::ApplicationIdentity *)(v3 + 12));
  *((_QWORD *)v3 + 17) = 0;
  *((_QWORD *)v3 + 19) = 0;
  RtlInitializeSRWLock(v3 + 6);
  *a1 = v3 + 4;
  a1[1] = v3;
  return a1;
}

```

## disassembly

```asm
0x18001c17c  mov     [rsp+arg_10], rbx
0x18001c181  mov     [rsp+arg_18], rsi
0x18001c186  mov     [rsp+arg_0], rcx
0x18001c18b  push    rdi
0x18001c18c  sub     rsp, 30h
0x18001c190  mov     rsi, rcx
0x18001c193  mov     ecx, 0A0h; Size
0x18001c198  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c19d  mov     rdi, rax
0x18001c1a0  mov     [rsp+38h+arg_0], rax
0x18001c1a5  xorps   xmm0, xmm0
0x18001c1a8  movups  xmmword ptr [rax], xmm0
0x18001c1ab  mov     eax, 1
0x18001c1b0  mov     [rdi+8], eax
0x18001c1b3  mov     [rdi+0Ch], eax
0x18001c1b6  lea     rax, ??_7?$_Ref_count_obj2@VSebBroker@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::SebBroker>::`vftable'
0x18001c1bd  mov     [rdi], rax
0x18001c1c0  lea     rbx, [rdi+10h]
0x18001c1c4  mov     byte ptr [rbx], 0
0x18001c1c7  lea     rcx, [rbx+10h]
0x18001c1cb  mov     qword ptr [rcx], 0
0x18001c1d2  mov     qword ptr [rcx+8], 0
0x18001c1da  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18001c1df  lea     rcx, [rbx+20h]; this
0x18001c1e3  call    ??0ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::ApplicationIdentity(void)
0x18001c1e8  mov     qword ptr [rbx+78h], 0
0x18001c1f0  mov     qword ptr [rbx+88h], 0
0x18001c1fb  lea     rcx, [rbx+8]
0x18001c1ff  call    cs:__imp_RtlInitializeSRWLock
0x18001c205  nop
0x18001c206  mov     [rsi], rbx
0x18001c209  mov     [rsi+8], rdi
0x18001c20d  mov     rax, rsi
0x18001c210  mov     rbx, [rsp+38h+arg_10]
0x18001c215  mov     rsi, [rsp+38h+arg_18]
0x18001c21a  add     rsp, 30h
0x18001c21e  pop     rdi
0x18001c21f  retn
```
