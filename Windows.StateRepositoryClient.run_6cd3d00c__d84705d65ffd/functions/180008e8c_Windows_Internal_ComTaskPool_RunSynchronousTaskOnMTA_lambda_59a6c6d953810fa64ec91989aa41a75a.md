# Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_59a6c6d953810fa64ec91989aa41a75a___

- ea: `0x180008e8c`
- end: `0x180008f55`
- name: `Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_59a6c6d953810fa64ec91989aa41a75a___`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d090`

## callees

- `0x180008df8`
- `0x180008e8c`
- `0x18000bbb0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180008eb5`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180008eb5`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180008f28`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180008f28`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_59a6c6d953810fa64ec91989aa41a75a___(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  unsigned int v4; // ebx
  __int64 *v5; // rax
  __int64 v6; // rdi
  int v7; // ebx
  _QWORD v9[5]; // [rsp+30h] [rbp-28h] BYREF
  int v10; // [rsp+60h] [rbp+8h] BYREF
  __int64 v11; // [rsp+70h] [rbp+18h] BYREF
  int v12; // [rsp+78h] [rbp+20h] BYREF

  v11 = a3;
  v10 = 0;
  v12 = 0;
  if ( CoGetApartmentType((APTTYPE *)&v10, (APTTYPEQUALIFIER *)&v12) < 0 || !v10 || v10 == 3 )
    v4 = 0;
  else
    v4 = 4;
  LODWORD(v11) = 0;
  v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_59a6c6d953810fa64ec91989aa41a75a____long____lambda_59a6c6d953810fa64ec91989aa41a75a___(
                    v9,
                    &v11);
  v6 = *v5;
  *v5 = 0;
  if ( v9[0] )
  {
    v9[0] = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  v7 = SHTaskPoolQueueTask(v4, 32, a2);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v7 >= 0 )
    return (unsigned int)v11;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008e8c  mov     rax, rsp
0x180008e8f  mov     [rax+18h], r8
0x180008e93  mov     [rax+8], ecx
0x180008e96  push    rbx
0x180008e97  push    rsi
0x180008e98  push    rdi
0x180008e99  sub     rsp, 40h
0x180008e9d  mov     esi, edx
0x180008e9f  mov     dword ptr [rax+8], 0
0x180008ea6  lea     rdx, [rax+20h]; pAptQualifier
0x180008eaa  mov     dword ptr [rax+20h], 0
0x180008eb1  lea     rcx, [rax+8]; pAptType
0x180008eb5  call    cs:__imp_CoGetApartmentType
0x180008ebb  test    eax, eax
0x180008ebd  js      short loc_180008ED3
0x180008ebf  mov     eax, [rsp+58h+arg_0]
0x180008ec3  test    eax, eax
0x180008ec5  jz      short loc_180008ED3
0x180008ec7  cmp     eax, 3
0x180008eca  jz      short loc_180008ED3
0x180008ecc  mov     ebx, 4
0x180008ed1  jmp     short loc_180008ED5
0x180008ed3  xor     ebx, ebx
0x180008ed5  lea     rdx, [rsp+58h+arg_10]
0x180008eda  mov     dword ptr [rsp+58h+arg_10], 0
0x180008ee2  lea     rcx, [rsp+58h+var_28]
0x180008ee7  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_59a6c6d953810fa64ec91989aa41a75a____long____lambda_59a6c6d953810fa64ec91989aa41a75a___
0x180008eec  mov     rdi, [rax]
0x180008eef  mov     qword ptr [rax], 0
0x180008ef6  mov     rcx, [rsp+58h+var_28]
0x180008efb  test    rcx, rcx
0x180008efe  jz      short loc_180008F0E
0x180008f00  mov     [rsp+58h+var_28], 0
0x180008f09  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180008f0e  xor     r9d, r9d
0x180008f11  mov     [rsp+58h+var_30], 0
0x180008f1a  mov     r8d, esi
0x180008f1d  mov     [rsp+58h+var_38], rdi
0x180008f22  mov     ecx, ebx
0x180008f24  lea     edx, [r9+20h]
0x180008f28  call    cs:__imp_SHTaskPoolQueueTask
0x180008f2e  mov     ebx, eax
0x180008f30  test    rdi, rdi
0x180008f33  jz      short loc_180008F44
0x180008f35  mov     rdx, [rdi]
0x180008f38  mov     rcx, rdi
0x180008f3b  mov     rax, [rdx+10h]
0x180008f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f44  test    ebx, ebx
0x180008f46  cmovns  ebx, dword ptr [rsp+58h+arg_10]
0x180008f4b  mov     eax, ebx
0x180008f4d  add     rsp, 40h
0x180008f51  pop     rdi
0x180008f52  pop     rsi
0x180008f53  pop     rbx
0x180008f54  retn
```
