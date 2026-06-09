# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(uint)

- ea: `0x18000ef80`
- end: `0x18000efd4`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `84`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001e90`
- `0x18000ef80`
- `0x180023010`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(
        _DWORD *a1,
        char a2)
{
  __int64 v3; // rcx

  a1[11] = -1073741823;
  v3 = *((_QWORD *)a1 + 4);
  if ( v3 )
  {
    *((_QWORD *)a1 + 4) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000ef80  mov     [rsp+arg_0], rbx
0x18000ef85  push    rdi
0x18000ef86  sub     rsp, 20h
0x18000ef8a  mov     rbx, rcx
0x18000ef8d  mov     dword ptr [rcx+2Ch], 0C0000001h
0x18000ef94  mov     rcx, [rcx+20h]
0x18000ef98  mov     edi, edx
0x18000ef9a  test    rcx, rcx
0x18000ef9d  jz      short loc_18000EFB3
0x18000ef9f  mov     qword ptr [rbx+20h], 0
0x18000efa7  mov     rax, [rcx]
0x18000efaa  mov     rax, [rax+10h]
0x18000efae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efb3  test    dil, 1
0x18000efb7  jz      short loc_18000EFC6
0x18000efb9  mov     edx, 30h ; '0'; unsigned __int64
0x18000efbe  mov     rcx, rbx; void *
0x18000efc1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000efc6  mov     rax, rbx
0x18000efc9  mov     rbx, [rsp+28h+arg_0]
0x18000efce  add     rsp, 20h
0x18000efd2  pop     rdi
0x18000efd3  retn
```
