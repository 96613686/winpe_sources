# Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4__&___lambda_01fa8bf71aefe9d32f15bd03a3e807a4__&_

- ea: `0x180026b50`
- end: `0x180026be0`
- name: `Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4__&___lambda_01fa8bf71aefe9d32f15bd03a3e807a4__&_`
- size: `144`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026be8`

## callees

- `0x18000396c`
- `0x18001af70`
- `0x180020b20`
- `0x180026ae8`
- `0x180026b50`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4______lambda_01fa8bf71aefe9d32f15bd03a3e807a4____(
        __int64 *a1,
        __int64 a2)
{
  void *v4; // rax
  volatile int *v5; // rdx
  __int64 v6; // rdi
  void *v8; // [rsp+50h] [rbp+18h] BYREF
  void *v9; // [rsp+58h] [rbp+20h]

  *a1 = 0;
  v4 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v4;
  v9 = v4;
  if ( v4 )
  {
    v6 = Windows::Internal::ComTaskPool::CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4____::CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4______lambda_01fa8bf71aefe9d32f15bd03a3e807a4____(
           v4,
           a2);
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(
        *a1,
        v5);
    *a1 = v6;
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4______::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4______(&v8);
  return a1;
}

```

## disassembly

```asm
0x180026b50  mov     rax, rsp
0x180026b53  mov     [rax+10h], rbx
0x180026b57  mov     [rax+8], rcx
0x180026b5b  push    rdi
0x180026b5c  sub     rsp, 30h
0x180026b60  mov     rdi, rdx
0x180026b63  mov     rbx, rcx
0x180026b66  mov     dword ptr [rax-18h], 0
0x180026b6d  mov     qword ptr [rcx], 0
0x180026b74  mov     dword ptr [rax-18h], 1
0x180026b7b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026b82  mov     ecx, 38h ; '8'; unsigned __int64
0x180026b87  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026b8c  mov     [rsp+38h+arg_10], rax
0x180026b91  mov     [rsp+38h+arg_18], rax
0x180026b96  test    rax, rax
0x180026b99  jz      short loc_180026BC7
0x180026b9b  mov     [rsp+38h+var_10], rax
0x180026ba0  mov     rdx, rdi
0x180026ba3  mov     rcx, rax
0x180026ba6  call    Windows__Internal__ComTaskPool__CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4______CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4______lambda_01fa8bf71aefe9d32f15bd03a3e807a4____
0x180026bab  mov     rdi, rax
0x180026bae  mov     rcx, [rbx]
0x180026bb1  test    rcx, rcx
0x180026bb4  jz      short loc_180026BBB
0x180026bb6  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180026bbb  mov     [rbx], rdi
0x180026bbe  mov     [rsp+38h+arg_10], 0
0x180026bc7  lea     rcx, [rsp+38h+arg_10]
0x180026bcc  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4_________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4______
0x180026bd1  mov     rax, rbx
0x180026bd4  mov     rbx, [rsp+38h+arg_8]
0x180026bd9  add     rsp, 30h
0x180026bdd  pop     rdi
0x180026bde  retn
```
