# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::GetWeakReference(IWeakReference * *)

- ea: `0x180005090`
- end: `0x180005128`
- name: `?GetWeakReference@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAppInfoFactoryBroker@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAPEAUIWeakReference@@@Z`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004250`
- `0x180004658`
- `0x180005090`
- `0x180006270`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::GetWeakReference(
        __int64 a1,
        struct IUnknown *a2)
{
  signed __int64 v2; // rbx
  __int64 v5; // rbx
  __int64 WeakReference; // rcx
  bool v8; // zf
  __int64 v9; // rax

  v2 = *(_QWORD *)(a1 + 48);
  a2->lpVtbl = 0;
  if ( v2 >= 0 )
  {
    WeakReference = (__int64)Microsoft::WRL::Details::CreateWeakReference((Microsoft::WRL::Details *)(a1 - 8), a2);
    if ( !WeakReference )
      return 2147942414LL;
    while ( 1 )
    {
      *(_DWORD *)(WeakReference + 16) = v2;
      v9 = _InterlockedCompareExchange64(
             (volatile signed __int64 *)(a1 + 48),
             (WeakReference >> 1) | 0x8000000000000000uLL,
             v2);
      v8 = v2 == v9;
      v2 = v9;
      if ( v8 )
        break;
      if ( v9 < 0 )
      {
        Microsoft::WRL::Details::WeakReferenceImpl::`vector deleting destructor'(
          (Microsoft::WRL::Details::WeakReferenceImpl *)WeakReference,
          1u);
        goto LABEL_2;
      }
    }
    a2->lpVtbl = (struct IUnknownVtbl *)WeakReference;
  }
  else
  {
LABEL_2:
    v5 = 2 * v2;
    Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v5 + 12), (volatile int *)a2);
    a2->lpVtbl = (struct IUnknownVtbl *)v5;
  }
  return 0;
}

```

## disassembly

```asm
0x180005090  mov     [rsp+arg_0], rbx
0x180005095  mov     [rsp+arg_8], rsi
0x18000509a  push    rdi
0x18000509b  sub     rsp, 20h
0x18000509f  mov     rbx, [rcx+30h]
0x1800050a3  mov     rdi, rdx
0x1800050a6  mov     qword ptr [rdx], 0
0x1800050ad  mov     rsi, rcx
0x1800050b0  test    rbx, rbx
0x1800050b3  jns     short loc_1800050C6
0x1800050b5  add     rbx, rbx
0x1800050b8  lea     rcx, [rbx+0Ch]; this
0x1800050bc  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x1800050c1  mov     [rdi], rbx
0x1800050c4  jmp     short loc_180005116
0x1800050c6  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x1800050ca  call    ?CreateWeakReference@Details@WRL@Microsoft@@YAPEAVWeakReferenceImpl@123@PEAUIUnknown@@@Z; Microsoft::WRL::Details::CreateWeakReference(IUnknown *)
0x1800050cf  mov     rcx, rax; this
0x1800050d2  test    rax, rax
0x1800050d5  jnz     short loc_1800050DE
0x1800050d7  mov     eax, 8007000Eh
0x1800050dc  jmp     short loc_180005118
0x1800050de  mov     rdx, rcx
0x1800050e1  mov     rax, 8000000000000000h
0x1800050eb  sar     rdx, 1
0x1800050ee  or      rdx, rax
0x1800050f1  mov     [rcx+10h], ebx
0x1800050f4  mov     rax, rbx
0x1800050f7  lock cmpxchg [rsi+30h], rdx
0x1800050fd  mov     rbx, rax
0x180005100  jz      short loc_180005113
0x180005102  test    rax, rax
0x180005105  jns     short loc_1800050F1
0x180005107  mov     edx, 1; unsigned int
0x18000510c  call    ??_EWeakReferenceImpl@Details@WRL@Microsoft@@UEAAPEAXI@Z; Microsoft::WRL::Details::WeakReferenceImpl::`vector deleting destructor'(uint)
0x180005111  jmp     short loc_1800050B5
0x180005113  mov     [rdi], rcx
0x180005116  xor     eax, eax
0x180005118  mov     rbx, [rsp+28h+arg_0]
0x18000511d  mov     rsi, [rsp+28h+arg_8]
0x180005122  add     rsp, 20h
0x180005126  pop     rdi
0x180005127  retn
```
