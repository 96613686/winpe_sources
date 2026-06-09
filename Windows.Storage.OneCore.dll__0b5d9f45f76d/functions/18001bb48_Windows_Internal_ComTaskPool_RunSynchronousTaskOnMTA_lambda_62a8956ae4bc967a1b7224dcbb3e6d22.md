# Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_62a8956ae4bc967a1b7224dcbb3e6d22___

- ea: `0x18001bb48`
- end: `0x18001bc22`
- name: `Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_62a8956ae4bc967a1b7224dcbb3e6d22___`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021820`

## callees

- `0x180013e10`
- `0x18001b1e8`
- `0x18001bb48`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001bb76`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001bb76`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001bbec`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001bbec`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_62a8956ae4bc967a1b7224dcbb3e6d22___(
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
  v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_62a8956ae4bc967a1b7224dcbb3e6d22____long____lambda_62a8956ae4bc967a1b7224dcbb3e6d22___(
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
0x18001bb48  mov     rax, rsp
0x18001bb4b  mov     [rax+10h], rbx
0x18001bb4f  mov     [rax+18h], rsi
0x18001bb53  mov     [rax+8], ecx
0x18001bb56  push    rdi
0x18001bb57  sub     rsp, 40h
0x18001bb5b  mov     rdi, r8
0x18001bb5e  mov     esi, edx
0x18001bb60  mov     dword ptr [rax+8], 0
0x18001bb67  mov     dword ptr [rax-18h], 0
0x18001bb6e  lea     rdx, [rax-18h]; pAptQualifier
0x18001bb72  lea     rcx, [rax+8]; pAptType
0x18001bb76  call    cs:__imp_CoGetApartmentType
0x18001bb7c  test    eax, eax
0x18001bb7e  js      short loc_18001BB94
0x18001bb80  mov     eax, [rsp+48h+arg_0]
0x18001bb84  test    eax, eax
0x18001bb86  jz      short loc_18001BB94
0x18001bb88  cmp     eax, 3
0x18001bb8b  jz      short loc_18001BB94
0x18001bb8d  mov     ebx, 4
0x18001bb92  jmp     short loc_18001BB96
0x18001bb94  xor     ebx, ebx
0x18001bb96  mov     [rsp+48h+arg_18], 0
0x18001bb9e  mov     r8, rdi
0x18001bba1  lea     rdx, [rsp+48h+arg_18]
0x18001bba6  lea     rcx, [rsp+48h+var_10]
0x18001bbab  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_62a8956ae4bc967a1b7224dcbb3e6d22____long____lambda_62a8956ae4bc967a1b7224dcbb3e6d22___
0x18001bbb0  mov     rdi, [rax]
0x18001bbb3  mov     qword ptr [rax], 0
0x18001bbba  mov     rcx, [rsp+48h+var_10]
0x18001bbbf  test    rcx, rcx
0x18001bbc2  jz      short loc_18001BBD2
0x18001bbc4  mov     [rsp+48h+var_10], 0
0x18001bbcd  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001bbd2  mov     [rsp+48h+var_20], 0
0x18001bbdb  mov     [rsp+48h+var_28], rdi
0x18001bbe0  xor     r9d, r9d
0x18001bbe3  mov     r8d, esi
0x18001bbe6  lea     edx, [r9+20h]
0x18001bbea  mov     ecx, ebx
0x18001bbec  call    cs:__imp_SHTaskPoolQueueTask
0x18001bbf2  mov     ebx, eax
0x18001bbf4  test    rdi, rdi
0x18001bbf7  jz      short loc_18001BC09
0x18001bbf9  mov     rdx, [rdi]
0x18001bbfc  mov     rcx, rdi
0x18001bbff  mov     rax, [rdx+10h]
0x18001bc03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc08  nop
0x18001bc09  test    ebx, ebx
0x18001bc0b  cmovns  ebx, [rsp+48h+arg_18]
0x18001bc10  mov     eax, ebx
0x18001bc12  mov     rbx, [rsp+48h+arg_8]
0x18001bc17  mov     rsi, [rsp+48h+arg_10]
0x18001bc1c  add     rsp, 40h
0x18001bc20  pop     rdi
0x18001bc21  retn
```
