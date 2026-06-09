# DllGetClassObject

- ea: `0x180001230`
- end: `0x180001454`
- name: `DllGetClassObject`
- size: `548`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001230`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000125f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000125f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000141d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000141d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800013c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800013c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001354`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001378`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001354`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001378`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180001316`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180001316`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800013da`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800013da`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180001328`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180001400`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180001328`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180001400`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rax
  _QWORD *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rbx
  RTL_SRWLOCK *v11; // rdi
  void *v12; // rcx
  HRESULT v13; // esi
  RTL_SRWLOCK *v15; // rsi
  void *v16; // rcx
  PVOID v17; // rdi
  int v18; // [rsp+60h] [rbp+18h] BYREF
  PVOID Ptr; // [rsp+68h] [rbp+20h] BYREF

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18001C548 = 1;
  *ppv = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                            + 32))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
     + 8;
  v7 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                            + 40))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
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
            return v13;
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
          return 0;
        }
        return v13;
      }
    }
    v6 += 8LL;
  }
  return -2147221231;
}

```

## disassembly

```asm
0x180001230  mov     [rsp+arg_0], rbx
0x180001235  mov     [rsp+arg_8], rbp
0x18000123a  push    rsi
0x18000123b  push    rdi
0x18000123c  push    r14
0x18000123e  sub     rsp, 30h
0x180001242  mov     r14, r8
0x180001245  mov     rsi, rdx
0x180001248  mov     rdi, rcx
0x18000124b  xor     r9d, r9d; Context
0x18000124e  xor     r8d, r8d; Parameter
0x180001251  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180001258  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000125f  call    cs:__imp_InitOnceExecuteOnce
0x180001265  mov     cs:byte_18001C548, 1
0x18000126c  xor     ebp, ebp
0x18000126e  mov     [r14], rbp
0x180001271  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180001278  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000127f  mov     rax, [rax+20h]
0x180001283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001288  lea     rbx, [rax+8]
0x18000128c  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180001293  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000129a  mov     rax, [rax+28h]
0x18000129e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012a3  cmp     rbx, rax
0x1800012a6  jnb     loc_180001425
0x1800012ac  mov     rcx, [rbx]
0x1800012af  test    rcx, rcx
0x1800012b2  jz      short loc_1800012CD
0x1800012b4  mov     rdx, [rcx+8]
0x1800012b8  mov     rcx, [rdx]
0x1800012bb  sub     rcx, [rdi]
0x1800012be  jnz     short loc_1800012C8
0x1800012c0  mov     rcx, [rdx+8]
0x1800012c4  sub     rcx, [rdi+8]
0x1800012c8  test    rcx, rcx
0x1800012cb  jz      short loc_1800012D3
0x1800012cd  add     rbx, 8
0x1800012d1  jmp     short loc_1800012A3
0x1800012d3  lfence
0x1800012d6  mov     [rsp+48h+arg_10], 1
0x1800012de  mov     rbx, [rbx]
0x1800012e1  mov     [r14], rbp
0x1800012e4  mov     [rsp+48h+Ptr], rbp
0x1800012e9  mov     rax, [rbx+18h]
0x1800012ed  mov     rcx, [rax]
0x1800012f0  test    rcx, rcx
0x1800012f3  jz      loc_18000137E
0x1800012f9  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180001300  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180001307  mov     rax, [rax+38h]
0x18000130b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001310  mov     rdi, rax
0x180001313  mov     rcx, rax; SRWLock
0x180001316  call    cs:__imp_AcquireSRWLockShared
0x18000131c  mov     rcx, [rbx+18h]
0x180001320  mov     rcx, [rcx]; Ptr
0x180001323  test    rcx, rcx
0x180001326  jz      short loc_180001370
0x180001328  call    cs:__imp_DecodePointer
0x18000132e  mov     r9, rax
0x180001331  mov     [rsp+48h+Ptr], rax
0x180001336  mov     rcx, [rax]
0x180001339  mov     rax, [rcx]
0x18000133c  mov     r8, r14
0x18000133f  mov     rdx, rsi
0x180001342  mov     rcx, r9
0x180001345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000134a  mov     esi, eax
0x18000134c  test    rdi, rdi
0x18000134f  jz      short loc_18000135B
0x180001351  mov     rcx, rdi; SRWLock
0x180001354  call    cs:__imp_ReleaseSRWLockShared
0x18000135a  nop
0x18000135b  mov     eax, esi
0x18000135d  mov     rbx, [rsp+48h+arg_0]
0x180001362  mov     rbp, [rsp+48h+arg_8]
0x180001367  add     rsp, 30h
0x18000136b  pop     r14
0x18000136d  pop     rdi
0x18000136e  pop     rsi
0x18000136f  retn
0x180001370  test    rdi, rdi
0x180001373  jz      short loc_18000137E
0x180001375  mov     rcx, rdi; SRWLock
0x180001378  call    cs:__imp_ReleaseSRWLockShared
0x18000137e  lea     r9, [rsp+48h+Ptr]
0x180001383  mov     r8, rsi
0x180001386  mov     rdx, rbx
0x180001389  lea     rcx, [rsp+48h+arg_10]
0x18000138e  mov     rax, [rbx]
0x180001391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001396  mov     esi, eax
0x180001398  test    eax, eax
0x18000139a  js      short loc_18000135B
0x18000139c  test    byte ptr [rsp+48h+arg_10], 4
0x1800013a1  jnz     short loc_1800013F1
0x1800013a3  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800013aa  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800013b1  mov     rax, [rax+38h]
0x1800013b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013ba  mov     rsi, rax
0x1800013bd  mov     rcx, rax; SRWLock
0x1800013c0  call    cs:__imp_AcquireSRWLockExclusive
0x1800013c6  mov     rcx, [rbx+18h]
0x1800013ca  mov     rcx, [rcx]; Ptr
0x1800013cd  test    rcx, rcx
0x1800013d0  jnz     short loc_180001400
0x1800013d2  mov     rdi, rbp
0x1800013d5  mov     rcx, [rsp+48h+Ptr]; Ptr
0x1800013da  call    cs:__imp_EncodePointer
0x1800013e0  mov     rcx, [rbx+18h]
0x1800013e4  mov     [rcx], rax
0x1800013e7  test    rsi, rsi
0x1800013ea  jnz     short loc_18000141A
0x1800013ec  test    rdi, rdi
0x1800013ef  jnz     short loc_18000142F
0x1800013f1  mov     rdi, [rsp+48h+Ptr]
0x1800013f6  mov     [r14], rdi
0x1800013f9  mov     esi, ebp
0x1800013fb  jmp     loc_18000135B
0x180001400  call    cs:__imp_DecodePointer
0x180001406  mov     rdi, rax
0x180001409  mov     rcx, [rax]
0x18000140c  mov     rax, [rcx+8]
0x180001410  mov     rcx, rdi
0x180001413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001418  jmp     short loc_1800013E7
0x18000141a  mov     rcx, rsi; SRWLock
0x18000141d  call    cs:__imp_ReleaseSRWLockExclusive
0x180001423  jmp     short loc_1800013EC
0x180001425  mov     eax, 80040111h
0x18000142a  jmp     loc_18000135D
0x18000142f  mov     rcx, [rsp+48h+Ptr]
0x180001434  mov     rax, [rcx]
0x180001437  mov     rax, [rax+10h]
0x18000143b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001440  mov     rcx, [rsp+48h+Ptr]
0x180001445  mov     rax, [rcx]
0x180001448  mov     rax, [rax+10h]
0x18000144c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001451  jmp     short loc_1800013F6
```
