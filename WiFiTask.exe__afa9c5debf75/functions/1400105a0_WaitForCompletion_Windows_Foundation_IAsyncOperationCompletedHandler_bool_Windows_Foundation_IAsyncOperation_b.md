# `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`scalar deleting destructor'(uint)

- ea: `0x1400105a0`
- end: `0x140010614`
- name: `??_GFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@EEAAPEAXI@Z`
- size: `116`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1400016c4`
- `0x1400105a0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400105c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400105c8`

## pseudocode

```c
void *__fastcall `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>'::`2'::FTMEventDelegate::`scalar deleting destructor'(
        void *Block,
        char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)Block = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)Block + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>'::`2'::FTMEventDelegate::`vftable';
  CloseHandle(*((HANDLE *)Block + 7));
  *((_DWORD *)Block + 11) = -1073741823;
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
0x1400105a0  mov     [rsp+arg_0], rbx
0x1400105a5  push    rdi
0x1400105a6  sub     rsp, 20h
0x1400105aa  mov     edi, edx
0x1400105ac  mov     rbx, rcx
0x1400105af  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@_N@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x1400105b6  mov     [rcx], rax
0x1400105b9  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1400105c0  mov     [rcx+8], rax
0x1400105c4  mov     rcx, [rcx+38h]; hObject
0x1400105c8  call    cs:__imp_CloseHandle
0x1400105ce  mov     dword ptr [rbx+2Ch], 0C0000001h
0x1400105d5  mov     rcx, [rbx+20h]
0x1400105d9  test    rcx, rcx
0x1400105dc  jz      short loc_1400105F3
0x1400105de  mov     qword ptr [rbx+20h], 0
0x1400105e6  mov     rax, [rcx]
0x1400105e9  mov     rax, [rax+10h]
0x1400105ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400105f2  nop
0x1400105f3  test    dil, 1
0x1400105f7  jz      short loc_140010606
0x1400105f9  mov     edx, 40h ; '@'
0x1400105fe  mov     rcx, rbx; Block
0x140010601  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140010606  mov     rax, rbx
0x140010609  mov     rbx, [rsp+28h+arg_0]
0x14001060e  add     rsp, 20h
0x140010612  pop     rdi
0x140010613  retn
```
