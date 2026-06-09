# Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_b9edf738e17dc43f74c922ccb415010b__&___lambda_b9edf738e17dc43f74c922ccb415010b__&_

- ea: `0x18000cb90`
- end: `0x18000cc20`
- name: `Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_b9edf738e17dc43f74c922ccb415010b__&___lambda_b9edf738e17dc43f74c922ccb415010b__&_`
- size: `144`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cdbc`

## callees

- `0x18000396c`
- `0x1800091fc`
- `0x18000cb90`
- `0x18001af70`
- `0x180020b20`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_b9edf738e17dc43f74c922ccb415010b______lambda_b9edf738e17dc43f74c922ccb415010b____(
        __int64 *a1,
        __int64 a2)
{
  _QWORD *v4; // rax
  volatile int *v5; // rdx
  _QWORD *v6; // rdi
  _QWORD *v8; // [rsp+50h] [rbp+18h] BYREF
  _QWORD *v9; // [rsp+58h] [rbp+20h]

  *a1 = 0;
  v4 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v4;
  v9 = v4;
  if ( v4 )
  {
    v6 = Windows::Internal::ComTaskPool::CTaskWrapper__lambda_b9edf738e17dc43f74c922ccb415010b____::CTaskWrapper__lambda_b9edf738e17dc43f74c922ccb415010b______lambda_b9edf738e17dc43f74c922ccb415010b____(
           v4,
           a2);
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(
        *a1,
        v5);
    *a1 = (__int64)v6;
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4______::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4______(&v8);
  return a1;
}

```

## disassembly

```asm
0x18000cb90  mov     rax, rsp
0x18000cb93  mov     [rax+10h], rbx
0x18000cb97  mov     [rax+8], rcx
0x18000cb9b  push    rdi
0x18000cb9c  sub     rsp, 30h
0x18000cba0  mov     rdi, rdx
0x18000cba3  mov     rbx, rcx
0x18000cba6  mov     dword ptr [rax-18h], 0
0x18000cbad  mov     qword ptr [rcx], 0
0x18000cbb4  mov     dword ptr [rax-18h], 1
0x18000cbbb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cbc2  mov     ecx, 38h ; '8'; unsigned __int64
0x18000cbc7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cbcc  mov     [rsp+38h+arg_10], rax
0x18000cbd1  mov     [rsp+38h+arg_18], rax
0x18000cbd6  test    rax, rax
0x18000cbd9  jz      short loc_18000CC07
0x18000cbdb  mov     [rsp+38h+var_10], rax
0x18000cbe0  mov     rdx, rdi
0x18000cbe3  mov     rcx, rax
0x18000cbe6  call    Windows__Internal__ComTaskPool__CTaskWrapper__lambda_b9edf738e17dc43f74c922ccb415010b______CTaskWrapper__lambda_b9edf738e17dc43f74c922ccb415010b______lambda_b9edf738e17dc43f74c922ccb415010b____
0x18000cbeb  mov     rdi, rax
0x18000cbee  mov     rcx, [rbx]
0x18000cbf1  test    rcx, rcx
0x18000cbf4  jz      short loc_18000CBFB
0x18000cbf6  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18000cbfb  mov     [rbx], rdi
0x18000cbfe  mov     [rsp+38h+arg_10], 0
0x18000cc07  lea     rcx, [rsp+38h+arg_10]
0x18000cc0c  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4_________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_01fa8bf71aefe9d32f15bd03a3e807a4______
0x18000cc11  mov     rax, rbx
0x18000cc14  mov     rbx, [rsp+38h+arg_8]
0x18000cc19  add     rsp, 30h
0x18000cc1d  pop     rdi
0x18000cc1e  retn
```
