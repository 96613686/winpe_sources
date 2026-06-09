# Windows::Internal::ComTaskPool::QueueTask__lambda_01fa8bf71aefe9d32f15bd03a3e807a4__&_

- ea: `0x180026be8`
- end: `0x180026c69`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_01fa8bf71aefe9d32f15bd03a3e807a4__&_`
- size: `129`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800282c0`

## callees

- `0x180020b20`
- `0x180026b50`
- `0x180026be8`
- `0x180031010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180026c3f`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180026c3f`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__lambda_01fa8bf71aefe9d32f15bd03a3e807a4____(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edi
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF

  v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4______lambda_01fa8bf71aefe9d32f15bd03a3e807a4____(
                    v9,
                    a4);
  v6 = *v5;
  *v5 = 0;
  if ( v9[0] )
  {
    v9[0] = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  v7 = SHTaskPoolQueueTask(0, 4096, a3, 0, v6, 0);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v7;
}

```

## disassembly

```asm
0x180026be8  mov     [rsp+arg_0], rbx
0x180026bed  push    rdi
0x180026bee  sub     rsp, 40h
0x180026bf2  mov     edi, r8d
0x180026bf5  mov     rdx, r9
0x180026bf8  lea     rcx, [rsp+48h+var_18]
0x180026bfd  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4______lambda_01fa8bf71aefe9d32f15bd03a3e807a4____
0x180026c02  mov     rbx, [rax]
0x180026c05  mov     qword ptr [rax], 0
0x180026c0c  mov     rcx, [rsp+48h+var_18]
0x180026c11  test    rcx, rcx
0x180026c14  jz      short loc_180026C24
0x180026c16  mov     [rsp+48h+var_18], 0
0x180026c1f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180026c24  mov     [rsp+48h+var_20], 0
0x180026c2d  mov     [rsp+48h+var_28], rbx
0x180026c32  xor     r9d, r9d
0x180026c35  mov     r8d, edi
0x180026c38  mov     edx, 1000h
0x180026c3d  xor     ecx, ecx
0x180026c3f  call    cs:__imp_SHTaskPoolQueueTask
0x180026c45  mov     edi, eax
0x180026c47  test    rbx, rbx
0x180026c4a  jz      short loc_180026C5C
0x180026c4c  mov     rdx, [rbx]
0x180026c4f  mov     rcx, rbx
0x180026c52  mov     rax, [rdx+10h]
0x180026c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c5b  nop
0x180026c5c  mov     eax, edi
0x180026c5e  mov     rbx, [rsp+48h+arg_0]
0x180026c63  add     rsp, 40h
0x180026c67  pop     rdi
0x180026c68  retn
```
