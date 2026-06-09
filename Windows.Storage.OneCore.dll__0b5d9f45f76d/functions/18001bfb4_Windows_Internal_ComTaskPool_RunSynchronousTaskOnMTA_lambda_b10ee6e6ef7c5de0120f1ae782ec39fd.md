# Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_b10ee6e6ef7c5de0120f1ae782ec39fd___

- ea: `0x18001bfb4`
- end: `0x18001c08e`
- name: `Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_b10ee6e6ef7c5de0120f1ae782ec39fd___`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021500`

## callees

- `0x180013e10`
- `0x18001b54c`
- `0x18001bfb4`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001bfe2`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001bfe2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001c058`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001c058`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_b10ee6e6ef7c5de0120f1ae782ec39fd___(
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
  v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_b10ee6e6ef7c5de0120f1ae782ec39fd____long____lambda_b10ee6e6ef7c5de0120f1ae782ec39fd___(
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
0x18001bfb4  mov     rax, rsp
0x18001bfb7  mov     [rax+10h], rbx
0x18001bfbb  mov     [rax+18h], rsi
0x18001bfbf  mov     [rax+8], ecx
0x18001bfc2  push    rdi
0x18001bfc3  sub     rsp, 40h
0x18001bfc7  mov     rdi, r8
0x18001bfca  mov     esi, edx
0x18001bfcc  mov     dword ptr [rax+8], 0
0x18001bfd3  mov     dword ptr [rax-18h], 0
0x18001bfda  lea     rdx, [rax-18h]; pAptQualifier
0x18001bfde  lea     rcx, [rax+8]; pAptType
0x18001bfe2  call    cs:__imp_CoGetApartmentType
0x18001bfe8  test    eax, eax
0x18001bfea  js      short loc_18001C000
0x18001bfec  mov     eax, [rsp+48h+arg_0]
0x18001bff0  test    eax, eax
0x18001bff2  jz      short loc_18001C000
0x18001bff4  cmp     eax, 3
0x18001bff7  jz      short loc_18001C000
0x18001bff9  mov     ebx, 4
0x18001bffe  jmp     short loc_18001C002
0x18001c000  xor     ebx, ebx
0x18001c002  mov     [rsp+48h+arg_18], 0
0x18001c00a  mov     r8, rdi
0x18001c00d  lea     rdx, [rsp+48h+arg_18]
0x18001c012  lea     rcx, [rsp+48h+var_10]
0x18001c017  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_b10ee6e6ef7c5de0120f1ae782ec39fd____long____lambda_b10ee6e6ef7c5de0120f1ae782ec39fd___
0x18001c01c  mov     rdi, [rax]
0x18001c01f  mov     qword ptr [rax], 0
0x18001c026  mov     rcx, [rsp+48h+var_10]
0x18001c02b  test    rcx, rcx
0x18001c02e  jz      short loc_18001C03E
0x18001c030  mov     [rsp+48h+var_10], 0
0x18001c039  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001c03e  mov     [rsp+48h+var_20], 0
0x18001c047  mov     [rsp+48h+var_28], rdi
0x18001c04c  xor     r9d, r9d
0x18001c04f  mov     r8d, esi
0x18001c052  lea     edx, [r9+20h]
0x18001c056  mov     ecx, ebx
0x18001c058  call    cs:__imp_SHTaskPoolQueueTask
0x18001c05e  mov     ebx, eax
0x18001c060  test    rdi, rdi
0x18001c063  jz      short loc_18001C075
0x18001c065  mov     rdx, [rdi]
0x18001c068  mov     rcx, rdi
0x18001c06b  mov     rax, [rdx+10h]
0x18001c06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c074  nop
0x18001c075  test    ebx, ebx
0x18001c077  cmovns  ebx, [rsp+48h+arg_18]
0x18001c07c  mov     eax, ebx
0x18001c07e  mov     rbx, [rsp+48h+arg_8]
0x18001c083  mov     rsi, [rsp+48h+arg_10]
0x18001c088  add     rsp, 40h
0x18001c08c  pop     rdi
0x18001c08d  retn
```
