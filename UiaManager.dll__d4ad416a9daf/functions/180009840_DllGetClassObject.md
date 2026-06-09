# DllGetClassObject

- ea: `0x180009840`
- end: `0x180009a9f`
- name: `DllGetClassObject`
- size: `607`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009840`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800099f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800099f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009982`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009982`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800099c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009a65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800099c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009a65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009a51`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009a51`
- `RPCRT4!NdrDllGetClassObject` at `0x180009875`
- `RPCRT4!NdrDllGetClassObject` at `0x180009875`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180009897`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180009897`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009998`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009a34`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009998`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009a34`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009a0d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009a0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rax
  _QWORD *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rbx
  HRESULT v12; // edi
  RTL_SRWLOCK *v13; // rsi
  void *v14; // rcx
  RTL_SRWLOCK *v15; // rsi
  void *v16; // rcx
  PVOID v17; // rdi
  PVOID Ptr[9]; // [rsp+30h] [rbp-48h] BYREF
  int v19; // [rsp+98h] [rbp+20h] BYREF

  result = NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  if ( result < 0 )
  {
    InitOnceExecuteOnce(
      &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
      _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_1800C51B8 = 1;
    *ppv = 0;
    v7 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                              + 32))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
       + 8;
    v8 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                              + 40))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
    while ( 1 )
    {
      if ( v7 >= v8 )
        return -2147221231;
      if ( *(_QWORD *)v7 )
      {
        v9 = *(_QWORD **)(*(_QWORD *)v7 + 8LL);
        v10 = *v9 - *(_QWORD *)&rclsid->Data1;
        if ( *v9 == *(_QWORD *)&rclsid->Data1 )
          v10 = v9[1] - *(_QWORD *)rclsid->Data4;
        if ( !v10 )
          break;
      }
      v7 += 8LL;
    }
    _mm_lfence();
    v19 = 1;
    v11 = *(_QWORD *)v7;
    *ppv = 0;
    Ptr[0] = 0;
    if ( **(_QWORD **)(v11 + 24) )
    {
      v13 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                + 56))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
      AcquireSRWLockShared(v13);
      v14 = **(void ***)(v11 + 24);
      if ( v14 )
      {
        Ptr[0] = DecodePointer(v14);
        v12 = (**(__int64 (__fastcall ***)(PVOID, const IID *const, LPVOID *))Ptr[0])(Ptr[0], riid, ppv);
        if ( v13 )
          ReleaseSRWLockShared(v13);
        return v12;
      }
      if ( v13 )
        ReleaseSRWLockShared(v13);
    }
    v12 = (*(__int64 (__fastcall **)(int *, __int64, const IID *const, PVOID *))v11)(&v19, v11, riid, Ptr);
    if ( v12 >= 0 )
    {
      if ( (v19 & 4) != 0 )
        goto LABEL_22;
      v15 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                + 56))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
      AcquireSRWLockExclusive(v15);
      v16 = **(void ***)(v11 + 24);
      if ( v16 )
      {
        v17 = DecodePointer(v16);
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)v17 + 8LL))(v17);
      }
      else
      {
        v17 = 0;
        **(_QWORD **)(v11 + 24) = EncodePointer(Ptr[0]);
      }
      if ( v15 )
        ReleaseSRWLockExclusive(v15);
      if ( v17 )
      {
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr[0] + 16LL))(Ptr[0]);
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr[0] + 16LL))(Ptr[0]);
      }
      else
      {
LABEL_22:
        v17 = Ptr[0];
      }
      *ppv = v17;
      return 0;
    }
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x180009840  push    rbx
0x180009842  push    rbp
0x180009843  push    rsi
0x180009844  push    rdi
0x180009845  push    r14
0x180009847  push    r15
0x180009849  sub     rsp, 48h
0x18000984d  mov     r14, r8
0x180009850  mov     rbp, rdx
0x180009853  mov     rdi, rcx
0x180009856  lea     rax, gPFactory
0x18000985d  mov     [rsp+78h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180009862  lea     rax, CLSID_PSFactoryBuffer
0x180009869  mov     [rsp+78h+pclsid], rax; pclsid
0x18000986e  lea     r9, aProxyFileList; pProxyFileList
0x180009875  call    cs:__imp_NdrDllGetClassObject
0x18000987b  test    eax, eax
0x18000987d  jns     loc_180009958
0x180009883  xor     r9d, r9d; Context
0x180009886  xor     r8d, r8d; Parameter
0x180009889  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180009890  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180009897  call    cs:__imp_InitOnceExecuteOnce
0x18000989d  mov     cs:byte_1800C51B8, 1
0x1800098a4  xor     r15d, r15d
0x1800098a7  mov     [r14], r15
0x1800098aa  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800098b1  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800098b8  mov     rax, [rax+20h]
0x1800098bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098c1  lea     rbx, [rax+8]
0x1800098c5  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800098cc  mov     rax, [rcx+28h]
0x1800098d0  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800098d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098dc  nop     dword ptr [rax+00h]
0x1800098e0  cmp     rbx, rax
0x1800098e3  jnb     loc_180009A70
0x1800098e9  mov     rcx, [rbx]
0x1800098ec  test    rcx, rcx
0x1800098ef  jz      short loc_18000990A
0x1800098f1  mov     rdx, [rcx+8]
0x1800098f5  mov     rcx, [rdx]
0x1800098f8  sub     rcx, [rdi]
0x1800098fb  jnz     short loc_180009905
0x1800098fd  mov     rcx, [rdx+8]
0x180009901  sub     rcx, [rdi+8]
0x180009905  test    rcx, rcx
0x180009908  jz      short loc_180009910
0x18000990a  add     rbx, 8
0x18000990e  jmp     short loc_1800098E0
0x180009910  lfence
0x180009913  mov     [rsp+78h+arg_18], 1
0x18000991e  mov     rbx, [rbx]
0x180009921  mov     [r14], r15
0x180009924  mov     [rsp+78h+Ptr], r15
0x180009929  mov     rax, [rbx+18h]
0x18000992d  mov     rcx, [rax]
0x180009930  test    rcx, rcx
0x180009933  jnz     short loc_180009965
0x180009935  lea     r9, [rsp+78h+Ptr]
0x18000993a  mov     r8, rbp
0x18000993d  mov     rdx, rbx
0x180009940  lea     rcx, [rsp+78h+arg_18]
0x180009948  mov     rax, [rbx]
0x18000994b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009950  mov     edi, eax
0x180009952  test    eax, eax
0x180009954  jns     short loc_1800099CC
0x180009956  mov     eax, edi
0x180009958  add     rsp, 48h
0x18000995c  pop     r15
0x18000995e  pop     r14
0x180009960  pop     rdi
0x180009961  pop     rsi
0x180009962  pop     rbp
0x180009963  pop     rbx
0x180009964  retn
0x180009965  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000996c  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180009973  mov     rax, [rax+38h]
0x180009977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000997c  mov     rsi, rax
0x18000997f  mov     rcx, rax; SRWLock
0x180009982  call    cs:__imp_AcquireSRWLockShared
0x180009988  mov     rcx, [rbx+18h]
0x18000998c  mov     rcx, [rcx]; Ptr
0x18000998f  test    rcx, rcx
0x180009992  jz      loc_180009A59
0x180009998  call    cs:__imp_DecodePointer
0x18000999e  mov     r9, rax
0x1800099a1  mov     [rsp+78h+Ptr], rax
0x1800099a6  mov     rcx, [rax]
0x1800099a9  mov     rax, [rcx]
0x1800099ac  mov     r8, r14
0x1800099af  mov     rdx, rbp
0x1800099b2  mov     rcx, r9
0x1800099b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ba  mov     edi, eax
0x1800099bc  test    rsi, rsi
0x1800099bf  jz      short loc_180009956
0x1800099c1  mov     rcx, rsi; SRWLock
0x1800099c4  call    cs:__imp_ReleaseSRWLockShared
0x1800099ca  jmp     short loc_180009956
0x1800099cc  test    byte ptr [rsp+78h+arg_18], 4
0x1800099d4  jnz     short loc_180009A24
0x1800099d6  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800099dd  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800099e4  mov     rax, [rax+38h]
0x1800099e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ed  mov     rsi, rax
0x1800099f0  mov     rcx, rax; SRWLock
0x1800099f3  call    cs:__imp_AcquireSRWLockExclusive
0x1800099f9  mov     rcx, [rbx+18h]
0x1800099fd  mov     rcx, [rcx]; Ptr
0x180009a00  test    rcx, rcx
0x180009a03  jnz     short loc_180009A34
0x180009a05  mov     rdi, r15
0x180009a08  mov     rcx, [rsp+78h+Ptr]; Ptr
0x180009a0d  call    cs:__imp_EncodePointer
0x180009a13  mov     rcx, [rbx+18h]
0x180009a17  mov     [rcx], rax
0x180009a1a  test    rsi, rsi
0x180009a1d  jnz     short loc_180009A4E
0x180009a1f  test    rdi, rdi
0x180009a22  jnz     short loc_180009A7A
0x180009a24  mov     rdi, [rsp+78h+Ptr]
0x180009a29  mov     [r14], rdi
0x180009a2c  mov     edi, r15d
0x180009a2f  jmp     loc_180009956
0x180009a34  call    cs:__imp_DecodePointer
0x180009a3a  mov     rdi, rax
0x180009a3d  mov     rcx, [rax]
0x180009a40  mov     rax, [rcx+8]
0x180009a44  mov     rcx, rdi
0x180009a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a4c  jmp     short loc_180009A1A
0x180009a4e  mov     rcx, rsi; SRWLock
0x180009a51  call    cs:__imp_ReleaseSRWLockExclusive
0x180009a57  jmp     short loc_180009A1F
0x180009a59  test    rsi, rsi
0x180009a5c  jz      loc_180009935
0x180009a62  mov     rcx, rsi; SRWLock
0x180009a65  call    cs:__imp_ReleaseSRWLockShared
0x180009a6b  jmp     loc_180009935
0x180009a70  mov     edi, 80040111h
0x180009a75  jmp     loc_180009956
0x180009a7a  mov     rcx, [rsp+78h+Ptr]
0x180009a7f  mov     rax, [rcx]
0x180009a82  mov     rax, [rax+10h]
0x180009a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a8b  mov     rcx, [rsp+78h+Ptr]
0x180009a90  mov     rax, [rcx]
0x180009a93  mov     rax, [rax+10h]
0x180009a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a9c  jmp     short loc_180009A29
```
