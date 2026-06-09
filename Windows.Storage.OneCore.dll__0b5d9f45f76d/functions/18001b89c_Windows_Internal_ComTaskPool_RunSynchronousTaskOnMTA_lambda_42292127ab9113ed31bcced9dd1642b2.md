# Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_42292127ab9113ed31bcced9dd1642b2___

- ea: `0x18001b89c`
- end: `0x18001b976`
- name: `Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_42292127ab9113ed31bcced9dd1642b2___`
- size: `218`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800212c0`

## callees

- `0x180013e10`
- `0x18001b05c`
- `0x18001b89c`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001b8ca`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001b8ca`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001b940`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001b940`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_42292127ab9113ed31bcced9dd1642b2___(
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
  v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_42292127ab9113ed31bcced9dd1642b2____long____lambda_42292127ab9113ed31bcced9dd1642b2___(
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
0x18001b89c  mov     rax, rsp
0x18001b89f  mov     [rax+10h], rbx
0x18001b8a3  mov     [rax+18h], rsi
0x18001b8a7  mov     [rax+8], ecx
0x18001b8aa  push    rdi
0x18001b8ab  sub     rsp, 40h
0x18001b8af  mov     rdi, r8
0x18001b8b2  mov     esi, edx
0x18001b8b4  mov     dword ptr [rax+8], 0
0x18001b8bb  mov     dword ptr [rax-18h], 0
0x18001b8c2  lea     rdx, [rax-18h]; pAptQualifier
0x18001b8c6  lea     rcx, [rax+8]; pAptType
0x18001b8ca  call    cs:__imp_CoGetApartmentType
0x18001b8d0  test    eax, eax
0x18001b8d2  js      short loc_18001B8E8
0x18001b8d4  mov     eax, [rsp+48h+arg_0]
0x18001b8d8  test    eax, eax
0x18001b8da  jz      short loc_18001B8E8
0x18001b8dc  cmp     eax, 3
0x18001b8df  jz      short loc_18001B8E8
0x18001b8e1  mov     ebx, 4
0x18001b8e6  jmp     short loc_18001B8EA
0x18001b8e8  xor     ebx, ebx
0x18001b8ea  mov     [rsp+48h+arg_18], 0
0x18001b8f2  mov     r8, rdi
0x18001b8f5  lea     rdx, [rsp+48h+arg_18]
0x18001b8fa  lea     rcx, [rsp+48h+var_10]
0x18001b8ff  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_42292127ab9113ed31bcced9dd1642b2____long____lambda_42292127ab9113ed31bcced9dd1642b2___
0x18001b904  mov     rdi, [rax]
0x18001b907  mov     qword ptr [rax], 0
0x18001b90e  mov     rcx, [rsp+48h+var_10]
0x18001b913  test    rcx, rcx
0x18001b916  jz      short loc_18001B926
0x18001b918  mov     [rsp+48h+var_10], 0
0x18001b921  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001b926  mov     [rsp+48h+var_20], 0
0x18001b92f  mov     [rsp+48h+var_28], rdi
0x18001b934  xor     r9d, r9d
0x18001b937  mov     r8d, esi
0x18001b93a  lea     edx, [r9+20h]
0x18001b93e  mov     ecx, ebx
0x18001b940  call    cs:__imp_SHTaskPoolQueueTask
0x18001b946  mov     ebx, eax
0x18001b948  test    rdi, rdi
0x18001b94b  jz      short loc_18001B95D
0x18001b94d  mov     rdx, [rdi]
0x18001b950  mov     rcx, rdi
0x18001b953  mov     rax, [rdx+10h]
0x18001b957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b95c  nop
0x18001b95d  test    ebx, ebx
0x18001b95f  cmovns  ebx, [rsp+48h+arg_18]
0x18001b964  mov     eax, ebx
0x18001b966  mov     rbx, [rsp+48h+arg_8]
0x18001b96b  mov     rsi, [rsp+48h+arg_10]
0x18001b970  add     rsp, 40h
0x18001b974  pop     rdi
0x18001b975  retn
```
