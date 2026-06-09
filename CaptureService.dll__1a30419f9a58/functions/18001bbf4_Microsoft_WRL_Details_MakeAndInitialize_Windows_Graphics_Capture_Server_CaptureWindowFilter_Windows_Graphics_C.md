# Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CaptureWindowFilter,Windows::Graphics::Capture::Server::CaptureWindowFilter,Windows::Internal::PlatformExtensions::Capture::IFilteredCaptureSession *>(Windows::Graphics::Capture::Server::CaptureWindowFilter * *,Windows::Internal::PlatformExtensions::Capture::IFilteredCaptureSession * &&)

- ea: `0x18001bbf4`
- end: `0x18001bcc2`
- name: `??$MakeAndInitialize@VCaptureWindowFilter@Server@Capture@Graphics@Windows@@V12345@PEAUIFilteredCaptureSession@3PlatformExtensions@Internal@5@@Details@WRL@Microsoft@@YAJPEAPEAVCaptureWindowFilter@Server@Capture@Graphics@Windows@@$$QEAPEAUIFilteredCaptureSession@5PlatformExtensions@Internal@7@@Z`
- size: `206`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ca68`

## callees

- `0x18000335c`
- `0x18000dc98`
- `0x18001bbf4`
- `0x18001bffc`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CaptureWindowFilter,Windows::Graphics::Capture::Server::CaptureWindowFilter,Windows::Internal::PlatformExtensions::Capture::IFilteredCaptureSession *>(
        _QWORD *a1,
        __int64 *a2)
{
  Windows::Graphics::Capture::Server::CaptureWindowFilter *v4; // rax
  unsigned int v5; // ebx
  _QWORD *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rdi
  Windows::Graphics::Capture::Server::CaptureWindowFilter *v10; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = (Windows::Graphics::Capture::Server::CaptureWindowFilter *)operator new(
                                                                    0x40u,
                                                                    (const struct std::nothrow_t *)std::nothrow);
  v10 = v4;
  if ( v4 )
  {
    v6 = (_QWORD *)Windows::Graphics::Capture::Server::CaptureWindowFilter::CaptureWindowFilter(v4);
    v10 = 0;
    v7 = *a2;
    v8 = v6[6];
    v6[6] = v7;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v6 )
      (*(void (__fastcall **)(_QWORD *))(*v6 + 8LL))(v6);
    *a1 = v6;
    if ( v6 )
      (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
    v5 = 0;
  }
  else
  {
    v5 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v10);
  return v5;
}

```

## disassembly

```asm
0x18001bbf4  mov     [rsp+arg_8], rbx
0x18001bbf9  mov     [rsp+arg_10], rsi
0x18001bbfe  push    rdi
0x18001bbff  sub     rsp, 20h
0x18001bc03  mov     rdi, rdx
0x18001bc06  mov     rsi, rcx
0x18001bc09  mov     qword ptr [rcx], 0
0x18001bc10  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bc17  mov     ecx, 40h ; '@'; unsigned __int64
0x18001bc1c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001bc21  mov     [rsp+28h+arg_0], rax
0x18001bc26  test    rax, rax
0x18001bc29  jnz     short loc_18001BC32
0x18001bc2b  mov     ebx, 8007000Eh
0x18001bc30  jmp     short loc_18001BCA6
0x18001bc32  mov     rcx, rax; this
0x18001bc35  call    ??0CaptureWindowFilter@Server@Capture@Graphics@Windows@@QEAA@XZ; Windows::Graphics::Capture::Server::CaptureWindowFilter::CaptureWindowFilter(void)
0x18001bc3a  mov     rbx, rax
0x18001bc3d  mov     [rsp+28h+arg_0], 0
0x18001bc46  mov     rcx, [rdi]
0x18001bc49  mov     rdi, [rax+30h]
0x18001bc4d  mov     [rax+30h], rcx
0x18001bc51  test    rcx, rcx
0x18001bc54  jz      short loc_18001BC62
0x18001bc56  mov     rdx, [rcx]
0x18001bc59  mov     rax, [rdx+8]
0x18001bc5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc62  test    rdi, rdi
0x18001bc65  jz      short loc_18001BC77
0x18001bc67  mov     rax, [rdi]
0x18001bc6a  mov     rcx, rdi
0x18001bc6d  mov     rax, [rax+10h]
0x18001bc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc76  nop
0x18001bc77  test    rbx, rbx
0x18001bc7a  jz      short loc_18001BC8C
0x18001bc7c  mov     rax, [rbx]
0x18001bc7f  mov     rcx, rbx
0x18001bc82  mov     rax, [rax+8]
0x18001bc86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc8b  nop
0x18001bc8c  mov     [rsi], rbx
0x18001bc8f  test    rbx, rbx
0x18001bc92  jz      short loc_18001BCA4
0x18001bc94  mov     rax, [rbx]
0x18001bc97  mov     rcx, rbx
0x18001bc9a  mov     rax, [rax+10h]
0x18001bc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bca3  nop
0x18001bca4  xor     ebx, ebx
0x18001bca6  lea     rcx, [rsp+28h+arg_0]
0x18001bcab  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x18001bcb0  mov     eax, ebx
0x18001bcb2  mov     rbx, [rsp+28h+arg_8]
0x18001bcb7  mov     rsi, [rsp+28h+arg_10]
0x18001bcbc  add     rsp, 20h
0x18001bcc0  pop     rdi
0x18001bcc1  retn
```
