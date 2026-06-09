# Wallet::WalletWebServiceRequest::ExecuteAsync(ushort const *)

- ea: `0x180036300`
- end: `0x1800363a3`
- name: `?ExecuteAsync@WalletWebServiceRequest@Wallet@@UEAAJPEBG@Z`
- size: `163`
- prototype: `__int64 __fastcall(PVOID pv, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ae4`
- `0x180013fe4`
- `0x180036300`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003635c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003635c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003634a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003634a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180036381`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180036381`

## pseudocode

```c
__int64 __fastcall Wallet::WalletWebServiceRequest::ExecuteAsync(PVOID pv, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  struct _TP_WORK *ThreadpoolWork; // rax
  signed int LastError; // eax
  PVOID v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = pv;
  if ( pv )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)pv + 8LL))(pv);
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          (__int64)pv + 80,
                          (__int64)a2) )
  {
    ThreadpoolWork = CreateThreadpoolWork(Wallet::WalletWebServiceRequest::ExecuteWork, pv, 0);
    *((_QWORD *)pv + 17) = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      v4 = 0;
      SubmitThreadpoolWork(ThreadpoolWork);
      v8 = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v4 = -2143748092;
      }
    }
  }
  else
  {
    v4 = -2147024882;
  }
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v8);
  return v4;
}

```

## disassembly

```asm
0x180036300  mov     [rsp+arg_8], rbx
0x180036305  push    rdi
0x180036306  sub     rsp, 20h
0x18003630a  mov     [rsp+28h+arg_0], rcx
0x18003630f  mov     rdi, rdx
0x180036312  mov     rbx, rcx
0x180036315  test    rcx, rcx
0x180036318  jz      short loc_180036326
0x18003631a  mov     rax, [rcx]
0x18003631d  mov     rax, [rax+8]
0x180036321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036326  lea     rcx, [rbx+50h]
0x18003632a  mov     rdx, rdi
0x18003632d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180036332  test    al, al
0x180036334  jnz     short loc_18003633D
0x180036336  mov     ebx, 8007000Eh
0x18003633b  jmp     short loc_18003638C
0x18003633d  xor     r8d, r8d; pcbe
0x180036340  lea     rcx, ?ExecuteWork@WalletWebServiceRequest@Wallet@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180036347  mov     rdx, rbx; pv
0x18003634a  call    cs:__imp_CreateThreadpoolWork
0x180036350  mov     [rbx+88h], rax
0x180036357  test    rax, rax
0x18003635a  jnz     short loc_18003637C
0x18003635c  call    cs:__imp_GetLastError
0x180036362  mov     ebx, eax
0x180036364  test    eax, eax
0x180036366  jz      short loc_180036375
0x180036368  jle     short loc_18003638C
0x18003636a  movzx   ebx, ax
0x18003636d  or      ebx, 80070000h
0x180036373  jmp     short loc_18003638C
0x180036375  mov     ebx, 80390004h
0x18003637a  jmp     short loc_18003638C
0x18003637c  xor     ebx, ebx
0x18003637e  mov     rcx, rax; pwk
0x180036381  call    cs:__imp_SubmitThreadpoolWork
0x180036387  mov     [rsp+28h+arg_0], rbx
0x18003638c  lea     rcx, [rsp+28h+arg_0]
0x180036391  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180036396  mov     eax, ebx
0x180036398  mov     rbx, [rsp+28h+arg_8]
0x18003639d  add     rsp, 20h
0x1800363a1  pop     rdi
0x1800363a2  retn
```
