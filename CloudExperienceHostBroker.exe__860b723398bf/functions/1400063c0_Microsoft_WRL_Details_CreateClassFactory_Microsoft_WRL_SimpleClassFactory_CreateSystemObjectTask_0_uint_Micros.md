# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x1400063c0`
- end: `0x140006471`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCreateSystemObjectTask@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400063c0`
- `0x1400065e8`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v7; // ebx
  _DWORD *v9; // rbx
  int v10; // eax
  unsigned int v11; // edi
  _DWORD *v12; // [rsp+20h] [rbp-38h] BYREF

  v12 = 0;
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>,Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>,>(&v12);
  if ( v7 >= 0 )
  {
    v9 = v12;
    v12[5] = *a1;
    v10 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, __int64))v9)(v9, a3, a4);
    v11 = v10;
    if ( (*(_BYTE *)a1 & 1) != 0 )
    {
      if ( v10 < 0 )
      {
        v9[5] &= 0xFFFFFFFA;
      }
      else if ( (*(_BYTE *)a1 & 4) != 0 )
      {
        (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      }
      else
      {
        v9 = 0;
      }
    }
    if ( v9 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
    return v11;
  }
  else
  {
    if ( v12 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v12 + 16LL))(v12);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x1400063c0  push    rbx
0x1400063c2  push    rbp
0x1400063c3  push    rsi
0x1400063c4  push    rdi
0x1400063c5  sub     rsp, 38h
0x1400063c9  mov     rdi, r9
0x1400063cc  mov     rbp, r8
0x1400063cf  mov     rsi, rcx
0x1400063d2  mov     [rsp+58h+var_38], 0
0x1400063db  lea     rcx, [rsp+58h+var_38]
0x1400063e0  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VCreateSystemObjectTask@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VCreateSystemObjectTask@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>,Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0>,>(Microsoft::WRL::SimpleClassFactory<CreateSystemObjectTask,0> * *)
0x1400063e5  mov     ebx, eax
0x1400063e7  test    eax, eax
0x1400063e9  jns     short loc_140006406
0x1400063eb  mov     rcx, [rsp+58h+var_38]
0x1400063f0  test    rcx, rcx
0x1400063f3  jz      short loc_140006402
0x1400063f5  mov     rdx, [rcx]
0x1400063f8  mov     rax, [rdx+10h]
0x1400063fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006401  nop
0x140006402  mov     eax, ebx
0x140006404  jmp     short loc_140006468
0x140006406  mov     rbx, [rsp+58h+var_38]
0x14000640b  mov     eax, [rsi]
0x14000640d  mov     [rbx+14h], eax
0x140006410  mov     rax, [rbx]
0x140006413  mov     r8, rdi
0x140006416  mov     rdx, rbp
0x140006419  mov     rcx, rbx
0x14000641c  mov     rax, [rax]
0x14000641f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006424  mov     edi, eax
0x140006426  test    byte ptr [rsi], 1
0x140006429  jz      short loc_140006451
0x14000642b  test    eax, eax
0x14000642d  js      short loc_14000644D
0x14000642f  test    byte ptr [rsi], 4
0x140006432  jz      short loc_140006449
0x140006434  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000643b  mov     rax, [rcx]
0x14000643e  mov     rax, [rax+8]
0x140006442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006447  jmp     short loc_140006451
0x140006449  xor     ebx, ebx
0x14000644b  jmp     short loc_140006451
0x14000644d  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x140006451  test    rbx, rbx
0x140006454  jz      short loc_140006466
0x140006456  mov     rax, [rbx]
0x140006459  mov     rcx, rbx
0x14000645c  mov     rax, [rax+10h]
0x140006460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006465  nop
0x140006466  mov     eax, edi
0x140006468  add     rsp, 38h
0x14000646c  pop     rdi
0x14000646d  pop     rsi
0x14000646e  pop     rbp
0x14000646f  pop     rbx
0x140006470  retn
```
