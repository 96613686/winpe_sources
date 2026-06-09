# Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_95afcd39453873b60d63f0d5792d158c___

- ea: `0x18001bed4`
- end: `0x18001bfae`
- name: `Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_95afcd39453873b60d63f0d5792d158c___`
- size: `218`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020f50`

## callees

- `0x180013e10`
- `0x18001b470`
- `0x18001bed4`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001bf02`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001bf02`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001bf78`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001bf78`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_95afcd39453873b60d63f0d5792d158c___(
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
  v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_95afcd39453873b60d63f0d5792d158c____long____lambda_95afcd39453873b60d63f0d5792d158c___(
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
0x18001bed4  mov     rax, rsp
0x18001bed7  mov     [rax+10h], rbx
0x18001bedb  mov     [rax+18h], rsi
0x18001bedf  mov     [rax+8], ecx
0x18001bee2  push    rdi
0x18001bee3  sub     rsp, 40h
0x18001bee7  mov     rdi, r8
0x18001beea  mov     esi, edx
0x18001beec  mov     dword ptr [rax+8], 0
0x18001bef3  mov     dword ptr [rax-18h], 0
0x18001befa  lea     rdx, [rax-18h]; pAptQualifier
0x18001befe  lea     rcx, [rax+8]; pAptType
0x18001bf02  call    cs:__imp_CoGetApartmentType
0x18001bf08  test    eax, eax
0x18001bf0a  js      short loc_18001BF20
0x18001bf0c  mov     eax, [rsp+48h+arg_0]
0x18001bf10  test    eax, eax
0x18001bf12  jz      short loc_18001BF20
0x18001bf14  cmp     eax, 3
0x18001bf17  jz      short loc_18001BF20
0x18001bf19  mov     ebx, 4
0x18001bf1e  jmp     short loc_18001BF22
0x18001bf20  xor     ebx, ebx
0x18001bf22  mov     [rsp+48h+arg_18], 0
0x18001bf2a  mov     r8, rdi
0x18001bf2d  lea     rdx, [rsp+48h+arg_18]
0x18001bf32  lea     rcx, [rsp+48h+var_10]
0x18001bf37  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_95afcd39453873b60d63f0d5792d158c____long____lambda_95afcd39453873b60d63f0d5792d158c___
0x18001bf3c  mov     rdi, [rax]
0x18001bf3f  mov     qword ptr [rax], 0
0x18001bf46  mov     rcx, [rsp+48h+var_10]
0x18001bf4b  test    rcx, rcx
0x18001bf4e  jz      short loc_18001BF5E
0x18001bf50  mov     [rsp+48h+var_10], 0
0x18001bf59  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001bf5e  mov     [rsp+48h+var_20], 0
0x18001bf67  mov     [rsp+48h+var_28], rdi
0x18001bf6c  xor     r9d, r9d
0x18001bf6f  mov     r8d, esi
0x18001bf72  lea     edx, [r9+20h]
0x18001bf76  mov     ecx, ebx
0x18001bf78  call    cs:__imp_SHTaskPoolQueueTask
0x18001bf7e  mov     ebx, eax
0x18001bf80  test    rdi, rdi
0x18001bf83  jz      short loc_18001BF95
0x18001bf85  mov     rdx, [rdi]
0x18001bf88  mov     rcx, rdi
0x18001bf8b  mov     rax, [rdx+10h]
0x18001bf8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf94  nop
0x18001bf95  test    ebx, ebx
0x18001bf97  cmovns  ebx, [rsp+48h+arg_18]
0x18001bf9c  mov     eax, ebx
0x18001bf9e  mov     rbx, [rsp+48h+arg_8]
0x18001bfa3  mov     rsi, [rsp+48h+arg_10]
0x18001bfa8  add     rsp, 40h
0x18001bfac  pop     rdi
0x18001bfad  retn
```
