# std::_Temporary_owner<PluginPendingMessage>::~_Temporary_owner<PluginPendingMessage>(void)

- ea: `0x18001fb24`
- end: `0x18001fb90`
- name: `??1?$_Temporary_owner@UPluginPendingMessage@@@std@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800269a4`
- `0x18002a530`
- `0x180033d6c`
- `0x180033ed4`

## callees

- `0x180001900`
- `0x1800031a4`
- `0x18001fb24`
- `0x180035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall std::_Temporary_owner<PluginPendingMessage>::~_Temporary_owner<PluginPendingMessage>(_QWORD **a1)
{
  _QWORD *v1; // rbx
  void *v2; // rdi
  volatile signed __int32 *v3; // rdx

  v1 = *a1;
  if ( *a1 )
  {
    v2 = (void *)v1[2];
    if ( v2 )
    {
      std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(v1[2]);
      operator delete(v2);
    }
    v3 = (volatile signed __int32 *)(v1[1] - 24LL);
    if ( _InterlockedExchangeAdd(v3 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 8LL))(*(_QWORD *)v3);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18001fb24  mov     [rsp+arg_0], rbx
0x18001fb29  push    rdi
0x18001fb2a  sub     rsp, 20h
0x18001fb2e  mov     rbx, [rcx]
0x18001fb31  test    rbx, rbx
0x18001fb34  jz      short loc_18001FB85
0x18001fb36  mov     rdi, [rbx+10h]
0x18001fb3a  test    rdi, rdi
0x18001fb3d  jz      short loc_18001FB54
0x18001fb3f  mov     rcx, rdi
0x18001fb42  call    ??1?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(void)
0x18001fb47  mov     edx, 18h
0x18001fb4c  mov     rcx, rdi; Block
0x18001fb4f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fb54  mov     rdx, [rbx+8]
0x18001fb58  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001fb5c  or      eax, 0FFFFFFFFh
0x18001fb5f  lock xadd [rdx+10h], eax
0x18001fb64  sub     eax, 1
0x18001fb67  jg      short loc_18001FB78
0x18001fb69  mov     rcx, [rdx]
0x18001fb6c  mov     rax, [rcx]
0x18001fb6f  mov     rax, [rax+8]
0x18001fb73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb78  mov     edx, 18h
0x18001fb7d  mov     rcx, rbx; Block
0x18001fb80  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fb85  mov     rbx, [rsp+28h+arg_0]
0x18001fb8a  add     rsp, 20h
0x18001fb8e  pop     rdi
0x18001fb8f  retn
```
