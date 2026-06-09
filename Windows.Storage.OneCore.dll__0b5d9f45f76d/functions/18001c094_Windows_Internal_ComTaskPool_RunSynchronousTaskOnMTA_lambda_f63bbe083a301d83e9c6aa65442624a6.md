# Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_f63bbe083a301d83e9c6aa65442624a6___

- ea: `0x18001c094`
- end: `0x18001c16e`
- name: `Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_f63bbe083a301d83e9c6aa65442624a6___`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021610`

## callees

- `0x180013e10`
- `0x18001b628`
- `0x18001c094`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001c0c2`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001c0c2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001c138`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001c138`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_f63bbe083a301d83e9c6aa65442624a6___(
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
  v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_f63bbe083a301d83e9c6aa65442624a6____long____lambda_f63bbe083a301d83e9c6aa65442624a6___(
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
0x18001c094  mov     rax, rsp
0x18001c097  mov     [rax+10h], rbx
0x18001c09b  mov     [rax+18h], rsi
0x18001c09f  mov     [rax+8], ecx
0x18001c0a2  push    rdi
0x18001c0a3  sub     rsp, 40h
0x18001c0a7  mov     rdi, r8
0x18001c0aa  mov     esi, edx
0x18001c0ac  mov     dword ptr [rax+8], 0
0x18001c0b3  mov     dword ptr [rax-18h], 0
0x18001c0ba  lea     rdx, [rax-18h]; pAptQualifier
0x18001c0be  lea     rcx, [rax+8]; pAptType
0x18001c0c2  call    cs:__imp_CoGetApartmentType
0x18001c0c8  test    eax, eax
0x18001c0ca  js      short loc_18001C0E0
0x18001c0cc  mov     eax, [rsp+48h+arg_0]
0x18001c0d0  test    eax, eax
0x18001c0d2  jz      short loc_18001C0E0
0x18001c0d4  cmp     eax, 3
0x18001c0d7  jz      short loc_18001C0E0
0x18001c0d9  mov     ebx, 4
0x18001c0de  jmp     short loc_18001C0E2
0x18001c0e0  xor     ebx, ebx
0x18001c0e2  mov     [rsp+48h+arg_18], 0
0x18001c0ea  mov     r8, rdi
0x18001c0ed  lea     rdx, [rsp+48h+arg_18]
0x18001c0f2  lea     rcx, [rsp+48h+var_10]
0x18001c0f7  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_f63bbe083a301d83e9c6aa65442624a6____long____lambda_f63bbe083a301d83e9c6aa65442624a6___
0x18001c0fc  mov     rdi, [rax]
0x18001c0ff  mov     qword ptr [rax], 0
0x18001c106  mov     rcx, [rsp+48h+var_10]
0x18001c10b  test    rcx, rcx
0x18001c10e  jz      short loc_18001C11E
0x18001c110  mov     [rsp+48h+var_10], 0
0x18001c119  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001c11e  mov     [rsp+48h+var_20], 0
0x18001c127  mov     [rsp+48h+var_28], rdi
0x18001c12c  xor     r9d, r9d
0x18001c12f  mov     r8d, esi
0x18001c132  lea     edx, [r9+20h]
0x18001c136  mov     ecx, ebx
0x18001c138  call    cs:__imp_SHTaskPoolQueueTask
0x18001c13e  mov     ebx, eax
0x18001c140  test    rdi, rdi
0x18001c143  jz      short loc_18001C155
0x18001c145  mov     rdx, [rdi]
0x18001c148  mov     rcx, rdi
0x18001c14b  mov     rax, [rdx+10h]
0x18001c14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c154  nop
0x18001c155  test    ebx, ebx
0x18001c157  cmovns  ebx, [rsp+48h+arg_18]
0x18001c15c  mov     eax, ebx
0x18001c15e  mov     rbx, [rsp+48h+arg_8]
0x18001c163  mov     rsi, [rsp+48h+arg_10]
0x18001c168  add     rsp, 40h
0x18001c16c  pop     rdi
0x18001c16d  retn
```
