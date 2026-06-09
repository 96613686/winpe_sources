# Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_7ba05ad01ccac0ac0d571139ec3757e5___

- ea: `0x18001bd14`
- end: `0x18001bdee`
- name: `Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_7ba05ad01ccac0ac0d571139ec3757e5___`
- size: `218`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021920`

## callees

- `0x180013e10`
- `0x18001b2a8`
- `0x18001bd14`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001bd42`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001bd42`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001bdb8`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001bdb8`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_7ba05ad01ccac0ac0d571139ec3757e5___(
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
  v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_7ba05ad01ccac0ac0d571139ec3757e5____long____lambda_7ba05ad01ccac0ac0d571139ec3757e5___(
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
0x18001bd14  mov     rax, rsp
0x18001bd17  mov     [rax+10h], rbx
0x18001bd1b  mov     [rax+18h], rsi
0x18001bd1f  mov     [rax+8], ecx
0x18001bd22  push    rdi
0x18001bd23  sub     rsp, 40h
0x18001bd27  mov     rdi, r8
0x18001bd2a  mov     esi, edx
0x18001bd2c  mov     dword ptr [rax+8], 0
0x18001bd33  mov     dword ptr [rax-18h], 0
0x18001bd3a  lea     rdx, [rax-18h]; pAptQualifier
0x18001bd3e  lea     rcx, [rax+8]; pAptType
0x18001bd42  call    cs:__imp_CoGetApartmentType
0x18001bd48  test    eax, eax
0x18001bd4a  js      short loc_18001BD60
0x18001bd4c  mov     eax, [rsp+48h+arg_0]
0x18001bd50  test    eax, eax
0x18001bd52  jz      short loc_18001BD60
0x18001bd54  cmp     eax, 3
0x18001bd57  jz      short loc_18001BD60
0x18001bd59  mov     ebx, 4
0x18001bd5e  jmp     short loc_18001BD62
0x18001bd60  xor     ebx, ebx
0x18001bd62  mov     [rsp+48h+arg_18], 0
0x18001bd6a  mov     r8, rdi
0x18001bd6d  lea     rdx, [rsp+48h+arg_18]
0x18001bd72  lea     rcx, [rsp+48h+var_10]
0x18001bd77  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_7ba05ad01ccac0ac0d571139ec3757e5____long____lambda_7ba05ad01ccac0ac0d571139ec3757e5___
0x18001bd7c  mov     rdi, [rax]
0x18001bd7f  mov     qword ptr [rax], 0
0x18001bd86  mov     rcx, [rsp+48h+var_10]
0x18001bd8b  test    rcx, rcx
0x18001bd8e  jz      short loc_18001BD9E
0x18001bd90  mov     [rsp+48h+var_10], 0
0x18001bd99  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001bd9e  mov     [rsp+48h+var_20], 0
0x18001bda7  mov     [rsp+48h+var_28], rdi
0x18001bdac  xor     r9d, r9d
0x18001bdaf  mov     r8d, esi
0x18001bdb2  lea     edx, [r9+20h]
0x18001bdb6  mov     ecx, ebx
0x18001bdb8  call    cs:__imp_SHTaskPoolQueueTask
0x18001bdbe  mov     ebx, eax
0x18001bdc0  test    rdi, rdi
0x18001bdc3  jz      short loc_18001BDD5
0x18001bdc5  mov     rdx, [rdi]
0x18001bdc8  mov     rcx, rdi
0x18001bdcb  mov     rax, [rdx+10h]
0x18001bdcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdd4  nop
0x18001bdd5  test    ebx, ebx
0x18001bdd7  cmovns  ebx, [rsp+48h+arg_18]
0x18001bddc  mov     eax, ebx
0x18001bdde  mov     rbx, [rsp+48h+arg_8]
0x18001bde3  mov     rsi, [rsp+48h+arg_10]
0x18001bde8  add     rsp, 40h
0x18001bdec  pop     rdi
0x18001bded  retn
```
