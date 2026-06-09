# Microsoft::WRL::Details::Make<WpcDesktop::OTS::Manager::WpcOtsTimeRequest,WpcDesktop::OTS::Manager::RequestManagerDependencies const &,std::shared_ptr<Com::InterfaceMarshaler<IWpcOtsRequestManager>> &,Sid &>(WpcDesktop::OTS::Manager::RequestManagerDependencies const &,std::shared_ptr<Com::InterfaceMarshaler<IWpcOtsRequestManager>> &,Sid &)

- ea: `0x18000b6e0`
- end: `0x18000b7a5`
- name: `??$Make@VWpcOtsTimeRequest@Manager@OTS@WpcDesktop@@AEBURequestManagerDependencies@234@AEAV?$shared_ptr@V?$InterfaceMarshaler@UIWpcOtsRequestManager@@@Com@@@std@@AEAVSid@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWpcOtsTimeRequest@Manager@OTS@WpcDesktop@@@12@AEBURequestManagerDependencies@Manager@OTS@WpcDesktop@@AEAV?$shared_ptr@V?$InterfaceMarshaler@UIWpcOtsRequestManager@@@Com@@@std@@AEAVSid@@@Z`
- size: `197`
- prototype: `__int64 *__fastcall(__int64 *, __int64, __int128 *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c164`

## callees

- `0x180003308`
- `0x1800036d8`
- `0x18000b6e0`
- `0x18000b808`
- `0x18002c010`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::Details::Make<WpcDesktop::OTS::Manager::WpcOtsTimeRequest,WpcDesktop::OTS::Manager::RequestManagerDependencies const &,std::shared_ptr<Com::InterfaceMarshaler<IWpcOtsRequestManager>> &,Sid &>(
        __int64 *a1,
        __int64 a2,
        __int128 *a3,
        __int64 a4)
{
  void *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int128 v12[3]; // [rsp+40h] [rbp-38h] BYREF

  *a1 = 0;
  v8 = operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v8 )
  {
    v12[0] = 0;
    v9 = *((_QWORD *)a3 + 1);
    if ( v9 )
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
    v12[0] = *a3;
    v10 = ((__int64 (__fastcall *)(void *, __int64, __int128 *, __int64, int, void *, void *, void *))WpcDesktop::OTS::Manager::WpcOtsTimeRequest::WpcOtsTimeRequest)(
            v8,
            a2,
            v12,
            a4,
            1,
            v8,
            v8,
            v8);
    if ( *a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v10;
  }
  return a1;
}

```

## disassembly

```asm
0x18000b6e0  mov     [rsp+arg_0], rcx
0x18000b6e5  push    rbx
0x18000b6e6  push    rbp
0x18000b6e7  push    rsi
0x18000b6e8  push    rdi
0x18000b6e9  sub     rsp, 58h
0x18000b6ed  mov     rsi, r9
0x18000b6f0  mov     rdi, r8
0x18000b6f3  mov     rbp, rdx
0x18000b6f6  mov     rbx, rcx
0x18000b6f9  mov     [rsp+78h+var_58], 0
0x18000b701  mov     qword ptr [rcx], 0
0x18000b708  mov     [rsp+78h+var_58], 1
0x18000b710  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b717  mov     ecx, 0B0h; unsigned __int64
0x18000b71c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b721  mov     [rsp+78h+var_50], rax
0x18000b726  mov     [rsp+78h+var_48], rax
0x18000b72b  test    rax, rax
0x18000b72e  jz      short loc_18000B78B
0x18000b730  mov     [rsp+78h+var_40], rax
0x18000b735  xorps   xmm0, xmm0
0x18000b738  movdqu  [rsp+78h+var_38], xmm0
0x18000b73e  mov     rcx, [rdi+8]
0x18000b742  test    rcx, rcx
0x18000b745  jz      short loc_18000B74B
0x18000b747  lock inc dword ptr [rcx+8]
0x18000b74b  mov     rcx, [rdi]
0x18000b74e  mov     qword ptr [rsp+78h+var_38], rcx
0x18000b753  mov     rcx, [rdi+8]
0x18000b757  mov     qword ptr [rsp+78h+var_38+8], rcx
0x18000b75c  mov     r9, rsi
0x18000b75f  lea     r8, [rsp+78h+var_38]
0x18000b764  mov     rdx, rbp
0x18000b767  mov     rcx, rax
0x18000b76a  call    ??0WpcOtsTimeRequest@Manager@OTS@WpcDesktop@@QEAA@AEBURequestManagerDependencies@123@V?$shared_ptr@V?$InterfaceMarshaler@UIWpcOtsRequestManager@@@Com@@@std@@AEBVSid@@@Z; WpcDesktop::OTS::Manager::WpcOtsTimeRequest::WpcOtsTimeRequest(WpcDesktop::OTS::Manager::RequestManagerDependencies const &,std::shared_ptr<Com::InterfaceMarshaler<IWpcOtsRequestManager>>,Sid const &)
0x18000b76f  mov     rdi, rax
0x18000b772  mov     rcx, [rbx]
0x18000b775  test    rcx, rcx
0x18000b778  jz      short loc_18000B786
0x18000b77a  mov     rdx, [rcx]
0x18000b77d  mov     rax, [rdx+10h]
0x18000b781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b786  mov     [rbx], rdi
0x18000b789  xor     eax, eax
0x18000b78b  test    rax, rax
0x18000b78e  jz      short loc_18000B798
0x18000b790  mov     rcx, rax; Block
0x18000b793  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b798  mov     rax, rbx
0x18000b79b  add     rsp, 58h
0x18000b79f  pop     rdi
0x18000b7a0  pop     rsi
0x18000b7a1  pop     rbp
0x18000b7a2  pop     rbx
0x18000b7a3  retn
```
