# DllCanUnloadNow

- ea: `0x180004f10`
- end: `0x18000507a`
- name: `DllCanUnloadNow`
- size: `362`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004f10`
- `0x180038010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180004ff0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004f2d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004f2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004fff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000506a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004fff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000506a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005050`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005050`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005016`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005016`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllCanUnloadNow()
{
  unsigned __int64 v0; // rbx
  unsigned __int64 v1; // rdi
  bool v2; // al
  PVOID v4; // rax
  RTL_SRWLOCK *v5; // rsi
  void **v6; // rax
  void *v7; // rbp

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18004E9C8 = 1;
  v0 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                            + 32))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
     + 8;
  v1 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                            + 48))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  while ( 1 )
  {
    if ( v0 >= v1 )
    {
      v2 = (*(unsigned int (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                     + 24))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_) == 0;
      goto LABEL_8;
    }
    if ( *(_QWORD *)v0 )
      break;
LABEL_6:
    v0 += 8LL;
  }
  if ( !(*(unsigned int (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                  + 24))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_) )
  {
    if ( **(_QWORD **)(*(_QWORD *)v0 + 24LL) )
    {
      v5 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                               + 56))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
      AcquireSRWLockExclusive(v5);
      v6 = *(void ***)(*(_QWORD *)v0 + 24LL);
      v7 = *v6;
      if ( *v6 )
      {
        *v6 = 0;
        if ( v5 )
          ReleaseSRWLockExclusive(v5);
        v4 = DecodePointer(v7);
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)v4 + 16LL))(v4);
      }
      else if ( v5 )
      {
        ReleaseSRWLockExclusive(v5);
      }
    }
    goto LABEL_6;
  }
  v2 = 0;
LABEL_8:
  if ( v2 )
    return NdrDllCanUnloadNow(&gPFactory);
  else
    return 1;
}

```

## disassembly

```asm
0x180004f10  push    rbx
0x180004f12  push    rbp
0x180004f13  push    rsi
0x180004f14  push    rdi
0x180004f15  sub     rsp, 28h
0x180004f19  xor     r9d, r9d; Context
0x180004f1c  xor     r8d, r8d; Parameter
0x180004f1f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180004f26  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180004f2d  call    cs:__imp_InitOnceExecuteOnce
0x180004f33  mov     cs:byte_18004E9C8, 1
0x180004f3a  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180004f41  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180004f48  mov     rax, [rax+20h]
0x180004f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f51  lea     rbx, [rax+8]
0x180004f55  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180004f5c  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180004f63  mov     rax, [rax+30h]
0x180004f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f6c  mov     rdi, rax
0x180004f6f  nop
0x180004f70  cmp     rbx, rdi
0x180004f73  jnb     short loc_180004FB3
0x180004f75  cmp     qword ptr [rbx], 0
0x180004f79  jz      short loc_180004FAD
0x180004f7b  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180004f82  mov     rax, [rcx+18h]
0x180004f86  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180004f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f92  test    eax, eax
0x180004f94  jnz     loc_180005072
0x180004f9a  mov     rax, [rbx]
0x180004f9d  mov     rcx, [rax+18h]
0x180004fa1  mov     rax, [rcx]
0x180004fa4  test    rax, rax
0x180004fa7  jnz     loc_180005033
0x180004fad  add     rbx, 8
0x180004fb1  jmp     short loc_180004F70
0x180004fb3  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180004fba  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180004fc1  mov     rax, [rax+18h]
0x180004fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fca  test    eax, eax
0x180004fcc  setz    al
0x180004fcf  test    al, al
0x180004fd1  jnz     short loc_180004FE1
0x180004fd3  mov     eax, 1
0x180004fd8  add     rsp, 28h
0x180004fdc  pop     rdi
0x180004fdd  pop     rsi
0x180004fde  pop     rbp
0x180004fdf  pop     rbx
0x180004fe0  retn
0x180004fe1  lea     rcx, gPFactory
0x180004fe8  add     rsp, 28h
0x180004fec  pop     rdi
0x180004fed  pop     rsi
0x180004fee  pop     rbp
0x180004fef  pop     rbx
0x180004ff0  jmp     cs:__imp_NdrDllCanUnloadNow
0x180004ff7  test    rsi, rsi
0x180004ffa  jz      short loc_180004FAD
0x180004ffc  mov     rcx, rsi; SRWLock
0x180004fff  call    cs:__imp_ReleaseSRWLockExclusive
0x180005005  jmp     short loc_180004FAD
0x180005007  mov     qword ptr [rax], 0
0x18000500e  test    rsi, rsi
0x180005011  jnz     short loc_180005067
0x180005013  mov     rcx, rbp; Ptr
0x180005016  call    cs:__imp_DecodePointer
0x18000501c  mov     rdx, rax
0x18000501f  mov     rcx, [rax]
0x180005022  mov     rax, [rcx+10h]
0x180005026  mov     rcx, rdx
0x180005029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000502e  jmp     loc_180004FAD
0x180005033  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000503a  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180005041  mov     rax, [rax+38h]
0x180005045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000504a  mov     rsi, rax
0x18000504d  mov     rcx, rax; SRWLock
0x180005050  call    cs:__imp_AcquireSRWLockExclusive
0x180005056  mov     rcx, [rbx]
0x180005059  mov     rax, [rcx+18h]
0x18000505d  mov     rbp, [rax]
0x180005060  test    rbp, rbp
0x180005063  jnz     short loc_180005007
0x180005065  jmp     short loc_180004FF7
0x180005067  mov     rcx, rsi; SRWLock
0x18000506a  call    cs:__imp_ReleaseSRWLockExclusive
0x180005070  jmp     short loc_180005013
0x180005072  xor     al, al
0x180005074  jmp     loc_180004FCF
```
