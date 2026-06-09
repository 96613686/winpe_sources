# Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_6aece9f498c1836e6b49856eae513237___

- ea: `0x18001bc28`
- end: `0x18001bd0c`
- name: `Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_6aece9f498c1836e6b49856eae513237___`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021160`

## callees

- `0x180003100`
- `0x18001ad6c`
- `0x18001bc28`
- `0x18001c4f0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001bc54`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001bc54`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001bcd9`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001bcd9`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_6aece9f498c1836e6b49856eae513237___(
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
    v7 = Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_6aece9f498c1836e6b49856eae513237___::CResultTaskWrapper__lambda_6aece9f498c1836e6b49856eae513237_____lambda_6aece9f498c1836e6b49856eae513237___(
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
0x18001bc28  mov     rax, rsp
0x18001bc2b  mov     [rax+10h], rbx
0x18001bc2f  mov     [rax+8], ecx
0x18001bc32  push    rbp
0x18001bc33  push    rsi
0x18001bc34  push    rdi
0x18001bc35  sub     rsp, 40h
0x18001bc39  mov     rsi, r8
0x18001bc3c  mov     ebp, edx
0x18001bc3e  mov     dword ptr [rax+8], 0
0x18001bc45  mov     dword ptr [rax-28h], 0
0x18001bc4c  lea     rdx, [rax-28h]; pAptQualifier
0x18001bc50  lea     rcx, [rax+8]; pAptType
0x18001bc54  call    cs:__imp_CoGetApartmentType
0x18001bc5a  test    eax, eax
0x18001bc5c  js      short loc_18001BC72
0x18001bc5e  mov     eax, [rsp+58h+arg_0]
0x18001bc62  test    eax, eax
0x18001bc64  jz      short loc_18001BC72
0x18001bc66  cmp     eax, 3
0x18001bc69  jz      short loc_18001BC72
0x18001bc6b  mov     ebx, 4
0x18001bc70  jmp     short loc_18001BC74
0x18001bc72  xor     ebx, ebx
0x18001bc74  mov     [rsp+58h+arg_18], 0
0x18001bc7c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bc83  mov     ecx, 198h; unsigned __int64
0x18001bc88  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001bc8d  mov     [rsp+58h+var_20], rax
0x18001bc92  xor     edi, edi
0x18001bc94  test    rax, rax
0x18001bc97  jz      short loc_18001BCB5
0x18001bc99  mov     r8, rsi
0x18001bc9c  lea     rdx, [rsp+58h+arg_18]
0x18001bca1  mov     rcx, rax
0x18001bca4  call    Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_6aece9f498c1836e6b49856eae513237_____CResultTaskWrapper__lambda_6aece9f498c1836e6b49856eae513237_____lambda_6aece9f498c1836e6b49856eae513237___
0x18001bca9  mov     rdi, rax
0x18001bcac  mov     [rsp+58h+var_20], 0
0x18001bcb5  lea     rcx, [rsp+58h+var_20]
0x18001bcba  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_f63bbe083a301d83e9c6aa65442624a6________MakeAllocator_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_f63bbe083a301d83e9c6aa65442624a6_____
0x18001bcbf  mov     [rsp+58h+var_30], 0
0x18001bcc8  mov     [rsp+58h+var_38], rdi
0x18001bccd  xor     r9d, r9d
0x18001bcd0  mov     r8d, ebp
0x18001bcd3  lea     edx, [r9+20h]
0x18001bcd7  mov     ecx, ebx
0x18001bcd9  call    cs:__imp_SHTaskPoolQueueTask
0x18001bcdf  mov     ebx, eax
0x18001bce1  test    rdi, rdi
0x18001bce4  jz      short loc_18001BCF6
0x18001bce6  mov     rdx, [rdi]
0x18001bce9  mov     rcx, rdi
0x18001bcec  mov     rax, [rdx+10h]
0x18001bcf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcf5  nop
0x18001bcf6  test    ebx, ebx
0x18001bcf8  cmovns  ebx, [rsp+58h+arg_18]
0x18001bcfd  mov     eax, ebx
0x18001bcff  mov     rbx, [rsp+58h+arg_8]
0x18001bd04  add     rsp, 40h
0x18001bd08  pop     rdi
0x18001bd09  pop     rsi
0x18001bd0a  pop     rbp
0x18001bd0b  retn
```
