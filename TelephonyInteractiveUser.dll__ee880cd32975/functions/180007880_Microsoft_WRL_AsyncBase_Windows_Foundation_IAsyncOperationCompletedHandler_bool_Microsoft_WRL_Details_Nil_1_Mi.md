# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`scalar deleting destructor'(uint)

- ea: `0x180007880`
- end: `0x1800078fa`
- name: `??_G?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `122`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001984`
- `0x180007880`
- `0x18000f610`
- `0x180019010`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`scalar deleting destructor'(
        _DWORD *Block,
        char a2)
{
  bool v2; // zf
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = Block[4] == 0;
  *(_QWORD *)Block = &Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable';
  if ( v2 )
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete((__int64)Block);
  v5 = *((_QWORD *)Block + 6);
  if ( v5 )
  {
    *((_QWORD *)Block + 6) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *((_QWORD *)Block + 3);
  if ( v6 )
  {
    *((_QWORD *)Block + 3) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180007880  mov     [rsp+arg_0], rbx
0x180007885  push    rdi
0x180007886  sub     rsp, 20h
0x18000788a  cmp     dword ptr [rcx+10h], 0
0x18000788e  lea     rax, ??_7?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@6B@; const Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'
0x180007895  mov     [rcx], rax
0x180007898  mov     edi, edx
0x18000789a  mov     rbx, rcx
0x18000789d  jnz     short loc_1800078A4
0x18000789f  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x1800078a4  mov     rcx, [rbx+30h]
0x1800078a8  test    rcx, rcx
0x1800078ab  jz      short loc_1800078C1
0x1800078ad  mov     qword ptr [rbx+30h], 0
0x1800078b5  mov     rax, [rcx]
0x1800078b8  mov     rax, [rax+10h]
0x1800078bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078c1  mov     rcx, [rbx+18h]
0x1800078c5  test    rcx, rcx
0x1800078c8  jz      short loc_1800078DE
0x1800078ca  mov     qword ptr [rbx+18h], 0
0x1800078d2  mov     rax, [rcx]
0x1800078d5  mov     rax, [rax+10h]
0x1800078d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078de  test    dil, 1
0x1800078e2  jz      short loc_1800078EC
0x1800078e4  mov     rcx, rbx; Block
0x1800078e7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800078ec  mov     rax, rbx
0x1800078ef  mov     rbx, [rsp+28h+arg_0]
0x1800078f4  add     rsp, 20h
0x1800078f8  pop     rdi
0x1800078f9  retn
```
