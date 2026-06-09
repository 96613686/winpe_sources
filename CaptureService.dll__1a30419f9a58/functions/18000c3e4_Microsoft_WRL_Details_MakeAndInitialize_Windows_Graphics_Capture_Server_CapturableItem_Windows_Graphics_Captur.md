# Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(Windows::Graphics::Capture::Server::CapturableItem * *,Windows::Internal::PlatformExtensions::Capture::ICapturableItem * &&,bool &&)

- ea: `0x18000c3e4`
- end: `0x18000c4ca`
- name: `??$MakeAndInitialize@VCapturableItem@Server@Capture@Graphics@Windows@@V12345@PEAUICapturableItem@3PlatformExtensions@Internal@5@_N@Details@WRL@Microsoft@@YAJPEAPEAVCapturableItem@Server@Capture@Graphics@Windows@@$$QEAPEAUICapturableItem@5PlatformExtensions@Internal@7@$$QEA_N@Z`
- size: `230`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server::CapturableItem **, struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem **, char *)`
- caller_count: `7`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e3b8`
- `0x180016050`
- `0x180016370`
- `0x180016540`
- `0x1800167e0`
- `0x1800169d8`
- `0x180016dc4`

## callees

- `0x18000335c`
- `0x18000c3e4`
- `0x18000d5b4`
- `0x18000dc98`
- `0x18000edd0`
- `0x180014948`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(
        Windows::Graphics::Capture::Server::CapturableItem **a1,
        struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem **a2,
        char *a3)
{
  Windows::Graphics::Capture::Server::CapturableItem *v6; // rax
  int v7; // edi
  __int64 v8; // rax
  char v9; // r8
  Windows::Graphics::Capture::Server::CapturableItem *v10; // rbx
  Windows::Graphics::Capture::Server::CapturableItem *v12; // [rsp+30h] [rbp+8h] BYREF
  Windows::Graphics::Capture::Server::CapturableItem *v13; // [rsp+48h] [rbp+20h] BYREF

  *a1 = 0;
  v6 = (Windows::Graphics::Capture::Server::CapturableItem *)operator new(
                                                               0x78u,
                                                               (const struct std::nothrow_t *)std::nothrow);
  v13 = v6;
  if ( v6 )
  {
    v8 = Windows::Graphics::Capture::Server::CapturableItem::CapturableItem(v6);
    v12 = 0;
    Microsoft::WRL::ComPtr<Windows::Graphics::Capture::Server::CapturableItem>::Attach(&v12, v8);
    v13 = 0;
    v9 = *a3;
    v10 = v12;
    v7 = Windows::Graphics::Capture::Server::CapturableItem::RuntimeClassInitialize(v12, *a2, v9);
    if ( v7 >= 0 )
    {
      if ( v10 )
        (*(void (__fastcall **)(Windows::Graphics::Capture::Server::CapturableItem *))(*(_QWORD *)v10 + 8LL))(v10);
      *a1 = v10;
      if ( v10 )
        (*(void (__fastcall **)(Windows::Graphics::Capture::Server::CapturableItem *))(*(_QWORD *)v10 + 16LL))(v10);
      v7 = 0;
    }
    else if ( v10 )
    {
      (*(void (__fastcall **)(Windows::Graphics::Capture::Server::CapturableItem *))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  else
  {
    v7 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000c3e4  mov     [rsp+arg_8], rbx
0x18000c3e9  mov     [rsp+arg_10], rsi
0x18000c3ee  push    rdi
0x18000c3ef  sub     rsp, 20h
0x18000c3f3  mov     rbx, r8
0x18000c3f6  mov     rdi, rdx
0x18000c3f9  mov     rsi, rcx
0x18000c3fc  mov     qword ptr [rcx], 0
0x18000c403  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c40a  mov     ecx, 78h ; 'x'; unsigned __int64
0x18000c40f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c414  mov     [rsp+28h+arg_18], rax
0x18000c419  test    rax, rax
0x18000c41c  jnz     short loc_18000C428
0x18000c41e  mov     edi, 8007000Eh
0x18000c423  jmp     loc_18000C4AE
0x18000c428  mov     rcx, rax; this
0x18000c42b  call    ??0CapturableItem@Server@Capture@Graphics@Windows@@QEAA@XZ; Windows::Graphics::Capture::Server::CapturableItem::CapturableItem(void)
0x18000c430  mov     [rsp+28h+arg_0], 0
0x18000c439  mov     rdx, rax
0x18000c43c  lea     rcx, [rsp+28h+arg_0]
0x18000c441  call    ?Attach@?$ComPtr@VCapturableItem@Server@Capture@Graphics@Windows@@@WRL@Microsoft@@QEAAXPEAVCapturableItem@Server@Capture@Graphics@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Graphics::Capture::Server::CapturableItem>::Attach(Windows::Graphics::Capture::Server::CapturableItem *)
0x18000c446  mov     [rsp+28h+arg_18], 0
0x18000c44f  mov     r8b, [rbx]; bool
0x18000c452  mov     rdx, [rdi]; struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *
0x18000c455  mov     rbx, [rsp+28h+arg_0]
0x18000c45a  mov     rcx, rbx; this
0x18000c45d  call    ?RuntimeClassInitialize@CapturableItem@Server@Capture@Graphics@Windows@@QEAAJPEAUICapturableItem@3PlatformExtensions@Internal@5@_N@Z; Windows::Graphics::Capture::Server::CapturableItem::RuntimeClassInitialize(Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool)
0x18000c462  mov     edi, eax
0x18000c464  test    eax, eax
0x18000c466  jns     short loc_18000C47F
0x18000c468  test    rbx, rbx
0x18000c46b  jz      short loc_18000C47D
0x18000c46d  mov     rcx, [rbx]
0x18000c470  mov     rax, [rcx+10h]
0x18000c474  mov     rcx, rbx
0x18000c477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c47c  nop
0x18000c47d  jmp     short loc_18000C4AE
0x18000c47f  test    rbx, rbx
0x18000c482  jz      short loc_18000C494
0x18000c484  mov     rax, [rbx]
0x18000c487  mov     rcx, rbx
0x18000c48a  mov     rax, [rax+8]
0x18000c48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c493  nop
0x18000c494  mov     [rsi], rbx
0x18000c497  test    rbx, rbx
0x18000c49a  jz      short loc_18000C4AC
0x18000c49c  mov     rax, [rbx]
0x18000c49f  mov     rcx, rbx
0x18000c4a2  mov     rax, [rax+10h]
0x18000c4a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4ab  nop
0x18000c4ac  xor     edi, edi
0x18000c4ae  lea     rcx, [rsp+28h+arg_18]
0x18000c4b3  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x18000c4b8  mov     eax, edi
0x18000c4ba  mov     rbx, [rsp+28h+arg_8]
0x18000c4bf  mov     rsi, [rsp+28h+arg_10]
0x18000c4c4  add     rsp, 20h
0x18000c4c8  pop     rdi
0x18000c4c9  retn
```
