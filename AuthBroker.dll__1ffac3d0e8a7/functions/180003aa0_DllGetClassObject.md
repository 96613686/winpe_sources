# DllGetClassObject

- ea: `0x180003aa0`
- end: `0x180003cfc`
- name: `DllGetClassObject`
- size: `604`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003aa0`
- `0x180021010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180003cea`
- `RPCRT4!NdrDllGetClassObject` at `0x180003cea`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180003ac9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180003ac9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003c2d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003c2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003c76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003c76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003bca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003bdd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003bca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003bdd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003b88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003b88`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003b9a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003c56`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003b9a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003c56`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180003c47`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180003c47`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rax
  _QWORD *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdi
  _RTL_SRWLOCK *v11; // r15
  void *v12; // rcx
  int v13; // ebx
  _RTL_SRWLOCK *v14; // r15
  void *v15; // rcx
  PVOID v16; // rbx
  int v18; // [rsp+70h] [rbp+18h] BYREF
  PVOID Ptr; // [rsp+78h] [rbp+20h] BYREF

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_.initialized_ = 1;
  *ppv = 0;
  v6 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> *))(*(_QWORD *)Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_.data_ + 32LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
     + 8;
  v7 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> *))(*(_QWORD *)Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_.data_ + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  while ( v6 < v7 )
  {
    if ( *(_QWORD *)v6 )
    {
      v8 = *(_QWORD **)(*(_QWORD *)v6 + 8LL);
      v9 = *v8 - *(_QWORD *)&rclsid->Data1;
      if ( *v8 == *(_QWORD *)&rclsid->Data1 )
        v9 = v8[1] - *(_QWORD *)rclsid->Data4;
      if ( !v9 )
      {
        _mm_lfence();
        v10 = *(_QWORD *)v6;
        v18 = 1;
        *ppv = 0;
        Ptr = 0;
        if ( **(_QWORD **)(v10 + 24) )
        {
          v11 = (_RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> *))(*(_QWORD *)Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_.data_ + 56LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
          AcquireSRWLockShared(v11);
          v12 = **(void ***)(v10 + 24);
          if ( v12 )
          {
            Ptr = DecodePointer(v12);
            v13 = (**(__int64 (__fastcall ***)(PVOID, const IID *const, LPVOID *))Ptr)(Ptr, riid, ppv);
            if ( v11 )
              ReleaseSRWLockShared(v11);
            goto LABEL_25;
          }
          if ( v11 )
            ReleaseSRWLockShared(v11);
        }
        v13 = (*(__int64 (__fastcall **)(int *, __int64, const IID *const, PVOID *))v10)(&v18, v10, riid, &Ptr);
        if ( v13 >= 0 )
        {
          if ( (v18 & 4) != 0 )
            goto LABEL_23;
          v14 = (_RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> *))(*(_QWORD *)Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_.data_ + 56LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
          AcquireSRWLockExclusive(v14);
          v15 = **(void ***)(v10 + 24);
          if ( v15 )
          {
            v16 = DecodePointer(v15);
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)v16 + 8LL))(v16);
          }
          else
          {
            v16 = 0;
            **(_QWORD **)(v10 + 24) = EncodePointer(Ptr);
          }
          if ( v14 )
            ReleaseSRWLockExclusive(v14);
          if ( !v16 )
          {
LABEL_23:
            v16 = Ptr;
          }
          else
          {
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
          }
          *ppv = v16;
          v13 = 0;
        }
LABEL_25:
        if ( v13 >= 0 )
          return 0;
        return NdrDllGetClassObject(
                 rclsid,
                 riid,
                 ppv,
                 (const ProxyFileInfo **)aProxyFileList,
                 &CLSID_PSFactoryBuffer,
                 &gPFactory);
      }
    }
    v6 += 8LL;
  }
  return NdrDllGetClassObject(
           rclsid,
           riid,
           ppv,
           (const ProxyFileInfo **)aProxyFileList,
           &CLSID_PSFactoryBuffer,
           &gPFactory);
}

```

## disassembly

```asm
0x180003aa0  push    rbx
0x180003aa2  push    rbp
0x180003aa3  push    rsi
0x180003aa4  push    r12
0x180003aa6  push    r14
0x180003aa8  sub     rsp, 30h
0x180003aac  mov     rsi, ppv
0x180003aaf  mov     r14, riid
0x180003ab2  mov     rbp, rclsid
0x180003ab5  lea     riid, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180003abc  xor     r8d, r8d; Parameter
0x180003abf  lea     rclsid, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180003ac6  xor     r9d, r9d; Context
0x180003ac9  call    cs:__imp_InitOnceExecuteOnce
0x180003acf  mov     cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A.initialized_, 1; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_ ...
0x180003ad6  lea     rclsid, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180003add  xor     r12d, r12d
0x180003ae0  mov     [rsi], r12
0x180003ae3  mov     rax, qword ptr cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A.data_; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_ ...
0x180003aea  mov     rax, [rax+20h]
0x180003aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003af3  lea     rclsid, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180003afa  lea     rbx, [rax+8]
0x180003afe  mov     rax, qword ptr cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A.data_; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_ ...
0x180003b05  mov     rax, [rax+28h]
0x180003b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b0e  cmp     rbx, rax
0x180003b11  jnb     loc_180003CC2
0x180003b17  mov     rclsid, [rbx]
0x180003b1a  test    rclsid, rclsid
0x180003b1d  jz      short loc_180003B39
0x180003b1f  mov     riid, [rclsid+8]
0x180003b23  mov     rclsid, [riid]
0x180003b26  sub     rclsid, [rbp+0]
0x180003b2a  jnz     short loc_180003B34
0x180003b2c  mov     rclsid, [riid+8]
0x180003b30  sub     rclsid, [rbp+8]
0x180003b34  test    rclsid, rclsid
0x180003b37  jz      short loc_180003B3F
0x180003b39  add     rbx, 8
0x180003b3d  jmp     short loc_180003B0E
0x180003b3f  mov     [rsp+58h+arg_0], rdi
0x180003b44  mov     [rsp+58h+arg_8], r15
0x180003b49  lfence
0x180003b4c  mov     rdi, [rbx]
0x180003b4f  mov     [rsp+58h+arg_10], 1
0x180003b57  mov     [rsi], r12
0x180003b5a  mov     [rsp+58h+Ptr], r12
0x180003b5f  mov     rax, [rdi+18h]
0x180003b63  mov     rclsid, [rax]
0x180003b66  test    rclsid, rclsid
0x180003b69  jz      short loc_180003BE3
0x180003b6b  mov     rax, qword ptr cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A.data_; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_ ...
0x180003b72  lea     rclsid, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180003b79  mov     rax, [rax+38h]
0x180003b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b82  mov     rclsid, rax; SRWLock
0x180003b85  mov     r15, rax
0x180003b88  call    cs:__imp_AcquireSRWLockShared
0x180003b8e  mov     rclsid, [rdi+18h]
0x180003b92  mov     rclsid, [rclsid]; Ptr
0x180003b95  test    rclsid, rclsid
0x180003b98  jz      short loc_180003BD5
0x180003b9a  call    cs:__imp_DecodePointer
0x180003ba0  mov     [rsp+58h+Ptr], rax
0x180003ba5  mov     ppv, rsi
0x180003ba8  mov     r9, rax
0x180003bab  mov     riid, r14
0x180003bae  mov     rclsid, [rax]
0x180003bb1  mov     rax, [rclsid]
0x180003bb4  mov     rclsid, r9
0x180003bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bbc  mov     ebx, eax
0x180003bbe  test    r15, r15
0x180003bc1  jz      loc_180003CB0
0x180003bc7  mov     rclsid, r15; SRWLock
0x180003bca  call    cs:__imp_ReleaseSRWLockShared
0x180003bd0  jmp     loc_180003CB0
0x180003bd5  test    r15, r15
0x180003bd8  jz      short loc_180003BE3
0x180003bda  mov     rclsid, r15; SRWLock
0x180003bdd  call    cs:__imp_ReleaseSRWLockShared
0x180003be3  mov     rax, [rdi]
0x180003be6  lea     r9, [rsp+58h+Ptr]
0x180003beb  mov     ppv, r14
0x180003bee  lea     rclsid, [rsp+58h+arg_10]
0x180003bf3  mov     riid, rdi
0x180003bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bfb  mov     ebx, eax
0x180003bfd  test    eax, eax
0x180003bff  js      loc_180003CB0
0x180003c05  test    byte ptr [rsp+58h+arg_10], 4
0x180003c0a  jnz     loc_180003CA5
0x180003c10  mov     rax, qword ptr cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A.data_; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_ ...
0x180003c17  lea     rclsid, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180003c1e  mov     rax, [rax+38h]
0x180003c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c27  mov     rclsid, rax; SRWLock
0x180003c2a  mov     r15, rax
0x180003c2d  call    cs:__imp_AcquireSRWLockExclusive
0x180003c33  mov     rclsid, [rdi+18h]
0x180003c37  mov     rclsid, [rclsid]; Ptr
0x180003c3a  test    rclsid, rclsid
0x180003c3d  jnz     short loc_180003C56
0x180003c3f  mov     rclsid, [rsp+58h+Ptr]; Ptr
0x180003c44  mov     rbx, r12
0x180003c47  call    cs:__imp_EncodePointer
0x180003c4d  mov     rclsid, [rdi+18h]
0x180003c51  mov     [rclsid], rax
0x180003c54  jmp     short loc_180003C6E
0x180003c56  call    cs:__imp_DecodePointer
0x180003c5c  mov     rbx, rax
0x180003c5f  mov     rclsid, [rax]
0x180003c62  mov     rax, [rclsid+8]
0x180003c66  mov     rclsid, rbx
0x180003c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c6e  test    r15, r15
0x180003c71  jz      short loc_180003C7C
0x180003c73  mov     rclsid, r15; SRWLock
0x180003c76  call    cs:__imp_ReleaseSRWLockExclusive
0x180003c7c  test    rbx, rbx
0x180003c7f  jz      short loc_180003CA5
0x180003c81  mov     rclsid, [rsp+58h+Ptr]
0x180003c86  mov     rax, [rclsid]
0x180003c89  mov     rax, [rax+10h]
0x180003c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c92  mov     rclsid, [rsp+58h+Ptr]
0x180003c97  mov     rax, [rclsid]
0x180003c9a  mov     rax, [rax+10h]
0x180003c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ca3  jmp     short loc_180003CAA
0x180003ca5  mov     rbx, [rsp+58h+Ptr]
0x180003caa  mov     [rsi], rbx
0x180003cad  mov     ebx, r12d
0x180003cb0  mov     r15, [rsp+58h+arg_8]
0x180003cb5  mov     rdi, [rsp+58h+arg_0]
0x180003cba  test    ebx, ebx
0x180003cbc  js      short loc_180003CC2
0x180003cbe  xor     eax, eax
0x180003cc0  jmp     short loc_180003CF0
0x180003cc2  lea     rax, gPFactory
0x180003cc9  mov     ppv, rsi; ppv
0x180003ccc  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180003cd1  lea     r9, aProxyFileList; pProxyFileList
0x180003cd8  lea     rax, CLSID_PSFactoryBuffer
0x180003cdf  mov     riid, r14; riid
0x180003ce2  mov     rclsid, rbp; rclsid
0x180003ce5  mov     [rsp+58h+pclsid], rax; pclsid
0x180003cea  call    cs:__imp_NdrDllGetClassObject
0x180003cf0  add     rsp, 30h
0x180003cf4  pop     r14
0x180003cf6  pop     r12
0x180003cf8  pop     rsi
0x180003cf9  pop     rbp
0x180003cfa  pop     rbx
0x180003cfb  retn
```
