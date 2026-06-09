# Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_5b2cb0125494a185df564e0f90df558f___

- ea: `0x18001b97c`
- end: `0x18001ba60`
- name: `Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_5b2cb0125494a185df564e0f90df558f___`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800213c0`

## callees

- `0x180003100`
- `0x18001acc4`
- `0x18001b97c`
- `0x18001c4f0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001b9a8`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001b9a8`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001ba2d`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001ba2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_5b2cb0125494a185df564e0f90df558f___(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  unsigned int v5; // ebx
  void *v6; // rax
  __int64 v7; // rdi
  int v8; // ebx
  int v10; // [rsp+30h] [rbp-28h] BYREF
  void *v11; // [rsp+38h] [rbp-20h] BYREF
  int v12; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v13; // [rsp+78h] [rbp+20h] BYREF

  v12 = 0;
  v10 = 0;
  if ( CoGetApartmentType((APTTYPE *)&v12, (APTTYPEQUALIFIER *)&v10) < 0 || !v12 || v12 == 3 )
    v5 = 0;
  else
    v5 = 4;
  v13 = 0;
  v6 = operator new(0x198u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v6;
  v7 = 0;
  if ( v6 )
  {
    v7 = Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_5b2cb0125494a185df564e0f90df558f___::CResultTaskWrapper__lambda_5b2cb0125494a185df564e0f90df558f_____lambda_5b2cb0125494a185df564e0f90df558f___(
           v6,
           &v13,
           a3);
    v11 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_f63bbe083a301d83e9c6aa65442624a6_____::_MakeAllocator_Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_f63bbe083a301d83e9c6aa65442624a6_____(&v11);
  v8 = SHTaskPoolQueueTask(v5, 32, a2);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v8 >= 0 )
    return v13;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001b97c  mov     rax, rsp
0x18001b97f  mov     [rax+10h], rbx
0x18001b983  mov     [rax+8], ecx
0x18001b986  push    rbp
0x18001b987  push    rsi
0x18001b988  push    rdi
0x18001b989  sub     rsp, 40h
0x18001b98d  mov     rsi, r8
0x18001b990  mov     ebp, edx
0x18001b992  mov     dword ptr [rax+8], 0
0x18001b999  mov     dword ptr [rax-28h], 0
0x18001b9a0  lea     rdx, [rax-28h]; pAptQualifier
0x18001b9a4  lea     rcx, [rax+8]; pAptType
0x18001b9a8  call    cs:__imp_CoGetApartmentType
0x18001b9ae  test    eax, eax
0x18001b9b0  js      short loc_18001B9C6
0x18001b9b2  mov     eax, [rsp+58h+arg_0]
0x18001b9b6  test    eax, eax
0x18001b9b8  jz      short loc_18001B9C6
0x18001b9ba  cmp     eax, 3
0x18001b9bd  jz      short loc_18001B9C6
0x18001b9bf  mov     ebx, 4
0x18001b9c4  jmp     short loc_18001B9C8
0x18001b9c6  xor     ebx, ebx
0x18001b9c8  mov     [rsp+58h+arg_18], 0
0x18001b9d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b9d7  mov     ecx, 198h; unsigned __int64
0x18001b9dc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001b9e1  mov     [rsp+58h+var_20], rax
0x18001b9e6  xor     edi, edi
0x18001b9e8  test    rax, rax
0x18001b9eb  jz      short loc_18001BA09
0x18001b9ed  mov     r8, rsi
0x18001b9f0  lea     rdx, [rsp+58h+arg_18]
0x18001b9f5  mov     rcx, rax
0x18001b9f8  call    Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_5b2cb0125494a185df564e0f90df558f_____CResultTaskWrapper__lambda_5b2cb0125494a185df564e0f90df558f_____lambda_5b2cb0125494a185df564e0f90df558f___
0x18001b9fd  mov     rdi, rax
0x18001ba00  mov     [rsp+58h+var_20], 0
0x18001ba09  lea     rcx, [rsp+58h+var_20]
0x18001ba0e  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_f63bbe083a301d83e9c6aa65442624a6________MakeAllocator_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_f63bbe083a301d83e9c6aa65442624a6_____
0x18001ba13  mov     [rsp+58h+var_30], 0
0x18001ba1c  mov     [rsp+58h+var_38], rdi
0x18001ba21  xor     r9d, r9d
0x18001ba24  mov     r8d, ebp
0x18001ba27  lea     edx, [r9+20h]
0x18001ba2b  mov     ecx, ebx
0x18001ba2d  call    cs:__imp_SHTaskPoolQueueTask
0x18001ba33  mov     ebx, eax
0x18001ba35  test    rdi, rdi
0x18001ba38  jz      short loc_18001BA4A
0x18001ba3a  mov     rdx, [rdi]
0x18001ba3d  mov     rcx, rdi
0x18001ba40  mov     rax, [rdx+10h]
0x18001ba44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba49  nop
0x18001ba4a  test    ebx, ebx
0x18001ba4c  cmovns  ebx, [rsp+58h+arg_18]
0x18001ba51  mov     eax, ebx
0x18001ba53  mov     rbx, [rsp+58h+arg_8]
0x18001ba58  add     rsp, 40h
0x18001ba5c  pop     rdi
0x18001ba5d  pop     rsi
0x18001ba5e  pop     rbp
0x18001ba5f  retn
```
