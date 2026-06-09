# DllCanUnloadNow

- ea: `0x180017010`
- end: `0x180017169`
- name: `DllCanUnloadNow`
- size: `345`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180017010`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017107`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017107`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001712b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001715d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001712b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001715d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180017134`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180017134`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180017031`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180017031`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1800170e4`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1800170e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT v0; // esi
  unsigned __int64 v1; // rbx
  unsigned __int64 v2; // r14
  bool v3; // al
  RTL_SRWLOCK *v5; // rdi
  void **v6; // rax
  void *v7; // rbp
  PVOID v8; // rax

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  v0 = 1;
  byte_180072D28 = 1;
  v1 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                            + 32))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
     + 8;
  v2 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                            + 48))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  while ( v1 < v2 )
  {
    if ( *(_QWORD *)v1 )
    {
      if ( (*(unsigned int (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                     + 24))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_) )
      {
        v3 = 0;
        goto LABEL_6;
      }
      if ( **(_QWORD **)(*(_QWORD *)v1 + 24LL) )
      {
        v5 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                 + 56))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
        AcquireSRWLockExclusive(v5);
        v6 = *(void ***)(*(_QWORD *)v1 + 24LL);
        v7 = *v6;
        if ( *v6 )
        {
          *v6 = 0;
          if ( v5 )
            ReleaseSRWLockExclusive(v5);
          v8 = DecodePointer(v7);
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)v8 + 16LL))(v8);
        }
        else if ( v5 )
        {
          ReleaseSRWLockExclusive(v5);
        }
      }
    }
    v1 += 8LL;
  }
  v3 = (*(unsigned int (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                 + 24))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_) == 0;
LABEL_6:
  if ( v3 )
    return NdrDllCanUnloadNow(&gPFactory);
  return v0;
}

```

## disassembly

```asm
0x180017010  push    rbx
0x180017012  push    rbp
0x180017013  push    rsi
0x180017014  push    rdi
0x180017015  push    r14
0x180017017  push    r15
0x180017019  sub     rsp, 28h
0x18001701d  xor     r9d, r9d; Context
0x180017020  xor     r8d, r8d; Parameter
0x180017023  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001702a  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180017031  call    cs:__imp_InitOnceExecuteOnce
0x180017037  mov     esi, 1
0x18001703c  mov     cs:byte_180072D28, sil
0x180017043  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18001704a  lea     r15, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180017051  mov     rcx, r15
0x180017054  mov     rax, [rax+20h]
0x180017058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001705d  lea     rbx, [rax+8]
0x180017061  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180017068  mov     rax, [rcx+30h]
0x18001706c  mov     rcx, r15
0x18001706f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017074  mov     r14, rax
0x180017077  cmp     rbx, r14
0x18001707a  jnb     short loc_1800170C3
0x18001707c  cmp     qword ptr [rbx], 0
0x180017080  jz      short loc_1800170BD
0x180017082  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180017089  mov     rax, [rcx+18h]
0x18001708d  mov     rcx, r15
0x180017090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017095  test    eax, eax
0x180017097  jz      short loc_1800170AE
0x180017099  xor     al, al
0x18001709b  test    al, al
0x18001709d  jnz     short loc_1800170DD
0x18001709f  mov     eax, esi
0x1800170a1  add     rsp, 28h
0x1800170a5  pop     r15
0x1800170a7  pop     r14
0x1800170a9  pop     rdi
0x1800170aa  pop     rsi
0x1800170ab  pop     rbp
0x1800170ac  pop     rbx
0x1800170ad  retn
0x1800170ae  mov     rax, [rbx]
0x1800170b1  mov     rcx, [rax+18h]
0x1800170b5  mov     rax, [rcx]
0x1800170b8  test    rax, rax
0x1800170bb  jnz     short loc_1800170EE
0x1800170bd  add     rbx, 8
0x1800170c1  jmp     short loc_180017077
0x1800170c3  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800170ca  mov     rcx, r15
0x1800170cd  mov     rax, [rax+18h]
0x1800170d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170d6  test    eax, eax
0x1800170d8  setz    al
0x1800170db  jmp     short loc_18001709B
0x1800170dd  lea     rcx, gPFactory; pPSFactoryBuffer
0x1800170e4  call    cs:__imp_NdrDllCanUnloadNow
0x1800170ea  mov     esi, eax
0x1800170ec  jmp     short loc_18001709F
0x1800170ee  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800170f5  mov     rcx, r15
0x1800170f8  mov     rax, [rax+38h]
0x1800170fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017101  mov     rdi, rax
0x180017104  mov     rcx, rax; SRWLock
0x180017107  call    cs:__imp_AcquireSRWLockExclusive
0x18001710d  mov     rcx, [rbx]
0x180017110  mov     rax, [rcx+18h]
0x180017114  mov     rbp, [rax]
0x180017117  test    rbp, rbp
0x18001711a  jz      short loc_180017151
0x18001711c  mov     qword ptr [rax], 0
0x180017123  test    rdi, rdi
0x180017126  jz      short loc_180017131
0x180017128  mov     rcx, rdi; SRWLock
0x18001712b  call    cs:__imp_ReleaseSRWLockExclusive
0x180017131  mov     rcx, rbp; Ptr
0x180017134  call    cs:__imp_DecodePointer
0x18001713a  mov     rdx, rax
0x18001713d  mov     rcx, [rax]
0x180017140  mov     rax, [rcx+10h]
0x180017144  mov     rcx, rdx
0x180017147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001714c  jmp     loc_1800170BD
0x180017151  test    rdi, rdi
0x180017154  jz      loc_1800170BD
0x18001715a  mov     rcx, rdi; SRWLock
0x18001715d  call    cs:__imp_ReleaseSRWLockExclusive
0x180017163  jmp     loc_1800170BD
```
