# Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA<_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_>(Windows::Internal::TaskOptions,ulong,_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_ &&)

- ea: `0x180012680`
- end: `0x18001275a`
- name: `??$RunSynchronousTaskOnMTA@V_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_@@@ComTaskPool@Internal@Windows@@SAJW4TaskOptions@12@K$$QEAV_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013b70`

## callees

- `0x180012024`
- `0x180012680`
- `0x180013e10`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800126ae`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800126ae`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180012724`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180012724`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA<_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_>(
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
  v6 = Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CResultTaskWrapper<_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_>,long &,_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_>(
         &v11,
         (__int64)&v13,
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
0x180012680  mov     rax, rsp
0x180012683  mov     [rax+10h], rbx
0x180012687  mov     [rax+18h], rsi
0x18001268b  mov     [rax+8], ecx
0x18001268e  push    rdi
0x18001268f  sub     rsp, 40h
0x180012693  mov     rdi, r8
0x180012696  mov     esi, edx
0x180012698  mov     dword ptr [rax+8], 0
0x18001269f  mov     dword ptr [rax-18h], 0
0x1800126a6  lea     rdx, [rax-18h]; pAptQualifier
0x1800126aa  lea     rcx, [rax+8]; pAptType
0x1800126ae  call    cs:__imp_CoGetApartmentType
0x1800126b4  test    eax, eax
0x1800126b6  js      short loc_1800126CC
0x1800126b8  mov     eax, [rsp+48h+arg_0]
0x1800126bc  test    eax, eax
0x1800126be  jz      short loc_1800126CC
0x1800126c0  cmp     eax, 3
0x1800126c3  jz      short loc_1800126CC
0x1800126c5  mov     ebx, 4
0x1800126ca  jmp     short loc_1800126CE
0x1800126cc  xor     ebx, ebx
0x1800126ce  mov     [rsp+48h+arg_18], 0
0x1800126d6  mov     r8, rdi
0x1800126d9  lea     rdx, [rsp+48h+arg_18]
0x1800126de  lea     rcx, [rsp+48h+var_10]
0x1800126e3  call    ??$Make@V?$CResultTaskWrapper@V_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_@@@ComTaskPool@Internal@Windows@@AEAJV_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CResultTaskWrapper@V_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_@@@ComTaskPool@Internal@Windows@@@12@AEAJ$$QEAV_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CResultTaskWrapper<_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_>,long &,_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_>(long &,_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_ &&)
0x1800126e8  mov     rdi, [rax]
0x1800126eb  mov     qword ptr [rax], 0
0x1800126f2  mov     rcx, [rsp+48h+var_10]
0x1800126f7  test    rcx, rcx
0x1800126fa  jz      short loc_18001270A
0x1800126fc  mov     [rsp+48h+var_10], 0
0x180012705  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001270a  mov     [rsp+48h+var_20], 0
0x180012713  mov     [rsp+48h+var_28], rdi
0x180012718  xor     r9d, r9d
0x18001271b  mov     r8d, esi
0x18001271e  lea     edx, [r9+20h]
0x180012722  mov     ecx, ebx
0x180012724  call    cs:__imp_SHTaskPoolQueueTask
0x18001272a  mov     ebx, eax
0x18001272c  test    rdi, rdi
0x18001272f  jz      short loc_180012741
0x180012731  mov     rdx, [rdi]
0x180012734  mov     rcx, rdi
0x180012737  mov     rax, [rdx+10h]
0x18001273b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012740  nop
0x180012741  test    ebx, ebx
0x180012743  cmovns  ebx, [rsp+48h+arg_18]
0x180012748  mov     eax, ebx
0x18001274a  mov     rbx, [rsp+48h+arg_8]
0x18001274f  mov     rsi, [rsp+48h+arg_10]
0x180012754  add     rsp, 40h
0x180012758  pop     rdi
0x180012759  retn
```
