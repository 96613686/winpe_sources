# Wallet::WalletWebServiceRequest::Cancel(void)

- ea: `0x180035f00`
- end: `0x180035f52`
- name: `?Cancel@WalletWebServiceRequest@Wallet@@UEAAJXZ`
- size: `82`
- prototype: `__int64 __fastcall(Wallet::WalletWebServiceRequest *this, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180035f00`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180035f1a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180035f1a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180035f27`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180035f27`

## pseudocode

```c
__int64 __fastcall Wallet::WalletWebServiceRequest::Cancel(Wallet::WalletWebServiceRequest *this, __int64 a2)
{
  struct _TP_WORK *v3; // rcx

  v3 = (struct _TP_WORK *)*((_QWORD *)this + 17);
  if ( v3 )
  {
    WaitForThreadpoolWorkCallbacks(v3, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 17));
    *((_QWORD *)this + 17) = 0;
  }
  LOBYTE(a2) = 1;
  return (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 208LL))(*((_QWORD *)this + 4), a2);
}

```

## disassembly

```asm
0x180035f00  push    rbx
0x180035f02  sub     rsp, 20h
0x180035f06  mov     rbx, rcx
0x180035f09  mov     rcx, [rcx+88h]; pwk
0x180035f10  test    rcx, rcx
0x180035f13  jz      short loc_180035F38
0x180035f15  mov     edx, 1; fCancelPendingCallbacks
0x180035f1a  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180035f20  mov     rcx, [rbx+88h]; pwk
0x180035f27  call    cs:__imp_CloseThreadpoolWork
0x180035f2d  mov     qword ptr [rbx+88h], 0
0x180035f38  mov     rcx, [rbx+20h]
0x180035f3c  mov     dl, 1
0x180035f3e  mov     rax, [rcx]
0x180035f41  mov     rax, [rax+0D0h]
0x180035f48  add     rsp, 20h
0x180035f4c  pop     rbx
0x180035f4d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
