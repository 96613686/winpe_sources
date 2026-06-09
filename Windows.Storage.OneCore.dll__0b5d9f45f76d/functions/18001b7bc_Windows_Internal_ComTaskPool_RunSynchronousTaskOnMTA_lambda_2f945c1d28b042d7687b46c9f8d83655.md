# Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_2f945c1d28b042d7687b46c9f8d83655___

- ea: `0x18001b7bc`
- end: `0x18001b896`
- name: `Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_2f945c1d28b042d7687b46c9f8d83655___`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021060`

## callees

- `0x180013e10`
- `0x18001af90`
- `0x18001b7bc`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001b7ea`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001b7ea`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001b860`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001b860`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_2f945c1d28b042d7687b46c9f8d83655___(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  unsigned int v5; // ebx
  __int64 *v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rcx
  int v9; // ebx
  int v11; // [rsp+30h] [rbp-18h] BYREF
  __int64 v12; // [rsp+38h] [rbp-10h] BYREF
  int v13; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v14; // [rsp+68h] [rbp+20h] BYREF

  v13 = 0;
  v11 = 0;
  if ( CoGetApartmentType((APTTYPE *)&v13, (APTTYPEQUALIFIER *)&v11) < 0 || !v13 || v13 == 3 )
    v5 = 0;
  else
    v5 = 4;
  v14 = 0;
  v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_2f945c1d28b042d7687b46c9f8d83655____long____lambda_2f945c1d28b042d7687b46c9f8d83655___(
                    &v12,
                    &v14,
                    a3);
  v7 = *v6;
  *v6 = 0;
  v8 = v12;
  if ( v12 )
  {
    v12 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v8);
  }
  v9 = SHTaskPoolQueueTask(v5, 32, a2);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v9 >= 0 )
    return v14;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001b7bc  mov     rax, rsp
0x18001b7bf  mov     [rax+10h], rbx
0x18001b7c3  mov     [rax+18h], rsi
0x18001b7c7  mov     [rax+8], ecx
0x18001b7ca  push    rdi
0x18001b7cb  sub     rsp, 40h
0x18001b7cf  mov     rdi, r8
0x18001b7d2  mov     esi, edx
0x18001b7d4  mov     dword ptr [rax+8], 0
0x18001b7db  mov     dword ptr [rax-18h], 0
0x18001b7e2  lea     rdx, [rax-18h]; pAptQualifier
0x18001b7e6  lea     rcx, [rax+8]; pAptType
0x18001b7ea  call    cs:__imp_CoGetApartmentType
0x18001b7f0  test    eax, eax
0x18001b7f2  js      short loc_18001B808
0x18001b7f4  mov     eax, [rsp+48h+arg_0]
0x18001b7f8  test    eax, eax
0x18001b7fa  jz      short loc_18001B808
0x18001b7fc  cmp     eax, 3
0x18001b7ff  jz      short loc_18001B808
0x18001b801  mov     ebx, 4
0x18001b806  jmp     short loc_18001B80A
0x18001b808  xor     ebx, ebx
0x18001b80a  mov     [rsp+48h+arg_18], 0
0x18001b812  mov     r8, rdi
0x18001b815  lea     rdx, [rsp+48h+arg_18]
0x18001b81a  lea     rcx, [rsp+48h+var_10]
0x18001b81f  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_2f945c1d28b042d7687b46c9f8d83655____long____lambda_2f945c1d28b042d7687b46c9f8d83655___
0x18001b824  mov     rdi, [rax]
0x18001b827  mov     qword ptr [rax], 0
0x18001b82e  mov     rcx, [rsp+48h+var_10]
0x18001b833  test    rcx, rcx
0x18001b836  jz      short loc_18001B846
0x18001b838  mov     [rsp+48h+var_10], 0
0x18001b841  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001b846  mov     [rsp+48h+var_20], 0
0x18001b84f  mov     [rsp+48h+var_28], rdi
0x18001b854  xor     r9d, r9d
0x18001b857  mov     r8d, esi
0x18001b85a  lea     edx, [r9+20h]
0x18001b85e  mov     ecx, ebx
0x18001b860  call    cs:__imp_SHTaskPoolQueueTask
0x18001b866  mov     ebx, eax
0x18001b868  test    rdi, rdi
0x18001b86b  jz      short loc_18001B87D
0x18001b86d  mov     rdx, [rdi]
0x18001b870  mov     rcx, rdi
0x18001b873  mov     rax, [rdx+10h]
0x18001b877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b87c  nop
0x18001b87d  test    ebx, ebx
0x18001b87f  cmovns  ebx, [rsp+48h+arg_18]
0x18001b884  mov     eax, ebx
0x18001b886  mov     rbx, [rsp+48h+arg_8]
0x18001b88b  mov     rsi, [rsp+48h+arg_10]
0x18001b890  add     rsp, 40h
0x18001b894  pop     rdi
0x18001b895  retn
```
