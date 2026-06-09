# Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_7c7248d2766b066219d9c24e5b842382___

- ea: `0x18001bdf4`
- end: `0x18001bece`
- name: `Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_7c7248d2766b066219d9c24e5b842382___`
- size: `218`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021710`

## callees

- `0x180013e10`
- `0x18001b394`
- `0x18001bdf4`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001be22`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001be22`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001be98`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001be98`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_7c7248d2766b066219d9c24e5b842382___(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  unsigned int v5; // ebx
  __int64 *v6; // rax
  __int64 v7; // rdi
  int v8; // ebx
  int v10; // [rsp+30h] [rbp-18h] BYREF
  __int64 v11; // [rsp+38h] [rbp-10h] BYREF
  int v12; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v13; // [rsp+68h] [rbp+20h] BYREF

  v12 = 0;
  v10 = 0;
  if ( CoGetApartmentType((APTTYPE *)&v12, (APTTYPEQUALIFIER *)&v10) < 0 || !v12 || v12 == 3 )
    v5 = 0;
  else
    v5 = 4;
  v13 = 0;
  v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_7c7248d2766b066219d9c24e5b842382____long____lambda_7c7248d2766b066219d9c24e5b842382___(
                    &v11,
                    &v13,
                    a3);
  v7 = *v6;
  *v6 = 0;
  if ( v11 )
  {
    v11 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
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
0x18001bdf4  mov     rax, rsp
0x18001bdf7  mov     [rax+10h], rbx
0x18001bdfb  mov     [rax+18h], rsi
0x18001bdff  mov     [rax+8], ecx
0x18001be02  push    rdi
0x18001be03  sub     rsp, 40h
0x18001be07  mov     rdi, r8
0x18001be0a  mov     esi, edx
0x18001be0c  mov     dword ptr [rax+8], 0
0x18001be13  mov     dword ptr [rax-18h], 0
0x18001be1a  lea     rdx, [rax-18h]; pAptQualifier
0x18001be1e  lea     rcx, [rax+8]; pAptType
0x18001be22  call    cs:__imp_CoGetApartmentType
0x18001be28  test    eax, eax
0x18001be2a  js      short loc_18001BE40
0x18001be2c  mov     eax, [rsp+48h+arg_0]
0x18001be30  test    eax, eax
0x18001be32  jz      short loc_18001BE40
0x18001be34  cmp     eax, 3
0x18001be37  jz      short loc_18001BE40
0x18001be39  mov     ebx, 4
0x18001be3e  jmp     short loc_18001BE42
0x18001be40  xor     ebx, ebx
0x18001be42  mov     [rsp+48h+arg_18], 0
0x18001be4a  mov     r8, rdi
0x18001be4d  lea     rdx, [rsp+48h+arg_18]
0x18001be52  lea     rcx, [rsp+48h+var_10]
0x18001be57  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_7c7248d2766b066219d9c24e5b842382____long____lambda_7c7248d2766b066219d9c24e5b842382___
0x18001be5c  mov     rdi, [rax]
0x18001be5f  mov     qword ptr [rax], 0
0x18001be66  mov     rcx, [rsp+48h+var_10]
0x18001be6b  test    rcx, rcx
0x18001be6e  jz      short loc_18001BE7E
0x18001be70  mov     [rsp+48h+var_10], 0
0x18001be79  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001be7e  mov     [rsp+48h+var_20], 0
0x18001be87  mov     [rsp+48h+var_28], rdi
0x18001be8c  xor     r9d, r9d
0x18001be8f  mov     r8d, esi
0x18001be92  lea     edx, [r9+20h]
0x18001be96  mov     ecx, ebx
0x18001be98  call    cs:__imp_SHTaskPoolQueueTask
0x18001be9e  mov     ebx, eax
0x18001bea0  test    rdi, rdi
0x18001bea3  jz      short loc_18001BEB5
0x18001bea5  mov     rdx, [rdi]
0x18001bea8  mov     rcx, rdi
0x18001beab  mov     rax, [rdx+10h]
0x18001beaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001beb4  nop
0x18001beb5  test    ebx, ebx
0x18001beb7  cmovns  ebx, [rsp+48h+arg_18]
0x18001bebc  mov     eax, ebx
0x18001bebe  mov     rbx, [rsp+48h+arg_8]
0x18001bec3  mov     rsi, [rsp+48h+arg_10]
0x18001bec8  add     rsp, 40h
0x18001becc  pop     rdi
0x18001becd  retn
```
