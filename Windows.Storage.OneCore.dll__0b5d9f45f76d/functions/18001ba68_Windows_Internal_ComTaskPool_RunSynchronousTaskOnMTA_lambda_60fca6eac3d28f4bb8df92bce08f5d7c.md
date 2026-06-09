# Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_60fca6eac3d28f4bb8df92bce08f5d7c___

- ea: `0x18001ba68`
- end: `0x18001bb42`
- name: `Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_60fca6eac3d28f4bb8df92bce08f5d7c___`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021a40`

## callees

- `0x180013e10`
- `0x18001b11c`
- `0x18001ba68`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001ba96`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001ba96`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001bb0c`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001bb0c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_60fca6eac3d28f4bb8df92bce08f5d7c___(
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
  v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_60fca6eac3d28f4bb8df92bce08f5d7c____long____lambda_60fca6eac3d28f4bb8df92bce08f5d7c___(
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
0x18001ba68  mov     rax, rsp
0x18001ba6b  mov     [rax+10h], rbx
0x18001ba6f  mov     [rax+18h], rsi
0x18001ba73  mov     [rax+8], ecx
0x18001ba76  push    rdi
0x18001ba77  sub     rsp, 40h
0x18001ba7b  mov     rdi, r8
0x18001ba7e  mov     esi, edx
0x18001ba80  mov     dword ptr [rax+8], 0
0x18001ba87  mov     dword ptr [rax-18h], 0
0x18001ba8e  lea     rdx, [rax-18h]; pAptQualifier
0x18001ba92  lea     rcx, [rax+8]; pAptType
0x18001ba96  call    cs:__imp_CoGetApartmentType
0x18001ba9c  test    eax, eax
0x18001ba9e  js      short loc_18001BAB4
0x18001baa0  mov     eax, [rsp+48h+arg_0]
0x18001baa4  test    eax, eax
0x18001baa6  jz      short loc_18001BAB4
0x18001baa8  cmp     eax, 3
0x18001baab  jz      short loc_18001BAB4
0x18001baad  mov     ebx, 4
0x18001bab2  jmp     short loc_18001BAB6
0x18001bab4  xor     ebx, ebx
0x18001bab6  mov     [rsp+48h+arg_18], 0
0x18001babe  mov     r8, rdi
0x18001bac1  lea     rdx, [rsp+48h+arg_18]
0x18001bac6  lea     rcx, [rsp+48h+var_10]
0x18001bacb  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_60fca6eac3d28f4bb8df92bce08f5d7c____long____lambda_60fca6eac3d28f4bb8df92bce08f5d7c___
0x18001bad0  mov     rdi, [rax]
0x18001bad3  mov     qword ptr [rax], 0
0x18001bada  mov     rcx, [rsp+48h+var_10]
0x18001badf  test    rcx, rcx
0x18001bae2  jz      short loc_18001BAF2
0x18001bae4  mov     [rsp+48h+var_10], 0
0x18001baed  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001baf2  mov     [rsp+48h+var_20], 0
0x18001bafb  mov     [rsp+48h+var_28], rdi
0x18001bb00  xor     r9d, r9d
0x18001bb03  mov     r8d, esi
0x18001bb06  lea     edx, [r9+20h]
0x18001bb0a  mov     ecx, ebx
0x18001bb0c  call    cs:__imp_SHTaskPoolQueueTask
0x18001bb12  mov     ebx, eax
0x18001bb14  test    rdi, rdi
0x18001bb17  jz      short loc_18001BB29
0x18001bb19  mov     rdx, [rdi]
0x18001bb1c  mov     rcx, rdi
0x18001bb1f  mov     rax, [rdx+10h]
0x18001bb23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb28  nop
0x18001bb29  test    ebx, ebx
0x18001bb2b  cmovns  ebx, [rsp+48h+arg_18]
0x18001bb30  mov     eax, ebx
0x18001bb32  mov     rbx, [rsp+48h+arg_8]
0x18001bb37  mov     rsi, [rsp+48h+arg_10]
0x18001bb3c  add     rsp, 40h
0x18001bb40  pop     rdi
0x18001bb41  retn
```
