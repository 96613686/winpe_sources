# DllGetClassObject

- ea: `0x180013de0`
- end: `0x18001404d`
- name: `DllGetClassObject`
- size: `621`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180013de0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013fa3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013fa3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013fd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013fd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180013f0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001401d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180013f0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001401d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180013ecb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180013ecb`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180013fbd`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180013fbd`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180013ee1`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180013ff7`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180013ee1`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180013ff7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180013e13`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180013e13`
- `RPCRT4!NdrDllGetClassObject` at `0x180013f59`
- `RPCRT4!NdrDllGetClassObject` at `0x180013f59`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rax
  _QWORD *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r14
  RTL_SRWLOCK *v11; // rsi
  void *v12; // rcx
  HRESULT v13; // ebx
  RTL_SRWLOCK *v15; // rsi
  void *v16; // rcx
  PVOID v17; // rbx
  int v18; // [rsp+70h] [rbp+18h] BYREF
  PVOID Ptr; // [rsp+78h] [rbp+20h] BYREF

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180072D28 = 1;
  *ppv = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                            + 32))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
     + 8;
  v7 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                            + 40))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  while ( 1 )
  {
    if ( v6 >= v7 )
    {
      v13 = -2147221231;
      goto LABEL_12;
    }
    if ( *(_QWORD *)v6 )
    {
      v8 = *(_QWORD **)(*(_QWORD *)v6 + 8LL);
      v9 = *v8 - *(_QWORD *)&rclsid->Data1;
      if ( *v8 == *(_QWORD *)&rclsid->Data1 )
        v9 = v8[1] - *(_QWORD *)rclsid->Data4;
      if ( !v9 )
        break;
    }
    v6 += 8LL;
  }
  _mm_lfence();
  v18 = 1;
  v10 = *(_QWORD *)v6;
  *ppv = 0;
  Ptr = 0;
  if ( **(_QWORD **)(v10 + 24) )
  {
    v11 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                              + 56))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
    AcquireSRWLockShared(v11);
    v12 = **(void ***)(v10 + 24);
    if ( v12 )
    {
      Ptr = DecodePointer(v12);
      v13 = (**(__int64 (__fastcall ***)(PVOID, const IID *const, LPVOID *))Ptr)(Ptr, riid, ppv);
      if ( v11 )
        ReleaseSRWLockShared(v11);
      goto LABEL_12;
    }
    if ( v11 )
      ReleaseSRWLockShared(v11);
  }
  v13 = (*(__int64 (__fastcall **)(int *, __int64, const IID *const, PVOID *))v10)(&v18, v10, riid, &Ptr);
  if ( v13 >= 0 )
  {
    if ( (v18 & 4) != 0 )
      goto LABEL_22;
    v15 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                              + 56))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
    AcquireSRWLockExclusive(v15);
    v16 = **(void ***)(v10 + 24);
    if ( v16 )
    {
      v17 = DecodePointer(v16);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v17 + 8LL))(v17);
    }
    else
    {
      v17 = 0;
      **(_QWORD **)(v10 + 24) = EncodePointer(Ptr);
    }
    if ( v15 )
      ReleaseSRWLockExclusive(v15);
    if ( v17 )
    {
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
    }
    else
    {
LABEL_22:
      v17 = Ptr;
    }
    *ppv = v17;
    v13 = 0;
  }
LABEL_12:
  if ( v13 < 0 )
    return NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  else
    return v13;
}

```

## disassembly

```asm
0x180013de0  mov     [rsp+arg_0], rbx
0x180013de5  mov     [rsp+arg_8], rbp
0x180013dea  push    rsi
0x180013deb  push    rdi
0x180013dec  push    r12
0x180013dee  push    r14
0x180013df0  push    r15
0x180013df2  sub     rsp, 30h
0x180013df6  mov     r15, r8
0x180013df9  mov     rbp, rdx
0x180013dfc  mov     rdi, rcx
0x180013dff  xor     r9d, r9d; Context
0x180013e02  xor     r8d, r8d; Parameter
0x180013e05  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180013e0c  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180013e13  call    cs:__imp_InitOnceExecuteOnce
0x180013e19  mov     cs:byte_180072D28, 1
0x180013e20  xor     r12d, r12d
0x180013e23  mov     [r15], r12
0x180013e26  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180013e2d  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180013e34  mov     rax, [rax+20h]
0x180013e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e3d  lea     rbx, [rax+8]
0x180013e41  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180013e48  mov     rax, [rcx+28h]
0x180013e4c  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180013e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e58  cmp     rbx, rax
0x180013e5b  jnb     loc_180013FED
0x180013e61  mov     rcx, [rbx]
0x180013e64  test    rcx, rcx
0x180013e67  jz      short loc_180013E82
0x180013e69  mov     rdx, [rcx+8]
0x180013e6d  mov     rcx, [rdx]
0x180013e70  sub     rcx, [rdi]
0x180013e73  jnz     short loc_180013E7D
0x180013e75  mov     rcx, [rdx+8]
0x180013e79  sub     rcx, [rdi+8]
0x180013e7d  test    rcx, rcx
0x180013e80  jz      short loc_180013E88
0x180013e82  add     rbx, 8
0x180013e86  jmp     short loc_180013E58
0x180013e88  lfence
0x180013e8b  mov     [rsp+58h+arg_10], 1
0x180013e93  mov     r14, [rbx]
0x180013e96  mov     [r15], r12
0x180013e99  mov     [rsp+58h+Ptr], r12
0x180013e9e  mov     rax, [r14+18h]
0x180013ea2  mov     rcx, [rax]
0x180013ea5  test    rcx, rcx
0x180013ea8  jz      loc_180013F61
0x180013eae  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180013eb5  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180013ebc  mov     rax, [rax+38h]
0x180013ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ec5  mov     rsi, rax
0x180013ec8  mov     rcx, rax; SRWLock
0x180013ecb  call    cs:__imp_AcquireSRWLockShared
0x180013ed1  mov     rcx, [r14+18h]
0x180013ed5  mov     rcx, [rcx]; Ptr
0x180013ed8  test    rcx, rcx
0x180013edb  jz      loc_180014011
0x180013ee1  call    cs:__imp_DecodePointer
0x180013ee7  mov     r9, rax
0x180013eea  mov     [rsp+58h+Ptr], rax
0x180013eef  mov     rcx, [rax]
0x180013ef2  mov     rax, [rcx]
0x180013ef5  mov     r8, r15
0x180013ef8  mov     rdx, rbp
0x180013efb  mov     rcx, r9
0x180013efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f03  mov     ebx, eax
0x180013f05  test    rsi, rsi
0x180013f08  jz      short loc_180013F14
0x180013f0a  mov     rcx, rsi; SRWLock
0x180013f0d  call    cs:__imp_ReleaseSRWLockShared
0x180013f13  nop
0x180013f14  test    ebx, ebx
0x180013f16  js      short loc_180013F31
0x180013f18  mov     eax, ebx
0x180013f1a  mov     rbx, [rsp+58h+arg_0]
0x180013f1f  mov     rbp, [rsp+58h+arg_8]
0x180013f24  add     rsp, 30h
0x180013f28  pop     r15
0x180013f2a  pop     r14
0x180013f2c  pop     r12
0x180013f2e  pop     rdi
0x180013f2f  pop     rsi
0x180013f30  retn
0x180013f31  lea     rax, gPFactory
0x180013f38  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180013f3d  lea     rax, CLSID_PSFactoryBuffer
0x180013f44  mov     [rsp+58h+pclsid], rax; pclsid
0x180013f49  lea     r9, aProxyFileList; pProxyFileList
0x180013f50  mov     r8, r15; ppv
0x180013f53  mov     rdx, rbp; riid
0x180013f56  mov     rcx, rdi; rclsid
0x180013f59  call    cs:__imp_NdrDllGetClassObject
0x180013f5f  jmp     short loc_180013F1A
0x180013f61  lea     r9, [rsp+58h+Ptr]
0x180013f66  mov     r8, rbp
0x180013f69  mov     rdx, r14
0x180013f6c  lea     rcx, [rsp+58h+arg_10]
0x180013f71  mov     rax, [r14]
0x180013f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f79  mov     ebx, eax
0x180013f7b  test    eax, eax
0x180013f7d  js      short loc_180013F14
0x180013f7f  test    byte ptr [rsp+58h+arg_10], 4
0x180013f84  jnz     short loc_180013FDD
0x180013f86  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180013f8d  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180013f94  mov     rax, [rax+38h]
0x180013f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f9d  mov     rsi, rax
0x180013fa0  mov     rcx, rax; SRWLock
0x180013fa3  call    cs:__imp_AcquireSRWLockExclusive
0x180013fa9  mov     rcx, [r14+18h]
0x180013fad  mov     rcx, [rcx]; Ptr
0x180013fb0  test    rcx, rcx
0x180013fb3  jnz     short loc_180013FF7
0x180013fb5  mov     rbx, r12
0x180013fb8  mov     rcx, [rsp+58h+Ptr]; Ptr
0x180013fbd  call    cs:__imp_EncodePointer
0x180013fc3  mov     rcx, [r14+18h]
0x180013fc7  mov     [rcx], rax
0x180013fca  test    rsi, rsi
0x180013fcd  jz      short loc_180013FD8
0x180013fcf  mov     rcx, rsi; SRWLock
0x180013fd2  call    cs:__imp_ReleaseSRWLockExclusive
0x180013fd8  test    rbx, rbx
0x180013fdb  jnz     short loc_180014028
0x180013fdd  mov     rbx, [rsp+58h+Ptr]
0x180013fe2  mov     [r15], rbx
0x180013fe5  mov     ebx, r12d
0x180013fe8  jmp     loc_180013F14
0x180013fed  mov     ebx, 80040111h
0x180013ff2  jmp     loc_180013F14
0x180013ff7  call    cs:__imp_DecodePointer
0x180013ffd  mov     rbx, rax
0x180014000  mov     rcx, [rax]
0x180014003  mov     rax, [rcx+8]
0x180014007  mov     rcx, rbx
0x18001400a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001400f  jmp     short loc_180013FCA
0x180014011  test    rsi, rsi
0x180014014  jz      loc_180013F61
0x18001401a  mov     rcx, rsi; SRWLock
0x18001401d  call    cs:__imp_ReleaseSRWLockShared
0x180014023  jmp     loc_180013F61
0x180014028  mov     rcx, [rsp+58h+Ptr]
0x18001402d  mov     rax, [rcx]
0x180014030  mov     rax, [rax+10h]
0x180014034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014039  mov     rcx, [rsp+58h+Ptr]
0x18001403e  mov     rax, [rcx]
0x180014041  mov     rax, [rax+10h]
0x180014045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001404a  jmp     short loc_180013FE2
```
