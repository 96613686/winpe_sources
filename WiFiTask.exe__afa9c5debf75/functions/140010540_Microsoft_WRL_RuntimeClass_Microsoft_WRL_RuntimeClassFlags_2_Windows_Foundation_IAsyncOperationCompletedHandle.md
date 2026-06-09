# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vector deleting destructor'(uint)

- ea: `0x140010540`
- end: `0x140010595`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `85`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1400016c4`
- `0x140010540`
- `0x140012010`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vector deleting destructor'(
        _DWORD *Block,
        char a2)
{
  __int64 v4; // rcx

  Block[11] = -1073741823;
  v4 = *((_QWORD *)Block + 4);
  if ( v4 )
  {
    *((_QWORD *)Block + 4) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x140010540  mov     [rsp+arg_0], rbx
0x140010545  push    rdi
0x140010546  sub     rsp, 20h
0x14001054a  mov     edi, edx
0x14001054c  mov     rbx, rcx
0x14001054f  mov     dword ptr [rcx+2Ch], 0C0000001h
0x140010556  mov     rcx, [rcx+20h]
0x14001055a  test    rcx, rcx
0x14001055d  jz      short loc_140010574
0x14001055f  mov     qword ptr [rbx+20h], 0
0x140010567  mov     rax, [rcx]
0x14001056a  mov     rax, [rax+10h]
0x14001056e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010573  nop
0x140010574  test    dil, 1
0x140010578  jz      short loc_140010587
0x14001057a  mov     edx, 30h ; '0'
0x14001057f  mov     rcx, rbx; Block
0x140010582  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140010587  mov     rax, rbx
0x14001058a  mov     rbx, [rsp+28h+arg_0]
0x14001058f  add     rsp, 20h
0x140010593  pop     rdi
0x140010594  retn
```
